---
title: Köpa ett domännamn i Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Läs om hur du köper ett domännamn i Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 5ffb5f9268dcd8b38245e0b85c7d790b46628766
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894473"
---
# <a name="buy-a-domain-name-in-office-365"></a>Köpa ett domännamn i Office 365

 *Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller en [företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*  

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Logga in och \> gå \> till Inställningar Domäner Köp en domän

1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
    
3. På sidan **Domäner** väljer du **Köp domän**.
    
Du kan välja bland följande toppnivådomän för din domän.
  
- .biz (biz)
    
- .com (på marknaden)
    
- .info (info)
    
- .me
    
- .mobi (mobi)
    
- .net (netto)
    
- .org (på andra)
    
- .tv
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> När du väljer **Köp domän**kan du omdirigeras till din Microsoft-partners webbplats om klienten köps/hanteras via en Microsoft-partner.

### <a name="domain-privacy"></a>Domän sekretess
Vi erbjuder en gratis Prenumeration på domänsekretess vid köp av en domän. Detta håller dina kontaktuppgifter kopplade till registreringen av din domän med ICANN privat. [Lära sig mer.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Köpa en domän från en annan domänregistrator
Om du vill köpa en domän från en annan domänregistrator än [GoDaddy](https://www.godaddy.com)rekommenderar vi att du använder en nedan som stöder automatisk installation (Domain Connect). 
  
- [1&amp;1 IONOS](https://www.1and1.com/)
- [Wordpress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Överföra din domän till en annan domänregistrator

Om din domän är registrerad hos en leverantör som inte stöder alla nödvändiga DNS-poster kan du överföra den till en annan registrator. När du överför domänen kan du ändra vem du skickar betalningar till för att förnya och behålla ditt domännamn.
  
Begär överföringen hos registratorn du vill flytta din domän till. Titta efter ett alternativ som **Överför DNS** på registratorns webbplats. När ändringarna har genomförts kan det ta några dagar innan de uppdateras på Internet.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Så här köper du en domän för Office 365 som drivs av 21Vianet



Om du inte redan har en egen domän kan du enkelt köpa en online hos en domännamnsregistrator, en domänåterförsäljare eller hos din nuvarande Internetleverantör. Du får ett domännamn när du registrerar dig för Office 365 med 21Vianet, till exempel contoso.partner.onmschina.cn. Men du kanske vill använda ett eget domännamn, till exempel fourthcoffee.com.
  
Om du vill konfigurera en domän i Office 365 måste du äga domänen och ändra vissa av domänens DNS-poster.
  
> [!CAUTION]
> Vissa domänregistratorer eller DNS-värdtjänster tillåter inte att alla DNS-poster som krävs för Office 365 skapas. Följande lista med värdtjänster stöder alla nödvändiga poster. Om du funderar på att använda en annan värdtjänst bör du [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
När du har registrerat din domän (hos en domänregistrator) kan du logga in på Office 365 som administratör och konfigurera domänen så att du kan använda den med din e-postadress och andra tjänster.
  
> [!NOTE]
> Informationen om den offentliga SharePoint Online-webbplatsen i den här artikeln gäller endast om organisationen har köpt Office 365 före den 9 mars 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-office-365"></a>Domänregistratorer som stöder alla DNS-poster som krävs för Office 365

- [Oray](https://oray.com/)
    
- [HejKina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till en domän i Office 365](../setup/add-domain.md)

[Vanliga frågor och svar om domäner](../setup/domains-faq.md)

[Få hjälp med Office 365-domäner](get-help-with-domains.md)

[Uppdatera DNS-poster för att hålla din webbplats med din nuvarande värdleverantör](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider) 