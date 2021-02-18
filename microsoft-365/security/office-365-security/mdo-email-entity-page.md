---
title: E-postentitetssidan i Microsoft Defender för Office 365 (MDO)
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
description: Microsoft Defender för Office 365 E5- och ATP P1- och ATP P2-kunder kan nu få en 360-gradersvy av varje e-postmeddelande med entitetssidan för e-post.
ms.openlocfilehash: 0a866b4d635e5c9e26b6fc065503b44ee2063e9f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289491"
---
# <a name="the-email-entity-page"></a>Sidan E-post entitet

**I den här artikeln:**
- [Nå entitetssidan för e-post](#reach-the-email-entity-page)
- [Läs entitetssidan för e-post](#read-the-email-entity-page)
- [Använda sidflikar för entitet e-post](#use-email-entity-page-tabs)
- [Entitetssidan i e-postmeddelandet är ny](#new-to-the-email-entity-page)

Administratörerna för Microsoft Defender för Office 365 (eller MDO) E5 och MDO P1 och P2 har en 360-gradersvy av e-post med hjälp av sidan E-post **entitet.** Den här sidan med gå till [e-post](threat-explorer-views.md)har skapats för att förbättra informationen som levereras i e-postinformationen i Threat Explorer.

## <a name="reach-the-email-entity-page"></a>Nå entitetssidan för e-post

I något av de befintliga säkerhets- och efterlevnadscenterna för Office (protection.office.com) eller nya Säkerhetscenter för Microsoft 365 (security.microsoft.com) kan du se och använda sidan för e-postentitet.

|Centrera  |URL  |Navigering  |
|---------|---------|---------|
|Efterlevnad & säkerhet |protection.office.com | Threat Management > Explorer   |
|Microsoft 365 Säkerhetscenter |security.microsoft.com | E& för samarbete > Utforskaren |

I Hot Explorer väljer du ämnet för ett e-postmeddelande som du undersöker. Ett guldfält visas högst upp i e-postmeddelandet. I den här inbjudan till den nya sidan står det "Prova vår nya e-post entitetssida med anrikade data...". Välj att visa den nya sidan.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Du kommer att se en guld banderoll med orden *Prova vår nya sida för e-post entitet med bättre data* för att navigera till den nya upplevelsen.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Den här bilden på sidan med entitet e-post fokuserar på rubriker som du ser. Observera att e-posthuvudet visas här.":::

> [!NOTE]
> Behörigheterna som krävs för att visa och använda den här sidan är desamma som för att visa Hotutforskaren. Administratören måste vara medlem i en global administratör eller global läsare, eller säkerhetsadministratör eller säkerhetsläsare.

## <a name="read-the-email-entity-page"></a>Läs entitetssidan för e-post

Strukturen är utformad för att vara lätt att läsa och navigera i. Med olika flikar högst upp på sidan kan du undersöka mer ingående. Så här fungerar layouten:

1. De mest obligatoriska fälten finns till vänster i den utfällbaserade sidan. Den här informationen är "fäst", vilket innebär att de är fästa till vänster oavsett vilken flik du navigerar till i resten av flyget.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Bild på sidan för e-postentitet med vänster sida markerad. Rubriken och information om e-postleveransen finns här.":::

2. I det övre högra hörnet finns de åtgärder som kan vidtas i ett e-postmeddelande. Alla åtgärder som kan vidtas i Utforskaren kommer också att vara tillgängliga via e-post entitetssidan.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Bild på sidan för e-postentitet med *höger* sidan markerad, den här gången. Åtgärder som förhandsgranskning av e-post och Gå till karantän är här.":::

3. Djupare analyser kan göras genom att sortera resten av sidan. Kontrollera informationen om identifiering av e-post, e-postautentiseringsstatus och rubrik. Vi bör titta efter det här området från fall till fall, men informationen på flikarna är tillgänglig för alla e-postmeddelanden.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Huvudpanelen på den här sidan innehåller e-posthuvud och autentiseringsstatus.":::

### <a name="use-email-entity-page-tabs"></a>Använda sidflikar för entitet e-post

Med flikarna högst upp på entitetssidan kan du undersöka e-post effektivt.

1. **Tidslinje:** Tidslinjevyn för ett e-postmeddelande (enligt tidslinjen i Threat Explorer) visar den ursprungliga leveransen till efterleveranshändelser som inträffar i ett e-postmeddelande. För e-postmeddelanden som inte har några åtgärder efter leveransen visas den ursprungliga leveransraden i tidslinjevyn. Händelser som: Zap (Zero-hour Auto Purge), Åtgärd, URL-klick och oanvända data från källor som system, administratör och användare visas här, i den ordning de inträffade.
2. **Analys:** Analysen visar fält som hjälper administratörer att analysera ett e-postmeddelande på djupet. I de fall där administratörer behöver förstå mer om identifiering, avsändare/mottagare och information om e-postautentisering ska de använda fliken Analys. Länkar till bifogade filer och URL-adresser finns också på den här sidan, under "Relaterade enheter". Både bifogade filer och identifierade hot numreras här och när du klickar tar du dig direkt till bifogade filer och URL-sidor. Den här fliken har också alternativet Visa sidhuvud för *att visa e-postrubriken.* Administratörer kan för tydlighets skull jämföra information från e-posthuvudena sida vid sida med informationen i huvudpanelen.
3. **Bifogade filer:** Här undersöks bifogade filer som hittades i e-postmeddelandet med annan information som hittades på bifogade filer. Antalet bifogade filer som visas är för närvarande begränsat till 10. Observera att information om detonation för bifogade filer som visar sig vara skadliga också visas här.
4. **URL:er:** Den här fliken visar URL:er som finns i e-postmeddelandet med annan information om URL:er. Antalet URL:er är begränsat till 10 just nu, men de här 10 prioriteras för att *visa skadliga URL:er först.* Med prioritering sparas tid och gissningsarbete. Url:erna som identifierats som skadliga och detonerade visas också här.
5. **Liknande e-postmeddelanden:** På den här fliken visas alla e-postmeddelanden som liknar kombinationen *av nätverksmeddelande-ID +* mottagare som är specifik för det här e-postmeddelandet. Likheten baseras endast på *brödtexten i* meddelandet. De beslut som gjorts om att kategorisera dem som "liknande" tas inte med i beräkningen av bifogade *filer.*

## <a name="new-to-the-email-entity-page"></a>Entitetssidan i e-postmeddelandet är ny

Det finns nya funktioner som kommer med den här e-postentitetssidan. Här är listan.

### <a name="email-preview-for-cloud-mailboxes"></a>Förhandsgranskning av e-post för molnbaserade postlådor
Administratörer kan förhandsgranska e-postmeddelanden i molnbaserade ***postlådor,*** om e-postmeddelandena fortfarande finns i molnet. Vid en mjuk borttagning (av en administratör eller användare) eller ZAP (för karantän) finns inte längre e-postmeddelanden på molnplatsen. I så fall kan inte administratörer förhandsgranska de specifika e-postmeddelandena. E-postmeddelanden som släppts, eller där leveransen misslyckades, tog faktiskt aldrig emot den till postlådan. Därför kan inte administratörer förhandsgranska de e-postmeddelandena heller.

> [!WARNING]
>För förhandsgranskning av e-postmeddelanden krävs en särskild roll **som** heter * Preview _ för att tilldelas till administratörer. Du kan lägga till den här rollen genom att gå till _ *Behörigheter &* roller * > **E&-post** och samarbetsroller i *security.microsoft.com* eller **Behörigheter** *i protection.office.com.* Lägg  till förhandsversionsrollen i någon av rollgrupperna eller en kopia av en rollgrupp som gör att administratörer i organisationen kan arbeta i Hotutforskaren.

### <a name="detonation-details"></a>Information om detonation

Den här informationen är specifik för e-postbilagor och URL-adresser.

Användarna ser bättre detonationsinformation för kända skadliga bifogade filer eller hyperlänkar i postlådorna, inklusive detonationskedjan, sammanfattningen av detonationen, skärmbild och observerat beteendeinformation för att hjälpa kunderna att förstå varför den bifogade filen eller URL:en anses vara skadlig och detonerad.
 
- *Detonationskedjan*: En enda fil- eller URL-detonation kan utlösa flera detonationer. Detonationskedjan spårar sökvägen till detonationer, inklusive den ursprungliga skadliga filen eller URL-adressen som orsakade bedömning, och alla andra filer eller URL-adresser som påverkas av detonationen. Dessa URL:er eller bifogade filer kanske inte finns direkt i e-postmeddelandet, men det är viktigt att ta med den analysen för att fastställa varför filen eller URL-adressen hittades som skadlig.
- *Sammanfattning av detonation*: Detta ger information om:
    - Detonationsintervall.
    - Bedömning av den bifogade filen eller URL-adressen.
    - Relaterad information (filnummer, URL:er, IP-adresser eller domäner), som är andra enheter som är under detonation.
- *Skärmbild av detonation*: Visar skärmbilder som tagits under detonationsprocessen.
- *Information om detonation:* Det här är den exakta beteendeinformationen för varje process som ägde rum vid detonationen.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Skärmbild av detonationssammanfattningen med kedja, sammanfattning, detonationsdetaljer och skärmbild under rubriken *Djupanalys*.":::

### <a name="other-innovations"></a>Andra innovationer

*Taggar:* Det här är taggar som tillämpas på användare. Om användaren är mottagare ser administratörer en *mottagartagg.* På samma sätt gäller om användaren är en avsändare, en *avsändartagg.* Detta visas till vänster på sidan för e-postenheter (i  den del som beskrivs som fäst och därför fäst vid sidan).

*Senaste leveransplats:* Den senaste leveransplatsen är den plats där ett e-postmeddelande landade efter systemåtgärder som ZAP eller administrativa åtgärder som Flytta till Borttagna objekt slutförs. Senaste leveransplats är inte tänkt att informera administratörer om meddelandets *aktuella* plats. Om en användare till exempel tar bort ett meddelande eller flyttar det till arkivering, uppdateras inte leveransplatsen. Men om en systemåtgärd har vidtas och uppdaterat platsen (t.ex. ett ZAP som resulterar i att ett e-postmeddelande flyttas till karantän) uppdateras den senaste leveransplatsen till karantän.

*E-postinformation:* Information som krävs för en djupare förståelse av e-post på *fliken* Analys.

- *Exchange-transportregler (ETR-regler* eller e-postflödesregler) : Dessa regler tillämpas på ett meddelande på transportlagret och har företräde framför nättändiga och skräppostinställanden. Dessa kan bara skapas och ändras i administrationscentret för Exchange, men om en ETR-regel gäller för ett meddelande visas ETR-namnet och GUID här. Värdefull information för uppföljning.
    
- *Systemav åsidosättningar:* Det här är ett sätt att göra undantag till leveransplatsen som är avsedd för ett meddelande genom att åsidosätta leveransplatsen som anges av systemet (enligt teknik för hot och identifiering).
    
- *Skräppostpostlåderegel:* Skräppost är en dold inkorgsregel som aktiveras som standard i alla postlådor.
    - När skräppostregeln har aktiverats för postlådan kan Exchange Online Protection (EOP) flytta meddelanden till Skräppost enligt vissa villkor. Flytten kan baseras på skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller listan Spärrade avsändare i postlådan.  Om du inaktiverar skräppostregeln *förhindras* leverans av meddelanden till mappen Skräppost baserat på listan Betrodda avsändare i postlådan.
    - När skräppostregeln är  inaktiverad för postlådan kan EOP inte flytta meddelanden till mappen Skräppost baserat på åtgärden skräppostfiltrering och flyttningsåtgärden Flytta meddelandet till mappen Skräppost eller listan Över säkra i postlådan.
    
- *BCL (Bulk Compliant Level):* Nivå för massklagomål (BCL) för meddelandet. Om du anger ett högre BCL-tecken är det troligare att ett massutskick genererar klagomål (det naturliga resultatet om e-postmeddelandet troligen är skräppost).
    
- *SCL (Spam Confidence Level):* SCL (Spam Confidence Level) för meddelandet. Ett högre värde innebär att det är mer troligt att meddelandet är skräppost.

- *Domännamn:* Är avsändarens domännamn.
    
- *Domänägare:* Anger ägaren av avsändardomänen.
    
- *Domänplats:* Anger platsen för den avsändande domänen.
    
- *Datum då domänen skapades:* Anger datumet då den avsändande domänen skapades. En nyligen skapad domän är något du kan vara försiktig med om andra signaler anger något misstänkt beteende.

E-postautentisering: E-postautentiseringsmetoder som används av Microsoft 365 är SPF, DKIM och DMARC.

- Sender Policy Framework **(SPF**): Beskriver resultat för SPF-kontroll för meddelandet. Möjliga värden kan vara:
    - Godkänd (IP-adress): SPF-kontrollen för meddelandet skickas och innehåller avsändarens IP-adress. Klienten har tillåtelse att skicka eller vidarebefordra e-post på avsändarens domän.
    - Fel (IP-adress): SPF-kontrollen för meddelandet misslyckades och inkluderar avsändarens IP-adress. Det här kallas ibland för en hard fail.
    - Softfail (orsak): SPF-posten anger att värden inte tillåts skicka men är under övergång.
    - Neutral: SPF-posten anger uttryckligen att den inte utesluter om IP-adressen har behörighet att skicka.
    - Inget: Domänen har ingen SPF-post, eller så utvärderas inte SPF-posten till ett resultat.
    - Problem: Ett tillfälligt fel har inträffat. Till exempel ett DNS-fel. Samma kontroll kan senare lyckas.
    - Permerror: Ett permanent fel har inträffat. Domänen har till exempel en dåligt formaterad SPF-post.

- **DKIM**(DomainKeys Identified Mail):
    - Godkänd: Anger DKIM-kontrollen för meddelandet som skickas.
    - Fel (orsak): Anger DKIM-kontrollen för meddelandet misslyckades och varför. Om du till exempel inte har signerat meddelandet eller om signaturen inte har verifierats.
    - Inget: Anger att meddelandet inte har signerats. Detta indikerar kanske, men kanske inte, att domänen har ett DKIM-register eller att DKIM-registret inte utvärderats till ett resultat, endast att meddelandet inte signerats.

- Domänbaserad meddelandeautentisering, rapportering och överensstämmelse **(DMARC):**
    - Godkänd: Anger DMARC-kontrollen för meddelandet som skickas.
    - Fel: Anger att DMARC-kontrollen för meddelandet misslyckades.
    - Bestguesspass: Anger att det inte finns någon DMARC TXT-post för domänen, men om en sådan fanns skulle DMARC-kontrollen för meddelandet ha passerat.
    - Inget: Anger att det inte finns någon DMARC TXT-post för den avsändande domänen i DNS.

*Sammansatt autentisering:* Det här är ett värde som används av Microsoft 365 för att kombinera e-postautentisering som SPF, DKIM och DMARC för att avgöra om meddelandet är äkta. *E-postdomänen* Från används som grund för utvärdering.
