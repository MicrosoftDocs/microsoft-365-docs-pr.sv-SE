---
title: Sök efter hot på olika enheter, e-postmeddelanden, appar och identiteter med avancerad sökning
description: Studera vanliga sökscenarier och exempelfrågor som täcker enheter, e-postmeddelanden, appar och identiteter.
keywords: avancerad sökning, Office365-data, Windows-enheter, Office365-e-postmeddelanden normalisera, e-postmeddelanden, appar, identiteter, sökning efter hot, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932256"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Leta efter hot på olika enheter, e-postmeddelanden, appar och identiteter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[Med avancerad](advanced-hunting-overview.md) sökning i Microsoft 365 Defender kan du proaktivt leta efter hot i:
- Enheter som hanteras av Microsoft Defender för Endpoint
- E-postmeddelanden som bearbetas av Microsoft 365
- Aktiviteter i molnappen, autentiseringshändelser och domänkontrollantaktiviteter som spåras av Microsoft Cloud App Security och Microsoft Defender för identitet

Med den här synlighetsnivån kan du snabbt leta efter hot som passerar genom delar av nätverket, inklusive avancerade intrång som anländer på e-post eller webben, förhöjda lokala behörigheter, skaffa behörighet för domäner och flytta dem till andra enheter. 

Här är allmänna tekniker och exempelfrågor som baseras på olika sökscenarier som kan hjälpa dig att utforska hur du kan skapa frågor när du letar efter så avancerade hot.

## <a name="get-entity-info"></a>Hämta entitetsinformation
Använd dessa frågor för att lära dig hur du snabbt kan få information om användarkonton, enheter och filer. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Hämta användarkonton från e-postadresser
När du skapar frågor i tabeller [som](advanced-hunting-schema-tables.md)täcker enheter och e-postmeddelanden måste du förmodligen hämta användarnamn från avsändares eller mottagares e-postadresser. I allmänhet kan du göra detta för antingen mottagare eller avsändaradress med *den lokala värden* från e-postadressen.

I avsnittet nedan använder vi funktionen [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto för att extrahera den lokala värden direkt före från mottagarens `@` e-postadresser i `RecipientEmailAddress` kolumnen.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
Frågan nedan visar hur det här avsnittet kan användas:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Slå samman tabellen IdentityInfo

Du kan få kontonamn och annan kontoinformation genom att slå ihop eller koppla [tabellen IdentityInfo.](advanced-hunting-identityinfo-table.md) Frågan nedan hämtar listan över identifieringar av nätfiske och skadlig programvara från tabellen [EmailEvents](advanced-hunting-emailevents-table.md) och ansluter sedan informationen till tabellen för att få detaljerad `IdentityInfo` information om varje mottagare. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Hämta enhetsinformation
Det [avancerade sökschemat](advanced-hunting-schema-tables.md) innehåller omfattande enhetsinformation i olika tabeller. Till exempel innehåller [tabellen DeviceInfo omfattande](advanced-hunting-deviceinfo-table.md) enhetsinformation baserat på händelsedata som aggregeras regelbundet. Den här frågan använder tabellen för att kontrollera om en potentiellt komprometterad användare () har loggat in på någon enhet och visar sedan aviseringarna som har utlösts på `DeviceInfo` `<account-name>` dessa enheter.

>[!Tip]
> Den här frågan `kind=inner` används för att ange en inre [koppling,](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)vilket förhindrar avduplicering av värden på vänster sida `DeviceId` för.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>Scenarier med visning

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Lista inloggningsaktiviteter för användare som har fått e-postmeddelanden som inte har zappeds
[ZAP (Zero-hour auto purge)](../office-365-security/zero-hour-auto-purge.md) adresserar skadliga e-postmeddelanden när de har tagits emot. Om ZAP misslyckas kan skadlig kod så småningom köras på enheten och konton kan bli komprometterade. Den här frågan söker efter inloggningsaktivitet som gjorts av mottagarna av e-postmeddelanden som inte har åtgärdats av ZAP.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Få inloggningsförsök för domänkonton som riktas av autentiseringsstöld
Den här frågan identifierar först alla aviseringar om autentiseringsuppgifter i `AlertInfo` tabellen. Därefter slås tabellen ihop eller kopplas, som den parsar för namnen på de riktade kontona och filtren för endast `AlertEvidence` domänkopplingade konton. Slutligen kontrolleras tabellen för `IdentityLogonEvents` att få alla inloggningsaktiviteter för de domän sammanfogade riktade kontona.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Kontrollera om filer från en känd skadlig avsändare finns på dina enheter
Om du känner till en e-postadress som skickar skadliga filer (), kan du köra den här frågan för att avgöra om filer från den här `MaliciousSender@example.com` avsändaren finns på dina enheter. Du kan till exempel använda den här frågan för att identifiera enheter som påverkas av en distribution till skadlig programvara.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Granska inloggningsförsök efter kvitto på skadlig e-post
Den här frågan hittar de 10 senaste inloggningarna som utförts av e-postmottagare inom 30 minuter efter att de fått kända skadliga e-postmeddelanden. Du kan använda den här frågan för att kontrollera om kontona för e-postmottagarna har komprometterats.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Granska PowerShell-aktiviteter efter e-postmeddelanden från känd avsändare
Skadliga e-postmeddelanden innehåller ofta dokument och andra särskilt utformade bifogade filer som kör PowerShell-kommandon för att leverera ytterligare nyttolaster. Om du är medveten om att e-postmeddelanden kommer från en känd avsändare ( ) kan du använda den här frågan för att lista och granska PowerShell-aktiviteter som inträffat inom 30 minuter efter att ett e-postmeddelande togs emot från `MaliciousSender@example.com` avsändaren.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
