---
title: Köpa ett domännamn
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
description: Lär dig hur du köper ett domän namn i Microsoft 365.
ms.openlocfilehash: d8c0bac5921b5cb3efacffdfee3ab948857b8a1f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658617"
---
# <a name="buy-a-domain-name"></a>Köpa ett domännamn

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 *För att lägga till, ändra eller ta bort domäner **måste** du vara **Global administratör** för [företags-eller företags abonnemang](https://products.office.com/business/office). Dessa ändringar påverkar hela klient organisationen, *anpassade administratörer* eller *vanliga användare* kommer inte att kunna göra dessa ändringar.*  

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Logga in och gå till inställnings \> domäner \> köpa en domän

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
3. På sidan **domäner** väljer du **Köp domän**.
    
Du kan välja bland följande toppnivådomän för din domän.
  
- . B2B argumentssida
    
- . com
    
- . info
    
- . mig
    
- .mobi
    
- Studio
    
- . org
    
- . TV
    
- . co.uk
    
- org.uk
    

> [!NOTE]
> När du väljer **Köp domän** kanske du omdirigeras till din Microsoft-partners webbplats om klient organisationen köps/hanteras via en Microsoft-partner.

### <a name="domain-privacy"></a>Domän integritet
Vi tillhandahåller ett kostnads fritt domän integritets abonnemang med köp av en domän. Då hålls dina kontakt uppgifter kopplade till registreringen av din domän med ICANN privat. [Lära sig mer.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Köpa en domän från en annan domänregistrator
Om du vill köpa en domän från en annan domän registrator än [GoDaddy](https://www.godaddy.com)rekommenderar vi att du använder en nedan som stöder automatisk konfigurering (Domain Connect). 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Överföra din domän till en annan domänregistrator

Om din domän är registrerad hos en leverantör som inte stöder alla nödvändiga DNS-poster kan du överföra den till en annan registrator. När du överför domänen kan du ändra vem du skickar betalningar till för att förnya och behålla ditt domännamn.
  
Begär överföringen hos registratorn du vill flytta din domän till. Titta efter ett alternativ som **Överför DNS** på registratorns webbplats. När ändringarna har genomförts kan det ta några dagar innan de uppdateras på Internet.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Så här köper du en domän för Office 365 som drivs av 21Vianet



Om du inte redan har en egen domän kan du enkelt köpa en online hos en domännamnsregistrator, en domänåterförsäljare eller hos din nuvarande Internetleverantör. Du får ett domännamn när du registrerar dig för Office 365 med 21Vianet, till exempel contoso.partner.onmschina.cn. Men du kanske vill använda ett eget domännamn, till exempel fourthcoffee.com.
  
Om du vill konfigurera en domän i Microsoft 365 måste du äga en domän och ändra vissa av domänens DNS-poster.
  
> [!CAUTION]
> Vissa domän registratorer eller DNS-värdar tillåter inte att de DNS-poster som krävs av Microsoft 365 skapas. Följande lista med värdtjänster stöder alla nödvändiga poster. Om du funderar på att använda en annan värdtjänst bör du [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
När du har registrerat din domän (hos en domän registrator) loggar du in på Microsoft 365 som administratör och konfigurerar din domän så att du kan använda den med din e-postadress och andra tjänster..
  
> [!NOTE]
> Informationen om den offentliga SharePoint Online-webbplatsen i den här artikeln gäller endast om din organisation köpte Microsoft 365 före den 9 mars 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Domän registratorer som stöder alla DNS-poster som krävs för Microsoft 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Lägga till en domän i Microsoft 365](../setup/add-domain.md)

[Vanliga frågor och svar om domäner](../setup/domains-faq.yml)

[Uppdatera DNS-poster för att behålla din webbplats hos din nuvarande värd](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider).
