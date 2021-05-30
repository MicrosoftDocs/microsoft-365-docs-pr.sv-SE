---
title: Stoppa e-post med automatisk vidarebefordring
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Lär dig hur du stoppar automatisk vidarebefordran av e-postmeddelanden genom att skapa en e-postflödesregel för att undvika stöld av upphovsrättsskyddad information.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706480"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="45099-103">Stoppa vidarebefordran av e-post automatiskt</span><span class="sxs-lookup"><span data-stu-id="45099-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="45099-104">Titta på: Stoppa e-postmeddelanden om automatisk vidarebefordran</span><span class="sxs-lookup"><span data-stu-id="45099-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="45099-105">Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information.</span><span class="sxs-lookup"><span data-stu-id="45099-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="45099-106">Du kan stoppa detta genom att skapa en e-postflödesregel.</span><span class="sxs-lookup"><span data-stu-id="45099-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="45099-107">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="45099-107">Try it!</span></span>

1. <span data-ttu-id="45099-108">I Microsoft 365 väljer du **Exchange**, e-postflöde och på  fliken Regler väljer du plustecknet och **väljer skapa en ny regel.** </span><span class="sxs-lookup"><span data-stu-id="45099-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="45099-109">Välj **Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="45099-109">Select **More options**.</span></span> <span data-ttu-id="45099-110">Ge den nya regeln ett namn.</span><span class="sxs-lookup"><span data-stu-id="45099-110">Name your new rule.</span></span>
1. <span data-ttu-id="45099-111">Öppna sedan listrutan för att **tillämpa regeln om**, välj avsändaren **och** sedan är **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="45099-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="45099-112">Välj **Inom organisationen** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="45099-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="45099-113">Välj **Lägg till** villkor , öppna listrutan, välj Egenskaper för **meddelande** och inkludera **sedan meddelandetypen**.</span><span class="sxs-lookup"><span data-stu-id="45099-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="45099-114">Öppna **listrutan välj** meddelandetyp, välj **Vidarebefordra automatiskt** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="45099-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="45099-115">Öppna **listrutan Gör följande,** välj **Blockera meddelandet och avvisa** sedan meddelandet och ge en **förklaring**.</span><span class="sxs-lookup"><span data-stu-id="45099-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="45099-116">Ange meddelandetexten för din förklaring och välj **sedan OK.**</span><span class="sxs-lookup"><span data-stu-id="45099-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="45099-117">Rulla längst ned och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="45099-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="45099-118">Din regel har skapats och hackare kommer inte längre att kunna vidarebefordra meddelanden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="45099-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="45099-119">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="45099-119">Related content</span></span>

<span data-ttu-id="45099-120">[Lägga till ytterligare ett e-postalias för en användare](../admin/email/add-another-email-alias-for-a-user.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45099-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="45099-121">[Konfigurera vidarebefordran av e-post i Microsoft 365](../admin/email/configure-email-forwarding.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45099-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="45099-122">[Hitta och korrigera problem med e-postleverans som Office 365 för företag-administratör](/exchange/troubleshoot/email-delivery/email-delivery-issues) (artikel)</span><span class="sxs-lookup"><span data-stu-id="45099-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>