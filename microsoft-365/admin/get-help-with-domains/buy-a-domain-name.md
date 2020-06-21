---
title: Köpa ett domännamn
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Läs om hur du köper ett domännamn i Microsoft 365.
ms.openlocfilehash: fcf13314d7206837f10459ed8c0a44e5d41f219b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780199"
---
# <a name="buy-a-domain-name"></a>Köpa ett domännamn

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 *Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller en [företagsplan](https://products.office.com/business/office). Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*  

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Logga in och gå till Inställningar \> Domäner \> Köp en domän

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
3. På sidan **Domäner** väljer du **Köp domän**.
    
Du kan välja bland följande toppnivådomän för din domän.
  
- .biz (biz)
    
- .com (på marknaden)
    
- .info (info)
    
- .me
    
- .mobi (mobi)
    
- .net (netto)
    
- .org (på andra)
    
- .tv (tv)
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> När du väljer **Köp domän**kan du omdirigeras till din Microsoft-partners webbplats om klienten köps/hanteras via en Microsoft-partner.

### <a name="domain-privacy"></a>Domän sekretess
Vi erbjuder en gratis prenumeration på domänsekretess vid köp av en domän. Detta håller dina kontaktuppgifter kopplade till registreringen av din domän med ICANN privat. [Lära sig mer.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Köpa en domän från en annan domänregistrator
Om du vill köpa en domän från en annan domänregistrator än [GoDaddy](https://www.godaddy.com)rekommenderar vi att du använder en nedan som stöder automatisk installation (Domain Connect). 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [Wordpress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Överföra din domän till en annan domänregistrator

If your domain is managed by a provider that doesn't support all the necessary DNS records, you can transfer it to a different registrar. When you transfer the domain, you change who you send payments to in order to renew and keep your domain name.
  
Request the transfer at the registrar that you want to move your domain to. Look on their website for an option such as **Transfer DNS**. Be aware that after they make the changes, it can take a few days update across the Internet.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Så här köper du en domän för Office 365 som drivs av 21Vianet



If you don't already have your own domain, you can easily buy one online at a domain name registrar, domain reseller, or even at your current Internet provider. You get a domain name when you sign up for Office 365 operated by 21Vianet, for example, contoso.partner.onmschina.cn. But you may want to use a custom domain name, like fourthcoffee.com.
  
Om du vill konfigurera en domän i Microsoft 365 måste du äga en domän och ändra några av DNS-posterna för domänen.
  
> [!CAUTION]
> Vissa domänregistratorer eller DNS-värdleverantörer tillåter inte att du skapar alla DNS-poster som krävs av Microsoft 365. Följande lista med värdtjänster stöder alla nödvändiga poster. Om du funderar på att använda en annan värdtjänst bör du [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
När du har registrerat domänen (hos en domänregistrare) loggar du in på Microsoft 365 som administratör och konfigurerar domänen så att du kan använda den med din e-postadress och andra tjänster..
  
> [!NOTE]
> Informationen om den offentliga sharepoint-webbplatsen för SharePoint Online i den här artikeln gäller endast om din organisation köpte Microsoft 365 före den 9 mars 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Domänregistratorer som stöder alla DNS-poster som krävs för Microsoft 365

- [Oray](https://oray.com/)
    
- [HejKina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till en domän i Microsoft 365](../setup/add-domain.md)

[Vanliga frågor och svar om domäner](../setup/domains-faq.md)

[Få hjälp med domäner](get-help-with-domains.md)

[Uppdatera DNS-poster för att hålla din webbplats med din nuvarande webbhotell](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider).
