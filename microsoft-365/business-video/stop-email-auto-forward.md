---
title: Stoppa e-post med automatisk vidarebefordring
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du stoppar vidarebefordran av e-postmeddelanden automatiskt.
ms.openlocfilehash: ca4383a3f9d64a123955ebe005d0fad5819d3a5d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421805"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="c12bb-103">Stoppa vidarebefordran av e-post automatiskt</span><span class="sxs-lookup"><span data-stu-id="c12bb-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="c12bb-104">Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information.</span><span class="sxs-lookup"><span data-stu-id="c12bb-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="c12bb-105">Du kan stoppa detta genom att skapa en e-postflödesregel.</span><span class="sxs-lookup"><span data-stu-id="c12bb-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="c12bb-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="c12bb-106">Try it!</span></span>

1. <span data-ttu-id="c12bb-107">I administrationscentret för Microsoft 365 väljer du **Exchange,** e-postflöde och på fliken Regler väljer du plustecknet och skapar **en ny regel.** </span><span class="sxs-lookup"><span data-stu-id="c12bb-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="c12bb-108">Välj **Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-108">Select **More options**.</span></span> <span data-ttu-id="c12bb-109">Ge den nya regeln ett namn.</span><span class="sxs-lookup"><span data-stu-id="c12bb-109">Name your new rule.</span></span>
1. <span data-ttu-id="c12bb-110">Öppna listrutan för att tillämpa **regeln om,** markera **avsändaren och** sedan är **extern intern.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="c12bb-111">Välj **i organisationen och** sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="c12bb-112">Välj **Lägg till** villkor, öppna listrutan, välj Egenskaper för **meddelandet** och ange **sedan meddelandetypen.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="c12bb-113">Öppna **listrutan Välj meddelandetyp,** välj **Vidarebefordra automatiskt** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="c12bb-114">Öppna **listrutan Gör följande,** välj **Blockera meddelandet** och avvisa sedan meddelandet och ge **en förklaring.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="c12bb-115">Ange meddelandetexten för din förklaring och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="c12bb-116">Rulla längst ned och välj **Spara.**</span><span class="sxs-lookup"><span data-stu-id="c12bb-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="c12bb-117">Din regel har skapats och hackare kommer inte längre att kunna vidarebefordra meddelanden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c12bb-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>