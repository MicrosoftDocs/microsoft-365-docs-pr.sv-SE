---
title: Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell
f1.keywords:
- NOCSH
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
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Lär dig hur du dirigerar trafik till en befintlig offentlig webbplats som inte finns hos Microsoft, om du har ställt in Microsoft på att hantera DNS-poster för din egen domän.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572147"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="d2ca5-103">Uppdatera DNS-poster för att behålla din webbplats hos ditt nuvarande webbhotell</span><span class="sxs-lookup"><span data-stu-id="d2ca5-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="d2ca5-104">**Om du hanterar domänens Microsoft-poster hos din DNS-värd** behöver du inte bry dig om stegen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="d2ca5-105">Din webbplats finns kvar på samma plats och användarna kan fortfarande komma åt den.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="d2ca5-106">**Om Microsoft hanterar dina DNS-poster gör** du följande för att dirigera trafik till en befintlig offentlig webbplats som finns utanför Microsoft, gör du följande när du har lagt till din domän i Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d2ca5-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d2ca5-107">Uppdatera DNS-poster Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d2ca5-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="d2ca5-108">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="d2ca5-109">På sidan **Domains** väljer du domänen och sedan **DNS Records.**</span><span class="sxs-lookup"><span data-stu-id="d2ca5-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="d2ca5-110">Välj **+ Add record** och ange följande:</span><span class="sxs-lookup"><span data-stu-id="d2ca5-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="d2ca5-111">Ange **följande** för typ: **A (Adress)**</span><span class="sxs-lookup"><span data-stu-id="d2ca5-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="d2ca5-112">I **Värdnamn eller alias** skriver du in **@**</span><span class="sxs-lookup"><span data-stu-id="d2ca5-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="d2ca5-113">I **IP-adress** skriver du in den statiska IP-adress där webbplatsen finns för närvarande (till exempel 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="d2ca5-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="d2ca5-p102">Det måste vara en  *statisk*  IP-adress för webbplatsen, inte en  *dynamisk*  IP-adress.Kontrollera med webbplatsen som är värd för din webbplats för att se till att du kan få en statisk IP-adress till din offentliga webbplats.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="d2ca5-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-116">Select **Save**.</span></span> 
    
<span data-ttu-id="d2ca5-117">Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="d2ca5-118">Välj **+ Add record** och ange följande:</span><span class="sxs-lookup"><span data-stu-id="d2ca5-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="d2ca5-119">Ange **följande** för typ: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="d2ca5-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="d2ca5-120">I **Värdnamn eller alias** skriver du in **www**</span><span class="sxs-lookup"><span data-stu-id="d2ca5-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="d2ca5-121">I **Pekar på adress** skriver du in det fullständiga domännamnet (FQDN) för webbplatsen (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d2ca5-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="d2ca5-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-122">Select **Save**.</span></span> 
    
<span data-ttu-id="d2ca5-123">Gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d2ca5-123">Finally, do the following:</span></span>
  
<span data-ttu-id="d2ca5-124">[Uppdatera domänens NS-poster så](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) att de pekar på Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="d2ca5-125">När NS-posterna har uppdaterats så att de pekar på Microsoft är din domän konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="d2ca5-126">E-post kommer att dirigeras till Microsoft och trafiken till din webbplatsadress kommer fortsätta att gå till din nuvarande webbplatsvärd.</span><span class="sxs-lookup"><span data-stu-id="d2ca5-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
