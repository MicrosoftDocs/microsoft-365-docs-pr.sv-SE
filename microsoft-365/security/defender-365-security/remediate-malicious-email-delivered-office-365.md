---
title: Åtgärda skadlig e-post som levererats i Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Åtgärder för hot
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 202ebc8b79368c8d41fd3727b67359ddcb8a08fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073194"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Åtgärda skadlig e-post som levereras i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

Åtgärd innebär att vidta en bestämt åtgärd mot ett hot. Skadlig e-post som skickas till din organisation kan tas bort antingen av systemet, via nolltimmars automatisk rensning (ZAP) eller av säkerhetsgrupper genom åtgärder som att flytta till Inkorgen *,* gå till *skräppost,* gå till borttagna *objekt,* mjuk borttagning eller ta bort permanent *.*  Med Microsoft Defender för Office 365 P2/E5 kan säkerhetsteam åtgärda hot i e-post- och samarbetsfunktionerna genom manuell och automatiserad undersökning.

> [!NOTE]
> För att åtgärda skadlig e-post behöver säkerhetsteamen *tilldelad sök-* och rensningsrollen. Rolltilldelning utförs via behörigheter i säkerhets- och efterlevnadscentret.

## <a name="what-you-need-to-know-before-you-begin"></a>Vad du behöver veta innan du börjar

Administratörer kan vidta nödvändiga åtgärder i e-postmeddelanden, men för  att få åtgärderna godkända måste de ha tilldelats sök- och rensningsrollen via behörigheter **för säkerhets-** & \> **efterlevnadscenter.** Utan rollen "sök och rensa" som har lagts till i en av rollgrupperna kan de inte utföra åtgärden.

## <a name="manual-and-automated-remediation"></a>Manuell och automatiserad åtgärd

*Manuell sökning* sker när säkerhetsgrupper identifierar hot manuellt med hjälp av sök- och filtreringsfunktionerna i Threat Explorer. Åtgärder för manuell e-post kan utlösas via valfri e-postvy *(skadlig* kod, *phish* eller *all* e-post) när du har identifierat en uppsättning e-postmeddelanden som behöver åtgärdas.

> [!div class="mx-imgBorder"]
> [![Manuell jäning i Office 365 Threat Explorer på datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Säkerhetsteam kan använda Hotutforskaren för att välja e-postmeddelanden på flera olika sätt:

- Välja e-postmeddelanden för hand: Använd filter i olika vyer. Välj upp till 100 e-postmeddelanden att åtgärda.

- Frågeval: Markera en hel fråga genom att klicka på **knappen Markera allt** högst upp. Samma fråga visas också i information om inskickade e-postmeddelanden i åtgärdscenter.

- Frågeval med undantag: Ibland vill säkerhetsåtgärder grupper åtgärda e-postmeddelanden genom att välja en hel fråga och exkludera vissa e-postmeddelanden från frågan manuellt. För att göra det kan en administratör använda kryssrutan Markera **alla och rulla** nedåt för att utesluta e-postmeddelanden manuellt. Frågan kan innehålla högst 1 000 e-postmeddelanden. Det maximala antalet undantag är 100.

När du har valt e-postmeddelanden i Hotutforskaren kan du starta åtgärden genom att vidta direktåtgärder eller köa e-postmeddelanden för en åtgärd:

- Direktgodkännande: När åtgärder som att flytta till Inkorgen , gå till  skräppost *,* flytta till borttagna *objekt,* mjuk borttagning eller permanent borttagning markeras av säkerhetspersonalen som har rätt behörighet och nästa steg i åtgärden följs, påbörjas den valda åtgärden.  En tillfällig utfällning visar den pågående åtgärd.

- Tvåstegsgodkännande: Åtgärden "Lägg till i åtgärd" kan vidtas av administratörer som inte har rätt behörighet eller som behöver vänta på att åtgärden ska utföras. I det här fallet läggs riktade e-postmeddelanden till i en åtgärdsbehållare. Godkännande krävs innan reparationen utförs.

**Automatiserade undersöknings- och** svarsåtgärder utlöses av varningar eller av säkerhetsåtgärder grupper från Threat Explorer. Dessa kan omfatta rekommenderade åtgärdsåtgärder som måste godkännas av ett team för säkerhetsåtgärder. De här åtgärderna finns på fliken **Åtgärd** i den automatiska undersökningen.

> [!div class="mx-imgBorder"]
> [![E-post med skadlig programvara på sidan "Zapped" som visar tid för Zap-körning.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alla åtgärder (antingen direkt godkännande eller tvåstegsgodkännande) som skapats i Hotutforskaren samt godkända åtgärder från automatiserade undersökningar visas i Åtgärdscenter. Du kommer åt dem  via den vänstra navigeringspanelen under \> **Granska Åtgärdscenter**.

> [!div class="mx-imgBorder"]
> [![Åtgärdscenter med en lista över hot efter datum och allvarlighetsgrad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Åtgärdscenter visar alla åtgärder för de senaste 30 dagarna. Åtgärder som utförs i Hotutforskaren listas efter namnet som teamet för säkerhetsåtgärder gav när reparationen skapades. Åtgärder som vidtas genom automatiska undersökningar har rubriker som börjar med den relaterade aviseringen som utlöste undersökningen, till exempel "Zap email cluster... ".

Öppna ett åtgärdsobjekt för att visa information om det, inklusive dess namn, skapandedatum, beskrivning, allvarlighetsgrad och status för hot. Dessutom visas följande två flikar.

- **Fliken för inskick** av e-post: Visar antalet e-postmeddelanden som skickats via Hotutforskaren eller automatiserade undersökningar som ska åtgärdas. Dessa e-postmeddelanden kan vara åtgärdsbara eller inte åtgärdsbara.

  > [!div class="mx-imgBorder"]
  > [![Åtgärdscenter med åtgärdsbara och inte åtgärdbara hot.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Åtgärd kan** åtgärdas: E-postmeddelanden på följande molnbaserade postlådeplatser kan åtgärdas och flyttas:
    - Inkorgen
    - Skräppost
    - Borttaget mapp
    - Mjuk borttaget mapp

      > [!NOTE]
      > För närvarande kan endast en användare med åtkomst till postlådan återställa objekt från en mjuk borttagna mapp.

  - **Inte åtgärdsbar:** E-postmeddelanden på följande platser kan inte åtgärdas eller flyttas i åtgärder:
    - Karantän
    - Mappen Borttaget
    - Lokalt/externt
    - Misslyckades/ignorerades

  Misstänkta meddelanden kategoriseras som antingen åtgärdsbara eller icke-åtgärdsbara. I de flesta fall är de åtgärderbara och icke-remedierbara meddelandena samma som det totala antalet skickade meddelanden. Men i sällsynta fall kanske det inte är sant. Det här kan inträffa på grund av systemfördröjningar, tidsgränser eller utgångna meddelanden. Meddelanden upphör att gälla baserat på lagringstiden för hotutforskaren för din organisation.

  Om du inte åtgärdar gamla meddelanden efter att organisationen har kvarhållningstiden för Hotutforskaren är det lämpligt att försöka åtgärda objekt om du ser flera inkonsekvenser. För systemfördröjningar uppdateras vanligtvis åtgärdsuppdateringar inom några timmar.

  Om organisationens bevarandeperiod för e-post i Threat Explorer är 30 dagar och du åtgärdar e-postmeddelanden 29–30 dagar, kanske antalet e-postinskickade inskickade meddelanden inte alltid adderar. E-postmeddelandena kan redan ha börjat flyttas från lagringstiden.

  Om åtgärder har fastnat i läget "Pågår" ett tag beror det sannolikt på systemfördröjningar. Det kan ta upp till några timmar att åtgärda. Du kan se variationer i antalet e-postinskickade meddelanden eftersom vissa av e-postmeddelandena kanske inte hade inkluderats i frågan i början av åtgärder på grund av systemfördröjningar. Det är en bra idé att försöka åtgärda det i sådana fall.

  > [!NOTE]
  > För bästa resultat bör åtgärder utföras i grupper om 50 000 eller färre.

  Endast åtgärdsbara e-postmeddelanden åtgärdas under åtgärder. Icke-remedierbara e-postmeddelanden kan inte åtgärdas av Office 365-e-postsystemet, eftersom de inte lagras i molnbaserade postlådor.

  Administratörer kan vidta åtgärder för e-postmeddelanden i karantän om det behövs, men de e-postmeddelandena löper ut från karantänen om de inte rensas manuellt. E-postmeddelanden som sätts i karantän på grund av skadligt innehåll är inte tillgängliga för användarna, så säkerhetspersonalen behöver inte vidta någon åtgärd för att ta bort hot i karantän. Om e-postmeddelandena finns lokalt eller externt kan användaren kontaktas för att åtgärda det misstänkta e-postmeddelandet. Eller också kan administratörerna använda separata e-postservrar/säkerhetsverktyg för borttagning. Dessa e-postmeddelanden kan identifieras genom att använda *leveransplatsen = on-prem* externt filter i Threat Explorer. För misslyckade eller nedslyckade e-postmeddelanden, eller e-post som inte kan nås av användarna, finns det inte någon e-post att minimera, eftersom dessa e-postmeddelanden inte når postlådan.

  Följande bild visar hur en inskickning ser ut i Åtgärdscenter. En åtgärd kan innehålla flera inlämningar. Om flera åtgärder godkänns genom en automatiserad undersökning visas varje åtgärd för e-post- eller e-postkluster i samma åtgärd som en annan inskicking.

  > [!div class="mx-imgBorder"]
  > [![Utfällpanel för ZAP-e-postkluster.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Markera ett objekt för e-postinskickning om du vill visa information om den här reparationen, till exempel frågan (när åtgärder utlöses genom automatiska undersökningar eller Hotutforskaren genom att välja en fråga) och start- och sluttid för åtgärder. Dessutom visas en lista över meddelanden som har skickats för åtgärd. När meddelanden flyttas från lagringsperioden i Threat Explorer försvinner meddelandena från den här listan. Listan visar även enskilda meddelanden som kan åtgärdas.

- **Åtgärdsloggar:** På den här fliken visas de meddelanden som har åtgärdats, inklusive godkänt datum, administratör som godkänt åtgärden, åtgärden, status och antal.

  Status kan vara:

  - **Startad**: Åtgärd utlöses.
  - **I kö:** Åtgärd är i kö för åtgärder av e-postmeddelanden.
  - **Pågående :** Minskningar pågår.
  - **Slutförd**: Minskning av alla reparerbara e-postmeddelanden har slutförts eller med vissa fel.
  - **Misslyckades**: Inga åtgärder lyckades.

  Eftersom endast åtgärdsbara e-postmeddelanden kan åtgärdas, visas rensningen för varje e-postmeddelande som lyckades eller misslyckades. Från de totala åtgärdsbara e-postmeddelandena rapporteras lyckade och misslyckade åtgärder.

  - **Framgång:** Önskad åtgärd för åtgärdsbara e-postmeddelanden har utförts. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så administratören använder mjuk borttagning av e-postmeddelanden. Om ett åtgärdat e-postmeddelande inte hittas i den ursprungliga mappen efter att åtgärden har vidtagits, visas statusen som lyckades.

  - **Fel:** Den åtgärd du ville vidta för att åtgärda e-postmeddelanden misslyckades. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så administratören använder mjuk borttagning av e-postmeddelanden. Om ett åtgärdat e-postmeddelande finns kvar i postlådan efter att åtgärden har vidtagits, visas status som misslyckad.
  
  - **Redan i mål:** Önskad åtgärd har redan vidtagits för e-postmeddelandet ELLER så fanns e-postmeddelandet redan på målplatsen. Till exempel: Ett e-postmeddelande togs bort mjukt av administratören via Utforskaren på dag ett. Sedan visas liknande e-postmeddelanden dag 2, som återigen tas bort mjukt av administratören. Medan de här e-postmeddelandena markeras väljer administratören vissa e-postmeddelanden från dag ett som redan är mjuka borttagna. Nu kommer dessa e-postmeddelanden inte att ageras igen, de visas bara som "redan på destinationen", eftersom ingen åtgärd har vidtagits för dem eftersom de fanns på målplatsen.

  Markera ett objekt i åtgärdsloggen om du vill visa åtgärdsinformation. Om informationen säger "lyckades" eller "hittades inte i postlådan" har objektet redan tagits bort från postlådan. Ibland kan det finnas ett fel under en åtgärd. I sådana fall är det en bra idé att försöka åtgärda det.

  Om du åtgärdar stora batchar kan du också exportera meddelandena för åtgärd via e-postinskick och meddelanden som har åtgärdats via åtgärdsloggar. Exportgränsen ökas till 100 000 poster.

Säkerhetsteamet kan ta upp till 50 samtidiga manuella åtgärder. Det finns dock ingen gräns för automatisk undersökning och svarsåtgärder.

  Åtgärd är ett kraftfullt verktyg för att minska hot och åtgärda misstänkta e-postmeddelanden. Det hjälper till att skydda organisationen.
