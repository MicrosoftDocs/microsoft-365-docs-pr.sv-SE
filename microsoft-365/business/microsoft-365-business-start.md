---
title: Komma igång med Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Läs mer Microsoft 365 för företag, hur du bereder det och hur du förbereder användarnas enheter och datorer för att säkerställa att de skyddas av Microsoft 365 för företag.
ms.openlocfilehash: 2ab0079da7a8f30d481cdb3d3dc6d165b4a19e99
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339299"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Komma igång med Microsoft 365 för företag

## <a name="what-is-microsoft-365-for-business"></a>Vad är Microsoft 365 för företag

Microsoft 365 för företag är en omfattande uppsättning produktivitets- och samarbetsverktyg för företag, till exempel Outlook, Word, Excel och andra Office-produkter, som alltid är uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.

## <a name="watch-what-is-microsoft-365-business-premium"></a>Video: Vad är Microsoft 365 Business Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 för företag är avsedd för upp till 300 licenser. Om du behöver fler licenser finns mer information i dokumentationen för [Microsoft 365 Enterprise](../enterprise/index.yml). 
  
## <a name="get-microsoft-365-for-business"></a>Skaffa Microsoft 365 för företag

- Om du har en partner får partner i Microsoft 365 för företag: [Skaffa Microsoft 365 för företag från Microsoft Partner Center.](get-microsoft-365-business.md)
    
- Om du inte har en partner och vill skaffa ett Microsoft 365 företag kan du [köpa det här](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Konfigurera Microsoft 365 för företag

 **Översikt över Microsoft 365 för företag-paketet**
  
I följande diagram beskrivs hur administratörer konfigurerar Microsoft 365 för företag. Dessutom beskrivs stegen för att förbereda Windows för företag Microsoft 365. Du kan också lägga till nya enheter i Administrationscenter för Microsoft 365 med [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Du kan använda AutoPilot för att konfigurera och förkonfigurera nya enheter så att de är redo för produktiv användning så snart en användare loggar in med sina inloggningsuppgifter för Microsoft 365 för företag.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>Titta: Konfigurera Microsoft 365 företag

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälp dig kan du ta en titt på den[fullständiga utbildningsserien för småföretag och de som är nya för Microsoft 365](../business-video/index.yml).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Konfigurera Microsoft 365 för företag (administratör)

Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com/adminportal/home) dina autentiseringsuppgifter som global administratör och slutför följande steg för att konfigurera Microsoft 365 för företag. 
  
1. [Krav för att skydda data på enheter med Microsoft 365 för företag](pre-requisites-for-data-protection.md)
    
    Läs först förutsättningarna för att kontrollera att dina enheter är redo för Microsoft 365 för företag.
    
2. [Använda installationsguiden för att konfigurera Microsoft 365 för företag](set-up.md)
    
    Om du flyttar permanent från en lokal **Active Directory-installation** till molnet kan du gå till Administrationscenter för Microsoft 365 och använda installationsguiden för att lägga till användarna manuellt eller göra en synkronisering för bara en gång med Azure AD Anslut. Du kan göra det på två sätt: 
    
    - Om du även har en Exchange 2010-, Exchange 2013- eller Exchange 2016-server kan du använda Minimal hybrid för att snabbt migrera Exchange-postlådor [till Microsoft 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) I de minimala hybridstegen ingår en synkronisering av användare till Azure AD och e-postmigrering från lokalt till molnet. När e-postmigrering är klar inaktiveras katalogsynkroniseringen automatiskt när du använder den här metoden.
    
    - Använd guiden för katalogsynkronisering för att synkronisera användarna till molnet. Följ stegen i Konfigurera [katalogsynkronisering för Microsoft 365](../enterprise/set-up-directory-synchronization.md) slutföra processen. När du har synkroniserat användarna med molnet måste du inaktivera [katalogsynkronisering för Microsoft 365](../enterprise/turn-off-directory-synchronization.md).
    
    Du måste också ge varje användare som har lagts till på det här sättet en licens för Microsoft 365 för företag. Det kan du göra i [installationsguiden eller](set-up.md) så kan du [tilldela användare licenser.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Förbereda mobila enheter

Följ stegen i Konfigurera mobila enheter för [Microsoft 365 för](set-up-mobile-devices.md) företag om du vill installera Office-appar på enheter och kontrollera att de skyddas av Microsoft 365 för företag. 
  
### <a name="3-prepare-pcs"></a>3: Förbereda datorer

Administratörer kan förvälja inställningar för nya Windows 10-datorer med hjälp [av Windows AutoPilot.](add-autopilot-devices-and-profile.md) Användarna kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i det här avsnittet: Konfigurera Windows-datorer för [Microsoft 365 för företagsanvändare.](set-up-windows-devices.md) För befintliga enheter kan **användare, om du vill,** [flytta filer till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som är kopplade Windows profil till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 för företag för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i Aktivera [domän-anslutna Windows 10-enheter](manage-windows-devices.md) som ska hanteras av Microsoft 365 för företag för att konfigurera detta. Den här metoden rekommenderas och enheter i det här läget kallas för **Hybrid Azure AD-anslutna enheter.** 
  
Om du behåller en lokal Active Directory-fil som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina **Azure AD-anslutna** enheter åtkomst till dessa resurser genom att följa stegen här: Få åtkomst till lokala resurser från en [Azure AD-ansluten](access-resources.md)enhet i Microsoft 365 för företag.
  
  
## <a name="contact-support"></a>Kontakta support

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som administratör Microsoft 365 för företag har du tillgång till vårt kundsupportteam: Kontakta supporten för **[företagsprodukter – hjälp för administratörer](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Relaterat innehåll

[Microsoft 365 dokumentation och resurser för för företag](./index.yml) (länksida)\
[Hantera Microsoft 365 för företag](manage.md) (artikel)\
[Migrera till Microsoft 365 för företag](migrate-to-microsoft-365-business.md) (artikel)\
[Utbildningsvideor för Microsoft 365 Business](../business-video/index.yml) (länksida)