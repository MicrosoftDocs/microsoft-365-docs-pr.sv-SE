---
title: Office 365 säkerhet, Microsoft Defender för Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 06/11/2021
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Säkerhet i Office 365, från EOP till Defender för Office 365 abonnemang 1 och 2, Standard jämfört med strikt säkerhetskonfigurationer med mera. Förstå vad du har och hur du skyddar dina egenskaper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ecdfe324ded6224745b0e2eac087e432ac76c83
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930253"
---
# <a name="microsoft-defender-for-office-365-security-overview"></a>Översikt över Office 365 Microsoft Defender

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)

Den här artikeln presenterar ditt nya Microsoft Defender för Office 365 säkerhetsegenskaper i molnet. Oavsett om du är en del av ett Säkerhetscenter är du en säkerhetsadministratör som är ny till utrymmet eller vill uppdatera dig. Då börjar vi.

> [!CAUTION]
> ***Klicka på denna länk*** om du använder **Outlook.com**, **Microsoft 365 Family** eller **Microsoft 365 Personal** och vill ha information om *Säkra länkar* eller *Säkra bifogade filer*: [Avancerad Outlook.com-säkerhet för Microsoft 365-prenumeranter](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="what-is-defender-for-office-365-security"></a>Vad är Defender för Office 365 säkerhet

I varje Office 365-prenumeration ingår säkerhetsfunktioner. Vilka mål och åtgärder du kan ta beror på vilka prenumerationer som är i fokus. I Säkerhet i Office 365 finns det tre huvudsakliga säkerhetstjänster (eller produkter) kopplade till din prenumerationstyp:

1. Exchange Online Protection (EOP)
1. Microsoft Defender för Office 365 Abonnemang 1 (Defender för Office P1)
1. Microsoft Defender för Office 365 Abonnemang 2 (Defender för Office P2)

> [!NOTE]
> Om du har köpt prenumerationen och behöver distribuera säkerhetsfunktioner *direkt*, kan du gå vidare till stegen i artikeln [Skydda mot hot](protect-against-threats.md). Om du inte har en prenumeration tidigare och vill veta vilken licens du har innan du börjar bläddrar du till Fakturering > Dina produkter i [Administrationscenter för Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

Säkerhet i Office 365 bygger på de kärnskydd som EOP erbjuder. EOP finns i alla prenumerationer där Exchange Online-postlådor kan hittas (kom ihåg att alla säkerhetsprodukter som diskuteras här är molnbaserade).

Du är kanske van vid att se de här tre komponenterna som diskuterats på det här sättet:

|EOP|Microsoft Defender för Office 365 P1|Microsoft Defender för Office 365 P2|
|---|---|---|
|Förhindrar breda, volymbaserade, kända attacker.|Skyddar e-post och samarbete från dag noll-sårbarhet skadlig kod, nätfiske och äventyrande av affärs-e-post.|Lägger till undersökning efter intrång, jakt och svar, samt automatisering och simulering (för utbildning).|
|

Men när det gäller arkitektur börjar vi med att se varje del som kumulativa lager av säkerhet, var och en med betoning på säkerheten. Mer så här:

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP och Microsoft Defender för Office 365 samt deras relationer till varandra med tjänstefaktorer, inklusive en anteckning om e-postautentisering.":::

Även om var och en av de här tjänsterna framhäver ett mål från skydda, identifiera, undersöka och svara ***alla** _ tjänsterna kan utföra _ *_något_** av målen för att skydda, identifiera, undersöka och svara.

Kärnan i Office 365-säkerhet är EOP-skydd. Microsoft Defender för Office 365 P1 innehåller EOP. Defender för Office 365 P2 innehåller P1 och EOP. Strukturen är kumulativ. Därför bör du när du konfigurerar den här produkten börja med EOP och arbeta med Defender för Office 365.

Även om konfiguration av e-postautentisering sker i offentlig DNS är det viktigt att konfigurera den här funktionen för att skydda mot förfalskning. *Om du har EOP* ***bör du [konfigurera e-postautentisering](email-validation-and-authentication.md)***.

Om du har En Office 365 E3 eller nedanför har du EOP, men med alternativet att köpa fristående Defender för Office 365 P1 via uppgradering. Om du har Office 365 E5 har du redan Defender för Office 365 P2.

> [!TIP]
> Om din prenumeration varken är Office 365 E3 eller E5 kan du fortfarande kontrollera om du har möjlighet att uppgradera till Microsoft Defender för Office 365 P1. Om du är intresserad visar [den här webbsidan](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) prenumerationer som är kvalificerade för Uppgraderingen av Microsoft Defender för Office 365 P1 (kontrollera slutet av sidan för det finstilta).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Office 365 säkerhet stege från EOP till Microsoft Defender för Office 365

> [!IMPORTANT]
> Läs mer på följande sidor: [Exchange Online Protection](exchange-online-protection-overview.md)och [Defender för Office 365](defender-for-office-365.md).

Det som gör det svårt att lägga till Microsoft Defender för Office 365-abonnemang till att endast hantera EOP-hot kan vara svårt att se vid första anblicken. För att ta reda på om en uppgraderingsväg är rätt för din organisation kan vi titta på funktionerna för varje produkt när det gäller:

- förhindra och upptäcka hot
- undersökning
- svara

starta med **Exchange Online Protection (EOP)**:
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Tekniker som ingår:<ul><li>skräppost</li><li>nätfiske</li><li>skadlig programvara</li><li>massutskick</li><li>förfalskningsinformation</li><li>identifiering av imitation</li><li>Administratörskarantän</li><li>Administratörer och användare som skickar in falska positiva och falska negativa</li><li>Tillåt/blockera för URL-adresser och filer</li><li>Rapporter</li></u1>|<li>Granskningsloggsökning</li><li>Meddelandespårning</li>|<li>Zero-hour Auto-Purge (ZAP)</li><li>Förfining och testning av listorna Tillåt och Blockera</li>|
|

Om du vill gräva djupare i EOP kan du **[hoppa till den här artikeln](exchange-online-protection-overview.md)**.

Eftersom dessa produkter är kumulativa kommer du att lägga till dessa färdigheter om du går upp till Microsoft Defender för Office 365 P1 och bestämmer dig för att prenumerera på det.

Fördelar med **Defender för Office 365 Abonnemang 1** (hittills):
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Tekniker inkluderar allt i EOP plus:<u1><li>Säkra bifogade filer</li><li>Säkra länkar<li>Microsoft Defender för Office 365 skydd för arbetsbelastningar (t.ex. SharePoint Online, Teams och OneDrive för företag)</li><li>Klickskydd i e-post, Office-klienter och Teams</li><li>skydd mot nätfiske i Defender för Office 365.</li><li>Skydd för imitation av användare och domäner</li><li>API för varningar och SIEM-integrering för varningar</li>|<li>API för SIEM-integrering för identifieringar</li><li>**Identifieringsverktyg i realtid**</li><li>URL-spårning</li>|<li>Samma</li></u1>

Så, Microsoft Defender för Office 365 P1 utökas på ***-skydd** _ sida av hemmet, och lägger till extra former av _*_identifiering_**.

Microsoft Defender för Office 365 P1 lägger även till **realtidsidentifiering** för undersökningar. Namnet på det här verktyget för hot är i fetstil eftersom det är tydligt innebär att du *veta* du har Defender för Office 365 P1. Den visas inte i Defender för Office 365 P2.

Fördelar med **Defender för Office 365 Abonnemang 2** (hittills):
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Tekniker inkluderar allt i EOP och Microsoft Defender för Office 365 P1 samt:<u1><li>Samma</li>|<li>**Hotutforskaren**</li><li>Hotspårare</li><li>Kampanjvyer</li>|<li>Automatiska undersökningar och svar (AIR)</li><li>AIR från Hotutforskaren</li><li>AIR för komprometterade användare</li><li>API för SIEM-integrering för automatiserade undersökningar</li>

Därför utökar Microsoft Defender för Office 365 P2 ***undersökning och svar*** sidan av hemmet, och lägger till en ny jaktstyrka. Automatisering.

I Microsoft Defender för Office 365 P2 kallas det primära sökverktyget **Hotutforskaren** i stället för Realtidsidentifiering. Om du ser Hotutforskaren när du navigerar till Microsoft 365 Defender-portalen är du i Microsoft Defender för Office 365 P2.

Om du vill gå in på information om Microsoft Defender för Office 365 P1 och P2 kan du **[hoppa till den här artikeln](defender-for-office-365.md)**.

> [!TIP]
> EOP och Microsoft Defender för Office 365 skiljer sig också när det gäller slutanvändare. I EOP och Defender för Office 365 P1 är fokus *medvetenhet*, och därför innehåller dessa två tjänster *Outlook-tillägget rapportmeddelande* så att användare kan rapportera e-postmeddelanden som de hittar misstänkta, för vidare analys. <p> I Defender för Office 365 P2 (som innehåller allt i EOP och P1), flyttas fokus till *vidare utbildning* för slutanvändare, och därför har Säkerhetscenter tillgång till ett kraftfullt verktyg *Hotsimulering*, och slutanvändarmåtten det tillhandahåller.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender för Office 365 Abonnemang 1 jämfört med Abonnemang 2 översiktsblad

Den här snabbreferensen hjälper dig att förstå vilka funktioner som ingår i varje Microsoft Defender för Office 365-prenumeration. När den kombineras med dina kunskaper om EOP-funktioner kan den hjälpa affärsbeslutsfattarna att avgöra vilken Microsoft Defender för Office 365 som passar bäst för deras behov.

|Microsoft Defender för Office 365 Abonnemang 1|Microsoft Defender för Office 365 abonnemang 2|
|---|---|
|Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](safe-attachments.md)</li><li>[Säkra länkar](safe-links.md)</li><li>[Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Skydd mot nätfiske i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Defender för Office 365 Abonnemang 1  <p> --- plus --- <p> Funktioner för automatisering, undersökning, reparationer och utbildning: <ul><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](office-365-air.md)</li><li>[Attacksimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender för Office 365 Abonnemang 2 ingår i Office 365 E5, Office 365 A5, Microsoft 365 E5.

- Microsoft Defender för Office 365 Abonnemang 1 ingår i Microsoft 365 Business Premium.

- Microsoft Defender för Office 365, Abonnemang 1 och Defender för Office 365 Abonnemang 2 är tillgängliga som ett tillägg för vissa abonnemang. Läs mer i [Funktionstillgänglighet för Microsoft Defender för Office 365-abonnemang](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Funktionen [Säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Microsoft Defender för Office 365-abonnemang).

- Om du inte har Microsoft Defender för Office 365, kan du [kontakta försäljningsavdelningen för att starta en utvärderingsversion](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) och se hur Microsoft Defender för Office 365 fungerar för din organisation.

> [!TIP]
> ***Insider tips** _. Du kan använda docs.microsoft.com innehållsförteckning om du vill veta mer om EOP och Microsoft Defender för Office 365. Gå tillbaka till den här sidan [Säkerhetsöversikt i Office 365](index.yml). Organisationen för innehållsförteckningen visas i sidlisten. Det börjar med Distribution (inklusive migrering) och fortsätter sedan till skydd, identifiering, undersökning och svar. <p> Den här strukturen är uppdelad så att ämnen för _ *Säkerhetsadministration** följs av ämnen för **Säkerhetsåtgärder**. Om du är ny medlem i någon av jobbrollerna kan du använda länken i det här tipset, och dina kunskaper om innehållsförteckningen, för att öka utrymmet. Kom ihåg att använda *länkar till feedback* och *betygsätta artiklar* medans du håller på. Feedback hjälper oss att förbättra det vi erbjuder.

## <a name="where-to-go-next"></a>Gå vidare

Om du är Säkerhetsadministratör kan du behöva konfigurera DKIM eller DMARC för din e-post. Du kanske vill distribuera säkerhetsinställningarna Strikt för dina prioritetsanvändare eller leta efter vad som är nytt i produkten. Eller om du arbetar med Security Ops kanske du vill använda Realtidsidentifiering eller Hotutforskaren för att undersöka och svara, eller utbilda slutanvändareidentifiering med Attacksimulatorn. Oavsett är här några ytterligare rekommendationer för hur du ska gå vidare.

[E-postautentisering, inklusive SPF, DKIM och DMARC (med länkar till konfiguration av alla tre)](email-validation-and-authentication.md)

[Läs mer om specifika rekommenderade “gyllene” konfigurationer ](recommended-settings-for-eop-and-office365.md) och [använda rekommenderade förval för att snabbt konfigurera säkerhetsprinciper](preset-security-policies.md)

Komma i kapp med [nyheter i Microsoft Defender för Office 365 (inklusive EOP-utveckling)](whats-new-in-defender-for-office-365.md)

[Använda Hotutforskaren eller Realtidsidentifieringar](threat-explorer.md)

Använda [Attacksimulator i Defender för Office 365](attack-simulator.md)

