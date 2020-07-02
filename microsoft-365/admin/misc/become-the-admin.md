---
title: Utför ett internt administrationsövertagande
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Läs om hur du verifierar din e-post och domänägarskap för att ta över en ohanterat klientorganisation i Microsoft 365
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022163"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="5bbc4-103">Utför ett internt administrationsövertagande</span><span class="sxs-lookup"><span data-stu-id="5bbc4-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="5bbc4-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="5bbc4-105">Om du är administratör och vill ta över en ohanterat klient som skapats av en självbetjäningsanvändaranst registrering kan du göra detta med ett internt administrationsövertagande.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="5bbc4-106">En självbetjäningslogga för alla molntjänster som använder Azure AD lägger till användaren i en ohanterad eller "skugga" Azure AD-katalog och skapar en ohanterad klient.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="5bbc4-107">En ohantend klient är en katalog utan global administratör.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="5bbc4-108">Information om huruvida en klient hanteras eller inte hanteras finns i [Bestämma klienttyp](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="5bbc4-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="5bbc4-109">Steg 1: Verifiera din e-postadress</span><span class="sxs-lookup"><span data-stu-id="5bbc4-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="5bbc4-110">Om självbetjäning är aktiverat i din klientorganisation kan användare prenumerera på kostnadsfria tjänster, till exempel Power BI, på egen hand.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="5bbc4-111">De här stegen förutsätter att en självbetjäningsanvändarprenumeration har skapat den ohanterat klient som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterat klienten med Power BI för att illustrera sökvägen till admin-uppköp.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="5bbc4-112">Om du vill registrera dig för Power BI går du till [Power BI-webbplatsen](https://powerbi.com) och väljer **Startfri**  >  **startfri provperiod** (i rutan Dela med Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="5bbc4-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="5bbc4-113">Registrera dig med ett användarkonto som använder domännamnet för din organisation (till exempel `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="5bbc4-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="5bbc4-114">Om ditt konto redan används loggar du in med ditt nuvarande lösenord.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="5bbc4-115">Kontrollera din e-post för **verifieringskoden** och ange koden för att validera din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="5bbc4-116">Steg 2: Skapa ett nytt konto</span><span class="sxs-lookup"><span data-stu-id="5bbc4-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="5bbc4-117">När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="5bbc4-118">Fyll i användarnamn och lösenord med det konto som du vill använda och välj sedan **Start**.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="5bbc4-119">Steg 3: Verifiera domänägarskap och bli administratör</span><span class="sxs-lookup"><span data-stu-id="5bbc4-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="5bbc4-120">Guiden **Bli administratör öppnas.**</span><span class="sxs-lookup"><span data-stu-id="5bbc4-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="5bbc4-121">Om guiden inte startar letar du efter panelen **Admin** och väljer den.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="5bbc4-122">Välj **Ja, jag vill vara administratör**.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="5bbc4-123">Kontrollera att du äger den domän som du vill ta över genom att lägga till en TXT-post i domänregistraren.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="5bbc4-124">Guiden ger dig TXT-posten att lägga till, samt ger en länk till din registrators webbplats och en länk till steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="5bbc4-125">När du har lagt till TXT-posten på din registratorswebbplats går du tillbaka till guiden och väljer **Okej, jag har lagt till posten**.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5bbc4-126">Om du tar över skuggklienten påverkas ingen befintlig information eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="5bbc4-127">Om några användare i domänen har registrerat sig för tjänster som kräver en licens blir du ombedd att köpa licenser för dem som en del av att ta över administratörsrollen.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="5bbc4-128">Du kan köpa eller ta bort licenser när administratörsinstallationen är klar.</span><span class="sxs-lookup"><span data-stu-id="5bbc4-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5bbc4-129">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5bbc4-129">Related articles</span></span>

<span data-ttu-id="5bbc4-130">YouTube: [3 steg för att göra en IT-administratör Takeover för Power BI och Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="5bbc4-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="5bbc4-131">Admin övertagande i Azure AD</span><span class="sxs-lookup"><span data-stu-id="5bbc4-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="5bbc4-132">Få hjälp med domäner</span><span class="sxs-lookup"><span data-stu-id="5bbc4-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="5bbc4-133">Använda självbetjäningsanmäla i din organisation</span><span class="sxs-lookup"><span data-stu-id="5bbc4-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="5bbc4-134">Förstå rollen power bi-tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="5bbc4-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

