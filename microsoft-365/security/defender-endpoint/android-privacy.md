---
title: Microsoft Defender för Endpoint för Android – Sekretessinformation
description: Sekretesskontroller, hur du konfigurerar principinställningar som påverkar sekretess och information om diagnostikdata som samlas in i Microsoft Defender för slutpunkt på Android.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, android, sekretess, diagnostik
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
ms.openlocfilehash: 415a1f555e1a33c103894221086b783aa754cf32
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930143"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="a6226-104">Microsoft Defender för Endpoint för Android – Sekretessinformation</span><span class="sxs-lookup"><span data-stu-id="a6226-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="a6226-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a6226-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6226-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6226-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6226-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6226-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a6226-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a6226-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a6226-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a6226-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="a6226-110">Defender för slutpunkt på Android samlar in information från dina konfigurerade Android-enheter och lagrar den i samma klientorganisation där du har Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="a6226-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="a6226-111">Informationen samlas in för att hålla Defender för Endpoint för Android säker, uppdaterad och fungerar som förväntat, och för att stödja tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a6226-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="a6226-112">Mer information om datalagring finns i [Microsoft Defender för Slutpunktens datalagring och sekretess.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="a6226-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="a6226-113">Information samlas in för att hålla Defender för Endpoint för Android säkert och uppdaterat så att det fungerar som förväntat och för att stödja tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a6226-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="a6226-114">Data som krävs</span><span class="sxs-lookup"><span data-stu-id="a6226-114">Required Data</span></span> 

<span data-ttu-id="a6226-115">Data som krävs består av data som krävs för att Defender för Slutpunkt för Android ska fungera som förväntat.</span><span class="sxs-lookup"><span data-stu-id="a6226-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="a6226-116">Dessa data är viktiga för att tjänsten ska kunna användas och kan innehålla data relaterade till slutanvändare, organisation, enhet och appar.</span><span class="sxs-lookup"><span data-stu-id="a6226-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="a6226-117">Här är en lista över de typer av data som samlas in:</span><span class="sxs-lookup"><span data-stu-id="a6226-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="a6226-118">Appinformation</span><span class="sxs-lookup"><span data-stu-id="a6226-118">App information</span></span>

<span data-ttu-id="a6226-119">Information om **skadliga** Android-programpaket (APKs) på enheten, inklusive</span><span class="sxs-lookup"><span data-stu-id="a6226-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="a6226-120">Installera källa</span><span class="sxs-lookup"><span data-stu-id="a6226-120">Install source</span></span>
-  <span data-ttu-id="a6226-121">Lagringsplats (sökväg) för APK</span><span class="sxs-lookup"><span data-stu-id="a6226-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="a6226-122">Tid för installation, storlek på APK och behörigheter</span><span class="sxs-lookup"><span data-stu-id="a6226-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="a6226-123">Webbsida/nätverksinformation</span><span class="sxs-lookup"><span data-stu-id="a6226-123">Web page / Network information</span></span>

- <span data-ttu-id="a6226-124">Fullständig URL för webbplatsen endast när en skadlig anslutning eller webbsida identifieras.</span><span class="sxs-lookup"><span data-stu-id="a6226-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="a6226-125">Anslutningsinformation</span><span class="sxs-lookup"><span data-stu-id="a6226-125">Connection information</span></span>
- <span data-ttu-id="a6226-126">Protokolltyp (till exempel HTTP, HTTPS osv.)</span><span class="sxs-lookup"><span data-stu-id="a6226-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="a6226-127">Enhet och kontoinformation</span><span class="sxs-lookup"><span data-stu-id="a6226-127">Device and account information</span></span>

- <span data-ttu-id="a6226-128">Enhetsinformation som datum & tid, Android-version, OEM-modell, CPU-information och enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="a6226-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="a6226-129">Enhetsidentifierare är något av följande:</span><span class="sxs-lookup"><span data-stu-id="a6226-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="a6226-130">Wi-Fi mac-adapteradress</span><span class="sxs-lookup"><span data-stu-id="a6226-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="a6226-131">[Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (som genereras av Android vid första starten av enheten)</span><span class="sxs-lookup"><span data-stu-id="a6226-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="a6226-132">Slumpmässigt genererad globalt unik identifierare (GUID)</span><span class="sxs-lookup"><span data-stu-id="a6226-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="a6226-133">Information om klientorganisation, enhet och användare</span><span class="sxs-lookup"><span data-stu-id="a6226-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="a6226-134">Enhets-ID för Azure Active Directory (AD) och Azure Användar-ID: Identifierar enheten, respektive användaren vid Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a6226-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="a6226-135">Azure-klientorganisations-ID – GUID som identifierar organisationen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a6226-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="a6226-136">Organisations-ID för Microsoft Defender ATP – Unikt ID associerat med företaget som enheten tillhör.</span><span class="sxs-lookup"><span data-stu-id="a6226-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="a6226-137">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda företag och hur många företag som påverkas</span><span class="sxs-lookup"><span data-stu-id="a6226-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="a6226-138">User Principal Name – Användarens e-post-ID</span><span class="sxs-lookup"><span data-stu-id="a6226-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="a6226-139">Användningsdata för produkter och tjänster</span><span class="sxs-lookup"><span data-stu-id="a6226-139">Product and service usage data</span></span>

<span data-ttu-id="a6226-140">Följande information samlas endast in för appen Microsoft Defender för slutpunkt som är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="a6226-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="a6226-141">Information om programpaket, inklusive namn, version och appuppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="a6226-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="a6226-142">Åtgärder som utförs i appen</span><span class="sxs-lookup"><span data-stu-id="a6226-142">Actions performed in the app</span></span>

-   <span data-ttu-id="a6226-143">Information om identifiering av hot, till exempel namn på hot, kategori osv.</span><span class="sxs-lookup"><span data-stu-id="a6226-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="a6226-144">Kraschrapportloggar som genererats av Android</span><span class="sxs-lookup"><span data-stu-id="a6226-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="a6226-145">Valfria data</span><span class="sxs-lookup"><span data-stu-id="a6226-145">Optional Data</span></span>

<span data-ttu-id="a6226-146">Valfria data omfattar diagnostikdata och feedbackdata.</span><span class="sxs-lookup"><span data-stu-id="a6226-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="a6226-147">Valfria diagnostikdata är ytterligare data som ligger till grund för produktförbättringar och ger förbättrad information som hjälper oss att upptäcka, diagnostisera och åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="a6226-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="a6226-148">Valfria diagnostikdata omfattar:</span><span class="sxs-lookup"><span data-stu-id="a6226-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="a6226-149">App-, CPU- och nätverksanvändning</span><span class="sxs-lookup"><span data-stu-id="a6226-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="a6226-150">Status för enheten ur appperspektiv, inklusive genomsökningsstatus, tidsinställningar för skanning, beviljad appbehörighet och uppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="a6226-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="a6226-151">Funktioner som konfigurerats av administratören</span><span class="sxs-lookup"><span data-stu-id="a6226-151">Features configured by the admin</span></span>

-   <span data-ttu-id="a6226-152">Grundläggande information om webbläsare på enheten</span><span class="sxs-lookup"><span data-stu-id="a6226-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="a6226-153">**Feedbackdata** samlas in via feedback som ges av användaren i appen</span><span class="sxs-lookup"><span data-stu-id="a6226-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="a6226-154">Användarens e-postadress, om han eller hon väljer att ange den</span><span class="sxs-lookup"><span data-stu-id="a6226-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="a6226-155">Feedbacktyp (leende, bägare, idé) och eventuella feedbackkommentarer som skickats in av användaren</span><span class="sxs-lookup"><span data-stu-id="a6226-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
