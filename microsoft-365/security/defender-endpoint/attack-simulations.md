---
title: Upplev Microsoft Defender för Endpoint genom simulerade attacker
description: Kör simuleringar av angivna attackscenarion för att se hur Microsoft Defender för Endpoint kan upptäcka, undersöka och hantera överträdelser.
keywords: test, scenario, attack, simulering, simulerad, gör-det-själv, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339544"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Upplev Microsoft Defender för Endpoint genom simulerade attacker 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Läs mer om de senaste förbättringarna i Microsoft Defender för Slutpunkt: [Nyheter i Defender för Slutpunkt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
>- Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen. Läs: [Insights från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

Du kanske vill använda Defender för Slutpunkt innan du inför mer än ett fåtal enheter i tjänsten. Det kan du göra genom att köra kontrollerad attack simulering på några testenheter. När du har kört de simulerade attackerna kan du se hur Defender för Endpoint visar skadlig aktivitet och undersöker hur det möjliggör ett effektivt svar.

## <a name="before-you-begin"></a>Innan du börjar

Om du vill köra någon av de angivna simuleringarna behöver du minst [en inbyggd enhet](onboard-configure.md). 

Läs genomgångsdokumentet som tillhandahålls för varje attackscenario. Varje dokument innehåller OS- och programkrav samt detaljerade anvisningar som är specifika för ett attackscenario.

## <a name="run-a-simulation"></a>Köra en simulering

1. I **självstudiekurserna**  >  **&**  >  **slutpunktsutvärderingar och &** kan du välja vilka tillgängliga attackscenarier du vill simulera:

   - **Scenario 1: Dokument tappar backdoor** – simulerar leverans av ett socialt teknikerat lure-dokument. Dokumentet öppnar en särskilt utformad backdoor som ger attackerare kontroll.

   - **Scenario 2: PowerShell-skript** i fillös attack – simulerar en fillös attack som förlitar sig på PowerShell, visar minskning av attackytan och enhetsinlärning av skadlig minnesaktivitet.
    
   - **Scenario 3: Automatiserat incidentsvar** – utlöser automatiserad undersökning, som automatiskt söker efter och åtgärdar intrångsartefakter för att anpassa svarskapaciteten för incidenter.

2. Ladda ned och läs motsvarande genomgångar för ditt valda scenario.

3. Ladda ned simuleringsfilen eller kopiera simuleringsskriptet genom att navigera till **Hjälp**  >  **simuleringar & självstudiekurser.** Du kan välja att ladda ned filen eller skriptet på testenheten men det är inte obligatoriskt.

4. Kör simuleringsfilen eller skriptet på testenheten enligt anvisningarna i genomgångsdokumentet.

> [!NOTE]
> Simuleringsfiler eller skript efterliknar attackaktivitet men är faktiskt inte deras skada eller äventyrar testenheten.
> 
> 
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Relaterade ämnen

- [Onboard-enheter](onboard-configure.md)
- [Registrera Windows 10-enheter](configure-endpoints.md)
