---
title: Åtgärda skadlig e-post som har levererats i Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: O365-seccomp
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Hot-reparation
appliesto:
- Microsoft 365 Defender
ms.openlocfilehash: 67b27102ff9319e334b5ff1e006fe49f14d3f1ed
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620581"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Åtgärda skadlig e-post som skickas i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Genom reparation menas en fastställd åtgärd mot ett hot. Skadlig e-post som skickas till din organisation kan rensas antingen av systemet, med rensad automatisk rensning (ZAP) eller av säkerhets team genom reparations åtgärder som *Flytta till Inkorgen*, *flyttas till skräp post*, *flyttas till borttagna objekt*, *mjuka rader* *eller* borttagningar. Microsoft Defender för Office 365 P2/E5 gör det möjligt för säkerhets team att åtgärda hot om e-post och samarbets funktioner genom manuell och automatisk undersökning.

> [!NOTE]
> För att åtgärda skadlig e-post måste säkerhets teamen ha tilldelats *Sök-och rensnings* rollen. Roll tilldelning sker genom behörigheter i säkerhets-och kompatibilitetstillstånd.

## <a name="what-you-need-to-know-before-you-begin"></a>Vad du behöver veta innan du börjar

Administratörer kan utföra den åtgärd som krävs för e-post, men för att få dessa åtgärder godkända måste de ha rollen *Sök och ta bort* som har tilldelats dem via **säkerhet & krav för kompatibilitetskontrollen** \> . Utan att rollen "Sök och rensa" har lagts till i en av roll grupperna kan de inte utföra åtgärden.

## <a name="manual-and-automated-remediation"></a>Manuell och automatisk reparation

*Manuell jakt* inträffar när säkerhets team identifierar hot manuellt med hjälp av Sök-och filtrerings funktionerna i Threat Explorer. Manuell e-postreparation kan utlösas via valfri e-postvy (*malware*, *Phish* eller *all e-post*) när du har identifierat en uppsättning e-postmeddelanden som måste åtgärdas.

> [!div class="mx-imgBorder"]
> [![Manuell jakt i Office 365 Threat Explorer efter datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Säkerhets team kan använda Threat Explorer för att välja e-post på flera olika sätt:

- Välj e-post för hand: Använd filter i olika vyer. Välj upp till 100 e-post för att åtgärda.

- Urval för fråga: Markera en hel fråga med knappen **Markera alla** . Samma fråga visas också i åtgärds Center för e-postinformation.

- Urval av frågor med undantag: säkerhets åtgärds team kan ibland åtgärda e-postmeddelanden genom att välja en hel fråga och exkludera vissa e-postmeddelanden från frågan manuellt. För att göra detta kan administratören använda kryss rutan **Markera alla** och rulla nedåt för att utesluta e-postmeddelanden manuellt. Frågan kan innehålla högst 1 000 e-postmeddelanden. Det maximala antalet undantag är 100.

När e-postmeddelanden har marker ATS via Threat Explorer kan du starta reparationen genom att vidta direkt åtgärd eller genom att köa e-post för en åtgärd:

- Direkt godkännande: när en åtgärd som *flyttas till Inkorgen* *flyttas till skräp post*, *flyttas till borttaget*, *mjuk borttagning* eller *fast borttagning* väljs av en säkerhets person som har rätt behörighet och nästa steg i reparations processen används för att utföra den valda åtgärden. En tillfällig utfällning visar pågående reparation.

- Godkännande med två steg: en "Lägg till i reparation"-åtgärd kan vidtas av administratörer som inte har rätt behörighet eller som måste vänta på att utföra åtgärden. I det här fallet läggs riktade meddelanden till i en reparations behållare. Godkännande krävs innan reparationen utförs.

**Automatiserade undersökningar och svars** åtgärder löses genom notifieringar eller av säkerhets åtgärder från Threat Explorer. Dessa kan inkludera rekommenderade reparations åtgärder som måste godkännas av en säkerhets åtgärds grupp. Dessa åtgärder är inkluderade på fliken **åtgärd** i den automatiska undersökningen.

> [!div class="mx-imgBorder"]
> [![Skicka e-post med skadlig program vara på sidan "zapped" med den här tiden för ZAP-körning.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alla reparationer (antingen direkt godkännande eller ett godkännande med två steg) som skapats i Threat Explorer samt godkända åtgärder från automatiserade undersökningar visas i åtgärds centret. Komma åt dessa via den vänstra navigerings panelen under **gransknings** \> **Åtgärds Center**.

> [!div class="mx-imgBorder"]
> [![Åtgärds Center med en lista med hot efter datum och allvarlighets grad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Åtgärds Center visar alla reparations åtgärder under de senaste 30 dagarna. Åtgärder som vidtas via Threat Explorer listas efter det namn som säkerhets åtgärds gruppen tillhandahöll när reparationen skapades. Åtgärder som utförs genom automatiserade utredningar har titlar som börjar med den relaterade aviseringen som utlöste undersökningen, till exempel "ZAP-e-postkluster...."

Öppna ett reparations objekt om du vill visa information om det, inklusive namn, tillkomst datum, beskrivning, risk allvarlighets grad och status. Här visas även två flikar.

- Fliken **e-post** : visar antalet e-postmeddelanden som skickas via Threat Explorer eller automatiska utredningar som ska åtgärdas. Dessa e-postmeddelanden kan vara åtgärdade eller inte åtgärdade.

  > [!div class="mx-imgBorder"]
  > [![Åtgärds Center med problem som åtgärdas och inte är åtgärdade.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Åtgärdbar**: e-postmeddelanden i följande moln post lådor kan användas och flyttas:
    - Brevlåda
    - Mappen
    - Borttagen mapp
    - Mappen Borttaget

      > [!NOTE]
      > För närvarande kan bara en användare som har till gång till post lådan återskapa objekt från en mapp som du har tagit bort.

  - **Ej åtgärdbar**: e-postmeddelanden på följande platser kan inte utföras eller flyttas i åtgärds åtgärder:
    - Karantän
    - Mappen tas bort
    - Lokal/extern
    - Misslyckad/avbruten

  Misstänkta meddelanden kategoriseras som antingen åtgärds bara eller nonremediable. I de flesta fall kan avhjälps bara och nonremediable-meddelanden vara lika med totalt antal skickade meddelanden. I sällsynta fall kan det här vara sant. Detta kan bero på att systemet förskjuts, timeout eller gått ut. Meddelanden upphör att gälla baserat på den bevarande tids perioden för din organisation.

  Om du inte reparerar gamla meddelanden efter det att du har bevarat en bevarande period i din organisations under skrift bör du försöka åtgärda objekt igen om du ser inkonsekvenser av tal. För system fördröjningar uppdateras vanligt vis reparations uppdateringar inom några timmar.

  Om din organisations bevarande period för e-post i Threat Explorer är 30 dagar och du åtgärdar e-post som går tillbaka 29-30 dagar, kan du inte alltid lägga till e-post. E-postmeddelandena kan ha börjat flytta sig från lagrings perioden redan.

  Om reparationen fastnar i tillståndet "pågående" för ett tag beror det troligt vis på systemets fördröjning. Det kan ta upp till några timmar att åtgärda. Du kan se variationer i antal e-postsändningar eftersom vissa av e-postmeddelandena kanske inte har inkluderats i början av reparationen på grund av system fördröjningar. Det är en bra idé att försöka åtgärda detta i sådana fall.

  > [!NOTE]
  > För bästa resultat ska reparationen göras i grupper om 50 000 eller färre.

  Endast avhjälpade e-postmeddelanden behandlas vid reparation. Nonremediable-e-postmeddelanden kan inte åtgärdas av Office 365-e-postsystemet, eftersom de inte lagras i moln post lådor.

  Administratörer kan utföra åtgärder för e-postmeddelanden i karantän om det behövs, men dessa e-postmeddelanden upphör att gälla om de inte töms manuellt. E-postmeddelanden i karantän eftersom skadligt innehåll inte är tillgängligt för användarna, så säkerhets personalen behöver inte vidta några åtgärder för att få bort hot i karantänen. Om e-posten är lokal eller extern kan användaren kontaktas för att adressera den misstänkta e-postmeddelandet. Eller så kan administratörer använda separata e-postservrar/säkerhets verktyg för borttagning. Dessa e-postmeddelanden kan identifieras genom att använda *lokala* externa filter i Threat Explorer. För misslyckad eller avbruten e-post eller e-post som inte är tillgänglig för användarna är det inget e-postmeddelande att undvika, eftersom dessa e-postmeddelanden inte når post lådan.

  I följande bild visas hur en överföring ser ut i åtgärds Center. En åtgärd kan innehålla flera inlämningar. Om flera åtgärder godkänns genom en automatisk undersökning visas varje e-post eller e-postkluster åtgärd i samma reparation som en annan överföring.

  > [!div class="mx-imgBorder"]
  > [![Den utfällbara panelen för e-postgrupp.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Välj ett e-postobjekt om du vill visa information om den här åtgärden, till exempel frågan (när reparationen utlöses genom automatiska utredningar eller hot Explorer genom att välja en fråga) och start-och slut tiderna för reparationen. Dessutom visas en lista med meddelanden som skickades för reparation. När meddelanden flyttas från den bevarande perioden för hot Explorer försvinner meddelandena från den här listan. Listan visar också enskilda meddelanden som är avhjälpade.

- **Åtgärds loggar**: den här fliken visar de meddelanden som har åtgärd ATS, inklusive godkänt datum, administratören som godkände åtgärden, åtgärden, statusen och antalet.

  Status kan vara:

  - **Startad**: åtgärd aktive ras.
  - **Köade**: reparation är i kö för att minska antalet e-postmeddelanden.
  - **Pågår**: det pågår.
  - **Slutfört**: begränsning av alla avhjälpda e-postmeddelanden har antingen genomförts eller med fel.
  - **Misslyckades**: ingen åtgärd lyckades.

  Det är bara att lösa in e-postmeddelanden som kan åtgärdas genom att rensa varje e-postmeddelande. Från de totala avhjälpade e-postmeddelandena, lyckade och misslyckade begränsningarna rapporteras.

  - **Lyckades**: den önskade åtgärden i avhjälpade e-postmeddelanden har gjorts. Till exempel: en administratör vill ta bort e-postmeddelanden från post lådor, så administratören tar bort e-postmeddelandena. Om det inte går att hitta en åtgärd med e-post i originalmappen efter åtgärden är statusen klar.

  - **Fel**: den önskade åtgärden på avhjälpade e-postmeddelanden misslyckades. Till exempel: en administratör vill ta bort e-postmeddelanden från post lådor, så administratören tar bort e-postmeddelandena. Om det finns ett åtgärdat e-postmeddelande som fortfarande hittas i post lådan efter åtgärden har statusen visats som misslyckad.

  Markera ett objekt i åtgärds loggen för att Visa reparations information. Om informationen säger "lyckades" eller "finns inte i post lådan", så har den redan tagits bort från post lådan. Ibland uppstår ett systemfel under reparationen. I dessa fall är det en bra idé att försöka igen.

  Om du reparerar stora satser kan du också exportera meddelanden om att få reparation via e-post och meddelanden som har åtgärd ATS i händelse loggar. Export gränsen höjs till 100K-poster.

  Reparation är ett kraftfullt verktyg för att minska riskerna och adressera misstänkta e-postmeddelanden. Det hjälper till att skydda en organisation.
