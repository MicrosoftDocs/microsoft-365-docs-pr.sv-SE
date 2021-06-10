---
title: Utföra ett internt administratörsupptagande
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
description: Lär dig hur du verifierar din e-post och domänägarskap för att ta över en ohanterad klientorganisation som skapats av en självbetjänad användarregistrering i Microsoft 365.
ms.openlocfilehash: aa44023ffdc2b59e4db024706323c5b872566260
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635992"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="12404-103">Utföra ett internt administratörsupptagande</span><span class="sxs-lookup"><span data-stu-id="12404-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="12404-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="12404-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="12404-105">Om du är administratör och vill ta över en ohanterad klientorganisation som skapas genom registrering av självbetjäning kan du göra detta med ett internt administratörsköp.</span><span class="sxs-lookup"><span data-stu-id="12404-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="12404-106">Om du registrerar dig som självbetjäning för en molntjänst som använder Azure AD kommer användaren att läggas till i en ohanterad eller "skuggig" Azure AD-katalog och en ohanterad klientorganisation skapas.</span><span class="sxs-lookup"><span data-stu-id="12404-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="12404-107">En ohanterad klientorganisation är en katalog utan global administratör.</span><span class="sxs-lookup"><span data-stu-id="12404-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="12404-108">Information om huruvida en klientorganisation hanteras eller hanteras utan avbrott finns i [Fastställa klientorganisationstyp.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="12404-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="12404-109">Steg 1: Verifiera din e-postadress</span><span class="sxs-lookup"><span data-stu-id="12404-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="12404-110">Om självbetjäning är aktiverad i klientorganisationen kan användare prenumerera på kostnadsfria tjänster som Power BI, på egen hand.</span><span class="sxs-lookup"><span data-stu-id="12404-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="12404-111">De här stegen förutsätter att en användarprenumeration med självbetjäning har skapat den ohanterade klientorganisationen som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterade klientorganisationen, med hjälp Power BI för att illustrera administrationsvägen för övergången.</span><span class="sxs-lookup"><span data-stu-id="12404-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="12404-112">Om du vill registrera Power BI kostnadsfri utvärderingsversion går du till [webbplatsen Power BI](https://powerbi.com) och väljer Starta kostnadsfri utvärderingsversion  >   (i rutan Dela Power BI Pro start).</span><span class="sxs-lookup"><span data-stu-id="12404-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="12404-113">Registrera dig med ett användarkonto som använder domännamnet för din organisation (t.ex. `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="12404-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="12404-114">Om ditt konto redan används loggar du in med ditt nuvarande lösenord.</span><span class="sxs-lookup"><span data-stu-id="12404-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="12404-115">Kontrollera din e-postadress **för verifieringskoden** och ange koden för att verifiera din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="12404-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="12404-116">Steg 2: Skapa ett nytt konto</span><span class="sxs-lookup"><span data-stu-id="12404-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="12404-117">När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto.</span><span class="sxs-lookup"><span data-stu-id="12404-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="12404-118">Fyll i användarnamns- och lösenordsfälten med det konto som du vill använda och välj sedan **Starta.**</span><span class="sxs-lookup"><span data-stu-id="12404-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="12404-119">Steg 3: Verifiera att du äger domänen och bli administratör</span><span class="sxs-lookup"><span data-stu-id="12404-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="12404-120">Guiden **Bli administratör** öppnas.</span><span class="sxs-lookup"><span data-stu-id="12404-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="12404-121">Om guiden inte startar letar du upp panelen **Admin** och väljer den.</span><span class="sxs-lookup"><span data-stu-id="12404-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="12404-122">Välj **Ja, jag vill vara administratör.**</span><span class="sxs-lookup"><span data-stu-id="12404-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="12404-123">Verifiera att du äger den domän du vill ta över genom att lägga till en TXT-post i din domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="12404-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="12404-124">Guiden ger dig TXT-posten att lägga till, samt en länk till din registrators webbplats samt en länk till stegvisa instruktioner.</span><span class="sxs-lookup"><span data-stu-id="12404-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="12404-125">När du har lagt till TXT-posten på registratorns webbplats går du tillbaka till guiden och väljer **Okej, jag har lagt till posten**.</span><span class="sxs-lookup"><span data-stu-id="12404-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="12404-126">Att ta över skuggklientorganisationen påverkar inte befintlig information eller befintliga tjänster.</span><span class="sxs-lookup"><span data-stu-id="12404-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="12404-127">Men om några användare i domänen har registrerat sig för tjänster som kräver en licens uppmanas du att köpa licenser till dem när du tar över administratörsrollen.</span><span class="sxs-lookup"><span data-stu-id="12404-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="12404-128">Du kan köpa eller ta bort licenser när administratörsinstallationen är klar.</span><span class="sxs-lookup"><span data-stu-id="12404-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="12404-129">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="12404-129">Related content</span></span>

<span data-ttu-id="12404-130">YouTube: [3 steg för att göra ett ÖVERtagande av IT-administratörer Power BI och Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span><span class="sxs-lookup"><span data-stu-id="12404-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>\
<span data-ttu-id="12404-131">[Administratörsupptagande i Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artikel)</span><span class="sxs-lookup"><span data-stu-id="12404-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="12404-132">[Med självbetjäning registrerar du dig i din organisation](self-service-sign-up.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="12404-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="12404-133">[Förstå tjänstadministratörsrollen Power BI](/power-bi/service-admin-role) (artikel)</span><span class="sxs-lookup"><span data-stu-id="12404-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>