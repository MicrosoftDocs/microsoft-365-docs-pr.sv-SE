---
title: Låt användare återställa sina egna lösenord
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
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Lär dig hur du återställer dina lösenord med självbetjäningsverktyget för återställning av lösenord.
ms.openlocfilehash: 0842430eda8c96647dd12d0da6d0c9e0481346dc
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023767"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="15bb6-103">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="15bb6-103">Let users reset their own passwords</span></span>

<span data-ttu-id="15bb6-104">Som Microsoft 365-administratör kan du [](https://go.microsoft.com/fwlink/p/?LinkId=522677) låta personer använda självbetjäningsverktyget för återställning av lösenord så att du inte behöver återställa lösenord åt dem.</span><span class="sxs-lookup"><span data-stu-id="15bb6-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="15bb6-105">Det innebär mindre jobb för dig!</span><span class="sxs-lookup"><span data-stu-id="15bb6-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="15bb6-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="15bb6-106">Before you begin</span></span>
  
- <span data-ttu-id="15bb6-107">Självbetjäning för återställning av  lösenord för molnanvändare krävs kostnadsfritt i alla betalabonnemang för Microsoft 365 Business, Education eller Office 365 för ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="15bb6-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="15bb6-108">Det fungerar inte med utvärderingsversionen av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15bb6-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="15bb6-p103">Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.</span><span class="sxs-lookup"><span data-stu-id="15bb6-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="15bb6-p104">**Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="15bb6-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="15bb6-114">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="15bb6-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="15bb6-115">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="15bb6-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="15bb6-116">Vad är ett administratörskonto?</span><span class="sxs-lookup"><span data-stu-id="15bb6-116">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

<span data-ttu-id="15bb6-117">Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="15bb6-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="15bb6-118">Titta: Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="15bb6-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="15bb6-119">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="15bb6-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="15bb6-120">Steg: Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="15bb6-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="15bb6-121">Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="15bb6-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="15bb6-122">I <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret går</a>du till sidan **Inställningar** > **för** organisationen.</span><span class="sxs-lookup"><span data-stu-id="15bb6-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15bb6-123">I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan **Sekretess för** \> **&amp; inställningar.**</span><span class="sxs-lookup"><span data-stu-id="15bb6-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15bb6-124">I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan **Inställningar för** \>  \> **sekretesssäkerhet. &amp;**</span><span class="sxs-lookup"><span data-stu-id="15bb6-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="15bb6-125">Högst upp på sidan **Organisationsinställningar** väljer du fliken **Säkerhet &** Sekretess.</span><span class="sxs-lookup"><span data-stu-id="15bb6-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="15bb6-126">Välj **Självbetjäning för återställning av lösenord.**</span><span class="sxs-lookup"><span data-stu-id="15bb6-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="15bb6-127">Under **Självbetjäning för återställning av** lösenord väljer du Gå till Azure Portal för att aktivera **självbetjäning för återställning av lösenord.**</span><span class="sxs-lookup"><span data-stu-id="15bb6-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="15bb6-128">I det vänstra navigeringsfönstret väljer **du** Användare och går sedan till **fliken | Alla användare** väljer **lösenordsåterställning.**</span><span class="sxs-lookup"><span data-stu-id="15bb6-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="15bb6-129">På sidan **Egenskaper** väljer du **Alla för** att aktivera det för alla i företaget. Välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15bb6-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="15bb6-130">När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa lösenordet i framtiden.</span><span class="sxs-lookup"><span data-stu-id="15bb6-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="15bb6-131">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="15bb6-131">Related content</span></span>

[<span data-ttu-id="15bb6-132">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="15bb6-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="15bb6-133">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="15bb6-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="15bb6-134">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="15bb6-134">Microsoft 365 Business training videos</span></span>](../../business-video/index.yml)
