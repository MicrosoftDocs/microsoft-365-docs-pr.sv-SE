---
title: Microsoft 365 Rapporter i administrationscentret – Användning av e-postprogram
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
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Läs om hur du får rapporten om användning av e-postprogram för att få information om vilka e-postprogram som ansluter till Exchange Online och Outlook-versionen som användarna använder.
ms.openlocfilehash: f2a7b79a00b47896dac4427c532f85dccb931c60
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921990"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365 Rapporter i administrationscentret – Användning av e-postprogram

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användningsrapporten för e-postprogram kan du se hur många e-postprogram som ansluter till Exchange Online. Du kan även se versionsinformationen för Outlook-program som användarna använder, så att du kan följa upp med dem som använder versioner som inte stöds och installera versioner av Outlook som stöds.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Så här kommer du åt rapporten om e-postprogram

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.
2. Välj **Visa mer under** **E-postaktivitet**. 
3. I **listrutan** E-postaktivitet väljer du Ange Exchange  \> **E-postprogramsanvändning**.
  
## <a name="interpret-the-email-apps-report"></a>Tolka rapporten om e-postprogram

Du kan få information om aktiviteten i e-postappar genom att titta på **diagrammen** Användare **och** Klienter. 
  
![E-postklienter som används](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I **användningsrapporten för** e-postprogram kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |I vyn **Användare** visas antalet unika användare som har anslutit till Exchange Online med ett e-postprogram.  <br/> |
|4.  <br/> |I vyn **Appar** visas antalet unika användare per app under den valda tidsperioden.  <br/> |
|5.  <br/> |I **vyn** Versioner visas antalet unika användare för varje version av Outlook i Windows.  <br/> |
|6.  <br/> | I diagrammet **Användare** är Y-axeln det totala antalet unika användare som har anslutit till ett program någon dag under rapporteringsperioden.  <br/>  I diagrammet **Användare** är X-axeln antalet unika användare som har använt programmet under rapporteringsperioden.  <br/>  I diagrammet **Appar** är Y-axeln det totala antalet unika användare som har använt ett visst program under rapporteringsperioden.  <br/>  I diagrammet **Appar** är X-axeln listan över program i organisationen.  <br/>  I diagrammet **Versioner** är Y-axeln det totala antalet unika användare med en viss version av Outlook för skrivbordet. Om rapporten inte kan matcha versionsnumret för Outlook visas antalet som **Obestämbar**.  <br/>  I diagrammet **Versioner** är X-axeln listan över program i organisationen.  <br/> |
|7.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen.  <br/> |
|8.  <br/> | Du kan kanske inte se alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/> **Användarnamn** är namnet på e-postprogrammets ägare.  <br/> **Datum för senaste aktivitet** är det senaste datumet som användaren läst eller skickat ett e-postmeddelande.  <br/> **Mac Mail**, **Outlook för Mac** och **Outlook**, **Outlook Mobile** och **Outlook på webben** är exempel på e-postprogram som du kan ha i organisationen.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information **finns i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i Microsoft 365 administrationscenter](activity-reports.md).  <br/> |
|9.  <br/> |Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport om användning av e-postprogram – välj kolumner](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
