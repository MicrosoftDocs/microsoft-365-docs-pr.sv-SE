---
title: Minderåriga och förvärva tillägg från Store
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
description: Läs mer om de allmänna dataskyddsförordningen (GDPR) som reglerar minderårigas personuppgifter.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103118"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderåriga och förvärva tillägg från Store

Den allmänna dataskyddsförordningen (GDPR) är en EU-förordning som träder i kraft den 25 maj 2018. Det ger användarna rätt till och skydd av sina uppgifter. En av aspekterna av GDPR är att minderåriga inte kan få sina personuppgifter skickade till parter som deras förälder eller vårdnadshavare inte har godkänt. Den specifika ålder som definieras som minderårig beror på den region där personen är belägen.
  
Regioner som har lagstadgade bestämmelser om föräldrarnas samtycke inkluderar USA, Sydkorea, Storbritannien och Eu ropeiska unionen. För dessa regioner blockeras en minderårig (via Azure Active Directory) från att hämta nya Office-tillägg från Store och köra tillägg som tidigare har förvärvats. För länder utan lagstadgade bestämmelser kommer det inte att finnas några nedladdningsrestriktioner.
  
En användare bedöms vara en minderårig baserat på data som anges i Azure Active Directory. Organisationsadministratören ansvarar för att deklarera den juridiska åldersgruppen och föräldrarnas samtycke för den användaren.
  
Om föräldern/vårdnadshavaren samtycker till en minderårig med hjälp av ett specifikt tillägg kan organisationsadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har medgivande.
  
För att vara GDPR-kompatibel för minderåriga måste du se till att en av följande versioner av Office distribueras i din skola/organisation.
 
 **För Word, Excel, PowerPoint och Project:** 

|**Plattform** <br/> |**Bygg nummer** <br/> |
|:-----|:-----|
|Microsoft 365-appar för företag (aktuell kanal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Halvårsvis Företagskanal)  <br/> |8431.2159  <br/> |
|Office 2016 för Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 för Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 för Mac  <br/> |16.11.18020200  <br/> |
|Office för webben  <br/> |EJ TILLÄMPLIGT  <br/> |
   
 **För Outlook:** 
  
|**Plattform** <br/> |**Bygg nummer** <br/> |
|:-----|:-----|
|Outlook 2016 för Windows (MSI)  <br/> |Skapa ingen TBD  <br/> |
|Outlook 2016 för Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 för Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile för iOS  <br/> |2.75.0  <br/> |
|Outlook mobile för Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |EJ TILLÄMPLIGT  <br/> |

 **Office 2013-krav**
  
Word, Excel och PowerPoint 2013 för Windows stöder samma mindre kontroller om Active Directory Authentication Library (ADAL) är aktiverat. Det finns två alternativ för efterlevnad, som förklaras härnäst.
  
- **Aktivera ADAL**. I den hÃ¤r artikeln beskrivs hur du aktiverar ADAL för Office 2013: [HÃ¤r Ã¤ger microsoft 365 modern autentisering med Office-klienter](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Du måste också ange registernycklarna så att de aktiverar ADAL enligt beskrivningen i [Aktivera modern autentisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).<br/>Dessutom måste du installera följande apriluppdateringar för Office 2013:
    
  - [Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, uppdatering för Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivera inte ADAL**. Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda Grupprincip för att stänga av Store för Office-klienterna. Information om hur du inaktiverar appen för Office-inställningar finns [här](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Relaterade artiklar

[Distribuera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Hantera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
