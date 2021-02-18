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
description: Administratörer kan lära sig att använda korrigeringen av möjliga e-postslingor i instrumentpanelen för e-postflöde i säkerhets- & och efterlevnadscentret för att identifiera och åtgärda e-postslingor i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290567"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="a83cd-103">Åtgärda möjliga insikter i e-postslingan i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="a83cd-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a83cd-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a83cd-104">**Applies to**</span></span>
- [<span data-ttu-id="a83cd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a83cd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a83cd-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a83cd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a83cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a83cd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a83cd-108">E-postslingor är dåliga eftersom:</span><span class="sxs-lookup"><span data-stu-id="a83cd-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="a83cd-109">De slösar bort systemresurser.</span><span class="sxs-lookup"><span data-stu-id="a83cd-109">They waste system resources.</span></span>
- <span data-ttu-id="a83cd-110">De använder organisationens e-postvolym.</span><span class="sxs-lookup"><span data-stu-id="a83cd-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="a83cd-111">De skickar förvirrande rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändarmeddelanden) till de ursprungliga avsändarna.</span><span class="sxs-lookup"><span data-stu-id="a83cd-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="a83cd-112">Fix **possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center [notifies](https://protection.office.com) you when a mail loop isected in your organization.</span><span class="sxs-lookup"><span data-stu-id="a83cd-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="a83cd-113">Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).</span><span class="sxs-lookup"><span data-stu-id="a83cd-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Åtgärda insikter för långsamt e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="a83cd-115">När du klickar **på Visa** information på widgeten visas en utfäll tillgänglig meny med mer information:</span><span class="sxs-lookup"><span data-stu-id="a83cd-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="a83cd-116">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a83cd-116">**Domain**</span></span>
- <span data-ttu-id="a83cd-117">**Antal meddelanden:** Du kan klicka på [](message-trace-scc.md) **Visa exempelmeddelanden** om du vill visa meddelandespårningsresultaten för ett exempel på meddelanden som har påverkats av loopen.</span><span class="sxs-lookup"><span data-stu-id="a83cd-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="a83cd-118">**Domäntyp**" Till exempel auktoritativ eller icke-auktoritativ.</span><span class="sxs-lookup"><span data-stu-id="a83cd-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="a83cd-119">**MX-post:** Värden **(E-postserver)** **och** prioritetsvärden för MX-posten för domänen.</span><span class="sxs-lookup"><span data-stu-id="a83cd-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="a83cd-120">**Looporsak** **och hur du åtgärdar:** Vi identifierar de vanligaste e-postslingsscenarierna och tillhandahåller rekommenderade åtgärder för att åtgärda slingan.</span><span class="sxs-lookup"><span data-stu-id="a83cd-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Den utfällna informationen som visas när du klickar på Visa information om åtgärda möjlig e-postslinga](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="a83cd-122">Se även</span><span class="sxs-lookup"><span data-stu-id="a83cd-122">See also</span></span>

<span data-ttu-id="a83cd-123">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a83cd-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
