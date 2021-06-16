---
title: Exempel på avancerad sökning för Microsoft Defender för Office 365
description: Kom igång med att söka efter e-posthot med avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965154"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="c3fd8-104">Exempel på avancerad sökning för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="c3fd8-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c3fd8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c3fd8-105">**Applies to:**</span></span>
- <span data-ttu-id="c3fd8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3fd8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c3fd8-107">Vill du komma igång med att söka efter e-posthot med avancerad sökning?</span><span class="sxs-lookup"><span data-stu-id="c3fd8-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="c3fd8-108">Prova det här:</span><span class="sxs-lookup"><span data-stu-id="c3fd8-108">Try this:</span></span>

<span data-ttu-id="c3fd8-109">Avsnittet [Komma igång](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) i artikeln [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) har en logisk tidig konfigurationsdel som ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="c3fd8-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="c3fd8-110">Konfigurera allt med "Anti" i namnet.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="c3fd8-111">Skydd mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="c3fd8-111">Anti-malware</span></span>
   - <span data-ttu-id="c3fd8-112">Skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="c3fd8-112">Anti-phishing</span></span>
   - <span data-ttu-id="c3fd8-113">Skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="c3fd8-113">Anti-spam</span></span>
2. <span data-ttu-id="c3fd8-114">Konfigurera allt med "Valv" i namnet.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="c3fd8-115">Säkra länkar</span><span class="sxs-lookup"><span data-stu-id="c3fd8-115">Safe Links</span></span>
   - <span data-ttu-id="c3fd8-116">Säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="c3fd8-116">Safe Attachments</span></span>
3. <span data-ttu-id="c3fd8-117">Försvara arbets belastningarna (t. ex.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-117">Defend the workloads (ex.</span></span> <span data-ttu-id="c3fd8-118">SharePoint Online, OneDrive och Teams).</span><span class="sxs-lookup"><span data-stu-id="c3fd8-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="c3fd8-119">Skydda med automatisk rensning utan timme.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="c3fd8-120">Tillsammans med en [länk](../office-365-security/protect-against-threats.md) kan du hoppa direkt in och få igång konfigurationen dag 1.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="c3fd8-121">Det sista steget i **Komma igång** skyddar användare med **Automatisk rensning**, även kallat ZAP.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="c3fd8-122">Det kan vara mycket viktigt att veta om du har lyckats med ZAP:a ett misstänkt eller skadligt e-postmeddelande efter leverans.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="c3fd8-123">Att snabbt kunna navigera till Kusto frågespråk för att leta efter problem är en fördel med konvergering av dessa två säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="c3fd8-124">Säkerhetsteam kan övervaka ZAP-misser genom att vidta nästa steg [här,](https://security.microsoft.com/advanced-hunting)under **Sökning** \> **efter avancerad sökning.**</span><span class="sxs-lookup"><span data-stu-id="c3fd8-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="c3fd8-125">På sidan Advanced Hunting klickar du på **Query**.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="c3fd8-126">Kopiera frågan nedan till frågefönstret.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="c3fd8-127">Välj **Kör fråga.**</span><span class="sxs-lookup"><span data-stu-id="c3fd8-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Sidan Avancerad sökning (under Sök) med Fråga markerad högst upp i frågepanelen och kör en Kusto-fråga för att fånga ZAP-åtgärder under de senaste 7 dagarna.":::

<span data-ttu-id="c3fd8-129">Data från den här frågan visas i resultatpanelen under själva frågan.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="c3fd8-130">Resultaten innehåller information som ‘Enhetsnamn’, ‘KontoVisningsNamn’ och ‘ZapTid’ i en anpassningsbar resultatuppsättning.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="c3fd8-131">Resultat kan även exporteras för posterna.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-131">Results can also be exported for your records.</span></span> <span data-ttu-id="c3fd8-132">Om frågan är en du behöver igen väljer du **Spara** > **Spara som** och lägger till frågan i din lista med frågor, delade frågor eller communityfrågor.</span><span class="sxs-lookup"><span data-stu-id="c3fd8-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="c3fd8-133">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="c3fd8-133">Related information</span></span>
- [<span data-ttu-id="c3fd8-134">Avancerade metodtips för sökning</span><span class="sxs-lookup"><span data-stu-id="c3fd8-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c3fd8-135">Översikt – Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="c3fd8-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
