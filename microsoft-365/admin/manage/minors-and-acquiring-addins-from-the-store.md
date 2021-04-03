---
title: Minderåriga och köp av tillägg från Store
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Läs mer om dataskyddsförordningen (GDPR) som styr personuppgifter om minderåriga.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580924"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderåriga och köp av tillägg från Store

Allmänna Dataskyddsförordningen (GDPR) är en EU-bestämmelse som blir gällande den 25 maj 2018. Det ger användare rättigheter till och skydd av sina data. En av GDPR:s aspekter är att minderåriga inte kan få sina personliga data skickade till parter som deras föräldrar eller vårdnadshavare inte har godkänt. Vilken ålder som definierar en minderårig beror på var personen befinner sig.
  
Regioner som har lagstadgade föreskrifter om målsmans medgivande är bland annat USA, Sydkorea, Storbritannien och EU. En minderårig i sådana regioner kommer att blockeras (via Azure Active Directory) från att få nya Office-tillägg från Store och att köra tillägg som har förvärvats tidigare. För länder utan lagstadgade föreskrifter kommer det inte att finnas några begränsningar för nedladdning.
  
En användare har fastställt att han eller hon är minderårig baserat på data som angetts i Azure Active Directory. Organisationens administratör är ansvarig för att deklarera åldersgruppen och målsmans medgivande för användaren.
  
Om föräldern/målsman samtycker till att en minderårig använder ett specifikt tillägg kan organisationsadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har medgivande.
  
För att vara GDPR-kompatibel för minderåriga måste du se till att en av följande versioner av Office har distribuerats i skolan/organisationen.
 
 **För Word, Excel, PowerPoint och Project:** 

|**Plattform** <br/> |**Versionsnummer** <br/> |
|:-----|:-----|
|Microsoft 365-appar för företag (Aktuell kanal)  <br/> |9001.2138   <br/> |
|Microsoft 365-appar för företag (Halvårskanal för företag)  <br/> |8431.2159  <br/> |
|Office 2016 för Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 för Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 för Mac  <br/> |16.11.18020200  <br/> |
|Office på webben  <br/> |Uppgift saknas  <br/> |
   
 **För Outlook:** 
  
|**Plattform** <br/> |**Versionsnummer** <br/> |
|:-----|:-----|
|Outlook 2016 för Windows (MSI)  <br/> |Version nr TBD  <br/> |
|Outlook 2016 för Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 för Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile för iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile för Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Uppgift saknas  <br/> |

 **Krav för Office 2013**
  
Word, Excel och PowerPoint 2013 för Windows stöder samma minderåriga kontroller om Active Directory Authentication Library (ADAL) är aktiverat. Det finns två alternativ för efterlevnad, som beskrivs härnäst.
  
- **Aktivera ADAL.** I den här artikeln förklaras hur du aktiverar ADAL för Office 2013: Använda modern autentisering [i Microsoft 365 med Office-klienter.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>Du måste också ange registernycklarna för att aktivera ADAL enligt förklaras i Aktivera modern autentisering för [Office 2013 på Windows-enheter.](../security-and-compliance/enable-modern-authentication.md)<br/>Dessutom måste du installera följande uppdateringar för april för Office 2013:
    
  - [Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [Uppdatering för Office 2013 (KB4018333) den 3 april 2018](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL kan inte aktiveras.** Om du inte kan aktivera ADAL i Office 2013 rekommenderas du att använda Grupprincip för att stänga av Office Store för Office-klienter. Information om hur du inaktiverar appen för Office-inställningar finns [här.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))

## <a name="related-articles"></a>Relaterade artiklar

[Distribuera tillägg i administrations centret för](./manage-deployment-of-add-ins.md)

[Hantera tillägg i administrationscentret](./manage-addins-in-the-admin-center.md)
