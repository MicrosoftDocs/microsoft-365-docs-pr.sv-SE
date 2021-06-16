---
title: Vanliga frågor och svar om centraliserad distribution
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Läs svaren på vanliga frågor om centraliserad distribution från administrationscentret för Microsoft 365.
ms.openlocfilehash: 210174d80a94df640245e1b80c5a7670e68952b1
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950005"
---
# <a name="centralized-deployment-faq"></a>Vanliga frågor och svar om centraliserad distribution

Centraliserad distribution är det rekommenderade sättet för Office 365-administratörer att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för användning av centraliserad distribution som beskrivs i den här artikeln.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hur vet jag om min organisation är konfigurerad för centraliserad distribution?  

Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-program för företag (och är inloggade på Office med inloggningsuppgifter för organisationen) och har Exchange Online-postlådor. Prenumerationskatalogen måste finnas i eller vara extern till Azure Active Directory.  
 
Centraliserad distribution stöds endast för onlinepostlådor. Den har inte stöd för distribution till lokala Exchange-postlådor.

Du kan använda [kompatibilitetskontrollen för centraliserad distribution för att](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   avgöra om din prenumeration är berättigad. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hur riktar du användartilldelningar för tillägg med centraliserad distribution?  

Centraliserad distribution har stöd för tilldelningar till enskilda användare, grupper och alla i klientorganisationen. Centraliserad distribution kan användas för användare i grupper på översta nivå eller grupper utan överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper. Centraliserad distribution ingår också i de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributionslistor och säkerhetsgrupper.  

Det är bättre att använda grupptilldelningar i stället för tilldelning av enskilda användare för att underlätta hanteringen.
 
Mer information finns i [Användar- och grupptilldelningar.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hur lång tid tar det innan tillägg visas för alla användare?  

Det kan ta upp till 24 timmar innan ett tillägg visas för alla användare. Det kan ta lika lång tid för tilläggsuppdateringar, ändringar från att aktivera eller inaktivera, eller att ta bort tillägg. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hur hanterar jag användaråtkomst som administratör till tillägg för min organisation?

För enkel distribution av tillägg till användare, grupper eller till hela organisationen rekommenderar vi att administratörer använder centraliserad distribution.

Mer information om hur du hanterar användaråtkomst finns i:
 - [Förhindra tilläggsnedladdningar genom att inaktivera Office Store för alla klienter (utom Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Ange de administratörer och användare som kan installera och hantera tillägg för Outlook](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Ger centraliserad distribution administratörer flexibiliteten att välja distributionsmetod för Outlook-tillägg?  

Ja. Centraliserad distribution ger administratörer möjlighet att välja någon av tre distributionsmetoder för Outlook-tillägg under distributionen:

**Fast (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och de kan inte ta bort det.  
 
**Tillgänglig** Användarna kan installera tillägget i Outlook genom att välja Start > Hämta fler tillägg och **> administratör hanterade.**
 
**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kan administratörer uppdatera verksamhetsbaserade tillägg?  

Ja. Administratörer kan ladda upp en ny manifestfil för att stödja metadataändringar för administratörs deployerade LOB-tillägg. Tillägget uppdateras nästa gång Office-programmen startas. Webbprogrammet kan ändras när som helst.  
 
Mer information finns [i verksamhets tillägg.](./manage-addins-in-the-admin-center.md)  

## <a name="can-admins-turn-off-add-ins"></a>Kan administratörer inaktivera tillägg?  

Ja. Administratörer kan aktivera eller inaktivera tillägg som de distribuerar för alla användare i administrationscentret för Microsoft.

Mer information finns i [Tilläggsstater](./manage-addins-in-the-admin-center.md#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kan administratörer ta bort eller ta bort tillägg?

Ja. Administratörer kan ta bort tillägg som de har distribuerat för alla användare från Microsofts administrationscenter.

Mer information finns i [Ta bort ett tillägg.](./manage-addins-in-the-admin-center.md#delete-an-add-in) 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution? 

Nej. Du kan för stunden inte distribuera betalda tillägg från Office Store med centraliserad distribution.  
 
Vi föreslår att ISV-utvecklaren tar del av det betalda tillägget för att begära en manifestfil eller en URL. Klientorganisationens administratör kan sedan distribuera tillägget som ett LOB-tillägg med hjälp av centraliserad distribution.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Vilken administratörsroll behöver jag för att hantera tillägg för min organisation?  

Global administratör är den rekommenderade rollen med fullständig åtkomst till livscykeln för hantering av tillägg. Om du är den person som köpte Microsoft 365 Business-prenumerationen är du global administratör. 
 
Din prenumeration levereras med en uppsättning administratörsroller som du kan tilldela andra användare i organisationen. Varje administratörsroll mappar till vanliga affärsfunktioner och ger personerna i organisationen behörighet att utföra särskilda uppgifter i administrationscentret för Microsoft 365.  
 
Mer information finns i Tilldela [administratörsroller.](../add-users/assign-admin-roles.md?view=o365-worldwide) 
