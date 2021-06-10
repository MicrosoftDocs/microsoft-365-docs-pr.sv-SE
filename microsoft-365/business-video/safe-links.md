---
title: Hantera Valv länkar
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
description: Lär dig hur du hanterar Valv för att skydda företaget från skadliga webbplatser.
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580636"
---
# <a name="manage-safe-links"></a><span data-ttu-id="60453-103">Hantera Valv länkar</span><span class="sxs-lookup"><span data-stu-id="60453-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="60453-104">Microsoft Defender för Office 365 , kallades tidigare för Microsoft 365 ATP eller Advanced Threat Protection, hjälper till att skydda företaget mot skadliga webbplatser när personer klickar på länkar i Office program.</span><span class="sxs-lookup"><span data-stu-id="60453-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="60453-105">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="60453-105">Try it!</span></span>

1. <span data-ttu-id="60453-106">Gå till [administrationscentret](https://admin.microsoft.com)och välj **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="60453-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="60453-107">Rulla nedåt till **Öka skyddet mot avancerade hot**.</span><span class="sxs-lookup"><span data-stu-id="60453-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="60453-108">Välj **Visa,** **Hantera** och sedan **ATP Valv Länkar**.</span><span class="sxs-lookup"><span data-stu-id="60453-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="60453-109">Under **Principer som gäller för hela organisationen** väljer du **Standardprincip** och sedan **redigeringsikonen.**</span><span class="sxs-lookup"><span data-stu-id="60453-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="60453-110">Ange en URL-adress som du vill blockera.</span><span class="sxs-lookup"><span data-stu-id="60453-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="60453-111">Välj **Använd säkra länkar i Office, Office för iOS och Android**; välj **Spåra inte när användare klickar på säkra länkar**; och välj **Låt inte användare klicka sig igenom säkra länkar till den ursprungliga URL:en.**</span><span class="sxs-lookup"><span data-stu-id="60453-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="60453-112">De kanske redan är markerade om du har ställt in standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="60453-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="60453-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60453-113">Select **Save**.</span></span>
1. <span data-ttu-id="60453-114">Under **Principer som gäller för specifika mottagare** väljer du **Rekommenderad regel för säkra** länkar och sedan **redigeringsikonen.**</span><span class="sxs-lookup"><span data-stu-id="60453-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="60453-115">Välj **inställningar**, rulla nedåt, ange den URL-adress som du inte vill kontrollera och välj sedan ikonen **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="60453-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="60453-116">Välj **tillämpas på** och välj sedan ditt domännamn.</span><span class="sxs-lookup"><span data-stu-id="60453-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="60453-117">Markera alla ytterligare domäner som du vill att regeln ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="60453-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="60453-118">Välj **lägg** till , **OK** och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60453-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="60453-119">ATP Valv-länkar är nu konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="60453-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="60453-120">Det kan ta upp till 30 minuter innan ändringarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="60453-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="60453-121">När en användare får ett e-postmeddelande med länkar genomsöks länkarna.</span><span class="sxs-lookup"><span data-stu-id="60453-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="60453-122">Om länkarna anses vara säkra går de att klicka på.</span><span class="sxs-lookup"><span data-stu-id="60453-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="60453-123">Men om länken finns med i listan över blockerade länkar visas ett meddelande om att länken har blockerats.</span><span class="sxs-lookup"><span data-stu-id="60453-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>