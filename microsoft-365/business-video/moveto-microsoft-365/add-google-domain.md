---
title: Lägga till din Google Workspace-domän
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
description: Lär dig hur du flyttar din domän från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794747"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="b5f47-103">Lägga till din Google Workspace-domän i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5f47-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="b5f47-104">Lägg till din Google Workspace-domän till Microsoft 365 för företag så att du kan fortsätta att använda din företags e-postadress.</span><span class="sxs-lookup"><span data-stu-id="b5f47-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="b5f47-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="b5f47-105">Try it!</span></span>

1. <span data-ttu-id="b5f47-106">Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b5f47-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b5f47-107">I administrations centret för Microsoft 365 väljer du **Visa alla**, **Inställningar** och sedan **domäner** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="b5f47-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="b5f47-108">Välj **Lägg till domän**, ange ditt domän namn och välj sedan **Använd denna domän**.</span><span class="sxs-lookup"><span data-stu-id="b5f47-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="b5f47-109">Välj, **Lägg till en TXT-post till domänernas DNS-poster**, Välj **Fortsätt** och kopiera värdet txt.</span><span class="sxs-lookup"><span data-stu-id="b5f47-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="b5f47-110">Gå tillbaka till [Google Admin Console](https://admin.google.com), Välj **domäner**, **hantera domäner**, **Visa information**, **Hantera domän**, **DNS** och sedan bläddra ned till **anpassade resurs poster**.</span><span class="sxs-lookup"><span data-stu-id="b5f47-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="b5f47-111">Öppna List rutan Record Type, Välj **txt**, klistra in det txt-värde som du kopierade och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b5f47-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="b5f47-112">Det tar vanligt vis några minuter att uppdatera uppdateringen, men det kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="b5f47-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="b5f47-113">Gå tillbaka till administrations centret för Microsoft 365, Välj **Verifiera** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b5f47-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="b5f47-114">Om du vill ange din domän som primär e-postadress för dina användare väljer du **användare**  >  **aktiva användare** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="b5f47-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="b5f47-115">Välj en användare, Välj **hantera användar namn och e-post**, **Redigera**, välj din domän i list rutan och välj sedan **klar** och **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b5f47-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="b5f47-116">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="b5f47-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="b5f47-117">När du är klar kan du installera Office-apparna och migrera dina e-post-och Kalender objekt till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5f47-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 