---
title: Säkerhetsproblem i min organisation – hantering av hot och risker
description: Här listas vanliga säkerhetsproblem och exponeringar (CVE) för svagheter i den programvara som körs i organisationen. Upptäcks av Microsoft Defender för funktioner för slutpunktshot och sårbarhetshantering.
keywords: mdatp-hot & sårbarhetshantering, hot och sårbarhetshantering, mdatp tvm-ändringssida, hitta svagheter via tvm, tvm-sårbarhetslista, sårbarhetsinformation i tvm
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0f573b2425764876e877de44555691979a0e1fcf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689407"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>Säkerhetsproblem i min organisation – hantering av hot och risker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Hantering av hot och risker använder samma signaler i Defender för Endpoints slutpunktsskydd för att söka igenom och upptäcka svagheter.

På **sidan Svagheter** visas svagheter i programvaran som dina enheter exponeras för genom att lista CVE-ID (Common Vulnerabilities and Exposures). Du kan också se allvarlighetsgrad, CVSS-klassificering (Common Vulnerability Rating System), aktuella uppgifter i organisationen, motsvarande intrång, hotinsikter med mera.

>[!NOTE]
>Om det inte finns någon officiell CVE-ID tilldelad till en sårbarhet, tilldelas sårbarhetsnamnet med hjälp av hantering av hot och sårbarhet.

>[!TIP]
>E-postmeddelanden om nya sårbarhetshändelser finns i [Konfigurera e-postaviseringar om säkerhetsrisk i Microsoft Defender för slutpunkt](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-weaknesses-page"></a>Gå till sidan Svagheter

Gå till sidan Svagheter på ett par olika sätt:

- Välja **Känslighet** från navigeringsmenyn för hot och sårbarhetshantering i [Microsoft Defender Säkerhetscenter](portal-overview.md)
- Global sökning

### <a name="navigation-menu"></a>Navigeringsmeny

Gå till navigeringsmenyn för hot och sårbarhetshantering och välj **Svagheter** för att öppna listan över CV:er.

### <a name="vulnerabilities-in-global-search"></a>Säkerhetsproblem i global sökning

1. Gå till den nedrullningsmenyn för global sökning.
2. Välj **Sårbarhet** och nyckel i det vanliga säkerhetsproblem och exponerings-ID (CVE) som du letar efter och välj sedan sökikonen. Sidan **Bevarande** öppnas med den CVE-information som du letar efter.
![Global sökruta med listrutan "sårbarhet" markerat och ett exempel på CVE.](images/tvm-vuln-globalsearch.png)
3. Välj CVE för att öppna en utfällbarhetspanel med mer information, inklusive sårbarhetsbeskrivning, information om hot, hotinsikter och exponerade enheter.

Om du vill se resten av svagheterna på sidan **Förvarna** skriver du CVE och väljer sedan sök.

## <a name="weaknesses-overview"></a>Översikt över svagheter

Åtgärda säkerhetsproblem i exponerade enheter för att minska risken för tillgångar och organisation. Om kolumnen **Exponerade** enheter visar 0, innebär det att du inte är i riskabelt fall.

![Svagheter på startsidan.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a>Insikter om intrång och hot

Visa eventuella relaterade insikter om intrång och hot **i kolumnen** Hot när ikonerna är röda.

 >[!NOTE]
 > Prioritera alltid rekommendationer som är associerade med pågående hot. Dessa rekommendationer markeras med ikonen för ![ hotinsikter Enkel ritning av ett rött fel.](images/tvm_bug_icon.png) och insiktsikonen ![ Enkel ritning av en pil som ska nå ett ](images/tvm_alert_icon.png) mål. .  

Ikonen för intrångsinformation markeras om det finns en säkerhetsrisk i organisationen.
![Exempel på text med intrångsinformation som kan visas när du hovrar över en ikon. Den här säger "möjlig aktiv avisering är kopplad till den här rekommendationen.](images/tvm-breach-insights.png)

Ikonen för hotinsikter markeras om det finns associerade sårbarheter i den sårbarhet som finns i organisationen. Hovra över ikonen för att se om risken är en del av en sårbarhetssats eller kopplad till specifika avancerade beständiga kampanjer eller aktivitetsgrupper. När rapporten är tillgänglig finns det en länk till en rapport om hotanalys där det inte finns några dagars användningsnyheter, avslöjanden eller relaterade säkerhetsrådgivare.  

![Text med hotinsikter som kan visas när du hovrar över en ikon. Den här har flera punkter och länkad text.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>Få sårbarhetsinsikter

Om du väljer en CVE öppnas en utfällbarhetspanel med mer information, till exempel sårbarhetsbeskrivning, information, information om hot och exponerade enheter.

- Kategorin "OS-funktion" visas i relevanta scenarier
- Du kan gå till relaterad säkerhetsrekommendationer för varje CVE med exponerade enheter

 ![Det utfällfälle exemplet Flygblad.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a>Programvara som inte stöds

CV:er för programvara som för närvarande inte stöds av & sårbarhetshantering finns fortfarande på sidan Förskanning. Eftersom programvaran inte stöds är endast begränsade data tillgängliga.

Information om exponerade enheter kommer inte att vara tillgänglig för CV:er med programvara som inte stöds. Filtrera efter programvara som inte stöds genom att välja alternativet "Inte tillgängligt" i avsnittet "Exponerade enheter".

 ![Filtrera exponerade enheter.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>Visa vanliga säkerhetsproblem och exponeringar (CVE) på andra platser

### <a name="top-vulnerable-software-in-the-dashboard"></a>Mest sårbar programvara på instrumentpanelen

1. Gå till [instrumentpanelen för hot och sårbarhetshantering](tvm-dashboard-insights.md) och rulla ned till den **mest sårbara programvaruwidgeten.** Du kommer att se antalet svagheter i varje programvara, tillsammans med information om hot och en detaljerad bild av exponering av enheter över tid.

    ![Övre sårbara programvarukort med fyra kolumner: programvara, svagheter, hot, exponerade enheter.](images/tvm-top-vulnerable-software500.png)

2. Välj den programvara du vill undersöka för att gå till en sida med en detaljgranskning.
3. Välj fliken **Identifierade säkerhetsproblem.**
4. Välj det säkerhetsproblem du vill undersöka för mer information om sårbarhetsinformation

    ![Windows Server 2019 – granska nedåt – översikt.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a>Upptäck säkerhetsproblem på enhetssidan

Visa relaterad information om svagheter på enhetens sida.

1. Gå till menyraden för navigering i Microsoft Defender Säkerhetscenter och välj sedan enhetsikonen. Sidan **Enheter öppnas.**
2. På sidan **Enheter väljer** du namnet på enheten som du vill undersöka.

    ![Enhetslista med vald enhet att undersöka.](images/tvm_machinetoinvestigate.png)

3. Enhetens sida öppnas med information och svarsalternativ för den enhet du vill undersöka.
4. Välj **Identifierade säkerhetsproblem**.

    ![Sida för enhet med information och svarsalternativ.](images/tvm-discovered-vulnerabilities.png)

5. Välj det sårbarhet som du vill undersöka för att öppna en utfällbarhetspanel med CVE-information, till exempel: sårbarhetsbeskrivning, hotinsikter och identifieringslogik.

#### <a name="cve-detection-logic"></a>Logik för identifiering av CVE

I likhet med programvarubevisen visar vi nu den identifieringslogik vi använt på en enhet för att visa att den är sårbar. Det nya avsnittet kallas "Identifieringslogik" (i alla identifierade problem på enhetssidan) och visar identifieringslogiken och källan.

Kategorin "OS-funktion" visas också i relevanta scenarier. En CVE skulle påverka enheter som kör ett sårbart operativsystem endast om en specifik OS-komponent är aktiverad. Anta att Windows Server 2019 har en säkerhetsrisk i DNS-komponenten. Med den här nya funktionen kommer vi bara att ansluta denna CVE till Windows Server 2019-enheter med DNS-funktionen aktiverad i operativsystemet.

![Exempel på identifieringslogik med den programvara som upptäckts på enheten och KB:er.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a>Rapportera felaktigheter

Rapportera en falsk positiv när du ser någon vag, felaktig eller ofullständig information. Du kan också rapportera säkerhetsrekommendationer som redan har åtgärdats.

1. Öppna CVE på sidan Försv.
2. Välj **Rapportens felaktigheter så** öppnas ett utfällt fönster.
3. Välj kategorin felaktigheter i den nedrullningrullningsmenyn och fyll i din e-postadress och information om felaktigheter.
4. Välj **Skicka**. Din feedback skickas omedelbart till experter på hot och sårbarhetshantering.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Programvaruinventering](tvm-software-inventory.md)
- [Instrumentpanelsinsikter](tvm-dashboard-insights.md)
- [Visa och ordna listan Microsoft Defender för slutpunktsenheter](machines-view-overview.md)
