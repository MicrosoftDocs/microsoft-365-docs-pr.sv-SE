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
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Lär dig mer om Microsoft 365 för företag, hur du konfigurerar det och hur du förbereder användarnas enheter och datorer för att säkerställa att de skyddas av Microsoft 365 för företag.
ms.openlocfilehash: 17b142fb704d1b0be088a649490e751effb19517
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633212"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Komma igång med Microsoft 365 för företag

## <a name="what-is-microsoft-365-for-business"></a>Vad är Microsoft 365 för företag

Microsoft 365 för företag är en omfattande uppsättning verktyg för företagsproduktivitet och samarbete, till exempel Outlook, Word, Excel och andra Office-produkter, som alltid är uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.

Titta på det här videoklippet om du vill ha en snabb översikt över Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 för företag är avsett för upp till 300 licenser. Om du behöver fler licenser läser du [Microsoft 365 Enterprise-dokumentationen](https://go.microsoft.com/fwlink/p/?linkid=860986) för mer information. 
  
## <a name="get-microsoft-365-for-business"></a>Skaffa Microsoft 365 för företag

- Om du har en partner får de Microsoft 365 för företag: [Skaffa Microsoft 365 för företag från Microsoft Partner Center](get-microsoft-365-business.md).
    
- Om du inte har en partner och vill få Microsoft 365 för företag, kan du [köpa den här](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Konfigurera Microsoft 365 för företag

 **Översikt över Microsoft 365 för företag Suite-uppsättning**
  
I följande diagram beskrivs hur administratörer konfigurerar Microsoft 365 för företag. I rapporten beskrivs också stegen för att förbereda Windows-datorer för Microsoft 365 för företag. Du kan också lägga till nya enheter i Microsoft 365-administrationscentret med [Windows AutoPilot](add-autopilot-devices-and-profile.md). Du kan använda Autopilot för att konfigurera och förkonfigurera nya enheter så att de är redo för produktiv användning så snart en användare loggar in med sina Microsoft 365 för affärsautentiseringsuppgifter.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Titta på det här videoklippet om du vill ha en översikt över installationsprogrammet för Microsoft 365 för företag.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Konfigurera Microsoft 365 för företag (admin)

Logga in på [Microsoft 365 admincenter](https://portal.office.com/adminportal/home) med dina globala administratörsuppgifter och slutför följande steg för att konfigurera Microsoft 365 för företag. 
  
1. [Förutsättningar för att skydda data på enheter med Microsoft 365 för företag](pre-requisites-for-data-protection.md)
    
    Läs förutsättningarna först för att se till att dina enheter är redo för Microsoft 365 för företag.
    
2. [Använd installationsguiden för att konfigurera Microsoft 365 för företag](set-up.md)
    
    Om du **flyttar permanent från en lokal Active Directory till molnet**kan du gå till administrationscentret för Microsoft 365 och använda installationsguiden för att lägga till användarna manuellt, eller så kan du göra en engångssynkronisering med Azure AD Connect. Du kan göra det på två sätt: 
    
    - Om du också har en Exchange 2010-, Exchange 2013- eller Exchange 2016-server kan du [använda Minimal Hybrid för att snabbt migrera Exchange-postlådor till Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). De minimala hybridstegen inkluderar en engångssynkronisering av användare till Azure AD och e-postmigrering från lokalt till molnet. När e-postmigrering har slutförts inaktiveras katalogsynkroniseringen automatiskt när du använder den här metoden.
    
    - Använd katalogsynkroniseringsguiden för att synkronisera användarna till molnet. Följ stegen i [Konfigurera katalogsynkronisering för Microsoft 365 för](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) att slutföra den här processen. När du har synkroniserat användarna med molnet måste du [inaktivera katalogsynkronisering för Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Du måste också ge varje användare som har lagts till på det här sättet en licens till Microsoft 365 för företag. Du kan göra detta i [installationsguiden](set-up.md) eller [tilldela licenser till användare i Microsoft 365 för företag](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Förbered mobila enheter

Följ stegen i [Konfigurera mobila enheter för Microsoft 365 för företagsanvändare](set-up-mobile-devices.md) för att installera Office-appar på enheter och se till att de skyddas av Microsoft 365 för företag. 
  
### <a name="3-prepare-pcs"></a>3: Förbereda datorer

Administratörer kan förvälja inställningar för nya Windows 10-datorer med hjälp av [Windows AutoPilot](add-autopilot-devices-and-profile.md). Användare kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i det här avsnittet: [Konfigurera Windows-datorer för Microsoft 365 för företagsanvändare](set-up-windows-devices.md). För befintliga enheter kan användare **eventuellt** [flytta filer till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som är associerade med Windows-profilen till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 för företag för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag](manage-windows-devices.md) för att konfigurera detta. Den här metoden är att föredra och enheter i det här tillståndet kallas **Hybrid Azure AD-anslutna enheter**. 
  
Om du behåller en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina **Azure AD-anslutna enheter** åtkomst till dessa resurser genom att följa stegen här: [Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 för företag](access-resources.md).
  
  
## <a name="contact-support"></a>Kontakta support

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som Microsoft 365 för företag-administratör har du tillgång till vårt kundsupportteam: ** [Kontakta support för företagsprodukter - Administratörshjälp](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Snabbreferens

[Microsoft 365 för affärsdokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Hantera Microsoft 365 för företag](manage.md)[Migrera till Microsoft 365 för företag](migrate-to-microsoft-365-business.md)

[Microsoft 365 för företagsutbildningsvideor](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
