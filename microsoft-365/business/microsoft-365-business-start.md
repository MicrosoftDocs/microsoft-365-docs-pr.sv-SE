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
description: Lär dig mer om Microsoft 365 för företag, hur du konfigurerar det och hur du förbereder användarnas enheter och datorer så att de skyddas av Microsoft 365 för företag.
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306498"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Komma igång med Microsoft 365 för företag

## <a name="what-is-microsoft-365-for-business"></a>Vad är Microsoft 365 för företag?

Microsoft 365 för företag är en omfattande uppsättning Business Productivity-och samarbets verktyg, till exempel Outlook, Word, Excel och andra Office-produkter, som alltid är uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android-och Windows 10-enheter med säkerhet i företags kvalitet som är lätt att hantera.

Titta på den här videon för en snabb översikt över Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 för företag är avsedda för upp till 300-licenser. Om du behöver fler licenser finns mer information i dokumentationen för [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986). 
  
## <a name="get-microsoft-365-for-business"></a>Skaffa Microsoft 365 för företag

- Om du har en partner får de Microsoft 365 för företag: [Skaffa microsoft 365 för företag från Microsoft Partner Center](get-microsoft-365-business.md).
    
- Om du inte har en partner och vill skaffa Microsoft 365 för företag kan du [köpa den här](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Konfigurera Microsoft 365 för företag

 **Översikt över konfiguration av Microsoft 365 för företag**
  
Följande diagram beskriver hur administratörer konfigurerar Microsoft 365 för företag. Här beskrivs hur du förbereder Windows-datorer för Microsoft 365 för företag. Du kan också lägga till nya enheter i administrations centret för Microsoft 365 med [autopilot för Windows](add-autopilot-devices-and-profile.md). Du kan använda autopilot för att konfigurera och förkonfigurera nya enheter så att de är redo för produktiv användning så fort en användare loggar in med sina Microsoft 365 för företag-autentiseringsuppgifter.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Titta på den här videon för en översikt över installation av Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Konfigurera Microsoft 365 för företag (administratör)

Logga in i [administrations centret för microsoft 365](https://portal.office.com/adminportal/home) med dina globala administratörs uppgifter och utför följande steg för att konfigurera Microsoft 365 för företag. 
  
1. [Förutsättningar för att skydda data på enheter med Microsoft 365 för företag](pre-requisites-for-data-protection.md)
    
    Läs igenom kraven först för att se till att dina enheter är klara för Microsoft 365 för företag.
    
2. [Använda installations guiden för att konfigurera Microsoft 365 för företag](set-up.md)
    
    Om du **flyttar permanent från en lokal Active Directory till molnet**kan du gå till administrations centret för Microsoft 365 och använda installations guiden för att lägga till användarna manuellt, eller så kan du göra en tidssynkronisering med Azure AD Connect. Du kan göra det på två sätt: 
    
    - Om du också har en Exchange 2010-, Exchange 2013-eller Exchange 2016-Server kan du [använda minimal hybrid för att snabbt migrera Exchange-postlådor till Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). De lägsta hybrid stegen omfattar en engångs synkronisering av användare till Azure AD och e-postmigrering från lokal till molnet. När e-postmigreringen är klar inaktive ras katalog synkronisering automatiskt när du använder den här metoden.
    
    - Använd guiden för att synkronisera dina användare till molnet. Följ stegen i [Konfigurera katalog synkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) för att slutföra processen. När du har synkroniserat användarna till molnet måste du [inaktivera profilsynkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization).
    
    Du måste också ge varje användare som lagts till på det här sättet en licens till Microsoft 365 för företag. Du kan göra det i [installations guiden](set-up.md) eller [tilldela användare licenser](../admin/manage/assign-licenses-to-users.md).
    
### <a name="2-prepare-mobile-devices"></a>2: förbereda mobila enheter

Följ stegen i [Konfigurera mobila enheter för Microsoft 365 för företag-användare](set-up-mobile-devices.md) om du vill installera Office-appar på enheter och se till att de skyddas av Microsoft 365 för företag. 
  
### <a name="3-prepare-pcs"></a>3: förbereda datorer

Administratörer kan välja inställningar för nya Windows 10-datorer med hjälp av [Windows autopilot](add-autopilot-devices-and-profile.md). Användare kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i det här avsnittet: [Konfigurera Windows-datorer för Microsoft 365 för företag-användare](set-up-windows-devices.md). För befintliga **enheter kan användarna** [Flytta filer till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som är kopplade till Windows-profilen till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 för företag för att skydda Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal inloggning. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag](manage-windows-devices.md) för att konfigurera detta. Den här metoden är standard och enheter i det här tillståndet kallas **hybrid Azure AD-anslutna enheter**. 
  
Om du behåller en lokal Active Directory-resurs (till exempel fil resurser och skrivare) kan du ge **Azure AD-anslutna enheter** åtkomst till dessa resurser genom att följa stegen här: [åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 för företag](access-resources.md).
  
  
## <a name="contact-support"></a>Kontakta support

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som Microsoft 365 för företag-administratör har du till gång till vårt kund support team: ** [kontakta supporten för företags produkter – hjälp för administratörer](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>Se även

[Dokumentation och resurser för Microsoft 365 för företag](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Hantera microsoft 365 för företag](manage.md)–[migrera till Microsoft 365 för företag](migrate-to-microsoft-365-business.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
