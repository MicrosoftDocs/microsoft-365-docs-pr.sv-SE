---
title: Öka efterlevnad för Microsoft Defender för slutpunktens säkerhetsbaslinje
description: Säkerhetsbaslinjen för Microsoft Defender för Slutpunkt anger säkerhetskontroller för att ge optimalt skydd.
keywords: Hantering av Intune, Microsoft Defender för Slutpunkt, Microsoft Defender, Microsoft Defender för Slutpunkt ASR, säkerhetsbaslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933607"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="897bb-104">Öka efterlevnad för Microsoft Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="897bb-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="897bb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="897bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="897bb-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="897bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="897bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="897bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="897bb-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="897bb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="897bb-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="897bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="897bb-110">Säkerhetsbaslinjer säkerställer att säkerhetsfunktionerna konfigureras enligt vägledning från både säkerhetsexperter och experta Windows-systemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="897bb-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="897bb-111">När den har distribuerats ger Defender för Slutpunktens säkerhetsbaslinje baslinje Defender för slutpunktssäkerhetskontroller för att ge optimalt skydd.</span><span class="sxs-lookup"><span data-stu-id="897bb-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="897bb-112">Läs följande vanliga frågor och svar för att förstå säkerhetsbaslinjer och hur de tilldelas på Intune [med hjälp av konfigurationsprofiler.](https://docs.microsoft.com/intune/security-baselines#q--a)</span><span class="sxs-lookup"><span data-stu-id="897bb-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="897bb-113">Innan du kan distribuera och spåra efterlevnad för säkerhetsbaslinjer:</span><span class="sxs-lookup"><span data-stu-id="897bb-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="897bb-114">Registrera dina enheter till Intune-hantering</span><span class="sxs-lookup"><span data-stu-id="897bb-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="897bb-115">Kontrollera att du har de behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="897bb-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="897bb-116">Jämför Säkerhetsbaslinjer för Microsoft Defender för Slutpunkt och Windows Intune</span><span class="sxs-lookup"><span data-stu-id="897bb-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="897bb-117">Säkerhetsbaslinjen för Windows Intune innehåller en omfattande uppsättning rekommenderade inställningar som krävs för att säkert konfigurera enheter som kör Windows, inklusive webbläsarinställningar, PowerShell-inställningar samt inställningar för vissa säkerhetsfunktioner som Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="897bb-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="897bb-118">Defender för slutpunktsbaslinje tillhandahåller däremot inställningar som optimerar alla säkerhetskontroller i Defender för slutpunktsstacken, inklusive inställningar för identifiering av slutpunkt och svar (EDR) samt inställningar som också finns i Windows Intune-säkerhetsbaslinjen.</span><span class="sxs-lookup"><span data-stu-id="897bb-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="897bb-119">Mer information om varje baslinje finns i:</span><span class="sxs-lookup"><span data-stu-id="897bb-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="897bb-120">Inställningar för Windows-säkerhetsbaslinje för Intune</span><span class="sxs-lookup"><span data-stu-id="897bb-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="897bb-121">Baslinjeinställningar för Microsoft Defender för Slutpunkt för Intune</span><span class="sxs-lookup"><span data-stu-id="897bb-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="897bb-122">Under idealiska förhållanden distribueras enheter som finns i Defender för Slutpunkt med båda baslinjerna: Säkerhetsbaslinjen för Windows Intune till att först skydda Windows och sedan Defender för slutpunktens säkerhetsbaslinje lagd ovanpå för att optimalt konfigurera Defender för slutpunktssäkerhetskontroller.</span><span class="sxs-lookup"><span data-stu-id="897bb-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="897bb-123">För att dra nytta av de senaste data om risker och hot och för att minimera konflikter allt eftersom baslinjer utvecklas ska du alltid använda de senaste versionerna av baslinjerna för alla produkter så snart de släpps.</span><span class="sxs-lookup"><span data-stu-id="897bb-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="897bb-124">Säkerhetsbaslinjen för Defender för slutpunkt har optimerats för fysiska enheter och rekommenderas för närvarande inte för användning på virtuella maskiner eller VDI-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="897bb-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="897bb-125">Vissa baslinjeinställningar kan påverka fjärranslutna interaktiva sessioner i virtualiserade miljöer.</span><span class="sxs-lookup"><span data-stu-id="897bb-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="897bb-126">Övervaka efterlevnad av Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="897bb-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="897bb-127">Kortet **med säkerhetsbaslinje** för hantering av [enhetskonfiguration](configure-machines.md) ger en översikt över efterlevnad för alla Windows 10-enheter som har tilldelats Defender för slutpunktens säkerhetsbaslinje.</span><span class="sxs-lookup"><span data-stu-id="897bb-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="897bb-128">![Baslinjekort för säkerhet](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="897bb-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="897bb-129">*Kort som visar efterlevnad för Defender för slutpunktens säkerhetsbaslinje*</span><span class="sxs-lookup"><span data-stu-id="897bb-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="897bb-130">Varje enhet ges en av följande statustyper:</span><span class="sxs-lookup"><span data-stu-id="897bb-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="897bb-131">**Matchar baslinjen**– enhetsinställningarna matchar alla inställningar i baslinjen</span><span class="sxs-lookup"><span data-stu-id="897bb-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="897bb-132">**Stämmer inte in på** baslinjen – minst en enhetsinställning matchar inte baslinjen</span><span class="sxs-lookup"><span data-stu-id="897bb-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="897bb-133">**Felkonfigurerad**– minst en baslinjeinställning är inte korrekt konfigurerad på enheten och statusen är konflikt, fel eller väntande</span><span class="sxs-lookup"><span data-stu-id="897bb-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="897bb-134">**Inte tillämpligt**– minst en baslinjeinställning är inte tillämplig på enheten</span><span class="sxs-lookup"><span data-stu-id="897bb-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="897bb-135">Om du vill granska vissa enheter väljer **du Konfigurera säkerhetsbaslinje** på kortet.</span><span class="sxs-lookup"><span data-stu-id="897bb-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="897bb-136">Då kommer du till Intune-enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="897bb-136">This takes you to Intune device management.</span></span> <span data-ttu-id="897bb-137">Därifrån väljer **du Enhetsstatus** för namn och status för enheterna.</span><span class="sxs-lookup"><span data-stu-id="897bb-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="897bb-138">Det kan hända att avvikelser visas i aggregerade data på sidan Konfigurationshantering för enheter och data som visas på översiktsskärmar i Intune.</span><span class="sxs-lookup"><span data-stu-id="897bb-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="897bb-139">Granska och tilldela Microsoft Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="897bb-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="897bb-140">Enhetshantering övervakar endast grundläggande efterlevnad av Windows 10-enheter som specifikt har tilldelats Microsoft Defender för slutpunktens säkerhetsbaslinje.</span><span class="sxs-lookup"><span data-stu-id="897bb-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="897bb-141">Du kan enkelt granska baslinjen och tilldela den till enheter med Intune-enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="897bb-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="897bb-142">Välj **Konfigurera säkerhetsbaslinje** på kortet **Säkerhetsbaslinje** om du vill gå till Intune-enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="897bb-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="897bb-143">En liknande översikt över grundläggande efterlevnad visas.</span><span class="sxs-lookup"><span data-stu-id="897bb-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="897bb-144">Alternativt kan du navigera till säkerhetsbaslinjen för Defender för slutpunkt i Microsoft Azure-portalen från Alla tjänster **> Intune > Enhetssäkerhet > Säkerhetsbaslinjer > baslinje > Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="897bb-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="897bb-145">Skapa en ny profil.</span><span class="sxs-lookup"><span data-stu-id="897bb-145">Create a new profile.</span></span>

   <span data-ttu-id="897bb-146">![Översikt över Säkerhetsbaslinje för Microsoft Defender för Slutpunkt på Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="897bb-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="897bb-147">*Översikt över Säkerhetsbaslinje för Microsoft Defender för Slutpunkt på Intune*</span><span class="sxs-lookup"><span data-stu-id="897bb-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="897bb-148">När du skapar en profil kan du granska och justera specifika inställningar för originalplanen.</span><span class="sxs-lookup"><span data-stu-id="897bb-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="897bb-149">![Alternativ för säkerhetsbaslinje vid profilskapande på Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="897bb-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="897bb-150">*Alternativ för säkerhetsbaslinje vid profilskapande på Intune*</span><span class="sxs-lookup"><span data-stu-id="897bb-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="897bb-151">Tilldela profilen till rätt enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="897bb-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="897bb-152">![Säkerhetsbaslinjeprofiler i Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="897bb-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="897bb-153">*Tilldela säkerhetsbaslinjeprofilen i Intune*</span><span class="sxs-lookup"><span data-stu-id="897bb-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="897bb-154">Skapa profilen för att spara den och distribuera den till den tilldelade enhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="897bb-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="897bb-155">![Tilldela säkerhetsbaslinjen i Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="897bb-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="897bb-156">*Skapa säkerhetsbaslinjeprofilen i Intune*</span><span class="sxs-lookup"><span data-stu-id="897bb-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="897bb-157">Säkerhetsbaslinjer för Intune är ett bekvämt sätt att skydda dina enheter på ett fullständigt säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="897bb-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="897bb-158">[Läs mer om säkerhetsbaslinjer i Intune](https://docs.microsoft.com/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="897bb-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="897bb-159">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="897bb-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="897bb-160">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="897bb-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="897bb-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="897bb-161">Related topics</span></span>
- [<span data-ttu-id="897bb-162">Se till att dina enheter är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="897bb-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="897bb-163">Få enheter skickade till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="897bb-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="897bb-164">Optimera ASR-regeldistribution och identifiering</span><span class="sxs-lookup"><span data-stu-id="897bb-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
