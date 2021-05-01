---
title: Exempel på nätfiskeattack
description: Gå igenom en exempelanalys av nätfiskeangrepp.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114785"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="1332a-104">Exempel på nätfiskeattack</span><span class="sxs-lookup"><span data-stu-id="1332a-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1332a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1332a-105">**Applies to:**</span></span>
- <span data-ttu-id="1332a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1332a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1332a-107">Microsoft 365 Defender kan hjälpa dig att identifiera skadliga bifogade filer som levereras via e-post.</span><span class="sxs-lookup"><span data-stu-id="1332a-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="1332a-108">Eftersom [Office 365 Säkerhets-](https://protection.office.com/) och efterlevnadscenter är integrerat med Microsoft 365 Defender kan säkerhetsanalytiker se hot som kommer in från Office 365, till exempel via e-postbilagor.</span><span class="sxs-lookup"><span data-stu-id="1332a-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="1332a-109">En analytiker har till exempel tilldelats ett incident i flera steg.</span><span class="sxs-lookup"><span data-stu-id="1332a-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Exempel på incident i flera steg"::: 

<span data-ttu-id="1332a-111">På fliken **Aviseringar** för incidenten visas aviseringar från Defender för Office 365 och Microsoft Cloud App Security visas.</span><span class="sxs-lookup"><span data-stu-id="1332a-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="1332a-112">Analytikern kan granska nedåt i Defender för att få Office 365 avisering genom att välja e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="1332a-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="1332a-113">Informationen om aviseringen visas i sidofönstret.</span><span class="sxs-lookup"><span data-stu-id="1332a-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Exempel på en e-postavisering":::
 
<span data-ttu-id="1332a-115">Genom att rulla nedåt ytterligare visas mer information som visar skadliga filer och användare som har påverkats.</span><span class="sxs-lookup"><span data-stu-id="1332a-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Exempel på hur en e-postavisering påverkar användare och filer":::
  
<span data-ttu-id="1332a-117">Om **du väljer sidan** Öppna avisering kommer du till den specifika aviseringen där olika information kan visas mer ingående genom att klicka på länken.</span><span class="sxs-lookup"><span data-stu-id="1332a-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="1332a-118">Själva e-postmeddelandet kan visas genom **att välja Visa meddelanden i Utforskaren** längst ned i panelen.</span><span class="sxs-lookup"><span data-stu-id="1332a-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Exempel på information om en avisering"::: 

<span data-ttu-id="1332a-120">Då kommer analytikern till sidan Threat Management där e-postmeddelandet Ämne, Mottagare, Avsändare och annan information visas.</span><span class="sxs-lookup"><span data-stu-id="1332a-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="1332a-121">**ZAP** under **Specialåtgärder** meddelar analytikern att automatisk rensning har implementerats med nolltimmarsrensning.</span><span class="sxs-lookup"><span data-stu-id="1332a-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="1332a-122">ZAP identifierar och tar automatiskt bort skadliga meddelanden och skräppostmeddelanden från postlådor i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="1332a-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="1332a-123">Mer information finns i [ZAP (Zero-hour auto purge) i Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="1332a-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="1332a-124">Andra åtgärder kan vidtas på specifika meddelanden genom att välja **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="1332a-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Exempel på andra åtgärder som kan vidtas på e-postmeddelanden"::: 

## <a name="next-step"></a><span data-ttu-id="1332a-126">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1332a-126">Next step</span></span>

<span data-ttu-id="1332a-127">Se den [identitetsbaserade](first-incident-path-identity.md) attackundersökningssökvägen.</span><span class="sxs-lookup"><span data-stu-id="1332a-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="1332a-128">Se även</span><span class="sxs-lookup"><span data-stu-id="1332a-128">See also</span></span>

- [<span data-ttu-id="1332a-129">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="1332a-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1332a-130">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="1332a-130">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1332a-131">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="1332a-131">Manage incidents</span></span>](manage-incidents.md)
