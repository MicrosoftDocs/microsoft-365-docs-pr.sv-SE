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
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d3cec-104">Åtgärda defekta sensorer i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3cec-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3cec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d3cec-105">**Applies to:**</span></span>
- [<span data-ttu-id="d3cec-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3cec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d3cec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3cec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="d3cec-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d3cec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3cec-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d3cec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="d3cec-110">Enheter som kategoriseras som felkonfigurerade eller inaktiva kan flaggas på grund av olika orsaker.</span><span class="sxs-lookup"><span data-stu-id="d3cec-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="d3cec-111">Det här avsnittet innehåller några förklaringar till vad som kan ha orsakat att en enhet kategoriserats som inaktiv eller felaktigt konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="d3cec-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="d3cec-112">Inaktiva enheter</span><span class="sxs-lookup"><span data-stu-id="d3cec-112">Inactive devices</span></span>

<span data-ttu-id="d3cec-113">En inaktiv enhet är inte nödvändigtvis flaggad på grund av ett problem.</span><span class="sxs-lookup"><span data-stu-id="d3cec-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="d3cec-114">Följande åtgärder som utförs på en enhet kan medföra att en enhet kategoriseras som inaktiv:</span><span class="sxs-lookup"><span data-stu-id="d3cec-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="d3cec-115">Enheten används inte</span><span class="sxs-lookup"><span data-stu-id="d3cec-115">Device is not in use</span></span>

<span data-ttu-id="d3cec-116">Om enheten av någon anledning inte används under mer än sju dagar förblir den statusen Inaktiv i portalen.</span><span class="sxs-lookup"><span data-stu-id="d3cec-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="d3cec-117">Enheten har installerats om eller bytt namn</span><span class="sxs-lookup"><span data-stu-id="d3cec-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="d3cec-118">En enhet som har installerats om eller bytt namn genererar en ny enhet i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="d3cec-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d3cec-119">Den föregående enhetens entitet förblir med statusen Inaktiv i portalen.</span><span class="sxs-lookup"><span data-stu-id="d3cec-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="d3cec-120">Om du har installerat om en enhet och distribuerat Defender för slutpunkt-paketet söker du efter namnet på den nya enheten för att kontrollera att enheten rapporterar normalt.</span><span class="sxs-lookup"><span data-stu-id="d3cec-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="d3cec-121">Enheten var offboarded</span><span class="sxs-lookup"><span data-stu-id="d3cec-121">Device was offboarded</span></span>
<span data-ttu-id="d3cec-122">Om enheten var offboarded visas den fortfarande i listan över enheter.</span><span class="sxs-lookup"><span data-stu-id="d3cec-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="d3cec-123">Efter sju dagar bör enhetens hälsotillstånd ändras till inaktivt.</span><span class="sxs-lookup"><span data-stu-id="d3cec-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="d3cec-124">Enheten skickar inte signaler</span><span class="sxs-lookup"><span data-stu-id="d3cec-124">Device is not sending signals</span></span>
<span data-ttu-id="d3cec-125">Om enheten inte skickar några signaler under mer än sju dagar till någon av Microsoft Defender för Slutpunktskanaler av någon anledning, inklusive villkor som faller under felaktigt konfigurerad klassificering av enheter, kan en enhet anses vara inaktiv.</span><span class="sxs-lookup"><span data-stu-id="d3cec-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="d3cec-126">Förväntar du dig att en enhet ska ha statusen Aktiv?</span><span class="sxs-lookup"><span data-stu-id="d3cec-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="d3cec-127">[Öppna ett support ärende](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span><span class="sxs-lookup"><span data-stu-id="d3cec-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="d3cec-128">Felkonfigurerade enheter</span><span class="sxs-lookup"><span data-stu-id="d3cec-128">Misconfigured devices</span></span>
<span data-ttu-id="d3cec-129">Felkonfigurerade enheter kan klassificeras ytterligare till:</span><span class="sxs-lookup"><span data-stu-id="d3cec-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="d3cec-130">Nedsatt kommunikation</span><span class="sxs-lookup"><span data-stu-id="d3cec-130">Impaired communications</span></span>
- <span data-ttu-id="d3cec-131">Inga sensordata</span><span class="sxs-lookup"><span data-stu-id="d3cec-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="d3cec-132">Nedsatt kommunikation</span><span class="sxs-lookup"><span data-stu-id="d3cec-132">Impaired communications</span></span>
<span data-ttu-id="d3cec-133">Den här statusen anger att det finns begränsad kommunikation mellan enheten och tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="d3cec-134">Följande föreslagna åtgärder kan hjälpa dig att åtgärda problem som rör en felkonfigurerad enhet med nedsatt kommunikation:</span><span class="sxs-lookup"><span data-stu-id="d3cec-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="d3cec-135">Kontrollera att enheten har internetanslutning</span><span class="sxs-lookup"><span data-stu-id="d3cec-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="d3cec-136">Microsoft Defender för slutpunkts sensoren kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="d3cec-137">Verifiera klientanslutningen till URL-adresser för Microsoft Defender för slutpunktstjänsten</span><span class="sxs-lookup"><span data-stu-id="d3cec-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="d3cec-138">Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL-adresser för Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="d3cec-139">Om du har vidta korrigerande åtgärder och enhetens status fortfarande är felaktigt konfigurerad, öppna [ett support ärende](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="d3cec-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="d3cec-140">Inga sensordata</span><span class="sxs-lookup"><span data-stu-id="d3cec-140">No sensor data</span></span>
<span data-ttu-id="d3cec-141">En felkonfigurerad enhet med statusen Inga sensordata har kommunikation med tjänsten men kan bara rapportera ofullständiga sensordata.</span><span class="sxs-lookup"><span data-stu-id="d3cec-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="d3cec-142">Följ dessa åtgärder för att korrigera kända problem relaterade till en felkonfigurerad enhet med statusen Inga sensordata:</span><span class="sxs-lookup"><span data-stu-id="d3cec-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="d3cec-143">Kontrollera att enheten har internetanslutning</span><span class="sxs-lookup"><span data-stu-id="d3cec-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="d3cec-144">Microsoft Defender för slutpunkts sensoren kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="d3cec-145">Verifiera klientanslutningen till URL-adresser för Microsoft Defender för slutpunktstjänsten</span><span class="sxs-lookup"><span data-stu-id="d3cec-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="d3cec-146">Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL-adresser för Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="d3cec-147">Kontrollera att diagnostikdatatjänsten är aktiverad</span><span class="sxs-lookup"><span data-stu-id="d3cec-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="d3cec-148">Om enheterna inte rapporterar korrekt kan du behöva kontrollera att Windows 10-diagnostikdatatjänsten är inställd på att startas automatiskt och körs på slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="d3cec-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="d3cec-149">Se till att Microsoft Defender Antivirus inte är inaktiverat enligt policy</span><span class="sxs-lookup"><span data-stu-id="d3cec-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="d3cec-150">Om dina enheter kör en tredjepartsklient för program mot skadlig programvara måste drivrutinen för Microsoft Defender Antivirus Early Launch Antimalware (ELAM) aktiveras.</span><span class="sxs-lookup"><span data-stu-id="d3cec-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="d3cec-151">Om du har vidta korrigerande åtgärder och enhetens status fortfarande är felaktigt konfigurerad, öppna [ett support ärende](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="d3cec-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3cec-152">Se även</span><span class="sxs-lookup"><span data-stu-id="d3cec-152">See also</span></span>
- [<span data-ttu-id="d3cec-153">Kontrollera sensorhälsan i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3cec-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
