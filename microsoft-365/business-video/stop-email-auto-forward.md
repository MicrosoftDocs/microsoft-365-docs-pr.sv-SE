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
description: Lär dig hur du stoppar automatisk vidarebefordran av e-postmeddelanden.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903688"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="3519e-103">Stoppa vidarebefordran av e-post automatiskt</span><span class="sxs-lookup"><span data-stu-id="3519e-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="3519e-104">Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information.</span><span class="sxs-lookup"><span data-stu-id="3519e-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="3519e-105">Du kan stoppa detta genom att skapa en e-postflödesregel.</span><span class="sxs-lookup"><span data-stu-id="3519e-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="3519e-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="3519e-106">Try it!</span></span>

1. <span data-ttu-id="3519e-107">I administrationscentret för Microsoft 365 väljer du **Exchange** **,** e-postflöde och på fliken Regler väljer du plustecknet och **sedan Skapa en ny regel.** </span><span class="sxs-lookup"><span data-stu-id="3519e-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="3519e-108">Välj **Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="3519e-108">Select **More options**.</span></span> <span data-ttu-id="3519e-109">Ge den nya regeln ett namn.</span><span class="sxs-lookup"><span data-stu-id="3519e-109">Name your new rule.</span></span>
1. <span data-ttu-id="3519e-110">Öppna sedan listrutan för att **tillämpa regeln om**, välj avsändaren **och** sedan är **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="3519e-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="3519e-111">Välj **Inom organisationen** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="3519e-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="3519e-112">Välj **Lägg till** villkor , öppna listrutan, välj Egenskaper för **meddelande** och inkludera **sedan meddelandetypen**.</span><span class="sxs-lookup"><span data-stu-id="3519e-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="3519e-113">Öppna **listrutan välj** meddelandetyp, välj **Vidarebefordra automatiskt** och sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="3519e-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="3519e-114">Öppna **listrutan Gör följande,** välj **Blockera meddelandet och avvisa** sedan meddelandet och ge en **förklaring**.</span><span class="sxs-lookup"><span data-stu-id="3519e-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="3519e-115">Ange meddelandetexten för din förklaring och välj **sedan OK.**</span><span class="sxs-lookup"><span data-stu-id="3519e-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="3519e-116">Rulla längst ned och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3519e-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="3519e-117">Din regel har skapats och hackare kommer inte längre att kunna vidarebefordra meddelanden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3519e-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="3519e-118">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="3519e-118">Related content</span></span>

<span data-ttu-id="3519e-119">Lägga till ytterligare [ett e-postalias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) för en användare (artikel) Konfigurera vidarebefordran av e-post i [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (artikel) Hitta och korrigera problem med e-postleverans som administratör för [Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) för företag (artikel)</span><span class="sxs-lookup"><span data-stu-id="3519e-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>