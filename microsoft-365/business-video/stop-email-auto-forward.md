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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du stoppar vidarebefordran av e-postmeddelanden automatiskt.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925892"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="b9329-103">Stoppa vidarebefordran av e-post automatiskt</span><span class="sxs-lookup"><span data-stu-id="b9329-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="b9329-104">Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information.</span><span class="sxs-lookup"><span data-stu-id="b9329-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="b9329-105">Du kan stoppa detta genom att skapa en e-postflödesregel.</span><span class="sxs-lookup"><span data-stu-id="b9329-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="b9329-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="b9329-106">Try it!</span></span>

1. <span data-ttu-id="b9329-107">I administrationscentret för Microsoft 365 väljer du **Exchange,** e-postflöde och på fliken Regler väljer du plustecknet och skapar **en ny regel.** </span><span class="sxs-lookup"><span data-stu-id="b9329-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="b9329-108">Välj **Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="b9329-108">Select **More options**.</span></span> <span data-ttu-id="b9329-109">Ge den nya regeln ett namn.</span><span class="sxs-lookup"><span data-stu-id="b9329-109">Name your new rule.</span></span>
1. <span data-ttu-id="b9329-110">Öppna listrutan för att tillämpa **regeln om,** markera **avsändaren och** sedan är **extern intern.**</span><span class="sxs-lookup"><span data-stu-id="b9329-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="b9329-111">Markera **i organisationen** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="b9329-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="b9329-112">Välj **Lägg till** villkor, öppna listrutan, välj Egenskaper för **meddelandet** och ta sedan **med meddelandetypen.**</span><span class="sxs-lookup"><span data-stu-id="b9329-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="b9329-113">Öppna **listrutan Välj meddelandetyp,** välj **Vidarebefordra automatiskt** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="b9329-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="b9329-114">Öppna **listrutan Gör följande,** välj **Blockera meddelandet** och avvisa sedan meddelandet och ge **en förklaring.**</span><span class="sxs-lookup"><span data-stu-id="b9329-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="b9329-115">Ange meddelandetexten för din förklaring och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="b9329-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="b9329-116">Rulla längst ned och välj **Spara.**</span><span class="sxs-lookup"><span data-stu-id="b9329-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="b9329-117">Din regel har skapats och hackare kommer inte längre att kunna vidarebefordra meddelanden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b9329-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>