---
title: Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter
description: Använd verktyg för hantering av mobila enheter för att distribuera konfigurationspaketet på enheter så att de kan kommas in i tjänsten.
keywords: onboard-enheter som använder mdm, enhetshantering, onboard Windows ATP-enheter, onboard Microsoft Defender för Endpoint-enheter, mdm
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
ms.openlocfilehash: f3042ef9ced11ebc5439308d2781528d5267975f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893619"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="77e0e-104">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="77e0e-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77e0e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="77e0e-105">**Applies to:**</span></span>
- [<span data-ttu-id="77e0e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="77e0e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77e0e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77e0e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="77e0e-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="77e0e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="77e0e-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="77e0e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="77e0e-110">Du kan använda MDM-lösningar (Mobile Device Management) för att konfigurera enheter.</span><span class="sxs-lookup"><span data-stu-id="77e0e-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="77e0e-111">Defender för Endpoint stöder MDM genom att tillhandahålla OMA-URIs att skapa principer för att hantera enheter.</span><span class="sxs-lookup"><span data-stu-id="77e0e-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="77e0e-112">Mer information om hur du använder Defender för slutpunkt-CSP finns i [WindowsAdvancedThreatProtection CSP-](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) och [WindowsAdvancedThreatProtection DDF-fil.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="77e0e-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77e0e-113">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="77e0e-113">Before you begin</span></span>
<span data-ttu-id="77e0e-114">Om du använder Microsoft Intune måste enheten MDM vara registrerad.</span><span class="sxs-lookup"><span data-stu-id="77e0e-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="77e0e-115">Annars kommer inställningarna inte att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="77e0e-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="77e0e-116">Mer information om hur du aktiverar MDM med Microsoft Intune finns i [Enhetsregistrering (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="77e0e-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="77e0e-117">Onboard-enheter med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77e0e-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="77e0e-118">[![Bild av PDF-filen som visar onboarding-enheter för Defender för Endpoint med Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77e0e-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="77e0e-119">Ta en titta på [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [eller Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distribuera Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="77e0e-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="77e0e-120">Följ instruktionerna från [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="77e0e-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="77e0e-121">Mer information om hur du använder Defender för slutpunkt-CSP finns i [WindowsAdvancedThreatProtection CSP-](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) och [WindowsAdvancedThreatProtection DDF-fil.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="77e0e-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="77e0e-122">Principen **Hälsostatus för onboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="77e0e-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="77e0e-123">Konfiguration av frekvens för diagnostikdatarapportering är endast tillgänglig för enheter i Windows 10 version 1703.</span><span class="sxs-lookup"><span data-stu-id="77e0e-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="77e0e-124">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="77e0e-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="77e0e-125">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="77e0e-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="77e0e-126">Läs PDF- [eller](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distributionen av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="77e0e-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="77e0e-127">Offboard och övervaka enheter med hjälp av verktyg för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="77e0e-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="77e0e-128">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="77e0e-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="77e0e-129">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="77e0e-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="77e0e-130">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="77e0e-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="77e0e-131">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="77e0e-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="77e0e-132">Hämta offboarding-paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="77e0e-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="77e0e-133">I navigeringsfönstret väljer du **Inställningar**  >  **offboarding**.</span><span class="sxs-lookup"><span data-stu-id="77e0e-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="77e0e-134">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="77e0e-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="77e0e-135">I fältet **Distributionsmetod** väljer du **Hantering av mobila enheter/Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="77e0e-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="77e0e-136">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="77e0e-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="77e0e-137">Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet.</span><span class="sxs-lookup"><span data-stu-id="77e0e-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="77e0e-138">Du bör ha en fil med *namnet WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="77e0e-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="77e0e-139">Använd den anpassade konfigurationsprincipen för Microsoft Intune för att distribuera följande OMA-URI-inställningar som stöds.</span><span class="sxs-lookup"><span data-stu-id="77e0e-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="77e0e-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="77e0e-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="77e0e-141">Datumtyp: Sträng</span><span class="sxs-lookup"><span data-stu-id="77e0e-141">Date type: String</span></span><br/>
      <span data-ttu-id="77e0e-142">Värde: [Kopiera och klistra in värdet från innehållet i WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="77e0e-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="77e0e-143">Mer information om Inställningar för Microsoft Intune-princip finns i [Principinställningar för Windows 10 i Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="77e0e-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="77e0e-144">Principen **Hälsostatus för offboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="77e0e-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77e0e-145">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="77e0e-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77e0e-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="77e0e-146">Related topics</span></span>
- [<span data-ttu-id="77e0e-147">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="77e0e-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="77e0e-148">Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77e0e-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="77e0e-149">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="77e0e-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="77e0e-150">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="77e0e-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="77e0e-151">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="77e0e-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="77e0e-152">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="77e0e-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
