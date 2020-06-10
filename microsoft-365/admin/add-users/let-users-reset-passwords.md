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
description: Läs om hur du kan återställa dina lösenord med hjälp av verktyget för återställning av lösenord med självbetjäning.
ms.openlocfilehash: 40f094489a1981302e97043b019e8c90a52ffc55
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678688"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="4b088-103">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="4b088-103">Let users reset their own passwords</span></span>

<span data-ttu-id="4b088-104">Står folk i kö och ber dig återställa deras lösenord?</span><span class="sxs-lookup"><span data-stu-id="4b088-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="4b088-105">Som Microsoft 365-administratör kan du låta användarna använda [självbetjäningsverktyget](https://go.microsoft.com/fwlink/p/?LinkId=522677) för återställning av lösenord så att du inte behöver återställa lösenord för dem.</span><span class="sxs-lookup"><span data-stu-id="4b088-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="4b088-106">Det innebär mindre jobb för dig!</span><span class="sxs-lookup"><span data-stu-id="4b088-106">Less work for you!</span></span> 
  
<span data-ttu-id="4b088-107">Här är några saker du kan behöva veta:</span><span class="sxs-lookup"><span data-stu-id="4b088-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="4b088-108">Du får lösenordsåterställning med självbetjäning för molnanvändare **gratis** med alla Microsoft 365-företag, utbildningar eller avgiftsbetalda organisationer.</span><span class="sxs-lookup"><span data-stu-id="4b088-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="4b088-109">Det fungerar inte med Microsoft 365 rättegång.</span><span class="sxs-lookup"><span data-stu-id="4b088-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="4b088-p103">Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.</span><span class="sxs-lookup"><span data-stu-id="4b088-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="4b088-p104">**Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="4b088-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="4b088-115">Titta på en kort video om att låta användare återställa sina egna lösenord.</span><span class="sxs-lookup"><span data-stu-id="4b088-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="4b088-116">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="4b088-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="4b088-117">Låt andra återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="4b088-117">Let people reset their own passwords</span></span>

<span data-ttu-id="4b088-118">Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4b088-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4b088-119">Gå till sidan **Inställningar** org i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret.</a> > **Org settings**</span><span class="sxs-lookup"><span data-stu-id="4b088-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4b088-120">Gå till sekretesssidan **för Inställningars** säkerhet i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> \> \*\* &amp; \*\*</span><span class="sxs-lookup"><span data-stu-id="4b088-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4b088-121">Gå till sekretesssidan för Sekretess för Inställningar i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> **Settings** \> **Settings** \> \*\* &amp; administratörscentret.\*\*</span><span class="sxs-lookup"><span data-stu-id="4b088-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="4b088-122">Högst upp på sidan **Organisationsinställningar** väljer du fliken **Sekretess för säkerhet &.**</span><span class="sxs-lookup"><span data-stu-id="4b088-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="4b088-123">Välj **Självbetjäningslösenordsåterställning**.</span><span class="sxs-lookup"><span data-stu-id="4b088-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="4b088-124">Under **Återställning av lösenord för självbetjäning**väljer du Gå till **Azure-portalen för att aktivera återställning av lösenord för självbetjäning**.</span><span class="sxs-lookup"><span data-stu-id="4b088-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="4b088-125">I det vänstra navigeringsfönstret väljer du **Användare**och sedan på **användarna | Välj** **Återställ lösenord**för alla användare .</span><span class="sxs-lookup"><span data-stu-id="4b088-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="4b088-126">På sidan **Egenskaper** väljer du **Alla** för att aktivera det för alla i ditt företag och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4b088-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="4b088-127">När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa sitt lösenord i framtiden.</span><span class="sxs-lookup"><span data-stu-id="4b088-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4b088-128">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4b088-128">Related articles</span></span>

[<span data-ttu-id="4b088-129">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="4b088-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="4b088-130">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="4b088-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="4b088-131">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="4b088-131">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
