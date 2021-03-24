---
title: Hantering av hot och sårbarhet
description: Den här nya funktionen använder en riskbaserad metod för att upptäcka, prioritera och åtgärda eventuella svagheter och felkonfigurationer i slutpunkten.
keywords: threat & vulnerability management, threat and vulnerability management, MDATP TVM, MDATP-TVM, vulnerability management, vulnerability assessment, threat and vulnerability scanning, secure configuration assessment, microsoft defender atp, microsoft defender atp, endpoint vulnerabilities, next generation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: a56b10ec32611a046bffb5ea3c0bfd226c51f8cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069337"
---
# <a name="threat-and-vulnerability-management"></a>Hantering av hot och sårbarhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Att effektivt identifiera, utvärdera och åtgärda slutpunktsbrister är pivotalt i att köra ett hälsosamt säkerhetsprogram och minska organisationens risk. Hantering av hot och risker fungerar som en infrastruktur för att minska exponering av organisationen, hårdnande ändpunktsyta och öka organisationens motståndskraft.

Upptäck säkerhetsproblem och felkonfigurationer i realtid med sensorerna, och utan behov av agenter eller periodiska genomsökningar. Den prioriterar säkerhetsproblem utifrån hotbildens landskap, identifieringar i organisationen, känslig information om sårbara enheter och affärskontext.

Titta på den här videon för en snabb överblick över hot och sårbarhetshantering.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>Fylla arbetsflödesgaparna

Hantering av hot och sårbarheter är inbyggda, i realtid och använder molnet. Det är helt integrerat med Microsoft-slutpunktssäkerhetsstacken, Microsoft Intelligent Security Graph och kunskapsbasen för programanalyser.  

Sårbarhetshantering är den första lösningen i branschen för att överbrygga klyftan mellan säkerhetsadministration och IT-administration under åtgärdsprocessen. Skapa en säkerhetsuppgift eller -biljett genom att integrera med Microsoft Intune och Microsoft Endpoint Configuration Manager.

### <a name="real-time-discovery"></a>Identifiering i realtid

För att upptäcka säkerhetsproblem och felkonfigurering använder hantering av hot och risker samma inbyggda Defender för slutpunktssensorer för att minska krångliga nätverkssökningar och IT-overhead.

Den innehåller även:

- **Lager av enheter i realtid** – Enheter som introduceras till Defender för Endpoint rapporterar automatiskt och pushar sårbarhets- och säkerhetskonfigurationsdata till instrumentpanelen.
- **Insyn i programvara och säkerhetsproblem** –optisk information om organisationens lager av programvara och programvaruändringar som installationer, avinstallationer och korrigeringar. Nyligen identifierade säkerhetsproblem rapporteras med åtgärdsbara minskningar rekommendationer för program från första och tredje part.
- **Application runtime context** – Synlighet för programanvändningsmönster för bättre prioritering och beslut.
- **Konfigurationssäkerhet** – insyn i organisationens säkerhetskonfiguration eller felaktig konfiguration. Problem rapporteras i instrumentpanelen med interaktiva säkerhetsrekommendationer.

### <a name="intelligence-driven-prioritization"></a>Intelligence-driven prioritering

Hantering av hot och risker hjälper kunderna att prioritera och fokusera på de svagheter som utgör den mest brådskande och högsta risken för organisationen. Den måste se till att rekommendationer om säkerhet finns med dynamiska hot och affärskontext:

- **Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations. Hantering av hot och risker fokuserar på säkerhetsproblem som utnyttjas för närvarande i de jokertecken och nya hot som utgör den största risken.
- **Pinpointing av aktiva överträdelser** – Korrelerar hot och sårbarhetshantering och EDR-insikter för att prioritera säkerhetsproblem som utnyttjas i aktiva intrång i organisationen.
- **Skydda tillgångar med höga värden** – Identifiera exponerade enheter med affärskritiska program, konfidentiella data eller användare med höga värden.

### <a name="seamless-remediation"></a>Smidig åtgärd

Med hantering av hot och sårbarhet kan säkerhetsadministratörer och IT-administratörer samarbeta smidigt för att åtgärda problem.

- **Åtgärdsförfrågningar som skickas till IT** – Skapa en åtgärdsuppgift i Microsoft Intune utifrån en viss säkerhetsrekommendationer. Vi planerar att utöka den här funktionen till andra plattformar för IT-säkerhetshantering.
- **Alternativa åtgärder – Få** insikter om ytterligare minskningar, till exempel konfigurationsändringar som kan minska risker som är associerade med svagheter i programvaran.
- **Status för åtgärder i realtid** – övervakning i realtid av status och status för åtgärdsaktiviteter i organisationen.

## <a name="threat-and-vulnerability-management-walk-through"></a>Genomgång av hot- och sårbarhetshantering

I den här videon får du en omfattande genomgång av hot och sårbarhetshantering.

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>Navigeringsfönstret

Område | Beskrivning
:---|:---
**Instrumentpanelen**   | Få en högnivåvy av exponeringsresultatet för organisationen, Microsoft Secure Score för enheter, exponeringsfördelning av enheter, toppsäkerhetsrekommendationer, övre sårbar programvara, toppreparationsaktiviteter och top-exponerade enhetsdata.
[**Säkerhetsrekommendationer**](tvm-security-recommendation.md) | Se listan över säkerhetsrekommendationer och relaterad information om hot. När du väljer ett objekt i listan öppnas en utfällbarhetspanel med sårbarhetsinformation, en länk för att öppna programvarusidan samt alternativ för åtgärder och undantag. Du kan också öppna ett ärende i Intune om dina enheter är anslutna via Azure Active Directory och du har aktiverat Dina Intune-anslutningar i Defender för slutpunkt.
[**Åtgärda**](tvm-remediation.md) | Se åtgärder som du har skapat och undantag från rekommendation.
[**Inventering av programvara**](tvm-software-inventory.md) | Visa listan över sårbar programvara i organisationen, tillsammans med information om säkerhet och hot.
[**Svagheter**](tvm-weaknesses.md) | Se listan över vanliga säkerhetsproblem och exponeringar (CVEs) i organisationen.
[**Händelsetidslinje**](threat-and-vuln-mgt-event-timeline.md) | Visa händelser som kan påverka organisationens risk.

## <a name="apis"></a>API:er

Kör API-anrop som rör hot och sårbarhetshantering för att automatisera arbetsflöden för hantering av sårbarheter. Läs mer i det [här Microsoft Tech Community-blogginlägget](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).

Se följande artiklar för relaterade API:er:

- [Microsoft Defender-API:er som stöds för slutpunkts-API:er](exposed-apis-list.md)
- [Dator-API:er](machine.md)
- [API:er för rekommendation](vulnerability.md)
- [Poäng-API:er](score.md)
- [Programvaru-API:er](software.md)
- [Sårbarhets-API:er](vulnerability.md)
- [Lista säkerhetsproblem efter maskin och programvara](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>Se även

- [Operativsystem och plattformar som stöds](tvm-supported-os.md)
- [Instrumentpanel för hantering av hot och hot](tvm-dashboard-insights.md)
- [BLOGG: Microsofts & sårbarhetshantering hjälper nu tusentals kunder att upptäcka, prioritera och åtgärda säkerhetsproblem i realtid](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
