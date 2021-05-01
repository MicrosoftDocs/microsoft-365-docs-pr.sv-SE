---
title: Aktivera moln levererat skydd i Microsoft Defender Antivirus
description: Aktivera moln levererat skydd för att dra nytta av funktioner för snabbt och avancerat skydd.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, moln, block vid första synen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 04/30/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 5fcbd30eca3a6d0965fe65e13d2623ff54d1ff5f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114254"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-104">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dfb0b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-105">**Applies to:**</span></span>

- [<span data-ttu-id="dfb0b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="dfb0b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="dfb0b-107">Den Microsoft Defender Antivirus molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till nätverket och slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="dfb0b-108">Även om den kallas för en molntjänst är den inte bara skydd för filer som lagras i molnet. I stället används distribuerade resurser och maskininlärning för att ge skydd till dina slutpunkter i en takt som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="dfb0b-109">Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, realtids- och intelligent skydd.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="dfb0b-110">[Lär känna de avancerade teknikerna som ligger till grund för nästa](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)generations skydd för Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="dfb0b-111">![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="dfb0b-112">Du kan aktivera Microsoft Defender Antivirus eller inaktivera moln levererat-skydd på flera olika sätt:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="dfb0b-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dfb0b-113">Microsoft Intune</span></span>
- <span data-ttu-id="dfb0b-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dfb0b-114">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="dfb0b-115">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="dfb0b-115">Group Policy</span></span>
- <span data-ttu-id="dfb0b-116">PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="dfb0b-117">Du kan också aktivera eller inaktivera det i enskilda klienter med Windows-säkerhet program.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="dfb0b-118">Se [Använda Microsoft moln levererat skydd för](cloud-protection-microsoft-defender-antivirus.md) en översikt över Microsoft Defender Antivirus moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="dfb0b-119">Mer information om specifika nätverksanslutningskrav för att säkerställa att slutpunkterna kan ansluta till den molnbaserade skyddstjänsten finns i [Konfigurera och verifiera nätverksanslutningar.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dfb0b-120">I Windows 10 finns det ingen skillnad mellan **rapportalternativen Grundläggande** och **Avancerat** som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="dfb0b-121">Det här är en äldre skillnad och om du väljer en av inställningarna får du samma nivå av moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="dfb0b-122">Det är ingen skillnad på vilken typ av information och hur mycket information som delas.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="dfb0b-123">Mer information om vad vi samlar in finns i [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-124">Använda Intune för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dfb0b-125">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="dfb0b-126">I fönstret **Start** väljer du **Enhetskonfiguration > Profiler**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="dfb0b-127">Välj den **profiltyp för** Enhetsbegränsningar som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="dfb0b-128">Om du behöver skapa en ny **profiltyp för Enhetsbegränsningar** kan du gå [till Konfigurera inställningar för enhetsbegränsningar i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="dfb0b-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="dfb0b-129">Välj   >  **Konfigurationsinställningar för egenskaper:**  >  **Redigera Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="dfb0b-130">På **växeln Moln levererat skydd** väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="dfb0b-131">I **listrutan Fråga användarna före** exempelinskickning väljer du Skicka alla data **automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="dfb0b-132">Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar, finns i [Vad är Microsoft Intune enhetsprofiler?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-133">Använd Microsoft Endpoint Manager för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dfb0b-134">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="dfb0b-135">Välj **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-135">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="dfb0b-136">Välj en antivirusprofil.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-136">Select an antivirus profile.</span></span> <span data-ttu-id="dfb0b-137">(Om du inte redan har en, eller om du vill skapa en ny profil, se Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="dfb0b-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="dfb0b-138">Välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-138">Select **Properties**.</span></span> <span data-ttu-id="dfb0b-139">Välj sedan Redigera bredvid **Konfigurationsinställningar.** </span><span class="sxs-lookup"><span data-stu-id="dfb0b-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="dfb0b-140">Expandera **Molnskydd** och välj sedan **något** av följande i listan Moln levererat skyddsnivå:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="dfb0b-141">**Hög:** Använder en stark identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-141">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="dfb0b-142">**Hög plus:** Använder **högnivån** och tillämpar ytterligare skyddsåtgärder (kan påverka klientprestandan).</span><span class="sxs-lookup"><span data-stu-id="dfb0b-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="dfb0b-143">**Nollarvering**: Blockerar alla okända körbara filer.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-143">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="dfb0b-144">Välj **Granska + spara** och välj sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="dfb0b-145">Mer information om konfigurering av Microsoft Endpoint Configuration Manager finns i Skapa och distribuera principer för skydd mot [skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="dfb0b-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-146">Använda grupprinciper för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="dfb0b-147">Öppna grupprinciphanteringskonsolen på [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="dfb0b-148">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="dfb0b-149">Välj **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="dfb0b-150">Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > KARTOR**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="dfb0b-151">Dubbelklicka på Anslut **till Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="dfb0b-152">Kontrollera att alternativet är aktiverat och inställt på **Grundläggande KARTOR** eller **Avancerade KARTOR.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="dfb0b-153">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-153">Select **OK**.</span></span>

6. <span data-ttu-id="dfb0b-154">Dubbelklicka på Skicka **filexempel när ytterligare analys krävs**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="dfb0b-155">Kontrollera att det första alternativet är **inställt på Aktiverad** och att de andra alternativen är inställda på något av följande:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="dfb0b-156">**Skicka säkra exempel** (1)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="dfb0b-157">**Skicka alla exempel** (3)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="dfb0b-158">Alternativet **Skicka säkra exempel** (1) innebär att de flesta urval kommer att skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="dfb0b-159">Filer som troligtvis innehåller personlig information uppmanas fortfarande och kräver ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="dfb0b-160">Om du anger **alternativet Fråga** alltid (0) sänks skyddstillståndet för enheten.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="dfb0b-161">Om du ställer **in det på** Skicka aldrig (2) innebär det att funktionen [Blockera](configure-block-at-first-sight-microsoft-defender-antivirus.md) vid första synning i Microsoft Defender för slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="dfb0b-162">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-163">Använda PowerShell-cmdlets för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="dfb0b-164">Följande cmdlets kan aktivera moln levererat skydd:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="dfb0b-165">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="dfb0b-166">[Policy CSP – Defender](/windows/client-management/mdm/policy-csp-defender) har också mer information specifikt om [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="dfb0b-167">Du kan också **ange -SubmitSamplesConsent** `SendSafeSamples` till (standardinställningen), `NeverSend` eller `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="dfb0b-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="dfb0b-168">Inställningen `SendSafeSamples` innebär att de flesta exempel skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="dfb0b-169">Filer som troligtvis innehåller personlig information uppmanas fortfarande och kräver ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="dfb0b-170">Inställning **-SubmitSamplesConsent** till `NeverSend` eller `AlwaysPrompt` sänker skyddsnivån för enheten.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="dfb0b-171">Om du sätter den till `NeverSend` innebär det också att funktionen Blockera vid första synning [i](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender för Slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="dfb0b-172">Använd Windows management instruction (WMI) för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="dfb0b-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="dfb0b-173">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="dfb0b-174">Mer information om tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="dfb0b-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="dfb0b-175">Aktivera moln levererat skydd på enskilda klienter med Windows-säkerhet program</span><span class="sxs-lookup"><span data-stu-id="dfb0b-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="dfb0b-176">Om inställningen Konfigurera lokal åsidosättning för rapportering av Grupprincip för  **Microsoft MAPS** är inställd på Inaktiverad kommer den molnbaserade skyddsinställningen i Windows Inställningar att vara nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="dfb0b-177">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows Inställningar.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="dfb0b-178">Öppna Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka efter Defender på **startmenyn.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="dfb0b-179">Välj panelen **&** för skydd mot hot (eller sköldikonen på den vänstra menyraden) och sedan & för skydd **mot** hot:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhet datorprogrammet](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="dfb0b-181">Kontrollera att **molnbaserat skydd och automatisk** **exempelinskickning** är på **.**</span><span class="sxs-lookup"><span data-stu-id="dfb0b-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="dfb0b-182">Om automatisk exempelinskickning har konfigurerats med Grupprincip kommer inställningen att vara nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dfb0b-183">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="dfb0b-183">Related articles</span></span>

- [<span data-ttu-id="dfb0b-184">Konfigurera tidsgräns för blockering i molnet</span><span class="sxs-lookup"><span data-stu-id="dfb0b-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dfb0b-185">Konfigurera blocket vid första synen</span><span class="sxs-lookup"><span data-stu-id="dfb0b-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dfb0b-186">Använd cmdlets från PowerShell för att hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="dfb0b-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="dfb0b-187">[Skydda Windows datorer med Endpoint Protection för Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="dfb0b-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="dfb0b-188">Defender-cmdlets</span><span class="sxs-lookup"><span data-stu-id="dfb0b-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="dfb0b-189">Använd Microsoft moln levererat skydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="dfb0b-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dfb0b-190">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="dfb0b-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="dfb0b-191">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="dfb0b-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
