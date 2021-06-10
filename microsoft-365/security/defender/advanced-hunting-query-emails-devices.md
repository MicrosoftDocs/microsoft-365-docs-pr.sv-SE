---
title: Sök efter hot på enheter, e-postmeddelanden, appar och identiteter med avancerad sökning
description: Studera vanliga scenarier för sökningar och exempelfrågor som täcker enheter, e-postmeddelanden, appar och identiteter.
keywords: avancerad sökning, Office365-data, Windows-enheter, Office365-e-postmeddelanden normalisera, e-postmeddelanden, appar, identiteter, sökning efter hot, sökning efter cyberhot, frågor, telemetri, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932971"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="ac66d-104">Jaga efter hot på olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="ac66d-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac66d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ac66d-105">**Applies to:**</span></span>
- <span data-ttu-id="ac66d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac66d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ac66d-107">[Med avancerad](advanced-hunting-overview.md) sökning i Microsoft 365 Defender kan du proaktivt leta efter hot i:</span><span class="sxs-lookup"><span data-stu-id="ac66d-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="ac66d-108">Enheter som hanteras av Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac66d-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ac66d-109">E-postmeddelanden behandlas av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac66d-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="ac66d-110">Aktiviteter i molnappen, autentiseringshändelser och domänkontrollanter spåras av Microsoft Cloud App Security och Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="ac66d-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="ac66d-111">Med den här synlighetsnivån kan du snabbt jaga efter hot som passerar delar av nätverket, inklusive avancerade intrång som anländer i e-post eller på webben, förhöjda lokala behörigheter, skaffa behörighet till domänautentiseringsuppgifter och flytta dem till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="ac66d-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="ac66d-112">Här hittar du allmänna tekniker och exempelfrågor som baseras på olika sökscenarier som kan hjälpa dig att utforska hur du kan skapa frågor när du letar efter så avancerade hot.</span><span class="sxs-lookup"><span data-stu-id="ac66d-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="ac66d-113">Hämta entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="ac66d-113">Get entity info</span></span>
<span data-ttu-id="ac66d-114">Använd de här frågorna för att lära dig hur du snabbt kan få information om användarkonton, enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="ac66d-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="ac66d-115">Hämta användarkonton från e-postadresser</span><span class="sxs-lookup"><span data-stu-id="ac66d-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="ac66d-116">När du skapar frågor i tabeller [som](advanced-hunting-schema-tables.md)täcker enheter och e-postmeddelanden, så måste du förmodligen hämta användarnamn från avsändares eller mottagares e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="ac66d-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="ac66d-117">I allmänhet kan du göra det åt mottagaren eller avsändarens adress med hjälp *av den lokala värden* från e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="ac66d-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="ac66d-118">I avsnittet nedan använder vi [funktionen tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto för att extrahera den lokala värden direkt före från mottagarens e-postadresser `@` i kolumnen `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="ac66d-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="ac66d-119">Frågan nedan visar hur det här avsnittet kan användas:</span><span class="sxs-lookup"><span data-stu-id="ac66d-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="ac66d-120">Slå samman tabellen IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ac66d-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="ac66d-121">Du kan få kontonamn och annan kontoinformation genom att slå samman eller sammanfoga [tabellen IdentityInfo.](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="ac66d-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="ac66d-122">Frågan nedan hämtar listan över identifieringar av nätfiske och skadlig kod från tabellen [EmailEvents](advanced-hunting-emailevents-table.md) och ansluter sedan informationen till tabellen för att få detaljerad `IdentityInfo` information om varje mottagare.</span><span class="sxs-lookup"><span data-stu-id="ac66d-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="ac66d-123">Hämta enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="ac66d-123">Get device information</span></span>
<span data-ttu-id="ac66d-124">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) innehåller omfattande enhetsinformation i olika tabeller.</span><span class="sxs-lookup"><span data-stu-id="ac66d-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="ac66d-125">I tabellen [DeviceInfo finns till exempel](advanced-hunting-deviceinfo-table.md) omfattande enhetsinformation baserad på händelsedata som aggregeras regelbundet.</span><span class="sxs-lookup"><span data-stu-id="ac66d-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="ac66d-126">Den här frågan använder tabellen för att kontrollera om en potentiellt komprometterad användare () har loggat in på någon enhet och visar sedan aviseringarna som har utlösts `DeviceInfo` `<account-name>` på dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="ac66d-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="ac66d-127">Den här frågan `kind=inner` används för att ange en inre [koppling,](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)vilket förhindrar avduplicering av värden på vänster sida för `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="ac66d-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="ac66d-128">Scenarier för scenarier</span><span class="sxs-lookup"><span data-stu-id="ac66d-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="ac66d-129">Lista inloggningsaktiviteter för användare som har fått e-postmeddelanden som inte har zapped</span><span class="sxs-lookup"><span data-stu-id="ac66d-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="ac66d-130">[ZAP (Zero-hour auto purge) adresserar skadliga e-postmeddelanden](../office-365-security/zero-hour-auto-purge.md) efter att de har tagits emot.</span><span class="sxs-lookup"><span data-stu-id="ac66d-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="ac66d-131">Om ZAP misslyckas kan skadlig kod så småningom köras på enheten och konton kan bli hackade.</span><span class="sxs-lookup"><span data-stu-id="ac66d-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="ac66d-132">Den här frågan kontrollerar inloggningsaktivitet som görs av mottagarna av e-postmeddelanden som inte har adresserts av ZAP.</span><span class="sxs-lookup"><span data-stu-id="ac66d-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="ac66d-133">Få inloggningsförsök från domänkonton som riktas av autentiseringsstöld</span><span class="sxs-lookup"><span data-stu-id="ac66d-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="ac66d-134">Den här frågan identifierar först alla aviseringar om autentiseringsåtkomst i `AlertInfo` tabellen.</span><span class="sxs-lookup"><span data-stu-id="ac66d-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="ac66d-135">Sedan slås tabellen samman eller kopplas, som den parsar för namnen på de riktade kontona och filtren `AlertEvidence` för endast domänsammanslagna konton.</span><span class="sxs-lookup"><span data-stu-id="ac66d-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="ac66d-136">Slutligen kontrolleras tabellen för `IdentityLogonEvents` att få alla inloggningsaktiviteter från domänmedlemna riktade konton.</span><span class="sxs-lookup"><span data-stu-id="ac66d-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="ac66d-137">Kontrollera om filer från en känd avsändare finns på dina enheter</span><span class="sxs-lookup"><span data-stu-id="ac66d-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="ac66d-138">Om du känner till en e-postadress som skickar skadliga filer ( ) kan du köra den här frågan för att avgöra om filer från den här `MaliciousSender@example.com` avsändaren finns på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="ac66d-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="ac66d-139">Du kan till exempel använda den här frågan för att identifiera enheter som påverkas av en distributionskampanj för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="ac66d-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="ac66d-140">Granska inloggningsförsök efter kvitto på skadliga e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="ac66d-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="ac66d-141">Den här frågan hittar de 10 senaste inloggningarna som utförts av e-postmottagare inom 30 minuter efter att de fått kända skadliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ac66d-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="ac66d-142">Du kan använda den här frågan för att kontrollera om e-postmottagarnas konton har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="ac66d-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="ac66d-143">Granska PowerShell-aktiviteter efter e-postmeddelanden från känd avsändare</span><span class="sxs-lookup"><span data-stu-id="ac66d-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="ac66d-144">Skadliga e-postmeddelanden innehåller ofta dokument och andra särskilt utformade bifogade filer som kör PowerShell-kommandon för att leverera ytterligare nyttolaster.</span><span class="sxs-lookup"><span data-stu-id="ac66d-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="ac66d-145">Om du är medveten om e-postmeddelanden från en känd avsändare ( ) kan du använda den här frågan för att lista och granska PowerShell-aktiviteter som inträffade inom 30 minuter efter att ett e-postmeddelande togs emot från `MaliciousSender@example.com` avsändaren.</span><span class="sxs-lookup"><span data-stu-id="ac66d-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="ac66d-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ac66d-146">Related topics</span></span>
- [<span data-ttu-id="ac66d-147">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ac66d-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ac66d-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="ac66d-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ac66d-149">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="ac66d-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ac66d-150">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="ac66d-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ac66d-151">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="ac66d-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ac66d-152">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="ac66d-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)