---
title: Introducera tidigare versioner av Windows på Microsoft Defender för Endpoint
description: Registrera tidigare versioner av Windows enheter som stöds så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensor
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, nedåtnivå
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7ed7390f67747d176145bb051d8b1633a7146a23
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730816"
---
# <a name="onboard-previous-versions-of-windows"></a>Registrera tidigare versioner av Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformar**
- Windows 7 SP1 Enterprise
- Windows 7 SP1-Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

Defender för Endpoint utökar stödet till att inkludera operativsystem på undernivå, med avancerade funktioner för identifiering och undersökning av attacker i versioner som Windows.

Om du vill introducera Windows-slutpunkter i Defender för Endpoint måste du:
- Konfigurera och uppdatera System Center Endpoint Protection klienter.
- Installera och konfigurera Microsoft Monitoring Agent (MMA) för att rapportera sensordata till Defender för Slutpunkt enligt anvisningarna nedan.

> [!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att den är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunktsslutpunkt.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Konfigurera och uppdatera System Center Endpoint Protection klienter
> [!IMPORTANT]
> Det här steget krävs bara om din organisation använder System Center Endpoint Protection (S UPP)..

Defender för Endpoint integreras med System Center Endpoint Protection för att göra det möjligt att identifiera skadlig programvara och stoppa spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara. 

Följande steg krävs för att aktivera den här integreringen: 
- Installera uppdateringen [för plattformsuppdateringen för skydd mot skadlig programvara i januari 2017 Endpoint Protection klienter](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Konfigurera medlemskap i S FLERA-klientens Molnskyddstjänst till **inställningen** Avancerat
- Konfigurera nätverket för att tillåta anslutningar till Microsoft Defender Antivirus molnet. Mer information finns i [Tillåta anslutningar till Microsoft Defender Antivirus molnet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installera och konfigurera MMA (Microsoft Monitoring Agent) för att rapportera sensordata till Microsoft Defender för slutpunkt

### <a name="before-you-begin"></a>Innan du börjar
Granska följande information för att verifiera lägsta systemkrav:
- Installera den [månatliga uppdateringen för februari 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Gäller endast för Windows 7 SP1 Enterprise och Windows 7 SP1 Pro. 

- Installera uppdatering [för kundupplevelse och diagnostisk telemetri](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installera [antingen .NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) eller [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Gäller endast för Windows 7 SP1 Enterprise och Windows 7 SP1 Pro.
    > Installera inte .NET Framework 4.0.x, eftersom ovanstående installation kommer att avse.

- Uppfylla systemkraven för Azure Log Analytics-agenten. Mer information finns i Samla [in data från datorer i din miljö med logganalys.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Ladda ned installationsfilen för agenten: [Windows 64-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828603) [eller Windows 32-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Hämta arbetsyte-ID:
   - I navigeringsfönstret i Defender för slutpunkt väljer **du Inställningar > Enhetshantering > Onboarding**
   - Välj **Windows 7 SP1 och 8.1** som operativsystem
   - Kopiera arbetsyte-ID:t och arbetsytenyckeln

3. Använd nyckeln Arbetsyte-ID och Arbetsyta genom att välja någon av följande installationsmetoder för att installera agenten:
    - [Installera agenten manuellt med hjälp av konfigurationen](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      På sidan **Installationsalternativ för** agent väljer du **Anslut agenten till Azure Log Analytics (OMS)**
    - [Installera agenten med kommandoraden](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Konfigurera agenten med hjälp av ett skript](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Om du [](gov.md)är myndighetskund i USA måste du under "Azure Cloud" välja "Azure US Government" om du använder installationsguiden, eller om du använder en kommandorad eller ett skript – ange parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.

4. Om du använder en proxyserver för att ansluta till Internet kan du gå till avsnittet Konfigurera proxyinställningar.

När den är klar bör du se onboarded endpoints i portalen inom en timme.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Konfigurera inställningar för proxy- och Internetanslutning
 
- Varje Windows måste kunna ansluta till Internet med https. Den här anslutningen kan vara direkt, med hjälp av en proxy eller via [OMS-gatewayen.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)
- Om en proxy eller brandvägg blockerar all trafik som standard och bara tillåter specifika domäner via eller HTTPS-genomsökning (SSL-kontroll) är aktiverat ska du se till att du aktiverar åtkomst till Defender för [slutpunktstjänst-URL:er.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

## <a name="offboard-client-endpoints"></a>Offboard-klientslutpunkter
Till offboard kan du avinstallera MMA-agenten från slutpunkten eller koppla från den från rapporteringen till Defender för slutpunkt-arbetsytan. När agenten har offboarding skickar slutpunkten inte längre sensordata till Defender för Slutpunkt. 

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).
