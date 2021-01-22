---
title: Office 365-säkerhet, Microsoft Defender för Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Säkerhet i Office 365, från EOP till Defender för Office 365 Abonnemang 1 och 2, Standard och Strikt säkerhetskonfigurationer med mera. Förstå vad du har och hur du skyddar dina egenskaper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f83eef6a19e26f4b8f47a049e2b2959b32a92550
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932556"
---
# <a name="office-365-security-overview"></a>Översikt över Säkerhet i Office 365

Den här artikeln presenterar de nya säkerhetsegenskaperna i molnet. Oavsett om du ingår i ett säkerhetsoperationscenter, är du ny säkerhetsadministratör i utrymmet eller vill uppdatera så kan vi komma igång.

> [!CAUTION]
> Om du använder **Outlook.com,** Microsoft **365 Family** eller Microsoft **365 Personal** och  behöver information om säkra länkar eller säkra bifogade filer ***** klickar du på den här länken _: Avancerad Outlook.com-säkerhet för [Microsoft 365-prenumeranter.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2) 

## <a name="office-365-security-spelled-out"></a>Office 365-säkerhet är utstavad

Alla Office 365-prenumerationer levereras med säkerhetsfunktioner. Vilka mål och åtgärder du kan vidta beror på hur de olika prenumerationerna ligger i fokus. I Office 365-säkerhet finns det tre huvudsakliga säkerhetstjänster (eller produkter) kopplade till din prenumerationstyp:

1. Exchange Online Protection (EOP)
1. Microsoft Defender för Office 365 abonnemang 1 (Defender för Office P1)
1. Microsoft Defender för Office 365 abonnemang 2 (Defender för Office P2)

> [!NOTE]
> Om du har köpt din prenumeration och behöver distribuera säkerhetsfunktionerna _right*, går du vidare till stegen i [artikeln Skydda mot](protect-against-threats.md) hot. Om du inte har börjat använda prenumerationen och vill ha information om din licens innan du börjar bläddrar du till Fakturering > Dina produkter i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

Office 365-säkerhetsuppdateringar bygger på de kärnskydd som EOP erbjuder. EOP finns i alla prenumerationer där Exchange Online-postlådor kan hittas (kom ihåg att alla säkerhetsprodukter som diskuteras här är molnbaserade).

Du är kanske van vid att se dessa tre komponenter som diskuteras på det här sättet:

|EOP|Microsoft Defender för Office 365 P1|Microsoft Defender för Office 365 P2|
|---|---|---|
|Förhindrar breda, volymbaserade, kända attacker.|Skyddar e-post och samarbete från skadlig programvara utan dagar, nätt och företags-e-post komprometterat.|Lägger till undersökning efter intrång, söker efter och svar samt automatisering och simulering (för utbildning).|
|

Men när det gäller arkitektur börjar vi med att se varje del som kumulativa säkerhetsnivåer, var och en med en säkerhets betoning. Mer så här:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP och Microsoft Defender för Office 365 och deras relationer till varandra med betoning på tjänsten, inklusive en anteckning för e-postautentisering.":::

Även om var och en av de här tjänsterna fokuserar på ett mål från _**_ att skydda, identifiera, undersöka och svara, ***alla** _ kan tjänsterna utföra något av målen för att skydda, identifiera, undersöka och svara.

Kärnan i Office 365-säkerhet är EOP-skydd. Microsoft Defender för Office 365 P1 innehåller EOP. Defender för Office 365 P2 innehåller P1 och EOP. Strukturen är kumulativ. Därför bör du när du konfigurerar den här produkten börja med EOP och arbeta med Defender för Office 365.

Även om konfigurationen av e-postautentisering sker i offentlig DNS är det viktigt att konfigurera den här funktionen för att försvara sig mot förfalskning. _Om du har EOP*, bör du **konfigurera [e-postautentisering.](email-validation-and-authentication.md)**_

Om du har ett Office 365 E3 eller nedanför har du EOP, men med alternativet att köpa fristående Defender för Office 365 P1 genom uppgradering. Om du har Office 365 E5 har du redan Defender för Office 365 P2.

> [!TIP]
> Om din prenumeration varken är Office 365 E3 eller E5 kan du kontrollera om du har möjlighet att uppgradera till Microsoft Defender för Office 365 P1. Om du är [](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) intresserad visar den här webbsidan prenumerationer som är kvalificerade för uppgraderingen av Microsoft Defender för Office 365 P1 (kontrollera slutet av sidan för mer information).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Säkerhetscentret för Office 365 från EOP till Microsoft Defender för Office 365

![EOP och Microsoft Defender för Office 365 med säkerhets betoning från Skydda och Identifiera för att undersöka och svara. Konfiguration av e-postautentisering (minst DKIM och DMARC) ska konfigureras för EOP och uppåt.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Läs mer på följande sidor: [Exchange Online Protection](exchange-online-protection-overview.md)och Defender för Office [365.](office-365-atp.md)

Det som gör att det kan vara svårt att berätta vid första anblicken är att lägga till Microsoft Defender för Office 365-abonnemang till en fördel för att hantera hot med endast EOP. Vi tar reda på om en uppgraderingsväg är rätt för organisationen genom att titta på funktionerna i varje produkt när det gäller:

- förhindra och upptäcka hot
- undersöker
- svara

börjar med _*Exchange Online Protection**:
<p>

|Förhindra/identifiera|Undersöka|Svara|
|---|---|---|
|Teknikerna omfattar:<ul><li>skräppost</li><li>phish</li><li>skadlig programvara</li><li>massutskick</li><li>förfalskningsinformation</li><li>Identifiering av personifiering</li><li>Administratörs karantän</li><li>Administratörs- och användarinskick av falska positiva tal och falska negativa</li><li>Tillåt/blockera för URL:er och filer</li><li>Rapporter</li></u1>|<li>Granskningsloggsökning</li><li>Meddelandespårning</li>|<li>Zap (Auto-Purge) utan timme</li><li>Förfining och testning av listor över tillåtna och blockerade</li>|
|

Om du vill ta dig in i EOP kan **[du läsa den här artikeln.](exchange-online-protection-overview.md)**

Eftersom dessa produkter är kumulativa och du utvärderar Microsoft Defender för Office 365 P1 och bestämmer dig för att prenumerera på den, lägger du till de här förmågorna.

Vinster med **Defender för Office 365, abonnemang 1** (hittills):
<p>

|Förhindra/identifiera|Undersöka|Svara|
|---|---|---|
|Teknikerna inkluderar allt i EOP plus:<u1><li>Säkra bifogade filer</li><li>Säkra länkar<li>Microsoft Defender för Office 365-skydd för arbetsbelastningar (t.ex. SharePoint Online, Teams, OneDrive för företag)</li><li>Time-of-click-skydd i e-post, Office-klienter och Teams</li><li>skydd mot nätfiske i Defender för Office 365</li><li>Personifieringsskydd av användare och domän</li><li>Varningar och SIEM-integrerings-API för varningar</li>|<li>SIEM-integreringS-API för identifieringar</li><li>**Verktyget Identifieringar i realtid**</li><li>URL-spårning</li>|<li>Samma</li></u1>

Därför expanderar Microsoft Defender för Office 365 P1 på **_prevention_* _ sidan av huset, och lägger till extra _*_identifieringsformulär._*_

Microsoft Defender för Office 365 P1 lägger också till _ *Identifieringar i realtid** för undersökningar. Namnet på det här hotverktyget är i fetstil  eftersom det är tydligt att veta att du har Defender för Office 365 P1. Den visas inte i Defender för Office 365 P2.

Vinster med **Defender för Office 365, abonnemang 2** (hittills):
<p>

|Förhindra/identifiera|Undersöka|Svara|
|---|---|---|
|Teknikerna omfattar allt i EOP och Microsoft Defender för Office 365 P1 samt:<u1><li>Samma</li>|<li>**Hotutforskaren**</li><li>Hotspårare</li><li>Kampanjvyer</li>|<li>Automatiserad undersökning och svar (AIR)</li><li>AIR från Threat Explorer</li><li>AIR för komprometterade användare</li><li>SIEM Integration API för automatiska undersökningar</li>

Därför utökas Microsoft Defender för Office 365 P2 på *_*_* undersöknings- och svarssidan i huset och lägger till en ny sökstyrka. Automatisering.

I Microsoft Defender för Office 365 P2 kallas det primära sökverktyget _ *Threat Explorer** i stället för identifieringar i realtid. Om du ser HotUtforskaren när du navigerar till säkerhetscentret är du i Microsoft Defender för Office 365 P2.

Mer information om Microsoft Defender för Office 365 P1 och P2 finns i **[den här artikeln.](office-365-atp.md)**

> [!TIP]
> EOP och Microsoft Defender för Office 365 skiljer sig också åt för slutanvändare. I EOP och Defender för Office 365 P1 är fokus på information och därför innehåller de två tjänsterna rapportmeddelandet Outlook-tillägget så att användarna kan rapportera *e-postmeddelanden* som de hittar misstänkta, för vidare analys. <p> I Defender för Office 365 P2 (som innehåller allt i EOP och P1) flyttas fokus till vidare utbildning  för slutanvändare, och därför har Säkerhetscenter tillgång till ett kraftfullt verktyg för hot och slutanvändarstatistik som ingår. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender för Office 365 abonnemang 1 jämfört med abonnemang 2 – lathund

Den här snabbreferensen hjälper dig att förstå vilka funktioner som ingår i varje Microsoft Defender för Office 365-prenumeration. I kombination med dina kunskaper om EOP-funktioner kan det hjälpa beslutsfattare att avgöra vad Microsoft Defender för Office 365 passar bäst för deras behov.

|Defender för Office 365 abonnemang 1|Defender för Office 365 abonnemang 2|
|---|---|
|Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](atp-safe-attachments.md)</li><li>[Säkra länkar](atp-safe-links.md)</li><li>[Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Skydd mot nätfiske i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Defender för Office 365 abonnemang 1-funktioner <p> --- plus --- <p> Funktioner för automatisering, undersökning, reparationer och utbildning: <ul><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](office-365-air.md)</li><li>[Attacksimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender för Office 365 abonnemang 2 ingår i Office 365 E5, Office 365 A5 och Microsoft 365 E5.

- Microsoft Defender för Office 365 Abonnemang 1 ingår i Microsoft 365 Business Premium.

- Microsoft Defender för Office 365 abonnemang 1 och Defender för Office 365 abonnemang 2 är alla tillgängliga som ett tillägg för vissa prenumerationer. Om du vill veta mer kan du hitta en annan länk [till funktionstillgänglighet i Microsoft Defender för Office 365-abonnemang.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- Funktionen [Säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Microsoft Defender för Office 365-abonnemang).

- Om Microsoft Defender för Office 365 inte ingår i din nuvarande prenumeration och du vill ha den [kan](https://go.microsoft.com/fwlink/p/?LinkId=518644)du kontakta försäljning för att starta en utvärderingsversion och ta reda på hur Microsoft Defender för Office 365 kan arbeta för din organisation.

> [!TIP]
> ***Insider-tips** _. Du kan använda docs.microsoft.com om du vill veta mer om EOP och Microsoft Defender för Office 365. Gå tillbaka till den här sidan, översikten över Säkerhet i [Office 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security)och du kommer att märka att organisationen med innehållsförteckningar finns i sidofältet. Den börjar med distribution (inklusive migrering) och fortsätter sedan i förebyggande, identifiering, undersökning och svar. <p> Strukturen är uppdelad så att avsnitten _ *Säkerhetsadministration** följs av **avsnitten om Säkerhetsåtgärder.** Om du är ny medlem i någon av jobbrollerna kan du använda länken i det här tipset och den kunskap du har om innehållsförteckningen för att få mer information. Kom ihåg att *använda feedbacklänkar* *och betygsätta* artiklar när du är på språng. Feedback hjälper oss att förbättra det vi erbjuder.

## <a name="where-to-go-next"></a>Nästa steg

Om du är säkerhetsadministratör kan du behöva konfigurera DKIM eller DMARC för din e-post. Du kanske vill distribuera säkerhetsinställningarna Strikt för dina prioriterade användare eller se vad som är nytt i produkten. Om du använder Säkerhets ops kanske du vill utnyttja identifieringar i realtid eller Hot Explorer för att undersöka och svara, eller utbilda slutanvändaren med Attack Attack Attack. I vilket fall som än så kommer här några ytterligare rekommendationer om vad du ska titta på härnäst.

[E-postautentisering, inklusive SPF, DKIM och DMARC (med länkar till konfigurationen av alla tre)](email-validation-and-authentication.md)

[Se de specifika rekommenderade "gyllene" konfigurationerna och](recommended-settings-for-eop-and-office365-atp.md) [använd deras rekommenderade förval för att snabbt konfigurera säkerhetsprinciper](preset-security-policies.md)

Få information om [vad som är nytt i Microsoft Defender för Office 365 (inklusive EOP-utvecklingar)](whats-new-in-office-365-atp.md)

[Använda Hotutforskaren eller identifieringar i realtid](threat-explorer.md)

Använda [AttackTat i Microsoft Defender för Office 365](attack-simulator.md)
