---
title: Aktivera molnskydd i Microsoft Defender Antivirus
description: Aktivera molnskydd för att dra nytta av snabba och avancerade skyddsfunktioner.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, moln, blockera vid första anblicken
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
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-104">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b10ba-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b10ba-105">**Applies to:**</span></span>

- [<span data-ttu-id="b10ba-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b10ba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="b10ba-107">Den Microsoft Defender Antivirus molntjänsten är en mekanism för att leverera uppdaterat skydd till ditt nätverk och punkter.</span><span class="sxs-lookup"><span data-stu-id="b10ba-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="b10ba-108">Även om det kallas en molntjänst är det inte bara skydd för filer som lagras i molnet; I stället används distribuerade resurser och maskininlärning för att leverera skydd till dina punkter i en hastighet som är mycket snabbare än traditionella Security Intelligence-uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="b10ba-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="b10ba-109">Microsoft Defender Antivirus använder flera detekterings- och förebyggande tekniker för att leverera korrekt, realtids- och intelligent skydd.</span><span class="sxs-lookup"><span data-stu-id="b10ba-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="b10ba-110">[Lär känna de avancerade teknikerna i kärnan av Microsoft Defender för Endpoint nästa generations skydd](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="b10ba-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="b10ba-111">Du kan aktivera Microsoft Defender Antivirus molnskydd på eller av på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="b10ba-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="b10ba-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b10ba-112">Microsoft Intune</span></span>
- <span data-ttu-id="b10ba-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b10ba-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="b10ba-114">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="b10ba-114">Group Policy</span></span>
- <span data-ttu-id="b10ba-115">PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b10ba-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="b10ba-116">Du kan också aktivera eller inaktivera den i enskilda klienter med Windows-säkerhet appen.</span><span class="sxs-lookup"><span data-stu-id="b10ba-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="b10ba-117">Se [Använda Microsofts molnbaserade skydd](cloud-protection-microsoft-defender-antivirus.md) för en översikt över Microsoft Defender Antivirus ett molnskydd.</span><span class="sxs-lookup"><span data-stu-id="b10ba-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="b10ba-118">Mer information om de specifika kraven för nätverksanslutning för att säkerställa att slutpunkterna kan ansluta till den molnbaserade skyddstjänsten finns i [Konfigurera och validera nätverksanslutningar](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b10ba-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b10ba-119">I Windows 10 finns det ingen skillnad mellan alternativen grundläggande **och** **avancerad rapportering som beskrivs** i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b10ba-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="b10ba-120">Detta är en äldre distinktion och att välja någon av inställningen kommer att resultera i samma nivå av molnskydd.</span><span class="sxs-lookup"><span data-stu-id="b10ba-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="b10ba-121">Det finns ingen skillnad i vilken typ eller mängd information som delas.</span><span class="sxs-lookup"><span data-stu-id="b10ba-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="b10ba-122">Mer information om vad vi samlar in finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="b10ba-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-123">Använd Intune för att aktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="b10ba-124">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="b10ba-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="b10ba-125">Välj **Enhetskonfiguration** för **enhetsprofiler i > fönstret**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="b10ba-126">Välj den **profiltyp för** enhetsbegränsningar som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="b10ba-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="b10ba-127">Om du behöver skapa en ny **profiltyp för enhetsbegränsningar** kan du [se Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="b10ba-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="b10ba-128">Välj **inställningar för**  >  **egenskapskonfiguration:** Redigera  >  **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="b10ba-129">Välj Aktivera **på den molnbaserade** skyddsbrytaren. </span><span class="sxs-lookup"><span data-stu-id="b10ba-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="b10ba-130">I **listrutan Fråga användare före exempelöverföring** väljer **du Skicka alla data automatiskt**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="b10ba-131">Mer information om Intune-enhetsprofiler, inklusive hur du skapar och konfigurerar deras inställningar, [finns i Microsoft Intune enhetsprofiler?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="b10ba-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-132">Använd Microsoft Endpoint Manager för att aktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="b10ba-133">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="b10ba-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="b10ba-134">Välj **Säkerhets antivirus för**  >  **slutpunkt**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="b10ba-135">Välj en antivirusprofil.</span><span class="sxs-lookup"><span data-stu-id="b10ba-135">Select an antivirus profile.</span></span> <span data-ttu-id="b10ba-136">(Om du inte har en ännu eller om du vill skapa en ny profil kan du se [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="b10ba-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="b10ba-137">Välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-137">Select **Properties**.</span></span> <span data-ttu-id="b10ba-138">Välj sedan Redigera bredvid  **Konfigurationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="b10ba-139">Expandera **molnskydd** och välj sedan något av följande i listan **Molnskyddsnivå:**</span><span class="sxs-lookup"><span data-stu-id="b10ba-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="b10ba-140">**Hög**: Tillämpar en stark detektionsnivå.</span><span class="sxs-lookup"><span data-stu-id="b10ba-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="b10ba-141">**Högt plus:** Använder **hög nivå** och tillämpar ytterligare skyddsåtgärder (kan påverka klientens prestanda).</span><span class="sxs-lookup"><span data-stu-id="b10ba-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="b10ba-142">**Nolltolerans**: Blockerar alla okända körbara filer.</span><span class="sxs-lookup"><span data-stu-id="b10ba-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="b10ba-143">Välj **Granska + spara** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="b10ba-144">Mer information om hur du konfigurerar Microsoft Endpoint Configuration Manager finns i [Så här skapar och distribuerar du principer för skadlig kod: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="b10ba-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-145">Använd grupprincip för att aktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="b10ba-146">Öppna konsolen Grupprinciphantering på [grupprinciphanteringskonsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="b10ba-147">Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b10ba-148">Välj **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="b10ba-149">Expandera trädet **Windows komponenter > Microsoft Defender Antivirus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="b10ba-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="b10ba-150">Dubbelklicka **på Gå med i Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="b10ba-151">Kontrollera att alternativet är aktiverat och inställt på **Grundläggande KARTOR** eller **Avancerade KARTOR**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="b10ba-152">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-152">Select **OK**.</span></span>

6. <span data-ttu-id="b10ba-153">Dubbelklicka **på Skicka filexempel när ytterligare analys krävs**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="b10ba-154">Kontrollera att det första alternativet är inställt på **Aktiverat** och att de andra alternativen är inställda på antingen:</span><span class="sxs-lookup"><span data-stu-id="b10ba-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="b10ba-155">**Skicka säkra prover** (1)</span><span class="sxs-lookup"><span data-stu-id="b10ba-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="b10ba-156">**Skicka alla prover** (3)</span><span class="sxs-lookup"><span data-stu-id="b10ba-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="b10ba-157">Alternativet **Skicka säkra prover** (1) innebär att de flesta prover skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b10ba-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="b10ba-158">Filer som sannolikt innehåller personlig information kommer fortfarande att fråga och kräva ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="b10ba-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="b10ba-159">Om du ställer in **alternativet Till Fråga** alltid (0) sänks enhetens skyddstillstånd.</span><span class="sxs-lookup"><span data-stu-id="b10ba-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="b10ba-160">Om du ställer **in den** på Skicka (2) betyder det att funktionen [Blockera vid](configure-block-at-first-sight-microsoft-defender-antivirus.md) första ögonkastet i Microsoft Defender för slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="b10ba-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="b10ba-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-162">Använd PowerShell-cmdlets för att aktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="b10ba-163">Följande cmdletar kan aktivera molnskydd:</span><span class="sxs-lookup"><span data-stu-id="b10ba-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="b10ba-164">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i [Använda PowerShell-cmdletar för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdletar](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="b10ba-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="b10ba-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) har också mer information specifikt om [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="b10ba-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="b10ba-166">Du kan också ställa **in -SubmitSamplesConsent** till `SendSafeSamples` (standardinställningen), `NeverSend` eller `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="b10ba-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="b10ba-167">Inställningen `SendSafeSamples` innebär att de flesta exempel skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b10ba-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="b10ba-168">Filer som sannolikt innehåller personlig information kommer fortfarande att fråga och kräva ytterligare bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="b10ba-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="b10ba-169">Inställning **-SubmitSamplesConsent** `NeverSend` till eller sänker `AlwaysPrompt` enhetens skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="b10ba-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="b10ba-170">Om du ställer in den `NeverSend` på betyder det dessutom att funktionen Blockera [vid](configure-block-at-first-sight-microsoft-defender-antivirus.md) första ögonkastet i Microsoft Defender för slutpunkt inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="b10ba-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="b10ba-171">Använd Windows Management Instruction (WMI) för att aktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="b10ba-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="b10ba-172">Använd [ **klassen Set** för **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="b10ba-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="b10ba-173">Mer information om tillåtna parametrar finns i [Windows Defender WMIv2 API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b10ba-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="b10ba-174">Aktivera molnskydd för enskilda klienter med den Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="b10ba-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="b10ba-175">Om inställningen **Konfigurera lokal inställning för rapportering av Microsoft MAPS-grupprincipinställning** är inaktiverad **blir** **den molnbaserade** skyddsinställningen i Windows Inställningar nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b10ba-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="b10ba-176">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="b10ba-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="b10ba-177">Öppna appen Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka på startmenyn för **Defender**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="b10ba-178">Välj **viruspanelen & hotskydd** (eller sköldikonen på den vänstra menyraden) **och sedan etiketten Virus & hotskydd:**</span><span class="sxs-lookup"><span data-stu-id="b10ba-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Skärmbild på inställningsetiketten för Skydd mot virus och hot i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="b10ba-180">Bekräfta att **molnbaserat skydd och** automatisk **provöverföring är** växlade till **På**.</span><span class="sxs-lookup"><span data-stu-id="b10ba-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="b10ba-181">Om automatisk exempelöverföring har konfigurerats med Grupprincip blir inställningen nedtonad och otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b10ba-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b10ba-182">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="b10ba-182">Related articles</span></span>

- [<span data-ttu-id="b10ba-183">Konfigurera tidsgräns för blockering i molnet</span><span class="sxs-lookup"><span data-stu-id="b10ba-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b10ba-184">Konfigurera block vid första anblicken</span><span class="sxs-lookup"><span data-stu-id="b10ba-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b10ba-185">Använd cmdlets från PowerShell för att hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b10ba-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="b10ba-186">[Hjälp till Windows skydda datorer Endpoint Protection för Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="b10ba-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="b10ba-187">Defender cmdlets</span><span class="sxs-lookup"><span data-stu-id="b10ba-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="b10ba-188">Använd Microsofts molnskydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b10ba-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b10ba-189">Så här skapar och distribuerar du principer mot skadlig kod: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="b10ba-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="b10ba-190">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="b10ba-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
