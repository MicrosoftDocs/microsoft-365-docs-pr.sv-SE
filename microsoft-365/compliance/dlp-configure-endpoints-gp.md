---
title: Registrera Windows 10-enheter via grupprincip
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Använd grupprincip för att distribuera konfigurationspaketet på Windows 10-enheter så att de förs in i tjänsten.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162761"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="1a1f8-103">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="1a1f8-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="1a1f8-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-104">**Applies to:**</span></span>

- [<span data-ttu-id="1a1f8-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="1a1f8-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="1a1f8-106">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="1a1f8-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="1a1f8-107">Om du vill använda grupprincipuppdateringar (GP) för att distribuera paketet måste du använda Windows Server 2008 R2 eller senare.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="1a1f8-108">För Windows Server 2019 kan du behöva ersätta NT AUTHORITY\Well-Known-System-Account med NT AUTHORITY\SYSTEM för den XML-fil som grupprincipinställning skapar.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="1a1f8-109">Registrera enheter med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="1a1f8-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="1a1f8-110">Öppna filen för GP.zip konfigurationspaket *(DeviceComplianceOnboardingPackage.zip)* som du laddade ned från guiden för registrering av tjänster.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="1a1f8-111">Du kan också hämta paketet från [Microsofts efterlevnadscenter](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="1a1f8-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="1a1f8-112">Välj Registrering av enhet **Inställningar**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="1a1f8-113">Välj **Grupprincip i** fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="1a1f8-114">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="1a1f8-115">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1a1f8-116">Du bör ha en mapp med namnet *OptionalParamsPolicy* och filen *DeviceComplianceLocalOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="1a1f8-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="1a1f8-117">Öppna GPMC [(Group Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="1a1f8-118">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** **och** sedan Inställningar och **inställningar för Kontrollpanelen.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="1a1f8-119">Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på **Direktaktivitet (minst Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="1a1f8-120">I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp,** skriver SYSTEM och klickar sedan **på Kontrollera namn** och sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="1a1f8-121">NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="1a1f8-122">Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="1a1f8-123">Gå till fliken **Åtgärder** och klicka på **Ny...** Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1a1f8-124">Ange filnamnet och platsen för den delade *filen WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="1a1f8-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="1a1f8-125">Klicka **på OK** och stäng alla öppna GPMC-fönster.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="1a1f8-126">Offboard-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="1a1f8-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="1a1f8-127">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="1a1f8-128">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="1a1f8-129">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="1a1f8-130">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="1a1f8-131">Hämta offboarding-paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="1a1f8-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="1a1f8-132">I navigeringsfönstret väljer du **Inställningar**  >  **//Device onboarding**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="1a1f8-133">Välj **Grupprincip i** fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="1a1f8-134">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="1a1f8-135">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1a1f8-136">Du bör ha en fil med *namnet DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="1a1f8-137">Öppna GPMC [(Group Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="1a1f8-138">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration,** **inställningar** och sedan Inställningar på **Kontrollpanelen.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="1a1f8-139">Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på **Direktaktivitet.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="1a1f8-140">I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Välj det lokala systemanvändarkontot (INBYGGD\SYSTEM) under **Säkerhetsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="1a1f8-141">Markera **Kör om användaren är inloggad eller inte** och markera **kryssrutan** Kör med högst behörighet.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="1a1f8-142">Gå till fliken **Åtgärder** och klicka på **Nytt...**. Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1a1f8-143">Ange filnamn och plats för den delade filen *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="1a1f8-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="1a1f8-144">Klicka **på OK** och stäng alla öppna GPMC-fönster.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a1f8-145">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="1a1f8-146">Övervaka enhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="1a1f8-146">Monitor device configuration</span></span>
<span data-ttu-id="1a1f8-147">Med Grupprincip finns det inte något alternativ för att övervaka distribution av principer på enheter.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="1a1f8-148">Övervakning kan utföras direkt i portalen eller med hjälp av de olika distributionsverktygen.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="1a1f8-149">Övervaka enheter med hjälp av portalen</span><span class="sxs-lookup"><span data-stu-id="1a1f8-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="1a1f8-150">Gå till [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1a1f8-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="1a1f8-151">Klicka **på Listan** Enheter.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="1a1f8-152">Kontrollera att enheter visas.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="1a1f8-153">Det kan ta flera dagar innan enheter börjar visas i **listan Enheter.**</span><span class="sxs-lookup"><span data-stu-id="1a1f8-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="1a1f8-154">Det inkluderar den tid det tar för principerna att distribueras till enheten, den tid det tar innan användaren loggar in och den tid det tar för slutpunkten att starta rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="1a1f8-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1a1f8-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1a1f8-155">Related topics</span></span>
- [<span data-ttu-id="1a1f8-156">Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1a1f8-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="1a1f8-157">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="1a1f8-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="1a1f8-158">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="1a1f8-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="1a1f8-159">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="1a1f8-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="1a1f8-160">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Slutpunkt-enheter</span><span class="sxs-lookup"><span data-stu-id="1a1f8-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="1a1f8-161">Felsöka Microsoft Defender Avancerat skydd onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="1a1f8-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)