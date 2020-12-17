---
title: Hantera säkra länkar
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
description: Lär dig hur du hanterar säkra Länkar för att skydda ditt företag från skadliga webbplatser.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702665"
---
# <a name="manage-safe-links"></a><span data-ttu-id="eb85e-103">Hantera säkra länkar</span><span class="sxs-lookup"><span data-stu-id="eb85e-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="eb85e-104">Microsoft Defender för Office 365, kallades tidigare Microsoft 365 ATP eller Avancerat skydd, hjälper till att skydda ditt företag mot skadliga webbplatser när personer klickar på länkar i Office-program.</span><span class="sxs-lookup"><span data-stu-id="eb85e-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="eb85e-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="eb85e-105">Try it!</span></span>

1. <span data-ttu-id="eb85e-106">Gå till [administrations centret](https://admin.microsoft.com)och välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="eb85e-107">Rulla nedåt för att **öka skyddet mot avancerade hot**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="eb85e-108">Välj **Visa**, **Hantera** och sedan **ATP-säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="eb85e-109">Under **principer som gäller för hela organisationen** väljer du **standard** principen och sedan **redigerings** ikonen.</span><span class="sxs-lookup"><span data-stu-id="eb85e-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="eb85e-110">Ange en URL som du vill blockera.</span><span class="sxs-lookup"><span data-stu-id="eb85e-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="eb85e-111">Välj **Använd säkra länkar i Office-program, Office för iOS och Android**. Välj **Spåra inte när användare klickar på säkra länkar**; och välj **Tillåt inte att användare klickar via säkra länkar till original-URL: en**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="eb85e-112">Dessa kanske redan är markerade om du har ställt in standard policyn.</span><span class="sxs-lookup"><span data-stu-id="eb85e-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="eb85e-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-113">Select **Save**.</span></span>
1. <span data-ttu-id="eb85e-114">Välj **regel för rekommenderade säkra länkar** under **principer som gäller för specifika mottagare** och välj sedan **redigerings** ikonen.</span><span class="sxs-lookup"><span data-stu-id="eb85e-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="eb85e-115">Välj **Inställningar**, Bläddra ned, ange den URL som du inte vill ska markeras och välj sedan ikonen **Lägg till** .</span><span class="sxs-lookup"><span data-stu-id="eb85e-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="eb85e-116">Välj **tillämpas på** och välj sedan ditt domän namn.</span><span class="sxs-lookup"><span data-stu-id="eb85e-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="eb85e-117">Markera de ytterligare domäner som du vill tillämpa regeln på.</span><span class="sxs-lookup"><span data-stu-id="eb85e-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="eb85e-118">Välj **Lägg till**, **OK** och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb85e-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="eb85e-119">Nu har du konfigurerat ATP-länkar.</span><span class="sxs-lookup"><span data-stu-id="eb85e-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="eb85e-120">Tillåt upp till 30 minuter innan ändringarna börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="eb85e-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="eb85e-121">När en användare får ett e-postmeddelande med länkar genomsöks länkarna.</span><span class="sxs-lookup"><span data-stu-id="eb85e-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="eb85e-122">Om länkarna betraktas som säkra kan de vara Klicka bara på dem.</span><span class="sxs-lookup"><span data-stu-id="eb85e-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="eb85e-123">Om länken finns i blockeringslistan visas ett meddelande om att det har blockerats.</span><span class="sxs-lookup"><span data-stu-id="eb85e-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>