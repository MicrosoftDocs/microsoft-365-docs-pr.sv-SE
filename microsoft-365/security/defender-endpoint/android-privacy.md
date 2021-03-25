---
title: Microsoft Defender ATP för Android – information om sekretess
description: Sekretesskontroller, hur du konfigurerar principinställningar som påverkar sekretess och information om diagnostikdata som samlas in i Microsoft Defender ATP för Android.
keywords: microsoft, defender, atp, android, sekretess, diagnostik
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: abb22b2e733d1e40bd4f2733ef2d25767c69ccf7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163333"
---
#  <a name="microsoft-defender-for-endpoint-for-android---privacy-information"></a><span data-ttu-id="7754c-104">Microsoft Defender för slutpunkt för Android – information om sekretess</span><span class="sxs-lookup"><span data-stu-id="7754c-104">Microsoft Defender for Endpoint for Android - Privacy information</span></span>

<span data-ttu-id="7754c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7754c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7754c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7754c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7754c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7754c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7754c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7754c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7754c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7754c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="7754c-110">Defender för slutpunkt för Android samlar in information från dina konfigurerade Android-enheter och lagrar den i samma klientorganisation där du har Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7754c-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="7754c-111">Information samlas in för att hålla Defender för Endpoint för Android säkert och uppdaterat så att det fungerar som förväntat och för att stödja tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7754c-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="7754c-112">Data som krävs</span><span class="sxs-lookup"><span data-stu-id="7754c-112">Required Data</span></span> 

<span data-ttu-id="7754c-113">Data som krävs består av data som krävs för att Defender för Slutpunkt för Android ska fungera som förväntat.</span><span class="sxs-lookup"><span data-stu-id="7754c-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="7754c-114">Dessa data är viktiga för att tjänsten ska kunna användas och kan innehålla data relaterade till slutanvändare, organisation, enhet och appar.</span><span class="sxs-lookup"><span data-stu-id="7754c-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="7754c-115">Här är en lista över de typer av data som samlas in:</span><span class="sxs-lookup"><span data-stu-id="7754c-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="7754c-116">Appinformation</span><span class="sxs-lookup"><span data-stu-id="7754c-116">App information</span></span>

<span data-ttu-id="7754c-117">Information om Android-programpaket (APKs) på enheten, inklusive</span><span class="sxs-lookup"><span data-stu-id="7754c-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="7754c-118">Installera källa</span><span class="sxs-lookup"><span data-stu-id="7754c-118">Install source</span></span>
-  <span data-ttu-id="7754c-119">Lagringsplats (sökväg) för APK</span><span class="sxs-lookup"><span data-stu-id="7754c-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="7754c-120">Tid för installation, storlek på APK och behörigheter</span><span class="sxs-lookup"><span data-stu-id="7754c-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="7754c-121">Webbsida/nätverksinformation</span><span class="sxs-lookup"><span data-stu-id="7754c-121">Web page / Network information</span></span>

- <span data-ttu-id="7754c-122">Fullständig URL (på webbläsare som stöds), vid klickning</span><span class="sxs-lookup"><span data-stu-id="7754c-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="7754c-123">Anslutningsinformation</span><span class="sxs-lookup"><span data-stu-id="7754c-123">Connection information</span></span>
- <span data-ttu-id="7754c-124">Protokolltyp (till exempel HTTP, HTTPS osv.)</span><span class="sxs-lookup"><span data-stu-id="7754c-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="7754c-125">Enhet och kontoinformation</span><span class="sxs-lookup"><span data-stu-id="7754c-125">Device and account information</span></span>

- <span data-ttu-id="7754c-126">Enhetsinformation som datum & tid, Android-version, OEM-modell, CPU-information och enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="7754c-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="7754c-127">Enhetsidentifierare är något av följande:</span><span class="sxs-lookup"><span data-stu-id="7754c-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="7754c-128">Wi-Fi mac-adapteradress</span><span class="sxs-lookup"><span data-stu-id="7754c-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="7754c-129">[Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (som genereras av Android vid första starten av enheten)</span><span class="sxs-lookup"><span data-stu-id="7754c-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="7754c-130">Slumpmässigt genererad globalt unik identifierare (GUID)</span><span class="sxs-lookup"><span data-stu-id="7754c-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="7754c-131">Information om klientorganisation, enhet och användare</span><span class="sxs-lookup"><span data-stu-id="7754c-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="7754c-132">Enhets-ID för Azure Active Directory (AD) och Azure Användar-ID: Identifierar enheten, respektive användaren vid Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7754c-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="7754c-133">Azure-klientorganisations-ID – GUID som identifierar organisationen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7754c-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="7754c-134">Organisations-ID för Microsoft Defender ATP – Unikt ID associerat med företaget som enheten tillhör.</span><span class="sxs-lookup"><span data-stu-id="7754c-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="7754c-135">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda företag och hur många företag som påverkas</span><span class="sxs-lookup"><span data-stu-id="7754c-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="7754c-136">User Principal Name – Användarens e-post-ID</span><span class="sxs-lookup"><span data-stu-id="7754c-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="7754c-137">Användningsdata för produkter och tjänster</span><span class="sxs-lookup"><span data-stu-id="7754c-137">Product and service usage data</span></span>
-   <span data-ttu-id="7754c-138">Information om programpaket, inklusive namn, version och appuppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="7754c-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="7754c-139">Åtgärder som utförs i appen</span><span class="sxs-lookup"><span data-stu-id="7754c-139">Actions performed in the app</span></span>

-   <span data-ttu-id="7754c-140">Information om identifiering av hot, till exempel namn på hot, kategori osv.</span><span class="sxs-lookup"><span data-stu-id="7754c-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="7754c-141">Kraschrapportloggar som genererats av Android</span><span class="sxs-lookup"><span data-stu-id="7754c-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="7754c-142">Valfria data</span><span class="sxs-lookup"><span data-stu-id="7754c-142">Optional Data</span></span>

<span data-ttu-id="7754c-143">Valfria data omfattar diagnostikdata och feedbackdata.</span><span class="sxs-lookup"><span data-stu-id="7754c-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="7754c-144">Valfria diagnostikdata är ytterligare data som ligger till grund för produktförbättringar och ger förbättrad information som hjälper oss att upptäcka, diagnostisera och åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="7754c-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="7754c-145">Valfria diagnostikdata omfattar:</span><span class="sxs-lookup"><span data-stu-id="7754c-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="7754c-146">App-, CPU- och nätverksanvändning</span><span class="sxs-lookup"><span data-stu-id="7754c-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="7754c-147">Status för enheten ur appperspektiv, inklusive genomsökningsstatus, tidsinställningar för skanning, beviljad appbehörighet och uppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="7754c-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="7754c-148">Funktioner som konfigurerats av administratören</span><span class="sxs-lookup"><span data-stu-id="7754c-148">Features configured by the admin</span></span>

-   <span data-ttu-id="7754c-149">Grundläggande information om webbläsare på enheten</span><span class="sxs-lookup"><span data-stu-id="7754c-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="7754c-150">**Feedbackdata** samlas in via feedback som ges av användaren i appen</span><span class="sxs-lookup"><span data-stu-id="7754c-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="7754c-151">Användarens e-postadress, om han eller hon väljer att ange den</span><span class="sxs-lookup"><span data-stu-id="7754c-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="7754c-152">Feedbacktyp (leende, bägare, idé) och eventuella feedbackkommentarer som skickats in av användaren</span><span class="sxs-lookup"><span data-stu-id="7754c-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
