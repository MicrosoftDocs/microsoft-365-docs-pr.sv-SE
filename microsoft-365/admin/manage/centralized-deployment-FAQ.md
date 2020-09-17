---
title: Vanliga frågor och svar om centraliserad distribution
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs vanliga frågor om centraliserad distribution från administrations centret för Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948694"
---
# <a name="centralized-deployment-faq"></a>Vanliga frågor och svar om centraliserad distribution

Centraliserad distribution är det rekommenderade sättet för en Office 365-administratör att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för centraliserad distribution enligt den här artikeln.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hur vet jag om min organisation är konfigurerad för centraliserad distribution?  

Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-appar för företag (och är inloggade på Office med deras organisations inloggnings uppgifter) och har Exchange Online-postlådor. Abonnemangs katalogen måste antingen vara i eller federerad till Azure Active Directory.  
 
Centraliserad distribution stöds endast för Online-postlådor. Den stöder inte distribution till lokala Exchange-postlådor.

Du kan använda [kompatibilitetskontrollen för centraliserad distribution](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   för att ta reda på om ditt abonnemang är kvalificerat. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hur kan du lägga in användar tilldelningar för användare med centraliserad distribution?  

Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klient organisationen. Centraliserad distribution kan användas för användare i grupper eller grupper som inte är överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper. Centraliserad distribution är också en del av de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributions listor och säkerhets grupper.  

Det är bättre att använda grupp tilldelningar i stället för enskilda användar uppgifter för att under lätta hanteringen.
 
Mer information finns i [användar-och grupp tilldelningar](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hur lång tid tar det för tillägg att visas för alla användare?  

Det kan ta upp till 24 timmar innan tillägget visas för alla användare. Det kan ta samma tid för tilläggs uppdateringar, ändringar som aktive ras eller inaktive ras. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hur hanterar jag användar åtkomst till tillägg för min organisation som administratör?

För enkel distribution av tillägg till användare, grupper eller i hela organisationen rekommenderar vi administratörer att använda centraliserad distribution.

Mer information om hur du hanterar användar åtkomst finns i:
 - [Förhindra hämtning av tillägg genom att stänga av Office Store på alla klienter (utom Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Ange administratörer och användare som kan installera och hantera tillägg för Outlook](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Kan centraliserad distribution ge administratörer flexibiliteten att välja distributions metod för Outlook-tillägg?  

Ja. Centraliserad distribution ger administratörer flexibiliteten att välja någon av tre distributions metoder för Outlook-tillägg under distribution av tillägg:

**Åtgärdat (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och kan inte tas bort.  
 
**Tillgänglig** Användare kan installera tillägget i Outlook genom att välja **Home > skaffa fler tillägg > administratörs hanterat**.
 
**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kan administratörer uppdatera LOB-tillägg (Line-of-Business)?  

Ja. Administratörer kan ladda upp en ny manifest fil för att stödja metadata ändringar för tillägg som distribueras med administratör. Tillägget uppdateras nästa gång Office-programmen startas. Webb programmet kan ändras när som helst.  
 
Mer information finns i avsnittet [line-of-Business](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).  

## <a name="can-admins-turn-off-add-ins"></a>Kan administratörer inaktivera tillägg?  

Ja. Administratörer kan aktivera och inaktivera tillägg som de distribuerar för alla användare från Microsoft Admin Center.

Mer information finns i [tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kan administratörer ta bort eller ta bort tillägg?

Ja. Administratörer kan ta bort tillägg som de distribuerat för alla användare från Microsoft Admin Center.

Mer information finns i [ta bort ett tillägg](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution? 

Nej. Du kan inte distribuera betalda tillägg från Office Store med centraliserad distribution för tillfället.  
 
Vi föreslår att få en manifest fil eller URL till ISV-utvecklare för det betalda tillägget. Klient organisationens administratör kan sedan distribuera tillägget som ett LOB-tillägg med centraliserad distribution.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Vilken administratörs roll behöver jag för att hantera tillägg för min organisation?  

Global admin är den rekommenderade rollen med fullständig åtkomst till livs cykeln för tilläggs hantering. Andra administratörs roller har begränsad åtkomst till livs cykeln för distribution av tillägg. Om du är den person som köpte ditt Microsoft 365 för företag-abonnemang är du den globala administratören. 
 
Ditt abonnemang kommer med en uppsättning administrativa roller som du kan tilldela till andra användare i organisationen. Varje administratörs roll mappar till vanliga affärs funktioner och ger användare i din organisations behörighet att utföra specifika uppgifter i administrations centret för Microsoft 365.  
 
Mer information finns i [tilldela administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  


