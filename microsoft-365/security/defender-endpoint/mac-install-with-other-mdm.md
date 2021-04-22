---
title: Distribution med ett annat MDM-system (Mobile Device Management) för Microsoft Defender för Endpoint på Mac
description: Installera Microsoft Defender för Slutpunkt på Mac på andra hanteringslösningar.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, installation, distribuera, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca779fc4cc8c40adb25a0e95a9450f59954dc605
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933799"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d1b8f-104">Distribution med ett annat MDM-system (Mobile Device Management) för Microsoft Defender för Slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="d1b8f-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d1b8f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d1b8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1b8f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d1b8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1b8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1b8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1b8f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d1b8f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d1b8f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="d1b8f-110">Krav och systemkrav</span><span class="sxs-lookup"><span data-stu-id="d1b8f-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="d1b8f-111">Innan du börjar kan du gå [till huvudsidan för Microsoft Defender](microsoft-defender-endpoint-mac.md) för Slutpunkt på macOS för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="approach"></a><span data-ttu-id="d1b8f-112">Metod</span><span class="sxs-lookup"><span data-stu-id="d1b8f-112">Approach</span></span>

> [!CAUTION]

> <span data-ttu-id="d1b8f-113">För närvarande har Microsoft officiellt endast stöd för Intune och JAMF för distribution och hantering av Microsoft Defender för Endpoint på macOS.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="d1b8f-114">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="d1b8f-115">Om din organisation använder en MDM-lösning (Mobile Device Management) som inte stöds officiellt betyder det inte att du inte kan distribuera eller köra Microsoft Defender för slutpunkt på macOS.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="d1b8f-116">Microsoft Defender för Slutpunkt på macOS är inte beroende av några leverantörsspecifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="d1b8f-117">Den kan användas med alla MDM-lösningar som har stöd för följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="d1b8f-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="d1b8f-118">Distribuera en .pkg för macOS till hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="d1b8f-119">Distribuera macOS-systemkonfigurationsprofiler till hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="d1b8f-120">Kör ett godtyckligt administratörskonfigurerat verktyg/skript på hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="d1b8f-121">De flesta moderna MDM-lösningar innehåller dessa funktioner, men de kanske ser annorlunda ut.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="d1b8f-122">Du kan distribuera Defender utan det sista kravet från ovanstående lista, men:</span><span class="sxs-lookup"><span data-stu-id="d1b8f-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="d1b8f-123">Du kan inte samla in status på ett centraliserat sätt</span><span class="sxs-lookup"><span data-stu-id="d1b8f-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="d1b8f-124">Om du bestämmer dig för att avinstallera Defender måste du logga in på klientenheten lokalt som administratör</span><span class="sxs-lookup"><span data-stu-id="d1b8f-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="d1b8f-125">Distribution</span><span class="sxs-lookup"><span data-stu-id="d1b8f-125">Deployment</span></span>

<span data-ttu-id="d1b8f-126">De flesta MDM-lösningar använder samma modell för hantering av macOS-enheter med liknande terminologi.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="d1b8f-127">Använd [JAMF-baserad distribution](mac-install-with-jamf.md) som mall.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="d1b8f-128">Paket</span><span class="sxs-lookup"><span data-stu-id="d1b8f-128">Package</span></span>

<span data-ttu-id="d1b8f-129">Konfigurera distributionen av [ett programpaket som](mac-install-with-jamf.md)krävs med installationspaketet (wdav.pkg) som hämtats [från Microsoft Defender Säkerhetscenter.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="d1b8f-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="d1b8f-130">Följ instruktionerna som är kopplade till din MDM-lösning för att distribuera paketet till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="d1b8f-131">Licensinställningar</span><span class="sxs-lookup"><span data-stu-id="d1b8f-131">License settings</span></span>

<span data-ttu-id="d1b8f-132">Konfigurera en [systemkonfigurationsprofil](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="d1b8f-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> 

<span data-ttu-id="d1b8f-133">Din MDM-lösning kan kalla den något liknande "Profil för anpassade inställningar", eftersom Microsoft Defender för Slutpunkt på macOS inte är en del av macOS.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="d1b8f-134">Använd egenskapslistan, jamf/WindowsDefenderATPOnboarding.plist, som kan extraheras från ett onboarding-paket som laddas ned från [Microsoft Defender Säkerhetscenter.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="d1b8f-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="d1b8f-135">Systemet kan ha stöd för en lista med godtyckliga egenskaper i XML-format.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="d1b8f-136">Du kan ladda upp filen jamf/WindowsDefenderATPOnboarding.plist som den är i så fall.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="d1b8f-137">Du kan också kräva att du konverterar egenskapslistan till ett annat format först.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="d1b8f-138">Vanligtvis har din anpassade profil ett ID, ett namn eller ett domänattribut.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="d1b8f-139">Du måste använda exakt "com.microsoft.wdav.atp" för det här värdet.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="d1b8f-140">MDM använder den för att distribuera inställningsfilen till **/Bibliotek/Hanterade inställningar/com.microsoft.wdav.atp.plist** på en klientenhet, och Defender använder den här filen för inläsning av onboarding-informationen.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="d1b8f-141">Kernel-tilläggspolicy</span><span class="sxs-lookup"><span data-stu-id="d1b8f-141">Kernel extension policy</span></span>

<span data-ttu-id="d1b8f-142">Konfigurera en KEXT- eller kernel-förlängningsprincip.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="d1b8f-143">Använd teamidentifierare **UBF8T346G9** för att tillåta kernel-tillägg som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1b8f-144">Om miljön består av Apple Silicon-enheter (M1) bör dessa datorer inte ta emot konfigurationsprofiler med KEXT-principer.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="d1b8f-145">Apple stöder inte KEXT på dessa datorer, distributionen av sådan profil skulle misslyckas på M1-datorer.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="d1b8f-146">Princip för systemtillägg</span><span class="sxs-lookup"><span data-stu-id="d1b8f-146">System extension policy</span></span>

<span data-ttu-id="d1b8f-147">Konfigurera en princip för systemtillägg.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-147">Set up a system extension policy.</span></span> <span data-ttu-id="d1b8f-148">Använd **teamidentifierare UBF8T346G9** och godkänn följande paketidentifierare:</span><span class="sxs-lookup"><span data-stu-id="d1b8f-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="d1b8f-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="d1b8f-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="d1b8f-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="d1b8f-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="d1b8f-151">Fullständig princip för diskåtkomst</span><span class="sxs-lookup"><span data-stu-id="d1b8f-151">Full disk access policy</span></span>

<span data-ttu-id="d1b8f-152">Bevilja fullständig diskåtkomst till följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="d1b8f-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="d1b8f-153">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d1b8f-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="d1b8f-154">Identifierare: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="d1b8f-155">Identifierartyp: Paket-ID</span><span class="sxs-lookup"><span data-stu-id="d1b8f-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="d1b8f-156">Kodkrav: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="d1b8f-157">Microsoft Defender för Slutpunktssäkerhetstillägg</span><span class="sxs-lookup"><span data-stu-id="d1b8f-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="d1b8f-158">Identifierare: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="d1b8f-159">Identifierartyp: Paket-ID</span><span class="sxs-lookup"><span data-stu-id="d1b8f-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="d1b8f-160">Kodkrav: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="d1b8f-161">Princip för nätverkstillägg</span><span class="sxs-lookup"><span data-stu-id="d1b8f-161">Network extension policy</span></span>

<span data-ttu-id="d1b8f-162">Som en del av funktionerna Identifiering och svar av slutpunkt inspekterar Microsoft Defender för slutpunkt på macOS sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="d1b8f-163">Med följande princip kan nätverkstillägget utföra de här funktionerna.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="d1b8f-164">Filtertyp: Plugin-program</span><span class="sxs-lookup"><span data-stu-id="d1b8f-164">Filter type: Plugin</span></span>
- <span data-ttu-id="d1b8f-165">Identifierare för plugin-paket: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="d1b8f-166">Identifierare för filterleverantörspaket: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="d1b8f-167">Filterdataleverantör angett krav: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="d1b8f-168">Filteruttag: `true`</span><span class="sxs-lookup"><span data-stu-id="d1b8f-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="d1b8f-169">Kontrollera installationsstatus</span><span class="sxs-lookup"><span data-stu-id="d1b8f-169">Check installation status</span></span>

<span data-ttu-id="d1b8f-170">Kör [Microsoft Defender för Slutpunkt på](mac-install-with-jamf.md) en klientenhet för att kontrollera onboarding-statusen.</span><span class="sxs-lookup"><span data-stu-id="d1b8f-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
