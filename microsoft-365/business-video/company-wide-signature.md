---
title: Skapa en företagsomfattande signatur
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du skapar en e-postsignatur för hela företaget.
ms.openlocfilehash: 669c61d17784641d1ecc88ac0952a46575c7898b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706268"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="e0354-103">Skapa en företagsomfattande e-postsignatur</span><span class="sxs-lookup"><span data-stu-id="e0354-103">Create a company-wide email signature</span></span>

## <a name="watch-create-a-company-wide-email-signature"></a><span data-ttu-id="e0354-104">Titta: Skapa en företagsomfattande e-postsignatur</span><span class="sxs-lookup"><span data-stu-id="e0354-104">Watch: Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="e0354-105">En företagsomfattande e-postsignatur visas i alla e-postmeddelanden som skickas av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e0354-105">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="e0354-106">Du kan använda den för att visa viktig information, till exempel företagets kontaktinformation eller en juridisk ansvarsfriskrivning.</span><span class="sxs-lookup"><span data-stu-id="e0354-106">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="e0354-107">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="e0354-107">Try it!</span></span>

1. <span data-ttu-id="e0354-108">I Microsoft 365 väljer du **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e0354-108">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="e0354-109">Välj **E-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="e0354-109">Select **Mail flow**.</span></span>
1. <span data-ttu-id="e0354-110">Välj **Lägg till +** och välj sedan Använd **ansvarsfriskrivningar.**</span><span class="sxs-lookup"><span data-stu-id="e0354-110">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="e0354-111">På **sidan Ny** regel:</span><span class="sxs-lookup"><span data-stu-id="e0354-111">On the **New rule** page:</span></span>
    1. <span data-ttu-id="e0354-112">Ange ett namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="e0354-112">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="e0354-113">I **listrutan Använd den här** regeln om väljer du **Använd för alla meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="e0354-113">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="e0354-114">I **listrutan Gör följande** kontrollerar du att **Lägg till ansvarsfriskrivningen** visas.</span><span class="sxs-lookup"><span data-stu-id="e0354-114">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="e0354-115">Till höger på sidan väljer du Skriv **text** och skriver sedan texten för din e-postsignatur i textrutan Ange text **för** ansvarsfriskrivning.</span><span class="sxs-lookup"><span data-stu-id="e0354-115">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="e0354-116">Du kan förbättra utseendet på din signatur genom att formatera texten med HTML.</span><span class="sxs-lookup"><span data-stu-id="e0354-116">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="e0354-117">Om du vill att en bild ska visas i signaturen måste du använda en offentlig URL för den bilden.</span><span class="sxs-lookup"><span data-stu-id="e0354-117">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="e0354-118">Bläddra till bilden på webben, högerklicka på den och välj **Kopiera bildadress**.</span><span class="sxs-lookup"><span data-stu-id="e0354-118">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="e0354-119">Klistra in adressen i rutan Ange **text för ansvarsfriskrivning.**</span><span class="sxs-lookup"><span data-stu-id="e0354-119">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="e0354-120">Välj **OK** och rulla sedan nedåt.</span><span class="sxs-lookup"><span data-stu-id="e0354-120">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="e0354-121">Om du vill vara säker på att signaturen fungerar med krypterade e-postmeddelanden kan du lägga till ett reservalternativ.</span><span class="sxs-lookup"><span data-stu-id="e0354-121">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="e0354-122">Välj Välj ett till höger på **sidan,** välj **Radbryt** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="e0354-122">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="e0354-123">Rulla nedåt och lämna läget Tvinga **och** välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e0354-123">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="e0354-124">Ett varningsmeddelande visas.</span><span class="sxs-lookup"><span data-stu-id="e0354-124">A warning message will appear.</span></span> <span data-ttu-id="e0354-125">Välj **Ja** om du vill tillämpa regeln på alla framtida meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e0354-125">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="e0354-126">Signaturen har skapats.</span><span class="sxs-lookup"><span data-stu-id="e0354-126">Your signature has been created.</span></span> <span data-ttu-id="e0354-127">När du skickar nästa e-postmeddelande visas inte signaturen som du just har skapat, men e-postmottagarna kommer att se den.</span><span class="sxs-lookup"><span data-stu-id="e0354-127">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>