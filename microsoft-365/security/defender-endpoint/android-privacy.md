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
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694347"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="cd26b-104">Microsoft Defender för Endpoint för Android – Sekretessinformation</span><span class="sxs-lookup"><span data-stu-id="cd26b-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="cd26b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cd26b-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd26b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cd26b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cd26b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd26b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cd26b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cd26b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd26b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cd26b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="cd26b-110">Defender för slutpunkt på Android samlar in information från dina konfigurerade Android-enheter och lagrar den i samma klientorganisation där du har Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="cd26b-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="cd26b-111">Informationen samlas in för att hålla Defender för Endpoint för Android säker, uppdaterad och fungerar som förväntat, och för att stödja tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cd26b-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="cd26b-112">Mer information om datalagring finns i [Microsoft Defender för Slutpunktens datalagring och sekretess.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="cd26b-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="cd26b-113">Information samlas in för att hålla Defender för Endpoint för Android säkert och uppdaterat så att det fungerar som förväntat och för att stödja tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cd26b-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

<span data-ttu-id="cd26b-114">Mer information om de flesta vanliga sekretessfrågor om Microsoft Defender för slutpunkt på mobila enheter med Android och iOS finns i Microsoft Defender för Slutpunkt och sekretess på mobila [enheter med Android och iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)</span><span class="sxs-lookup"><span data-stu-id="cd26b-114">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="cd26b-115">Data som krävs</span><span class="sxs-lookup"><span data-stu-id="cd26b-115">Required Data</span></span> 

<span data-ttu-id="cd26b-116">Data som krävs består av data som krävs för att Defender för Slutpunkt för Android ska fungera som förväntat.</span><span class="sxs-lookup"><span data-stu-id="cd26b-116">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="cd26b-117">Dessa data är viktiga för att tjänsten ska kunna användas och kan innehålla data relaterade till slutanvändare, organisation, enhet och appar.</span><span class="sxs-lookup"><span data-stu-id="cd26b-117">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="cd26b-118">Här är en lista över de typer av data som samlas in:</span><span class="sxs-lookup"><span data-stu-id="cd26b-118">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="cd26b-119">Appinformation</span><span class="sxs-lookup"><span data-stu-id="cd26b-119">App information</span></span>

<span data-ttu-id="cd26b-120">Information om **skadliga** Android-programpaket (APKs) på enheten, inklusive</span><span class="sxs-lookup"><span data-stu-id="cd26b-120">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="cd26b-121">Installera källa</span><span class="sxs-lookup"><span data-stu-id="cd26b-121">Install source</span></span>
-  <span data-ttu-id="cd26b-122">Storage sökväg (sökväg) till APK</span><span class="sxs-lookup"><span data-stu-id="cd26b-122">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="cd26b-123">Tid för installation, storlek på APK och behörigheter</span><span class="sxs-lookup"><span data-stu-id="cd26b-123">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="cd26b-124">Webbsida/nätverksinformation</span><span class="sxs-lookup"><span data-stu-id="cd26b-124">Web page / Network information</span></span>

- <span data-ttu-id="cd26b-125">Fullständig URL för webbplatsen endast när en skadlig anslutning eller webbsida identifieras.</span><span class="sxs-lookup"><span data-stu-id="cd26b-125">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="cd26b-126">Anslutningsinformation</span><span class="sxs-lookup"><span data-stu-id="cd26b-126">Connection information</span></span>
- <span data-ttu-id="cd26b-127">Protokolltyp (till exempel HTTP, HTTPS osv.)</span><span class="sxs-lookup"><span data-stu-id="cd26b-127">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="cd26b-128">Enhet och kontoinformation</span><span class="sxs-lookup"><span data-stu-id="cd26b-128">Device and account information</span></span>

- <span data-ttu-id="cd26b-129">Enhetsinformation som datum & tid, Android-version, OEM-modell, CPU-information och enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="cd26b-129">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="cd26b-130">Enhetsidentifierare är något av följande:</span><span class="sxs-lookup"><span data-stu-id="cd26b-130">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="cd26b-131">Wi-Fi mac-adapteradress</span><span class="sxs-lookup"><span data-stu-id="cd26b-131">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="cd26b-132">[Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (som genereras av Android vid första starten av enheten)</span><span class="sxs-lookup"><span data-stu-id="cd26b-132">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="cd26b-133">Slumpmässigt genererad globalt unik identifierare (GUID)</span><span class="sxs-lookup"><span data-stu-id="cd26b-133">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="cd26b-134">Information om klientorganisation, enhet och användare</span><span class="sxs-lookup"><span data-stu-id="cd26b-134">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="cd26b-135">Azure Active Directory (AD) Enhets-ID och Azure Användar-ID: Unikt identifierar enheten respektive användaren i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd26b-135">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="cd26b-136">Azure-klientorganisations-ID – GUID som identifierar organisationen Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cd26b-136">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="cd26b-137">Microsoft Defender för slutpunktens organisations-ID – Unikt ID som associeras med företaget som enheten tillhör.</span><span class="sxs-lookup"><span data-stu-id="cd26b-137">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="cd26b-138">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda företag och hur många företag som påverkas</span><span class="sxs-lookup"><span data-stu-id="cd26b-138">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="cd26b-139">User Principal Name – Användarens e-post-ID</span><span class="sxs-lookup"><span data-stu-id="cd26b-139">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="cd26b-140">Användningsdata för produkter och tjänster</span><span class="sxs-lookup"><span data-stu-id="cd26b-140">Product and service usage data</span></span>

<span data-ttu-id="cd26b-141">Följande information samlas endast in för appen Microsoft Defender för slutpunkt som är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="cd26b-141">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="cd26b-142">Information om programpaket, inklusive namn, version och appuppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="cd26b-142">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="cd26b-143">Åtgärder som utförs i appen</span><span class="sxs-lookup"><span data-stu-id="cd26b-143">Actions performed in the app</span></span>

-   <span data-ttu-id="cd26b-144">Information om identifiering av hot, till exempel namn på hot, kategori osv.</span><span class="sxs-lookup"><span data-stu-id="cd26b-144">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="cd26b-145">Kraschrapportloggar som genererats av Android</span><span class="sxs-lookup"><span data-stu-id="cd26b-145">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="cd26b-146">Valfria data</span><span class="sxs-lookup"><span data-stu-id="cd26b-146">Optional Data</span></span>

<span data-ttu-id="cd26b-147">Valfria data omfattar diagnostikdata och feedbackdata.</span><span class="sxs-lookup"><span data-stu-id="cd26b-147">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="cd26b-148">Valfria diagnostikdata är ytterligare data som ligger till grund för produktförbättringar och ger förbättrad information som hjälper oss att upptäcka, diagnostisera och åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="cd26b-148">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="cd26b-149">Valfria diagnostikdata omfattar:</span><span class="sxs-lookup"><span data-stu-id="cd26b-149">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="cd26b-150">App-, CPU- och nätverksanvändning</span><span class="sxs-lookup"><span data-stu-id="cd26b-150">App, CPU, and network usage</span></span>

-   <span data-ttu-id="cd26b-151">Status för enheten ur appperspektiv, inklusive genomsökningsstatus, tidsinställningar för skanning, beviljad appbehörighet och uppgraderingsstatus</span><span class="sxs-lookup"><span data-stu-id="cd26b-151">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="cd26b-152">Funktioner som konfigurerats av administratören</span><span class="sxs-lookup"><span data-stu-id="cd26b-152">Features configured by the admin</span></span>

-   <span data-ttu-id="cd26b-153">Grundläggande information om webbläsare på enheten</span><span class="sxs-lookup"><span data-stu-id="cd26b-153">Basic information about the browsers on the device</span></span>

<span data-ttu-id="cd26b-154">**Feedbackdata** samlas in via feedback som ges av användaren i appen</span><span class="sxs-lookup"><span data-stu-id="cd26b-154">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="cd26b-155">Användarens e-postadress, om han eller hon väljer att ange den</span><span class="sxs-lookup"><span data-stu-id="cd26b-155">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="cd26b-156">Feedbacktyp (leende, bägare, idé) och eventuella feedbackkommentarer som skickats in av användaren</span><span class="sxs-lookup"><span data-stu-id="cd26b-156">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
