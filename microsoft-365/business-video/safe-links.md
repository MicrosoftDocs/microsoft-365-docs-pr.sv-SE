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
description: Lär dig hur du hanterar säkra länkar för att skydda företaget från skadliga webbplatser.
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422256"
---
# <a name="manage-safe-links"></a><span data-ttu-id="b93f6-103">Hantera säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b93f6-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="b93f6-104">Microsoft Defender för Office 365 , som tidigare hette Microsoft 365 ATP eller Advanced Threat Protection, hjälper dig att skydda företaget mot skadliga webbplatser när personer klickar på länkar i Office-program.</span><span class="sxs-lookup"><span data-stu-id="b93f6-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="b93f6-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="b93f6-105">Try it!</span></span>

1. <span data-ttu-id="b93f6-106">Gå till [administrationscentret](https://admin.microsoft.com)och välj **Installation.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="b93f6-107">Rulla nedåt för **att öka skyddet mot avancerade hot.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="b93f6-108">Välj **Visa,** **Hantera** och sedan **ATP – säkra länkar.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="b93f6-109">Under **Principer som gäller för hela organisationen** väljer du **Standardprincip** och sedan **redigeringsikonen.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="b93f6-110">Ange en URL som du vill blockera.</span><span class="sxs-lookup"><span data-stu-id="b93f6-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="b93f6-111">Välj **Använd säkra länkar i Office-appar, Office för iOS och Android.** välj **Spåra inte när användare klickar på säkra länkar**; och välj **Låt inte användare klicka igenom säkra länkar till den ursprungliga URL:en.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="b93f6-112">De kanske redan är markerade om du har angett standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="b93f6-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="b93f6-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b93f6-113">Select **Save**.</span></span>
1. <span data-ttu-id="b93f6-114">Under **Principer som gäller för specifika mottagare** väljer du regeln **Rekommenderade** säkra länkar och sedan **ikonen** Redigera.</span><span class="sxs-lookup"><span data-stu-id="b93f6-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="b93f6-115">Välj **inställningar,** rulla nedåt, ange den URL-adress som du inte vill kontrollera och välj sedan ikonen **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="b93f6-116">Välj **det du** vill använda på och välj sedan domännamnet.</span><span class="sxs-lookup"><span data-stu-id="b93f6-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="b93f6-117">Markera alla ytterligare domäner som du vill att regeln ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="b93f6-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="b93f6-118">Välj **Lägg till,** **OK** och sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="b93f6-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="b93f6-119">ATP – säkra länkar är nu konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="b93f6-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="b93f6-120">Det kan ta upp till 30 minuter innan ändringarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="b93f6-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="b93f6-121">När en användare får ett e-postmeddelande med länkar genomsöks länkarna.</span><span class="sxs-lookup"><span data-stu-id="b93f6-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="b93f6-122">Om länkarna anses vara säkra går de att klicka på.</span><span class="sxs-lookup"><span data-stu-id="b93f6-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="b93f6-123">Men om länken finns med i listan över blockerade ser användarna ett meddelande om att den har blockerats.</span><span class="sxs-lookup"><span data-stu-id="b93f6-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>