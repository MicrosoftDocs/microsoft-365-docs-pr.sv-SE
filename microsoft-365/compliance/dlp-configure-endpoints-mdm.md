---
title: Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter
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
description: Använd verktyg för hantering av mobila enheter för att distribuera konfigurationspaketet på enheter så att de kan kommas in i tjänsten.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162010"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="1d7ee-103">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="1d7ee-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="1d7ee-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1d7ee-104">**Applies to:**</span></span>

- [<span data-ttu-id="1d7ee-105">Microsoft 365 Dataförlustskydd i slutpunkt (DLP)</span><span class="sxs-lookup"><span data-stu-id="1d7ee-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="1d7ee-106">Du kan använda MDM-lösningar (Mobile Device Management) för att konfigurera enheter.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="1d7ee-107">Microsoft 365 Dataförlustskydd i slutpunkten stöder MDM genom att tillhandahålla OMA-URIs att skapa principer för hantering av enheter.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="1d7ee-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1d7ee-108">Before you begin</span></span>
<span data-ttu-id="1d7ee-109">Om du använder Microsoft Intune måste enheten MDM vara registrerad.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="1d7ee-110">Annars kommer inställningarna inte att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="1d7ee-111">Mer information om hur du aktiverar MDM med Microsoft Intune finns i [Enhetsregistrering (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="1d7ee-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="1d7ee-112">Onboard-enheter som använder Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1d7ee-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="1d7ee-113">Följ instruktionerna från [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="1d7ee-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="1d7ee-114">Principen **Hälsostatus för onboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="1d7ee-115">Offboard och övervaka enheter med hjälp av verktyg för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="1d7ee-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="1d7ee-116">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="1d7ee-117">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="1d7ee-118">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="1d7ee-119">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="1d7ee-120">Hämta offboarding-paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1d7ee-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="1d7ee-121">I navigeringsfönstret väljer du **Inställningar**  >  **Avboarding av**  >  **enheten.**</span><span class="sxs-lookup"><span data-stu-id="1d7ee-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="1d7ee-122">I fältet **Distributionsmetod** väljer du **Hantering av mobila enheter /Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="1d7ee-123">Klicka **på Ladda** ned paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="1d7ee-124">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="1d7ee-125">Du bör ha en fil med *namnet DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="1d7ee-126">Använd den Microsoft Intune konfigurationsprincipen för att distribuera följande OMA-URI-inställningar som stöds.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="1d7ee-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="1d7ee-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="1d7ee-128">Datumtyp: Sträng</span><span class="sxs-lookup"><span data-stu-id="1d7ee-128">Date type: String</span></span>      
      <span data-ttu-id="1d7ee-129">Värde: [Kopiera och klistra in värdet från innehållet i DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="1d7ee-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="1d7ee-130">Mer information om Microsoft Intune finns i ändra [Windows 10 principinställningar i Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="1d7ee-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="1d7ee-131">Principen **Hälsostatus för offboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d7ee-132">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="1d7ee-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d7ee-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1d7ee-133">Related topics</span></span>
- [<span data-ttu-id="1d7ee-134">Introducera Windows 10 enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="1d7ee-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="1d7ee-135">Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1d7ee-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="1d7ee-136">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="1d7ee-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="1d7ee-137">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="1d7ee-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="1d7ee-138">Felsöka Microsoft Defender Avancerat skydd onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="1d7ee-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)