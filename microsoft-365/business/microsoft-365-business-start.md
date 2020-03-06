---
title: Komma igång med Microsoft 365 Business
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Lär dig mer om Microsoft 365 Business, hur du konfigurerar det och hur du förbereder användarnas enheter och datorer för att säkerställa att de skyddas av Microsoft 365 Business.
ms.openlocfilehash: f6fd73762c0b57777c19d32886f758875e2e7e6a
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547740"
---
# <a name="get-started-with-microsoft-365-business"></a>Komma igång med Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Vad är Microsoft 365 Business

Microsoft 365 Business är en omfattande uppsättning verktyg för affärsproduktivitet och samarbete, till exempel Outlook, Word, Excel och andra Office-produkter, som alltid är uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.

Titta på det här videoklippet för en snabb översikt över Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 Business är avsett för upp till 300 licenser. Om du behöver fler licenser läser du Dokumentationen för [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) för mer information. 
  
## <a name="get-microsoft-365-business"></a>Skaffa Microsoft 365 Business

- Om du har en partner får de Microsoft 365 Business: [Skaffa Microsoft 365 Business från Microsoft Partner Center](get-microsoft-365-business.md).
    
- Om du inte har en partner men vill skaffa Microsoft 365 Business, kan du [köpa det här](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Konfigurera Microsoft 365 Business

 **Översikt över microsoft 365 Business Suite-konfigurerad**
  
I följande diagram beskrivs hur administratörer konfigurerar Microsoft 365 Business. Dessutom beskrivs stegen för att förbereda Windows-datorer för Microsoft 365 Business. Du kan också lägga till nya enheter i administrationscentret för Microsoft 365 Business med [Windows AutoPilot](add-autopilot-devices-and-profile.md). Du kan använda AutoPilot för att konfigurera och förkonfigurera nya enheter så att de är redo för produktiv användning så snart en användare loggar in med sina Microsoft 365 Business-autentiseringsuppgifter.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Titta på det här videoklippet för en översikt över installationsprogrammet för Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Konfigurera Microsoft 365 Business (Admin)

Logga in på [Microsoft 365 Business administrationscenter](https://portal.office.com/adminportal/home) med dina globala administratörsuppgifter och fyll i följande steg för att konfigurera Microsoft 365 Business. 
  
1. [Förutsättningar för att skydda data på enheter med Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Läs förutsättningarna först för att se till att dina enheter är klara för Microsoft 365 Business.
    
2. [Använda installationsguiden för att konfigurera Microsoft 365 Business](set-up.md)
    
    Om du **flyttar permanent från en lokal Active Directory till molnet**kan du gå till administrationscentret för Microsoft 365 Business och använda installationsguiden för att lägga till användarna manuellt, eller så kan du göra en engångssynkronisering med Azure AD Connect. Du kan göra det på två sätt: 
    
    - Om du också har en Exchange 2010-, Exchange 2013- eller Exchange 2016-server kan du [använda Minimal Hybrid för att snabbt migrera Exchange-postlådor till Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). De minimala hybridstegen inkluderar en engångssynkronisering av användare till Azure AD och e-postmigrering från lokalt till molnet. När e-postmigreringen är klar inaktiveras katalogsynkroniseringen automatiskt när du använder den här metoden.
    
    - Använd katalogsynkroniseringsguiden för Office 365 för att synkronisera användarna med molnet. Följ stegen i [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) för att slutföra processen. När du har synkroniserat användarna med molnet måste du [inaktivera katalogsynkronisering för Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Du måste också ge varje användare som har lagts till på det här sättet en licens till Microsoft 365 Business. Du kan göra detta i [installationsguiden](set-up.md) eller [tilldela licenser till användare i Office 365 för företag](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Förbered mobila enheter

Följ stegen i [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) för att installera Office-appar på enheter och se till att de skyddas av Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: Förbered datorer

Administratörer kan i förtid välja inställningar för nya Windows 10-datorer med hjälp av [Windows AutoPilot](add-autopilot-devices-and-profile.md). Användare kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i det här avsnittet: [Konfigurera Windows-datorer för Microsoft 365 Business-användare](set-up-windows-devices.md). För befintliga enheter kan användare **eventuellt** [flytta filer till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som är associerade med Windows-profilen till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) för att konfigurera detta. Den här metoden är att föredra och enheter i det här tillståndet kallas **Hybrid Azure AD-anslutna enheter**. 
  
Om du behåller en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina **Azure AD-anslutna enheter** åtkomst till dessa resurser genom att följa stegen här: [Få tillgång till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).
  
  
## <a name="contact-support"></a>Kontakta support

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som Microsoft 365 Business-administratör har du tillgång till vår kundtjänst: ** [Kontaktsupport för företagsprodukter – hjälp för administratörer](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Se även

[Microsoft 365 Business dokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Hantera Microsoft 365 Business](manage.md)[Migrera till Microsoft 365 Business](migrate-to-microsoft-365-business.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
