---
title: Microsoft Defender för slutpunkt i Microsoft 365 Defender
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter att Microsoft 365 Defender
keywords: Komma igång med Microsoft 365 Defender, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt, MDO, MDE, säkerhetsportal, defender-säkerhetsportalen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: b43b7c99c6585e8610d34f3c4e5b372fb1c829a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842632"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft Defender för slutpunkt i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>Snabbreferens

I bilden och i tabellen nedan visas ändringar i navigeringen mellan Microsoft Defender Säkerhetscenter och Microsoft 365 Defender.

> [!div class="mx-imgBorder"]
> ![Bild av vad som flyttades dit](../../media/mde-m3d-security-center.png)

| Microsoft Defender Säkerhetscenter | Microsoft 365 Defender |
|---------|---------|
| Instrumentpaneler <ul><li>Säkerhetsåtgärder</li><li>Analys av hot</li></ul>  |home <ul><li>Analys av hot</li></ul>   |
| Incidenter | Incidenter & aviseringar |
| Enhetsinventering | Enhetsinventering |
| Varningskö | Incidenter & aviseringar |
| Automatiserade undersökningar | Åtgärdscenter |
| Avancerad jakt | Jakt |
| Rapporter | Rapporter |
| Partners & API:er | Partners & API:er |
| Hot & sårbarhetshantering | Sårbarhetshantering |
| Utvärdering och självstudiekurser | Utvärderingskurser & självstudiekurser |
| Konfigurationshantering | Konfigurationshantering |
| Inställningar | Inställningar | 

Den förbättrade [Microsoft 365 Defender](overview-security-center.md) kombinerar säkerhetsfunktioner som skyddar, identifierar, undersöker och svarar på e-post, [https://security.microsoft.com](https://security.microsoft.com) samarbete, identitet och enhetshot. Detta sammanför funktioner från befintliga Microsoft-säkerhetsportaler, Microsoft Defender Säkerhetscenter och säkerhets- Office 365 säkerhets- & efterlevnadscenter.

Om du är bekant med Microsoft Defender Säkerhetscenter här artikeln beskriver vi några av de ändringar och förbättringar som Microsoft 365 Defender. Det finns dock några nya och uppdaterade element som du bör känna till.

Historiskt sett har [Microsoft Defender Säkerhetscenter](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) varit hemmet för Microsoft Defender för Endpoint. Företagssäkerhetsteam har använt det för att övervaka och hjälpa till att svara på varningar om potentiella avancerade fortlöpande hot eller databrott. För att minska antalet portaler är Microsoft 365 Defender ett hem för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur.

Microsoft Defender för slutpunkt i Microsoft 365 Defender har stöd för att bevilja åtkomst till hanterade säkerhetstjänstleverantörer [(MSSP: er)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) på samma sätt som åtkomst beviljas i [Microsoft Defender säkerhetscenter.](mssp-access.md)

> [!IMPORTANT]
> Vad som visas i Microsoft 365 Defender beror på dina aktuella prenumerationer. Om du till exempel inte har en licens för Microsoft Defender för Office 365 visas inte avsnittet E& samarbete.

> [!Note]
> Microsoft 365 Defender är inte tillgängligt för:
>- Us Government Community Cloud (GCC)
>- Us Government Community Cloud High (GCC High)
>- US Department of Defense
>- Alla amerikanska statliga myndigheter med kommersiella licenser

Ta en titt på Microsoft 365 Defender: [https://security.microsoft.com](https://security.microsoft.com) .

Läs mer om fördelarna: [Översikt över Microsoft 365 Defender](overview-security-center.md)

## <a name="whats-changed"></a>Se vad som har ändrats

Den här tabellen är en snabbreferens för ändringarna mellan Microsoft Defender Säkerhetscenter och Microsoft 365 Defender.

### <a name="alerts-and-actions"></a>Aviseringar och åtgärder

| Område | Beskrivning av ändring |
|---------|---------|
| [Incidenter & aviseringar](incidents-overview.md)  | I Microsoft 365 Defender kan du hantera incidenter och aviseringar för alla dina slutpunkter, e-post och identiteter. Vi har konvergerat upplevelsen för att lättare hitta relaterade händelser. Mer information finns i [Incidentöversikt.](incidents-overview.md)   |
| [Jakt](advanced-hunting-overview.md)  |  Om du ändrar regler för anpassad identifiering som skapats i Microsoft Defender för Endpoint för att inkludera identitets- och e-posttabeller flyttas de automatiskt till Microsoft 365 Defender. Motsvarande aviseringar visas också i Microsoft 365 Defender. Mer information om dessa ändringar finns i [Migrera regler för anpassad identifiering.](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules) <br><br>Tabellen `DeviceAlertEvents` för avancerad sökning är inte tillgänglig i Microsoft 365 Defender. Om du vill söka efter enhetsspecifik aviseringsinformation i Microsoft 365 Defender kan du använda tabellerna och dem för att ge utrymme för ännu mer information från `AlertInfo` `AlertEvidence` en rad olika källor. Skapa nästa enhetsrelaterade fråga genom att följa [Skrivfrågor utan DeviceAlertEvents.](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)|
|[Åtgärdscenter](m365d-action-center.md)    | Listor med väntande och slutförda åtgärder som utförts efter automatiserade undersökningar och åtgärdsåtgärder. Åtgärdscenter i den Microsoft Defender Säkerhetscenter listade väntande och slutförda åtgärder för åtgärder som utförts endast på enheter, medan automatiska undersökningar listade aviseringar och status. I den förbättrade Microsoft 365 Defender sammanför Åtgärdscenter åtgärder och undersökningar mellan e-post, enheter och användare – allt på en och samma plats.  |
| [Analys av hot](threat-analytics.md) |  Flyttad högst upp i navigeringsfältet så att det blir lättare att hitta och använda den. Innehåller nu information om hot för både slutpunkter och e-post och samarbete.    |

### <a name="endpoints"></a>Slutpunkter

| Område | Beskrivning av ändring |
|---------|---------|
|Söka   |  I stället för att visas som rubrik flyttas sökfältet i Microsoft Defender för slutpunkt under avsnittet Slutpunkter. Du kan fortsätta att söka efter enheter, filer, användare, URL:er, IP-adresser, säkerhetsproblem, programvara och rekommendationer.  |
|[Instrumentpanelen](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Det här är din instrumentpanel för säkerhetsåtgärder. Se en översikt över hur många aktiva aviseringar som utlöstes, vilka enheter som är i risktagande, vilka användare som är i riskzonen och allvarlighetsnivå för aviseringar, enheter och användare. Du kan också se om några enheter har sensorproblem, din allmänna tjänsthälsa och hur omatchade aviseringar har upptäckts. |
|Enhetsinventering | Inga ändringar. |
|[Sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Namnet förkortades så att det passar i navigeringsfönstret. Det är samma som Hantering av hot och säkerhetsrisker, med alla sidor undertill.     |
| Partners och API:er | Inga ändringar. |
| Utvärderingar & självstudiekurser    |     Nya test- och inlärningsfunktioner.     |
| Konfigurationshantering   |  Inga ändringar.  |

> [!NOTE]
> **Automatisk undersökning och åtgärder är** nu en del av incidenter. Du kan se Automatiserad undersökning och åtgärdshändelser på fliken **> Undersökning.**

> [!TIP]
> Enhetssökning görs från slutpunkter > Sökning.

### <a name="access-and-reporting"></a>Access och rapportering

| Område | Beskrivning av ändring |
|---------|---------|
| Rapporter  | Se rapporter för slutpunkter och e& för samarbete, inklusive skydd mot hot, enhetshälsa och efterlevnad och sårbara enheter. |
| Hälsa  |  Länkar för närvarande till sidan "Tjänstens hälsa" i [Microsoft 365 administrationscentret](https://admin.microsoft.com/). |
| Inställningar |  Hantera dina inställningar för Microsoft 365 Defender, Slutpunkter, E& samarbete, identiteter och enhetsidentifiering.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 säkerhetsnavigering och funktioner

Det vänstra navigeringsfältet eller snabbstartsfältet ser bekant ut. Det finns dock några nya och uppdaterade element i det här säkerhetscentret.

### <a name="incidents-and-alerts"></a>Incidenter och aviseringar

Samlar incidenter och aviseringar för e-post, enheter och identiteter. Aviseringssidan ger fullständig kontext till aviseringen genom att kombinera attacksignaler för att konstruera en detaljerad berättelse. I en ny, enhetlig upplevelse samlas nu en enhetlig vy av aviseringar för arbetsbelastningar. Du kan snabbt göra triage, undersöka och vidta effektiva åtgärder.

- [Läs mer om incidenter](incidents-overview.md)
- [Läs mer om hur du hanterar varningar](investigate-alerts.md)

![Snabbstartfältet Aviseringar och Åtgärder](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Jakt

Sök proaktivt efter hot, skadlig programvara och skadlig aktivitet i dina slutpunkter, Office 365-postlådor med mera med hjälp av [avancerade sökfrågor](advanced-hunting-overview.md). Dessa kraftfulla frågor kan användas för att hitta och granska hotindikatorer och enheter för både kända och potentiella hot.

[Anpassade identifieringsregler kan](custom-detection-rules.md) byggas från avancerade sökfrågor för att proaktivt bevaka händelser som kan vara på grund av intrångsaktivitet och felkonfigurerade enheter.


### <a name="action-center"></a>Åtgärdscenter

Åtgärdscenter visar de undersökningar som skapats med automatiska undersöknings- och svarsfunktioner. Den här automatiserade självläkningen i Microsoft 365 Defender kan hjälpa säkerhetsteam genom att automatiskt svara på specifika händelser.

[Läs mer om Åtgärdscenter](m365d-action-center.md).

### <a name="threat-analytics"></a>Analys av hot

Få information om hot från Microsofts säkerhetsexpert. Hotanalys hjälper säkerhetsteam att bli mer effektiva när de står inför nya hot. Hotanalys omfattar:

- E-postrelaterade identifieringar och metoder från Microsoft Defender för Office 365. Det här är ett tillägg till de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Endpoint.
- Incidenter visas relaterat till hoten.
- Förbättrad upplevelse för att snabbt identifiera och använda hanterbar information i rapporterna.

Du kan komma åt hotanalyser antingen från det övre vänstra navigeringsfältet i Microsoft 365 Defender eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för din organisation.

Läs mer om hur du [spårar och svarar på nya hot med hotanalyser.](./threat-analytics.md)

### <a name="endpoints-section"></a>Avsnittet Slutpunkter

Visa och hantera säkerheten för slutpunkter i din organisation. Om du har använt Microsoft Defender Säkerhetscenter ser det bekant ut.

![Snabbstartfältet Slutpunkter](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Access och rapporter

Visa rapporter, ändra dina inställningar och ändra användarroller.

![Snabbstartsfältet i Access och Rapportering](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API-anslutningar

Om du använder [Defender för slutpunkt SIEM API](../defender-endpoint/enable-siem-integration.md)kan du fortsätta att göra det. Vi har lagt till nya länkar i API-nyttolasten som pekar på aviseringssidan eller incidentsidan i Microsoft 365 säkerhetsportalen. Nya API-fält innehåller LinkToMTP och IncidentLinkToMTP. Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Microsoft 365 Defender.](./microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>E-postaviseringar

Du kan fortsätta att använda e-postaviseringar för Defender för Endpoint. Vi har lagt till nya länkar i e-postmeddelandena som pekar på aviseringssidan eller incidentsidan i Microsoft 365 Defender. Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Microsoft 365 Defender.](./microsoft-365-security-mde-redirection.md)

### <a name="managed-security-service-providers-mssp"></a>Tjänstleverantörer för hanterade säkerhetstjänster (MSSP)

Det går för närvarande inte att logga in på flera klientorganisationar samtidigt i samma webbläsarsession i den enhetliga portalen. Du kan avanmäla dig från den automatiska omdirigeringen genom att återgå till den tidigare Microsoft Defender för [Endpoint-portalen](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), så att funktionen bibehålls tills problemet är löst.

## <a name="related-information"></a>Relaterad information

- [Microsoft 365 Defender](overview-security-center.md)
- [Microsoft Defender för slutpunkt i Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Omdirigera konton från Microsoft Defender för Slutpunkt till Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)
