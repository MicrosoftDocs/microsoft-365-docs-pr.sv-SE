---
title: Introducera icke-Windows-enheter till Microsoft Defender för slutpunktstjänsten
description: Konfigurera enheter som Windows enheter så att de kan skicka sensordata till Microsoft Defender för slutpunktstjänsten.
keywords: onboard non-Windows-enheter, macos, linux, enhetshantering, konfigurera Microsoft Defender för slutpunktsenheter
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
ms.openlocfilehash: 265a7e9093638caa2111c7d1d82e51c8c2437d12
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845468"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="f8547-104">Introducera icke-Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="f8547-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8547-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f8547-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8547-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8547-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8547-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8547-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f8547-108">**Plattformar**</span><span class="sxs-lookup"><span data-stu-id="f8547-108">**Platforms**</span></span>
- <span data-ttu-id="f8547-109">macOS</span><span class="sxs-lookup"><span data-stu-id="f8547-109">macOS</span></span>
- <span data-ttu-id="f8547-110">Linux</span><span class="sxs-lookup"><span data-stu-id="f8547-110">Linux</span></span>

><span data-ttu-id="f8547-111">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f8547-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f8547-112">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f8547-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="f8547-113">Defender för Endpoint tillhandahåller en centraliserad säkerhetsoperationer för både Windows och icke-Windows plattformar.</span><span class="sxs-lookup"><span data-stu-id="f8547-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="f8547-114">Du kan se aviseringar från olika operativsystem som stöds (OS) i Microsoft Defender Säkerhetscenter och bättre skydda organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="f8547-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="f8547-115">Du måste känna till exakt vilka Linux-distributioner och macOS-versioner som är kompatibla med Defender för Endpoint för att integreringen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="f8547-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="f8547-116">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="f8547-116">For more information, see:</span></span>
- [<span data-ttu-id="f8547-117">Systemkrav för Microsoft Defender för Slutpunkt på Linux</span><span class="sxs-lookup"><span data-stu-id="f8547-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="f8547-118">[Microsoft Defender för Slutpunkt på systemkrav för macOS](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="f8547-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="f8547-119">Onboarding non-Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="f8547-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="f8547-120">Du måste vidta följande steg för att registrera icke-Windows enheter:</span><span class="sxs-lookup"><span data-stu-id="f8547-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="f8547-121">Välj önskad onboardingmetod:</span><span class="sxs-lookup"><span data-stu-id="f8547-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="f8547-122">För macOS-enheter kan du välja att registrera dig via Microsoft Defender för Endpoint eller via en tredjepartslösning.</span><span class="sxs-lookup"><span data-stu-id="f8547-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="f8547-123">Mer information finns i [Microsoft Defender för slutpunkt på Mac.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="f8547-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="f8547-124">För andra enheter som Windows enheter väljer **du Onboard icke-Windows-enheter via tredjepartsintegrering.**</span><span class="sxs-lookup"><span data-stu-id="f8547-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="f8547-125">Välj Partner med **interoperabilitet i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="f8547-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="f8547-126">Kontrollera att tredjepartslösningen visas.</span><span class="sxs-lookup"><span data-stu-id="f8547-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="f8547-127">På fliken **Partnerprogram** väljer du den partner som stöder dina icke-Windows enheter.</span><span class="sxs-lookup"><span data-stu-id="f8547-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="f8547-128">Välj **Öppna partnersida** för att öppna partnerns sida.</span><span class="sxs-lookup"><span data-stu-id="f8547-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="f8547-129">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="f8547-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="f8547-130">När du har skapat ett konto eller prenumererat på partnerlösningen bör du komma till ett steg där en global administratör för klientorganisationen i organisationen uppmanas att acceptera en begäran om behörighet från partnerprogrammet.</span><span class="sxs-lookup"><span data-stu-id="f8547-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="f8547-131">Läs begäran om behörighet noga så att den stämmer överens med den tjänst du kräver.</span><span class="sxs-lookup"><span data-stu-id="f8547-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="f8547-132">Kör ett identifieringstest genom att följa anvisningarna för tredjepartslösningen.</span><span class="sxs-lookup"><span data-stu-id="f8547-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="f8547-133">Offboard-enheter som Windows enheter</span><span class="sxs-lookup"><span data-stu-id="f8547-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="f8547-134">Följ dokumentationen från tredje part för att koppla bort tredjepartslösningen från Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f8547-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="f8547-135">Ta bort behörigheter för tredjepartslösningen i Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f8547-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="f8547-136">Logga in på [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f8547-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="f8547-137">Välj **Azure Active Directory > Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="f8547-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="f8547-138">Välj det program du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="f8547-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="f8547-139">Välj knappen **Ta** bort.</span><span class="sxs-lookup"><span data-stu-id="f8547-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f8547-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f8547-140">Related topics</span></span>
- [<span data-ttu-id="f8547-141">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="f8547-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="f8547-142">Onboard servers</span><span class="sxs-lookup"><span data-stu-id="f8547-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="f8547-143">Konfigurera inställningar för proxy- och Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="f8547-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="f8547-144">Felsökning av problem med introduktion till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f8547-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
