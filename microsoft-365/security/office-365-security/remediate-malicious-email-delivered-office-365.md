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
description: Hotreparation
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f623957a79ccd76702482cd23b4d8ce219603f6
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166885"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Åtgärda skadlig e-post som levereras i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-    [Microsoft Defender för Office 365 abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)

Åtgärd innebär att vidta en föreskriven åtgärd mot ett hot. Skadliga e-postmeddelanden som skickas till organisationen kan rensas antingen av systemet, via autorensning utan timme (ZAP) eller av säkerhetsgrupper genom åtgärder som att flytta till *Inkorgen,* flytta till *skräppost,* gå till borttagna *objekt,* mjuk borttagning eller permanent *borttagning.* Med Microsoft Defender för Office 365 P2/E5 kan säkerhetsteam åtgärda hot via e-post och samarbete med hjälp av manuell och automatiserad undersökning.

> [!NOTE]
> För att åtgärda skadlig e-post behöver säkerhetsteam den *sök- och rensningsroll* som de har tilldelats. Rolltilldelning utförs via behörigheter i säkerhets- och efterlevnadscentret.

## <a name="what-you-need-to-know-before-you-begin"></a>Vad du behöver veta innan du börjar

Administratörer kan vidta nödvändiga åtgärder för e-postmeddelanden, men för  att få åtgärderna godkända måste de ha tilldelats sök- och rensningsrollen via behörigheter **i Säkerhets- &** \> **Efterlevnadscenter.** Utan rollen "sök och rensa" som har lagts till i rollgrupperna kan de inte utföra åtgärden.

## <a name="manual-and-automated-remediation"></a>Manuell och automatiserad åtgärd

*Manuell sökning* sker när säkerhetsteam identifierar hot manuellt med hjälp av sök- och filtreringsfunktionerna i Threat Explorer. Manuell e-postreparation kan utlösas via valfri e-postvy *(skadlig* kod, *phish* eller *all* e-post) när du har identifierat en uppsättning e-postmeddelanden som behöver åtgärdas.

> [!div class="mx-imgBorder"]
> [![Manuell licens i Office 365 Threat Explorer på datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Säkerhetsteam kan använda Hotutforskaren för att välja e-postmeddelanden på flera sätt:

- Välj e-postmeddelanden för hand: Använd filter i olika vyer. Välj upp till 100 e-postmeddelanden att åtgärda.

- Frågeval: Markera en hel fråga med hjälp av den översta **knappen Markera** alla. Samma fråga visas också i information om inskickade e-postmeddelanden i åtgärdscenter.

- Frågeval med undantag: Ibland vill säkerhetsåtgärder grupper åtgärda e-postmeddelanden genom att markera en hel fråga och exkludera vissa e-postmeddelanden från frågan manuellt. För att göra det kan en administratör använda kryssrutan Markera **alla och rulla** nedåt för att utesluta e-postmeddelanden manuellt. Frågan kan innehålla högst 1 000 e-postmeddelanden. Det maximala antalet undantag är 100.

När e-postmeddelanden har valts via Hotutforskaren kan du börja åtgärda genom att vidta direkta åtgärder eller genom att köa e-postmeddelanden för en åtgärd:

- Direktgodkännande: När åtgärder som att flytta till Inkorgen, gå till *skräppost,* flytta till borttagna *objekt,* mjuk borttagning eller permanent borttagning väljs av säkerhetspersonalen som har rätt behörighet och nästa steg i åtgärden följs, så utförs den valda åtgärden.   En tillfällig utfällning visar den åtgärd som pågår.

- Tvåstegsgodkännande: Åtgärden "Lägg till för åtgärd" kan vidtas av administratörer som inte har rätt behörighet eller som måste vänta på att utföra åtgärden. I det här fallet läggs de riktade e-postmeddelandena till i en åtgärdsbehållare. Godkännande krävs innan åtgärd utförs.

**Automatiserade undersöknings- och** svarsåtgärder utlöses av varningar eller säkerhetsåtgärder från Threat Explorer. Dessa kan omfatta rekommenderade åtgärder som måste godkännas av ett team för säkerhetsåtgärder. De här åtgärderna finns på **fliken Åtgärd** i den automatiska undersökningen.

> [!div class="mx-imgBorder"]
> [![E-post med skadlig programvara på sidan "Zapped" visar tid för Zap-körning.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alla åtgärder (antingen direkt godkännande eller tvåstegsgodkännande) som skapats i Hotutforskaren samt godkända åtgärder från automatiserade undersökningar visas i Åtgärdscenter. Du kommer åt dem via den vänstra **navigeringspanelen** under \> **Granska åtgärdscenter.**

> [!div class="mx-imgBorder"]
> [![Åtgärdscenter med en lista över hot per datum och allvarlighetsgrad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Åtgärdscenter visar alla åtgärder för de senaste 30 dagarna. Åtgärder som utförs i Threat Explorer listas av namnet som teamet för säkerhetsåtgärder gav när åtgärd skapades. Åtgärder som vidtas genom automatiserade undersökningar har rubriker som börjar med den relaterade aviseringen som utlöser undersökningen, till exempel "Zap e-postkluster... ".

Öppna ett åtgärdsobjekt för att visa information om det, inklusive dess namn, skapandedatum, beskrivning, allvarlighetsgrad och status för hot. Dessutom visas följande två flikar.

- **Fliken** Postinskickning: Visar antalet e-postmeddelanden som skickats via Threat Explorer eller automatiserade undersökningar som ska åtgärdas. De här e-postmeddelandena kan vara åtgärdsbara eller inte kan vidtas.

  > [!div class="mx-imgBorder"]
  > [![Åtgärdscenter med åtgärdsbara och inte åtgärdbara hot.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Åtgärdbar:** E-postmeddelanden på följande molnpostlådeplatser kan åtgärdas och flyttas:
    - Inkorgen
    - Skräppost
    - Borttaget mapp
    - Mjuk borttaget mapp

      > [!NOTE]
      > För närvarande kan endast en användare med åtkomst till postlådan återställa objekt från en mjukt borttagna mapp.

  - **Ingen åtgärd kan** åtgärdas: E-postmeddelanden på följande platser kan inte åtgärdas eller flyttas i åtgärder:
    - Karantän
    - Permanent borttaget mapp
    - Lokal/extern
    - Misslyckades/ignorerades

  Misstänkta meddelanden kategoriseras som antingen åtgärdsbara eller inte går att åtgärda. I de flesta fall kombinerar åtgärdsbara och icke-åtgärdsbara meddelanden det totala antalet skickade meddelanden. Men i sällsynta fall kanske detta inte är sant. Det här kan inträffa på grund av systemfördröjningar, tidsgränser eller meddelanden som upphört att gälla. Meddelandena upphör att gälla baserat på organisationens bevarandeperiod för Hotutforskaren.

  Om du inte åtgärdar gamla meddelanden efter organisationens bevarandeperiod för Hot Explorer, är det lämpligt att försöka åtgärda objekt om du ser antal inkonsekvenser. För systemfördröjningar uppdateras åtgärdsuppdateringar normalt inom några timmar.

  Om organisationens lagringstid för e-post i Threat Explorer är 30 dagar och du åtgärdar e-postmeddelanden 29–30 dagar, är det inte alltid räkningen för e-postinskickning som räknas. E-postmeddelandena kan redan ha börjat flytta från lagringstiden.

  Om åtgärder har fastnat i statusen "Pågår" ett tag beror det förmodligen på systemfördröjningar. Det kan ta upp till några timmar att åtgärda. Det kan visas variationer i antalet meddelanden som skickas, eftersom vissa av e-postmeddelandena kanske inte hade inkluderats i frågan i början av åtgärder på grund av systemfördröjningar. Det är en bra idé att försöka åtgärda detta i sådana fall.

  > [!NOTE]
  > För bästa resultat bör åtgärder utföras i grupper om 50 000 eller färre.

  Endast åtgärdsbara e-postmeddelanden vidta åtgärder under åtgärder. Icke-åtgärdsbara e-postmeddelanden kan inte åtgärdas av Office 365-e-postsystemet, eftersom de inte lagras i molnbaserade postlådor.

  Administratörer kan vidta åtgärder för e-postmeddelanden i karantän om det behövs, men de e-postmeddelandena upphör att vara i karantän om de inte rensas manuellt. E-postmeddelanden som sätts i karantän på grund av skadligt innehåll är inte tillgängliga för användare, så säkerhetspersonalen behöver inte vidta någon åtgärd för att ta bort hot i karantän. Om e-postmeddelandena är lokala eller externa kan användaren kontaktas för att åtgärda det misstänkta e-postmeddelandet. Administratörer kan också använda separata e-postservrar/säkerhetsverktyg för borttagning. Dessa e-postmeddelanden kan identifieras genom att använda *leveransplatsen = on-prem externt* filter i Threat Explorer. För misslyckade eller släppta e-postmeddelanden, eller e-post som inte är tillgänglig för användare, finns det inte några e-postmeddelanden att minimera, eftersom dessa e-postmeddelanden inte når postlådan.

  Följande bild visar hur en inskickning ser ut i Åtgärdscenter. En åtgärd kan innehålla flera inskickade objekt. Om flera åtgärder godkänns genom en automatiserad undersökning visas varje åtgärd för e-post- eller e-postkluster på samma åtgärd som för en annan inskicking.

  > [!div class="mx-imgBorder"]
  > [![Utfällpanel för ZAP-e-postkluster.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Välj ett objekt för e-postinskickning för att visa information om den här åtgärd, till exempel frågan (när åtgärder utlöses genom automatiska undersökningar eller Hotutforskaren genom att välja en fråga) och start- och sluttid för åtgärd. Dessutom visas en lista över meddelanden som skickats för åtgärd. När meddelandena flyttas från lagringstiden för Hotutforskaren försvinner meddelandena från den här listan. Listan visar även enskilda meddelanden som kan åtgärdas.

- **Åtgärdsloggar:** Den här fliken visar åtgärdade meddelanden, inklusive godkänt datum, administratör som godkänt åtgärden, åtgärden, status och antal.

  Status kan vara:

  - **Startad:** Åtgärd utlöses.
  - **I kö:** Åtgärd är i kö för åtgärder av e-postmeddelanden.
  - **Pågående:** Åtgärder är under utveckling.
  - **Slutförd:** Minskning av alla remedierbara e-postmeddelanden har slutförts eller med vissa fel.
  - **Misslyckades:** Inga åtgärder lyckades.

  Eftersom endast åtgärdsbara e-postmeddelanden kan åtgärdas visas rensningen för varje e-postmeddelande som lyckades eller misslyckades. Bland de totala åtgärdsbara e-postmeddelandena rapporteras lyckade och misslyckade minskningar.

  - **Lyckades:** Önskad åtgärd för åtgärdsbara e-postmeddelanden har utförts. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så administratören vidtar åtgärder för mjuk borttagning av e-postmeddelanden. Om ett åtgärdat e-postmeddelande inte hittas i den ursprungliga mappen efter att åtgärden har vidtagits, visas statusen som lyckades.

  - **Fel:** Den åtgärd du önskade för åtgärdsbara e-postmeddelanden misslyckades. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så administratören vidtar åtgärder för mjuk borttagning av e-postmeddelanden. Om ett åtgärdat e-postmeddelande fortfarande finns i postlådan när åtgärden har vidtagits, visas statusen som misslyckad.

  Markera ett objekt i åtgärdsloggen för att visa åtgärdsinformation. Om informationen säger "lyckades" eller "hittades inte i postlådan" har objektet redan tagits bort från postlådan. Ibland finns det ett stavfel under åtgärd. I sådana fall är det en bra idé att försöka åtgärda det igen.

  Om du åtgärdar stora batchar kan du också exportera meddelanden för åtgärd via inskickad e-post och meddelanden som har åtgärdats via åtgärdsloggar. Exportgränsen ökar till 100 000 poster.

  Åtgärd är ett kraftfullt verktyg för att minimera hot och hantera misstänkta e-postmeddelanden. Det hjälper till att skydda organisationen.
