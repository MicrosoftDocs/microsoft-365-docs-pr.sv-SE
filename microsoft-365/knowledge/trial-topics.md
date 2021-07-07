---
title: Köra en utvärderingsversion av Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du planerar och kör ett testpilotprogram för Microsoft Viva Topics i organisationen.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327147"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Köra en utvärderingsversion av Microsoft Viva Topics

I den här artikeln beskrivs hur du set up and run a trial pilot program to deploy Viva Topics to your organization. Den här artikeln rekommenderar även metodtips för utvärderingsversionen.

## <a name="sign-up-for-a-trial"></a>Registrera dig för en utvärderingsversion

Försök är offentligt tillgängliga från någon av följande källor. Utvärderingsversioner ger 25 användare tillgång till Viva Topics i 30 dagar.

- Produktsidan [Viva Topics](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- Administrationscenter för Microsoft 365 [](https://admin.microsoft.com)
    1.  Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
    2.  Gå till **Tjänster för**  >  **faktureringsköp.**
    3.  Rulla ned till **avsnittet** Tillägg.
    4.  På panelen **Ämnesupplevelser** väljer du **Detaljer**.
    5.  Välj **Hämta kostnadsfri utvärderingsversion**.
    6.  Bekräfta utvärderingsversionen genom att följa anvisningarna i guiden.

Du måste vara global Microsoft 365 eller faktureringsadministratör för att aktivera en utvärderingsversion.

> [!NOTE]
> Offentliga utvärderingsversioner kan bara läggas till en gång för Microsoft 365 klientorganisation.

### <a name="who-should-be-involved-in-a-trial"></a>Vem bör vara involverad i en utvärderingsversion

|Roll  |Aktivitet  |
|---------|---------|
|Microsoft 365 global administratör eller faktureringsadministratör  |   Aktivera utvärderingsversionen och tilldela licenser      |
|Microsoft 365 global administratör SharePoint administratör    |       Konfigurera Viva Ämnen och skapa ämnescentra  |
|Företagsanvändare     |   Utföra knowledge manager, ämnesdeltagare och ämneskonsumentroller      |

### <a name="before-you-activate-a-trial"></a>Innan du aktiverar en utvärderingsversion

Det är viktigt att planera för en effektiv utvärderingsversion av Viva Topics. Utvärderingsperioden är begränsad och måste omfatta upptäckt av ämnen och utforska ämneskvalitet, hantering och slutanvändarupplevelser.

#### <a name="discovery"></a>Upptäckt

Det finns två strategialternativ på hög nivå för konfiguration av ämnesidentifieringen under en utvärderingsversion:

- Indexera allt eller större delen av ditt SharePoint Online-innehåll.
   - Stora klientorganisationar kan ta upp till två veckor att helt indexera. Även om ämnen genereras stegvis under hela den här perioden kan fullständig indexering ta upp till hälften av utvärderingsperioden.
   - För klientorganisationar med en stor mängd data kan det här alternativet producera ett mycket stort antal ämnen, kanske tusentals.

- Identifiera en delmängd av dina SharePoint webbplatser för indexering.

Dessa strategier ger en balans mellan följande två faktorer:

- Ha tillräckligt med data för att skapa meningsfulla ämnen. AI i Viva-ämnen anpassas för att fungera med stora datamängder, helst sådana som har fler än 10 000 dokument.
- Det är överväldigande att inte generera så många ämnen under utvärderingsperioden som utvärderar dem under den tillgängliga tidsperioden.

För de flesta organisationer ger den andra strategin bästa resultat.

> [!NOTE]
> På grund av antalet dokument som krävs av AI:n rekommenderar vi att du kör Viva Topics-försök på en produktionsklientorganisation. Det påverkar inte klientorganisationens prestanda under den här perioden. Endast användare som har en utvärderingslicens kan komma åt användarupplevelsen i Viva Topics.

#### <a name="roles"></a>Roller

Under utvärderingsperioden finns det tre roller som måste vara aktiva, vilket beskrivs i följande tabell.

|Roll  |Aktivitet  |
|---------|---------|
|Knowledge Manager     |   Styra livscykelfasen för ämnen. bekräfta och ta bort ämnen; agera som community-hanterare för ämnesdeltagare      |
|Ämnesdeltagare    |      Ämnesexperter som kan:<br> Granska ämnen för att utvärdera kvaliteten på AI-definierat innehåll<br>Curate discovered topics with additional content<br>Skapa ytterligare ämnen som inte identifierats av AI   |
|Ämneskonsument    |     Använda ämnen genom att markera och söka på sidor<br>Ge feedback om värdet för de ämnen som presenteras    |

#### <a name="expected-topics"></a>Förväntade ämnen

Det kan vara bra att dokumentera de ämnen som du förväntar dig att genereras av AI, även om det bara baseras på antaganden. Den här uppgiften slutförs enkelt när du indexerar en definierad delmängd av dina SharePoint webbplatser som företag kan enkelt identifiera sig för.

Om du har en dokumenterad lista kan du:

- Granska listan med AI-genererade ämnen, som kan vara större än du förväntar dig.
- Ta del av de ämnen som du kan behöva skapa manuellt eller som är prioriteringar för läroplanen.

Det finns alltid ett behov av en blandning av AI-definierade ämnen och ämnen som skapats av människor i en lyckad distribution eller utvärdering av Viva-ämnen.

## <a name="activate-a-trial"></a>Aktivera en utvärderingsversion

När du påbörjar en utvärderingsversion måste du:

- Tilldela licenser till relevanta användare.
- Utför [ytterligare konfiguration av](set-up-topic-experiences.md) Viva Ämnen.

När utvärderingsversionen aktiveras påbörjas identifieringsprocessen för ämnen.

## <a name="during-a-trial"></a>Under en utvärderingsversion

Utvärderingsperioden ska användas för att utvärdera följande komponenter i Viva Topics:

- AI-föreslagna ämnen och ämnesinnehåll
- Slutanvändarupplevelserna, att visa ämneskort på moderna SharePoint sidor och i Microsoft Search

Tänk på följande faktorer:

- För att Viva Topics ska kunna ge maximalt värde måste innehållet i ämnena vara en kombination av AI-definierat innehåll och humant innehåll.
- Alla användarupplevelser "behörighets trimmas" (inklusive vyn knowledge manager på sidan **Hantera ämnen).** Användare ser bara ett ämne om de har behörighet att visa en del av de resurser som användes för att generera ämnet. Det innebär att olika användare kan se olika innehåll på samma ämnessida.
- Användare kan se flera avsnitt som har samma namn på **sidan Hantera ämnen.** De här avsnitten är inte nödvändigtvis dubbletter, men kan vara på grund av en term som används i flera sammanhang i dina data, till exempel ett projektkodsnamn som används av två olika projekt.

## <a name="after-a-trial"></a>Efter en utvärderingsversion

Baserat på resultatet av utvärderingsversionen kan du bestämma om du vill fortsätta med produktionsanvändningen av Viva Topics.

### <a name="proceed-to-production-use"></a>Fortsätt till produktionsanvändning

För att säkerställa kontinuiteten i tjänsten måste du köpa antalet licenser som krävs och tilldela licenserna till användarna. Utvärderingsanvändare som inte har en fullständig licens i slutet av utvärderingsperioden kommer inte att kunna komma åt Viva Topics-upplevelserna.

### <a name="dont-proceed-to-production-use"></a>Fortsätt inte till produktionsanvändning

Om du inte köper licenser efter utvärderingsversionen:

- Ämnesidentifieringen avbryts.
- Användarna kommer inte längre att se höjdpunkter eller kort för ämnen.
- Ämnescentret tas inte bort, men de föreslagna ämnena och hantera ämnen är inte tillgängliga.
- Alla AI-definierade ämnen går förlorade.
- Ämnen som har redigerats av en ämnesdeltagare finns kvar i biblioteket med ämnescentersidor. Endast manuellt tillhandahållet innehåll kommer att finnas kvar på dessa sidor, inte något AI-föreslaget innehåll.

## <a name="see-also"></a>Se även

[Kom igång med införandet av Microsoft Viva Topics](topics-adoption-getstarted.md)

