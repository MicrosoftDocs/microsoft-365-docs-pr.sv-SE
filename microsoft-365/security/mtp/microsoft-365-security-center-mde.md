---
title: Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Microsoft 365 Säkerhetscenter
keywords: Komma igång med Microsoft 365 säkerhetscenter, OATP, MDATP, MDO, MDE, en fönsterruta, konvergerad portal, säkerhetsportal, defender säkerhetsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167473"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender för Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

Det förbättrade [säkerhetscentret i Microsoft 365](overview-security-center.md) kombinerar säkerhetsfunktioner som skyddar, identifierar, undersöker och svarar på e-post, samarbete, identitet [https://security.microsoft.com](https://security.microsoft.com) och enhetshot. I det här säkerhetscentret samlas funktioner från befintliga Microsoft-säkerhetsportaler, bland annat Microsoft Defender Säkerhetscenter och Office 365 Säkerhets- & Efterlevnadscenter.

Om du är bekant med Microsoft Defender Säkerhetscenter beskriver den här artikeln några av de ändringar och förbättringar som har gjorts i det förbättrade säkerhetscentret i Microsoft 365. Det finns dock några nya och uppdaterade element som du bör känna till.

Microsoft Defender [Säkerhetscenter har historiskt varit](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) ett hem för Microsoft Defender för Endpoint. Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches. För att minska antalet portaler är Microsoft 365 säkerhetscenter ett hem för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur.

> [!IMPORTANT]
> Vad du ser i Microsoft 365 säkerhetscenter beror på dina aktuella prenumerationer. Om du till exempel inte har en licens för Microsoft Defender för Office 365 visas inte avsnittet & e-postsamarbete.

Ta en titt på det förbättrade säkerhetscentret i Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .

Läs mer om fördelarna: [Översikt över Säkerhetscenter i Microsoft 365](overview-security-center.md)

## <a name="whats-changed"></a>Vad har ändrats

Den här tabellen är en snabbreferens över ändringarna mellan Microsoft Defender Säkerhetscenter och Microsoft 365 säkerhetscenter.

### <a name="alerts-and-actions"></a>Varningar och åtgärder

|**Område**  |**Beskrivning av ändring**  |
|---------|---------|
| [Incidenter & aviseringar](incidents-overview.md)  | I Säkerhetscenter för Microsoft 365 kan du hantera incidenter och aviseringar för alla slutpunkter, e-post och identiteter. Vi har konvergerat upplevelsen för att lättare hitta relaterade händelser. Mer information finns i [Incidentöversikt.](incidents-overview.md)   |
| [Jägning](advanced-hunting-overview.md)  |  Om du ändrar anpassade identifieringsregler som skapats i Microsoft Defender för Endpoint för att inkludera identitets- och e-posttabeller flyttas de automatiskt till Microsoft 365 Defender. Motsvarande aviseringar visas också i Microsoft 365 Defender. Mer information om dessa ändringar finns i [Migrera regler för anpassad identifiering.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules) Tabellen `DeviceAlertEvents` för avancerad sökning finns inte i Microsoft 365 Defender. Om du vill fråga om enhetsspecifik aviseringsinformation i Microsoft 365 Defender kan du använda tabellerna och tabellerna för att få plats med ännu mer information från `AlertInfo` `AlertEvidence` en rad olika källor. Skapa nästa enhetsrelaterade fråga genom att följa [skrivfrågor utan DeviceAlertEvents.](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)|
|[Åtgärdscenter](mtp-action-center.md)    | Listor med väntande och slutförda åtgärder som utförts efter automatiserade undersökningar och åtgärdsåtgärder. Åtgärdscenter i Microsoft Defender Säkerhetscenter listade väntande och slutförda åtgärder för åtgärder som vidtas endast på enheter, medan automatiserade undersökningar listade varningar och status. I det förbättrade säkerhetscentret i Microsoft 365 sammanför åtgärdscenter åtgärder och undersökningar för e-post, enheter och användare – allt på en plats.  |
| [Analys av hot](threat-analytics.md) |  Flyttades högst upp i navigeringsfältet för enklare identifiering och användning. Innehåller nu information om hot för både slutpunkter och e-post och samarbete.    |

### <a name="endpoints"></a>Slutpunkter

|**Område**  |**Beskrivning av ändring**  |
|---------|---------|
|Sök   |  I stället för att vara i rubriken flyttas microsoft Defender för slutpunktssökfältet under avsnittet Slutpunkter. Du kan fortsätta att söka efter enheter, filer, användare, URL:er, IP-adresser, svagheter, programvara och rekommendationer.  |
|[Instrumentpanelen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Det här är instrumentpanelen för säkerhetsåtgärder. Se en översikt över hur många aktiva aviseringar som utlöstes, vilka enheter som är i riskzonen, vilka användare som är på risknivå och allvarlighetsnivå för aviseringar, enheter och användare. Du kan också se om några enheter har sensorproblem, din allmänna tjänsthälsa och hur omatchade aviseringar har upptäckts. |
|Enhetsinventering | Inga ändringar. |
|[Sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Namnet förkortades så att det passar i navigeringsfönstret. Det är samma som avsnittet om hantering av hot och sårbarhet, med alla sidor undertill.     |
| Partner och API:er | Inga ändringar. |
| Utvärderingar & självstudiekurser    |     Nya test- och inlärningsfunktioner.     |
| Konfigurationshantering   |  Inga ändringar.  |

> [!NOTE]
> **Automatisk undersökning och åtgärd är** nu en del av incidenter. Du kan se händelser för automatisk undersökning och åtgärd på fliken **> Incidentundersökning.**

### <a name="access-and-reporting"></a>Access och rapportering

|**Område**  |**Beskrivning av ändring**  |
|---------|---------|
| Rapporter  | Se rapporter för slutpunkter och e-& samarbete, inklusive skydd mot hot, enhetens hälsa och efterlevnad och sårbara enheter. |
| Hälsa  |  Länkar för närvarande ut till sidan Tjänstens hälsa i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/) |
| Inställningar |  Hantera dina inställningar för Microsoft 365 säkerhetscenter, Microsoft 365 Defender, slutpunkter, e-& samarbete, identiteter och enhetsidentifiering.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Säkerhetsnavigering och funktioner i Microsoft 365

Det vänstra navigeringsfältet, eller snabbstartfältet, ser bekant ut. Det finns dock några nya och uppdaterade element i det här säkerhetscentret.

### <a name="incidents-and-alerts"></a>Incidenter och aviseringar

Sammanför incidenter och aviseringshantering i din e-post, dina enheter och identiteter. På aviseringssidan får du fullständig kontext till aviseringen genom att kombinera attacksignaler för att skapa en detaljerad berättelse. En ny enhetlig upplevelse sammanför nu en enhetlig vy av aviseringar för alla arbetsbelastningar. Du kan snabbt ändra, undersöka och vidta effektiva åtgärder.

- [Läs mer om incidenter](incidents-overview.md)
- [Läs mer om att hantera aviseringar](investigate-alerts.md)

![Snabbstartsfältet Aviseringar och åtgärder](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Jägning

Proaktivt söka efter hot, skadlig programvara och skadlig aktivitet i slutpunkter, Office 365-postlådor och mycket mer med hjälp av avancerade [sökningsfrågor.](advanced-hunting-overview.md) Dessa kraftfulla frågor kan användas för att hitta och granska hotindikatorer och -enheter för både kända och potentiella hot.

[Anpassade identifieringsregler kan](custom-detection-rules.md) byggas från avancerade sökfrågor för att hjälpa dig att proaktivt hålla utkik efter händelser som kan vara misslyckad av intrångsaktivitet och felkonfigurerade enheter.


### <a name="action-center"></a>Åtgärdscenter

I åtgärdscenter visas undersökningar som skapats med automatisk undersökning och svarsfunktioner. Den här automatiska självbetjäningsprocessen i Microsoft 365 Defender kan hjälpa säkerhetsteam genom att automatiskt svara på specifika händelser.

[Läs mer om Åtgärdscenter](mtp-action-center.md)

### <a name="threat-analytics"></a>Hotanalys

Få information om hot från en expert på Microsoft-säkerhet. Hotanalys hjälper säkerhetsteam att bli effektivare när de står inför nya hot. Hotanalys omfattar:

- E-postrelaterade identifieringar och åtgärder från Microsoft Defender för Office 365. Detta är utöver de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Slutpunkt.
- Vyn Incidenter som är relaterad till hoten.
- Förbättrad upplevelse för att snabbt identifiera och använda användbar information i rapporterna.

Du kan komma åt hotanalyser antingen från det övre vänstra navigeringsfältet i Säkerhetscenter för Microsoft 365 eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för din organisation.

Läs mer om hur du [spårar och svarar på nya hot med hotanalyser](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Avsnittet Slutpunkter

Visa och hantera säkerheten för slutpunkter i din organisation. Om du har använt Microsoft Defender Säkerhetscenter ser det bekant ut.

![Snabbstartfältet för slutpunkter](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Access och rapporter

Visa rapporter, ändra dina inställningar och ändra användarroller.

![Snabbstartfältet för Access och rapportering](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API-anslutningar

Om du använder [Defender för Slutpunkt SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)kan du fortsätta att göra det. Vi har lagt till nya länkar i API-nyttolasten som pekar på aviseringssidan eller incidentsidan i Microsoft 365-säkerhetsportalen. Nya API-fält innehåller LinkToMTP och IncidentLinkToMTP. Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>E-postaviseringar

Du kan fortsätta att använda e-postaviseringar för Defender för Endpoint. Vi har lagt till nya länkar i e-postmeddelanden som pekar på aviseringssidan eller incidentsidan i Säkerhetscenter i Microsoft 365. Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

## <a name="related-information"></a>Relaterad information

- [Microsoft 365 Säkerhetscenter](overview-security-center.md)
- [Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365](microsoft-365-security-mde-redirection.md)
