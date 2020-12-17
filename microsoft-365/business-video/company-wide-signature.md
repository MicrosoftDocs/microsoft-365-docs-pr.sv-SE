---
title: Skapa en företagsomfattande signatur
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
description: Lär dig hur du skapar en e-postsignatur för hela företaget.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703028"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="f016d-103">Skapa en e-postsignatur för hela företaget</span><span class="sxs-lookup"><span data-stu-id="f016d-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="f016d-104">En e-postsignatur för hela företaget visas i alla e-postmeddelanden som skickas av personer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f016d-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="f016d-105">Du kan använda det för att visa viktig information, till exempel företagets kontakt information eller en juridisk fri skrivning.</span><span class="sxs-lookup"><span data-stu-id="f016d-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="f016d-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="f016d-106">Try it!</span></span>

1. <span data-ttu-id="f016d-107">I administrations centret för Microsoft 365 väljer du **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f016d-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="f016d-108">Välj **e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="f016d-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="f016d-109">Välj **Lägg till +** och sedan **Använd fri skrivningar**.</span><span class="sxs-lookup"><span data-stu-id="f016d-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="f016d-110">På sidan **ny regel** :</span><span class="sxs-lookup"><span data-stu-id="f016d-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="f016d-111">Ange ett namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="f016d-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="f016d-112">I list rutan **Använd denna regel** väljer **du Använd för alla meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="f016d-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="f016d-113">I list rutan **gör följande** kontrollerar **du att tillägg till fri skrivning** visas.</span><span class="sxs-lookup"><span data-stu-id="f016d-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="f016d-114">På höger sida av sidan väljer du **Ange text** och anger sedan texten för din e-postsignatur i text rutan **Ange fri skrivning** .</span><span class="sxs-lookup"><span data-stu-id="f016d-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="f016d-115">Du kan förbättra utseendet på din signatur genom att formatera texten med HTML.</span><span class="sxs-lookup"><span data-stu-id="f016d-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="f016d-116">Om du vill att en bild ska visas i din signatur måste du använda en offentlig URL för bilden.</span><span class="sxs-lookup"><span data-stu-id="f016d-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="f016d-117">Bläddra till bilden på webben, högerklicka på den och välj **Kopiera bild adress**.</span><span class="sxs-lookup"><span data-stu-id="f016d-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="f016d-118">Klistra in adressen i text rutan **Ange fri skrivning** .</span><span class="sxs-lookup"><span data-stu-id="f016d-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="f016d-119">Välj **OK** och sedan bläddra nedåt.</span><span class="sxs-lookup"><span data-stu-id="f016d-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="f016d-120">Om du vill att signaturen ska fungera med krypterade e-postmeddelanden lägger du till ett reserv alternativ.</span><span class="sxs-lookup"><span data-stu-id="f016d-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="f016d-121">Välj **Markera ett** på sidan, Välj **Radbryt** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="f016d-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="f016d-122">Rulla nedåt och lämna läget inställt på **tvinga** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f016d-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="f016d-123">Ett varnings meddelande visas.</span><span class="sxs-lookup"><span data-stu-id="f016d-123">A warning message will appear.</span></span> <span data-ttu-id="f016d-124">Välj **Ja** om du vill tillämpa regeln på alla framtida meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f016d-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="f016d-125">Din signatur har skapats.</span><span class="sxs-lookup"><span data-stu-id="f016d-125">Your signature has been created.</span></span> <span data-ttu-id="f016d-126">När du skickar nästa e-postmeddelande visas inte signaturen som du har skapat, men e-postmottagarna visas.</span><span class="sxs-lookup"><span data-stu-id="f016d-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>