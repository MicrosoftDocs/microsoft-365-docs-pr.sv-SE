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
description: 'Sammanfattning: beskriver IPv6-stöd i Microsoft Office 365-komponenter och i Office 365 stats support.'
ms.openlocfilehash: c4ecd2ef26ecf660eb1d172b1951907724d2238a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694478"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="3619b-103">IPv6-stöd i Office 365-tjänster</span><span class="sxs-lookup"><span data-stu-id="3619b-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="3619b-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3619b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3619b-105">Office 365 stöder både IPv6 och IPv4; men inte alla Office 365-funktioner är helt aktiverade med IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="3619b-106">Det innebär att du måste använda både IPv4 och IPv6 för att ansluta till Office 365.</span><span class="sxs-lookup"><span data-stu-id="3619b-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="3619b-107">Om du filtrerar utgående trafik till Office 365 finns den fullständiga listan över IPv6-adresser som stöds av Office 365 i artikeln [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="3619b-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="3619b-108">När nätverket är konfigurerat och rätt IPv6-adresser tillåts kan du hämta [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) från Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="3619b-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="3619b-109">IPv6-stöd i prenumerations tjänsten för Office 365</span><span class="sxs-lookup"><span data-stu-id="3619b-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="3619b-110">Exchange Online och IPv6</span><span class="sxs-lookup"><span data-stu-id="3619b-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="3619b-111">Om programmet som du använder för att ansluta till Exchange Online har stöd för IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk.</span><span class="sxs-lookup"><span data-stu-id="3619b-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="3619b-112">Om du vill styra kommunikationen till Exchange Online kan du använda IP-adressintervall i [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="3619b-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="3619b-113">SharePoint Online och IPv6</span><span class="sxs-lookup"><span data-stu-id="3619b-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="3619b-114">**Office 365 myndigheter G1/G3/G4/K1** Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 försöker det använda IPv6 som standard.</span><span class="sxs-lookup"><span data-stu-id="3619b-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="3619b-115">**Offentliga moln för flera innehavare** Microsoft möjliggör SharePoint Online-IPv6 på din begäran.</span><span class="sxs-lookup"><span data-stu-id="3619b-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="3619b-116">Du måste ange IP-adresserna för din organisations DNS-struktur för CIDR-uppskrivning.</span><span class="sxs-lookup"><span data-stu-id="3619b-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="3619b-117">Kom ihåg att den här DNS-infrastrukturen inte kan delas av andra organisationer för IPv6 så att den kan aktive ras för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="3619b-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="3619b-118">När IPv6 är aktiverat används IPv6 som standard om programmet som du använder för att ansluta till SharePoint Online har stöd för IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="3619b-119">Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk.</span><span class="sxs-lookup"><span data-stu-id="3619b-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="3619b-120">Om du vill styra kommunikationen till SharePoint Online använder du IP-adressintervallet i [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="3619b-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 <span data-ttu-id="3619b-121">**Office 365 myndigheter G1/G3/G4/K1** Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 försöker det använda IPv6 som standard.</span><span class="sxs-lookup"><span data-stu-id="3619b-121">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="3619b-122">Skype för företag och IPv6</span><span class="sxs-lookup"><span data-stu-id="3619b-122">Skype for Business and IPv6</span></span>

<span data-ttu-id="3619b-123">Observera att IPv6 inte stöds i Skype för företag och kan inte längre aktive ras.</span><span class="sxs-lookup"><span data-stu-id="3619b-123">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="3619b-124">Exchange Online Protection och IPv6</span><span class="sxs-lookup"><span data-stu-id="3619b-124">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="3619b-125">Exchange Online Protection (EOP) stöder IPv6 om överföringen sker via säkerhets protokollet Transport Layer.</span><span class="sxs-lookup"><span data-stu-id="3619b-125">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="3619b-126">Använd [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md)för det EOP intervallet.</span><span class="sxs-lookup"><span data-stu-id="3619b-126">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="3619b-127">IPv6-stöd för statligt utbud av Office 365</span><span class="sxs-lookup"><span data-stu-id="3619b-127">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="3619b-128">Stöd för Office 365 IPv6 för statliga offerter som följer organisationens förvaltnings-och budget avtal (OMB) för chefens myndigheters och byråers företags administratörer, samt statliga myndigheter för införande av en IPv6-memorandum (Internet Protocol version 6).</span><span class="sxs-lookup"><span data-stu-id="3619b-128">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="3619b-129">[Microsoft Office 365 för myndigheter](https://go.microsoft.com/fwlink/p/?LinkId=325414) är en tjänst för flera innehavare som lagrar statliga uppgifter i ett avdelat gemenskaps moln.</span><span class="sxs-lookup"><span data-stu-id="3619b-129">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="3619b-130">Precis som andra Office 365-erbjudanden tillhandahåller den funktioner för produktivitet och samarbete, inklusive Exchange Online, Skype för företag, SharePoint Online och Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="3619b-130">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="3619b-131">Microsoft Office 365 myndighets bud gäller endast för 2013 och senare.</span><span class="sxs-lookup"><span data-stu-id="3619b-131">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="3619b-132">Mer information om statligt utbud för Office 365 finns i artikeln [om att lansera office 365 för myndigheter: ett forum moln i USA](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span><span class="sxs-lookup"><span data-stu-id="3619b-132">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="3619b-133">Internationell trafik i stöd reglerna (ITAR) är en uppsättning amerikanska myndighets regler som styr export och import av skydd mot försvar i [Munitions lista (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span><span class="sxs-lookup"><span data-stu-id="3619b-133">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="3619b-134">Microsoft Office 365 för företag tillhandahåller dedikerade värd tjänster för Microsoft-lösningar som stöder säkerhets-, integritets-och myndighets krav för amerikanska myndigheter som kräver Federal Information Security Management (FISMA)-certifiering och kommersiella enheter, beroende på ITAR.</span><span class="sxs-lookup"><span data-stu-id="3619b-134">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="3619b-135">Saker att tänka på när du använder IPv6 och Office 365</span><span class="sxs-lookup"><span data-stu-id="3619b-135">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="3619b-136">Vi rekommenderar att du inte inaktiverar IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-136">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="3619b-137">Mer information finns i den här [artikeln](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span><span class="sxs-lookup"><span data-stu-id="3619b-137">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="3619b-138">För att ta reda på vilka IP-versioner som används i nätverket bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="3619b-138">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="3619b-139">Om visningen av kommandot **ipconfig** i kommando tolken innehåller rader med namnet "IPv6-adress" eller "tillfällig IPv6-adress" har du IPv6 i din miljö.</span><span class="sxs-lookup"><span data-stu-id="3619b-139">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="3619b-140">Om alla IPv6-adresser börjar med "FE80" och motsvarar rader med namnet "länk lokal IPv6-adress" har du inte IPv6 i din miljö.</span><span class="sxs-lookup"><span data-stu-id="3619b-140">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="3619b-141">Dessa överväganden kanske gäller för ditt nätverk:</span><span class="sxs-lookup"><span data-stu-id="3619b-141">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="3619b-142">Den offentliga abonnemangs tjänsten stöder inte inköp via kredit kort via IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-142">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="3619b-143">Detta gäller inte statliga community-molnet (GCC) eftersom regeringarna har en licens för Enterprise Agreement (EA).</span><span class="sxs-lookup"><span data-stu-id="3619b-143">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="3619b-144">IPv6 stöder inte vissa RMS-scenarier (Rights Management Services).</span><span class="sxs-lookup"><span data-stu-id="3619b-144">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="3619b-145">IPv6 stöder inte Black Berry® Enterprise Server (BES) eftersom Black Berry inte stöder IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-145">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="3619b-146">Om du använder AD FS (Active Directory Federation Services) med Office 365 stöds inte din AD FS-slutpunkt till Office 365 med IPv6.</span><span class="sxs-lookup"><span data-stu-id="3619b-146">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="3619b-147">Du bör inte ta med AAAA-poster i AD FS DNS-posten när du använder Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3619b-147">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="3619b-148">Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)</span><span class="sxs-lookup"><span data-stu-id="3619b-148">Here's a short link you can use to come back: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3619b-149">Se även</span><span class="sxs-lookup"><span data-stu-id="3619b-149">See also</span></span>

<span data-ttu-id="3619b-150">[Utbildnings översikt för IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="3619b-150">[IPv6 Learning Roadmap](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="3619b-151">Hjälp guide för IPv6</span><span class="sxs-lookup"><span data-stu-id="3619b-151">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
