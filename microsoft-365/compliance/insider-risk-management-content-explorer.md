---
title: Insider-riskhantering – Innehållsutforskaren
description: Läs mer om Insider-riskhantering Innehållsutforskaren i Microsoft 365
keywords: Microsoft 365, insider-riskhantering, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 44a17471f1e2ba92d0099f62b95dec8d0e56a224
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "52162806"
---
# <a name="insider-risk-management-content-explorer"></a>Insider-riskhantering – Innehållsutforskaren

Med **Insider-riskhanteringsinnehållsutforskaren** kan användare som tilldelats rollen *Insider-riskhanteringsrollen* undersöka kontext och information om innehåll som associeras med aktivitet i aviseringar. Ärendedata i Innehållsutforskaren uppdateras dagligen för att omfatta ny aktivitet. För alla aviseringar som bekräftas i ett ärende arkiveras kopior av data och meddelandefiler som en ögonblicksbild av objekten, samtidigt som de ursprungliga filerna och meddelandena i lagringskällorna behålls. Vid behov kan ärendedatafiler exporteras som en PDF-fil (Portable Document File) eller i det ursprungliga filformatet.

Kopieringen av data och meddelanden är transparent för användaren som är kopplad till aviseringen och för ägaren av innehållet. För nya fall tar det normalt ungefär en timme innan innehåll fylls i i Innehållsutforskaren. I fall med stora mängder innehåll kan det ta längre tid att skapa en ögonblicksbild. Om innehållet fortfarande läses in i Innehållsutforskaren visas en förloppsindikator som visar slutförandeprocenten.

I vissa fall kanske data som är associerade med ett ärende inte är tillgängliga som en ögonblicksbild för granskning i Innehållsutforskaren. Det här kan inträffa när ärendedata har tagits bort eller flyttats, eller när ett tillfälligt fel inträffar vid bearbetningen av ärendedata. Om så är fallet väljer **du** Visa filer i varningslisten för att visa filnamn, sökväg och orsak till felet för varje fil. Vid behov kan den här informationen exporteras till en .csv (kommaavgränsade värden).

Om innehållet omfattar informationsbehörigheter för rättighetshantering behålls de här behörigheterna för det kopierade innehållet och användare som tilldelats rollen *Insider-riskhanteringsrollen* måste ha dessa behörigheter och rättigheter om de behöver öppna och visa filerna. Varje fil och meddelande tilldelas automatiskt ett unikt fil-ID i insider-riskhanteringsfall i hanteringssyfte. Dokument som är kopplade till enhetsindikatoraktiviteter ingår inte i Innehållsutforskaren.

>[!Note]
>Innehållsutforskaren innehåller aktiviteter som är Microsoft Office filer. Aktiviteter på webbplatsnivå, till exempel när en SharePoint webbplats tas bort eller om webbplatsbehörigheter ändras, inte ingår i Innehållsutforskaren.

## <a name="column-options"></a>Kolumnalternativ

För att göra det enklare för riskanalytiker och experter att granska registrerade data och meddelanden och granska sammanhanget för ärendet ingår flera filtrerings- och sorteringsverktyg i Innehållsutforskaren. För grundläggande sortering stöder **kolumnerna Datum** **och Filklass** sortering med hjälp av kolumnrubrikerna i fönstret för innehållskö. Andra kökolumner är tillgängliga att lägga till i vyn för att ge olika pivoter i filer och meddelanden.

Om du vill lägga till eller ta bort kolumnrubriker för innehållskön använder du kontrollen **Redigera** kolumner och väljer något av följande kolumnalternativ. Kolumnerna mappas till de vanliga villkoren för e-post och dokumentegenskap som stöds i Innehållsutforskaren och som anges senare i den här artikeln.

| **Kolumnalternativ** | **Beskrivning** |
|:------------------|:----------------|
| **Författare** | Redigeringsfältet från Office, som finns kvar om ett dokument kopieras. Om en användare till exempel skapar ett dokument och e-postmeddelanden till någon annan som sedan laddar upp det till SharePoint, behåller dokumentet den ursprungliga författaren. |
| **Hemlig kopia** | Tillgängligt för e-postmeddelanden, användarna i meddelandefältet Hemlig kopia. |
| **Kopia** | Tillgängligt för e-postmeddelanden, användarna i fältet Kopia. |
| **Sammansatt sökväg** | Läsbar väg för en person som beskriver objektets källa. |
| **Konversations-ID** | Konversations-ID från meddelandet. |
| **Konversationsindex** | Konversationsindex från meddelandet. |
| **Skapat tid** | Tidpunkten då filen eller e-postmeddelandet skapades. |
| **Datum (UTC)** | För e-post: det datum då ett meddelande togs emot av en mottagare eller skickades av avsändaren. För dokument: det datum då ett dokument senast ändrades. Datumet är i UTC (Coordinated Universal Time).|
| **Dominant tema** | Dominant tema som beräknats för analys. |
| **ID för e-postuppsättning** | Grupp-ID för alla meddelanden i samma e-postuppsättning. |
| **Familje-ID** | Familje-ID grupperar alla objekt; för e-post innehåller den här kolumnen meddelandet och alla bifogade filer; för dokument innehåller den här kolumnen dokumentet och eventuella inbäddade objekt. |
| **Filklass** | För innehåll från SharePoint och OneDrive: **Dokument**; för innehåll från Exchange: **E-post** eller **Bifogad fil**. |
| **Fil-ID** | Dokumentidentifierare som är unik i det aktuella ärendet. |
| **Filtypsikon** | Filnamnstillägget för en fil. Till exempel docx, ett, pptx eller xlsx. Det här fältet har samma egenskap som webbplatsegenskapen FileExtension. |
| **ID** | GUID-identifieraren för filen. |
| **Oföränderligt ID** | Oföränderligt ID som lagrat i Office 365. |
| **Inkluderande typ** | Inkluderande typ som beräknas för **analys: 0** – inte inkluderande; **1** – inklusive; **2** – inklusive minus; **3 inklusive** kopia. |
| **Senast ändrad** | Datumet då ett dokument senast ändrades. |
| **Markerat som representativt** | Ett dokument från varje uppsättning med exakta dubbletter markeras som representanter. |
| **Meddelande sort** | Den typ av e-postmeddelande du vill söka efter. Möjliga värden: kontakter, dokument, e-post, externa data, fax, snabbmeddelanden, journaler, möten, Microsoft Teams (returnerar objekt från chattar, möten och samtal i Microsoft Teams), anteckningar, inlägg, RSS-feeds, uppgifter, röstbrevlåda |
| **Deltagare** | Lista över alla deltagare i ett meddelande. till exempel Avsändare, Till, Kopia, Hemlig kopia. |
| **Pivot-ID** | ID för en pivot. |
| **Mottaget** | Datumet då ett e-postmeddelande togs emot av en mottagare. Det här fältet har samma egenskap som egenskapen Mottagen e-post. |
| **Mottagare** | Alla mottagarfält i ett e-postmeddelande. De här fälten är Till, Kopia och Hemlig kopia. |
| **Representativt ID** | Numerisk identifierare för varje uppsättning med exakta dubbletter. |
| **Avsändare** | Avsändaren av ett e-postmeddelande. |
| **Avsändare/författare** | För e-post: den person som skickade ett meddelande. För dokument: den person som du citerar i fältet Författare Office dokument. Du kan skriva mer än ett namn, avgränsade med kommatecken. Två eller flera värden är logiskt sammankopplade av operatorn ELLER. |
| **Typer av känslig information** | De typer av känslig information som identifieras i innehållet. |
| **Känslighetsetiketter** | Känslighetsetiketterna som tillämpas på innehållet. |
| **Skickat** | Datumet då ett e-postmeddelande skickades av avsändaren. Det här fältet har samma egenskap som egenskapen Skickad e-post. |
| **Storlek** | Storleken på objektet (i byte) för både e-post och dokument. |
| **Ämne** | Texten i ämnesraden i ett e-postmeddelande. |
| **Ämne/rubrik** | För e-post: texten på ämnesraden i ett meddelande. För dokument, dokumentets rubrik. Som tidigare förklarats är titelegenskapen metadata angivna Microsoft Office dokument. Du kan skriva namnet på fler än ett ämne/en rubrik, avgränsade med kommatecken. Två eller flera värden är logiskt sammankopplade av operatorn ELLER. |
| **Listan Teman** | Lista över teman som beräknas för analys. |
| **Title** | Dokumentets rubrik. Titelegenskapen är metadata som anges i Office dokument. Den är inte samma som filnamnet i dokumentet. |
| **Till** | Mottagaren av ett e-postmeddelande i fältet Till. |

## <a name="filtering"></a>Filtrera

Du kan använda ett eller flera filter för att begränsa omfattningen av en sökning och returnera en mer förfinad uppsättning resultat. Om du vill ange ett filter **väljer** du Filter högst upp i innehållskön. Många filter innehåller ytterligare filtreringsalternativ för att begränsa resultatet som returneras av filtret. Filtret Datum innehåller *till exempel* kontroller för att konfigurera *startdatum* *och slutdatum* för **filtret** Datum. Välj ett eller flera filterobjekt i följande kategorier:

### <a name="common-filters"></a>Vanliga filter

| **Filter** | **Beskrivning** |
|:---------------------|:----------------|
| **Datum (UTC)** | För e-post: det datum då ett meddelande togs emot av en mottagare eller skickades av avsändaren. För dokument: det datum då ett dokument senast ändrades. |
| **Avsändare/författare** | För e-post: den person som skickade ett meddelande. För dokument: den person som du citerar *i fältet Författare* Office dokument. Du kan skriva mer än ett namn, avgränsade med kommatecken. |
| **Source** | Platsen för dokumentet i organisationen. Till exempel en specifik SharePoint webbplatsplats. |
| **Ämne/rubrik** | För e-post: texten på ämnesraden i ett meddelande. För dokument, dokumentets rubrik. Titelegenskapen i dokument är metadata som anges i Microsoft Office dokument. Du kan skriva namnet på fler än ett ämne/en rubrik, avgränsade med kommatecken. Två eller flera värden är logiskt sammankopplade av operatorn ELLER. |

### <a name="email-filters"></a>E-postfilter

| **Filter** | **Beskrivning** |
|:---------------------|:----------------|
| **Hemlig kopia** | Fältet Hemlig kopia i ett e-postmeddelande. |
| **Kopia** | Fältet Kopia i ett e-postmeddelande. |
| **Har bifogad fil** | Anger om ett meddelande har en bifogad fil. Värden anges som **sanna** eller **falska.** |
| **Bifogad fil i e-post** | Om dokumentet är en bifogad fil visas värdet som **Ja.** |
| **Är inbäddat dokument** | Om dokumentet är inbäddat i e-postmeddelandet visas värdet som **Ja.** |
| **Är bifogad fil i bifogad fil** | Om dokumentet är en bifogad fil i e-postmeddelandet visas värdet som **Ja.** |
| **Deltagare** | Alla personer (fält) i ett e-postmeddelande. De här fälten är Från, Till, Kopia och Hemlig kopia. |
| **Mottaget** | Datumet då ett e-postmeddelande togs emot av en mottagare. |
| **Mottagardomäner** | Lista över alla mottagares domäner för ett meddelande. |
| **Mottagare** | Mottagarna av e-postmeddelandet. |
| **Avsändare** | Fältet Sender (From) för meddelandetyper.  Formatet är **DisplayName \<SmtpAddress>**. |
| **Avsändningsdomän** | Domän för avsändaren. |
| **Till** | Fältet Till i ett e-postmeddelande. |
| **Unik i e-postuppsättning** | False om det finns en dubblett av den bifogade filen i dess e-postuppsättning. |

## <a name="document-filters"></a>Dokumentfilter

| **Filter** | **Beskrivning** |
|:---------------------|:----------------|
| **Efterlevnadsetiketter** | Efterlevnadsetiketter som används i Office 365. |
| **Skapat tid (UTC)** | Datum och tid då filen eller e-postmeddelandet skapades. Datum och tid finns i UTC (Coordinated Universal Time). |
| **Datum för senaste ändring (UTC)** | Datumet då ett dokument senast ändrades. Datum och tid finns i UTC (Coordinated Universal Time). |
| **Filnamnstillägg** | Filtilläggstypen. |
| **Användaraktivitetshändelser** | Aktivitet för objekt som är relaterade till specifik användaraktivitet i ett ärende.  När du till exempel väljer en länk för att  "Utforska innehåll" för en aktivitet på sidan Användaraktivitet för ett ärende används filtret till att visa objekt som är relaterade till den aktiviteten. |
| **Arbetsprodukt** | Typen av arbetsprodukt för dokumentet. Till exempel anteckningar eller taggar i dokumentet. |
