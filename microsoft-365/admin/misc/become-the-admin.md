---
title: Utföra en intern administrativ övertag Ande
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Lär dig hur du verifierar din e-post och domän ägarskap för att ta över en ohanterad klient organisation i Microsoft 365
ms.openlocfilehash: 9ae09a4b88887664a0615128bcddc48ad6f57118
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645065"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="753e5-103">Utföra en intern administrativ övertag Ande</span><span class="sxs-lookup"><span data-stu-id="753e5-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="753e5-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="753e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="753e5-105">Om du är administratör och vill ta över en ohanterad klient organisation som skapats av en självbetjänings användar registrering kan du göra det med en intern administratörs övertag Ande.</span><span class="sxs-lookup"><span data-stu-id="753e5-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="753e5-106">Ett själv underhåll för alla moln tjänster som använder Azure AD lägger till användaren i en ohanterad eller "skugg" Azure AD-katalog och skapar en ohanterad klient organisation.</span><span class="sxs-lookup"><span data-stu-id="753e5-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="753e5-107">En ohanterad klient organisation är en katalog utan global administratör.</span><span class="sxs-lookup"><span data-stu-id="753e5-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="753e5-108">För att avgöra om en klient organisation är hanterad eller ohanterad, se kontrol lera [klient organisations typ](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="753e5-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="753e5-109">Steg 1: bekräfta din e-postadress</span><span class="sxs-lookup"><span data-stu-id="753e5-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="753e5-110">Om själv service är aktiverat i din klient organisation kan användare abonnera på gratis tjänster, till exempel Power BI, på egen hand.</span><span class="sxs-lookup"><span data-stu-id="753e5-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="753e5-111">De här stegen förutsätter att en självbetjänings användar prenumeration har skapat den ohanterade klient organisation som du vill ta över som administratör. I det första steget skapar du en användar kontext i den ohanterade innehavaren med Power BI för att illustrera administratörs upptagnings vägen.</span><span class="sxs-lookup"><span data-stu-id="753e5-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="753e5-112">Registrera dig för Power BI genom att gå till [Power BI-webbplatsen](https://powerbi.com) och välja **Starta**gratis  >  **prov period** (i dela med Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="753e5-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="753e5-113">Registrera dig med ett användar konto som använder organisationens domän namn (till exempel `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="753e5-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="753e5-114">Om ditt konto redan används loggar du in med ditt nuvarande lösen ord.</span><span class="sxs-lookup"><span data-stu-id="753e5-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="753e5-115">Kontrol lera e-postmeddelandet **och ange koden för** att verifiera din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="753e5-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="753e5-116">Steg 2: skapa ett nytt konto</span><span class="sxs-lookup"><span data-stu-id="753e5-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="753e5-117">När du anger verifierings koden kommer du till en sida där du kan skapa ett nytt konto.</span><span class="sxs-lookup"><span data-stu-id="753e5-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="753e5-118">Fyll i fälten användar namn och lösen ord med det konto som du vill använda och välj sedan **Starta**.</span><span class="sxs-lookup"><span data-stu-id="753e5-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="753e5-119">Steg 3: bekräfta domän ägandet och bli administratör</span><span class="sxs-lookup"><span data-stu-id="753e5-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="753e5-120">Då öppnas **Administratörs** guiden.</span><span class="sxs-lookup"><span data-stu-id="753e5-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="753e5-121">Om guiden inte startar letar du reda på panelen **Administratörer** och väljer den.</span><span class="sxs-lookup"><span data-stu-id="753e5-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="753e5-122">Välj **Ja, jag vill vara administratör**.</span><span class="sxs-lookup"><span data-stu-id="753e5-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="753e5-123">Verifiera att du äger den domän som du vill ta med genom att lägga till en TXT-post i domän registratorn.</span><span class="sxs-lookup"><span data-stu-id="753e5-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="753e5-124">Guiden ger dig TXT-posten att lägga till samt en länk till registratorns webbplats samt en länk till steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="753e5-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="753e5-125">När du har lagt till TXT-posten på din registrators webbplats går du tillbaka till guiden och väljer **OK, jag har lagt till posten**.</span><span class="sxs-lookup"><span data-stu-id="753e5-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="753e5-126">Att ta över skugg klient organisationen påverkar inte befintliga uppgifter eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="753e5-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="753e5-127">Om en användare i domänen har registrerat sig för tjänster som kräver en licens uppmanas du att köpa licenser för dem som en del av att ta över administratörs rollen.</span><span class="sxs-lookup"><span data-stu-id="753e5-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="753e5-128">Du kan köpa eller ta bort licenser när administratörs konfigurationen är klar.</span><span class="sxs-lookup"><span data-stu-id="753e5-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="753e5-129">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="753e5-129">Related articles</span></span>

<span data-ttu-id="753e5-130">YouTube: [3 steg för att utföra en IT-administratörs övertag Ande för Power BI och Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="753e5-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="753e5-131">Administratörs övertag Ande i Azure AD</span><span class="sxs-lookup"><span data-stu-id="753e5-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="753e5-132">Använda automatisk registrering i din organisation</span><span class="sxs-lookup"><span data-stu-id="753e5-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="753e5-133">Förstå administratörs rollen för Power BI-tjänsten</span><span class="sxs-lookup"><span data-stu-id="753e5-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

