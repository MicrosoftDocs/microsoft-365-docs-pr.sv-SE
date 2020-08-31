---
title: Minderåriga och förvärvade tillägg från Store
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig mer om de regler för förordning (General Data Protection GDPR) som styr person uppgifter om minderåriga.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306557"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderåriga och förvärvade tillägg från Store

Den allmänna data skydds förordningen (GDPR) är en europeisk unions förordning som träder i kraft 25 maj 2018. Den ger användare rättigheter att och skyddar sina data. En av fördelarna med GDPR är att minderåriga inte kan ha sina person uppgifter skickade till parter som inte har godkänt sin förälder eller vårdnadshavare. Den specifika åldern som definieras som en del beror på regionen där personen finns.
  
Regioner som har lagstadgade förordningar om föräldra godkännande inkluderar USA, Sydkorea, Storbritannien och Europeiska unionen. För dessa regioner blockeras en del (via Azure Active Directory) från att få nya Office-tillägg från Store och via tillägg som tidigare har skaffats. För länder utan lagstadgade bestämmelser finns inga nedladdnings begränsningar.
  
En användare anses vara en del baserad på data som anges i Azure Active Directory. Organisationens administratör ansvarar för att deklarera gruppen Legal ålder och förälderns medgivande.
  
Om föräldern/vårdnadshavare samtycker till en mindre med ett specifikt tillägg kan organisationens administratör använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har godkänt.
  
För att vara GDPR-kompatibel för minderåriga måste du kontrol lera att någon av följande versioner av Office distribueras i din skola/organisation.
 
 **För Word, Excel, PowerPoint och Project**: 

|**Plattform** <br/> |**Versions nummer** <br/> |
|:-----|:-----|
|Microsoft 365-appar för Enterprise (aktuell kanal)  <br/> |9001,2138   <br/> |
|Microsoft 365-appar för företag (halvårs kanal för Enterprise)  <br/> |8431,2159  <br/> |
|Office 2016 för Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 för Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 för Mac  <br/> |16.11.18020200  <br/> |
|Office för webben  <br/> |Saknas  <br/> |
   
 **För Outlook**: 
  
|**Plattform** <br/> |**Versions nummer** <br/> |
|:-----|:-----|
|Outlook 2016 för Windows (MSI)  <br/> |Bygg inget TBD  <br/> |
|Outlook 2016 för Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 för Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile för iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile för Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Saknas  <br/> |

 **Krav för Office 2013**
  
Word, Excel och PowerPoint 2013 för Windows stöder samma minderåriga om Active Directory-autentiseringsschemat (ADAL) är aktive rad. Det finns två alternativ för efterlevnad, enligt förklarat nästa.
  
- **Aktivera ADAL**. I den här artikeln förklaras hur du aktiverar ADAL för Office 2013: [använda den moderna verifierade Microsoft 365 med Office-klienter](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Du måste också ange register nycklarna för att aktivera ADAL enligt beskrivningen i [Aktivera modern auktorisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).<br/>Dessutom måste du installera följande uppdateringar för april för Office 2013:
    
  - [Beskrivning av säkerhets uppdateringen för Office 2013:10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, uppdatering för Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivera inte ADAL**. Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda grup princip för att inaktivera butiken för Office-klienter. Information om hur du inaktiverar programmet för Office-inställningar finns [här](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Relaterade artiklar

[Distribuera tillägg i administrations centret för](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Hantera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
