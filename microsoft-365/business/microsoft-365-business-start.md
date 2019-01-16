---
title: Komma igång med Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Lär dig att konfigurera Microsoft 365 Business.
ms.openlocfilehash: 1c4adc64f62f7d4ae5038603804aa10e48d8a6e1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983799"
---
# <a name="get-started-with-microsoft-365-business"></a>Komma igång med Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Vad är Microsoft 365 Business

Microsoft 365 Business är en omfattande uppsättning produktivitets- och samarbetsverktyg för företag. Outlook, Word, Excel och de andra Office-produkterna är alltid uppdaterade. Du kan skydda dina arbetsfiler på alla dina iOS-, Android- och Windows 10-enheter med säkerhet i företagsklass som är enkel att hantera.
  
Microsoft 365 Business är avsett för upp till 300 licenser. Om du behöver fler licenser finns mer information i dokumentationen för [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986). 
  
## <a name="get-microsoft-365-business"></a>Skaffa Microsoft 365 Business

- Om du har en partner får denna Microsoft 365 Business: [Hämta Microsoft 365 Business från Microsoft-partnercenter](get-microsoft-365-business.md).
    
- Om du inte har en partner men vill skaffa Microsoft 365 Business, kan du [köpa det här](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Konfigurera Microsoft 365 Business

 **Översikt över Microsoft 365 Business Suite ställa in**
  
Följande diagram beskriver hur administratörer konfigurera Microsoft 365 Business. Här beskrivs också hur du förbereder Windows-datorer för Microsoft 365 Business. Du kan också lägga till nya enheter till Microsoft 365 Business admin Center med [Windows AutoPilot](add-autopilot-devices-and-profile.md). Du kan använda AutoPilot för att ställa in och konfigurera nya enheter före förbereda dem för produktiv användning när en användare loggar in med sina Microsoft 365 Business-autentiseringsuppgifter.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: ställa in Microsoft 365 Business (Admin)

Logga in på [administrationscentret för Microsoft 365 Business](https://portal.office.com/adminportal/home) med dina autentiseringsuppgifter som global administratör, och följ instruktionerna nedan för att konfigurera Microsoft 365 Business. 
  
1. [Förutsättningar för att skydda data på enheter med Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Läs först förutsättningarna för att kontrollera att dina enheter är redo för Microsoft 365 Business.
    
2. [Konfigurera Microsoft 365 Business med hjälp av installationsguiden](set-up.md)
    
    Om du **flyttar permanent från en lokal Active Directory till molnet**, du kan antingen lägga till användarna manuellt i Microsoft 365 Business administratörscenter med hjälp av guiden eller kan du göra en enstaka synkronisering med Azure AD Connect. Det finns två sätt att göra detta: 
    
  - Om du har en Exchange 2010, Exchange 2013 och 2016 för Exchange server, kan du [Använda Minimal Hybrid snabbt migrera Exchange-postlådor till Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Minimal hybrid stegen omfattar en enstaka användare till Azure AD-synkronisering samt e-migrering från lokal till molnet. När e-migreringen är klar, inaktiveras synkronisering directory automatiskt när du använder den här metoden.
    
  - Använd Office 365-guiden för katalogsynkronisering för att synkronisera användarna till molnet. Följ stegen i [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) för att slutföra processen. När du har synkroniserat användarna med molnet måste du [Turn off directory synchronization for Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Du måste även ge varje användare som har lagts till på så sätt en licens för Microsoft 365 verksamhet. Du kan göra detta i [installationsguiden](set-up.md)eller [tilldela licenser till användare i Office 365 för företag](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: förbereda för mobila enheter

Följ anvisningarna i[Konfigurera mobila enheter för Microsoft 365 Business användare](set-up-mobile-devices.md) att installera Office apps på enheter och se till att de är skyddade med Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: förbereda datorer

Administratörer kan före Välj inställningar för nya enheter Windows 10-datorer med hjälp av [Windows AutoPilot](add-autopilot-devices-and-profile.md). Användare kan ställa in sina befintliga eller nya Windows 10-enheter genom att följa instruktionerna i det här avsnittet: [Konfigurera Windows-datorer för Microsoft 365 företagsanvändare](set-up-windows-devices.md). För befintliga enheter kan användare också **Om du vill**[Flytta filerna till OneDrive för företag](move-files-to-onedrive.md). De kan också använda verktyg från tredje part för att flytta filer som hör till Windows-profil till OneDrive.
  
Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) att ställa in. Detta är den bästa metoden och enheter i det här tillståndet kallas **Hybrid Azure AD anslutna enheter**. 
  
Om du behåller en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), du kan ge din **Azure AD-anslutna enheter** åtkomst till dessa resurser genom att följa instruktionerna här: [Access lokal resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).
  
När du har ställt in Windows 10-datorer kan du [installera Office automatiskt](auto-install-or-uninstall-office.md) till enheter. 
  
## <a name="contact-support"></a>Kontakta supporten

 **Om du behöver kontakta supporten:**
  
- Kontakta din partner.
    
- Som en Microsoft 365 Business-administratör har du åtkomst till supportteamet kunden ** [Kontakta support för business-produkter - Admin-hjälp](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Närliggande avsnitt
[Microsoft 365 Business dokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Hantera Microsoft 365 Business](manage.md)[Migrera till Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

