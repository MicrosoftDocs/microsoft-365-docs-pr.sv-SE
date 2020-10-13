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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6c758c05a64cd7ce84a2b021fe32f9e5ce5c1090
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431069"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="c5379-104">Jakt efter hot på enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="c5379-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5379-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c5379-105">**Applies to:**</span></span>
- <span data-ttu-id="c5379-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5379-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c5379-107">Med [Avancerad jakt](advanced-hunting-overview.md) i Microsoft Threat Protection kan du proaktivt efter problem i:</span><span class="sxs-lookup"><span data-stu-id="c5379-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="c5379-108">Enheter som hanteras av Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c5379-108">Devices managed by Microsoft Defender ATP</span></span>
- <span data-ttu-id="c5379-109">E-postmeddelanden som bearbetas av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5379-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="c5379-110">Molnprogram aktiviteter, autentiseringsnivåer och aktiviteter för domän kontrol Lanterna spåras av Microsoft Cloud App Security och Azure ATP</span><span class="sxs-lookup"><span data-stu-id="c5379-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Azure ATP</span></span>

<span data-ttu-id="c5379-111">Med den här synbarheten kan du snabbt hitta hot som rör fram delar av nätverket, inklusive sofistikerade intrång som kommer via e-post eller webben, öka behörigheterna, skaffa privilegierade domänautentiseringsuppgifter och flytta dem senare till alla dina enheter.</span><span class="sxs-lookup"><span data-stu-id="c5379-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="c5379-112">Här är allmänna tekniker och urvals frågor baserat på olika jakt scenarier som hjälper dig att upptäcka hur du kan skapa frågor när jakt efter sådana avancerade hot.</span><span class="sxs-lookup"><span data-stu-id="c5379-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="c5379-113">Hämta entitetsinformation</span><span class="sxs-lookup"><span data-stu-id="c5379-113">Get entity info</span></span>
<span data-ttu-id="c5379-114">Använd de här frågorna för att få reda på hur du snabbt får information om användar konton, enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="c5379-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="c5379-115">Skaffa användar konton från e-postadresser</span><span class="sxs-lookup"><span data-stu-id="c5379-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="c5379-116">När du skapar frågor över [tabeller som täcker enheter och e-post](advanced-hunting-schema-tables.md)måste du antagligen skaffa användar konto namn från avsändare eller mottagares e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="c5379-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="c5379-117">Du kan vanligt vis göra detta för antingen mottagare eller avsändar adress via den *lokala värden* från e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="c5379-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="c5379-118">I det här avsnittet nedan använder vi funktionen [toString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto för att extrahera den lokala värd rättigheten före `@` från mottagarens e-postadresser i kolumnen `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="c5379-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="c5379-119">I frågan nedan visas hur det här avsnittet kan användas:</span><span class="sxs-lookup"><span data-stu-id="c5379-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="c5379-120">Slå samman tabellen IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c5379-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="c5379-121">Du kan skaffa konto namn och annan konto information genom att sammanfoga eller gå med i [IdentityInfo-tabellen](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="c5379-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="c5379-122">Frågan nedan erhåller listan över nät fiske och skadlig program vara som identifieras från [tabellen EmailEvents](advanced-hunting-emailevents-table.md) och sedan kopplas till den informationen med `IdentityInfo` tabellen för att få detaljerad information om varje mottagare.</span><span class="sxs-lookup"><span data-stu-id="c5379-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="c5379-123">Hämta enhets information</span><span class="sxs-lookup"><span data-stu-id="c5379-123">Get device information</span></span>
<span data-ttu-id="c5379-124">Det [avancerade jakt schemat](advanced-hunting-schema-tables.md) ger omfattande enhets information i olika tabeller.</span><span class="sxs-lookup"><span data-stu-id="c5379-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="c5379-125">[Tabellen deviceinfo](advanced-hunting-deviceinfo-table.md) innehåller till exempel omfattande enhets information baserat på händelse data som sammanlagts regelbundet.</span><span class="sxs-lookup"><span data-stu-id="c5379-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="c5379-126">Den här frågan använder `DeviceInfo` tabellen för att kontrol lera om en potentiellt utsatt användare ( `<account-name>` ) har loggat in på några enheter och sedan en lista över de aviseringar som har Aktiver ATS på dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="c5379-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="c5379-127">Den här frågan används `kind=inner` för att ange en [inre koppling](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), som förhindrar avduplicering av vänster sid värden för `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="c5379-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="c5379-128">Jakt scenarier</span><span class="sxs-lookup"><span data-stu-id="c5379-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="c5379-129">Visa inloggnings aktiviteter för användare som fått e-post som inte zapped</span><span class="sxs-lookup"><span data-stu-id="c5379-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="c5379-130">[Automatisk rensning för en tom timme (Zap)](../office-365-security/zero-hour-auto-purge.md) tar emot skadlig e-post efter att de har mottagits.</span><span class="sxs-lookup"><span data-stu-id="c5379-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="c5379-131">Om det inte fungerar kan det hända att skadlig kod kanske körs på enheten och lämnar konton.</span><span class="sxs-lookup"><span data-stu-id="c5379-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="c5379-132">Den här frågan söker efter inloggnings aktiviteter som görs av mottagarna av e-postmeddelanden som inte kunde besvaras med ZAP.</span><span class="sxs-lookup"><span data-stu-id="c5379-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="c5379-133">Få inloggnings försök från domän konton riktade till stöld av autentiseringsuppgiften</span><span class="sxs-lookup"><span data-stu-id="c5379-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="c5379-134">Denna fråga identifierar först alla notifieringar om autentiseringsuppgifter i `AlertInfo` tabellen.</span><span class="sxs-lookup"><span data-stu-id="c5379-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="c5379-135">Då sammanfogas eller kopplas `AlertEvidence` tabellen, vilket bara kan tolka namn på riktade konton och filter för domänbaserade konton.</span><span class="sxs-lookup"><span data-stu-id="c5379-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="c5379-136">Slutligen kontrollerar den `IdentityLogonEvents` tabellen för att få alla inloggnings aktiviteter av domänbaserade riktade konton.</span><span class="sxs-lookup"><span data-stu-id="c5379-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="c5379-137">Kontrol lera om filer från en känd angripare finns på dina enheter</span><span class="sxs-lookup"><span data-stu-id="c5379-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="c5379-138">Förutsatt att du känner till en e-postadress för att skicka skadliga filer ( `MaliciousSender@example.com` ) kan du köra den här frågan för att ta reda på om filer från den här avsändaren finns på din enhet.</span><span class="sxs-lookup"><span data-stu-id="c5379-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="c5379-139">Du kan använda den här frågan, till exempel för att identifiera enheter som påverkas av en distributions kampanj med skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="c5379-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="c5379-140">Granska inloggnings försök efter mottagning av illasinnade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c5379-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="c5379-141">Den här frågan hittar de tio senaste inloggningarna som utförs av e-postmottagarna inom 30 minuter efter att de fått kända skadliga meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c5379-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="c5379-142">Du kan använda den här frågan för att kontrol lera om kontona i e-postmottagaren har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="c5379-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="c5379-143">Granska PowerShell-aktiviteter efter mottagning av e-postmeddelanden från känd skadlig avsändare</span><span class="sxs-lookup"><span data-stu-id="c5379-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="c5379-144">Illvilliga e-postmeddelanden innehåller ofta dokument och andra särskilt utformade bilagor som kör PowerShell-kommandon för att leverera extra nytto laster.</span><span class="sxs-lookup"><span data-stu-id="c5379-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="c5379-145">Om du känner till e-postmeddelanden som kommer från en känd angripare ( `MaliciousSender@example.com` ) kan du använda den här frågan för att visa och granska PowerShell-aktiviteter som skedde inom 30 minuter efter att ett e-postmeddelande togs emot från avsändaren.</span><span class="sxs-lookup"><span data-stu-id="c5379-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="c5379-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c5379-146">Related topics</span></span>
- [<span data-ttu-id="c5379-147">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c5379-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5379-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c5379-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5379-149">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="c5379-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c5379-150">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="c5379-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5379-151">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c5379-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5379-152">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c5379-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
