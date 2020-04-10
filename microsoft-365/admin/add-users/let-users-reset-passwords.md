---
title: Låt användare återställa sina egna lösenord i Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Läs om hur du kan återställa dina lösenord med hjälp av verktyget för återställning av lösenord med självbetjäning.
ms.openlocfilehash: 666d3843f7917cf9bd5718c0ce29f87f93d6effe
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211901"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="81f28-103">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="81f28-103">Let users reset their own passwords</span></span>

<span data-ttu-id="81f28-104">Står folk i kö och ber dig återställa deras lösenord?</span><span class="sxs-lookup"><span data-stu-id="81f28-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="81f28-105">Som Microsoft 365-administratör kan du låta användarna använda [självbetjäningsverktyget](https://go.microsoft.com/fwlink/p/?LinkId=522677) för återställning av lösenord så att du inte behöver återställa lösenord för dem.</span><span class="sxs-lookup"><span data-stu-id="81f28-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="81f28-106">Det innebär mindre jobb för dig!</span><span class="sxs-lookup"><span data-stu-id="81f28-106">Less work for you!</span></span> 
  
<span data-ttu-id="81f28-107">Här är några saker du kan behöva veta:</span><span class="sxs-lookup"><span data-stu-id="81f28-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="81f28-p102">Självbetjäning för återställning av lösenord för molnanvändare ingår **kostnadsfritt** i alla betalabonnemang för Office 365 Business, Education eller Office 365 för ideella föreningar. Det fungerar inte med utvärderingsversioner av Office 365.</span><span class="sxs-lookup"><span data-stu-id="81f28-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="81f28-p103">Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.</span><span class="sxs-lookup"><span data-stu-id="81f28-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="81f28-p104">**Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="81f28-p104">**If you're using an on-premises Active Directory**, the above two points don't apply. Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="81f28-115">Titta på en kort video om att låta användare återställa sina egna lösenord.</span><span class="sxs-lookup"><span data-stu-id="81f28-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="81f28-116">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="81f28-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="81f28-117">Låt andra återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="81f28-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="81f28-118">Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81f28-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="81f28-119">Gå till sekretesssidan Inställningar <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">säkerhet & i</a> **administrationscentret.** \></span><span class="sxs-lookup"><span data-stu-id="81f28-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="81f28-120">Gå till sekretesssidan för **Inställningars &amp; säkerhet** i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Settings** \></span><span class="sxs-lookup"><span data-stu-id="81f28-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="81f28-121">Gå till sekretesssidan för **Inställningars &amp; säkerhet** i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Settings** \></span><span class="sxs-lookup"><span data-stu-id="81f28-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="81f28-122">Under Låt dina personer återställa sina egna lösenord väljer du länken för **Azure AD-administrationscentret**. **Let your people reset their own passwords**</span><span class="sxs-lookup"><span data-stu-id="81f28-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="81f28-123">Du får Azure kostnadsfritt!</span><span class="sxs-lookup"><span data-stu-id="81f28-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="81f28-124">Välj **Användare** i den vänstra navigeringen och välj sedan **Återställning av lösenord**.</span><span class="sxs-lookup"><span data-stu-id="81f28-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="81f28-125">På sidan Egenskaper väljer du **Alla** för att aktivera det för alla i ditt företag och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="81f28-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="81f28-126">När användarna loggar in på Office 365 uppmanas de ange ytterligare kontaktinformation så att de kan få hjälp med att återställa lösenordet i framtiden.</span><span class="sxs-lookup"><span data-stu-id="81f28-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="81f28-127">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="81f28-127">Related articles</span></span>

[<span data-ttu-id="81f28-128">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="81f28-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="81f28-129">Ange att en enskild användares lösenord aldrig ska förfalla</span><span class="sxs-lookup"><span data-stu-id="81f28-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="81f28-130">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="81f28-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
