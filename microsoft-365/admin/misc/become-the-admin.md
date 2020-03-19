---
title: Utföra ett internt administratörsövertagande i Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Lär dig hur du verifierar din e-postadress och domänägarskap att ta över en ohanterad klientorganisation i Office 365
ms.openlocfilehash: 0f7932b9ba727db62f81ac15b99a5f5ca276f09f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857409"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a><span data-ttu-id="5ac76-103">Utföra ett internt administratörsövertagande i Office 365</span><span class="sxs-lookup"><span data-stu-id="5ac76-103">Perform an internal admin takeover in Office 365</span></span>

 <span data-ttu-id="5ac76-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5ac76-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="5ac76-105">Om du är administratör och vill ta över en ohanterad klient som skapats av en självbetjäningsanvändare registrering, kan du göra detta med en intern administratör övertagande.</span><span class="sxs-lookup"><span data-stu-id="5ac76-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac76-106">En självbetjäningsregistrering för alla molntjänster som använder Azure AD kommer att lägga till användaren i en ohanterad eller "skugga" Azure AD-katalog och skapa en ohanterad klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="5ac76-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="5ac76-107">En ohanterad klient är en katalog utan en global administratör.</span><span class="sxs-lookup"><span data-stu-id="5ac76-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="5ac76-108">Information om huruvida en klient hanteras eller inte hanteras finns [i Bestämma klienttyp](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="5ac76-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="5ac76-109">Steg 1: Verifiera din e-postadress</span><span class="sxs-lookup"><span data-stu-id="5ac76-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="5ac76-110">Om självbetjäning är aktiverat i din klientkan användarna prenumerera på kostnadsfria tjänster, till exempel Power BI, på egen hand.</span><span class="sxs-lookup"><span data-stu-id="5ac76-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="5ac76-111">De här stegen förutsätter att en självbetjäningsanvändarprenumeration har skapat den ohanterade klientorganisation som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterade klienten med Power BI för att illustrera sökvägen för övertagande av administratörer.</span><span class="sxs-lookup"><span data-stu-id="5ac76-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="5ac76-112">Om du vill registrera dig för Power BI går du till [Power BI-webbplatsen](https://powerbi.com) och väljer **Start gratis** > **startgratis provversion** (i rutan Dela med Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="5ac76-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="5ac76-113">Registrera dig med ett användarkonto som använder organisationens `powerbiadmin@contoso.com`domännamn (t.ex. ).</span><span class="sxs-lookup"><span data-stu-id="5ac76-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="5ac76-114">Om ditt konto redan används loggar du in med ditt nuvarande lösenord.</span><span class="sxs-lookup"><span data-stu-id="5ac76-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="5ac76-115">Kontrollera din e-post för **verifieringskoden** och ange koden för att validera din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5ac76-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="5ac76-116">Steg 2: Skapa ett nytt konto</span><span class="sxs-lookup"><span data-stu-id="5ac76-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="5ac76-117">När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto.</span><span class="sxs-lookup"><span data-stu-id="5ac76-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="5ac76-118">Fyll i fälten användarnamn och lösenord med det konto som du vill använda och välj sedan **Start**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="5ac76-119">Steg 3: Verifiera domänägarskap och bli administratör</span><span class="sxs-lookup"><span data-stu-id="5ac76-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="5ac76-120">Guiden **Bli administratör** öppnas.</span><span class="sxs-lookup"><span data-stu-id="5ac76-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="5ac76-121">Om guiden inte startar letar du efter **panelen Admin** och markerar den.</span><span class="sxs-lookup"><span data-stu-id="5ac76-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="5ac76-122">Välj **Ja, jag vill vara admin**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="5ac76-123">Kontrollera att du äger den domän som du vill ta över genom att lägga till en TXT-post i domänregistratorn.</span><span class="sxs-lookup"><span data-stu-id="5ac76-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="5ac76-124">Guiden ger dig TXT-posten att lägga till, samt ger en länk till registratorns webbplats och en länk till steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="5ac76-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="5ac76-125">När du har lagt till TXT-posten på din registratorwebbplats, gå tillbaka till guiden och välj **Okej, jag har lagt till posten**.</span><span class="sxs-lookup"><span data-stu-id="5ac76-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ac76-126">Att ta över skuggklienten påverkar inte befintlig information eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="5ac76-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="5ac76-127">Om några användare i domänen har registrerat sig för tjänster som kräver en licens blir du dock ombedd att köpa licenser för dem som en del av att ta över administratörsrollen.</span><span class="sxs-lookup"><span data-stu-id="5ac76-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="5ac76-128">Du kan lägga till eller ta bort licenser när administratörsinstallationen är klar.</span><span class="sxs-lookup"><span data-stu-id="5ac76-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="5ac76-129">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5ac76-129">Related articles</span></span>

<span data-ttu-id="5ac76-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="5ac76-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="5ac76-131">Övertagande av administratörer i Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ac76-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="5ac76-132">Få hjälp med Office 365-domäner</span><span class="sxs-lookup"><span data-stu-id="5ac76-132">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.yml)

[<span data-ttu-id="5ac76-133">Använda självbetjäningsregistrering i organisationen</span><span class="sxs-lookup"><span data-stu-id="5ac76-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="5ac76-134">Förstå rollen power BI-tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="5ac76-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

