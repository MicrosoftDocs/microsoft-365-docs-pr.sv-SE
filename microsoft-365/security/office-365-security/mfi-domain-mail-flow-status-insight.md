---
title: Insikten E-postflödesstatus för översta domäner
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
description: Administratörer kan lära sig mer om den översta statusinformationen för domänutskicksflödet i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818597"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="9e54c-103">Insikten E-postflödesstatus för översta domäner</span><span class="sxs-lookup"><span data-stu-id="9e54c-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="9e54c-104">Statusinsikten **för toppdomänens e-postflöde** ger dig aktuell status för organisationens domäner när det gäller e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="9e54c-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="9e54c-105">Den här insikten hjälper dig att identifiera och felsöka domäner som upplever problem med ***e-postflödet*** (t.ex. inte kan ta emot extern e-post), särskilt domänförfall eller domäner med felaktiga MX-poster.</span><span class="sxs-lookup"><span data-stu-id="9e54c-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Statusinsikten för toppdomänflödet i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="9e54c-107">När du klickar på **Visa information** i insikten visas ett utfällbart utfällbart meddelande som visar mer information om status för varje domän.</span><span class="sxs-lookup"><span data-stu-id="9e54c-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="9e54c-108">En grön bock för en domän anger att den aktuella MX-posten (när du bläddrade till instrumentpanelen för e-postflödesinsikter) matchar det värde vi har på skiva och att domänen har fått e-post under de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="9e54c-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="9e54c-109">Ett rött x för en domän anger att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna.</span><span class="sxs-lookup"><span data-stu-id="9e54c-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="9e54c-110">Detta indikerar troligen att domänen har upphört att gälla eller att MX-posten har uppdaterats felaktigt.</span><span class="sxs-lookup"><span data-stu-id="9e54c-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="9e54c-111">Kontrollera med domänregistraren eller DNS-värdtjänsten om domänen har upphört att gälla eller om domänens MX-post är felaktig.</span><span class="sxs-lookup"><span data-stu-id="9e54c-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![Informationsutfällbart i statusinsikten för toppdomänflöde](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="9e54c-113">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9e54c-113">Related topics</span></span>

<span data-ttu-id="9e54c-114">Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9e54c-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
