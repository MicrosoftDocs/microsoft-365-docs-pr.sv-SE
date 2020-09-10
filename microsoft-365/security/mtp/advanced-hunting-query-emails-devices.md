---
title: Jakt efter hot på enheter, e-postmeddelanden, appar och identiteter med avancerad jakt
description: Studera vanliga jakt scenarier och exempel frågor som täcker enheter, e-postmeddelanden, appar och identiteter.
keywords: Avancerad jakt, Office365 data, Windows-enheter, Office365 e-post normalisera, e-post, appar, identiteter, Hot jakt, cyberterrorism hot jakt, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c24f5891573b8541a97a35d228c57642766fe4a0
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419150"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Jakt efter hot på enheter, e-postmeddelanden, appar och identiteter

**Gäller för:**
- Microsoft Hotskydd

Med [Avancerad jakt](advanced-hunting-overview.md) i Microsoft Threat Protection kan du proaktivt efter problem i:
- Enheter som hanteras av Microsoft Defender ATP
- E-postmeddelanden som bearbetas av Microsoft 365
- Molnprogram aktiviteter, autentiseringsnivåer och aktiviteter för domän kontrol Lanterna spåras av Microsoft Cloud App Security och Azure ATP

Med den här synbarheten kan du snabbt hitta hot som rör fram delar av nätverket, inklusive sofistikerade intrång som kommer via e-post eller webben, öka behörigheterna, skaffa privilegierade domänautentiseringsuppgifter och flytta dem senare till alla dina enheter. 

Här är allmänna tekniker och urvals frågor baserat på olika jakt scenarier som hjälper dig att upptäcka hur du kan skapa frågor när jakt efter sådana avancerade hot.

## <a name="get-entity-info"></a>Hämta entitetsinformation
Använd de här frågorna för att få reda på hur du snabbt får information om användar konton, enheter och filer. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Skaffa användar konton från e-postadresser
När du skapar frågor över [tabeller som täcker enheter och e-post](advanced-hunting-schema-tables.md)måste du antagligen skaffa användar konto namn från avsändare eller mottagares e-postadresser. Du kan vanligt vis göra detta för antingen mottagare eller avsändar adress via den *lokala värden* från e-postadressen.

I det här avsnittet nedan använder vi funktionen [toString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto för att extrahera den lokala värd rättigheten före `@` från mottagarens e-postadresser i kolumnen `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
I frågan nedan visas hur det här avsnittet kan användas:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Slå samman tabellen IdentityInfo

Du kan skaffa konto namn och annan konto information genom att sammanfoga eller gå med i [IdentityInfo-tabellen](advanced-hunting-identityinfo-table.md). Frågan nedan erhåller listan över nät fiske och skadlig program vara som identifieras från [tabellen EmailEvents](advanced-hunting-emailevents-table.md) och sedan kopplas till den informationen med `IdentityInfo` tabellen för att få detaljerad information om varje mottagare. 

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

### <a name="get-device-information"></a>Hämta enhets information
Det [avancerade jakt schemat](advanced-hunting-schema-tables.md) ger omfattande enhets information i olika tabeller. [Tabellen deviceinfo](advanced-hunting-deviceinfo-table.md) innehåller till exempel omfattande enhets information baserat på händelse data som sammanlagts regelbundet. Den här frågan använder `DeviceInfo` tabellen för att kontrol lera om en potentiellt utsatt användare ( `<account-name>` ) har loggat in på några enheter och sedan en lista över de aviseringar som har Aktiver ATS på dessa enheter.

>[!Tip]
> Den här frågan används `kind=inner` för att ange en [inre koppling](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), som förhindrar avduplicering av vänster sid värden för `DeviceId` .

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

## <a name="hunting-scenarios"></a>Jakt scenarier

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Visa inloggnings aktiviteter för användare som fått e-post som inte zapped
[Automatisk rensning för en tom timme (Zap)](../office-365-security/zero-hour-auto-purge.md) tar emot skadlig e-post efter att de har mottagits. Om det inte fungerar kan det hända att skadlig kod kanske körs på enheten och lämnar konton. Den här frågan söker efter inloggnings aktiviteter som görs av mottagarna av e-postmeddelanden som inte kunde besvaras med ZAP.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Få inloggnings försök från domän konton riktade till stöld av autentiseringsuppgiften
Denna fråga identifierar först alla notifieringar om autentiseringsuppgifter i `AlertInfo` tabellen. Då sammanfogas eller kopplas `AlertEvidence` tabellen, vilket bara kan tolka namn på riktade konton och filter för domänbaserade konton. Slutligen kontrollerar den `IdentityLogonEvents` tabellen för att få alla inloggnings aktiviteter av domänbaserade riktade konton.

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Kontrol lera om filer från en känd angripare finns på dina enheter
Förutsatt att du känner till en e-postadress för att skicka skadliga filer ( `MaliciousSender@example.com` ) kan du köra den här frågan för att ta reda på om filer från den här avsändaren finns på din enhet. Du kan använda den här frågan, till exempel för att identifiera enheter som påverkas av en distributions kampanj med skadlig kod.

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Granska inloggnings försök efter mottagning av illasinnade e-postmeddelanden
Den här frågan hittar de tio senaste inloggningarna som utförs av e-postmottagarna inom 30 minuter efter att de fått kända skadliga meddelanden. Du kan använda den här frågan för att kontrol lera om kontona i e-postmottagaren har komprometterats.

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Granska PowerShell-aktiviteter efter mottagning av e-postmeddelanden från känd skadlig avsändare
Illvilliga e-postmeddelanden innehåller ofta dokument och andra särskilt utformade bilagor som kör PowerShell-kommandon för att leverera extra nytto laster. Om du känner till e-postmeddelanden som kommer från en känd angripare ( `MaliciousSender@example.com` ) kan du använda den här frågan för att visa och granska PowerShell-aktiviteter som skedde inom 30 minuter efter att ett e-postmeddelande togs emot från avsändaren.  

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