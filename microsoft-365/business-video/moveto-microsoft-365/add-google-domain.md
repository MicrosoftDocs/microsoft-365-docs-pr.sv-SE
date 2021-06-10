---
title: Lägga till din Google Workspace-domän
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578777"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="748a1-103">Lägg till Google Workspace-domänen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="748a1-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="748a1-104">Lägg till Google Workspace-domänen i Microsoft 365 för företag så att du kan fortsätta använda din e-postadress för företaget.</span><span class="sxs-lookup"><span data-stu-id="748a1-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="748a1-105">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="748a1-105">Try it!</span></span>

1. <span data-ttu-id="748a1-106">Gå till [Microsoft 365 administrationscentret.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="748a1-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="748a1-107">I det Microsoft 365 navigeringscentret i vänstra navigeringsfältet väljer du Visa alla **,** **Inställningar** och sedan **Domäner.**</span><span class="sxs-lookup"><span data-stu-id="748a1-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="748a1-108">Välj **Add domain**, enter your domain name och select Use this **domain**.</span><span class="sxs-lookup"><span data-stu-id="748a1-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="748a1-109">Välj Add **a TXT record to the domains DNS records**, select **Continue** och copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="748a1-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="748a1-110">Gå tillbaka till administratörskonsolen för [Google](https://admin.google.com), välj **Domäner** **,** Hantera domäner **,** Visa information , Hantera **domän,** **DNS** och rulla ned till **Anpassade resursposter**.</span><span class="sxs-lookup"><span data-stu-id="748a1-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="748a1-111">Öppna listrutan record type, välj **TXT**, klistra in TXT-värdet du kopierade och välj sedan **Add**.</span><span class="sxs-lookup"><span data-stu-id="748a1-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="748a1-112">Uppdateringen tar normalt ett faktum inom några minuter men kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="748a1-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="748a1-113">Återgå till Microsoft 365, välj **Verifiera** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="748a1-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="748a1-114">Om du vill ange din domän som primär e-postadress för användarna väljer du Användare aktiva användare i **det**  >  **vänstra navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="748a1-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="748a1-115">Välj en användare, välj **Hantera användarnamn och e-post** **,** Redigera , välj din domän i listrutan och välj sedan **Klar** och **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="748a1-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="748a1-116">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="748a1-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="748a1-117">När du är klar är du redo att installera Office och migrera dina e-post- och kalenderobjekt till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="748a1-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 