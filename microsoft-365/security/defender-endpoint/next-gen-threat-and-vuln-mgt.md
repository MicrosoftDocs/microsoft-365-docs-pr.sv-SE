---
title: Hot och hantering av säkerhetsrisker
description: Den här nya funktionen använder en riskbaserad metod för att upptäcka, prioritera och åtgärda eventuella svagheter och felkonfigurationer i slutpunkten.
keywords: threat & hantering av säkerhetsrisker, Hantering av hot och säkerhetsrisker, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, hantering av säkerhetsrisker, vulnerability assessment, threat and vulnerability scanning, secure configuration assessment, Microsoft Defender for Endpoint, endpoint vulnerabilities, next generation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934171"
---
# <a name="threat-and-vulnerability-management"></a>Hot och hantering av säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Att effektivt identifiera, utvärdera och åtgärda slutpunktsbrister är pivotalt i att köra ett hälsosamt säkerhetsprogram och minska organisationens risk. Hot och hantering av säkerhetsrisker fungerar som en infrastruktur för att minska exponering av organisationen, hårdnande slutpunktsyta och öka organisationens motståndskraft.

Upptäck säkerhetsproblem och felkonfigurationer i realtid med sensorerna, och utan behov av agenter eller periodiska genomsökningar. Den prioriterar säkerhetsproblem utifrån hotbildens landskap, identifieringar i organisationen, känslig information om sårbara enheter och affärskontext.

Titta på den här videon för en snabb överblick över Hantering av hot och säkerhetsrisker.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>Fylla arbetsflödesgaparna

Hot och hantering av säkerhetsrisker är inbyggt, i realtid och använder molnet. Den är helt integrerad med Microsofts säkerhetsstack för slutpunkter, Microsoft Intelligent Security Graph och knowledge base för programanalyser.  

Sårbarhetshantering är den första lösningen i branschen för att överbrygga klyftan mellan säkerhetsadministration och IT-administration under åtgärdsprocessen. Skapa en säkerhetsaktivitet eller -biljett genom att integrera med Microsoft Intune och Microsoft Endpoint Configuration Manager.

### <a name="real-time-discovery"></a>Identifiering i realtid

För att upptäcka säkerhetsproblem och felaktig konfiguration av slutpunkter använder Hantering av hot och säkerhetsrisker samma inbyggda Defender för Slutpunktssensorer för att minska krångliga nätverkssökningar och IT-overhead.

Den innehåller även:

- **Lager av enheter i realtid** – Enheter som introduceras till Defender för Endpoint rapporterar automatiskt och pushar sårbarhets- och säkerhetskonfigurationsdata till instrumentpanelen.
- **Insyn i programvara och säkerhetsproblem** –optisk information om organisationens lager av programvara och programvaruändringar som installationer, avinstallationer och korrigeringar. Nyligen identifierade säkerhetsproblem rapporteras med åtgärdsbara minskningar rekommendationer för program från första och tredje part.
- **Application runtime context** – Synlighet för programanvändningsmönster för bättre prioritering och beslut.
- **Konfigurationssäkerhet** – insyn i organisationens säkerhetskonfiguration eller felaktig konfiguration. Problem rapporteras i instrumentpanelen med interaktiva säkerhetsrekommendationer.

### <a name="intelligence-driven-prioritization"></a>Intelligence-driven prioritering

Hot och hantering av säkerhetsrisker hjälper kunderna att prioritera och fokusera på de svagheter som kan vara den mest brådskande och den högsta risken för organisationen. Den måste se till att rekommendationer om säkerhet finns med dynamiska hot och affärskontext:

- **Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations. Hot och hantering av säkerhetsrisker fokuserar på säkerhetsproblem som utnyttjas för närvarande i de jokertecken och nya hot som utgör den största risken.
- **Pinpointing av aktiva överträdelser** – korrelerar Hantering av hot och säkerhetsrisker och Identifiering och åtgärd på slutpunkt insikter för att prioritera säkerhetsproblem som utnyttjas i aktiva intrång i organisationen.
- **Skydda tillgångar med höga värden** – Identifiera exponerade enheter med affärskritiska program, konfidentiella data eller användare med höga värden.

### <a name="seamless-remediation"></a>Smidig åtgärd

Hot och hantering av säkerhetsrisker gör att säkerhetsadministratörer och IT-administratörer smidigt kan samarbeta för att åtgärda problem.

- **Åtgärdsförfrågningar som skickas till IT** – Skapa en åtgärdsaktivitet i Microsoft Intune enligt en viss säkerhetsrekommendationer. Vi planerar att utöka den här funktionen till andra plattformar för IT-säkerhetshantering.
- **Alternativa åtgärder – Få** insikter om ytterligare minskningar, till exempel konfigurationsändringar som kan minska risker som är associerade med svagheter i programvaran.
- **Status för åtgärder i realtid** – övervakning i realtid av status och status för åtgärdsaktiviteter i organisationen.

## <a name="threat-and-vulnerability-management-walk-through"></a>Hot och hantering av säkerhetsrisker genomgång

I den här videon får du en omfattande genomgång av Hantering av hot och säkerhetsrisker.

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>Navigeringsfönstret

Område | Beskrivning
:---|:---
**Instrumentpanelen**   | Få en högnivåvy av exponeringsresultatet för organisationen, Microsoft Secure Score för enheter, exponeringsfördelning av enheter, toppsäkerhetsrekommendationer, övre sårbar programvara, toppreparationsaktiviteter och top-exponerade enhetsdata.
[**Säkerhetsrekommendationer**](tvm-security-recommendation.md) | Se listan över säkerhetsrekommendationer och relaterad information om hot. När du väljer ett objekt i listan öppnas en utfällbarhetspanel med sårbarhetsinformation, en länk för att öppna programvarusidan samt alternativ för åtgärder och undantag. Du kan också öppna ett ärende i Intune om dina enheter är anslutna via Azure Active Directory och du har aktiverat Intune-anslutningarna i Defender för Slutpunkt.
[**Åtgärda**](tvm-remediation.md) | Se åtgärder som du har skapat och undantag från rekommendation.
[**Programvaruinventering**](tvm-software-inventory.md) | Visa listan över sårbar programvara i organisationen, tillsammans med information om säkerhet och hot.
[**Svagheter**](tvm-weaknesses.md) | Se listan över vanliga säkerhetsproblem och exponeringar (CVEs) i organisationen.
[**Tidlinje för händelse**](threat-and-vuln-mgt-event-timeline.md) | Visa händelser som kan påverka organisationens risk.

## <a name="apis"></a>API:er

Kör Hantering av hot och säkerhetsrisker API-anrop för att automatisera hantering av säkerhetsrisker arbetsflöden. Läs mer i det [här Microsoft Tech Community-blogginlägget](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).

Se följande artiklar för relaterade API:er:

- [Microsoft Defender för Endpoint API:er som stöds](exposed-apis-list.md)
- [Dator-API:er](machine.md)
- [API:er för rekommendation](vulnerability.md)
- [Poäng-API:er](score.md)
- [Programvaru-API:er](software.md)
- [Sårbarhets-API:er](vulnerability.md)
- [Lista sårbarheter efter maskin och programvara](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>Se även

- [Operativsystem och plattformar som stöds](tvm-supported-os.md)
- [Hot och hantering av säkerhetsrisker instrumentpanel](tvm-dashboard-insights.md)
- [BLOGG: Microsofts & sårbarhetshantering hjälper nu tusentals kunder att upptäcka, prioritera och åtgärda säkerhetsproblem i realtid](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
