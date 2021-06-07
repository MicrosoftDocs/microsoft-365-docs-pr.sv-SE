---
title: Microsoft Productivity Score – innehållssamarbete
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Information om samarbetet i innehåll – personer får produktivitetspoäng.
ms.openlocfilehash: cca218d15af98925bf61bbb314cfd4d35aa0711a
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779741"
---
# <a name="content-collaboration--people-experiences"></a>Innehållssamarbete – upplevelser av personer

Produktivitetsresultatet ger insikter om organisationens digitala omvandlingsresa genom dess användning av Microsoft 365 och de teknikupplevelser som stöder den. Organisationens resultat återspeglar mätvärden för personer och teknikupplevelse och kan jämföras med riktmärken från organisationer som påminner om din. Kategorin för innehållssamarbete är en del av personernas måttupplevelser. Mer information finns i översikten [över Productivity Score](productivity-score.md) och [Microsofts sekretesspolicy.](https://privacy.microsoft.com/privacystatement)

## <a name="prerequisites"></a>Förutsättningar

För att komma igång med insikter om innehållssamarbete måste personer i organisationen licensieras för:

- OneDrive för företag
- SharePoint
- Exchange Online

Mer information finns i [tilldela licenser till användare.](../manage/assign-licenses-to-users.md)

 När användare har varit aktiva i ovanstående produkter minst en gång under de senaste 28 dagarna börjar du se insikterna.

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>Därför är din&#39;poäng för innehållssamarbete viktigt

En viktig del i den digitala transformationen är hur människor samarbetar i filer. Med ditt innehåll på Microsoft 365, kan personer komma åt, skapa, ändra och samarbeta om innehåll med andra personer från valfri plats. Efterforskningar visar att när personer samarbetar med onlinefiler sparar varje person i genomsnitt 100 minuter per vecka.

## <a name="how-we-calculate-the-content-collaboration-score"></a>Så här beräknar vi poäng för innehållssamarbete

Vi ger en primär insyn som innehåller de viktigaste måtten för samarbete med innehåll i organisationen. Sedan används ett poängramverk som anges nedan för dessa mått för att beräkna organisationens poäng.

> [!NOTE]
> Den 22 april 2021 ändrade vi hur värdet för medarbetare beräknas. Det här påverkar [den huvudsakliga](#primary-insight)insikten, den [viktigaste](#number-of-files-collaborated-on)insikten i filsamarbetet och det sätt som poäng för innehållssamarbete mäts. Den här ändringen hjälper till att minska bruset i data från icke-mänskliga agenter (eller robotar) från Microsoft och andra program från tredje part, vilket resulterar i ett mer exakt och användbart resultat.

### <a name="primary-insight"></a>Primär insyn

Microsoft OneDrive för företag och SharePoint hjälper användare att enkelt skapa, läsa och upptäcka sitt eget och delade innehåll i Microsoft 365 från olika enheter och program. De gör också att personer kan dela och samarbeta om innehåll på ett säkert sätt. Den primära insikten innehåller information från alla som kan använda OneDrive för företag och SharePoint. Dessutom bryts informationen om hur många personer som läser, skapar och samarbetar i innehåll som lagras i OneDrive för företag och SharePoint.

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="Primär information från poäng för kommunikationssamarbete.":::


De typer som anses vara till exempel Word-, Excel-, PowerPoint-, OneNote- och PDF-filer.

1. **Sidhuvud:** Visar hur många procent av alla i organisationen som har åtkomst till OneDrive eller SharePoint som samarbetar i innehåll.
2. **Brödtext:** Innehåller mer information om hur beteenden för att läsa och skapa filer online är kopplade till samarbete med filer.
3. **Visualisering (aktuell status):**
    - Vågräta staplar där de blå delarna representerar procentandelen personer som aktiverats för filsamarbete genom OneDrive eller  SharePoint som har varit **läsare,** skapare eller medarbetare på onlinefiler under de senaste 28 dagarna.

        De definieras på följande sätt:</br>
        **Läsare:** Personer som öppnar eller laddar ned onlinefiler i OneDrive eller SharePoint.</br>
        **Creators:** Personer som skapar, ändrar, laddar upp, synkroniserar, checkar in, kopierar eller flyttar online OneDrive eller SharePoint filer.</br>
        **Medarbetare:** Personer som samarbetar med onlinefiler genom att använda OneDrive eller SharePoint. Två personer är medarbetare om en av dem läser eller redigerar en online-Office-appen eller PDF-fil efter att den andra personen har skapat eller ändrat den, inom ett 28-dagarsfönster.

        > [!NOTE]
        > De filer som anses vara i visualiseringen är Word-, Excel-, PowerPoint-, OneNote- eller PDF-filer som är online och sparas i OneDrive eller SharePoint. 

    - Markera (täljare/nämnare) i bråket används för att beräkna procentandelen uttryckt i varje vågrätt fält.
    
      - **Läsare:**</br>
          - Täljare: Antal personer som har åtkomst till eller laddar ned onlinefiler i OneDrive eller SharePoint de senaste 28 dagarna</br>
          - Nämnare: Antalet personer som haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna</br>
      - **Creators:**</br>
        - Täljare: Antal personer som skapar, ändrar, laddar upp, synkroniserar, checkar in, kopierar eller flyttar onlinefiler i OneDrive eller SharePoint de senaste 28 dagarna</br>
        - Nämnare: Antalet personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna. </br> 
      - **Medarbetare:**</br>
        - Täljare: Antalet personer som har samarbetat med onlinefiler i OneDrive eller SharePoint de senaste 28 dagarna</br>
        - Nämnare: Antalet personer som har haft tillgång till i OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna

    - Peer benchmark value för var och en av läsarna, skaparna och kollegorna visas också som procent. Med andra ord visas värdet för skapare som en procentandel av antalet personer som har tillgång till OneDrive eller SharePoint.
    
1. **Länk till resurser:** Välj den här länken om du vill visa sorterade videoklipp och annat relaterat hjälpinnehåll.


#### <a name="trend-visualization-of-primary-insight"></a>Trendvisualisering av primär insyn

Diagrammet med trendvisualiseringar visar trendlinjen för mäteten av primärinsikter för läsare, skapare och medarbetare under de senaste 180 dagarna. Varje datapunkt i diagrammet är en mängd aktiviteter för de senaste 28 dagarna. Varje datapunkt för skapare ger antalet personer som har taggats som skapare under de senaste 28 dagarna för varje datum på x-axeln.

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="Diagram med trender för den viktigaste samarbetsinsikten.":::

### <a name="scoring-framework"></a>Poängramverk

Poäng för innehållssamarbete för organisationens åtgärder på en mängdnivå (organisation) oavsett om personer konsekvent läser, skapar eller samarbetar i Office-filer online, till exempel Word-, Excel-, PowerPoint-, OneNote- eller PDF-filer eller i OneDrive eller SharePoint.

Resultat anges inte på användarnivå.

## <a name="explore-how-your-organization-collaborates"></a>Utforska hur din organisation samarbetar

Vi ger dig även information som hjälper dig att se hur din organisation samarbetar om innehåll. Måtten bidrar inte direkt till ditt Produktivitetsresultat, utan hjälper dig att skapa en handlingsplan som en del av din digitala omvandling för att optimera hur människor arbetar.

### <a name="creating-files-in-onedrive-or-sharepoint"></a>Skapa filer i OneDrive eller SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="Diagram som visar antalet personer som skapar filer i OneDrive eller SharePoint":::

1. **Sidhuvud:** Höjdpunkter procentandel av de personer som är aktiva i Microsoft 365 Office program som skapar filer på OneDrive eller SharePoint.
2. **Brödtext:** Innehåller information om värdet av att skapa innehåll i OneDrive och SharePoint.
3. **Visualisering:** Fördelningen i visualiseringen visar i vilken utsträckning personer som använder Microsoft Office för att skapa filer i OneDrive och SharePoint enligt följande:
      - **OneDrive:** Den blå delen (färgad) av stapeln och bråket i stapeln representerar hur många personer som är aktiva i Office program som skapar innehåll OneDrive enligt följande:
        - Täljare: Antalet personer som skapar, ändrar, laddar upp, synkroniserar, checkar in, kopierar eller flyttar online Office filer i OneDrive de senaste 28 dagarna.</br>
        - Nämnare: Antalet personer som har tillgång till e-OneDrive eller SharePoint åtkomst till office-filer under de senaste 28 dagarna.
      - **SharePoint:** Den blå delen (färgad) av stapeln och bråket i stapeln representerar hur många personer som är aktiva i Office-program och skapar innehåll på SharePoint som:</br>
         - Täljare: Antalet personer som skapar, ändrar, laddar upp, synkroniserar, checkar in, kopierar eller flyttar Office-filer online (Microsoft Word-, Excel-, PowerPoint- eller OneNote-filer) på SharePoint de senaste 28 dagarna.</br>
        - Nämnare: Antalet personer som har tillgång till e OneDrive eller SharePoint har haft åtkomst Office de senaste 28 dagarna.

4. **Länk till resurser:** Välj den här länken om du vill visa hjälpinnehåll.

### <a name="use-of-attachments-in-email"></a>Användning av bifogade filer i e-post

:::image type="content" source="../../media/emailattachments.png" alt-text="Användning av e-postbilagor.":::

1. **Sidhuvud:** Höjdpunkter procentandel av personer som använder bifogade filer i e-postmeddelanden som inte har sparats i OneDrive eller SharePoint.
2. **Brödtext:** Innehåller information om värdet av att dela länkar till onlinefiler ur samarbets- och säkerhetsperspektiv.
3. **Visualisering:** Fördelningen i visualiseringen är avsedd att representera i vilken utsträckning personer som bifogar innehåll i e-postmeddelanden använder olika lägen (filer som inte finns på OneDrive eller SharePoint, länkar till onlinefiler och länkar som är inbäddade i e-postmeddelandet):
      - **Bifoga filer:** Den blå (färgade) delen av stapeln och bråket (täljare/nämnare) i fältet representerar procentandelen personer som använder bifogade filer i e-postmeddelanden.
        - Täljare: Antalet personer som bifogar filer i e-postmeddelanden som inte OneDrive eller SharePoint under de senaste 28 dagarna.
        - Nämnare: Antalet personer som har haft tillgång till e-Exchange och OneDrive, SharePoint, eller både och under de senaste 28 dagarna.
      - **Länkar till onlinefiler:** Den blå (färgade) delen av stapeln och bråket (täljare/nämnare) i fältet representerar procentandelen personer som använder bifogade filer och bifogar länkar till filer i e-postmeddelanden.
        - Täljare: Antalet personer som bifogar länkar till onlinefiler (sparas i OneDrive eller SharePoint) i e-postmeddelanden under de senaste 28 dagarna.
        - Nämnare: Antalet personer som har tillgång till e-Exchange OneDrive, SharePoint eller både och inom de senaste 28 dagarna.
      - **Bädda in länkar i e-postmeddelanden:** Den blå delen (färgad) av stapeln och bråket i stapeln representerar procentandelen personer som bäddar in länkar i brödtexten i e-postmeddelandena.
        - Täljare: Antalet personer som bäddar in länkar i brödtexten i e-postmeddelanden till onlinefiler (sparas i OneDrive eller SharePoint) under de senaste 28 dagarna.
        - Nämnare: Antalet personer som har tillgång till e-Exchange OneDrive, SharePoint eller både och inom de senaste 28 dagarna.
4. **Länk till resurser:** Välj den här länken om du vill visa hjälpinnehåll.

### <a name="sharing-of-online-files"></a>Delning av onlinefiler

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="Diagram som visar antalet personer som delar filer online.":::

1. **Sidhuvud:** Höjdpunkter procent av personer som har åtkomst till för de OneDrive eller SharePoint som delar filer externt.
2. **Brödtext:** Innehåller information om vilka administratörer&#39; möjlighet att ändra organisationens fildelningsinställningar för att göra det möjligt att samarbeta på det sätt som passar din organisation bäst.
3. **Visualisering:** Visar i vilken utsträckning personer som har åtkomst till OneDrive eller SharePoint delar filer internt eller externt:
      - **Externt:** Den blå (färgade) delen av stapeln och bråket (täljare/nämnare) i fältet representerar den procentandel av personer som har åtkomst till OneDrive eller SharePoint och delar filer externt.
        -  Täljare: Antalet personer som har delat filer externt med de senaste 28 dagarna
        - Nämnare: Det totala antalet personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
      - **Endast internt:** Den blå (färgade) delen av stapeln och bråket (täljare/nämnare) i fältet representerar den procentandel av personer som har åtkomst till OneDrive eller SharePoint och bara delar filer internt.
        - Täljare: Antalet personer som har delat filer internt bara under de senaste 28 dagarna
        - Nämnare: Det totala antalet personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
4. **Länk till resurser:** Välj den här länken om du vill visa hjälpinnehåll.

### <a name="number-of-files-collaborated-on"></a>Antalet filer som samarbetats på

:::image type="content" source="../../media/intensityofcollab.png" alt-text="Diagram som visar hur många filer som samarbetades mest.":::

1. **Sidhuvud:** Höjdpunkter procentandel av personer som har åtkomst till OneDrive eller SharePoint som samarbetar i 4 eller fler filer.
2. **Brödtext:** Innehåller information om hur andra kan utnyttja onlinefiler för bättre samarbete.
3. **Visualisering:** Visar en distribution av de personer som har åtkomst till OneDrive eller SharePoint, baserat på antalet filer som de samarbetar i. Detta visas i följande 4 kategorier (för var och en representerar den blå delen av stapeln och bråktalet den procentandel av personer som har åtkomst till OneDrive eller SharePoint som faller under den kategorin):
      - **Inget samarbete:**
        - Täljare: Antalet personer som inte samarbetar i några filer de senaste 28 dagarna.
        - Nämnare: Totalt antal personer som har tillgång till e OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
      - **Samarbete med 1–3 filer:**
        - Täljare: Antalet personer som samarbetar i 1–3 filer de senaste 28 dagarna.
        - Nämnare: Totalt antal personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
      - **Samarbete med 4–10 filer:**
        - Täljare: Antalet personer som samarbetar i 4–10 filer de senaste 28 dagarna.
        - Nämnare: Totalt antal personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
      - **Samarbete i 11 eller fler filer:**
        - Täljare: Antalet personer som samarbetar i 11 eller fler filer de senaste 28 dagarna.
        - Nämnare: Totalt antal personer som har haft tillgång till OneDrive eller SharePoint under minst 1 av de senaste 28 dagarna.
        
4. **Länk till resurser:** Välj den här länken om du vill visa hjälpinnehåll.

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>Nätverksprestandastyrkan för OneDrive och SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="Diagram som visar nätverksprestanda för OneDrive och SharePoint.":::

1. **Sidhuvud:** Höjdpunkter procentandel av alla enheter som testats som har dålig nätverksanslutning för att OneDrive och SharePoint. 
2. **Brödtext:** Innehåller information om varför nätverksanslutningsprestanda är viktig för samarbete. 
3. **Visualisering:** Visar en procentandel enheter med olika nivåer av nätverksanslutningsprestanda relaterad till OneDrive och SharePoint:
      - **81-100 (bäst)**: Den mörkgröna delen (färgad) i stapeln representerar det procenttal enheter som har bäst prestanda.
      - **61–80**: Den gröna (färgade) delen av stapeln representerar procentandelen enheter med nätverksprestandaresultat mellan 60–80. 
      - **41–60**: Den orange (färgade) delen av stapeln representerar procentandelen enheter med nätverksprestanda mellan 40 och 60. 
      - **21–40:** Den röda (färgade) delen av stapeln representerar procentandelen enheter med nätverksprestandaresultat mellan 20 och 40. 
      - **0–20**: Den mörkröda delen (färgad) i stapeln representerar procentandelen enheter med det sämsta nätverksprestandaresultatet mellan 0 och 20. 

## <a name="related-content"></a>Relaterat innehåll

[Microsoft 365 appens hälsa – teknikupplevelser](apps-health.md) (artikel)\
[Kommunikation – Personers upplevelser](communication.md) (artikel)\
[Möten – Upplevelser för personer](meetings.md) (artikel)\
[Mobility – People experiences](mobility.md) (artikel)\
[Sekretesskontroller för Productivity Score](privacy.md) (artikel)\
[Teamwork – Personliga upplevelser](teamwork.md) (artikel)
