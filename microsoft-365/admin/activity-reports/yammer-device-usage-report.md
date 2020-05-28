---
title: Microsoft 365-rapporter i administrationscentret – användningsrapport för Yammer-enheter
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
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: 'Få yammer-enhetsanvändningsrapporten om vilka enheter användarna använder Yammer på. '
ms.openlocfilehash: 17fcf6c7d46988f0783b5097d3381b9bc08cbbe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387459"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365-rapporter i administrationscentret – användningsrapport för Yammer-enheter

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
I rapporten om användning av Yammer på enheter hittar du information om vilka enheter användarna använder Yammer på. Du kan visa antalet dagliga användare efter enhetstyp och antalet användare efter enhetstyp. Båda går att visa för en viss tidsperiod. Du kan också visa detaljerad information per användare.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter. 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Hur får jag fram rapporten om användning av Yammer på enheter?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj Användning av **Yammer-enhet** i listrutan **Välj en rapport** \> **Device usage**.
  
## <a name="interpret-the-yammer-activity-report"></a>Tolka Yammer-aktivitetsrapporten

Genom att titta på diagrammen **Användare** och **Fördelning** kan du få insyn i användarnas användning av Yammer på sina enheter. 
  
Rapporten om användning av enhet innehåller följande information:
  
- Använd dagflikarna för att visa aktivitetstrender för **användning av Yammer-enhet** under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades). 
    
- Varje rapport har ett datum för när rapporten skapades. Rapporterna visar normalt 24 till 48 timmars fördröjning från aktivitetstiden.
    
- Du kan visa diagrammet **Användare** för att se antalet dagliga användare efter enhetstyp.<br/>![Användare visar i användningsdiagrammet för Yammer-enheten](../../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![Användningsrapport för Yammer-enhet som visar användarvyn](../../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- Du kan visa diagrammet **Fördelning** för att se antalet användare efter enhetstyp.<br/>![Distributionsvy i yammerenhetens användningsrapport](../../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Användningsrapport för Yammer-enheter](../../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- Tabellen **Information** under diagrammet visar en uppdelning av användningen av Yammer på enheter per användare. 
    
    Du kan också lägga till och ta bort kolumner. De tillgängliga kolumnerna är:
    
  - **Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. 
    
    Det här rutnätet visar användare som har loggat in på Yammer med Microsoft 365-kontot eller som loggat in på nätverket med enkel inloggning.
    
  - **Visningsnamn** är användarens fullständiga namn. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. 
    
  - **Användartillstånd** är ett av tre värden: Aktiv, Borttagen eller Inaktiverad. 
    
    De här rapporterna visar data för aktiva, inaktiverade och borttagna användare. De avspeglar inte väntande användare eftersom väntande användare inte kan publicera, läsa eller gilla ett meddelande.
    
  - **Webben** anger om användaren har använt Yammer på webben. 
    
  - **Windows-telefon** anger om användaren har använt Yammer på en Windows-telefon. 
    
  - **Android-telefon** anger om användaren har använt Yammer på en Android-telefon. 
    
  - **iPhone** anger om användaren har använt Yammer på en iPhone. 
    
  - **iPad** anger om användaren har använt Yammer på en iPad. 
    
  - **Annan** anger om användaren har använt Yammer på en annan enhet än ovan. 
    
    Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)
    
- Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
    

