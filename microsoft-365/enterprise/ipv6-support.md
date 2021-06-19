---
title: IPv6-stöd i Office 365-tjänster
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Sammanfattning: Beskriver stöd för IPv6 i Microsoft Office 365-komponenter och i Office 365-myndighetserbjudanden.'
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028913"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="41dc1-103">IPv6-stöd i Office 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="41dc1-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="41dc1-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="41dc1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="41dc1-105">Office 365 stöder både IPv6 och IPv4. Men alla Office 365-funktioner är inte helt aktiverade med IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="41dc1-106">Det innebär att du måste använda både IPv4 och IPv6 för att ansluta till Office 365.</span><span class="sxs-lookup"><span data-stu-id="41dc1-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="41dc1-107">Om du filtrerar din utgående trafik till Office 365 finns den fullständiga listan med IPv6-adresser som stöds av Office 365 i artikeln [Office 365 URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="41dc1-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="41dc1-108">När nätverket är konfigurerat och lämpliga IPv6-adresser är tillåtna kan du ladda ned [Office 365 IPv6-testplanen](https://go.microsoft.com/fwlink/?LinkId=293447) från Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="41dc1-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="41dc1-109">IPv6-stöd i Office 365-prenumerationstjänsten</span><span class="sxs-lookup"><span data-stu-id="41dc1-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="41dc1-110">Exchange Online och IPv6</span><span class="sxs-lookup"><span data-stu-id="41dc1-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="41dc1-111">Om programmet som du använder för att ansluta till Exchange Online stöder IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk.</span><span class="sxs-lookup"><span data-stu-id="41dc1-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="41dc1-112">Om du vill kontrollera kommunikationen till Exchange Online använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="41dc1-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="41dc1-113">SharePoint Online och IPv6</span><span class="sxs-lookup"><span data-stu-id="41dc1-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="41dc1-114">**Office 365 Government G1/G3/G4/K1** Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 försöker det använda IPv6 som standard.</span><span class="sxs-lookup"><span data-stu-id="41dc1-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="41dc1-115">**Offentligt moln för flera klientorganisationen** Microsoft aktiverar IPv6 för SharePoint Online på din begäran.</span><span class="sxs-lookup"><span data-stu-id="41dc1-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="41dc1-116">Du måste ange DE CIDR-noterade IP-adresserna för organisationens DNS-infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="41dc1-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="41dc1-117">Kom ihåg att den här DNS-infrastrukturen inte kan delas av andra organisationer för att IPv6 ska vara aktiverat för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="41dc1-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="41dc1-118">Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 används IPv6 som standard när IPv6 är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="41dc1-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="41dc1-119">Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk.</span><span class="sxs-lookup"><span data-stu-id="41dc1-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="41dc1-120">Om du vill kontrollera kommunikationen till SharePoint Online använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="41dc1-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="41dc1-121">Skype för företag och IPv6</span><span class="sxs-lookup"><span data-stu-id="41dc1-121">Skype for Business and IPv6</span></span>

<span data-ttu-id="41dc1-122">Tänk på att IPv6 inte stöds i Skype för företag och att det inte längre går att aktivera.</span><span class="sxs-lookup"><span data-stu-id="41dc1-122">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="41dc1-123">Microsoft Teams och IPV6</span><span class="sxs-lookup"><span data-stu-id="41dc1-123">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="41dc1-124">Microsoft Teams direktdirigering stöder endast IPv4.</span><span class="sxs-lookup"><span data-stu-id="41dc1-124">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="41dc1-125">Microsoft Teams-tjänsten och -klienten har stöd för både IPv4 och IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-125">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="41dc1-126">Om du vill kontrollera kommunikationen till Microsoft Teams använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="41dc1-126">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="41dc1-127">Exchange Online Protection och IPv6</span><span class="sxs-lookup"><span data-stu-id="41dc1-127">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="41dc1-128">Exchange Online Protection (EOP) stöder IPv6 om överföringen sker via Transport Layer Security Protocol.</span><span class="sxs-lookup"><span data-stu-id="41dc1-128">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="41dc1-129">För EOP-intervallet använder du [OFFICE 365 URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="41dc1-129">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="41dc1-130">IPv6-stöd för Office 365-myndighetserbjudanden</span><span class="sxs-lookup"><span data-stu-id="41dc1-130">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="41dc1-131">Office 365 IPv6-stöd för myndighetserbjudanden överensstämmer med Office of Management and Budget (OMB) Chief for Chief Information Officers of Executive Departments and Agencies, liksom Federal Government Adoption of Internet Protocol Version 6 (IPv6) -protokoll.</span><span class="sxs-lookup"><span data-stu-id="41dc1-131">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="41dc1-132">[Microsoft Office 365 för myndigheter](https://go.microsoft.com/fwlink/p/?LinkId=325414) är en tjänst för flera innehavare som lagrar data för amerikanska myndigheter i ett avskiljt communitymoln.</span><span class="sxs-lookup"><span data-stu-id="41dc1-132">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="41dc1-133">Precis som andra Office 365-erbjudanden erbjuder det produktivitets- och samarbetstjänster, inklusive Exchange Online, Skype för företag, SharePoint Online och Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="41dc1-133">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="41dc1-134">Microsoft Office 365-myndighetserbjudanden gäller endast för 2013 och senare.</span><span class="sxs-lookup"><span data-stu-id="41dc1-134">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="41dc1-135">Mer information om Office 365-myndighetserbjudanden finns i Vi presenterar [Office 365 för myndigheter: Ett amerikanska Government Community Cloud.](https://go.microsoft.com/fwlink/p/?LinkId=325414)</span><span class="sxs-lookup"><span data-stu-id="41dc1-135">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="41dc1-136">International Traffic in Arms Regulations (ITAR) är en uppsättning bestämmelser för myndigheter i USA som styr export och import av försvarrelaterade artiklar och tjänster för [United States Munitions List (USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415)</span><span class="sxs-lookup"><span data-stu-id="41dc1-136">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="41dc1-137">Microsoft Office 365 för företag tillhandahåller dedikerade värdtjänster för Microsofts produktivitetslösningar som uppfyller kraven för säkerhet, sekretess och regelefterlevnad för amerikanska federala myndigheter som kräver Federal Information Security Management-certifiering (FISMA) och kommersiella enheter som omfattas av ITAR.</span><span class="sxs-lookup"><span data-stu-id="41dc1-137">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="41dc1-138">Saker att tänka på när du använder IPv6 och Office 365</span><span class="sxs-lookup"><span data-stu-id="41dc1-138">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="41dc1-139">Vi rekommenderar att du inte inaktiverar IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-139">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="41dc1-140">Mer information finns i den här [vägledningsartikeln.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)</span><span class="sxs-lookup"><span data-stu-id="41dc1-140">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="41dc1-141">Ta hänsyn till följande för att fastställa vilka IP-versioner som används i nätverket:</span><span class="sxs-lookup"><span data-stu-id="41dc1-141">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="41dc1-142">Om visningen av **IPConfig-kommandot** i kommandotolken innehåller rader med namnet "IPv6-adress" eller "Tillfällig IPv6-adress" har du IPv6 i din miljö.</span><span class="sxs-lookup"><span data-stu-id="41dc1-142">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="41dc1-143">Om alla IPv6-adresser börjar med "fe80" och motsvarar rader med namnet "Länk lokal IPv6-adress" har du inte IPv6 i din miljö.</span><span class="sxs-lookup"><span data-stu-id="41dc1-143">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="41dc1-144">Det här kan gälla för ditt nätverk:</span><span class="sxs-lookup"><span data-stu-id="41dc1-144">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="41dc1-145">I den offentliga prenumerationstjänsten går det inte att göra köp med kreditkort via IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-145">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="41dc1-146">Detta gäller inte GCC (Government Community Cloud) eftersom myndigheter har EA-licensiering (Enterprise Agreement).</span><span class="sxs-lookup"><span data-stu-id="41dc1-146">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="41dc1-147">IPv6 stöder inte vissa RMS-scenarier (Rights Management Services).</span><span class="sxs-lookup"><span data-stu-id="41dc1-147">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="41dc1-148">IPv6 stöder inte BES (BlackBerry® Enterprise Server) eftersom BlackBerry inte stöder IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-148">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="41dc1-149">Om du använder AD FS (Active Directory Federation Services) med Office 365 stöds inte reklam din AD FS-nätverksslutpunkt till Office 365 med hjälp av IPv6.</span><span class="sxs-lookup"><span data-stu-id="41dc1-149">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="41dc1-150">Du ska inte inkludera AAAA-poster i AD FS DNS-posten när du använder Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41dc1-150">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="41dc1-151">Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="41dc1-151">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41dc1-152">Se även</span><span class="sxs-lookup"><span data-stu-id="41dc1-152">See also</span></span>

<span data-ttu-id="41dc1-153">[IPv6 Learning-översikt](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="41dc1-153">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="41dc1-154">IPv6- informationsguide</span><span class="sxs-lookup"><span data-stu-id="41dc1-154">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
