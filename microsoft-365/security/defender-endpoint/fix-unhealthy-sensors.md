---
title: Åtgärda defekta sensorer i Microsoft Defender för Endpoint
description: Åtgärda enhetssensorer som rapporterar att de är felkonfigurerade eller inaktiva så att tjänsten tar emot data från enheten.
keywords: felkonfigurerad, inaktiv, åtgärda sensor, sensorhälsa, inga sensordata, sensordata, nedsatt kommunikation, kommunikation
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935371"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Åtgärda defekta sensorer i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

Enheter som kategoriseras som felkonfigurerade eller inaktiva kan flaggas på grund av olika orsaker. Det här avsnittet innehåller några förklaringar till vad som kan ha orsakat att en enhet kategoriserats som inaktiv eller felaktigt konfigurerad.

## <a name="inactive-devices"></a>Inaktiva enheter

En inaktiv enhet är inte nödvändigtvis flaggad på grund av ett problem. Följande åtgärder som utförs på en enhet kan medföra att en enhet kategoriseras som inaktiv:

### <a name="device-is-not-in-use"></a>Enheten används inte

Om enheten av någon anledning inte används under mer än sju dagar förblir den statusen Inaktiv i portalen.

### <a name="device-was-reinstalled-or-renamed"></a>Enheten har installerats om eller bytt namn
En enhet som har installerats om eller bytt namn genererar en ny enhet i Microsoft Defender Säkerhetscenter. Den föregående enhetens entitet förblir med statusen Inaktiv i portalen. Om du har installerat om en enhet och distribuerat Defender för slutpunkt-paketet söker du efter namnet på den nya enheten för att kontrollera att enheten rapporterar normalt.

### <a name="device-was-offboarded"></a>Enheten var offboarded
Om enheten var offboarded visas den fortfarande i listan över enheter. Efter sju dagar bör enhetens hälsotillstånd ändras till inaktivt.

### <a name="device-is-not-sending-signals"></a>Enheten skickar inte signaler
Om enheten inte skickar några signaler under mer än sju dagar till någon av Microsoft Defender för Slutpunktskanaler av någon anledning, inklusive villkor som faller under felaktigt konfigurerad klassificering av enheter, kan en enhet anses vara inaktiv. 

Förväntar du dig att en enhet ska ha statusen Aktiv? [Öppna ett support ärende](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Felkonfigurerade enheter
Felkonfigurerade enheter kan klassificeras ytterligare till:
- Nedsatt kommunikation
- Inga sensordata

### <a name="impaired-communications"></a>Nedsatt kommunikation
Den här statusen anger att det finns begränsad kommunikation mellan enheten och tjänsten.

Följande föreslagna åtgärder kan hjälpa dig att åtgärda problem som rör en felkonfigurerad enhet med nedsatt kommunikation:

- [Kontrollera att enheten har internetanslutning](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender för slutpunkts sensoren kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Microsoft Defender för slutpunktstjänsten.

- [Verifiera klientanslutningen till URL-adresser för Microsoft Defender för slutpunktstjänsten](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL-adresser för Microsoft Defender för slutpunktstjänsten.

Om du har vidta korrigerande åtgärder och enhetens status fortfarande är felaktigt konfigurerad, öppna [ett support ärende](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

### <a name="no-sensor-data"></a>Inga sensordata
En felkonfigurerad enhet med statusen Inga sensordata har kommunikation med tjänsten men kan bara rapportera ofullständiga sensordata.
Följ dessa åtgärder för att korrigera kända problem relaterade till en felkonfigurerad enhet med statusen Inga sensordata:

- [Kontrollera att enheten har internetanslutning](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender för slutpunkts sensoren kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Microsoft Defender för slutpunktstjänsten.

- [Verifiera klientanslutningen till URL-adresser för Microsoft Defender för slutpunktstjänsten](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL-adresser för Microsoft Defender för slutpunktstjänsten.

- [Kontrollera att diagnostikdatatjänsten är aktiverad](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Om enheterna inte rapporterar korrekt kan du behöva kontrollera att Windows 10-diagnostikdatatjänsten är inställd på att startas automatiskt och körs på slutpunkten.

- [Se till att Microsoft Defender Antivirus inte är inaktiverat enligt policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Om dina enheter kör en tredjepartsklient för program mot skadlig programvara måste drivrutinen för Microsoft Defender Antivirus Early Launch Antimalware (ELAM) aktiveras.

Om du har vidta korrigerande åtgärder och enhetens status fortfarande är felaktigt konfigurerad, öppna [ett support ärende](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

## <a name="see-also"></a>Se även
- [Kontrollera sensorhälsan i Microsoft Defender för Endpoint](check-sensor-status.md)
