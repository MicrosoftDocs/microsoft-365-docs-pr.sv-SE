---
title: Registrera Windows 10-enheter med konfigurationshanteraren
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Använd Konfigurationshanteraren för att distribuera konfigurationspaketet på enheter så att de introduceras till tjänsten.
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162760"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="64583-103">Registrera Windows 10-enheter med konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="64583-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="64583-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="64583-104">**Applies to:**</span></span>

- [<span data-ttu-id="64583-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="64583-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="64583-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64583-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="64583-107">Onboard-enheter som använder System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64583-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="64583-108">Öppna konfigurationspaketet för Konfigurationshanteraren .zip *(DeviceComplianceOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="64583-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="64583-109">Du kan också hämta paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="64583-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="64583-110">I navigeringsfönstret väljer du **Inställningar**  >  **Onboarding**  >  **Onboarding för enheter.**</span><span class="sxs-lookup"><span data-stu-id="64583-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="64583-111">I fältet **Distributionsmetod** väljer du **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="64583-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="64583-112">Välj **Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="64583-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="64583-113">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet.</span><span class="sxs-lookup"><span data-stu-id="64583-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="64583-114">Du bör ha en fil med namnet *DeviceComplianceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="64583-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="64583-115">Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="64583-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="64583-116">Välj en fördefinierad enhetssamling att distribuera paketet till.</span><span class="sxs-lookup"><span data-stu-id="64583-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="64583-117">Microsoft 365 Dataförlustskydd i slutpunkten stöder inte onboarding under fas [OOBE (Out-Box Experience).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="64583-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="64583-118">Se till att användarna slutför OOBE när de har Windows installationen eller uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="64583-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="64583-119">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="64583-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="64583-120">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="64583-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="64583-121">Observera att det är möjligt att skapa en identifieringsregel i ett Configuration Manager-program för att kontinuerligt kontrollera om en enhet har introducerats.</span><span class="sxs-lookup"><span data-stu-id="64583-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="64583-122">Ett program är en annan typ av objekt än ett paket och ett program.</span><span class="sxs-lookup"><span data-stu-id="64583-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="64583-123">Om en enhet ännu inte är igång (på grund av att OOBE har slutförts eller av någon annan anledning) försöker Konfigurationshanteraren att registrera enheten igen tills regeln identifierar statusändringen.</span><span class="sxs-lookup"><span data-stu-id="64583-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="64583-124">Du kan åstadkomma detta genom att skapa en kontroll för identifieringsregel om registervärdet "OnboardingState" (av typen REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="64583-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="64583-125">Registervärdet finns under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="64583-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="64583-126">Mer information finns i Konfigurera [identifieringsmetoder i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="64583-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="64583-127">Konfigurera exempelsamlingsinställningar</span><span class="sxs-lookup"><span data-stu-id="64583-127">Configure sample collection settings</span></span>

<span data-ttu-id="64583-128">För varje enhet kan du ange ett konfigurationsvärde för att ange om exempel kan samlas in från enheten när en förfrågan görs via Microsoft Defender Säkerhetscenter att skicka en fil för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="64583-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="64583-129">De här konfigurationsinställningarna görs vanligtvis via Konfigurationshanteraren.</span><span class="sxs-lookup"><span data-stu-id="64583-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="64583-130">Du kan ange en regel för efterlevnad för konfigurationsobjektet i Konfigurationshanteraren om du vill ändra inställningen för exempelresursen på en enhet.</span><span class="sxs-lookup"><span data-stu-id="64583-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="64583-131">Den här regeln bör vara *ett konfigurationsobjekt* för efterlevnadsregel som anger värdet på en registernyckel på riktade enheter för att säkerställa att de är klagomål.</span><span class="sxs-lookup"><span data-stu-id="64583-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="64583-132">Konfigurationen anges via följande registernyckelpost:</span><span class="sxs-lookup"><span data-stu-id="64583-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="64583-133">Var:</span><span class="sxs-lookup"><span data-stu-id="64583-133">Where:</span></span><br>
<span data-ttu-id="64583-134">Nyckeltyp är en D-WORD.</span><span class="sxs-lookup"><span data-stu-id="64583-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="64583-135">Möjliga värden är:</span><span class="sxs-lookup"><span data-stu-id="64583-135">Possible values are:</span></span>
- <span data-ttu-id="64583-136">0 – tillåter inte exempeldelning från den här enheten</span><span class="sxs-lookup"><span data-stu-id="64583-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="64583-137">1 – tillåter delning av alla filtyper från den här enheten</span><span class="sxs-lookup"><span data-stu-id="64583-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="64583-138">Standardvärdet är 1 om registernyckeln inte finns.</span><span class="sxs-lookup"><span data-stu-id="64583-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="64583-139">Mer information om hur System Center Configuration Manager efterlevnad finns i Introduktion till efterlevnadsinställningar [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="64583-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="64583-140">Andra rekommenderade konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="64583-140">Other recommended configuration settings</span></span>
<span data-ttu-id="64583-141">Efter att du har introducerat enheter för tjänsten är det viktigt att du utnyttjar de skyddsfunktioner som ingår i tjänsten genom att aktivera dem med följande rekommenderade konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="64583-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="64583-142">Konfiguration av enhetssamling</span><span class="sxs-lookup"><span data-stu-id="64583-142">Device collection configuration</span></span>
<span data-ttu-id="64583-143">Om du använder Endpoint Configuration Manager, version 2002 eller senare, kan du välja att bredda distributionen så att den omfattar servrar eller klienter på nednivå.</span><span class="sxs-lookup"><span data-stu-id="64583-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="64583-144">Nästa generations skyddskonfiguration</span><span class="sxs-lookup"><span data-stu-id="64583-144">Next generation protection configuration</span></span>

<span data-ttu-id="64583-145">Följande konfigurationsinställningar rekommenderas:</span><span class="sxs-lookup"><span data-stu-id="64583-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="64583-146">**Skanna**</span><span class="sxs-lookup"><span data-stu-id="64583-146">**Scan**</span></span>

- <span data-ttu-id="64583-147">Skanna flyttbara lagringsenheter, till exempel USB-enheter: Ja</span><span class="sxs-lookup"><span data-stu-id="64583-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="64583-148">**Realtidsskydd**</span><span class="sxs-lookup"><span data-stu-id="64583-148">**Real-time Protection**</span></span>

- <span data-ttu-id="64583-149">Aktivera beteendeuppföljning: Ja</span><span class="sxs-lookup"><span data-stu-id="64583-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="64583-150">Aktivera skydd mot potentiellt oönskade program vid nedladdning och före installationen: Ja</span><span class="sxs-lookup"><span data-stu-id="64583-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="64583-151">**Molnskyddstjänst**</span><span class="sxs-lookup"><span data-stu-id="64583-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="64583-152">Molnskyddstjänsttyp: Avancerat medlemskap</span><span class="sxs-lookup"><span data-stu-id="64583-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="64583-153">**Minskning av attackytan** Konfigurera alla tillgängliga regler för granskning.</span><span class="sxs-lookup"><span data-stu-id="64583-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="64583-154">Att blockera dessa aktiviteter kan avbryta legitima affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="64583-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="64583-155">Det bästa sättet är att ange allt som ska granskas, identifiera vilka som är säkra att aktivera och sedan aktivera inställningarna på slutpunkter som inte har falsk positiv identifiering.</span><span class="sxs-lookup"><span data-stu-id="64583-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="64583-156">**Nätverksskydd**</span><span class="sxs-lookup"><span data-stu-id="64583-156">**Network protection**</span></span>

<span data-ttu-id="64583-157">Innan du aktiverar nätverksskydd i gransknings- eller blockeringsläge bör du kontrollera att du har installerat uppdateringen för program mot skadlig kod som kan fås från [supportsidan.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="64583-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="64583-158">**Kontrollerad mappåtkomst**</span><span class="sxs-lookup"><span data-stu-id="64583-158">**Controlled folder access**</span></span>

<span data-ttu-id="64583-159">Aktivera funktionen i granskningsläge i minst 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="64583-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="64583-160">Granska identifieringar och skapa en lista över program som får skriva i skyddade kataloger efter den här perioden.</span><span class="sxs-lookup"><span data-stu-id="64583-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="64583-161">Mer information finns i Utvärdera [reglerad mappåtkomst.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="64583-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="64583-162">Offboard-enheter med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="64583-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="64583-163">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="64583-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="64583-164">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="64583-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="64583-165">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketets namn.</span><span class="sxs-lookup"><span data-stu-id="64583-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="64583-166">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="64583-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="64583-167">Offboard-enheter som Microsoft Endpoint Configuration Manager current branch</span><span class="sxs-lookup"><span data-stu-id="64583-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="64583-168">Om du använder Microsoft Endpoint Configuration Manager current branch finns mer information [i Skapa en konfigurationsfil för offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="64583-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="64583-169">Offboard-enheter med System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64583-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="64583-170">Hämta offboarding-paketet från [Microsofts efterlevnadscenter:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="64583-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="64583-171">I navigeringsfönstret väljer du **Inställningar**  >   **Avboarding av** >  **enheten.**</span><span class="sxs-lookup"><span data-stu-id="64583-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="64583-172">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="64583-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="64583-173">I fältet **Distributionsmetod** väljer du **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="64583-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="64583-174">Välj **Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="64583-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="64583-175">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet.</span><span class="sxs-lookup"><span data-stu-id="64583-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="64583-176">Du bör ha en fil med *namnet DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="64583-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="64583-177">Distribuera paketet genom att följa stegen i artikeln Paket och program [i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="64583-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="64583-178">Välj en fördefinierad enhetssamling att distribuera paketet till.</span><span class="sxs-lookup"><span data-stu-id="64583-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64583-179">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="64583-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="64583-180">Övervaka enhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="64583-180">Monitor device configuration</span></span>

<span data-ttu-id="64583-181">Om du använder en Microsoft Endpoint Configuration Manager gren använder du den inbyggda Microsoft Defender för slutpunkt-instrumentpanelen i konfigurationshanterarens konsol.</span><span class="sxs-lookup"><span data-stu-id="64583-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="64583-182">Mer information finns i [Microsoft Defender Avancerat skydd - Bildskärm.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="64583-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="64583-183">Om du använder konfigurationshanteraren System Center 2012 R2 består övervakning av två delar:</span><span class="sxs-lookup"><span data-stu-id="64583-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="64583-184">Bekräfta att konfigurationspaketet har distribuerats korrekt och körs (eller har körts) på enheterna i nätverket.</span><span class="sxs-lookup"><span data-stu-id="64583-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="64583-185">Kontrollera att enheterna är kompatibla med Microsoft 365 Endpoint-tjänsten för dataförlustskydd (det säkerställer att enheten kan slutföra onboarding-processen och kan fortsätta rapportera data till tjänsten).</span><span class="sxs-lookup"><span data-stu-id="64583-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="64583-186">Bekräfta att konfigurationspaketet har distribuerats korrekt</span><span class="sxs-lookup"><span data-stu-id="64583-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="64583-187">Klicka på Övervakning längst ned i **navigeringsfönstret** i konfigurationshanterarens konsol.</span><span class="sxs-lookup"><span data-stu-id="64583-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="64583-188">Välj **Översikt** och **sedan Distributioner.**</span><span class="sxs-lookup"><span data-stu-id="64583-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="64583-189">Välj på distributionen med paketets namn.</span><span class="sxs-lookup"><span data-stu-id="64583-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="64583-190">Granska statusindikatorerna under **Slutstatistik** och **Innehållsstatus.**</span><span class="sxs-lookup"><span data-stu-id="64583-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="64583-191">Om distributionen misslyckades (enheter med **fel-** och krav **som** inte uppfylls eller **statusen Misslyckades)** kan du behöva felsöka enheterna.</span><span class="sxs-lookup"><span data-stu-id="64583-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="64583-192">Mer information finns i Felsöka [problem Microsoft Defender Avancerat skydd-introduktion.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="64583-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Konfigurationshanteraren visar en lyckad distribution utan fel](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="64583-194">Kontrollera att enheterna är kompatibla med Microsoft 365 ändpunktstjänst för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="64583-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="64583-195">Du kan ange en regel för efterlevnad för konfigurationsobjekt i System Center 2012 R2 Configuration Manager för att övervaka distributionen.</span><span class="sxs-lookup"><span data-stu-id="64583-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="64583-196">Denna procedur och registerpost gäller för Endpoint DLP samt Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="64583-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="64583-197">Den här regeln bör vara *ett konfigurationsobjekt som inte åtgärdar* konfigurationsobjekt för efterlevnadsregel som övervakar värdet för en registernyckel på riktade enheter.</span><span class="sxs-lookup"><span data-stu-id="64583-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="64583-198">Övervaka följande registernyckelpost:</span><span class="sxs-lookup"><span data-stu-id="64583-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="64583-199">Mer information finns i Introduktion [till inställningar för efterlevnad i System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="64583-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="64583-200">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="64583-200">Related topics</span></span>
- [<span data-ttu-id="64583-201">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="64583-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="64583-202">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="64583-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="64583-203">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="64583-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="64583-204">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="64583-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="64583-205">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="64583-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="64583-206">Felsöka Microsoft Defender Avancerat skydd onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="64583-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)