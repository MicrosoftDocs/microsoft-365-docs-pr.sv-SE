---
title: Fixa möjlig inblick i e-postslingan
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur de kan använda korrigeringen av möjliga informationsloopar för e-post i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att identifiera och åtgärda e-postslingor i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071298"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="a986d-103">Åtgärda möjliga insikter om e-postslingan i & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="a986d-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a986d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a986d-104">**Applies to**</span></span>
- [<span data-ttu-id="a986d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a986d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a986d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a986d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a986d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a986d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a986d-108">E-postslingor är dåliga eftersom:</span><span class="sxs-lookup"><span data-stu-id="a986d-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="a986d-109">De slösar på systemresurser.</span><span class="sxs-lookup"><span data-stu-id="a986d-109">They waste system resources.</span></span>
- <span data-ttu-id="a986d-110">De använder organisationens e-postvolym.</span><span class="sxs-lookup"><span data-stu-id="a986d-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="a986d-111">De skickar förvirrande rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) till de ursprungliga meddelandeavsändarna.</span><span class="sxs-lookup"><span data-stu-id="a986d-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="a986d-112">Åtgärda **möjliga insikter** om  e-postslingor [](mail-flow-insights-v2.md) i området Rekommenderas för dig på instrumentpanelen för e-postflöde i Säkerhets- och [&-efterlevnadscenter](https://protection.office.com) meddelar dig när en e-postslinga identifieras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a986d-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="a986d-113">Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).</span><span class="sxs-lookup"><span data-stu-id="a986d-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Åtgärda insikt i regler för långsamt e-postflöde i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="a986d-115">När du klickar **på Visa information** om widgeten visas en utfäll tillgänglig meny med mer information:</span><span class="sxs-lookup"><span data-stu-id="a986d-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="a986d-116">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a986d-116">**Domain**</span></span>
- <span data-ttu-id="a986d-117">**Antal meddelanden:** Du kan klicka på Visa **exempelmeddelanden** för att se resultatet [av meddelandespårningen](message-trace-scc.md) för ett exempel på meddelanden som har påverkats av loopen.</span><span class="sxs-lookup"><span data-stu-id="a986d-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="a986d-118">**Domäntyp**" Till exempel Auktoritativ eller Icke-auktoritativ.</span><span class="sxs-lookup"><span data-stu-id="a986d-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="a986d-119">**MX-post:** Värden **(e-postserver)** **och prioritetsvärden** för MX-posten för domänen.</span><span class="sxs-lookup"><span data-stu-id="a986d-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="a986d-120">**Looporsak** och **Hur du åtgärdar**: Vi identifierar de vanligaste e-postslingsscenarierna och tillhandahåller rekommenderade åtgärder för att åtgärda slingan.</span><span class="sxs-lookup"><span data-stu-id="a986d-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Information som visas när du klickar på Visa information i Åtgärda möjliga e-postslingor](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="a986d-122">Se även</span><span class="sxs-lookup"><span data-stu-id="a986d-122">See also</span></span>

<span data-ttu-id="a986d-123">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a986d-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
