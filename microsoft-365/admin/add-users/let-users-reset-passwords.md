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
description: Läs om hur du kan ange en princip så att användare kan återställa sina egna lösenord med självbetjäningsverktyget för återställning av lösenord.
ms.openlocfilehash: 81fbe1949b8d5e4a601411703d86165f95cc7b7f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634274"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="e67b1-103">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="e67b1-103">Let users reset their own passwords</span></span>

<span data-ttu-id="e67b1-104">Som Microsoft 365 kan du låta personer använda [](https://go.microsoft.com/fwlink/p/?LinkId=522677) självbetjäningsverktyget för återställning av lösenord så att du inte behöver återställa lösenord för dem.</span><span class="sxs-lookup"><span data-stu-id="e67b1-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="e67b1-105">Det innebär mindre jobb för dig!</span><span class="sxs-lookup"><span data-stu-id="e67b1-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e67b1-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e67b1-106">Before you begin</span></span>
  
- <span data-ttu-id="e67b1-107">Självbetjäning för återställning av  lösenord för molnanvändare är kostnadsfritt i alla betalabonnemang Microsoft 365 företag, utbildning och ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="e67b1-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="e67b1-108">Det fungerar inte med utvärderingsversionen Microsoft 365 utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e67b1-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="e67b1-p103">Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.</span><span class="sxs-lookup"><span data-stu-id="e67b1-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="e67b1-p104">**Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="e67b1-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="e67b1-114">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="e67b1-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e67b1-115">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="e67b1-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="e67b1-116">Vad är ett administratörskonto?</span><span class="sxs-lookup"><span data-stu-id="e67b1-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="e67b1-117">Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="e67b1-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="e67b1-118">Titta: Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="e67b1-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="e67b1-119">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="e67b1-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="e67b1-120">Steg: Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="e67b1-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="e67b1-121">Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e67b1-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="e67b1-122">I <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret går</a>du till sidan **Inställningar**  >  **Inställningar för** organisation.</span><span class="sxs-lookup"><span data-stu-id="e67b1-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="e67b1-123">Högst upp på sidan **Organisationsinställningar** väljer du fliken **Säkerhet &** Sekretess.</span><span class="sxs-lookup"><span data-stu-id="e67b1-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="e67b1-124">Välj **Självbetjäning för återställning av lösenord.**</span><span class="sxs-lookup"><span data-stu-id="e67b1-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="e67b1-125">Under **Självbetjäning för återställning av** lösenord väljer du Gå till Azure Portal för att aktivera **självbetjäning för återställning av lösenord.**</span><span class="sxs-lookup"><span data-stu-id="e67b1-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="e67b1-126">I det vänstra navigeringsfönstret väljer **du** Användare och går sedan till **fliken | Alla användare** väljer **lösenordsåterställning.**</span><span class="sxs-lookup"><span data-stu-id="e67b1-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="e67b1-127">På sidan **Egenskaper** väljer du **Alla för** att aktivera det för alla i företaget. Välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e67b1-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="e67b1-128">När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa lösenordet i framtiden.</span><span class="sxs-lookup"><span data-stu-id="e67b1-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="e67b1-129">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="e67b1-129">Related content</span></span>

<span data-ttu-id="e67b1-130">[Ange förfalloprincip för lösenord för din organisation](../manage/set-password-expiration-policy.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="e67b1-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="e67b1-131">[Ställa in en enskild användares lösenord för att aldrig ska förfalla](set-password-to-never-expire.md)(artikel)</span><span class="sxs-lookup"><span data-stu-id="e67b1-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="e67b1-132">[Microsoft 365 Business utbildningsvideor](../../business-video/index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="e67b1-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
