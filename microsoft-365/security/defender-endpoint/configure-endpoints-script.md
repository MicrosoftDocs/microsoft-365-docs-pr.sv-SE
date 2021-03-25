---
title: Registrera Windows 10-enheter med ett lokalt skript
description: Använd ett lokalt skript för att distribuera konfigurationspaketet på enheter så att de introduceras till tjänsten.
keywords: konfigurera enheter med ett lokalt skript, enhetshantering, konfigurera Windows ATP-enheter, konfigurera Microsoft Defender för slutpunktsenheter
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
ms.openlocfilehash: 77473df9cc3e0e98efac8eaacd0a51b551bc3258
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075905"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="5f1f0-104">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="5f1f0-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="5f1f0-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f1f0-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5f1f0-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5f1f0-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5f1f0-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="5f1f0-108">Du kan även manuellt registrera enskilda enheter i Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="5f1f0-109">Du kanske vill göra det här först när du testar tjänsten innan du åtar dig att registrera alla enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f1f0-110">Det här skriptet har optimerats för användning på upp till 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="5f1f0-111">Använd andra distributionsalternativ om du [vill distribuera i skala.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="5f1f0-112">Du kan till exempel distribuera ett onboarding-skript till fler än 10 enheter i produktionen med skriptet som är tillgängligt i [Hantera Windows 10-enheter med grupprincip.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="5f1f0-113">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="5f1f0-113">Onboard devices</span></span> 

<span data-ttu-id="5f1f0-114">[![Bild av PDF-filen som visar de olika distributionssökvägarna](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="5f1f0-115">Ta en titta på [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [eller Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distribuera Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="5f1f0-116">Öppna ZIP-filen för GP-konfigurationspaket *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="5f1f0-117">Du kan också hämta paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="5f1f0-118">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="5f1f0-119">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="5f1f0-120">Välj **Lokalt skript** i fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="5f1f0-121">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="5f1f0-122">Extrahera innehållet i konfigurationspaketet till en plats på den enhet som du vill registrera (till exempel skrivbordet).</span><span class="sxs-lookup"><span data-stu-id="5f1f0-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="5f1f0-123">Du bör ha en fil med namnet *WindowsDefenderATPOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-123">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="5f1f0-124">Öppna en upphöjd kommandoradsfråga på enheten och kör skriptet:</span><span class="sxs-lookup"><span data-stu-id="5f1f0-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="5f1f0-125">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="5f1f0-126">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Start-menyn i ett fönster som pekar på Kör som administratör](images/run-as-admin.png)

4.  <span data-ttu-id="5f1f0-128">Skriv skriptfilens plats.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-128">Type the location of the script file.</span></span> <span data-ttu-id="5f1f0-129">Om du kopierade filen till skrivbordet skriver du: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="5f1f0-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="5f1f0-130">Tryck på **Retur** eller klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="5f1f0-131">Mer information om hur du manuellt kan verifiera att enheten är kompatibel och korrekt rapporterar sensordata finns i Felsöka problem med Microsoft Defender för [slutpunkts onboarding.](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="5f1f0-132">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="5f1f0-133">Mer information finns i Köra [ett identifieringstest på en nyligen introducerad Microsoft Defender för slutpunktsslutpunkt.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="5f1f0-134">Konfigurera exempelsamlingsinställningar</span><span class="sxs-lookup"><span data-stu-id="5f1f0-134">Configure sample collection settings</span></span>
<span data-ttu-id="5f1f0-135">För varje enhet kan du ange ett konfigurationsvärde för att ange om exempel kan samlas in från enheten när en begäran görs via Microsoft Defender Säkerhetscenter för att skicka en fil för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="5f1f0-136">Du kan manuellt konfigurera exempeldelningsinställningen på enheten genom att använda *regedit* eller skapa och köra en *REG-fil.*</span><span class="sxs-lookup"><span data-stu-id="5f1f0-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="5f1f0-137">Konfigurationen anges via följande registernyckelpost:</span><span class="sxs-lookup"><span data-stu-id="5f1f0-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="5f1f0-138">Var:</span><span class="sxs-lookup"><span data-stu-id="5f1f0-138">Where:</span></span><br>
<span data-ttu-id="5f1f0-139">Namntypen är en D-WORD.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="5f1f0-140">Möjliga värden är:</span><span class="sxs-lookup"><span data-stu-id="5f1f0-140">Possible values are:</span></span>
- <span data-ttu-id="5f1f0-141">0 – tillåter inte exempeldelning från den här enheten</span><span class="sxs-lookup"><span data-stu-id="5f1f0-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="5f1f0-142">1 – tillåter delning av alla filtyper från den här enheten</span><span class="sxs-lookup"><span data-stu-id="5f1f0-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="5f1f0-143">Standardvärdet är 1 om registernyckeln inte finns.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="5f1f0-144">Offboard-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="5f1f0-144">Offboard devices using a local script</span></span>
<span data-ttu-id="5f1f0-145">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5f1f0-146">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="5f1f0-147">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5f1f0-148">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5f1f0-149">Hämta offboarding-paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="5f1f0-150">I navigeringsfönstret väljer du **Inställningar**  >  **offboarding**.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="5f1f0-151">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="5f1f0-152">Välj **Lokalt skript** i fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="5f1f0-153">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="5f1f0-154">Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av enheterna.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="5f1f0-155">Du bör ha en fil med *namnet WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="5f1f0-156">Öppna en upphöjd kommandoradsfråga på enheten och kör skriptet:</span><span class="sxs-lookup"><span data-stu-id="5f1f0-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="5f1f0-157">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="5f1f0-158">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Start-menyn i ett fönster som pekar på Kör som administratör](images/run-as-admin.png)

4.  <span data-ttu-id="5f1f0-160">Skriv skriptfilens plats.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-160">Type the location of the script file.</span></span> <span data-ttu-id="5f1f0-161">Om du kopierade filen till skrivbordet skriver du: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="5f1f0-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="5f1f0-162">Tryck på **Retur** eller klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f1f0-163">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="5f1f0-164">Övervaka enhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="5f1f0-164">Monitor device configuration</span></span>
<span data-ttu-id="5f1f0-165">Du kan följa de olika verifieringsstegen i [Felsöka onboarding-problem](troubleshoot-onboarding.md) för att verifiera att skriptet har slutförts och att agenten körs.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="5f1f0-166">Övervakning kan också utföras direkt i portalen eller med hjälp av de olika distributionsverktygen.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="5f1f0-167">Övervaka enheter med hjälp av portalen</span><span class="sxs-lookup"><span data-stu-id="5f1f0-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="5f1f0-168">Gå till Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="5f1f0-169">Klicka **på listan Enheter.**</span><span class="sxs-lookup"><span data-stu-id="5f1f0-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="5f1f0-170">Kontrollera att enheter visas.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5f1f0-171">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5f1f0-171">Related topics</span></span>
- [<span data-ttu-id="5f1f0-172">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="5f1f0-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="5f1f0-173">Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5f1f0-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="5f1f0-174">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="5f1f0-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="5f1f0-175">Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="5f1f0-176">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="5f1f0-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="5f1f0-177">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f1f0-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
