---
title: Sök efter hot på enheter, e-postmeddelanden, appar och identiteter med avancerad sökning
description: Studera vanliga scenarier för sökningar och exempelfrågor som täcker enheter, e-postmeddelanden, appar och identiteter.
keywords: avancerad sökning, Office365-data, Windows-enheter, Office365-e-postmeddelanden normalisera, e-postmeddelanden, appar, identiteter, sökning efter hot, sökning, sökning, frågor, telemetri, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964879"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="fe297-104">Jaga efter hot på olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="fe297-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fe297-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fe297-105">**Applies to:**</span></span>
- <span data-ttu-id="fe297-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe297-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fe297-107">[Med avancerad](advanced-hunting-overview.md) sökning Microsoft 365 Defender du proaktivt leta efter hot i:</span><span class="sxs-lookup"><span data-stu-id="fe297-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="fe297-108">Enheter som hanteras av Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe297-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="fe297-109">E-postmeddelanden behandlas av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe297-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="fe297-110">Aktiviteter i molnappen, autentiseringshändelser och domänkontrollanter spåras av Microsoft Cloud App Security och Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="fe297-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="fe297-111">Med den här synlighetsnivån kan du snabbt jaga efter hot som passerar delar av nätverket, inklusive avancerade intrång som anländer i e-post eller på webben, förhöjda lokala behörigheter, skaffa behörighet till domänautentiseringsuppgifter och flytta dem till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="fe297-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="fe297-112">Här hittar du allmänna tekniker och exempelfrågor som baseras på olika sökscenarier som kan hjälpa dig att utforska hur du kan skapa frågor när du letar efter så avancerade hot.</span><span class="sxs-lookup"><span data-stu-id="fe297-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="fe297-113">Hämta entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="fe297-113">Get entity info</span></span>
<span data-ttu-id="fe297-114">Använd de här frågorna för att lära dig hur du snabbt kan få information om användarkonton, enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="fe297-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="fe297-115">Hämta användarkonton från e-postadresser</span><span class="sxs-lookup"><span data-stu-id="fe297-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="fe297-116">När du skapar frågor i tabeller [som](advanced-hunting-schema-tables.md)täcker enheter och e-postmeddelanden, så måste du förmodligen hämta användarnamn från avsändares eller mottagares e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="fe297-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="fe297-117">I allmänhet kan du göra det åt mottagaren eller avsändarens adress med hjälp *av den lokala värden* från e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="fe297-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="fe297-118">I avsnittet nedan använder vi [funktionen tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto för att extrahera den lokala värden direkt före från mottagarens e-postadresser `@` i kolumnen `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="fe297-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="fe297-119">Frågan nedan visar hur det här avsnittet kan användas:</span><span class="sxs-lookup"><span data-stu-id="fe297-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="fe297-120">Slå samman tabellen IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="fe297-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="fe297-121">Du kan få kontonamn och annan kontoinformation genom att slå samman eller sammanfoga [tabellen IdentityInfo.](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="fe297-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="fe297-122">Frågan nedan hämtar listan över identifieringar av nätfiske och skadlig kod från tabellen [EmailEvents](advanced-hunting-emailevents-table.md) och ansluter sedan informationen till tabellen för att få detaljerad `IdentityInfo` information om varje mottagare.</span><span class="sxs-lookup"><span data-stu-id="fe297-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="fe297-123">Hämta enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="fe297-123">Get device information</span></span>
<span data-ttu-id="fe297-124">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) innehåller omfattande enhetsinformation i olika tabeller.</span><span class="sxs-lookup"><span data-stu-id="fe297-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="fe297-125">I tabellen [DeviceInfo finns till exempel](advanced-hunting-deviceinfo-table.md) omfattande enhetsinformation baserad på händelsedata som aggregeras regelbundet.</span><span class="sxs-lookup"><span data-stu-id="fe297-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="fe297-126">Den här frågan använder tabellen för att kontrollera om en potentiellt komprometterad användare () har loggat in på någon enhet och visar sedan aviseringarna som har utlösts `DeviceInfo` `<account-name>` på dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="fe297-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="fe297-127">Den här frågan `kind=inner` används för att ange en inre [koppling,](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)vilket förhindrar avduplicering av värden på vänster sida för `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="fe297-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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


### <a name="get-file-event-information"></a><span data-ttu-id="fe297-128">Hämta filhändelseinformation</span><span class="sxs-lookup"><span data-stu-id="fe297-128">Get file event information</span></span>

<span data-ttu-id="fe297-129">Använd följande fråga för att få information om filrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="fe297-129">Use the following query to get information on file related events.</span></span> 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a><span data-ttu-id="fe297-130">Hämta information om nätverkshändelse</span><span class="sxs-lookup"><span data-stu-id="fe297-130">Get network event information</span></span>

<span data-ttu-id="fe297-131">Använd följande fråga för att få information om nätverksrelaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="fe297-131">Use the following query to get information on network related events.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a><span data-ttu-id="fe297-132">Hämta versionsinformation för enhetsagenter</span><span class="sxs-lookup"><span data-stu-id="fe297-132">Get device agent version information</span></span>

<span data-ttu-id="fe297-133">Använd följande fråga för att köra versionen av agenten på en enhet.</span><span class="sxs-lookup"><span data-stu-id="fe297-133">Use the following query to get the version of the agent running on a device.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a><span data-ttu-id="fe297-134">Exempelfråga för macOS-enheter</span><span class="sxs-lookup"><span data-stu-id="fe297-134">Example query for macOS devices</span></span>

<span data-ttu-id="fe297-135">Använd följande exempelfråga för att se alla enheter med macOS med en version som är äldre än Catalina.</span><span class="sxs-lookup"><span data-stu-id="fe297-135">Use the following example query to see all devices running macOS with a version older than Catalina.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a><span data-ttu-id="fe297-136">Hämta information om enhetsstatus</span><span class="sxs-lookup"><span data-stu-id="fe297-136">Get device status info</span></span>

<span data-ttu-id="fe297-137">Använd följande fråga för att få status för en enhet.</span><span class="sxs-lookup"><span data-stu-id="fe297-137">Use the following query to get status of a device.</span></span> <span data-ttu-id="fe297-138">I följande exempel kontrollerar frågan om enheten är onboarded.</span><span class="sxs-lookup"><span data-stu-id="fe297-138">In the following example, the query checks to see if the device is onboarded.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a><span data-ttu-id="fe297-139">Scenarier för scenarier</span><span class="sxs-lookup"><span data-stu-id="fe297-139">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="fe297-140">Lista inloggningsaktiviteter för användare som har fått e-postmeddelanden som inte har zapped</span><span class="sxs-lookup"><span data-stu-id="fe297-140">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="fe297-141">[ZAP (Zero-hour auto purge) adresserar skadliga e-postmeddelanden](../office-365-security/zero-hour-auto-purge.md) efter att de har tagits emot.</span><span class="sxs-lookup"><span data-stu-id="fe297-141">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="fe297-142">Om ZAP misslyckas kan skadlig kod så småningom köras på enheten och konton kan bli hackade.</span><span class="sxs-lookup"><span data-stu-id="fe297-142">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="fe297-143">Den här frågan kontrollerar inloggningsaktivitet som görs av mottagarna av e-postmeddelanden som inte har adresserts av ZAP.</span><span class="sxs-lookup"><span data-stu-id="fe297-143">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="fe297-144">Få inloggningsförsök från domänkonton som riktas av autentiseringsstöld</span><span class="sxs-lookup"><span data-stu-id="fe297-144">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="fe297-145">Den här frågan identifierar först alla aviseringar om autentiseringsåtkomst i `AlertInfo` tabellen.</span><span class="sxs-lookup"><span data-stu-id="fe297-145">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="fe297-146">Sedan slås tabellen samman eller kopplas, som den parsar för namnen på de riktade kontona och filtren `AlertEvidence` för endast domänsammanslagna konton.</span><span class="sxs-lookup"><span data-stu-id="fe297-146">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="fe297-147">Slutligen kontrolleras tabellen för `IdentityLogonEvents` att få alla inloggningsaktiviteter från domänmedlemna riktade konton.</span><span class="sxs-lookup"><span data-stu-id="fe297-147">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="fe297-148">Kontrollera om filer från en känd avsändare finns på dina enheter</span><span class="sxs-lookup"><span data-stu-id="fe297-148">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="fe297-149">Om du känner till en e-postadress som skickar skadliga filer ( ) kan du köra den här frågan för att avgöra om filer från den här `MaliciousSender@example.com` avsändaren finns på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="fe297-149">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="fe297-150">Du kan till exempel använda den här frågan för att identifiera enheter som påverkas av en distributionskampanj för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fe297-150">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="fe297-151">Granska inloggningsförsök efter kvitto på skadliga e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="fe297-151">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="fe297-152">Den här frågan hittar de 10 senaste inloggningarna som utförts av e-postmottagare inom 30 minuter efter att de fått kända skadliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fe297-152">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="fe297-153">Du kan använda den här frågan för att kontrollera om e-postmottagarnas konton har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="fe297-153">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="fe297-154">Granska PowerShell-aktiviteter efter e-postmeddelanden från känd avsändare</span><span class="sxs-lookup"><span data-stu-id="fe297-154">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="fe297-155">Skadliga e-postmeddelanden innehåller ofta dokument och andra särskilt utformade bifogade filer som kör PowerShell-kommandon för att leverera ytterligare nyttolaster.</span><span class="sxs-lookup"><span data-stu-id="fe297-155">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="fe297-156">Om du är medveten om e-postmeddelanden från en känd avsändare ( ) kan du använda den här frågan för att lista och granska PowerShell-aktiviteter som inträffade inom 30 minuter efter att ett e-postmeddelande togs emot från `MaliciousSender@example.com` avsändaren.</span><span class="sxs-lookup"><span data-stu-id="fe297-156">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="fe297-157">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fe297-157">Related topics</span></span>
- [<span data-ttu-id="fe297-158">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="fe297-158">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fe297-159">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="fe297-159">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fe297-160">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="fe297-160">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fe297-161">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="fe297-161">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fe297-162">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="fe297-162">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fe297-163">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="fe297-163">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
