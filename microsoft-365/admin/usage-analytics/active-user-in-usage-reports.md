---
title: Aktiv användare i Användningsrapporter för Microsoft 365
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Läs mer om en aktiv användare av Microsoft 365-användningsanalys, aktivitetsrapporter och införandemått.
ms.openlocfilehash: 2117bae32913ad713318c1df25be66d6ef6859e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631797"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Aktiv användare i Användningsrapporter för Microsoft 365

## <a name="active-user-in-usage-reports"></a>Aktiv användare i användningsrapporter

En aktiv användare av Microsoft 365-produkter för [Microsoft 365-användningsanalys](usage-analytics.md) och [aktivitetsrapporter i administrationscentret](../activity-reports/activity-reports.md) definieras på följande sätt. 
  
|**Produkt**|**Definition av en aktiv användare**|**Kommentarer**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Alla användare som har läst eller skickat ett e-postmeddelande.  <br/> |Ingen kalenderinformation representeras, det kommer att läggas till i en kommande uppdatering.  <br/> |
|SharePoint Online  <br/> |Alla användare som har interagerat med en fil genom att skapa, ändra, visa, ta bort, dela internt eller externt eller synkronisera till klienter på en webbplats eller som har visat en sida på en webbplats.  <br/> |Det aktiva användarmåttet för SharePoint Online i mallappen Microsoft 365 Usage Analytics återspeglar endast användare som har gjort filaktivitet mot en SharePoint-gruppwebbplats eller gruppwebbplats. Mallappen uppdateras för att synkronisera definitionen till samma som i användningsrapporterna i administrationscentret.  <br/> |
|OneDrive för företag  <br/> |Alla användare som har interagerat med en fil genom att skapa, ändra, visa, ta bort, dela internt eller externt eller synkronisera till klienter.  <br/> ||
|Yammer  <br/> |Alla användare som har läst, publicerat eller gillat ett meddelande i Yammer.  <br/> ||
|Skype för företag  <br/> |Alla användare som har deltagit i en peer to peer-session (inklusive snabbmeddelanden, ljud- och videosamtal, programdelning och filöverföringar) eller som har ordnat eller deltagit i en konferens.  <br/> ||
|Office  <br/> |Alla användare som har aktiverat sin Microsoft 365 Pro Plus-, Visio Pro- eller Project Pro-prenumeration på minst en enhet.  <br/> ||
|Microsoft 365-grupper  <br/> |Alla medlemmar i gruppen med postlådeaktivitet (om ett meddelande har skickats till gruppen)  <br/> |Den här definitionen förbättras med gruppwebbplatsfilaktivitet och Yammer-gruppaktivitet (filaktivitet på gruppwebbplats och meddelande som publiceras i Yammer-gruppen som är associerad med gruppen.) Dessa data är för närvarande inte tillgängliga i mallappen Microsoft 365 Usage Analytics  <br/> |
|Microsoft Teams  <br/> |Alla användare som har deltagit i chattmeddelanden, privata chattmeddelanden, samtal, möten eller annan aktivitet. Annan aktivitet definieras som antalet andra gruppaktiviteter av användaren varav vissa inkluderar, och inte begränsat till: gilla meddelanden, appar, arbeta med filer, söka, följa team och kanal och favorit dem.  <br/> ||
   
## <a name="adoption-metrics"></a>Antagande mått

[Microsoft 365-användningsanalys](usage-analytics.md) innehåller ytterligare implementeringsmått som är relaterade till aktiva användare för att visa hur produkterna används över tid. Dessa mått är giltiga för den månad, det år och den valda produkten och definieras enligt följande. 
  
|**Metriska**|**Beskrivning**|
|:-----|:-----|
|Aktiveradeanvändare  <br/> |Antal användare som har aktiverats för att använda produkten i månaden.  <br/> |
|ActiveUsers  <br/> |Antal användare som är aktiva i månaden.  <br/> |
|MoMReturningAnvändare  <br/> |Antal användare som är aktiva i månaden och som också var aktiva under föregående månad.  <br/> |
|FirstTimeUsers  <br/> |Antal användare som är aktiva under den månad som aldrig hade använt tjänsten tidigare.  <br/> |
|Kumulativa Aktivaanvändare  <br/> |Antal användare som är aktiva i månaden plus en föregående månad.  <br/> |
|ActiveUsers(%)  <br/> |Procent av användare, avrundade till närmaste tionde, aktiva i månaden jämfört med antalet användare som är aktiverade under den månaden.  <br/> |
|MoMReturningAnvändare(%)  <br/> |Procent av användare, avrundade till närmaste tionde, aktiva i månaden som också var aktiva under föregående månad jämfört med antalet aktiva användare.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers återställdes från och med 1 januari 2018 med införandet av Microsoft Teams.
  
