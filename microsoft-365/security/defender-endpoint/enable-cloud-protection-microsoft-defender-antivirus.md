---
title: Aktivera moln levererat skydd i Microsoft Defender Antivirus
description: Aktivera moln levererat skydd för att dra nytta av funktioner för snabbt och avancerat skydd.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, moln, block vid första synen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572063"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-104">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f92c4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f92c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="f92c4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f92c4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="f92c4-107">Den Microsoft Defender Antivirus molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till nätverket och slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="f92c4-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="f92c4-108">Även om den kallas för en molntjänst är den inte bara skydd för filer som lagras i molnet. I stället används distribuerade resurser och maskininlärning för att ge skydd till dina slutpunkter i en takt som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="f92c4-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="f92c4-109">Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, realtids- och intelligent skydd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="f92c4-110">[Lär känna de avancerade teknikerna som ligger till grund för nästa](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)generations skydd för Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="f92c4-111">Du kan aktivera Microsoft Defender Antivirus eller inaktivera moln levererat-skydd på flera olika sätt:</span><span class="sxs-lookup"><span data-stu-id="f92c4-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="f92c4-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f92c4-112">Microsoft Intune</span></span>
- <span data-ttu-id="f92c4-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f92c4-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="f92c4-114">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="f92c4-114">Group Policy</span></span>
- <span data-ttu-id="f92c4-115">PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f92c4-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="f92c4-116">Du kan också aktivera eller inaktivera det i enskilda klienter med Windows-säkerhet program.</span><span class="sxs-lookup"><span data-stu-id="f92c4-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="f92c4-117">Se [Använda Microsoft moln levererat skydd för](cloud-protection-microsoft-defender-antivirus.md) en översikt över Microsoft Defender Antivirus moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="f92c4-118">Mer information om specifika nätverksanslutningskrav för att säkerställa att slutpunkterna kan ansluta till den molnbaserade skyddstjänsten finns i [Konfigurera och verifiera nätverksanslutningar.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f92c4-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f92c4-119">I Windows 10 finns det ingen skillnad mellan **rapportalternativen Grundläggande** och **Avancerat** som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f92c4-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="f92c4-120">Det här är en äldre skillnad och om du väljer en av inställningarna får du samma nivå av moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="f92c4-121">Det är ingen skillnad på vilken typ av information och hur mycket information som delas.</span><span class="sxs-lookup"><span data-stu-id="f92c4-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="f92c4-122">Mer information om vad vi samlar in finns i [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="f92c4-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-123">Använda Intune för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="f92c4-124">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="f92c4-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="f92c4-125">I fönstret **Start** väljer du **Enhetskonfiguration > Profiler**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="f92c4-126">Välj den **profiltyp för** Enhetsbegränsningar som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="f92c4-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="f92c4-127">Om du behöver skapa en ny **profiltyp för Enhetsbegränsningar** kan du gå [till Konfigurera inställningar för enhetsbegränsningar i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="f92c4-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="f92c4-128">Välj   >  **Konfigurationsinställningar för egenskaper:**  >  **Redigera Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="f92c4-129">På **växeln Moln levererat skydd** väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="f92c4-130">I **listrutan Fråga användarna före** exempelinskickning väljer du Skicka alla data **automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="f92c4-131">Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar, finns i [Vad är Microsoft Intune enhetsprofiler?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="f92c4-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-132">Använd Microsoft Endpoint Manager för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="f92c4-133">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="f92c4-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="f92c4-134">Välj **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="f92c4-135">Välj en antivirusprofil.</span><span class="sxs-lookup"><span data-stu-id="f92c4-135">Select an antivirus profile.</span></span> <span data-ttu-id="f92c4-136">(Om du inte redan har en, eller om du vill skapa en ny profil, se Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="f92c4-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="f92c4-137">Välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-137">Select **Properties**.</span></span> <span data-ttu-id="f92c4-138">Välj sedan Redigera bredvid **Konfigurationsinställningar.** </span><span class="sxs-lookup"><span data-stu-id="f92c4-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="f92c4-139">Expandera **Molnskydd** och välj sedan **något** av följande i listan Moln levererat skyddsnivå:</span><span class="sxs-lookup"><span data-stu-id="f92c4-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="f92c4-140">**Hög:** Använder en stark identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="f92c4-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="f92c4-141">**Hög plus:** Använder **högnivån** och tillämpar ytterligare skyddsåtgärder (kan påverka klientprestandan).</span><span class="sxs-lookup"><span data-stu-id="f92c4-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="f92c4-142">**Nollarvering**: Blockerar alla okända körbara filer.</span><span class="sxs-lookup"><span data-stu-id="f92c4-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="f92c4-143">Välj **Granska + spara** och välj sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="f92c4-144">Mer information om konfigurering av Microsoft Endpoint Configuration Manager finns i Skapa och distribuera principer för skydd mot [skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="f92c4-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-145">Använda grupprinciper för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="f92c4-146">Öppna grupprinciphanteringskonsolen på [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="f92c4-147">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="f92c4-148">Välj **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="f92c4-149">Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > KARTOR**</span><span class="sxs-lookup"><span data-stu-id="f92c4-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="f92c4-150">Dubbelklicka på Anslut **till Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="f92c4-151">Kontrollera att alternativet är aktiverat och inställt på **Grundläggande KARTOR** eller **Avancerade KARTOR.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="f92c4-152">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-152">Select **OK**.</span></span>

6. <span data-ttu-id="f92c4-153">Dubbelklicka på Skicka **filexempel när ytterligare analys krävs**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="f92c4-154">Kontrollera att det första alternativet är **inställt på Aktiverad** och att de andra alternativen är inställda på något av följande:</span><span class="sxs-lookup"><span data-stu-id="f92c4-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="f92c4-155">**Skicka säkra exempel** (1)</span><span class="sxs-lookup"><span data-stu-id="f92c4-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="f92c4-156">**Skicka alla exempel** (3)</span><span class="sxs-lookup"><span data-stu-id="f92c4-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="f92c4-157">Alternativet **Skicka säkra exempel** (1) innebär att de flesta urval kommer att skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="f92c4-158">Filer som troligtvis innehåller personlig information uppmanas fortfarande och kräver ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="f92c4-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="f92c4-159">Om du anger **alternativet Fråga** alltid (0) sänks skyddstillståndet för enheten.</span><span class="sxs-lookup"><span data-stu-id="f92c4-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="f92c4-160">Om du ställer **in det på** Skicka aldrig (2) innebär det att funktionen [Blockera](configure-block-at-first-sight-microsoft-defender-antivirus.md) vid första synning i Microsoft Defender för slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="f92c4-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="f92c4-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-162">Använda PowerShell-cmdlets för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="f92c4-163">Följande cmdlets kan aktivera moln levererat skydd:</span><span class="sxs-lookup"><span data-stu-id="f92c4-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="f92c4-164">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="f92c4-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="f92c4-165">[Policy CSP – Defender](/windows/client-management/mdm/policy-csp-defender) har också mer information specifikt om [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)</span><span class="sxs-lookup"><span data-stu-id="f92c4-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="f92c4-166">Du kan också **ange -SubmitSamplesConsent** `SendSafeSamples` till (standardinställningen), `NeverSend` eller `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="f92c4-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="f92c4-167">Inställningen `SendSafeSamples` innebär att de flesta exempel skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="f92c4-168">Filer som troligtvis innehåller personlig information uppmanas fortfarande och kräver ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="f92c4-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="f92c4-169">Inställning **-SubmitSamplesConsent** till `NeverSend` eller `AlwaysPrompt` sänker skyddsnivån för enheten.</span><span class="sxs-lookup"><span data-stu-id="f92c4-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="f92c4-170">Om du sätter den till `NeverSend` innebär det också att funktionen Blockera vid första synning [i](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender för Slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="f92c4-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="f92c4-171">Använd Windows management instruction (WMI) för att aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="f92c4-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="f92c4-172">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="f92c4-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="f92c4-173">Mer information om tillåtna parametrar finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f92c4-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="f92c4-174">Aktivera moln levererat skydd på enskilda klienter med Windows-säkerhet program</span><span class="sxs-lookup"><span data-stu-id="f92c4-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="f92c4-175">Om inställningen Konfigurera lokal åsidosättning för rapportering av Grupprincip för  **Microsoft MAPS** är inställd på Inaktiverad kommer den molnbaserade skyddsinställningen i Windows Inställningar att vara nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f92c4-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="f92c4-176">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f92c4-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="f92c4-177">Öppna Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka efter Defender på **startmenyn.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="f92c4-178">Välj panelen **&** för skydd mot hot (eller sköldikonen på den vänstra menyraden) och sedan & för skydd **mot** hot:</span><span class="sxs-lookup"><span data-stu-id="f92c4-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Skärmbild på inställningsetiketten för Skydd mot virus och hot i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="f92c4-180">Kontrollera att **molnbaserat skydd och automatisk** **exempelinskickning** är på **.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="f92c4-181">Om automatisk exempelinskickning har konfigurerats med Grupprincip kommer inställningen att vara nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f92c4-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f92c4-182">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="f92c4-182">Related articles</span></span>

- [<span data-ttu-id="f92c4-183">Konfigurera tidsgräns för blockering i molnet</span><span class="sxs-lookup"><span data-stu-id="f92c4-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f92c4-184">Konfigurera blocket vid första synen</span><span class="sxs-lookup"><span data-stu-id="f92c4-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f92c4-185">Använd cmdlets från PowerShell för att hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f92c4-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="f92c4-186">[Skydda Windows datorer med Endpoint Protection för Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="f92c4-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="f92c4-187">Defender-cmdlets</span><span class="sxs-lookup"><span data-stu-id="f92c4-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="f92c4-188">Använd Microsoft moln levererat skydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f92c4-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f92c4-189">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="f92c4-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="f92c4-190">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="f92c4-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
