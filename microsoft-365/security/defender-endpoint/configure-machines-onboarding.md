---
title: Få enheter skickade till Microsoft Defender för Endpoint
description: Spåra registrering av Intune-hanterade enheter i Microsoft Defender för Endpoint och öka introduktionshastigheten.
keywords: onboard, Intune-hantering, Microsoft Defender för Slutpunkt, Microsoft Defender, Windows Defender, konfigurationshantering
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
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841576"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="233ba-104">Få enheter skickade till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="233ba-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="233ba-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="233ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="233ba-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="233ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="233ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="233ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="233ba-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="233ba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="233ba-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="233ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="233ba-110">Varje onboarded-enhet lägger till ytterligare identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt) sensor och ökar synligheten för intrångsaktivitet i nätverket.</span><span class="sxs-lookup"><span data-stu-id="233ba-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="233ba-111">Onboarding ser också till att en enhet kan kontrolleras för sårbara komponenter och problem med säkerhetskonfigurationen och kan ta emot kritiska åtgärdsåtgärder under attacker.</span><span class="sxs-lookup"><span data-stu-id="233ba-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="233ba-112">Innan du kan spåra och hantera registrering av enheter:</span><span class="sxs-lookup"><span data-stu-id="233ba-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="233ba-113">Registrera dina enheter till Intune-hantering</span><span class="sxs-lookup"><span data-stu-id="233ba-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="233ba-114">Kontrollera att du har de behörigheter som krävs</span><span class="sxs-lookup"><span data-stu-id="233ba-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="233ba-115">Hitta och spåra oskyddade enheter</span><span class="sxs-lookup"><span data-stu-id="233ba-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="233ba-116">**Onboarding-kortet** ger en översikt över din registreringshastighet genom att jämföra antalet Windows 10-enheter som faktiskt har onboarded to Defender för Endpoint med det totala antalet Intune-hanterade Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="233ba-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="233ba-117">![Onboarding-kort för hantering av enhetskonfiguration](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="233ba-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="233ba-118">*Kort som visar onboarded-enheter jämfört med det totala antalet Intune-hanterade Windows 10 enheter*</span><span class="sxs-lookup"><span data-stu-id="233ba-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="233ba-119">Om du använde Säkerhetscenter Configuration Manager, onboarding-skriptet eller andra onboarding-metoder som inte använder Intune-profiler kan det uppstå dataavvikheter.</span><span class="sxs-lookup"><span data-stu-id="233ba-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="233ba-120">Om du vill lösa de här avvikelserna skapar du en motsvarande Intune-konfigurationsprofil för Defender för slutpunkts onboarding och tilldelar den profilen till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="233ba-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="233ba-121">Introducera fler enheter med Intune-profiler</span><span class="sxs-lookup"><span data-stu-id="233ba-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="233ba-122">Defender för Endpoint innehåller flera praktiska alternativ för [att Windows 10 -enheter.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="233ba-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="233ba-123">För Intune-hanterade enheter kan du använda Intune-profiler för att enkelt distribuera Defender för Slutpunkts sensor för att välja enheter, vilket effektivt introduktions av dessa enheter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="233ba-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="233ba-124">På **introduktionskortet** väljer du **Onboard more devices för** att skapa och tilldela en profil i Intune.</span><span class="sxs-lookup"><span data-stu-id="233ba-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="233ba-125">Länken tar dig till sidan enhetsefterlevnad på Intune, som ger en liknande översikt över din registrering.</span><span class="sxs-lookup"><span data-stu-id="233ba-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="233ba-126">![Sidan Microsoft Defender för Slutpunktens enhetsefterlevnad på Intune-enhetshantering](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="233ba-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="233ba-127">*Sidan Microsoft Defender för Slutpunktens enhetsefterlevnad på Intune-enhetshantering*</span><span class="sxs-lookup"><span data-stu-id="233ba-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="233ba-128">Alternativt kan du gå till sidan Defender för slutpunktsefterlevnad för registrering av slutpunkt i [Microsoft Azure-portalen](https://portal.azure.com/) från Alla tjänster **> Intune > enhetsefterlevnad > Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="233ba-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="233ba-129">Om du vill visa de senaste enhetsdata klickar du på Lista över **enheter utan ATP-sensor**.</span><span class="sxs-lookup"><span data-stu-id="233ba-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="233ba-130">På sidan för enhetsefterlevnad skapar du en konfigurationsprofil specifikt för distributionen av Defender för slutpunkts sensor och tilldelar den profilen till de enheter som du vill registrera.</span><span class="sxs-lookup"><span data-stu-id="233ba-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="233ba-131">Det kan du göra genom att antingen:</span><span class="sxs-lookup"><span data-stu-id="233ba-131">To do this, you can either:</span></span>

- <span data-ttu-id="233ba-132">Välj **Skapa en profil för enhetskonfiguration om du vill konfigurera ATP-sensorn** så att den börjar med en fördefinierad enhetskonfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="233ba-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="233ba-133">Skapa profilen för enhetskonfiguration från grunden.</span><span class="sxs-lookup"><span data-stu-id="233ba-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="233ba-134">Mer information finns i [om hur du använder konfigurationsprofiler för Intune-enheter för att registrera enheter i Defender för slutpunkt.](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="233ba-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="233ba-135">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="233ba-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="233ba-136">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="233ba-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="233ba-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="233ba-137">Related topics</span></span>
- [<span data-ttu-id="233ba-138">Se till att dina enheter är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="233ba-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="233ba-139">Öka efterlevnad för Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="233ba-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="233ba-140">Optimera ASR-regeldistribution och identifiering</span><span class="sxs-lookup"><span data-stu-id="233ba-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
