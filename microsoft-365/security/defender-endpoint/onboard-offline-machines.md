---
title: Onboard-enheter utan internetanslutning till Microsoft Defender för Endpoint
ms.reviewer: ''
description: Onboard-enheter utan internetanslutning så att de kan skicka sensordata till Microsoft Defender ATP-sensorn
keywords: onboard, servers, VM, on-premise, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: b31705a4e6dc8cdd480c8b43c2154a2d6ddacddd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186947"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Onboard-enheter utan internetanslutning till Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Om du vill registrera enheter utan åtkomst till Internet måste du göra följande allmänna steg:

> [!IMPORTANT] 
> Stegen nedan gäller endast för enheter som kör tidigare versioner av Windows, till exempel: Windows Server 2016 och tidigare eller Windows 8.1 och tidigare.

> [!NOTE]
> - En OMS-gatewayserver kan inte användas som proxy för frånkopplade Windows 10- eller Windows Server 2019-enheter när de konfigureras via registret 'TelemetryProxyServer' eller GPO.
> - För Windows 10 eller Windows Server 2019 – även om du använder telemetriproxyServer måste det peka på en vanlig proxyenhet eller enhet.
> - Dessutom måste Windows 10 eller Windows Server 2019 i frånkopplade miljöer kunna uppdatera certifikatförtroendelistor offline via en intern fil eller webbserver.
> - Mer information om hur du uppdaterar CTLs offline finns i [Konfigurera en fil eller webbserver för att ladda ned CTL-filer.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

Mer information om onboarding-metoder finns i följande artiklar:
- [Introducera tidigare versioner av Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Onboard servers to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Konfigurera enhetsproxy och internetanslutningsinställningar](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Lokala enheter

- Konfigurera Azure Log Analytics (hette tidigare OMS Gateway) som proxy eller hubb:
  - [Azure Log Analytics-agent](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Installera och konfigurera MMA-pekaren på Defender för](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) slutpunktsarbetsytans nyckel &-ID

- Offlineenheter i samma nätverk av Azure Log Analytics
  -  Konfigurera MMA så att det pekar på:
     - IP för Azure-logganalys som proxy
     - Nyckel för Defender för slutpunktsarbetsyta & ID

## <a name="azure-virtual-machines"></a>Virtuella Azure-datorer
- Konfigurera och aktivera [arbetsytan för Azure Logganalys](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Konfigurera Azure Log Analytics Gateway (kallades tidigare OMS Gateway) som proxy eller nav:
      - [Azure Log Analytics Gateway](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Installera och konfigurera MMA-pekaren på Defender för](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) slutpunktsarbetsytans nyckel &-ID
    - Offline-Azure VMs i samma nätverk av OMS Gateway
      - Konfigurera IP för Azure-logganalys som proxy
      - Nyckel för arbetsyta i Azure Log Analytics & ID

    - Azure Säkerhetscenter (ASC)
      - [Arbetsytan \> Logganalys för säkerhetsprinciper](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Tillåt identifiering \> av hot Låt Defender för Slutpunkt få åtkomst till mina data](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Mer information finns i [Arbeta med säkerhetsprinciper.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)
