---
title: Sidan för e-post entitet i Microsoft Defender Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender för Office 365 E5- och P1- och P2-kunder kan nu få en 360-gradersvy av varje e-postmeddelande med entitetssidan.
ms.openlocfilehash: d2f5a5b20034ef22b8e3894885079609a9ad5874
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083304"
---
# <a name="the-email-entity-page"></a>Sidan E-postenhet

**I den här artikeln:**
- [Nå entitetssidan för e-post](#reach-the-email-entity-page)
- [Sidan Läs e-post entitet](#read-the-email-entity-page)
- [Använda sidflikar för e-post entitet](#use-email-entity-page-tabs)
- [Nytt för sidan e-post entitet](#new-to-the-email-entity-page)

Administratörerna för Microsoft Defender för Office 365 (eller MDO) E5 och MDO P1 och P2 har en 360-gradersvy av e-post på sidan **E-post entitet.** Den här sidan för att gå till e-post har skapats för att förbättra informationen som levereras i e-postutforskaren i [Hotutforskaren.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>Nå entitetssidan för e-post

Sidan för e-post entitet är tillgänglig i Microsoft 365 defender-portalen <https://security.microsoft.com> () i **E& för samarbete** \> **i Utforskaren.** Du kan också använda för att gå **direkt till** sidan i <https://security.microsoft.com/threatexplorer> Utforskaren.

I **Utforskaren** väljer du ämnet för ett e-postmeddelande som du undersöker. En guldlist visas högst upp i e-postmeddelandet. Den här inbjudan till den nya sidan säger "Prova vår nya sida för e-post entitet med bättre data...". Välj för att visa den nya sidan.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Du kommer att se en guld banderoll med orden *Prova på vår nya sida för e-post entitet med bättre data* för att navigera till den nya upplevelsen.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Den här bilden på sidan för e-post entitet fokuserar på rubriker som du kommer att se. Observera att e-posthuvudet visas här.":::

> [!NOTE]
> Behörigheterna som krävs för att visa och använda den här sidan är samma som för att visa **Utforskaren**. Administratören måste vara medlem i en global administratör eller global läsare, eller säkerhetsadministratör eller säkerhetsläsare. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).

## <a name="read-the-email-entity-page"></a>Sidan Läs e-post entitet

Strukturen är utformad för att vara lätt att läsa och navigera i på ett ögonblick. Med olika flikar längst upp på sidan kan du undersöka mer ingående. Så här fungerar layouten:

1. De mest obligatoriska fälten finns till vänster i den utfällbaserade sidan. Den här informationen är "trög", vilket innebär att de är fästa till vänster oavsett vilken flik du navigerar till i resten av utfällpunkten.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Bild på sidan för e-post entitet med vänster sida markerad. Rubriken och fakta om e-postleveransen finns här.":::

2. I det övre högra hörnet finns de åtgärder som kan vidtas i ett e-postmeddelande. Alla åtgärder som kan vidtas i **Utforskaren kommer** också att vara tillgängliga via e-post entitetssidan.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Bild på sidan för e-post entitet med *höger*-sidan markerad, den här gången. Åtgärder som förhandsgranskning av e-post och Gå till karantän är här.":::

3. Djupare analyser kan göras genom att sortera resten av sidan. Kontrollera informationen om e-postidentifiering, e-postautentiseringsstatus och rubrik. Du bör titta i det här området från fall till fall, men informationen på flikarna är tillgänglig för alla e-postmeddelanden.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Huvudpanelen på den här sidan innehåller e-postrubrik och autentiseringsstatus.":::

### <a name="use-email-entity-page-tabs"></a>Använda sidflikar för e-post entitet

Med flikarna längst upp på entitetssidan kan du undersöka e-post effektivt.

1. **Tidslinje:** Tidslinjevyn för ett e-postmeddelande **(tidslinjen** i Utforskaren) visar den ursprungliga leveransen till efterleveranshändelser som inträffar i ett e-postmeddelande. För e-postmeddelanden som inte har några åtgärder efter leveransen visas den ursprungliga leveransraden i tidslinjevyn. Händelser som: Zap (Zero-hour auto purge), åtgärd, URL-klick och så vidare från källor som system, administratör och användare visas här, i den ordning de inträffade.
2. **Analys**: Analys visar fält som hjälper administratörer att analysera ett e-postmeddelande på djupet. I de fall där administratörer behöver förstå mer information om identifiering, avsändare/mottagare och information om e-postautentisering ska de använda fliken Analys. Länkar till bifogade filer och URL-adresser finns också på den här sidan, under "Relaterade enheter". Både bifogade filer och identifierade hot numreras här och när du klickar tar du dig direkt till bifogade filer och URL-sidor. Den här fliken har också alternativet Visa sidhuvud för *att visa e-posthuvudet*. Administratörer kan för tydlighets skull jämföra information från e-postrubriker sida vid sida med information i huvudpanelen.
3. **Bifogade filer:** Då undersöks bifogade filer som hittades i e-postmeddelandet med annan information som hittades på bifogade filer. Antalet bifogade filer som visas är för närvarande begränsat till 10. Observera att information om avonering av bifogade filer som visar sig vara skadliga också visas här.
4. **URL:er:** Den här fliken visar URL:er som finns i e-postmeddelandet med annan information om URL:er. Antalet URL:er är begränsade till 10 just nu, men dessa 10 prioriteras för att visa *skadliga URL:er först.* Med prioritering sparas tid och gissningsarbete. URL-adresser som identifierats som skadliga och detonerade visas också här.
5. **Liknande e-postmeddelanden:** Den här fliken visar alla e-postmeddelanden som liknar kombinationen av *nätverksmeddelande-ID + mottagare* för det här e-postmeddelandet. Likheten baseras endast på *brödtexten i meddelandet*. De beslut som gjorts för e-postmeddelanden om att kategorisera dem som "liknande" omfattar inte några överväganden av bifogade *filer.*

## <a name="new-to-the-email-entity-page"></a>Nytt för sidan e-post entitet

Det finns nya funktioner på sidan för den här e-postentitet. Här är listan.

### <a name="email-preview-for-cloud-mailboxes"></a>Förhandsgranskning av e-post för molnbaserade postlådor

Administratörer kan förhandsgranska e-postmeddelanden i molnbaserade ***postlådor,*** om e-postmeddelandena fortfarande finns kvar i molnet. Om en mjuk borttagning (av en administratör eller användare) eller ZAP (för karantän) används inte längre e-postmeddelanden på molnplatsen. I så fall kan inte administratörer förhandsgranska de specifika e-postmeddelandena. E-postmeddelanden som släppts, eller där leveransen misslyckades, har aldrig levererats till postlådan. Därför kan inte administratörerna förhandsgranska dessa e-postmeddelanden heller.

> [!WARNING]
> För förhandsgranskning av e-postmeddelanden krävs en särskild roll som **heter Förhandsgranska.** Du kan lägga till den här rollen Microsoft 365 Defender portalen enligt beskrivningen [i e& och samarbetsroller i Microsoft 365 Defender portalen.](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal) Du kan behöva skapa en ny rollgrupp **för e-&-postsamarbete** där och  lägga till förhandsgranskningsrollen i den nya rollgruppen, eller lägga till förhandsgranskningsrollen i en rollgrupp där administratörer i organisationen kan arbeta i **Utforskaren.** 

### <a name="detonation-details"></a>Information om detonation

Den här informationen är specifik för e-postbilagor och URL-adresser. Användarna kan se den här informationen  genom att gå till Utforskaren och använda det teknikfilter som är inställt på detonation eller en URL-detonation. E-postmeddelanden som filtreras efter fil detonation innehåller en skadlig fil med information om detonation, och de som filtreras efter URL-adresser innehåller en skadlig URL och information om avonationen.

Användarna ser mer information som kan göra det mer avancerat för kända skadliga bifogade filer och URL-adresser som finns i deras e-postmeddelanden, som har detonerats för den specifika klientorganisationen. Den består av detonationskedjan, sammanfattningen av detonationen, skärmbilden och den observerade funktionsinformationen som hjälper kunderna att förstå varför den bifogade filen eller URL:en anses vara skadlig och detonerad.

1. *Detonation chain*. En enskild fil eller URL-detonation kan utlösa flera detonationer. Detonation-kedjan spårar sökvägen till detonationer, inklusive den ursprungliga skadliga filen eller URL-adressen som orsakade bedömning, och alla andra filer eller URL-adresser som upptäckts av detonationen. Dessa URL:er eller bifogade filer kanske inte finns direkt i e-postmeddelandet, men det är viktigt att ta med denna analys för att fastställa varför filen eller URL:en hittades som skadlig.  

    > [!NOTE]
    > Det här kan bara visa objektet på översta nivån om ingen av enheterna som är länkade till det visar sig vara problematiskt eller har detonerats.

1. *Detonation Summary* ger en grundläggande sammanfattning för detonation, till exempel analystid, tiden då detonationen inträffade, operativsystem och program, operativsystemet och programmet där detonationen inträffade, filstorlek och bedömningsorsak.
1. *Skärmbilder* visar skärmbilderna som tagits vid detonation. Det kan finnas flera skärmbilder vid detonation. Inga skärmbilder visas för
    - Behållare skriver filer som .zip eller .rar.
    - Om en URL öppnas i en länk som direkt laddar ned en fil. Men du ser den nedladdade filen i detonationskedjan.
1. *Funktionsinformationen* är en export som visar information om beteendeinformation, till exempel exakta händelser som ägde rum vid detonation, och observabler som innehåller URL:er, IP-adresser, domäner och filer som hittades vid detonationen (och kan antingen vara problematiskt eller problematiskt). Observera att det kanske inte finns någon funktionsinformation för:
    - Behållarfiler som .zip eller .rar som innehåller andra filer.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Skärmbild av detonationssammanfattningen med kedja, sammanfattning, avoneringsinformation och skärmbild under rubriken *Djupanalys*.":::

### <a name="other-innovations"></a>Andra innovationer

*Taggar:* Det här är taggar som tillämpas på användare. Om användaren är mottagare ser administratörer en *mottagartagg.* På samma sätt är om användaren är en avsändare, en *avsändartagg.* Detta visas till vänster på sidan för e-postenheter (i  den del som beskrivs som fäst och därför fäst på sidan).

*Senaste leveransplats:* Den senaste leveransplatsen är den plats där ett e-postmeddelande landade efter systemåtgärder som ZAP eller administrativa åtgärder som Flytta till Borttagna objekt slutförs. Senaste leveransplats är inte tänkt att informera administratörer om meddelandets *aktuella* plats. Om en användare till exempel tar bort ett meddelande eller flyttar det till arkivering, uppdateras inte leveransplatsen. Men om en systemåtgärd har vidtagits och uppdaterat platsen (till exempel en ZAP som resulterar i ett e-postmeddelande som flyttas till karantän) uppdateras den senaste leveransplatsen till karantän.

*E-postinformation:* Information krävs för en djupare förståelse av e-post på *fliken* Analys.

- Exchange transportregler (kallas även e-postflödesregler eller *ETR-regler)*: De här reglerna tillämpas på ett meddelande på transportlagret och har företräde framför nätt och skräppost. Dessa kan bara skapas och ändras i administrationscentret för Exchange, men om något ETR gäller för ett meddelande visas ETR-namnet och GUID här. Värdefull information för spårningssyfte.

- *Åsidosättningar* i systemet: Det här är ett sätt att göra undantag till den leveransplats som är avsedd för ett meddelande genom att åsidosätta leveransplatsen som anges av systemet (enligt teknik för hot och identifiering).

- *Skräppostpostlåderegel:* Skräppost är en dold inkorgsregel som aktiveras som standard i alla postlådor.
  - När skräppostregeln har aktiverats i postlådan kan Exchange Online Protection (EOP) flytta meddelanden till Skräppost enligt vissa villkor. Flytten kan baseras på åtgärden skräppostfiltrering av bedömning Flytta meddelandet till mappen Skräppost eller i listan Spärrade avsändare i postlådan. Om du inaktiverar skräppostregeln *förhindras* leverans av meddelanden till mappen Skräppost baserat på Valv avsändare i postlådan.
  - När skräppostregeln är  inaktiverad för postlådan kan EOP inte flytta meddelanden till mappen Skräppost baserat på åtgärden skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.

- *BCL (Bulk Complaint Level):* BCL (Bulk Complaint Level) för meddelandet. En högre BCL anger att det är mer sannolikt att ett massutskick av e-postmeddelande skapar klagomål (det naturliga resultatet om e-postmeddelandet kan vara skräppost).

- *SCL (Spam Confidence Level):* SCL (Spam Confidence Level) för meddelandet. Ett högre värde innebär att det är mer troligt att meddelandet är skräppost.

- *Domännamn:* Är avsändarens domännamn.

- *Domänägare:* Anger ägaren av den avsändande domänen.

- *Domänplats:* Anger platsen för den avsändande domänen.

- *Datum då domänen skapades:* Anger datumet då avsändardomänen skapades. En nyligen skapad domän är något som du kan vara försiktig med om andra signaler anger något misstänkt beteende.

*E-postautentisering:* E-postautentiseringsmetoder som används av Microsoft 365 omfattar SPF, DKIM och DMARC.

- Sender Policy Framework (**SPF**): Beskriver resultaten för SPF-kontrollen för meddelandet. Möjliga värden kan vara:
  - Pass (IP address): SPF-kontrollen för meddelandet som skickas och innehåller avsändarens IP-adress. Klienten har tillåtelse att skicka eller vidarebefordra e-post på avsändarens domän.
  - Fel (IP-adress): SPF-kontrollen för meddelandet misslyckades och innehåller avsändarens IP-adress. Det här kallas ibland för en hard fail.
  - Softfail (orsak): SPF-posten har angett att värden inte tillåts skicka men är under övergång.
  - Neutral: SPF-posten anger uttryckligen att den inte kan avgöra om IP-adressen har behörighet att skicka.
  - Inget: Domänen har ingen SPF-post, eller så utvärderas inte SPF-posten till ett resultat.
  - Så här: Ett tillfälligt fel har uppstått. Till exempel ett DNS-fel. Samma kontroll kan senare lyckas.
  - Permerror: Ett permanent fel har inträffat. Domänen har till exempel en dåligt formaterad SPF-post.

- **DKIM**(DomainKeys Identified Mail):
  - Godkänd: Anger DKIM-kontrollen för meddelandet som har passerat.
  - Fel (orsak): Anger DKIM-kontrollen för meddelandet misslyckades och varför. Om du till exempel inte har signerat meddelandet eller om signaturen inte har verifierats.
  - Ingen: Anger att meddelandet inte har signerats. Detta indikerar kanske, men kanske inte, att domänen har ett DKIM-register eller att DKIM-registret inte utvärderats till ett resultat, endast att meddelandet inte signerats.

- **DMARC**(Domain-based Message Authentication, Reporting, and Conformance):
  - Godkänd: Anger DMARC-kontrollen för meddelandet som skickas.
  - Fel: Anger DMARC-kontrollen för meddelandet misslyckades.
  - Bestguesspass: Anger att det inte finns någon DMARC TXT-post för domänen, men om någon hade funnits skulle DMARC-kontrollen för meddelandet ha passerat.
  - Ingen: Anger att det inte finns någon DMARC TXT-post för den avsändande domänen i DNS.

*Sammansatt autentisering:* Det här är ett värde som används av Microsoft 365 för att kombinera e-postautentisering som SPF, DKIM och DMARC för att avgöra om meddelandet är äkta. Den använder domänen *Från:* för e-postmeddelandet som grund för utvärdering.
