---
title: Den främsta statusen för domän-e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder den främsta domänens e-postflödes status inblick i instrument panelen för e-postflöde i säkerhets & efterlevnad för att felsöka e-postproblem i samband med MX-poster i deras e-
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577765"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="1b2e6-103">Den främsta domänens e-postflödes status inblick i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1b2e6-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="1b2e6-104">Statusen för den **främsta domänens e-postflöde** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center ger dig den aktuella statusen för organisationens domäner i termer av e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="1b2e6-105">Denna inblick hjälper dig att identifiera och felsöka domäner som ***påverkar problem med e-postflöde*** (till exempel att det inte går att ta emot extern e-post), särskilt upphör att gälla för domänen eller domäner med felaktiga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Flödes schema för bästa domän status i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="1b2e6-107">När du klickar på **Visa information** i widgeten visas en utfällbar **domän status** som visar mer information om varje domän status:</span><span class="sxs-lookup"><span data-stu-id="1b2e6-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="1b2e6-108">**Domain**</span><span class="sxs-lookup"><span data-stu-id="1b2e6-108">**Domain**</span></span>
- <span data-ttu-id="1b2e6-109">**Föregående MX-post**</span><span class="sxs-lookup"><span data-stu-id="1b2e6-109">**Previous MX record**</span></span>
- <span data-ttu-id="1b2e6-110">**Aktuell MX-post**</span><span class="sxs-lookup"><span data-stu-id="1b2e6-110">**Current MX record**</span></span>
- <span data-ttu-id="1b2e6-111">**Status för e-postmottagning**</span><span class="sxs-lookup"><span data-stu-id="1b2e6-111">**Email receiving status**</span></span>
- <span data-ttu-id="1b2e6-112">**Domän status**: en grön bock markering anger den aktuella MX-posten (när du klickade på widgeten) matchar det värde som finns på posten och att domänen har fått e-post under de två timmarna.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="1b2e6-113">Ett rött X anger att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="1b2e6-114">Detta indikerar antagligen att din domän har upphört, eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="1b2e6-115">Kontrol lera med din domän registrator eller DNS-värd om domänen har upphört att gälla, eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="1b2e6-116">Du kan klicka på **Visa mer** om du vill se samma information för fler domäner.</span><span class="sxs-lookup"><span data-stu-id="1b2e6-116">You can click **View more** to see the same information for more domains.</span></span>

![Den utfällbara informationen i den främsta domänens e-flöde-status inblick](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="1b2e6-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1b2e6-118">Related topics</span></span>

<span data-ttu-id="1b2e6-119">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="1b2e6-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
