---
title: Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som ligger utanför Microsoft, om du har konfigurerat Microsoft för att hantera DNS-poster för din egen domän.
ms.openlocfilehash: 9a7090eef3ce7d1c67839e7320f31d7bd32aa6a7
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814404"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="62d4e-103">Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell</span><span class="sxs-lookup"><span data-stu-id="62d4e-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="62d4e-104">**Om du hanterar din domäns Microsoft-poster hos din DNS-värd**behöver du inte oroa dig för stegen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="62d4e-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="62d4e-105">Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den.</span><span class="sxs-lookup"><span data-stu-id="62d4e-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="62d4e-106">**Om Microsoft hanterar dina DNS-poster**och dirigerar trafik till en befintlig offentlig webbplats som finns utanför Microsoft, efter att du har lagt till din domän i Microsoft, gör du följande:</span><span class="sxs-lookup"><span data-stu-id="62d4e-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="62d4e-107">Uppdatera DNS-poster i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62d4e-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="62d4e-108">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="62d4e-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="62d4e-109">På sidan **domäner** väljer du domänen och sedan **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="62d4e-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="62d4e-110">Under **DNS-inställningar**väljer du **anpassade poster**.</span><span class="sxs-lookup"><span data-stu-id="62d4e-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="62d4e-111">Välj **+ Ny anpassad post** och ange följande:</span><span class="sxs-lookup"><span data-stu-id="62d4e-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="62d4e-112">Ange följande för **DNS-typ**: **A (adress)**</span><span class="sxs-lookup"><span data-stu-id="62d4e-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="62d4e-113">I **Värdnamn eller alias** skriver du in **@**</span><span class="sxs-lookup"><span data-stu-id="62d4e-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="62d4e-114">I **IP-adress** skriver du in den statiska IP-adress där webbplatsen finns för närvarande (till exempel 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="62d4e-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="62d4e-p102">Det måste vara en  *statisk*  IP-adress för webbplatsen, inte en  *dynamisk*  IP-adress.Kontrollera med webbplatsen som är värd för din webbplats för att se till att du kan få en statisk IP-adress till din offentliga webbplats.</span><span class="sxs-lookup"><span data-stu-id="62d4e-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="62d4e-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d4e-117">Select **Save**.</span></span> 
    
<span data-ttu-id="62d4e-118">Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="62d4e-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="62d4e-119">Välj **+ Ny anpassad post** och ange följande:</span><span class="sxs-lookup"><span data-stu-id="62d4e-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="62d4e-120">Ange följande för **DNS-typ**: **CNAME (alias)**</span><span class="sxs-lookup"><span data-stu-id="62d4e-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="62d4e-121">I **Värdnamn eller alias** skriver du in **www**</span><span class="sxs-lookup"><span data-stu-id="62d4e-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="62d4e-122">I **Pekar på adress** skriver du in det fullständiga domännamnet (FQDN) för webbplatsen (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="62d4e-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="62d4e-123">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62d4e-123">Select **Save**.</span></span> 
    
<span data-ttu-id="62d4e-124">Gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="62d4e-124">Finally, do the following:</span></span>
  
<span data-ttu-id="62d4e-125">[Uppdatera domänens NS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) så att de pekar på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62d4e-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="62d4e-126">När NS-posterna har uppdaterats så att de pekar på Microsoft är din domän konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="62d4e-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="62d4e-127">E-postmeddelandet dirigeras till Microsoft och trafik till din webb adress fortsätter att gå till din aktuella webbplats värd.</span><span class="sxs-lookup"><span data-stu-id="62d4e-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
