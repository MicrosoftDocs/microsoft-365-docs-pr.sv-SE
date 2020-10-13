---
title: Office 365-säkerhet, Office 365 ATP, EOP, ATP, MSDO
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
description: Säkerhet i Office 365, från EOP till ATP-abonnemang 1 och 2, standard kontra strikta säkerhetskonfigurationer. Förstå vad du har och hur du skyddar dina egenskaper.
ms.openlocfilehash: 94fce99d029d21524bc60af4622fda7ee38980e7
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430698"
---
# <a name="office-365-security-overview"></a>Säkerhets översikt för Office 365

I den här artikeln får du en introduktion till dina nya säkerhets egenskaper i molnet. Vare sig du är en del av ett säkerhets åtgärds Center är du en säkerhets administratör som är ny för utrymmet, eller så vill du att en uppdaterare kommer att komma igång.

> [!CAUTION]
> Om du använder **Outlook.com**, **Microsoft 365**eller **Microsoft 365 personal**och behöver *säkra länkar* eller information om *säkra bifogade filer* klickar du ***på den här länken***: [avancerad Outlook.com säkerhet för Microsoft 365-prenumeranter](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365-säkerheten har stavats bort

Alla Office 365-prenumerationer har säkerhetsfunktionerna. Vilka mål och åtgärder du kan vidta beror på de olika abonnemangens fokus. I säkerhet för Office 365 finns tre viktiga säkerhets tjänster (eller produkter) som är kopplade till din abonnemangs typ:

1. Exchange Online Protection (EOP)
1. Avancerat skydd, abonnemang 1 (ATP P1)
1. Avancerat skydd för hot, abonnemang 2 (ATP P2)

> [!NOTE]
> Om du har köpt din prenumeration och måste installera säkerhetsfunktionerna kan du *gå vidare till*åtgärderna i artikeln [skydda mot hot mot hotet](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) . Om du är nybörjare på ditt abonnemang och vill veta din licens innan du börjar kan du bläddra > dina produkter i [administrations centret för Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

Office 365-säkerhet bygger på de viktigaste skydd som erbjuds av EOP. EOP finns i alla abonnemang där Exchange Online-postlådor kan hittas (kom ihåg att alla säkerhets produkter som diskuteras här är molnbaserade).

Du kanske känner av dessa tre komponenter som diskuteras på det här sättet:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Förhindrar breda, volymbaserade, kända attacker.    |  Skydda e-post och samarbete från icke-dagars skadlig program vara, Phish och e-postkompromiss.       | Lägger till undersökningar, jakt och svar efter intrång samt automatisering och simulering (för utbildning).         |

Men i en arkitektur är det dags att tänka på varje del som en samlad säkerhet, var och en med en säkerhets betoning. Ungefär så här:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

Även om alla de här tjänsterna betonar ett mål från skydda, upptäcka, undersöka och svarar, kan ***alla*** tjänster hantera, upptäcka, utreda ***any*** och svara.

Kärnan i Office 365-säkerheten är EOP skydd. ATP P1 innehåller EOP. ATP P2 innehåller P1 och EOP. Strukturen är kumulativ. Därför ska du börja med EOP och arbeta med ATP när du konfigurerar den här produkten.

Även om konfigurationen av e-postkonfiguration sker i offentliga DNS är det viktigt att konfigurera den här funktionen för att skydda förfalskningar. *Om du har EOP* ***bör du [Konfigurera e-postauktorisering](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)***.

Om du har ett Office 365 E3 eller tidigare har du EOP, men du kan köpa fristående ATP P1 till uppgradering. Om du har Office 365 E5 har du redan ATP P2.

> [!TIP]
> Om ditt abonnemang varken är Office 365 E3 eller E5 kan du ändå kontrol lera om du har möjlighet att uppgradera till ATP P1. Om du är intresse rad av [den här webb sidan](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) kan du se vilka abonnemang som är kvalificerade för uppgraderingen av ATP P1 (kontrol lera slutet på sidan för utskriften).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>Säkerhets steg för Office 365 från EOP till ATP

<br/>

![EOP och ATP samt deras säkerhets betoning, att skydda och upptäcka för att undersöka och svara.Konfigurering av e-postkonfiguration (minst DKIM och DMARC) ska ställas in för EOP och up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> Lär dig mer om dessa sidor: [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)och [Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp).

Det kan vara svårt att lägga till ATP-abonnemang för att få en fördel med ren EOP Threat Management. För att hjälpa dig att sortera om en uppgraderings Sök väg passar för din organisation, ska vi titta på funktionerna för varje produkt när det gäller:

 - förhindra och upptäcka hot
 - undersöker
 - slutar

startar med **Exchange Online Protection**:
<p>

|Förhindra/upptäcka  |Undersöka  |Svara  |
|---------|---------|---------|
| Tekniken inkluderar:<ul><li>skräppost</li><li>phish</li><li>program</li><li>Mass utskick</li><li>Spoof-intelligens</li><li>identifiering av personifiering</li><li>Administratörs karantän</li><li>Administratörs-och användar inlämningar av falska positiva och falska negativa negativ</li><li>Tillåt/blockera för URL-adresser och filer</li><li>Rapporter</li></u1>|<li>Gransknings loggs ökning</li><li>Meddelande spårning</li>|<li>Automatisk rensning av noll-timme (ZAP)</li><li>Förfining och testning av listor över tillåtna och blockera</li>|

Om du vill ha en EOP går **[du till den här artikeln](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**.

Eftersom dessa produkter är kumulativa om du utvärderar ATP P1 och bestämmer dig för att prenumerera på den, kan du lägga till dessa förmågor.

Vinster med **Avancerat skydd, abonnemang 1** (till datum):
<p>

|Förhindra/upptäcka  |Undersöka  |Svara  |
|---------|---------|---------|
| Teknologierna innehåller allt i EOP plus:<u1><li>Säkra bifogade filer</li><li>Säkra länkar<li>Skydd mot ATP för arbets belastning (t. ex. SharePoint Online, teams, OneDrive för företag)</li><li>Tidpunkt för att klicka på skydd i e-post, Office-klienter och team</li><li>Stöldskydd med ATP</li><li>Skydd mot användar-och domän personifiering</li><li>Aviseringar och SIEM integration API för aviseringar</li>|<li>SIEM integrerings-API för identifiering</li><li>**Verktyg för identifiering av real tid**</li><li>URL-spårning</li>|<li>Det</li></u1>

Det innebär att ATP P1 utökas på ***förebyggande*** sidan av huset och lägger till extra former av ***identifiering***.

För ATP P1 läggs även **real tids identifiering** för utredningar. Det här anslags programmets namn är i fetstil eftersom det är lätt att *veta* att du har ATP P1. Det visas inte i ATP P2.

Vinster med **Avancerat skydd, abonnemang 2** (till datum):
<p>

|Förhindra/upptäcka  |Undersöka  |Svara  |
|---------|---------|---------|
| Teknologierna innehåller allt i EOP och ATP P1 plus:<u1><li>Det</li>|<li>**Hotutforskaren**</li><li>Hotspårare</li><li>Kampanjmallar</li>|<li>Automatisk undersökning och svar (luft)</li><li>FLYG från hot Explorer</li><li>LUFT för användare med kompromiss</li><li>SIEM integrerings-API för automatiserade utredningar</li>

Det innebär att ATP P2 växer på ***undersökningen och svars*** sidan av huset och lägger till en ny jakt styrka. Åtgärden.

I ATP P2 kallas det primära jakt verktyget **Threat Explorer** i stället för identifiering av real tid. Om du ser Threat Explorer när du navigerar till säkerhets Center befinner du dig i ATP P2.

**[Gå till den här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** om du vill ha mer information om ATP P1 och P2.

> [!TIP]
> EOP och ATP är också olika när det gäller slutanvändare. I EOP och ATP P1 är fokus ett *medvetenhet*och därför att de två tjänsterna inkluderar *Outlook-tillägget rapport* , så att användare kan rapportera e-post som de hittar misstänkta, för ytterligare analyser. <p> I ATP P2 (som innehåller allt i EOP och P1) flyttas fokus till *ytterligare utbildning* för slutanvändare och så att säkerhets åtgärds centret har till gång till ett kraftfullt verktyg för *hotet* och slutanvändarens resultat.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP-abonnemang 1 vs. 2 – översikts-ark

Den här snabb referensen hjälper dig att förstå vilka funktioner som kommer med varje abonnemang för ATP. Tillsammans med din kunskap om EOP funktioner kan den hjälpa företags besluts fattare att avgöra vad ATP är bäst för deras behov.

|Office 365 ATP-abonnemang 1|Office 365 ATP-abonnemang 2|
|---|---|
|<br/>Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](atp-safe-attachments.md)</li><li>[Säkra länkar](atp-safe-links.md)</li><li>[ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[ATP-skydd mot nätfiske](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Funktioner i Office 365 ATP-abonnemang 1<br/>--- plus ---<br/>Funktioner för automatisering, undersökning, reparationer och utbildning:</li><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Attacksimulator](attack-simulator.md)</li></ul>|
|

- Office 365 ATP-abonnemang 2 ingår i Office 365 E5, Office 365 A5 och Microsoft 365 E5.

- Office 365 ATP-abonnemang 1 ingår i Microsoft 365 Business Premium.

- Office 365 ATP-abonnemang 1 och Office 365 ATP-abonnemang 2 är tillgängliga som ett tillägg för vissa prenumerationer. För mer information, här finns en länk till [tillgänglighet för abonnemanget](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Funktionen [säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Office 365 ATP-abonnemang).

- Om ditt nuvarande abonnemang inte innehåller Office 365 ATP, [kontaktar du Sales för att starta en utvärderings version](https://go.microsoft.com/fwlink/p/?LinkId=518644)och tar reda på hur ATP fungerar för inom din organisation.

> [!TIP]
> ***Insider-tips***. Du kan använda innehålls förteckningen docs.microsoft.com för att lära dig mer om EOP och ATP. Navigera tillbaka till den här sidan, [Office 365-säkerhets översikt](https://docs.microsoft.com/microsoft-365/security/office-365-security/?view=o365-worldwide)och Lägg märke till att organisationen för innehålls förteckning är i sido fältet. Den börjar med distribution (inklusive migrering) och fortsätter sedan till förebyggande, identifiering, undersökning och svar. <p> Den här strukturen är uppdelad så att **säkerhets administrations** avsnitten följs av avsnitten om **säkerhets åtgärder** . Om du är en ny medlem i någon av jobb rollerna kan du använda länken i det här tipset och innehållet i innehålls förteckningen för att få reda på utrymmet. Kom ihåg att använda *feedback-länkar* och *betygs ätt artiklar* allteftersom. Feedback hjälper oss att förbättra vad vi ger dig.

## <a name="where-to-go-next"></a>Var du ska gå vidare

Om du är administratör kan du behöva konfigurera DKIM eller DMARC för din e-post. Du kanske vill visa "strikta" säkerhets för inställningar för dina prioriterade användare eller leta efter nyheter i produkten. Om du befinner dig med säkerhetsfunktionen kan det vara bra att använda upptäckter i real tid eller hot Utforskaren för att undersöka och svara eller utbilda slutanvändares identifiering med en angrepps Simulator. Här är några ytterligare rekommendationer för vad du kan titta på härnäst.

[E-postauktorisering, inklusive SPF, DKIM och DMARC (med länkar till konfiguration av alla tre)](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[Se de specifika rekommenderade "gyllene"-konfigurationerna](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) och [Använd de rekommenderade inställningarna för att konfigurera säkerhets principer snabbt](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

Håll koll på [vad som är nytt i Office 365 ATP (inklusive EOP-utveckling)](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

[Använda Threat Explorer eller real tids identifiering](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

Använda [angrepps Simulator i Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)