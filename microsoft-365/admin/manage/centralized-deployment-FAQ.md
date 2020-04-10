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
search.appverid:
- BCS160
- MET150
- MOE150
description: Granska svaren på vanliga frågor om centraliserad distribution från microsoft 365-administrationscentret.
ms.openlocfilehash: 39df2ec5a1671f800572bc845581bdbe2716d209
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209670"
---
# <a name="centralized-deployment-faq"></a>Vanliga frågor och svar om centraliserad distribution

Centraliserad distribution är det rekommenderade sättet för en Office 365-administratör att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för att använda centraliserad distribution enligt beskrivningen i den här artikeln.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hur vet jag om min organisation har konfigurerats för centraliserad distribution?  

Centraliserad distribution av tillägg kräver att användare använder Office 365 ProPlus (och är inloggade på Office med sina organisationsloggningsuppgifter) och har Exchange Online-postlådor. Din prenumerationskatalog måste antingen vara i eller federerade till Azure Active Directory.  
 
Centraliserad distribution stöds endast för onlinepostlådor. Det stöder inte distribution till lokala Exchange-postlådor.
 
Du kan använda [kompatibilitetskontrollen för centraliserad distribution i Office 365](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) för att avgöra om din prenumeration är kvalificerad. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hur inriktar du dig på tilläggsanvändartilldelningar med centraliserad distribution?  

Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klienten. Centraliserad distribution kan användas för användare i grupper på den högsta nivån eller grupper utan överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper. Centraliserad distribution är också en del av de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributionslistor och säkerhetsgrupper.  

Det är bättre att använda grupptilldelningar i stället för enskilda användartilldelning för enklare hantering.
 
Mer information finns i [Användar- och grupptilldelningar](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hur lång tid tar det för tillägg att visas för alla användare?  

Det kan ta upp till 24 timmar innan ett tillägg visas för alla användare. Det kan ta lika lång tid för tilläggsuppdateringar, ändringar från aktivera eller inaktivera eller tilläggsborttagningar. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hur hanterar jag användaråtkomst till tillägg för min organisation som administratör?

För enkel distribution av tillägg till användare, grupper eller till hela organisationen rekommenderar vi administratörer att använda centraliserad distribution.

Mer information om hur du hanterar användaråtkomst finns i </br>[Förhindra hämtning av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) och </br>[Ange de administratörer och användare som kan installera och hantera tillägg för Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Ger centraliserad distribution administratörer flexibiliteten att välja distributionsmetod för Outlook-tillägg?  

Ja. Centraliserad distribution ger administratörer flexibiliteten att välja en av tre distributionsmetoder för Outlook-tillägg under tilläggsdistributionen:

**Fast (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och de kan inte ta bort det.  
 
**Tillgänglig** Användare kan installera tillägget i Outlook genom att välja Hem > Få fler tillägg > Admin-hanterade.   
 
**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kan administratörer uppdatera LOB-tillägg (Line-of-Business)?  

Ja. Administratörer kan ladda upp en ny manifestfil för att stödja metadataändringar för administratörsbe distribuerade LOB-tillägg. Tillägget uppdateras nästa gång Office-programmen startas. Webbprogrammet kan ändras när som helst.  
 
Mer information finns [i tillägg för företagslinje](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).  

## <a name="can-admins-turn-off-add-ins"></a>Kan administratörer inaktivera tillägg?  

Ja. Administratörer kan aktivera eller inaktivera de tillägg som de distribuerar för alla användare från Microsofts administrationscenter.

Mer information finns [i Tilläggstillstånd](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kan administratörer ta bort eller ta bort tillägg?

Ja. Administratörer kan ta bort tillägg som de har distribuerat för alla användare från Microsofts administrationscenter.

Mer information finns [i Ta bort tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution? 

Nej. Du kan inte distribuera betalda tillägg från Office Store med centraliserad distribution just nu.  
 
Vi föreslår att du når ut till ISV-utvecklaren för det betalda tillägget för att begära en manifestfil eller en URL. Klientadministratören kan sedan distribuera tillägget som ett LOB-tillägg med centraliserad distribution.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Vilken administratörsroll behöver jag hantera tillägg för min organisation?  

Du måste ha rollen Global administratör för att hantera tillägg. Om du är den person som har köpt din Microsoft 365 för företag-prenumeration är du global administratör. 
 
Din prenumeration levereras med en uppsättning administratörsroller som du kan tilldela andra användare i organisationen. Varje administratörsroll mappar till vanliga affärsfunktioner och ger personer i organisationen behörighet att utföra specifika uppgifter i Microsoft 365-administrationscentret.  
 
Mer information finns i [Tilldela administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  