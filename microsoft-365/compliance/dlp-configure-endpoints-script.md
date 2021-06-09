---
title: Registrera Windows 10-enheter med ett lokalt skript
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
description: Använd ett lokalt skript för att distribuera konfigurationspaketet på enheter så att de introduceras till tjänsten.
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843452"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="1cecc-103">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="1cecc-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="1cecc-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1cecc-104">**Applies to:**</span></span>

- [<span data-ttu-id="1cecc-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="1cecc-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="1cecc-106">Du kan även registrera enskilda enheter manuellt Microsoft 365 skydd mot dataförlust i Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1cecc-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="1cecc-107">Du kanske vill göra det här först när du testar tjänsten innan du åtar dig att registrera alla enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="1cecc-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cecc-108">Det här skriptet har optimerats för användning på upp till 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="1cecc-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="1cecc-109">Använd andra distributionsalternativ om du [vill distribuera i skala.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1cecc-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="1cecc-110">Du kan till exempel distribuera ett onboarding-skript till fler än 10 enheter i produktionen med skriptet som är tillgängligt i [Onboard Windows 10-enheter med grupprincip.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="1cecc-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="1cecc-111">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="1cecc-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="1cecc-112">Öppna filen för GP.zip konfigurationspaket *(DeviceComplianceOnboardingPackage.zip)* som du laddade ned från guiden för registrering av tjänster.</span><span class="sxs-lookup"><span data-stu-id="1cecc-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="1cecc-113">Du kan också hämta paketet från [Microsofts efterlevnadscenter](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1cecc-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="1cecc-114">I navigeringsfönstret väljer du **Inställningar**  >  **Enhets onboarding**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="1cecc-115">Välj **Lokalt skript** i fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="1cecc-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="1cecc-116">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="1cecc-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="1cecc-117">Extrahera innehållet i konfigurationspaketet till en plats på den enhet som du vill registrera (till exempel skrivbordet).</span><span class="sxs-lookup"><span data-stu-id="1cecc-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="1cecc-118">Du bör ha en fil med namnet *DeviceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1cecc-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="1cecc-119">Öppna en upphöjd kommandoradsfråga på enheten och kör skriptet:</span><span class="sxs-lookup"><span data-stu-id="1cecc-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="1cecc-120">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="1cecc-121">Högerklicka på **Kommandotolken** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Start-menyn i ett fönster som pekar på Kör som administratör](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="1cecc-123">Skriv skriptfilens plats.</span><span class="sxs-lookup"><span data-stu-id="1cecc-123">Type the location of the script file.</span></span> <span data-ttu-id="1cecc-124">Om du kopierade filen till skrivbordet skriver du: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="1cecc-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="1cecc-125">Tryck på **Retur** eller klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="1cecc-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="1cecc-126">Mer information om hur du manuellt kan verifiera att enheten är kompatibel och korrekt rapporterar sensordata finns i [Felsöka problem Microsoft Defender Avancerat skydd onboarding.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="1cecc-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="1cecc-127">Offboard-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="1cecc-127">Offboard devices using a local script</span></span>
<span data-ttu-id="1cecc-128">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="1cecc-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="1cecc-129">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="1cecc-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="1cecc-130">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="1cecc-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="1cecc-131">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="1cecc-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="1cecc-132">Skaffa offboardingpaketet från [Microsofts efterlevnadscenter](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1cecc-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="1cecc-133">I navigeringsfönstret väljer du **Inställningar**  >  **Offboarding för enheter.**</span><span class="sxs-lookup"><span data-stu-id="1cecc-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="1cecc-134">Välj **Lokalt skript** i fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="1cecc-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="1cecc-135">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="1cecc-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="1cecc-136">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheterna.</span><span class="sxs-lookup"><span data-stu-id="1cecc-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="1cecc-137">Du bör ha en fil med *namnet DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1cecc-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="1cecc-138">Öppna en upphöjd kommandoradsfråga på enheten och kör skriptet:</span><span class="sxs-lookup"><span data-stu-id="1cecc-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="1cecc-139">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="1cecc-140">Högerklicka på **Kommandotolken** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Start-menyn i ett fönster som pekar på Kör som administratör](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="1cecc-142">Skriv skriptfilens plats.</span><span class="sxs-lookup"><span data-stu-id="1cecc-142">Type the location of the script file.</span></span> <span data-ttu-id="1cecc-143">Om du kopierade filen till skrivbordet skriver du: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="1cecc-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="1cecc-144">Tryck på **Retur** eller klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="1cecc-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cecc-145">Offboarding gör att enheten slutar skicka sensordata till portalen.</span><span class="sxs-lookup"><span data-stu-id="1cecc-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="1cecc-146">Övervaka enhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="1cecc-146">Monitor device configuration</span></span>
<span data-ttu-id="1cecc-147">Du kan följa de olika verifieringsstegen i [Felsök onboarding-problem]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) för att verifiera att skriptet har slutförts och att agenten körs.</span><span class="sxs-lookup"><span data-stu-id="1cecc-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="1cecc-148">Övervakning kan också utföras direkt i portalen eller med hjälp av de olika distributionsverktygen.</span><span class="sxs-lookup"><span data-stu-id="1cecc-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="1cecc-149">Övervaka enheter med hjälp av portalen</span><span class="sxs-lookup"><span data-stu-id="1cecc-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="1cecc-150">Gå till [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1cecc-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="1cecc-151">Välj **Inställningar**  >  **enheter för registrering av**  >  **enheter**.</span><span class="sxs-lookup"><span data-stu-id="1cecc-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="1cecc-152">Kontrollera att enheter visas.</span><span class="sxs-lookup"><span data-stu-id="1cecc-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1cecc-153">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1cecc-153">Related topics</span></span>
- [<span data-ttu-id="1cecc-154">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="1cecc-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="1cecc-155">Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1cecc-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="1cecc-156">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="1cecc-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="1cecc-157">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="1cecc-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="1cecc-158">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="1cecc-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="1cecc-159">Felsöka Microsoft Defender Avancerat skydd onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="1cecc-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)