---
title: Office 365-säkerhet, Microsoft Defender för Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Säkerhet i Office 365, från EOP till Defender för Office 365, abonnemang 1 och 2, standard kontra strikta säkerhets konfigurationer, med mera. Förstå vad du har och hur du skyddar dina egenskaper.
ms.openlocfilehash: 008488149a403fdafef9de0b0f64a9a43616debe
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357761"
---
# <a name="office-365-security-overview"></a>Säkerhets översikt för Office 365

I den här artikeln får du en introduktion till dina nya säkerhets egenskaper i molnet. Vare sig du är en del av ett säkerhets åtgärds Center är du en säkerhets administratör som är ny för utrymmet, eller så vill du att en uppdaterare kommer att komma igång.

> [!CAUTION]
> Om du använder **Outlook.com**, **Microsoft 365** eller **Microsoft 365 personal** och behöver *säkra länkar* eller information om *säkra bifogade filer* * klickar du **på den här länken** _: [avancerad Outlook.com säkerhet för Microsoft 365-prenumeranter](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365-säkerheten har stavats bort

Alla Office 365-prenumerationer har säkerhetsfunktionerna. Vilka mål och åtgärder du kan vidta beror på de olika abonnemangens fokus. I säkerhet för Office 365 finns tre viktiga säkerhets tjänster (eller produkter) som är kopplade till din abonnemangs typ:

1. Exchange Online Protection (EOP)
1. Microsoft Defender för Office 365 abonnemang 1 (Defender för Office P1)
1. Microsoft Defender för Office 365 abonnemang 2 (Defender för Office P2)

> [!NOTE]
> Om du har köpt din prenumeration och behöver installera säkerhetsfunktionerna _right nu *, går du vidare till åtgärderna i artikeln [skydda mot hot](protect-against-threats.md) . Om du är nybörjare på ditt abonnemang och vill veta din licens innan du börjar kan du bläddra > dina produkter i [administrations centret för Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

Office 365-säkerhet bygger på de viktigaste skydd som erbjuds av EOP. EOP finns i alla abonnemang där Exchange Online-postlådor kan hittas (kom ihåg att alla säkerhets produkter som diskuteras här är molnbaserade).

Du kanske känner av dessa tre komponenter som diskuteras på det här sättet:

|EOP|Microsoft Defender för Office 365 P1|Microsoft Defender för Office 365 P2|
|---|---|---|
|Förhindrar breda, volymbaserade, kända attacker.|Skydda e-post och samarbete från icke-dagars skadlig program vara, Phish och e-postkompromiss.|Lägger till undersökningar, jakt och svar efter intrång samt automatisering och simulering (för utbildning).|
|

Men i en arkitektur är det dags att tänka på varje del som en samlad säkerhet, var och en med en säkerhets betoning. Ungefär så här:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP och Microsoft Defender för Office 365 och deras relationer till varandra med service betoning, inklusive en kommentar om e-postauktorisering.":::

Även om de här tjänsterna betonar ett mål från skydda, upptäcka, undersöka och svarar ***alla** _ tjänsterna kan du _*_utföra de mål_*_ som gäller för att skydda, upptäcka, utreda och svara.

Kärnan i Office 365-säkerheten är EOP skydd. Microsoft Defender för Office 365 P1 innehåller EOP. Defender för Office 365 P2 innehåller P1 och EOP. Strukturen är kumulativ. Därför bör du börja med EOP och arbeta med Defender för Office 365 när du konfigurerar den här produkten.

Även om konfigurationen av e-postkonfiguration sker i offentliga DNS är det viktigt att konfigurera den här funktionen för att skydda förfalskningar. _Om du har EOP, * ***bör du [Konfigurera e-postauktorisering](email-validation-and-authentication.md)**_.

Om du har ett Office 365 E3 eller tidigare har du EOP, men med alternativet att köpa fristående Defender för Office 365 P1 till uppgradering. Om du har Office 365 E5 har du redan Defender för Office 365 P2.

> [!TIP]
> Om ditt abonnemang varken är Office 365 E3 eller E5 kan du ändå kontrol lera om du har möjlighet att uppgradera till Microsoft Defender för Office 365 P1. Om du är intresse rad av [den här webb sidan](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) kan du se vilka abonnemang som är kvalificerade för uppgraderingen av Microsoft Defender för Office 365 P1 (kontrol lera slutet på sidan för utskriften).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Säkerhets steg för Office 365 från EOP till Microsoft Defender för Office 365

![EOP och Microsoft Defender för Office 365 och deras säkerhets betoning för att gå från skydda och identifiera för att undersöka och svara. Konfigurering av e-postkonfiguration (minst DKIM och DMARC) ska ställas in för EOP och up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Lär dig mer om dessa sidor: [Exchange Online Protection](exchange-online-protection-overview.md)och [Defender för Office 365](office-365-atp.md).

Vad innebär att det är svårt att lägga till Microsoft Defender för Office 365-abonnemang med ren EOP Threat Management. För att hjälpa dig att sortera om en uppgraderings Sök väg passar för din organisation, ska vi titta på funktionerna för varje produkt när det gäller:

- förhindra och upptäcka hot
- undersöker
- slutar

startar med _ * Exchange Online Protection * *:
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Tekniken inkluderar:<ul><li>skräppost</li><li>phish</li><li>program</li><li>Mass utskick</li><li>Spoof-intelligens</li><li>identifiering av personifiering</li><li>Administratörs karantän</li><li>Administratörs-och användar inlämningar av falska positiva och falska negativa negativ</li><li>Tillåt/blockera för URL-adresser och filer</li><li>Rapporter</li></u1>|<li>Gransknings loggs ökning</li><li>Meddelande spårning</li>|<li>Automatisk rensning av noll-timme (ZAP)</li><li>Förfining och testning av listor över tillåtna och blockera</li>|
|

Om du vill ha en EOP går **[du till den här artikeln](exchange-online-protection-overview.md)**.

Eftersom dessa produkter är kumulativa om du utvärderar Microsoft Defender för Office 365 P1 och bestämmer dig för att prenumerera på den, lägger du till dessa förmågor.

Vinster med **Defender för Office 365, abonnemang 1** (till datum):
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Teknologierna innehåller allt i EOP plus:<u1><li>Säkra bifogade filer</li><li>Säkra länkar<li>Microsoft Defender för Office 365 skydd för arbets belastning (ex. SharePoint Online, teams, OneDrive för företag)</li><li>Tidpunkt för att klicka på skydd i e-post, Office-klienter och team</li><li>anti-nätfiske i Defender för Office 365</li><li>Skydd mot användar-och domän personifiering</li><li>Aviseringar och SIEM integration API för aviseringar</li>|<li>SIEM integrerings-API för identifiering</li><li>**Verktyg för identifiering av real tid**</li><li>URL-spårning</li>|<li>Det</li></u1>

Därför expanderas Microsoft Defender för Office 365 på **_skydds_* sidan i huset och lägger till extra former av _*_identifiering_*_.

Microsoft Defender för Office 365 P1 lägger också till _ *real tids identifieringar** för utredningar. Det här tillägget för att skydda hotet är i fetstil eftersom det är klart att *veta* att du har Defender för Office 365 P1. Det visas inte i Defender för Office 365 P2.

Vinster med **Defender för Office 365, abonnemang 2** (till datum):
<p>

|Förhindra/upptäcka|Undersöka|Svara|
|---|---|---|
|Teknologierna innehåller allt i EOP och Microsoft Defender för Office 365 P1 plus:<u1><li>Det</li>|<li>**Hotutforskaren**</li><li>Hotspårare</li><li>Kampanjmallar</li>|<li>Automatisk undersökning och svar (luft)</li><li>FLYG från hot Explorer</li><li>LUFT för användare med kompromiss</li><li>SIEM integrerings-API för automatiserade utredningar</li>

Därför expanderar Microsoft Defender för Office 365 P2 på **_undersökningen och svaret_* till huset, och lägger till en ny växt styrka. Åtgärden.

I Microsoft Defender för Office 365 P2 kallas det primära jakt verktyget _ *Threat Explorer** i stället för identifieringar i real tid. Om du ser Threat Explorer när du navigerar till säkerhets Center är du i Microsoft Defender för Office 365 P2.

**[Gå till den här artikeln](office-365-atp.md)** om du vill ha information om Microsoft Defender för Office 365 P1 och P2.

> [!TIP]
> EOP och Microsoft Defender för Office 365 är också olika när det gäller slutanvändare. I EOP och Defender för Office 365 P1 är fokus en *medvetenhet* om de två tjänsterna inkluderar *Outlook-tillägget rapport* , så att användare kan rapportera e-post som de hittar misstänkta, för ytterligare analyser. <p> I Defender för Office 365 P2 (som innehåller allt i EOP och P1) flyttas fokus till *ytterligare utbildning* för slutanvändare och så att säkerhets åtgärds Center har till gång till ett kraftfullt verktyg för *hotet* och slutanvändare.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender för Office 365 abonnemang 1 jämfört med abonnemang 2 – översikts blad

Den här snabb referensen hjälper dig att förstå vilka funktioner som ingår i varje Microsoft Defender för Office 365-prenumeration. Tillsammans med din kunskap om EOP funktioner kan den hjälpa företags besluts fattare att avgöra vad Microsoft Defender för Office 365 passar bäst för deras behov.

|Defender för Office 365 abonnemang 1|Defender för Office 365 abonnemang 2|
|---|---|
|Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](atp-safe-attachments.md)</li><li>[Säkra länkar](atp-safe-links.md)</li><li>[ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Skydd mot nätfiske i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Defender för Office 365 abonnemang 1-funktioner<br/>--- plus ---<br/>Funktioner för automatisering, undersökning, reparationer och utbildning:</li><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](office-365-air.md)</li><li>[Attacksimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender för Office 365 abonnemang 2 ingår i Office 365 E5, Office 365 A5 och Microsoft 365 E5.

- Microsoft Defender för Office 365 Abonnemang 1 ingår i Microsoft 365 Business Premium.

- Microsoft Defender för Office 365 abonnemang 1 och Defender för Office 365 abonnemang 2 finns tillgängliga som tillägg för vissa prenumerationer. Om du vill ha mer information kan du läsa mer om [tillgänglighets funktioner i Microsoft Defender för Office 365-abonnemang](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Funktionen [Säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Microsoft Defender för Office 365-abonnemang).

- Om ditt nuvarande abonnemang inte innehåller Microsoft Defender för Office 365 och du vill ha det kan du [Kontakta försäljning för att starta en utvärderings version](https://go.microsoft.com/fwlink/p/?LinkId=518644)och ta reda på hur Microsoft Defender för Office 365 kan arbeta i organisationen.

> [!TIP]
> ***Insider-tips** _. Du kan använda innehålls förteckningen docs.microsoft.com för att lära dig mer om EOP och Microsoft Defender för Office 365. Navigera tillbaka till den här sidan, [Office 365-säkerhets översikt](https://docs.microsoft.com/microsoft-365/security/office-365-security)och Lägg märke till att organisationen för innehålls förteckning är i sido fältet. Den börjar med distribution (inklusive migrering) och fortsätter sedan till förebyggande, identifiering, undersökning och svar. <p> Den här strukturen är uppdelad så att _ *säkerhets administration** följs av avsnitten om **säkerhets åtgärder** . Om du är en ny medlem i någon av jobb rollerna kan du använda länken i det här tipset och innehållet i innehålls förteckningen för att få reda på utrymmet. Kom ihåg att använda *feedback-länkar* och *betygs ätt artiklar* allteftersom. Feedback hjälper oss att förbättra vad vi ger dig.

## <a name="where-to-go-next"></a>Var du ska gå vidare

Om du är administratör kan du behöva konfigurera DKIM eller DMARC för din e-post. Du kanske vill visa "strikta" säkerhets för inställningar för dina prioriterade användare eller leta efter nyheter i produkten. Om du befinner dig med säkerhetsfunktionen kan det vara bra att använda upptäckter i real tid eller hot Utforskaren för att undersöka och svara eller utbilda slutanvändares identifiering med en angrepps Simulator. Här är några ytterligare rekommendationer för vad du kan titta på härnäst.

[E-postauktorisering, inklusive SPF, DKIM och DMARC (med länkar till konfiguration av alla tre)](email-validation-and-authentication.md)

[Se de specifika rekommenderade "gyllene"-konfigurationerna](recommended-settings-for-eop-and-office365-atp.md) och [Använd de rekommenderade inställningarna för att konfigurera säkerhets principer snabbt](preset-security-policies.md)

Håll koll på [vad som är nytt i Microsoft Defender för Office 365 (inklusive EOP)](whats-new-in-office-365-atp.md)

[Använda Threat Explorer eller real tids identifiering](threat-explorer.md)

Använda [angrepps Simulator i Microsoft Defender för Office 365](attack-simulator.md)
