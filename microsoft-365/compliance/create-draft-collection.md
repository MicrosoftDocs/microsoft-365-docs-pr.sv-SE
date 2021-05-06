---
title: Skapa en utkastsamling
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En utkastsamling är en eDiscovery-sökning av inskannande och icke-förfallna datakällor i ett Advanced eDiscovery-fall som returnerar en sökberäkning som matchar sökfrågan i samlingen. Du kan granska sökstatistik, förhandsgranska ett urval av objekt och revidera och köra samlingen igen innan du åtar dig att spara resultaten i en granskningsuppsättning.
ms.openlocfilehash: 18f018a5e00f355c3f320a963135e76ecc51f086
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161827"
---
# <a name="create-a-draft-collection-in-advanced-ediscovery"></a>Skapa ett utkast i Advanced eDiscovery

När du har identifierat dokument dokument och andra icke-dokumentbaserade datakällor för ärendet är du redo att identifiera och hitta en uppsättning dokument som är relevanta. Det gör du genom att använda verktyget Samlingar för att söka efter relevant innehåll i datakällor. Det gör du genom att skapa en samling som söker i angivna datakällor efter innehåll som matchar dina sökvillkor. Du kan skapa ett utkast med en uppskattning av objekten, eller så kan du skapa en samling som automatiskt lägger till objekt i en granskningsuppsättning. När du skapar en utkastsamling kan du visa information om det uppskattade resultat som matchade sökfrågan, till exempel det totala antalet hittade objekt och storleken på de hittade objekten, de olika datakällorna där de hittades och statistik om sökfrågan. Du kan också förhandsgranska ett exempel på objekt som har returnerats av samlingen. Med hjälp av den här statistiken kan du ändra sökfrågan och köra utkastsamlingen igen för att begränsa resultatet. När du är nöjd med samlingsresultatet kan du bekräfta samlingen i en granskningsuppsättning. När du åtar dig att skapa ett utkast kommer de objekt som returneras av samlingen att läggas till i en granskningsuppsättning för granskning, analys och export.

## <a name="before-you-create-a-draft-collection"></a>Innan du skapar en utkastsamling

- Lägg till andrekterare och icke-tilläggsdatakällor till ärendet innan du skapar ett utkast till en samling. Detta krävs för att du ska kunna välja datakällor när du skapar ett utkast till en samling. Mer information finns i:

  - [Lägga till dokumentägare i ett ärende](add-custodians-to-case.md)

  - [Lägga till datakällor utan dokumentägare i ett ärende](non-custodial-data-sources.md)

- Du kan söka efter ytterligare datakällor (sådana som inte har lagts till i ärendet som förfallna platser eller platser där de inte finns tillgängliga) i en utkastsamling efter innehåll som kan vara relevant för ärendet. Dessa datakällor kan omfatta postlådor, SharePoint webbplatser och Teams. Om det här är relevant för ditt ärende ska du sammanställa en lista över dessa datakällor så att du kan lägga till dem i samlingen.

## <a name="create-a-draft-collection"></a>Skapa en utkastsamling

1. I Microsoft 365 säkerhets- och efterlevnadscenter öppnar Advanced eDiscovery och väljer sedan **fliken** Samlingar.

2. På sidan **Samlingar** väljer du **Ny samling**  >  **Standardsamling**.

3. Skriv ett namn (obligatoriskt) och en beskrivning (valfritt) för samlingen. När samlingen har skapats kan du inte ändra namnet, men du kan ändra beskrivningen.

4. Gör något **av följande på sidan** Autentiseringsdatakällor om du vill identifiera de autentiseringsdatakällor som du vill samla in innehåll från:

   - Klicka **på Välj vårdnadshavare om** du vill söka i specifika bibliotek som lagts till i ärendet. Om du använder det här alternativet visas en lista över de objekt som inte kan det. Välj en eller flera vårdnadshavare. När du har valt och lagt till programianerna kan du också välja specifika datakällor för att söka efter varje enskild person. Dessa datakällor som visas har angetts när den som var den som förser meddelandet lades till i ärendet.

   - Klicka på **växlingsknappen** Markera alla för att söka i alla objekt som lagts till i ärendet. När du väljer det här alternativet söks alla datakällor för alla objekt i biblioteken igenom.

5. På sidan **Icke-uppslagna datakällor** gör du något av följande för att identifiera de datakällor som inte är avsides och samlar in innehåll från:

   - Klicka **på Markera icke-förfallna datakällor** om du vill välja specifika datakällor som inte är aktuella och som har lagts till i ärendet. Om du använder det här alternativet visas en lista med datakällor. Markera en eller flera av dessa datakällor.

   - Klicka på **växlingsknappen** Markera alla om du vill markera alla icke-förfallna datakällor som lagts till i ärendet.

6. På sidan **Ytterligare datakällor** kan du välja andra postlådor och webbplatser att söka efter som en del av samlingen. Dessa typer av datakällor lades inte till som förfallna eller icke-förfallna dataplatser. Du har också två alternativ när du söker i ytterligare datakällor:

   - Om du vill söka efter en viss tjänst på alla innehållsplatser (Exchange-postlådor, SharePoint- och OneDrive-webbplatser eller Exchange gemensamma mappar) klickar du på motsvarande **Markera** alla i **kolumnen Status.** Med det här alternativet söker du efter alla innehållsplatser i den valda tjänsten.

   - Om du vill söka efter en  specifik innehållsplats för en tjänst klickar du på motsvarande Växlingsknapp Markera alla  i kolumnen **Status** och klickar sedan på **Användare,** grupper eller team (för Exchange-postlådor) eller Välj webbplatser för (SharePoint- och OneDrive-webbplatser) för att söka efter specifika innehållsplatser.

7. På sidan **Villkor** kan du skapa sökfrågan som används för att samla in objekt från de datakällor som du har identifierat på tidigare sidor i guiden. Du kan söka efter nyckelord, property:value-par eller använda en nyckelordslista. Du kan också lägga till olika sökvillkor för att begränsa samlingens omfattning. Mer information finns i [Skapa sökfrågor för samlingar.](building-search-queries.md)

8. På sidan **Spara som utkast eller lägg till i granskningsuppsättning** väljer du Spara samling som **utkast**.

   > [!NOTE]
   > Med det andra alternativet på den här sidan kan du samla in objekt och lägga till dem direkt i en granskningsuppsättning. I stället för att skapa en utkastsamling som du kan granska statistik för och förhandsgranska ett urval av samlingsresultatet hoppar det här alternativet över processen och lägger automatiskt till samlingen i en granskningsuppsättning. Om du väljer det andra alternativet för att lägga till samlingen i en granskningsuppsättning har du ytterligare inställningar att konfigurera, till exempel samla in hela chattkonversationstrådar i Microsoft Teams och Yammer och samla in molnbilagor (kallas även moderna bifogade *filer).* Mer information om de här inställningarna finns i [Spara ett utkast till en granskningsuppsättning](commit-draft-collection.md).

9. På sidan **Granska din** samling kan du granska och uppdatera de samlingsinställningar som du konfigurerat på föregående sidor.

   -  Sammanfattningsflik: Granska och ändra namn och beskrivning för samlingen, sökvillkoren för samlingen, ytterligare dataplatser och samlingstypen.

   - **Fliken** Källor: Granska och ändra uppslagna och icke-uppsmövade datakällor för samlingen.

10. Klicka **på Skicka** för att skapa utkastsamlingen. En sida visas som bekräftar att samlingen har skapats.

## <a name="what-happens-after-you-create-a-draft-collection"></a>Vad händer när du har skapat en utkastsamling

När du har skapat en utkastsamling visas den på aktuella sidan Samlingar och statusen visar att den pågår.  Ett jobb med **namnet Förbereda förhandsgranskning och** uppskattningar skapas och visas också på **sidan** Jobb för ärendet.

Under utkastsamlingsprocessen utför Advanced eDiscovery en sökberäkning med hjälp av de sökvillkor och datakällor som du angav i samlingen. Advanced eDiscovery förbereder också ett urval av objekt som du kan förhandsgranska. När samlingen är klar uppdateras följande kolumner och motsvarande värden **på** sidan Samling:

![Statustillstånd för en utkastsamling](../media/DraftCollectionStatus.png)

- **Status**: Anger status och typ av samling. Värdet Uppskattad **anger att** ett utkast har slutförts. Samma värde anger också att samlingen är ett utkast och att den inte har lagts till i en granskningsuppsättning. Värdet Committed **i kolumnen** Status **anger** att samlingen har lagts till i en granskningsuppsättning.

- **Uppskattningsstatus:** Anger statusen för de uppskattade sökresultaten och om sökberäkningarna och statistiken är klara att granskas. Värdet Lyckades **anger att** resultatet av utkastsamlingen är klart för granskning. När du först skickar in en utkastsamling visas värdet **Pågår** för att visa att samlingen fortfarande körs

- **Förhandsgranskningsstatus:** Anger statusen för de exempelobjekt som du kan förhandsgranska. Värdet Lyckades **anger att** objekten är klara för förhandsgranskning. När du först skickar in en utkastsamling visas värdet **Pågår** för att indikera att samlingen fortfarande körs.

## <a name="next-steps-after-a-draft-collection-is-complete"></a>Nästa steg när en utkastsamling är klar

När utkastsamlingen är klar kan du utföra olika uppgifter. För att utföra de flesta av dessa uppgifter går du till **fliken** Samlingar och klickar på namnet på utkastsamlingen för att visa den utfällade sidan.

![Utfällingssida för en utkastsamling](../media/DraftCollectionFlyoutPage.png)

Här är en lista över saker du kan göra från samlingssidan:

- Välj fliken **Sammanfattning** för att visa sammanfattningsinformation om samlingen och det uppskattade sökresultatet som returneras av samlingen. Det omfattar det totala antalet objekt och storleken på det uppskattade sökresultatet, antalet postlådor och webbplatser som innehåller sökresultat och sökvillkoren (om de används) som används för samlingens omfattning.

- Välj fliken **Datakällor** om du vill visa en lista över objekt som inte är inskanningsdatakällor som har sökts igenom i samlingen. Alla ytterligare innehållsplatser som har sökts visas under **Platser** **på** fliken Sammanfattning.

- Välj fliken **Sök i** statistik om du vill visa statistik om samlingen. Det här omfattar det totala antalet och storleken på objekten i varje tjänst (till exempel Exchange-postlådor eller SharePoint-webbplatser) och en villkorsrapport som visar statistik om antalet objekt som returneras av olika komponenter i sökfrågan som används av samlingen. Mer information finns i Insamling [av statistik och rapporter.](collection-statistics-reports.md)

- Klicka **på Granska exempel** (längst ned på den utfällade sidan) om du vill förhandsgranska ett exempel på de objekt som returneras av samlingen.

- Spara utkastsamlingen i en granskningsuppsättning (genom att klicka på   >  **Åtgärder, redigera samling**). Det innebär att du kör samlingen igen (med de aktuella inställningarna) och lägger till de objekt som returneras av samlingen i en granskningsuppsättning. Som tidigare förklarats kan du också konfigurera ytterligare inställningar (till exempel konversationstrådning och molnbaserade bifogade filer) när du lägger till samlingen i en granskningsuppsättning. Mer information och stegvisa instruktioner finns i Spara ett utkast till en uppsättning [granskare.](commit-draft-collection.md)

## <a name="manage-a-draft-collection"></a>Hantera en utkastsamling

Du kan använda alternativen i menyn **Åtgärder på** den utfällade sidan i en utkastsamling till att utföra olika hanteringsuppgifter.

![Alternativ på menyn Åtgärder för utkastsamling](../media/DraftCollectionActionsMenu.png)

Här är beskrivningar av hanteringsalternativen.

- **Redigera samling:** Ändra inställningarna för utkastsamlingen. När du har gjort ändringar kan du köra samlingen igen och uppdatera sökberäkningarna och statistiken. Som tidigare förklarats använder du det här alternativet för att bekräfta en utkastsamling i en granskningsuppsättning.  

- **Ta bort samling**: Ta bort en utkastsamling. Observera att när en utkastsamling har satts in i en granskningsuppsättning kan den inte tas bort.

- **Uppdatera uppskattningar:** Kör frågan igen (mot datakällorna) som anges i utkastsamlingen för att uppdatera sökuppskattningar och statistik.

- **Exportera som rapport:** Exporterar information om utkastsamlingen till en CSV-fil som du kan ladda ned till din lokala dator. Exportrapporten innehåller följande information:

  - Identiteten för varje innehållsplats som innehåller objekt som matchar sökfrågan i utkastsamlingen. De här platserna är vanligtvis postlådor eller webbplatser.
  
  - Det totala antalet objekt på varje innehållsplats.
  
  - Den totala storleken (i byte) på objekten på varje innehållsplats.

  - Tjänsten (till exempel Exchange eller SharePoint) där innehållsplatsen finns.

- **Kopiera samling:** Skapa en ny utkastsamling genom att kopiera inställningarna från en befintlig samling. Du måste använda ett annat namn för den nya samlingen. Du kan också ändra inställningarna innan du skickar in den nya samlingen. När du har skickat in den körs sökfrågan och nya uppskattningar och statistik genereras. Det här är ett bra sätt att snabbt skapa ytterligare utkastsamling och sedan ändra valda inställningar efter behov, samtidigt som informationen i den ursprungliga samlingen bevaras. På så sätt kan du också enkelt jämföra resultatet av två liknande samlingar.

> [!NOTE]
> När en utkastsamling har angetts för en granskningsuppsättning kan du bara kopiera samlingen och exportera en rapport.
