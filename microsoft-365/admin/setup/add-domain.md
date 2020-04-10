---
title: Lägga till en domän i Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Lägg till din domän i Office 365 i Microsoft 365-administrationscentret genom att lägga till en DNS-post hos din DNS-värd. Installationsguiden går igenom processen.
ms.openlocfilehash: 746163b83190a73326ad589b8e3bc9377ddaa9b4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209646"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="e5121-104">Lägga till en domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="e5121-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="e5121-105">**[Läs frågor och svar om domäner](domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="e5121-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="e5121-106">*Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller en [företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*</span><span class="sxs-lookup"><span data-stu-id="e5121-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="e5121-107">Följ dessa steg för att lägga till, konfigurera eller fortsätta konfigurera en domän.</span><span class="sxs-lookup"><span data-stu-id="e5121-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e5121-108">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e5121-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="e5121-109">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="e5121-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e5121-110">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="e5121-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e5121-111">Gå till sidan > **Installationsdomäner.** **Setup**</span><span class="sxs-lookup"><span data-stu-id="e5121-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="e5121-112">Välj **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="e5121-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="e5121-113">Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e5121-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="e5121-114">Välj hur du vill verifiera att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e5121-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="e5121-115">Om din domän är registrerad på&amp;GoDaddy eller 1 1 väljer du **Logga in** > **nästa** så [konfigurerar](../get-help-with-domains/domain-connect.md)Office 365 dina poster automatiskt .</span><span class="sxs-lookup"><span data-stu-id="e5121-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="e5121-116">Du kan välja att ett e-postmeddelande ska skickas till den registrerade kontakten för domänen med en verifieringskod.</span><span class="sxs-lookup"><span data-stu-id="e5121-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="e5121-117">Om du inte känner igen eller har tillgång till e-postmeddelandet kan du använda det tredje alternativet.</span><span class="sxs-lookup"><span data-stu-id="e5121-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="e5121-118">Du kan använda en TXT-post för att verifiera din domän.</span><span class="sxs-lookup"><span data-stu-id="e5121-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="e5121-119">Välj det här och välj **Nästa** om du vill se instruktioner för hur du lägger till den här DNS-posten på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="e5121-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="e5121-120">Det kan ta upp till 30 minuter att verifiera när du har lagt till posten.</span><span class="sxs-lookup"><span data-stu-id="e5121-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="e5121-121">Välj hur du vill göra de DNS-ändringar som krävs för att Office ska kunna använda domänen.</span><span class="sxs-lookup"><span data-stu-id="e5121-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="e5121-122">Välj **Lägg till DNS-posterna åt mig** om du vill att Dns ska konfigureras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e5121-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="e5121-123">Välj **Jag lägger till DNS-posterna själv** om du bara vill koppla specifika Office 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och göra detta senare.</span><span class="sxs-lookup"><span data-stu-id="e5121-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="e5121-124">**Välj det här alternativet om du vet exakt vad du gör.**</span><span class="sxs-lookup"><span data-stu-id="e5121-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="e5121-125">Om du själv väljer att lägga till *DNS-poster* väljer du **Nästa** och du ser en sida med alla poster som du behöver lägga till på registrarernas webbplats för att konfigurera domänen.</span><span class="sxs-lookup"><span data-stu-id="e5121-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="e5121-126">Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="e5121-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="e5121-127">Kontrollera listan med [värdspecifika instruktioner](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver.</span><span class="sxs-lookup"><span data-stu-id="e5121-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="e5121-128">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="e5121-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="e5121-129">Om du vill vänta till senare bläddrar du längst ned och väljer **Hoppa över det här steget**.</span><span class="sxs-lookup"><span data-stu-id="e5121-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="e5121-130">Välj **Slutför** - du är klar!</span><span class="sxs-lookup"><span data-stu-id="e5121-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="e5121-131">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="e5121-131">Related articles</span></span>

[<span data-ttu-id="e5121-132">Vanliga frågor och svar om domäner</span><span class="sxs-lookup"><span data-stu-id="e5121-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="e5121-133">Vad är en domän?</span><span class="sxs-lookup"><span data-stu-id="e5121-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="e5121-134">Köpa ett domännamn i Office 365</span><span class="sxs-lookup"><span data-stu-id="e5121-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="e5121-135">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="e5121-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="e5121-136">Få hjälp med Office 365-domäner</span><span class="sxs-lookup"><span data-stu-id="e5121-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
