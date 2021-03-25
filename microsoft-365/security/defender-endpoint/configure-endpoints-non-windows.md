---
title: Introducera enheter som inte är Windows-enheter i Microsoft Defender för slutpunktstjänsten
description: Konfigurera enheter som inte är Windows-enheter så att de kan skicka sensordata till Microsoft Defender ATP-tjänsten.
keywords: onboard non-Windows devices, macos, linux, device management, configure Windows ATP devices, configure Microsoft Defender for Endpoint devices
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166083"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="7e8e5-104">Introducera enheter som inte är Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="7e8e5-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7e8e5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7e8e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e8e5-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e8e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7e8e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e8e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7e8e5-108">**Plattformar**</span><span class="sxs-lookup"><span data-stu-id="7e8e5-108">**Platforms**</span></span>
- <span data-ttu-id="7e8e5-109">macOS</span><span class="sxs-lookup"><span data-stu-id="7e8e5-109">macOS</span></span>
- <span data-ttu-id="7e8e5-110">Linux</span><span class="sxs-lookup"><span data-stu-id="7e8e5-110">Linux</span></span>

><span data-ttu-id="7e8e5-111">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7e8e5-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7e8e5-112">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="7e8e5-113">Defender för Endpoint ger en centraliserad säkerhetsoperationer för Windows och för icke-Windows-plattformar.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="7e8e5-114">Du kan se aviseringar från olika operativsystem som stöds (OS) i Microsoft Defender Säkerhetscenter och bättre skydda organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="7e8e5-115">Du måste känna till exakt vilka Linux-distributioner och macOS-versioner som är kompatibla med Defender för Endpoint för att integreringen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="7e8e5-116">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="7e8e5-116">For more information, see:</span></span>
- [<span data-ttu-id="7e8e5-117">Systemkrav för Microsoft Defender för Slutpunkt för Linux</span><span class="sxs-lookup"><span data-stu-id="7e8e5-117">Microsoft Defender for Endpoint for Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="7e8e5-118">[Systemkrav för Microsoft Defender för Endpoint för Mac.](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="7e8e5-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="7e8e5-119">Onboarding icke-Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="7e8e5-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="7e8e5-120">Du måste vidta följande steg för att registrera enheter som inte är Windows:</span><span class="sxs-lookup"><span data-stu-id="7e8e5-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="7e8e5-121">Välj önskad onboardingmetod:</span><span class="sxs-lookup"><span data-stu-id="7e8e5-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="7e8e5-122">För macOS-enheter kan du välja att registrera dig via Microsoft Defender ATP eller via en tredjepartslösning.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="7e8e5-123">Mer information finns i [Microsoft Defender för Slutpunkt för Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)</span><span class="sxs-lookup"><span data-stu-id="7e8e5-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>
   - <span data-ttu-id="7e8e5-124">För andra enheter som inte är **Windows-enheter väljer du Registrera icke-Windows-enheter via tredjepartsintegrering.**</span><span class="sxs-lookup"><span data-stu-id="7e8e5-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
       
     1. <span data-ttu-id="7e8e5-125">Välj Partner med **interoperabilitet i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="7e8e5-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="7e8e5-126">Kontrollera att tredjepartslösningen visas.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-126">Make sure the third-party solution is listed.</span></span>

        2. <span data-ttu-id="7e8e5-127">På fliken **Partnerprogram** väljer du den partner som stöder dina enheter som inte är Windows.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>

        3. <span data-ttu-id="7e8e5-128">Välj **Öppna partnersida** för att öppna partnerns sida.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="7e8e5-129">Följ instruktionerna på sidan.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-129">Follow the instructions provided on the page.</span></span>

        4. <span data-ttu-id="7e8e5-130">När du har skapat ett konto eller prenumererat på partnerlösningen bör du komma till ett steg där en global administratör för klientorganisationen i organisationen uppmanas att acceptera en begäran om behörighet från partnerprogrammet.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="7e8e5-131">Läs begäran om behörighet noga så att den stämmer överens med den tjänst du kräver.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="7e8e5-132">Kör ett identifieringstest genom att följa anvisningarna för tredjepartslösningen.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="7e8e5-133">Offboard-enheter som inte är Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="7e8e5-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="7e8e5-134">Följ dokumentationen från tredje part för att koppla bort tredjepartslösningen från Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="7e8e5-135">Ta bort behörigheter för tredjepartslösningen i Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="7e8e5-136">Logga in på [Azure Portal.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="7e8e5-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="7e8e5-137">Välj **Azure Active Directory > Enterprise Applications.**</span><span class="sxs-lookup"><span data-stu-id="7e8e5-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="7e8e5-138">Välj det program du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="7e8e5-139">Välj knappen **Ta** bort.</span><span class="sxs-lookup"><span data-stu-id="7e8e5-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7e8e5-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7e8e5-140">Related topics</span></span>
- [<span data-ttu-id="7e8e5-141">Introducera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="7e8e5-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="7e8e5-142">Onboard servers</span><span class="sxs-lookup"><span data-stu-id="7e8e5-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="7e8e5-143">Konfigurera proxy- och Internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="7e8e5-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="7e8e5-144">Felsökning av problem med introduktion till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="7e8e5-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
