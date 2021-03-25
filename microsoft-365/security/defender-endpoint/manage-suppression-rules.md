---
title: Hantera regler för Microsoft Defender för slutpunktsslutpunkter
description: Du kan behöva förhindra att aviseringar visas i portalen genom att använda regler som gäller här. Lär dig hur du hanterar regler som gäller i Microsoft Defender ATP.
keywords: hantera hantera hantera regler, regelnamn, omfattning, åtgärd, aviseringar, aktivera, inaktivera
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d2ff8fa1f07f82c3cc719f49f50ee25937aea243
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187571"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="2a7e7-105">Hantera regelhanter</span><span class="sxs-lookup"><span data-stu-id="2a7e7-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2a7e7-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2a7e7-106">**Applies to:**</span></span>
- [<span data-ttu-id="2a7e7-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a7e7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a7e7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a7e7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a7e7-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2a7e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a7e7-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2a7e7-111">Det kan finnas scenarier där du behöver dölja aviseringar från att visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="2a7e7-112">Du kan skapa regelregler för specifika aviseringar som är kända som obesvarade, till exempel kända verktyg eller processer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="2a7e7-113">Mer information om hur du ignorerar aviseringar finns i [Utelämna aviseringar.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="2a7e7-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="2a7e7-114">Du kan visa en lista över alla regler och hantera dem på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="2a7e7-115">Du kan också aktivera eller inaktivera en aviseringsregel.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="2a7e7-116">I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.**</span><span class="sxs-lookup"><span data-stu-id="2a7e7-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="2a7e7-117">Listan över regelregler som användare i organisationen har skapat visas.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="2a7e7-118">Välj en regel genom att klicka på kryssrutan bredvid regelnamnet.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="2a7e7-119">Klicka **på Aktivera regel,** **Redigera regel** eller Ta **bort regel.**</span><span class="sxs-lookup"><span data-stu-id="2a7e7-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="2a7e7-120">När du gör ändringar i en regel kan du välja att släppa aviseringar som redan har ignorerats, oavsett om aviseringarna matchar de nya villkoren eller inte.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="2a7e7-121">Visa information om en regel för en regel</span><span class="sxs-lookup"><span data-stu-id="2a7e7-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="2a7e7-122">I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.**</span><span class="sxs-lookup"><span data-stu-id="2a7e7-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="2a7e7-123">Listan över regelregler som användare i organisationen har skapat visas.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="2a7e7-124">Klicka på ett regelnamn.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-124">Click on a rule name.</span></span> <span data-ttu-id="2a7e7-125">Information om regeln visas.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-125">Details of the rule is displayed.</span></span> <span data-ttu-id="2a7e7-126">Du ser regeldetaljer som status, omfattning, åtgärd, antal matchande aviseringar, skapat av och datum då regeln skapades.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="2a7e7-127">Du kan också visa associerade aviseringar och regelvillkor.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a7e7-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2a7e7-128">Related topics</span></span>

- [<span data-ttu-id="2a7e7-129">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="2a7e7-129">Manage alerts</span></span>](manage-alerts.md)
