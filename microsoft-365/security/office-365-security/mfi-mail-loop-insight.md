---
title: Åtgärda möjliga e-postloopar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder korrigerings filen för möjlig e-post som inblickas i instrument panelen för e-postflöde i säkerhets & efterlevnad för att identifiera och åtgärda e-postloopar i organisationen.
ms.openlocfilehash: 54240cffc534b4be708492b37b827636edab280e
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577644"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="a4443-103">Åtgärda eventuell e-postloop inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a4443-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="a4443-104">En e-postloop är dålig eftersom den tar emot system resurser, använder organisationens e-postkvot och skickar förvirrande rapporter (kallas även för NDR eller studs meddelanden) till de ursprungliga avsändarna.</span><span class="sxs-lookup"><span data-stu-id="a4443-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="a4443-105">Den **åtgärd för möjlig e-post** som är inblick i **Rekommenderad för dig** -området i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i säkerhets & för regelefterlevnad meddelar dig när en e-postloop upptäcks i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a4443-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="a4443-106">Denna inblick visas bara efter det att villkoret har identifierats (om du inte har några e-postloopar visas inte inblicken).</span><span class="sxs-lookup"><span data-stu-id="a4443-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Åtgärda regler för långsam e-postflöde inblick i det rekommenderade för dig-området på instrument panelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="a4443-108">När du klickar på **Visa information** i widgeten visas en utfällbar lista med mer information:</span><span class="sxs-lookup"><span data-stu-id="a4443-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="a4443-109">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a4443-109">**Domain**</span></span>
- <span data-ttu-id="a4443-110">**Antal meddelanden**: du kan klicka på **Visa exempel meddelanden** för att se resultatet av [meddelande spårningen](message-trace-scc.md) för ett urval av de meddelanden som påverkade slingan.</span><span class="sxs-lookup"><span data-stu-id="a4443-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="a4443-111">**Domän typ**"till exempel auktoritär eller icke-auktoritativ.</span><span class="sxs-lookup"><span data-stu-id="a4443-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="a4443-112">**MX-post**:**värd-och** **prioritets** värden för MX-posten för domänen.</span><span class="sxs-lookup"><span data-stu-id="a4443-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="a4443-113">**Upprepa orsaken** och **hur du åtgärdar**: vi försöker att identifiera de vanligaste e-postlösningarna och ger de rekommenderade åtgärderna (om de finns tillgängliga) för att åtgärda slingan.</span><span class="sxs-lookup"><span data-stu-id="a4443-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Den utfällbara informationen som visas när du klickar på Visa information om att åtgärda eventuella problem med e-post](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="a4443-115">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a4443-115">Related topics</span></span>

<span data-ttu-id="a4443-116">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="a4443-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
