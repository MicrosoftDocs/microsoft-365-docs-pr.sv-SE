---
title: Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Säkerhetscenter för Microsoft 365
keywords: Komma igång med Microsoft 365 Säkerhetscenter, OATP, MDATP, MDO, MDE, enda fönsterruta av glas, konvergerad portal, säkerhetsportal, Defender-säkerhetsportalen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: edf0baa369142f6a0aafc86794a47ab0be6e345a
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760056"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

Det förbättrade [säkerhetscentret i Microsoft 365](overview-security-center.md) kombinerar säkerhetsfunktioner som skyddar, identifierar, undersöker och svarar på e-post, samarbete, identitet [https://security.microsoft.com](https://security.microsoft.com) och enhetshot. I det här säkerhetscentret samlas funktioner från befintliga Microsoft-säkerhetsportaler, bland annat Microsoft Defender Säkerhetscenter och Säkerhetscenter för Office 365 & efterlevnadscenter.

Om du är bekant med Microsoft Defender Säkerhetscenter beskriver den här artikeln några av de ändringar och förbättringar som har gjorts i det förbättrade säkerhetscentret i Microsoft 365. Det finns dock några nya och uppdaterade element som du bör känna till.

Tidigare har [Microsoft Defender Säkerhetscenter varit](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) hemmet för Microsoft Defender för Endpoint. Företagssäkerhetsteam har använt det för att övervaka och hjälpa till att svara på varningar om potentiella avancerade fortlöpande hot eller databrott. För att minska antalet portaler kommer Microsoft 365-säkerhetscentret att vara ett hem för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur.

Microsoft Defender för slutpunkt i Säkerhetscenter i Microsoft 365 har stöd för att bevilja åtkomst till tjänstleverantörer av hanterade säkerhetstjänster [(MSSP: er)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) på samma sätt som åtkomst beviljas i [Microsoft Defender säkerhetscenter.](mssp-access.md)


> [!IMPORTANT]
> Vad du ser i Microsoft 365 Säkerhetscenter beror på dina aktuella prenumerationer. Om du till exempel inte har en licens för Microsoft Defender för Office 365 visas inte avsnittet E& samarbete.

>[!Note]
>Den nya enhetliga portalen är inte tillgänglig för:
>- US Government Community Cloud (GCC)
>- US Government Community Cloud High (GCC High)
>- US Department of Defense
>- Alla amerikanska statliga myndigheter med kommersiella licenser

Ta en titt på det förbättrade säkerhetscentret för Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .

Läs mer om fördelarna: [Översikt för Microsoft 365 Säkerhetscenter](overview-security-center.md)

## <a name="whats-changed"></a>Se vad som har ändrats

Den här tabellen är en snabbreferens över ändringarna mellan Microsoft Defender Säkerhetscenter och Säkerhetscenter för Microsoft 365.

### <a name="alerts-and-actions"></a>Aviseringar och åtgärder

|**Område**  |**Beskrivning av ändring** |
|---------|---------|
| [Incidenter & aviseringar](incidents-overview.md)  | I Säkerhetscenter för Microsoft 365 kan du hantera incidenter och aviseringar för alla slutpunkter, e-post och identiteter. Vi har konvergerat upplevelsen för att lättare hitta relaterade händelser. Mer information finns i [Incidentöversikt.](incidents-overview.md)   |
| [Jakt](advanced-hunting-overview.md)  |  Om du ändrar regler för anpassad identifiering som skapats i Microsoft Defender för Endpoint för att inkludera identitets- och e-posttabeller flyttas de automatiskt till Microsoft 365 Defender. Motsvarande aviseringar visas också i Microsoft 365 Defender. Mer information om dessa ändringar finns i [Migrera regler för anpassad identifiering.](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules) <br><br>Tabellen `DeviceAlertEvents` för avancerad sökning är inte tillgänglig i Microsoft 365 Defender. Om du vill söka efter enhetsspecifik aviseringsinformation i Microsoft 365 Defender kan du använda tabellerna och tabellerna för att få plats med ännu mer information från `AlertInfo` `AlertEvidence` en rad olika källor. Skapa nästa enhetsrelaterade fråga genom att följa [Skrivfrågor utan DeviceAlertEvents.](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)|
|[Åtgärdscenter](m365d-action-center.md)    | Listor med väntande och slutförda åtgärder som utförts efter automatiserade undersökningar och åtgärdsåtgärder. Tidigare listade Åtgärdscenter i Microsoft Defender Säkerhetscenter väntande och slutförda åtgärder för åtgärder som utförts endast på enheter, medan automatiska undersökningar listade aviseringar och status. I det förbättrade Säkerhetscenter för Microsoft 365 sammanför Åtgärdscenter åtgärder och undersökningar för e-post, enheter och användare – allt på en och samma plats.  |
| [Analys av hot](threat-analytics.md) |  Flyttad högst upp i navigeringsfältet så att det blir lättare att hitta och använda den. Innehåller nu information om hot för både slutpunkter och e-post och samarbete.    |

### <a name="endpoints"></a>Slutpunkter

|**Område**  |**Beskrivning av ändring**  |
|---------|---------|
|Sök   |  I stället för att visas som rubrik flyttas sökfältet i Microsoft Defender för slutpunkt under avsnittet Slutpunkter. Du kan fortsätta att söka efter enheter, filer, användare, URL:er, IP-adresser, säkerhetsproblem, programvara och rekommendationer.  |
|[Instrumentpanelen](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Det här är din instrumentpanel för säkerhetsåtgärder. Se en översikt över hur många aktiva aviseringar som utlöstes, vilka enheter som är i risktagande, vilka användare som är i riskzonen och allvarlighetsnivå för aviseringar, enheter och användare. Du kan också se om några enheter har sensorproblem, din allmänna tjänsthälsa och hur omatchade aviseringar har upptäckts. |
|Enhetsinventering | Inga ändringar. |
|[Sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Namnet förkortades så att det passar i navigeringsfönstret. Det är samma som avsnittet om hot och sårbarhetshantering, med alla sidor undertill.     |
| Partners och API:er | Inga ändringar. |
| Utvärderingar & självstudiekurser    |     Nya test- och inlärningsfunktioner.     |
| Konfigurationshantering   |  Inga ändringar.  |

> [!NOTE]
> **Automatisk undersökning och åtgärder är** nu en del av incidenter. Du kan se Automatiserad undersökning och åtgärdshändelser på fliken **> Undersökning.**

### <a name="access-and-reporting"></a>Access och rapportering

|**Område**  |**Beskrivning av ändring**  |
|---------|---------|
| Rapporter  | Se rapporter för slutpunkter och e& för samarbete, inklusive skydd mot hot, enhetshälsa och efterlevnad och sårbara enheter. |
| Hälsa  |  Länkar för närvarande till sidan "Tjänstens hälsa" i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/) |
| Inställningar |  Hantera dina inställningar för Microsoft 365 Säkerhetscenter, Microsoft 365 Defender, Slutpunkter, E-& samarbete, identiteter och enhetsidentifiering.   |

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

[Läs mer om Åtgärdscenter](m365d-action-center.md)

### <a name="threat-analytics"></a>Analys av hot

Få information om hot från Microsofts säkerhetsexpert. Hotanalys hjälper säkerhetsteam att bli mer effektiva när de står inför nya hot. Hotanalys omfattar:

- E-postrelaterade identifieringar och metoder från Microsoft Defender för Office 365. Det här är ett tillägg till de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Endpoint.
- Incidenter visas relaterat till hoten.
- Förbättrad upplevelse för att snabbt identifiera och använda hanterbar information i rapporterna.

Du kan komma åt hotanalyser antingen från det övre vänstra navigeringsfältet i Microsoft 365 säkerhetscenter eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för din organisation.

Läs mer om hur du [spåra och svara på nya hot med hjälp av hotanalys](./threat-analytics.md)

### <a name="endpoints-section"></a>Avsnittet Slutpunkter

Visa och hantera säkerheten för slutpunkter i din organisation. Om du har använt Microsoft Defender Säkerhetscenter ser det bekant ut.

![Snabbstartfältet Slutpunkter](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Access och rapporter

Visa rapporter, ändra dina inställningar och ändra användarroller.

![Snabbstartsfältet i Access och Rapportering](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API-anslutningar

Om du använder [Defender för slutpunkt SIEM API](../defender-endpoint/enable-siem-integration.md)kan du fortsätta att göra det. Vi har lagt till nya länkar i API-nyttolasten som pekar på aviseringssidan eller incidentsidan i Microsoft 365-säkerhetsportalen. Nya API-fält innehåller LinkToMTP och IncidentLinkToMTP. Mer information finns i Omdirigera [konton från Microsoft Defender för Endpoint till Säkerhetscenter för Microsoft 365.](./microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>E-postaviseringar

Du kan fortsätta att använda e-postaviseringar för Defender för Endpoint. Vi har lagt till nya länkar i e-postmeddelandena som pekar på aviseringssidan eller incidentsidan i säkerhetscentret i Microsoft 365. Mer information finns i Omdirigera [konton från Microsoft Defender för Endpoint till Säkerhetscenter för Microsoft 365.](./microsoft-365-security-mde-redirection.md)

## <a name="related-information"></a>Relaterad information

- [Microsoft 365 Säkerhetscenter](overview-security-center.md)
- [Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365](microsoft-365-security-mde-redirection.md)