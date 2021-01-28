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
description: Administratörer kan läsa mer om hur du använder korrigerings filen för möjlig e-post som inblickas i instrument panelen för e-postflöde i säkerhets & efterlevnad för att identifiera och åtgärda e-postloopar i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029900"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="fa386-103">Åtgärda eventuell e-postloop inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="fa386-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fa386-104">E-postloopar är felaktiga på grund av följande:</span><span class="sxs-lookup"><span data-stu-id="fa386-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="fa386-105">De slösar system resurserna.</span><span class="sxs-lookup"><span data-stu-id="fa386-105">They waste system resources.</span></span>
- <span data-ttu-id="fa386-106">De förbrukar organisationens kvot för e-postvolym.</span><span class="sxs-lookup"><span data-stu-id="fa386-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="fa386-107">De skickar förvirrande rapporter (kallas även NDR eller studs meddelanden) till de ursprungliga avsändarna.</span><span class="sxs-lookup"><span data-stu-id="fa386-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="fa386-108">Den **åtgärd för möjlig e-post** som är inblick i **Rekommenderad för dig** -området i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & för regelefterlevnad](https://protection.office.com) meddelar dig när en e-postloop upptäcks i din organisation.</span><span class="sxs-lookup"><span data-stu-id="fa386-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="fa386-109">Denna inblick visas bara efter det att villkoret har identifierats (om du inte har några e-postloopar visas inte inblicken).</span><span class="sxs-lookup"><span data-stu-id="fa386-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Åtgärda regler för långsam e-postflöde inblick i det rekommenderade för dig-området på instrument panelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="fa386-111">När du klickar på **Visa information** i widgeten visas en utfällbar lista med mer information:</span><span class="sxs-lookup"><span data-stu-id="fa386-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="fa386-112">**Domain**</span><span class="sxs-lookup"><span data-stu-id="fa386-112">**Domain**</span></span>
- <span data-ttu-id="fa386-113">**Antal meddelanden**: du kan klicka på **Visa exempel meddelanden** för att se resultatet av [meddelande spårningen](message-trace-scc.md) för ett urval av de meddelanden som påverkade slingan.</span><span class="sxs-lookup"><span data-stu-id="fa386-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="fa386-114">**Domän typ**"till exempel auktoritär eller icke-auktoritativ.</span><span class="sxs-lookup"><span data-stu-id="fa386-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="fa386-115">**MX-post**:**värd-och** **prioritets** värden för MX-posten för domänen.</span><span class="sxs-lookup"><span data-stu-id="fa386-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="fa386-116">**Upprepa orsaken** och **hur du åtgärdar**: vi identifierar de vanligaste e-postlösningarna och ger rekommenderade åtgärder för att åtgärda slingan.</span><span class="sxs-lookup"><span data-stu-id="fa386-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Den utfällbara informationen som visas när du klickar på Visa information om att åtgärda eventuella problem med e-post](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="fa386-118">Se även</span><span class="sxs-lookup"><span data-stu-id="fa386-118">See also</span></span>

<span data-ttu-id="fa386-119">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="fa386-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
