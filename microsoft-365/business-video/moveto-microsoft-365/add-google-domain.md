---
title: Lägga till en Google Workspace-domän
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du flyttar din domän från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925008"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="b5d03-103">Lägga till en Google Workspace-domän i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5d03-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="b5d03-104">Lägg till din Google Workspace-domän i Microsoft 365 för företag så att du kan fortsätta använda din e-postadress för företaget.</span><span class="sxs-lookup"><span data-stu-id="b5d03-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="b5d03-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="b5d03-105">Try it!</span></span>

1. <span data-ttu-id="b5d03-106">Gå till [administrationscentret för Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b5d03-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b5d03-107">I det vänstra navigeringsfältet i administrationscentret för Microsoft 365 väljer du **Visa alla** inställningar **och** sedan **Domäner.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="b5d03-108">Välj **Lägg till domän,** ange domännamnet och välj Använd **den här domänen.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="b5d03-109">Välj Lägg **till en TXT-post i domänerna DNS-poster,** **välj Fortsätt** och kopiera TXT-värdet.</span><span class="sxs-lookup"><span data-stu-id="b5d03-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="b5d03-110">Gå tillbaka till [Googles administratörskonsol](https://admin.google.com)och välj **Domäner,** Hantera **domäner,** Visa **information,** Hantera **domän,** **DNS** och bläddra ned till **Anpassade resursposter.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="b5d03-111">Öppna listrutan posttyp, välj **TXT,** klistra in TXT-värdet du kopierade och välj Sedan **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="b5d03-112">Uppdateringen tar vanligtvis ett faktum inom några minuter men kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="b5d03-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="b5d03-113">Gå tillbaka till administrationscentret för Microsoft 365, **välj** Verifiera och stäng **sedan.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="b5d03-114">Om du vill ange din domän som primär e-postadress för användarna väljer du Användare aktiva användare **i** det  >  **vänstra navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="b5d03-115">Välj en användare, välj **Hantera användarnamn och e-post,** Redigera, välj din domän i listrutan och välj sedan **Klar** och Spara **ändringar.**</span><span class="sxs-lookup"><span data-stu-id="b5d03-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="b5d03-116">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="b5d03-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="b5d03-117">När du är klar är du redo att installera Office-program och migrera dina e-post- och kalenderobjekt till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5d03-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 