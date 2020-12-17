---
title: Stoppa e-postvidarebefordrade meddelanden automatiskt
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du stoppar automatisk vidarebefordran av e-post.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702595"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="d5996-103">Stoppa automatisk vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="d5996-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="d5996-104">Om en hackare får åtkomst till en användares post låda kan de automatiskt vidarebefordra användarens e-post till en extern adress och stjäla ägande information.</span><span class="sxs-lookup"><span data-stu-id="d5996-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="d5996-105">Du kan stoppa det genom att skapa en regel för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="d5996-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="d5996-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="d5996-106">Try it!</span></span>

1. <span data-ttu-id="d5996-107">I Microsoft 365 Admin Center väljer du **Exchange**, **mail flöde** och på fliken **regler** väljer du plus tecknet och väljer **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="d5996-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="d5996-108">Välj **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="d5996-108">Select **More options**.</span></span> <span data-ttu-id="d5996-109">Namnge den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="d5996-109">Name your new rule.</span></span>
1. <span data-ttu-id="d5996-110">Öppna sedan den nedrullningsbara List rutan för **Använd den här regeln om**, Välj **avsändaren** och sedan **är extern intern**.</span><span class="sxs-lookup"><span data-stu-id="d5996-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="d5996-111">Välj **inuti organisationen** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5996-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="d5996-112">Välj **Lägg till villkor**, öppna List rutan, Välj **meddelande egenskaperna** och ange sedan **meddelande typen**.</span><span class="sxs-lookup"><span data-stu-id="d5996-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="d5996-113">Öppna List rutan **Välj meddelande typ** , Välj **Auto-Forward** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5996-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="d5996-114">Öppna den nedrullningsbara List rutan **gör följande** , Välj **blockera meddelandet** **och ignorera sedan meddelandet och ta med en förklaring**.</span><span class="sxs-lookup"><span data-stu-id="d5996-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="d5996-115">Ange meddelande texten för din förklaring och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5996-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="d5996-116">Bläddra längst ned och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5996-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="d5996-117">Din regel har skapats och hackare kommer inte längre att kunna Vidarekoppla meddelanden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d5996-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>