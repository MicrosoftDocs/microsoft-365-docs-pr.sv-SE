---
title: Stöd för NAT med Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: I den här artikeln finns information om hur man uppskattar antalet klienter som du kan använda per IP-adress i din organisation via NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694314"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="c7f31-103">Stöd för NAT med Office 365</span><span class="sxs-lookup"><span data-stu-id="c7f31-103">NAT support with Office 365</span></span>

<span data-ttu-id="c7f31-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c7f31-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c7f31-105">Tidigare föreslog vägledning att det högsta antalet Exchange-klienter du bör använda per IP-adress för att ansluta till Office 365 skulle ha 2 000-klienter per nätverks port.</span><span class="sxs-lookup"><span data-stu-id="c7f31-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="c7f31-106">Varför ska jag använda NAT?</span><span class="sxs-lookup"><span data-stu-id="c7f31-106">Why use NAT?</span></span>

<span data-ttu-id="c7f31-107">Genom att använda NAT kan tusentals personer i ett företags nätverk "dela" några få offentligt routade IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7f31-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="c7f31-108">I de flesta företags nätverk används privata IP-adressutrymmet (RFC1918).</span><span class="sxs-lookup"><span data-stu-id="c7f31-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="c7f31-109">Det privata adress utrymmet tilldelas av Internet Assigned Numbers Authority (IANA) och är endast avsett för nätverk som inte dirigerar direkt till och från det globala Internet.</span><span class="sxs-lookup"><span data-stu-id="c7f31-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="c7f31-110">För att ge Internet åtkomst till enheter i ett privat IP-adressutrymme använder organisationer Gateway-teknologin, till exempel brand väggar och proxyservrar som tillhandahåller NAT-eller port Address Translation-tjänster (PAT).</span><span class="sxs-lookup"><span data-stu-id="c7f31-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="c7f31-111">Dessa gateways gör att trafik från interna enheter till Internet (inklusive Office 365) kommer från en eller flera offentligt routade IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7f31-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="c7f31-112">Varje utgående anslutning från en intern enhet översätts till en annan TCP-port på den offentliga IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="c7f31-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="c7f31-113">Varför måste du ha så många anslutningar att de är öppna för Office 365 samtidigt?</span><span class="sxs-lookup"><span data-stu-id="c7f31-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="c7f31-114">Outlook kan öppna åtta eller fler anslutningar (när det finns tillägg, delade kalendrar, post lådor och andra funktioner).</span><span class="sxs-lookup"><span data-stu-id="c7f31-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="c7f31-115">Eftersom det finns högst 64 000 portar tillgängliga på en Windows-baserad NAT-enhet kan det högsta antalet 8 000-användare bakom en IP-adress innan portarna uttömts.</span><span class="sxs-lookup"><span data-stu-id="c7f31-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="c7f31-116">Observera att om kunder använder datorer som inte är Windows OS-baserade kan de totala tillgängliga portarna vara beroende av vilken NAT-enhet eller program vara som används.</span><span class="sxs-lookup"><span data-stu-id="c7f31-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="c7f31-117">I det här scenariot kan det högsta antalet portar vara mindre än 64 000.</span><span class="sxs-lookup"><span data-stu-id="c7f31-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="c7f31-118">Tillgängligheten för portar påverkas också av andra faktorer som Windows begränsar 4 000-portar för eget bruk, vilket minskar det totala antalet tillgängliga portar för 60 000.</span><span class="sxs-lookup"><span data-stu-id="c7f31-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="c7f31-119">Det kan finnas andra program, till exempel Internet Explorer, som kan ansluta samtidigt och kräva ytterligare portar.</span><span class="sxs-lookup"><span data-stu-id="c7f31-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="c7f31-120">Beräkna högsta enheter som stöds bakom en enda offentlig IP-adress med Office 365</span><span class="sxs-lookup"><span data-stu-id="c7f31-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="c7f31-121">För att fastställa det högsta antalet enheter bakom en enda offentlig IP-adress bör du övervaka nätverks trafik för att fastställa högsta port förbrukning per klient.</span><span class="sxs-lookup"><span data-stu-id="c7f31-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="c7f31-122">Dessutom bör en topp faktor användas för port användning (minst 4).</span><span class="sxs-lookup"><span data-stu-id="c7f31-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="c7f31-123">**Använd följande formel för att beräkna antalet enheter som stöds per IP-adress:**</span><span class="sxs-lookup"><span data-stu-id="c7f31-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="c7f31-124">Högsta enheter som stöds bakom en enda offentlig IP-adress = (64 000-begränsade portar)/(högsta port förbrukning + högsta faktor)</span><span class="sxs-lookup"><span data-stu-id="c7f31-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="c7f31-125">**Om till exempel följande var sant:**</span><span class="sxs-lookup"><span data-stu-id="c7f31-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="c7f31-126">**Begränsade portar:** 4 000 för operativ systemet</span><span class="sxs-lookup"><span data-stu-id="c7f31-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="c7f31-127">**Högsta port förbrukning:** 6 per enhet</span><span class="sxs-lookup"><span data-stu-id="c7f31-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="c7f31-128">**Högsta faktor:** 4</span><span class="sxs-lookup"><span data-stu-id="c7f31-128">**Peak factor:** 4</span></span>

<span data-ttu-id="c7f31-129">Sedan kan de högsta enheter som stöds bakom en enda offentlig IP-adress = (64 000-4000)/(6 + 4) = 6 000</span><span class="sxs-lookup"><span data-stu-id="c7f31-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="c7f31-130">Med utgivningen av Office 365-värd paketet, som ingår i uppdateringarna från september 2011 för Microsoft Office Outlook 2007 eller november 2011 för Microsoft Outlook 2010 eller senare uppdatering, kan antalet anslutningar från Outlook (både Office Outlook 2007 med Service Pack 2 och Outlook 2010) till Exchange vara så lite som 2.</span><span class="sxs-lookup"><span data-stu-id="c7f31-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="c7f31-131">Du måste vara en faktor i de olika operativ systemen, användar funktioner och så vidare för att fastställa det lägsta och högsta antal portar som nätverket kräver vid hög belastning.</span><span class="sxs-lookup"><span data-stu-id="c7f31-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="c7f31-132">Om du vill ha stöd för fler enheter bakom en enda offentlig IP-adress följer du stegen som beskrivs för att utvärdera det maximala antalet enheter som stöds:</span><span class="sxs-lookup"><span data-stu-id="c7f31-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="c7f31-133">Övervaka nätverks trafik för att fastställa högsta port förbrukning per klient.</span><span class="sxs-lookup"><span data-stu-id="c7f31-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="c7f31-134">Du bör samla in dessa data:</span><span class="sxs-lookup"><span data-stu-id="c7f31-134">You should collect this data:</span></span>
  
- <span data-ttu-id="c7f31-135">Från flera platser</span><span class="sxs-lookup"><span data-stu-id="c7f31-135">From multiple locations</span></span>
    
- <span data-ttu-id="c7f31-136">Från flera enheter</span><span class="sxs-lookup"><span data-stu-id="c7f31-136">From multiple devices</span></span>
    
- <span data-ttu-id="c7f31-137">Flera gånger</span><span class="sxs-lookup"><span data-stu-id="c7f31-137">At multiple times</span></span>
    
<span data-ttu-id="c7f31-138">Använd den föregående formeln för att beräkna maximalt antal användare per IP-adress som kan användas i miljön.</span><span class="sxs-lookup"><span data-stu-id="c7f31-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="c7f31-139">Det finns olika metoder för att distribuera klient belastning mellan ytterligare offentliga IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7f31-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="c7f31-140">Vilka strategier som är tillgängliga beror på funktionerna i Corporate Gateway-lösningen.</span><span class="sxs-lookup"><span data-stu-id="c7f31-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="c7f31-141">Den enklaste lösningen är att segmentera ditt användar adress utrymme och statiskt "tilldela" ett antal IP-adresser till varje gateway.</span><span class="sxs-lookup"><span data-stu-id="c7f31-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="c7f31-142">Ett annat alternativ till att många gateway-enheter kan använda en adresspool för IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7f31-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="c7f31-143">Fördelen med adresspoolen är att det är mycket mer dynamiskt och mindre troligt att det krävs justering när användar basen växer.</span><span class="sxs-lookup"><span data-stu-id="c7f31-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7f31-144">Se även</span><span class="sxs-lookup"><span data-stu-id="c7f31-144">See also</span></span>

[<span data-ttu-id="c7f31-145">Hantera slut punkter för Office 365</span><span class="sxs-lookup"><span data-stu-id="c7f31-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="c7f31-146">Vanliga frågor om Office 365-slut punkter</span><span class="sxs-lookup"><span data-stu-id="c7f31-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
