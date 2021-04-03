---
title: Aktivera nätverksskydd
description: Aktivera nätverksskydd med Grupprincip, PowerShell eller Hantering av mobila enheter och Konfigurationshanteraren.
keywords: ANetwork protection, exploits, malicious website, ip, domain, domains, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a513013c4b5f41cf95b876648882cb56ba818b32
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571002"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="ce0df-104">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ce0df-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ce0df-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ce0df-105">**Applies to:**</span></span>
- [<span data-ttu-id="ce0df-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ce0df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ce0df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce0df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ce0df-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ce0df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ce0df-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ce0df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ce0df-110">[Nätverksskydd](network-protection.md) förhindrar anställda från att använda ett program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet.</span><span class="sxs-lookup"><span data-stu-id="ce0df-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="ce0df-111">Du kan [granska nätverksskyddet](evaluate-network-protection.md) i en testmiljö för att se vilka appar som blockeras innan du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="ce0df-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="ce0df-112">Läs mer om konfigurationsalternativ för nätverksfiltrering</span><span class="sxs-lookup"><span data-stu-id="ce0df-112">Learn more about network filtering configuration options</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="ce0df-113">Kontrollera om nätverksskyddet är aktiverat</span><span class="sxs-lookup"><span data-stu-id="ce0df-113">Check if network protection is enabled</span></span>

<span data-ttu-id="ce0df-114">Kontrollera om nätverksskyddet har aktiverats på en lokal enhet med registereditorn.</span><span class="sxs-lookup"><span data-stu-id="ce0df-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="ce0df-115">Välj knappen **Start** i aktivitetsfältet och skriv **regedit för** att öppna Registereditorn</span><span class="sxs-lookup"><span data-stu-id="ce0df-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>
1. <span data-ttu-id="ce0df-116">Välj **HKEY_LOCAL_MACHINE** i sidomenyn</span><span class="sxs-lookup"><span data-stu-id="ce0df-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>
1. <span data-ttu-id="ce0df-117">Navigera genom de kapslade menyerna **till**  >  **PROGRAMVARUprinciper**  >  **Microsoft**  >  **Windows Defender** Windows Defender Exploit  >  **Guard**  >  **Network Protection**</span><span class="sxs-lookup"><span data-stu-id="ce0df-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>
1. <span data-ttu-id="ce0df-118">Välj **EnableNetworkProtection** för att se aktuell status för nätverksskydd på enheten</span><span class="sxs-lookup"><span data-stu-id="ce0df-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="ce0df-119">0 eller **Av**</span><span class="sxs-lookup"><span data-stu-id="ce0df-119">0, or **Off**</span></span>
    * <span data-ttu-id="ce0df-120">1 eller **På**</span><span class="sxs-lookup"><span data-stu-id="ce0df-120">1, or **On**</span></span>
    * <span data-ttu-id="ce0df-121">2 eller **granskningsläge**</span><span class="sxs-lookup"><span data-stu-id="ce0df-121">2, or **Audit** mode</span></span>
    
    ![nätverksskydd](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="ce0df-123">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ce0df-123">Enable network protection</span></span>

<span data-ttu-id="ce0df-124">Aktivera nätverksskydd med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="ce0df-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="ce0df-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce0df-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="ce0df-126">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="ce0df-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="ce0df-127">Microsoft Endpoint Manager/Intune</span><span class="sxs-lookup"><span data-stu-id="ce0df-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="ce0df-128">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="ce0df-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="ce0df-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce0df-129">PowerShell</span></span>

1. <span data-ttu-id="ce0df-130">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**</span><span class="sxs-lookup"><span data-stu-id="ce0df-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="ce0df-131">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ce0df-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="ce0df-132">Valfritt: Aktivera funktionen i granskningsläge med följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ce0df-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="ce0df-133">Använd `Disabled` i stället för eller för att stänga av `AuditMode` `Enabled` funktionen.</span><span class="sxs-lookup"><span data-stu-id="ce0df-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="ce0df-134">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="ce0df-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="ce0df-135">Använd [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP) för att aktivera eller inaktivera nätverksskydd eller aktivera granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="ce0df-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="ce0df-136">Microsoft Endpoint Manager (tidigare Intune)</span><span class="sxs-lookup"><span data-stu-id="ce0df-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="ce0df-137">Logga in i administrationscentret för Microsoft Endpoint Manager (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ce0df-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="ce0df-138">Skapa eller redigera en [konfigurationsprofil för slutpunktsskydd](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="ce0df-138">Create or edit an [endpoint protection configuration profile](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="ce0df-139">Under "Konfigurationsinställningar" i profilflödet går du till **Microsoft Defender Sårbarhetsskydd**  >  **nätverksfiltrering**  >    >  **Aktivera eller** Granska **endast**</span><span class="sxs-lookup"><span data-stu-id="ce0df-139">Under "Configuration Settings" in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="ce0df-140">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="ce0df-140">Group Policy</span></span>

<span data-ttu-id="ce0df-141">Använd följande procedur för att aktivera nätverksskydd på domänbaserade datorer eller på en fristående dator.</span><span class="sxs-lookup"><span data-stu-id="ce0df-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="ce0df-142">På en fristående dator går du till **Start** och skriver och väljer **Redigera grupprincip.**</span><span class="sxs-lookup"><span data-stu-id="ce0df-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="ce0df-143">*Eller*</span><span class="sxs-lookup"><span data-stu-id="ce0df-143">*-Or-*</span></span>

    <span data-ttu-id="ce0df-144">På en domän ansluten grupprinciphanteringsdator öppnar du konsolen [Grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklickar på det grupprincipobjekt du vill konfigurera och väljer **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="ce0df-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="ce0df-145">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="ce0df-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="ce0df-146">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard-nätverksskydd**  >  .</span><span class="sxs-lookup"><span data-stu-id="ce0df-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce0df-147">I äldre versioner av Windows kan det hända att grupprincipsökvägen säger "Windows Defender Antivirus" i stället för "Microsoft Defender Antivirus".</span><span class="sxs-lookup"><span data-stu-id="ce0df-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="ce0df-148">Dubbelklicka på inställningen Förhindra **användare och appar från att komma åt skadliga webbplatser** och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="ce0df-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="ce0df-149">I avsnittet alternativ måste du ange något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="ce0df-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="ce0df-150">**Blockera** – användare kan inte komma åt skadliga IP-adresser och domäner</span><span class="sxs-lookup"><span data-stu-id="ce0df-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="ce0df-151">**Inaktivera (standard)** – Nätverksskyddsfunktionen fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="ce0df-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="ce0df-152">Användarna blockeras inte från att komma åt skadliga domäner</span><span class="sxs-lookup"><span data-stu-id="ce0df-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="ce0df-153">**Granskningsläge** – Om en användare besöker en skadlig IP-adress eller domän registreras en händelse i Windows-händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="ce0df-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="ce0df-154">Men användaren blockeras inte från att gå till adressen.</span><span class="sxs-lookup"><span data-stu-id="ce0df-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce0df-155">Om du vill aktivera nätverksskydd fullt ut  måste du ställa **in** grupprincipalternativet på Aktiverad och även välja Blockera i den nedrullningrullningsalternativsmeny som visas.</span><span class="sxs-lookup"><span data-stu-id="ce0df-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="ce0df-156">Kontrollera att nätverksskyddet är aktiverat på en lokal dator med hjälp av Registereditorn:</span><span class="sxs-lookup"><span data-stu-id="ce0df-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="ce0df-157">Välj **Start** och skriv **regedit för** att öppna **Registereditorn.**</span><span class="sxs-lookup"><span data-stu-id="ce0df-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="ce0df-158">Gå till **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span><span class="sxs-lookup"><span data-stu-id="ce0df-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span></span>

3. <span data-ttu-id="ce0df-159">Välj **EnableNetworkProtection** och bekräfta värdet:</span><span class="sxs-lookup"><span data-stu-id="ce0df-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="ce0df-160">0=Av</span><span class="sxs-lookup"><span data-stu-id="ce0df-160">0=Off</span></span>
   * <span data-ttu-id="ce0df-161">1=På</span><span class="sxs-lookup"><span data-stu-id="ce0df-161">1=On</span></span>
   * <span data-ttu-id="ce0df-162">2=Granskning</span><span class="sxs-lookup"><span data-stu-id="ce0df-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="ce0df-163">Se även</span><span class="sxs-lookup"><span data-stu-id="ce0df-163">See also</span></span>

* [<span data-ttu-id="ce0df-164">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ce0df-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="ce0df-165">Utvärdera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ce0df-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="ce0df-166">Felsöka nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ce0df-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
