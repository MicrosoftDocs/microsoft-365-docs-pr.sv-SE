---
title: Komma igång med Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Lär dig att konfigurera Microsoft 365 Business.
ms.openlocfilehash: ed302a79d125ffc9c6203d902f437749a5b0f8d4
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575907"
---
# <a name="get-started-with-microsoft-365-business"></a>Komma igång med Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Vad är Microsoft 365 Business

Microsoft 365 Business är en omfattande uppsättning produktivitets- och samarbetsverktyg för företag. Outlook, Word, Excel och de andra Office-produkterna är alltid uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.
  
Microsoft 365 Business är avsett för upp till 300 licenser. Om du behöver fler licenser finns mer information i dokumentationen för [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986). 
  
## <a name="get-microsoft-365-business"></a>Skaffa Microsoft 365 Business

- Om du har en partner får denna Microsoft 365 Business: [Hämta Microsoft 365 Business från Microsoft-partnercenter](get-microsoft-365-business.md).
    
- Om du inte har en partner men vill skaffa Microsoft 365 Business, kan du [köpa det här](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Konfigurera Microsoft 365 Business

 **Översikt över Microsoft 365 Business Suite-uppsättningen**
  
I följande diagram beskrivs hur administratörer har konfigurerat Microsoft 365 Business. Dessutom beskrivs stegen för att förbereda Windows-datorer för Microsoft 365 Business. Du kan också lägga till nya enheter i administrationscentret för Microsoft 365 Business med [Windows AutoPilot](add-autopilot-devices-and-profile.md). Du kan använda AutoPilot för att installera och förkonfigurera nya enheter och på så sätt göra dem klara att användas i produktionen så snart en användare loggar in med sina Microsoft 365 Business-autentiseringsuppgifter.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Konfigurera Microsoft 365 Business (admin)

Logga in på [administrationscentret för Microsoft 365 Business](https://portal.office.com/adminportal/home) med dina autentiseringsuppgifter som global administratör, och följ instruktionerna nedan för att konfigurera Microsoft 365 Business. 
  
1. [Förutsättningar för att skydda data på enheter med Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Läs först förutsättningarna för att kontrollera att dina enheter är redo för Microsoft 365 Business.
    
2. [Konfigurera Microsoft 365 Business med hjälp av installationsguiden](set-up.md)
    
    Om du **flyttar permanent från en lokal Active Directory till molnet**, kan du antingen lägga till dina användare manuellt i Microsoft 365 Business Admin Center med hjälp av installationsguiden eller du kan göra en engångs synkronisering med Azure AD Connect. Du kan göra det på två sätt: 
    
  - Om du också har en server med Exchange 2010, Exchange 2013 eller Exchange 2016 kan du [använda minimal hybrid för att snabbt migrera Exchange-postlådor till Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Stegen för minimal hybridkonfiguration omfattar en engångssynkronisering av användare till Azure AD samt e-postmigrering från lokala resurser till molnet. När e-postmigreringen är klar inaktiveras katalogsynkroniseringen automatiskt när du använder den här metoden.
    
  - Använd Office 365-guiden för katalogsynkronisering för att synkronisera användarna till molnet. Följ stegen i [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) för att slutföra processen. När du har synkroniserat användarna med molnet måste du [Turn off directory synchronization for Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Du måste också ge var och en av användarna som har lagts till på det här sättet en licens för Microsoft 365 Business. Du kan göra detta i [installationsguiden](set-up.md)eller i [tilldela licenser till användare i Office 365 för företag](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Förbered mobila enheter

Följ stegen i[Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) att installera Office-appar på enheter och se till att de skyddas av Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: Förbered datorer

Administratörer kan i förväg välja inställningar för nya enheter Windows 10-datorer med hjälp av [Windows autopilot](add-autopilot-devices-and-profile.md). Användare kan konfigurera sina befintliga eller nya Windows 10-enheter genom att följa stegen i det här avsnittet: [Konfigurera Windows-datorer för Microsoft 365 företagsanvändare](set-up-windows-devices.md). För befintliga enheter kan **användare också**[Flytta filer till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som är associerade med Windows-profil till OneDrive.
  
Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) för att konfigurera detta. Det här är den bästa metoden och enheter i det här tillståndet kallas **hybrid Azure AD-anslutna enheter**. 
  
Om du behåller en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), kan du ge dina **Azure AD-anslutna enheter** åtkomst till dessa resurser genom att följa stegen här: [åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).
  
När du har konfigurerat Windows 10-datorer kan du [automatiskt installera Office](auto-install-or-uninstall-office.md) på enheterna. 
  
## <a name="contact-support"></a>Kontakta supporten

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som Microsoft 365 Business admin har du tillgång till vårt kundsupportteam, ** [kontakta supporten för företags produkter-admin hjälp](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Närliggande ämnen
[Microsoft 365 Business dokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Hantera Microsoft 365 Business](manage.md)[Migrera till Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

