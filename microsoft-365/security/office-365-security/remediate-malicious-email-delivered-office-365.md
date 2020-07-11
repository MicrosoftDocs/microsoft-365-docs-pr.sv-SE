---
title: Åtgärda skadlig e-post som levererades i Office 365
author: msfttracyp
ms.author: tracyp
manager: ''
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Åtgärder mot hot
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 6c1a07c6de55022797f284eb471d8ad054cd325e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101706"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Åtgärda skadlig e-post som levererades i Office 365

Sanering innebär att vidta en förbjuden åtgärd mot ett hot. Skadliga e-postmeddelanden som skickas till din organisation kan rensas antingen av systemet, genom ZAP (Zero-hour Auto-Purge) eller av säkerhetsteamen genom reparationsåtgärder som att flytta till inkorgen, flytta till skräppost, flytta till mappen borttagna objekt, ta bort det mjukt eller ta bort det. Office Advanced Threat Protection (Office ATP) P2 / E5 erbjuder säkerhetsoperationer team möjlighet att medla hot i e-post och samarbetsfrågor genom manuell jakt och automatiserade utredningar.

> [!NOTE]
> För att säkerhetsteam ska kunna åtgärda e-postmeddelanden måste de ha en sök- och rensningsroll tilldelad till dem. Rolltilldelning görs med behörigheter i säkerhets- och efterlevnadscenter. 

## <a name="what-you-need-to-know-before-you-begin"></a>Vad du behöver veta innan du börjar

Om du vill utföra vissa åtgärder, till exempel visa meddelanderubriker eller hämta e-postmeddelandeinnehåll, måste du ha en ny roll som kallas *Förhandsgranska tillagd* i en annan lämplig rollgrupp. I följande tabell klargörs nödvändiga roller och behörigheter.

|Aktivitet  |Rollgrupp |Förhandsversionsroll behövs?  |
|---------|---------|---------|
|Använda Threat Explorer (och realtidsidentifieringar) för att analysera hot     |Global administratör <br> Säkerhetsadministratör <br> Säkerhetsläsare     | Nej   |
|Använda Threat Explorer (och realtidsidentifieringar) för att visa rubriker för e-postmeddelanden samt förhandsgranska och hämta e-postmeddelanden i karantän    |Global administratör <br> Säkerhetsadministratör <br>Säkerhetsläsare   |       Nej  |
|Använda Threat Explorer för att visa rubriker och hämta e-postmeddelanden som levereras till postlådor     |Global administratör <br>Säkerhetsadministratör <br> Säkerhetsläsare <br> Förhandsgranska   |   Ja      |

> [!NOTE]
> *Förhandsversion* är en roll och inte en rollgrupp. Förhandsrollen måste läggas till i en befintlig rollgrupp för Office 365. Rollen Global administratör tilldelas microsoft 365-administrationscentret ( [https://admin.microsoft.com](https://admin.microsoft.com) ) och rollerna Säkerhetsadministratör och säkerhetsläsare tilldelas i Säkerhets- & Compliance Center ( [https://protection.office.com](https://protection.office.com) ). Mer information om roller och behörigheter finns [i Behörigheter i Säkerhets- & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Administratörer kan vidta nödvändiga åtgärder för e-postmeddelanden, men för att få sin åtgärd godkänd måste de ha rollen "Sök och rensa" tilldelad dem via Security and Compliance Center >-behörigheter.

## <a name="manual-and-automated-remediation"></a>Manuell och automatiserad reparation

**Manuell jakt** sker när säkerhetsteam identifierar hot manuellt med hjälp av sök- och filtreringsfunktionerna i Threat Explorer. Manuell reparation av e-postmeddelanden kan utlösas via en e-postvy (Malware, Phish eller All email) efter att ha hittat en uppsättning e-postmeddelanden som måste åtgärdas.

[Manuell jakt i Office 365 Threat Explorer efter datum.](../../media/tp-RemediationArticle1.png)

Valet av e-postmeddelanden kan göras på flera sätt via Threat Explorer: 

1. Välja e-post för hand: Det innebär att säkerhetsoperationsteam kan använda filter i respektive vy och välja några e-postmeddelanden från Threat Explorer som måste åtgärdas. Den övre gränsen för att välja e-post är hundra (100). Säkerhetsoperationsteam kan inte välja fler än hundra e-postmeddelanden manuellt. 

2. Val av frågor: Säkerhetsoperationsteam kan välja en hel fråga med hjälp av den översta knappen "välj alla". Samma fråga visas också i information om e-postinlämning i Åtgärdscenter. 

3. Val av frågor med undantag: Det kan finnas tillfällen då säkerhetsoperationsteam bestämmer sig för att åtgärda e-postmeddelanden genom att både välja en hel fråga och utesluta några e-postmeddelanden från frågan, manuellt. För att göra det kan en administratör använda kryssrutan "Markera alla" och rulla nedåt för att utesluta några e-postmeddelanden manuellt. Det maximala antalet e-postmeddelanden som frågan kan innehålla är 1 000 (1 000) och det maximala antalet undantag är hundra (100), i det här fallet.

När e-postmeddelanden har valts från Threat Explorer kan skapande av reparation börja med att vidta direkta åtgärder eller genom att köa e-postmeddelanden för en åtgärd: 

1. Direkt godkännande: När åtgärder som "Flytta till inkorgen", "Flytta till skräp", "Flytta till borttagna objekt", "Mjuk borttagning", "Hård borttagning" väljs av säkerhetspersonal med lämpliga behörigheter och nästa steg följs tills reparation skapas, börjar reparationsprocessen att utföra en markerad åtgärd. Ett tillfälligt utfällbart utfällbart alternativ visar pågående reparation. 

2. Två steg godkännande: "Lägg till reparation" åtgärd kan vidtas av en administratör som inte har rätt behörighet eller som behöver vänta längre för att utföra åtgärden. I det här fallet utförs inte reparationsåtgärden direkt. I stället läggs e-postmeddelanden till i en reparationsbehållare som måste godkännas för att köras. Tills reparationen har godkänts kommer e-postmeddelandet inte att åtgärdas. När reparationen har godkänts kommer åtgärder att vidtas på e-postmeddelandet. 

**Automatiska åtgärder för undersökning och svar (AIR)** utlöses av aviseringar eller av säkerhetsoperationsgrupper inifrån Threat Explorer. De kan innehålla några rekommenderade reparationar som måste godkännas av säkerhetsoperationsgrupper. Dessa åtgärder för reparation finns på fliken Åtgärd i den automatiska undersökningen.  

[E-post med skadlig kod är Zapped sida som visar tidpunkten för Zap utförande.](../../media/tp-RemediationArticle3.png)

Alla avhjälpningar (antingen direkt godkännande eller tvåstegsgodkännande) som skapats genom Threat Explorer, och godkända åtgärder som kommer från automatiserade undersökningar, visas i Åtgärdscenter, som kan nås via den vänstra navigeringen under * Review * > **Action Center**.

[Åtgärdscenter med en lista över hot efter datum och allvarlighetsgrad.](../../media/tp-RemediationArticle4.png)

Åtgärdscenter visar alla reparationsåtgärder under de senaste 30 dagarna. Åtgärder som vidtas via Explorer visas med samma namn som tillhandahålls av säkerhetsoperationsteamen när reparationen skapades. Åtgärder som vidtas genom automatiserade undersökningar visas med titlar som börjar med den relaterade aviseringen som utlöste undersökningen – till exempel "Zap e-postkluster...".

Varje reparationsobjekt kan öppnas för att visa information om det. När ett reparationsobjekt öppnas visas grundläggande reparationsinformation, reparationsnamn, skapandedatum, beskrivning, allvarlighetsgrad för hot och status. Den visar också två flikar. 

1. **Fliken Skicka in e-post**: Det här är antalet e-postmeddelanden som skickas in via Threat Explorer eller automatiska undersökningar som ska åtgärdas. Dessa e-postmeddelanden kan vara: 

[Åtgärdscentret med användbara och inte användbara hot.](../../media/tp-RemediationArticle5.png)

**Användbart:** E-postmeddelanden i följande platser i molnpostlådan kan hanteras och flyttas, dvs. 
  - Inkorg 
  - Skräp  
  - Borttagen mapp 
  - Mjuk borttagen mapp 

[!NOTE]
> För närvarande kan bara en slutanvändare med åtkomst till postlådan återställa objekt från en mjuk borttagningsmapp.

**Inte användbart**: E-postmeddelanden på följande platser kan inte hanteras eller flyttas som en del av e-poståtgärder, dvs e-postmeddelanden i icke-avhjälpbara kategori kan inte flyttas antingen i den icke-avhjälpbara kategorin, eller i avhjälpbara. Platser som inte kan åtgärdas är: 

  - Karantän 
  - Svår borttagen mapp
  - On-prem / extern 
  - Misslyckade /tappade misstänkta meddelanden som skickas kategoriseras som antingen avhjälpbara eller icke-avhjälpbara. I de flesta fall bör reparationsbara och icke-åtgärdbara meddelanden lägga till upp till de totala meddelanden som skickas. Det kan dock finnas sällsynta fall där skickade meddelanden inte kan öka summan av avhjälpbara och icke-avhjälpbara objekt, och kan vara antingen högre eller lägre än det totala antalet skickade meddelanden. Detta kan inträffa på grund av systemfördröjningar, time-outs eller utgångna meddelanden. Meddelanden upphör att gälla baserat på Explorers kvarhållningsperiod för din organisation. 

Om du inte åtgärdar gamla meddelanden efter organisationens explorer-lagringsperiod, är det lämpligt att åtgärda objekt på nytt om du ser inkonsekvenser i siffror. För systemfördröjningar uppdateras reparationsuppdateringar vanligtvis inom några timmar. 

Om organisationens kvarhållningsperiod för e-post i Explorer är 30 dagar och du åtgärdar e-postmeddelanden som går 29-30 dagar tillbaka, kanske antalet postöverföringar inte alltid summerar eftersom e-postmeddelandena redan har börjat flyttas från kvarhållningsperioden. 

Om reparationar har fastnat i tillståndet "Pågår" ett tag beror det sannolikt på systemfördröjningar. Det kan ta upp till några timmar att åtgärda. Det kan finnas en variant som observerats i antalet postinlämningar eftersom vissa e-postmeddelanden inte var en del av frågan när du påbörjade reparation, på grund av systemfördröjningar. Det är en bra idé att försöka åtgärda i sådana fall.  

För bästa resultat, sanering bör göras i mindre partier på cirka 50k eller mindre e-post.  

Av alla e-postmeddelanden i postinlämning är avhjälpbara e-postmeddelanden de enda som kommer att åtgärdas under reparation. E-postmeddelanden som inte kan repareras kan inte åtgärdas av e-postsystemet i Office 365, eftersom de inte lagras i molnpostlådor. 

För e-postmeddelanden som finns i karantän kan administratörer gå till karantän för att vidta åtgärder på dessa e-postmeddelanden om det behövs, men e-postmeddelandena upphör att gälla ur karantän om de inte rensas manuellt. E-postmeddelanden i karantän på grund av skadligt innehåll är inte tillgängliga för slutanvändare, så säkerhetspersonal behöver inte vidta några specifika åtgärder för att bli av med hotet i karantän. Om e-postmeddelandena är prem eller externa kan slutanvändaren kontaktas för att adressera det misstänkta e-postmeddelandet eller använda separata e-postserver/säkerhetsverktyg för borttagning. Dessa e-postmeddelanden kan identifieras genom att tillämpa leveransplats = on-prem / externt filter i Threat Explorer. För misslyckade eller tappade e-postmeddelanden, eller e-post som inte är tillgänglig för slutanvändaren, bör det inte finnas e-post för att minska, eftersom de inte når postlådan. 

Så här visas en inlämning i Åtgärdscenter. En reparation kan innehålla flera inlämningar. Om flera åtgärder godkänns genom en automatiserad undersökning visas varje e-post- eller e-postklusteråtgärd i samma reparation som en annan inlämning.

[ZAP e-post kluster utfällbara panel.](../../media/tp-RemediationArticle6.png)

Om du klickar på ett postöverföringsobjekt visas information om reparationen, till exempel frågan (när reparation utlöses genom automatiska undersökningar eller Threat Explorer genom att välja en fråga), starttid och sluttid för reparation. Den visar också en lista över meddelanden som har skickats för reparation. När meddelanden flyttas ut ur lagringsperioden för Utforskaren försvinner meddelandena från den här listan. I den här listan visas också enskilda meddelanden från listan som kan åtgärdas.

2. **Fliken Åtgärdsloggar**: På den här fliken visas resultatet av meddelanden som har åtgärdats, inklusive information som godkänt datum, godkännare (administratör som godkände åtgärden), åtgärd, status och antal.  

Status är den övergripande statusen för reparationen. Status kan vara: 

  - **Startad**: När en reparation utlöses. 
  - **Kö :** När reparationen är köade för att begränsa e-postmeddelanden. 
  - **Pågår**: När begränsningen pågår. 
  - **Slutförd:** När begränsningen på alla avhjälpbara e-postmeddelanden görs antingen framgångsrikt eller med vissa fel. 
  - **Misslyckades**: När inga åtgärder har slutförts. 

Eftersom endast avhjälpbara e-postmeddelanden kan åtgärdas, granskas varje e-post rensning som lyckad eller misslyckad. Från den totala avhjälpbara e-postmeddelanden, exponerar vi framgångsrika och misslyckade mildrande åtgärder. 

  - **Framgång**: När den önskade åtgärden på avhjälpbara e-postmeddelanden sker och matchar avsikten med admin. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så att de vidtar åtgärder för att ta bort e-postmeddelanden. Om ett e-postmeddelande som kan åtgärdas inte hittas i den ursprungliga mappen efter att åtgärden har vidtagits visas statusen som lyckad.  

  - **Fel:** När den önskade åtgärden för avhjälpbara e-postmeddelanden misslyckas. Till exempel: En administratör vill ta bort e-postmeddelanden från postlådor, så han vidtar åtgärder för att ta bort e-postmeddelanden. Om ett åtgärdsbart e-postmeddelande fortfarande finns i postlådan visas status som misslyckad. 

Om du klickar på ett objekt i åtgärdsloggen visas information om reparation. För lyckade objekt, om detaljerna säger, lyckades eller inte hittades i postlådan, betyder det att objektet redan har tagits bort från postlådan. Ibland finns det fel som inträffar på grund av ett systemfel under reparation, och i dessa fall är det en bra idé att försöka åtgärda.  

Reparation är ett kraftfullt verktyg för att minska hot och ta itu med misstänkta e-postmeddelanden. Det hjälper till att hålla en organisation trygg och säker.  

## <a name="more-info"></a>Mer information

Se [Undersöka skadlig e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

