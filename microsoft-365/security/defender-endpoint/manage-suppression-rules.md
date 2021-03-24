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
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072002"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="0a0e2-105">Hantera regelhanter</span><span class="sxs-lookup"><span data-stu-id="0a0e2-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0a0e2-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0a0e2-106">**Applies to:**</span></span>
- [<span data-ttu-id="0a0e2-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a0e2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0a0e2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a0e2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0a0e2-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0a0e2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a0e2-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0a0e2-111">Det kan finnas scenarier där du behöver dölja aviseringar från att visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="0a0e2-112">Du kan skapa regelregler för specifika aviseringar som är kända som obesvarade, till exempel kända verktyg eller processer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="0a0e2-113">Mer information om hur du ignorerar aviseringar finns i [Utelämna aviseringar.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0a0e2-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="0a0e2-114">Du kan visa en lista över alla regler och hantera dem på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="0a0e2-115">Du kan också aktivera eller inaktivera en aviseringsregel.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="0a0e2-116">I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.**</span><span class="sxs-lookup"><span data-stu-id="0a0e2-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="0a0e2-117">Listan över regelregler som användare i organisationen har skapat visas.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="0a0e2-118">Välj en regel genom att klicka på kryssrutan bredvid regelnamnet.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="0a0e2-119">Klicka **på Aktivera regel,** **Redigera regel** eller Ta **bort regel.**</span><span class="sxs-lookup"><span data-stu-id="0a0e2-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="0a0e2-120">När du gör ändringar i en regel kan du välja att släppa aviseringar som redan har ignorerats, oavsett om aviseringarna matchar de nya villkoren eller inte.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="0a0e2-121">Visa information om en regel för en regel</span><span class="sxs-lookup"><span data-stu-id="0a0e2-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="0a0e2-122">I navigeringsfönstret väljer du Inställningar  >  **Avisering – sekretess.**</span><span class="sxs-lookup"><span data-stu-id="0a0e2-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="0a0e2-123">Listan över regelregler som användare i organisationen har skapat visas.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="0a0e2-124">Klicka på ett regelnamn.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-124">Click on a rule name.</span></span> <span data-ttu-id="0a0e2-125">Information om regeln visas.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-125">Details of the rule is displayed.</span></span> <span data-ttu-id="0a0e2-126">Du ser regeldetaljer som status, omfattning, åtgärd, antal matchande aviseringar, skapat av och datum då regeln skapades.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="0a0e2-127">Du kan också visa associerade aviseringar och regelvillkor.</span><span class="sxs-lookup"><span data-stu-id="0a0e2-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a0e2-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0a0e2-128">Related topics</span></span>

- [<span data-ttu-id="0a0e2-129">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="0a0e2-129">Manage alerts</span></span>](manage-alerts.md)
