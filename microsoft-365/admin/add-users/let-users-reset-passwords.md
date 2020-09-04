---
title: Låt användare återställa sina egna lösenord
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Lär dig hur du återställer dina lösen ord med standard verktyget för återställning av lösen ord.
ms.openlocfilehash: 1684afd1baf32acc6c4245938b2ac7ee024d7374
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361813"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="031a4-103">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="031a4-103">Let users reset their own passwords</span></span>

<span data-ttu-id="031a4-104">Som Microsoft 365-administratör kan du låta andra använda [standard verktyget för återställning av lösen ord](https://go.microsoft.com/fwlink/p/?LinkId=522677) så att du inte behöver återställa lösen ord för dem.</span><span class="sxs-lookup"><span data-stu-id="031a4-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="031a4-105">Det innebär mindre jobb för dig!</span><span class="sxs-lookup"><span data-stu-id="031a4-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="031a4-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="031a4-106">Before you begin</span></span>
  
- <span data-ttu-id="031a4-107">Du får själv återställning av lösen ord för moln användare **utan kostnad** för Microsoft 365-verksamhet, utbildning eller ideell betalning.</span><span class="sxs-lookup"><span data-stu-id="031a4-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="031a4-108">Den fungerar inte med utvärderings versionen av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="031a4-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="031a4-p103">Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.</span><span class="sxs-lookup"><span data-stu-id="031a4-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="031a4-p104">**Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="031a4-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="031a4-114">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="031a4-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="031a4-115">För att utföra de här stegen måste du logga in med ditt Microsoft 365-administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="031a4-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="031a4-116">Vad är ett administratörs konto?</span><span class="sxs-lookup"><span data-stu-id="031a4-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="031a4-117">Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="031a4-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="031a4-118">Titta: Låt användare återställa sina egna lösen ord</span><span class="sxs-lookup"><span data-stu-id="031a4-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="031a4-119">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="031a4-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="031a4-120">Steg: Låt andra återställa sina egna lösen ord</span><span class="sxs-lookup"><span data-stu-id="031a4-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="031a4-121">Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="031a4-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="031a4-122">Gå till sidan **Inställningar** organisations inställningar i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret</a> > **Org settings** .</span><span class="sxs-lookup"><span data-stu-id="031a4-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="031a4-123">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrations centret</a>går du till sidan **Inställningar** för \> **säkerhets &amp; Sekretess** .</span><span class="sxs-lookup"><span data-stu-id="031a4-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="031a4-124">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrations centret</a>går du till sidan **Inställningar** för \> **Settings** \> **säkerhets &amp; Sekretess** .</span><span class="sxs-lookup"><span data-stu-id="031a4-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="031a4-125">Högst upp på sidan **organisations inställningar** väljer du fliken **säkerhet & sekretess** .</span><span class="sxs-lookup"><span data-stu-id="031a4-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="031a4-126">Välj **självbetjäning för återställning av lösen ord**.</span><span class="sxs-lookup"><span data-stu-id="031a4-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="031a4-127">Under **Automatisk återställning av lösen ord**väljer **du gå till Azure-portalen för att aktivera automatisk återställning av lösen ord**.</span><span class="sxs-lookup"><span data-stu-id="031a4-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="031a4-128">I det vänstra navigerings fönstret väljer **du användare**och sedan, på **användare | Sidan alla användare** väljer du **Återställ lösen ord**.</span><span class="sxs-lookup"><span data-stu-id="031a4-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="031a4-129">På sidan **Egenskaper** väljer du **alla** för att aktivera det för alla i företaget och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="031a4-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="031a4-130">När användarna loggar in uppmanas de att ange ytterligare kontakt information som hjälper dem att återställa lösen ordet i framtiden.</span><span class="sxs-lookup"><span data-stu-id="031a4-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="031a4-131">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="031a4-131">Related content</span></span>

[<span data-ttu-id="031a4-132">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="031a4-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="031a4-133">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="031a4-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="031a4-134">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="031a4-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
