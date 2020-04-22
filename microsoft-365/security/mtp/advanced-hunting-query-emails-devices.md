---
title: Hitta hot på olika enheter och e-postmeddelanden med avancerad jakt
description: Studera vanliga jaktscenarier och exempelfrågor som täcker enheter och e-postmeddelanden.
keywords: avancerad jakt, Office365-data, Windows-enheter, Office365-e-postmeddelanden normaliserar, e-postmeddelanden, hotjakt, cyberhotjakt, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633513"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="d0e2d-104">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d0e2d-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="d0e2d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="d0e2d-105">**Applies to:**</span></span>
- <span data-ttu-id="d0e2d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d0e2d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d0e2d-107">[Med avancerad jakt](advanced-hunting-overview.md) i Microsoft Threat Protection kan du proaktivt jaga efter hot på dina Windows-enheter och Microsoft-e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Microsoft emails.</span></span> <span data-ttu-id="d0e2d-108">Här är några jaktscenarier och exempelfrågor som kan hjälpa dig att utforska hur du kan skapa frågor som täcker både enheter och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="d0e2d-109">Hämta användarkonton från e-postadresser</span><span class="sxs-lookup"><span data-stu-id="d0e2d-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="d0e2d-110">När du skapar frågor över [tabeller som täcker enheter och e-postmeddelanden](advanced-hunting-schema-tables.md)måste du förmodligen skaffa användarnamn från avsändare eller mottagare e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="d0e2d-111">Så här använder du den lokala värden från *e-postadressen:*</span><span class="sxs-lookup"><span data-stu-id="d0e2d-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="d0e2d-112">Den här normaliseringstekniken används i de efterföljande scenarierna.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="d0e2d-113">Jaktscenarier</span><span class="sxs-lookup"><span data-stu-id="d0e2d-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="d0e2d-114">Kontrollera om filer från en känd skadlig avsändare finns på dina enheter</span><span class="sxs-lookup"><span data-stu-id="d0e2d-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="d0e2d-115">Om du antar att du känner till en e-postadress som skickar skadliga filer kan du köra den här frågan för att avgöra om det finns filer från den här avsändaren på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="d0e2d-116">Du kan till exempel använda den här frågan för att fastställa antalet enheter som påverkas av en distributionskampanj för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="d0e2d-117">Granska inloggningsförsök efter mottagandet av skadliga e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d0e2d-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="d0e2d-118">Den här frågan hittar de 10 senaste inloggningarna som utförs av e-postmottagare inom 30 minuter efter att de fått kända skadliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="d0e2d-119">Du kan använda den här frågan för att kontrollera om e-postmottagarnas konton har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="d0e2d-120">Granska PowerShell-aktiviteter efter mottagandet av e-postmeddelanden från känd skadlig avsändare</span><span class="sxs-lookup"><span data-stu-id="d0e2d-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="d0e2d-121">Skadliga e-postmeddelanden innehåller ofta dokument och andra specialtillverkade bilagor som kör PowerShell-kommandon för att leverera ytterligare nyttolaster.</span><span class="sxs-lookup"><span data-stu-id="d0e2d-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="d0e2d-122">Om du är medveten om e-postmeddelanden som kommer från en känd skadlig avsändare kan du använda den här frågan för att lista och granska PowerShell-aktiviteter som inträffade inom 30 minuter efter att ett e-postmeddelande togs emot från avsändaren .</span><span class="sxs-lookup"><span data-stu-id="d0e2d-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="d0e2d-123">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d0e2d-123">Related topics</span></span>
- [<span data-ttu-id="d0e2d-124">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d0e2d-124">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0e2d-125">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d0e2d-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0e2d-126">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="d0e2d-126">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d0e2d-127">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="d0e2d-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0e2d-128">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d0e2d-128">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0e2d-129">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="d0e2d-129">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
