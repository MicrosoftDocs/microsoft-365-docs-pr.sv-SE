---
title: Microsoft Defender för Office 365 i Microsoft 365 Defender
description: Läs mer om ändringar från Office 365 säkerhets- och efterlevnadscenter för att Microsoft 365 Defender.
keywords: Microsoft 365 säkerhet, Komma igång med Microsoft 365 Defender, Microsoft Defender för Office 365, Microsoft Defender för Slutpunkt, MDO, MDE, enda fönsterruta av glas, ny säkerhetsportal, nya defender-säkerhetsportalen
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: decc991ef1d4a1b92f4e843fd39d595b9a1f7107
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964848"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender för Office 365 i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Snabbreferens

I tabellen nedan visas ändringar i navigeringen mellan Office 365 säkerhets- & kompatibilitetscenter och Microsoft 365 Defender.

<br>

****

|[Office 365 Säkerhets- & efterlevnad](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)|[Administrationscentret för Exchange](https://admin.exchange.microsoft.com/#/)|
|---|---|---|---|
|Varningar|<ul><li>[Aviseringsprinciper](https://security.microsoft.com/alertpolicies)</li><li>[Incidenter & aviseringar](https://security.microsoft.com/alerts)</li></ul>|[Sidan Aviseringar](https://compliance.microsoft.com/homepage)||
|Klassificering||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Skydd mot dataförlust||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Hantering av arkivhandlingar||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Informationsstyrning||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Hothantering|[E-& samarbete](https://security.microsoft.com/homepage)|||
|Behörigheter|[Behörigheter & roller](https://security.microsoft.com/emailandcollabpermissions)|Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|E-postflöde|||Se [Exchange administrationscenter](https://admin.exchange.microsoft.com/#/)|
|Datasekretess||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Söka|[Granskning](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|Sökning (innehållssökning)||
|Rapporter|[Rapport](https://security.microsoft.com/emailandcollabreport)|||
|Tjänstgranskning||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|Överövervakning||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||
|eDiscovery||Se [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage)||

[Microsoft 365 Defender](./overview-security-center.md) på kombinerar säkerhetsfunktioner från befintliga <https://security.microsoft.com> Microsoft-säkerhetsportaler, inklusive säkerhets- Office 365 säkerhets- & efterlevnadscenter. Det här förbättrade centret hjälper säkerhetsteam att skydda organisationen från hot mer produktivt och effektivt.

Om du är bekant med Office 365 säkerhets- och efterlevnadsportalen (protection.office.com) beskriver den här artikeln några av de ändringar och förbättringar Microsoft 365 Defender.

Läs mer om fördelarna: [Översikt över Microsoft 365 Defender](overview-security-center.md)

Om du letar efter efterlevnadsrelaterade objekt kan du gå till [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage).

## <a name="new-and-improved-capabilities"></a>Nya och förbättrade funktioner

Det vänstra navigeringsfältet eller snabbstartsfältet ser bekant ut. Det finns dock några nya och uppdaterade element i det här säkerhetscentret.

Med den enhetliga Microsoft 365 Defender lösningen kan du samlas ihop hot signalerna och fastställa hotens fullständiga omfattning och påverkan, och hur det för närvarande påverkar organisationen.

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Bild av Microsoft 365 Defender konvergerad upplevelse":::

Defender för Office 365 skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg.

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Bild på Defender för Office 365":::

### <a name="incidents-and-alerts"></a>Incidenter och aviseringar

Samlar incidenter och aviseringar för e-post, enheter och identiteter. Aviseringar är nu tillgängliga under noden Undersökning och bidrar till att ge en bredare bild av ett angrepp. Aviseringssidan ger en fullständig kontext till aviseringen genom att kombinera attackerande signaler för att skapa en detaljerad historia. Tidigare var aviseringar specifika för olika arbetsbelastningar. I en ny, enhetlig upplevelse samlas nu en enhetlig vy av aviseringar för arbetsbelastningar. Du kan snabbt göra triage, undersöka och vidta effektiva åtgärder.

- [Läs mer om undersökningar](incidents-overview.md)
- [Läs mer om hur du hanterar varningar](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![Snabbstartfältet Aviseringar och Åtgärder](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Jakt

Sök proaktivt efter hot, skadlig programvara och skadlig aktivitet i dina slutpunkter, Office 365-postlådor med mera med hjälp av [avancerade sökfrågor](advanced-hunting-overview.md). De här kraftfulla frågorna kan användas för att hitta och granska hotindikatorer och -enheter för både kända och potentiella hot.

[Anpassade identifieringsregler kan](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) byggas från avancerade sökfrågor för att proaktivt bevaka händelser som kan vara på grund av intrångsaktivitet och felkonfigurerade enheter.

Här är ett [exempel på avancerad sökning](advanced-hunting-example.md) i Microsoft Defender för Office 365.  

### <a name="action-center"></a>Åtgärdscenter

Åtgärdscenter visar de undersökningar som skapats med automatiska undersöknings- och svarsfunktioner. Den här automatiserade självläkningen i Microsoft 365 Defender kan hjälpa säkerhetsteam genom att automatiskt svara på specifika händelser.

Läs mer om [Åtgärdscenter](m365d-action-center.md).

#### <a name="threat-analytics"></a>Analys av hot

Få information om hot från Microsofts säkerhetsexpert. Hotanalys hjälper säkerhetsteam att bli mer effektiva när de står inför nya hot. Hotanalys omfattar:

- E-postrelaterade identifieringar och metoder från Microsoft Defender för Office 365. Det här är ett tillägg till de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Endpoint.
- Incidenter visas relaterat till hoten.
- Förbättrad upplevelse för att snabbt identifiera och använda hanterbar information i rapporterna.

Du kan komma åt hotanalyser antingen från det övre vänstra navigeringsfältet i Microsoft 365 Defender eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för organisationen.

Läs mer om hur du [spårar och svarar på nya hot med hotanalyser.](./threat-analytics.md)

### <a name="email--collaboration"></a>E-post och samarbete

Spåra och undersöka hot mot användarnas e-post, spåra kampanjer med mera. Om du har använt Säkerhets- och efterlevnadscenter för Office 365 känner du igen det här.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Snabbstartsmenyn för e& postmeddelande med Collab (eller MSDO) på vänster sida Microsoft 365 Defender.":::

#### <a name="email-entity-page"></a>Sidan E-postenhet 

Sidan [E-post](../office-365-security/mdo-email-entity-page.md) *entitet ger* en enhetlig e-postinformation som har varit utspridd över olika sidor eller vyer tidigare. Undersökning av e-post efter hot och trender är *centraliserat*. Rubrikinformation och förhandsgranskning av e-post kan nås via samma e-postsida och annan användbar e-postrelaterad information. På samma sätt kan detonationsstatus för skadliga bifogade filer eller URL-adresser finnas på en flik på samma sida. Sidan E-postenhet ger administratörer och säkerhetsteam möjlighet att förstå ett hot via e-postmeddelande och dess status, snabbt, och sedan agera för att snabbt avgöra hur hanteringen ska hanteras.

### <a name="access-and-reports"></a>Åtkomst och rapporter

Visa rapporter, ändra dina inställningar och ändra användarroller.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Snabbstartsmenyn för Microsoft 365 Defender behörigheter och rapportering, till vänster i säkerhetscentret.":::

> [!NOTE]
> DKIM (DomainKeys Identified Mail) säkerställer att mål-e-postsystem litar på meddelanden som skickas utgående från din egen domän.
> För Defender för Office 365-användare kan  du nu hantera och rotera DKIM-tangenter genom Microsoft 365 Defender: eller gå till <https://security.microsoft.com/threatpolicy> Policy & **Threat** \> **policies** \> **DKIM**.
> 
> Mer information finns i Use [DKIM to validate outbound email sent from your custom domain](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email).

## <a name="whats-changed"></a>Se vad som har ändrats

Den här tabellen är en snabbreferens om hantering av hot där ändringar har gjorts mellan Säkerhets- & **efterlevnadscenter** och **Microsoft 365 Defender-portalen.** Klicka på länkarna om du vill läsa mer om dessa områden.

<br>

****

|Område|Beskrivning av ändring|
|---|---|
|[Undersökning](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|Samlar AIR-funktioner i [Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) och [Defender för Endpoint](../defender-endpoint/automated-investigations.md). Med de här uppdateringarna och förbättringarna kommer säkerhetsgruppen att kunna visa information om automatiska undersökningar och åtgärder som gäller för e-post, samarbetsinnehåll, användarkonton och enheter, allt på ett och samma ställe.|
|[Aviseringskö](../../compliance/alert-policies.md)|Den **utfällcentret** för Visa aviseringar i Office säkerhets- och efterlevnadscenter innehåller nu länkar till Microsoft 365 Defender. Klicka på länken **Öppna aviseringssida** så Microsoft 365 Defender öppnas. Du kan öppna sidan **Visa varningar** genom att klicka på en Office 365-avisering i kön Aviseringar.|
|[Attacksimulering-utbildning](../office-365-security/attack-simulation-training-insights.md)|Använd Attacksimulering-utbildning för att köra realistiska attackscenarier i din organisation. De här simulerade attackerna kan utbilda din personal innan ett riktigt angrepp påverkar din organisation. Attacksimulering-utbildning innehåller fler alternativ, förbättrade rapporter och förbättrade utbildningsflöden som gör det enklare att leverera och hantera dina attacker samt utbildningsscenarier.|
|

Inga ändringar i dessa områden:

- [Explorer](../office-365-security/threat-explorer.md)
- [Principer och regler](../../compliance/alert-policies.md)
- [Kampanj](../office-365-security/campaigns.md)
- [Insändning](../office-365-security/admin-submission.md)
- [Granska](./m365d-action-center.md)
- [Hotspårare](../office-365-security/threat-trackers.md)

Titta också i avsnittet **Relaterad information** längst ned i den här artikeln.

> [!IMPORTANT]
> I Microsoft 365 Defender <https://security.microsoft.com> () kombineras säkerhetsfunktioner i <https://securitycenter.windows.com> och <https://protection.office.com> . Vad som visas beror dock på din prenumeration. Om du bara har Microsoft Defender för Office 365 Abonnemang 1 eller 2, som fristående prenumerationer, visas inte funktioner för säkerhet för slutpunkter och Defender för Office Abonnemang 1-kunder, ser inte objekt som hotanalys.

> [!TIP]
> Alla Exchange Online Protection (EOP) ingår i Microsoft 365 Defender, eftersom EOP är huvudelementet i Defender för Office 365.

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender Startsida

Startsidan i portalen visar viktig sammanfattningsinformation om säkerhetsstatus för din Microsoft 365 miljö.

Använd den **Guidade rundturen** för att ta en snabb rundtur på sidorna endpoint eller e-post och samarbete. Observera att det du ser här beror på om du har licens för Defender för Office 365 och/eller Defender för Endpoint.

Den innehåller en länk till **Office 365 Säkerhets- och efterlevnadscenter** att jämföra. Den sista länken är till sidan **Nyheter** beskriver de senaste uppdateringarna.

## <a name="related-information"></a>Relaterad information

- [Omdirigera Säkerhets- och efterlevnadscenter för Office 365 till Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [Åtgärdscentret](./m365d-action-center.md)
- [E-post- och samarbetsaviseringar](../../compliance/alert-policies.md#default-alert-policies)
- [Anpassade regler för identifiering](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Skapa en simulering av ett nätfiskeangrepp](../office-365-security/attack-simulation-training.md) och [skapa en nyttolast för utbildning av personerna](../office-365-security/attack-simulation-training-payloads.md)
