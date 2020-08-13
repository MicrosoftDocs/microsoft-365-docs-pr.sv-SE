---
title: Åtgärda skadlig e-post som har levererats i Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Hot-reparation
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 9ffa3f71dafec4728294b17530ae1f9490d480da
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656689"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Åtgärda skadlig e-post som har levererats i Office 365

Med reparation menas en åtgärd mot ett hot. Illvilliga e-postmeddelanden som skickas till din organisation kan rensas antingen av systemet, genom ZAP (automatisk rensning av nollor) eller av säkerhets team genom reparations åtgärder som flytta till Inkorgen, flyttas till skräp post, flyttas till mappen Borttaget, mjuk borttagning eller borttagning. Avancerat skydd för Office (Office ATP) P2/E5 erbjuder säkerhets åtgärder för att Mediate hot i e-post och samarbets problem genom manuella frågor och automatiska utredningar.

> [!NOTE]
> För att säkerhets team ska kunna åtgärda e-post måste de ha tilldelats Sök och rensa-rollen. Roll tilldelning sker genom behörigheter i säkerhets-och efterlevnadsprinciper.

## <a name="what-you-need-to-know-before-you-begin"></a>Vad du behöver veta innan du börjar

Om du vill utföra vissa åtgärder, till exempel Visa meddelande rubriker eller hämta e-postinnehåll, måste du ha en ny roll som heter för *förhands granskning* tillagd i en annan lämplig roll grupp. Följande tabell förklarar de roller och behörigheter som krävs.

****

|Aktivitet|Roll grupp|Vill du för hands Visa den?|
|---|---|---|
|Använd Threat Explorer (och real tids identifieringar) för att analysera hot |Global administratör <br> Säkerhets administratör <br> Säkerhets läsare|Nej|
|Använd Threat Explorer (och real tids identifieringar) för att visa rubriker för e-postmeddelanden samt för hands Visa och ladda ned e-postmeddelanden i karantän|Global administratör <br> Säkerhets administratör <br>Säkerhets läsare|Nej|
|Använda Threat Explorer för att visa rubriker och hämta e-postmeddelanden som skickas till post lådor|Global administratör <br>Säkerhets administratör <br> Säkerhets läsare <br> Automatisk|Ja|
|

> [!NOTE]
> För *hands versionen* är en roll och inte en roll grupp; förhands gransknings rollen måste läggas till i en befintlig roll grupp för Office 365. Rollen global administratör har tilldelats administratörs Center för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) och rollerna säkerhets administratör och säkerhets läsare tilldelas i säkerhets & Compliance Center ( [https://protection.office.com](https://protection.office.com) ). Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Administratörer kan vidta nödvändiga åtgärder för e-postmeddelanden, men för att få sina åtgärder godkända måste de ha rollen "Sök och rensa" som tilldelats dem via säkerhets-och efterlevnadsprinciper > behörigheter.

## <a name="manual-and-automated-remediation"></a>Manuell och automatisk reparation

**Manuell jakt** sker när säkerhets team identifierar hot manuellt, med hjälp av funktionerna för sökning och filtrering i Threat Explorer. Manuell reparation av e-postmeddelanden kan utlösas via valfri e-postvy (malware, Phish eller all e-post) efter en uppsättning e-postmeddelanden som måste åtgärdas.

[Manuell jakt i Office 365 Threat Explorer efter datum.](../../media/tp-RemediationArticle1.png)

Valet av e-postmeddelanden kan göras på flera olika sätt via Threat Explorer:

1. Välja e-post för hand: det innebär att säkerhets åtgärder team kan använda filter i respektive vy och välja några e-postmeddelanden från hot Utforskaren som måste åtgärdas. Den övre gränsen för att välja e-postmeddelanden är 100 (100). Säkerhets åtgärder kan inte välja fler än hundra e-postmeddelanden manuellt.

2. Urval av frågor: säkerhets åtgärder kan välja en hel fråga med knappen överst "Välj alla". Samma fråga visas också i åtgärds Center för e-postinformation.

3. Urval med undantag: det kan finnas tillfällen då säkerhets åtgärds teamen bestämmer sig för att åtgärda e-postmeddelanden genom att båda välja en hel fråga och utesluta ett fåtal e-postmeddelanden från frågan. För att göra detta kan administratören använda kryss rutan "Markera alla" och rulla nedåt för att utesluta ett fåtal e-postmeddelanden, manuellt. Det högsta antalet e-postmeddelanden som frågan kan innehålla är 1000 (1 000) och det högsta antalet undantag är 100 (100) i det här fallet.

När du har valt e-postmeddelanden från Threat Explorer kan du börja med att skapa en åtgärd genom att direkt vidta åtgärder, eller genom att köa e-post för en aktivitet:

1. Direkt godkännande: när åtgärder som "flytta till Inkorgen", "flytta till skräp post", "flytta till borttaget", "mjuk borttagning", "hårda Delete" väljs av säkerhets personalen med rätt behörighet och nästa steg följer med reparations processen för att utföra en vald åtgärd. En tillfällig utfällning visar pågående reparation.

2. Två steg godkännande: åtgärden "Lägg till i reparation" kan utföras av en administratör som saknar rätt behörighet eller som måste vänta på att utföra åtgärden. I det här fallet utförs inte reparations åtgärden direkt. I stället läggs e-postmeddelanden till i en reparations behållare som måste godkännas för att kunna köras. Tills reparationen godkänns åtgärdas inte e-postmeddelandet. När du har godkänt åtgärden utförs åtgärderna på e-postmeddelandet.

**Automatiserade undersökningar och svar (Air)** aktive ras via notifieringar eller av team för säkerhets åtgärder från Threat Explorer. De kan inkludera vissa rekommenderade reparationer som måste godkännas av team för säkerhets åtgärder. Dessa åtgärder finns på fliken åtgärd i den automatiska undersökningen.

[E-post med skadlig program vara är zapped sida som visar tiden för ZAP-körningen.](../../media/tp-RemediationArticle3.png)

Alla reparationer (antingen direkt godkännande eller ett godkännande med två steg) skapas via Threat Explorer och godkända åtgärder från automatiserade utredningar, visas i åtgärds centret, som du kommer åt via det vänstra navigerings fältet under * granska * > **Åtgärds Center**.

[Åtgärds Center med en lista med hot efter datum och allvarlighets grad.](../../media/tp-RemediationArticle4.png)

Åtgärds Center visar alla reparations åtgärder under de senaste 30 dagarna. Åtgärder som utförs via Utforskaren visas med samma namn som tillhandahålls av säkerhets åtgärds teamen när reparationen skapades. Åtgärder som utförs genom automatiserade utredningar bevaras med rubriker som börjar med den relaterade aviseringen som utlöste undersökningen – till exempel "ZAP-e-postkluster...".

Varje reparations objekt kan öppnas för att visa information om den. När ett åtgärds objekt öppnas visas grundläggande information om hjälp, reparations namn, skapelse datum, beskrivning, Hot allvarlighets grad och status. Här visas även två flikar.

1. **Fliken e-post**: det här är antalet e-postmeddelanden som skickas via Threat Explorer eller automatiska utredningar som ska åtgärdas. Dessa e-postmeddelanden kan vara:

   [Åtgärds Center med problem som åtgärdas och inte är åtgärdade.](../../media/tp-RemediationArticle5.png)

   - **Åtgärdbar**: e-postmeddelanden i följande moln post lådor kan behandlas och flyttas, dvs. alla e-postmeddelanden inom den avvisande kategorin kan flyttas från en plats till en annan:

     - Brevlåda
     - Mappen
     - Borttagen mapp
     - Mjuk borttagen mapp

     [!NOTE]
     > För närvarande kan bara en slutanvändare med åtkomst till post lådan återskapa objekt från en mjuk borttagnings mapp.

   - **Inte åtgärdbar**: e-postmeddelanden på följande platser kan inte utföras eller flyttas som en del av e-poståtgärderna, dvs. e-post i en icke-avhjälpbar kategori kan inte flyttas vare sig i den icke-omarbetande kategorin eller i avgörandet. Platser som inte går att lösa är:

     - Karantän
     - Mappen Borttaget
     - On-lokala/extern
     - Misslyckad/avbruten

   Misstänkta meddelanden som skickas är kategoriserade som antingen avhjälpa eller icke-avfria. I de flesta fall bör avhjälpade och icke-avfria meddelanden läggas till totalt antal skickade meddelanden. Det kan emellertid finnas sällsynta fall där de meddelanden som skickas kanske inte kan läggas till summan av de artiklar som inte går att avhjälpa, och det kan vara högre eller lägre än det totala antalet skickade meddelanden. Detta kan bero på fördröjningar, timeout eller inaktuella meddelanden. Meddelanden upphör att gälla baserat på webbläsarens bevarande period för din organisation.

   Om du inte reparerar gamla meddelanden efter att organisationens bevarande period är aktive rad och du ser inkonsekvenser i tal, bör du försöka åtgärda objekt igen. För system fördröjningar uppdateras vanligt vis reparations uppdateringar inom några timmar.

   Om din organisations bevarande period för e-post i Utforskaren är 30 dagar och du åtgärdar e-postmeddelanden som kommer 29-30 dagar tillbaka, kan inga meddelanden om att skicka e-post alltid läggas till eftersom e-postmeddelandena kanske har börjat flytta från lagrings perioden.

   Om reparationerna fastnat i ett läge som pågår, beror det troligt vis på systemets fördröjning. Det kan ta upp till några timmar att åtgärda. Det kan förekomma en variationer i e-postsändningen som vissa av e-postmeddelandena inte var en del av frågan när den startade reparationen på grund av system fördröjningar. Det är en bra idé att försöka åtgärda detta i sådana fall.

   För bästa resultat bör reparationen göras i mindre satser med cirka 50k eller färre e-postmeddelanden.

   Av alla e-postmeddelanden i e-post som skickas är avhjälpade e-postmeddelanden de enda som kommer att åtgärdas vid reparationen. E-postsystem som inte är avhjälpade kan inte åtgärdas av Office 365-e-postsystemet, eftersom de inte lagras i moln post lådor.

   För e-postmeddelanden som hittas i karantän kan administratörer gå till karantän för att utföra åtgärder på dessa e-postmeddelanden, men e-postmeddelandena upphör att gälla från karantänen om de inte töms manuellt. E-postmeddelanden som har satts i karantän på grund av skadligt innehåll är inte tillgängliga för slutanvändare, så säkerhets personalen behöver inte vidta någon särskild åtgärd för att ta bort hotet i karantänen. Om e-postmeddelandet är på lokala eller externt kan slutanvändaren kontaktas för att adressera den misstänkta e-postmeddelandet eller använda separata e-postserver/säkerhets verktyg för borttagning. Dessa e-postmeddelanden kan identifieras genom att använda leverans plats = lokala/externt filter i Threat Explorer. För misslyckad eller avbruten e-post, eller e-post som inte är tillgänglig för slutanvändaren, får inte e-post ändras, eftersom de inte når post lådan.

   Så här visas en överföring i åtgärds Center. En åtgärd kan innehålla flera inlämningar. Om flera åtgärder godkänns genom en automatisk undersökning visas varje e-post-eller e-postkluster-åtgärd i samma reparation som en annan överföring.

   [Den utfällbara panelen för e-postgrupp.](../../media/tp-RemediationArticle6.png)

   Om du klickar på ett objekt i ett e-postmeddelande visas information om reparationen, till exempel frågan (när reparationen utlöses genom automatiska utredningar eller hot Explorer genom att välja en fråga), start tid och slut tid. Dessutom visas en lista med meddelanden som skickades för reparation. Allteftersom meddelanden flyttas från den här tids perioden försvinner meddelandena från den här listan. Den här listan visar också enskilda meddelanden från listan som är avhjälpade.

2. **Fliken åtgärds loggar**: på den här fliken visas resultatet av meddelanden som har reparerats, inklusive uppgifter som godkänt datum, god kännare (administratör som godkände åtgärden), åtgärd, status och antal.

   Status är den övergripande statusen för reparationen. Status kan vara:

     - **Startat**: när en reparation utlöses.
     - **I kö**: när reparationen är i kö för att minska antalet e-postmeddelanden.
     - **Pågår**: när minskningen pågår.
     - **Slutfört**: när det är du som är på väg att avhjälpa e-postmeddelanden eller problem.
     - **Misslyckades**: när ingen åtgärd utförs.

   Eftersom det bara är möjligt att få hjälp via e-post kan alla e-postmeddelanden få ett lyckat resultat. Med hjälp av de totala avhjälpade e-postmeddelandena förklaras dina lyckade och misslyckade begränsningar.

   - **Lyckades**: när den önskade åtgärden i avhjälpade e-postmeddelanden görs och motsvarar avsikten med administratör. Till exempel: en administratör vill ta bort e-postmeddelanden från post lådor och ta bort e-postmeddelanden. Om det inte går att hitta en åtgärd med e-post i originalmappen efter åtgärden är statusen klar.

   - **Fel**: när den önskade åtgärden i avhjälpade e-postmeddelanden Miss lyckas. Till exempel: en administratör vill ta bort e-postmeddelanden från post lådor, så han tar bort e-postmeddelanden. Om ett e-postmeddelande som är omåtgärdat fortfarande hittas i post lådan visas statusen som misslyckad.

   Om du klickar på ett objekt i åtgärds logg visas information om reparation. Om det går bra att få objekt, om informationen säger, lyckades eller inte finns i post lådan, innebär det att objektet redan har tagits bort från post lådan. Ibland uppstår det problem som uppstår på grund av ett systemfel under reparation, och i dessa fall är det en bra idé att prova igen.

   Reparation är ett kraftfullt verktyg för att minska riskerna och adressera misstänkta e-postmeddelanden. Det hjälper till att skydda en organisation.

## <a name="more-info"></a>Mer information

Se [undersöka skadlig e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)
