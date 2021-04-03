---
title: Aktiv användare i Användningsrapporter för Microsoft 365
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Läs mer om en aktiv användare av Microsoft 365 användningsanalyser, aktivitetsrapporter och införandemätvärden.
ms.openlocfilehash: 21663722d1a3850389db2ad79321daf363d314c6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579080"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Aktiv användare i Användningsrapporter för Microsoft 365

## <a name="active-user-in-usage-reports"></a>Aktiv användare i användningsrapporter

En aktiv användare av Microsoft 365-produkter för [Microsoft 365](usage-analytics.md) användningsanalyser och aktivitetsrapporterna i [administrationscentret](../activity-reports/activity-reports.md) definieras på följande sätt. 
  
|**Produkt**|**Definition av en aktiv användare**|**Kommentarer**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Alla användare som har utfört någon av följande åtgärder: Markera som läst, skicka meddelanden, skapa avtalade tider, skicka mötesförfrågningar, acceptera (preliminärt) eller avböja mötesförfrågningar, avboka möten.  <br/> |Ingen kalenderinformation representeras, det kommer att läggas till i en kommande uppdatering.  <br/> |
|SharePoint Online  <br/> |Alla användare som har interagerat med en fil genom att skapa, ändra, visa, ta bort, dela internt eller externt eller synkronisera till klienter på en webbplats eller som har visat en sida på en webbplats.  <br/> |Mätet måttet för aktiv användare för SharePoint Online i mallappen Microsoft 365 användningsanalys speglar endast användare som gjorde filaktivitet mot en SharePoint-gruppwebbplats eller en gruppwebbplats. Mallappen uppdateras för att synkronisera definitionen på samma sätt som den för användningsrapporterna i administrationscentret.  <br/> |
|OneDrive för företag  <br/> |Alla användare som har interagerat med en fil genom att skapa, ändra, visa, ta bort, dela internt eller externt eller synkronisera till klienter.  <br/> ||
|Yammer  <br/> |Alla användare som har läst, publicerat eller gillat ett meddelande i Yammer.  <br/> ||
|Skype för företag  <br/> |Alla användare som har deltagit i en peer to peer-session (inklusive snabbmeddelanden, ljud- och videosamtal, programdelning och filöverföringar) eller som har ordnat eller deltagit i en konferens.  <br/> ||
|Office  <br/> |Alla användare som har aktiverat sin Microsoft 365 Pro Plus-, Visio Pro- eller Project Pro-prenumeration på minst en enhet.  <br/> ||
|Microsoft 365-grupper  <br/> |Alla medlemmar i gruppen med postlådeaktivitet (om ett meddelande har skickats till gruppen)  <br/> |Den här definitionen kommer att förbättras med filaktivitet på gruppwebbplatser och Yammer-gruppaktivitet (filaktivitet på webbplats för grupper och meddelande som publiceras i Yammer-grupp som är associerad med gruppen.) Dessa data är för närvarande inte tillgängliga i mallappen Microsoft 365 användningsanalyser  <br/> |
|Microsoft Teams  <br/> |Alla användare som har deltagit i chattmeddelanden, privata chattmeddelanden, samtal, möten eller annan aktivitet. Annan aktivitet definieras som antalet andra teamaktiviteter av användaren, av vilken en del inkluderar, och inte begränsat till: gilla meddelanden, appar, arbeta med filer, söka, följa team och kanal och göra dem till favorit.  <br/> ||
   
## <a name="adoption-metrics"></a>Införandemätvärden

[Microsoft 365 användningsanalyser](usage-analytics.md) innehåller ytterligare användningsmått relaterade till aktiva användare för att visa införande av produkterna med tiden. Dessa mått är giltiga för månad, år och vald produkt och definieras enligt följande. 
  
|**Metrisk**|**Beskrivning**|
|:-----|:-----|
|EnabledUsers  <br/> |Antalet användare som är aktiverade för att använda produkten under månaden.  <br/> |
|ActiveUsers  <br/> |Antalet användare som är aktiva i månaden.  <br/> |
|MoMReturningUsers  <br/> |Antalet aktiva användare under månaden som också var aktiva den föregående månaden.  <br/> |
|FirstTimeUsers  <br/> |Antalet användare som varit aktiva under månaden som aldrig har använt tjänsten tidigare.  <br/> |
|CumulativeActiveUsers  <br/> |Antalet användare som är aktiva i månaden plus eventuell föregående månad.  <br/> |
|ActiveUsers(%)  <br/> |Procent av användare, avrundade till närmaste tiondel, aktiv i månaden, jämfört med antalet användare som aktiverats under den månaden.  <br/> |
|MoMReturningUsers(%)  <br/> |Procent av användare, avrundade till närmaste tiondel, som var aktiva i månaden som också var aktiva under den föregående månaden, jämfört med antalet aktiva användare.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers återställdes från och med 1 januari &amp; 2018 med införandet av Microsoft Teams.
  
