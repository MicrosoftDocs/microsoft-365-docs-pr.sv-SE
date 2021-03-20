---
title: Komma igång med Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Läs mer om Microsoft 365 för företag, hur du bereder dem och hur du förbereder användarnas enheter och datorer för att säkerställa att de skyddas av Microsoft 365 för företag.
ms.openlocfilehash: 9430dc7aa637be3fdb833150b83e96caacc82170
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912971"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Komma igång med Microsoft 365 för företag

## <a name="what-is-microsoft-365-for-business"></a>Vad är Microsoft 365 för företag

Microsoft 365 för företag är en omfattande uppsättning produktivitets- och samarbetsverktyg för företag, till exempel Outlook, Word, Excel och andra Office-produkter, som alltid är uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.

Titta på den här videon för en snabb överblick över Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 för företag är avsett för upp till 300 licenser. Om du behöver fler licenser finns mer information i dokumentationen för [Microsoft 365 Enterprise](../enterprise/index.yml). 
  
## <a name="get-microsoft-365-for-business"></a>Skaffa Microsoft 365 för företag

- Om du har en partner får de Microsoft 365 för företag: [Skaffa Microsoft 365 för företag från Microsoft-partnercenter.](get-microsoft-365-business.md)
    
- Om du inte har en partner och vill skaffa Microsoft 365 för företag kan du [köpa det här](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Konfigurera Microsoft 365 för företag

 **Översikt över konfigurerat Microsoft 365 för företag-paket**
  
I följande diagram beskrivs hur administratörer konfigurerade Microsoft 365 för företag. Dessutom beskrivs stegen för att förbereda Windows-datorer för Microsoft 365 för företag. Du kan också lägga till nya enheter i administrationscentret för Microsoft 365 med [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Du kan använda AutoPilot för att konfigurera och förkonfigurera nya enheter så att de är redo för produktiv användning så snart en användare loggar in med sina autentiseringsuppgifter för Microsoft 365 för företag.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Titta på den här videon för en översikt över konfiguration av Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Konfigurera Microsoft 365 för företag (administratör)

Logga in på [administrationscentret för Microsoft 365](https://portal.office.com/adminportal/home) med dina autentiseringsuppgifter som global administratör och slutför följande steg för att konfigurera Microsoft 365 för företag. 
  
1. [Krav för att skydda data på enheter med Microsoft 365 för företag](pre-requisites-for-data-protection.md)
    
    Läs först förutsättningarna för att se till att dina enheter är redo för Microsoft 365 för företag.
    
2. [Använda installationsguiden för att konfigurera Microsoft 365 för företag](set-up.md)
    
    Om du flyttar permanent från en lokal **Active Directory-installation** till molnet kan du gå till administrationscentret för Microsoft 365 och använda installationsguiden för att lägga till användarna manuellt, eller göra en synkronisering bara en gång med Azure AD Connect. Du kan göra det på två sätt: 
    
    - Om du även har en Exchange 2010-, Exchange 2013- eller Exchange 2016-server kan du använda minimal hybridhybrid för att snabbt migrera Exchange-postlådor till [Microsoft 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) I de minimala hybridstegen ingår en synkronisering av användare till Azure AD och e-postmigrering från lokalt till molnet. När e-postmigrering är klar inaktiveras katalogsynkroniseringen automatiskt när du använder den här metoden.
    
    - Använd guiden för katalogsynkronisering för att synkronisera användarna till molnet. Följ stegen i Konfigurera [katalogsynkronisering för Microsoft 365 för](../enterprise/set-up-directory-synchronization.md) att slutföra processen. När du har synkroniserat användarna med molnet måste du inaktivera katalogsynkronisering [för Microsoft 365.](../enterprise/turn-off-directory-synchronization.md)
    
    Du måste också ge varje användare som har lagts till på det här sättet en licens för Microsoft 365 för företag. Det kan du göra i [installationsguiden eller](set-up.md) så kan du [tilldela användare licenser.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Förbereda mobila enheter

Följ anvisningarna i Konfigurera mobila enheter för [Microsoft 365](set-up-mobile-devices.md) för företag-användare för att installera Office-program på enheter och kontrollera att de skyddas av Microsoft 365 för företag. 
  
### <a name="3-prepare-pcs"></a>3: Förbereda datorer

Administratörer kan förvälja inställningar för nya Windows 10-datorer med hjälp av [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Användare kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i den här artikeln: Konfigurera Windows-datorer för [Microsoft 365 för företag-användare.](set-up-windows-devices.md) För befintliga enheter kan användare **flytta filer** [till OneDrive för företag.](move-files-to-onedrive.md) De kan också använda verktyg från tredje part för att flytta filer som är kopplade till Windows-profilen till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 för företag för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ anvisningarna i [Aktivera domänaktiverade Windows 10-enheter](manage-windows-devices.md) så att de kan hanteras av Microsoft 365 för företag för att konfigurera detta. Den här metoden rekommenderas och enheter i det här läget kallas för **Hybrid Azure AD-anslutna enheter.** 
  
Om du behåller en lokal Active Directory-fil som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina **Azure AD-anslutna** enheter åtkomst till dessa resurser genom att följa stegen här: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i [Microsoft 365 för](access-resources.md)företag.
  
  
## <a name="contact-support"></a>Kontakta support

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som Microsoft 365 för företag-administratör har du tillgång till vår kundtjänst: Kontakta supporten för **[företagsprodukter – hjälp för administratörer](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>Se även

[Dokumentation och resurser för Microsoft 365 för företag](./index.yml)
  
[Hantera Microsoft 365 för företag](manage.md)[Migrera till Microsoft 365 för företag](migrate-to-microsoft-365-business.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)