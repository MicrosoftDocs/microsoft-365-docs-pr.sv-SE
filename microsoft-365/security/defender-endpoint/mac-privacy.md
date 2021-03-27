---
title: Sekretess för Microsoft Defender ATP för Mac
description: Sekretesskontroller, hur du konfigurerar principinställningar som påverkar sekretess och information om diagnostikdata som samlas in i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, sekretess, diagnostik
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1386809778edeb92521a8656e9ece78591a682a4
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382907"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="8336b-104">Sekretess för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="8336b-104">Privacy for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8336b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8336b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8336b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8336b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8336b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8336b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8336b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8336b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8336b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8336b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="8336b-110">Microsoft strävar efter att tillhandahålla den information och de kontroller som du behöver för att göra val kring hur dina data samlas in och används när du använder Microsoft Defender för Endpoint för Mac.</span><span class="sxs-lookup"><span data-stu-id="8336b-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="8336b-111">I det här avsnittet beskrivs vilka sekretesskontroller som är tillgängliga i produkten, hur du hanterar kontrollerna med principinställningar och mer information om datahändelser som samlas in.</span><span class="sxs-lookup"><span data-stu-id="8336b-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="8336b-112">Översikt över sekretesskontroller i Microsoft Defender för Endpoint för Mac</span><span class="sxs-lookup"><span data-stu-id="8336b-112">Overview of privacy controls in Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="8336b-113">I det här avsnittet beskrivs sekretesskontroller för olika typer av data som samlas in av Microsoft Defender för Endpoint för Mac.</span><span class="sxs-lookup"><span data-stu-id="8336b-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="8336b-114">Diagnostikdata</span><span class="sxs-lookup"><span data-stu-id="8336b-114">Diagnostic data</span></span>

<span data-ttu-id="8336b-115">Diagnostikdata används för att hålla Microsoft Defender för Endpoint säkert och uppdaterat, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="8336b-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="8336b-116">Vissa diagnostiska data är obligatoriska, medan andra diagnostiska data är valfria.</span><span class="sxs-lookup"><span data-stu-id="8336b-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="8336b-117">Du kan välja om du vill skicka obligatoriska eller valfria diagnostikdata genom att använda sekretesskontroller, till exempel principinställningar för organisationer.</span><span class="sxs-lookup"><span data-stu-id="8336b-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="8336b-118">Det finns två nivåer av diagnostikdata för Microsoft Defender för endpoint-klientprogramvara som du kan välja bland:</span><span class="sxs-lookup"><span data-stu-id="8336b-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="8336b-119">**Obligatoriskt:** De data som krävs för att hålla Microsoft Defender för Slutpunkt säker, uppdaterad och fungerar som förväntat på den enhet som den är installerad på.</span><span class="sxs-lookup"><span data-stu-id="8336b-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="8336b-120">**Valfritt:** Ytterligare data som hjälper Microsoft göra produktförbättringar och ger förbättrad information som hjälper till att identifiera, diagnostisera och åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="8336b-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="8336b-121">Som standard skickas endast obligatoriska diagnostikdata till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8336b-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="8336b-122">Data för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="8336b-122">Cloud delivered protection data</span></span>

<span data-ttu-id="8336b-123">Moln levererat skydd används för att ge ett bättre och snabbare skydd med tillgång till de senaste skyddsdata i molnet.</span><span class="sxs-lookup"><span data-stu-id="8336b-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="8336b-124">Aktivering av den molnbaserade skyddstjänsten är valfri, men vi rekommenderar starkt att den skyddar mot skadlig programvara på slutpunkter och i nätverket.</span><span class="sxs-lookup"><span data-stu-id="8336b-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="8336b-125">Exempeldata</span><span class="sxs-lookup"><span data-stu-id="8336b-125">Sample data</span></span>

<span data-ttu-id="8336b-126">Exempeldata används för att förbättra skyddsfunktioner i produkten genom att skicka misstänkta exempel till Microsoft så att de kan analyseras.</span><span class="sxs-lookup"><span data-stu-id="8336b-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="8336b-127">Det är valfritt att aktivera automatisk exempelinskickning.</span><span class="sxs-lookup"><span data-stu-id="8336b-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="8336b-128">När den här funktionen är aktiverad och det exempel som samlas in troligen innehåller personlig information uppmanas användaren att ge sitt medgivande.</span><span class="sxs-lookup"><span data-stu-id="8336b-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="8336b-129">Hantera sekretesskontroller med principinställningar</span><span class="sxs-lookup"><span data-stu-id="8336b-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="8336b-130">Om du är IT-administratör kanske du vill konfigurera kontrollerna på företagsnivå.</span><span class="sxs-lookup"><span data-stu-id="8336b-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="8336b-131">Sekretesskontrollerna för de olika typerna av data som beskrivs i föregående avsnitt beskrivs i detalj i Ange inställningar för [Microsoft Defender för Slutpunkt för Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="8336b-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="8336b-132">Precis som med alla nya principinställningar bör du noggrant testa dem i en begränsad, kontrollerad miljö för att säkerställa att de inställningar som du konfigurerar har önskad effekt innan du implementerar principinställningarna i en större utsträckning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8336b-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="8336b-133">Diagnostikdatahändelser</span><span class="sxs-lookup"><span data-stu-id="8336b-133">Diagnostic data events</span></span>

<span data-ttu-id="8336b-134">I det här avsnittet beskrivs vad som krävs för diagnostikdata och vad som betraktas som valfria diagnostikdata, tillsammans med en beskrivning av händelser och fält som samlas in.</span><span class="sxs-lookup"><span data-stu-id="8336b-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="8336b-135">Datafält som är gemensamma för alla händelser</span><span class="sxs-lookup"><span data-stu-id="8336b-135">Data fields that are common for all events</span></span>
<span data-ttu-id="8336b-136">Det finns viss information om händelser som är gemensamma för alla aktiviteter, oavsett kategori eller dataundertyp.</span><span class="sxs-lookup"><span data-stu-id="8336b-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="8336b-137">Följande fält är gemensamma för alla händelser:</span><span class="sxs-lookup"><span data-stu-id="8336b-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="8336b-138">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-138">Field</span></span>                   | <span data-ttu-id="8336b-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="8336b-140">plattform</span><span class="sxs-lookup"><span data-stu-id="8336b-140">platform</span></span>                | <span data-ttu-id="8336b-141">Den breda klassificeringen för den plattform där appen körs.</span><span class="sxs-lookup"><span data-stu-id="8336b-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="8336b-142">Gör att Microsoft kan identifiera på vilka plattformar ett problem kan uppstå så att det kan prioriteras korrekt.</span><span class="sxs-lookup"><span data-stu-id="8336b-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="8336b-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="8336b-143">machine_guid</span></span>            | <span data-ttu-id="8336b-144">Unikt ID associerat med enheten.</span><span class="sxs-lookup"><span data-stu-id="8336b-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="8336b-145">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas.</span><span class="sxs-lookup"><span data-stu-id="8336b-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="8336b-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="8336b-146">sense_guid</span></span>              | <span data-ttu-id="8336b-147">Unikt ID associerat med enheten.</span><span class="sxs-lookup"><span data-stu-id="8336b-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="8336b-148">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas.</span><span class="sxs-lookup"><span data-stu-id="8336b-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="8336b-149">org_id</span><span class="sxs-lookup"><span data-stu-id="8336b-149">org_id</span></span>                  | <span data-ttu-id="8336b-150">Unikt ID associerat med företaget som enheten tillhör.</span><span class="sxs-lookup"><span data-stu-id="8336b-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="8336b-151">Microsoft kan identifiera om problem påverkar en uppsättning utvalda företag och hur många företag som påverkas.</span><span class="sxs-lookup"><span data-stu-id="8336b-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="8336b-152">hostname</span><span class="sxs-lookup"><span data-stu-id="8336b-152">hostname</span></span>                | <span data-ttu-id="8336b-153">Namn på lokal enhet (utan DNS-suffix).</span><span class="sxs-lookup"><span data-stu-id="8336b-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="8336b-154">Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda installationer och hur många användare som påverkas.</span><span class="sxs-lookup"><span data-stu-id="8336b-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="8336b-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="8336b-155">product_guid</span></span>            | <span data-ttu-id="8336b-156">Unikt ID för produkten.</span><span class="sxs-lookup"><span data-stu-id="8336b-156">Unique identifier of the product.</span></span> <span data-ttu-id="8336b-157">Gör att Microsoft kan särskilja problem som påverkar olika typer av produkten.</span><span class="sxs-lookup"><span data-stu-id="8336b-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="8336b-158">app_version</span><span class="sxs-lookup"><span data-stu-id="8336b-158">app_version</span></span>             | <span data-ttu-id="8336b-159">Version av Microsoft Defender för slutpunkt för Mac-programmet.</span><span class="sxs-lookup"><span data-stu-id="8336b-159">Version of the Microsoft Defender for Endpoint for Mac application.</span></span> <span data-ttu-id="8336b-160">Gör att Microsoft kan identifiera vilka versioner av produkten som visar ett problem så att det kan prioriteras korrekt.</span><span class="sxs-lookup"><span data-stu-id="8336b-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="8336b-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="8336b-161">sig_version</span></span>             | <span data-ttu-id="8336b-162">Version av databasen för säkerhetsintelligens.</span><span class="sxs-lookup"><span data-stu-id="8336b-162">Version of security intelligence database.</span></span> <span data-ttu-id="8336b-163">Gör att Microsoft kan identifiera vilka versioner av säkerhetsinformation som visar ett problem så att det kan prioriteras korrekt.</span><span class="sxs-lookup"><span data-stu-id="8336b-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="8336b-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="8336b-164">supported_compressions</span></span>  | <span data-ttu-id="8336b-165">Lista över komprimeringsalgoritmer som stöds av programmet, till exempel `['gzip']` .</span><span class="sxs-lookup"><span data-stu-id="8336b-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="8336b-166">Gör att Microsoft förstår vilka typer av komprimering som kan användas när de kommunicerar med programmet.</span><span class="sxs-lookup"><span data-stu-id="8336b-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="8336b-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="8336b-167">release_ring</span></span>            | <span data-ttu-id="8336b-168">Ring som enheten är kopplad till (till exempel Insider – snabbt, Insider – långsamt, Produktion).</span><span class="sxs-lookup"><span data-stu-id="8336b-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="8336b-169">Gör att Microsoft kan identifiera vilken version som ett problem kan inträffa så att det kan prioriteras korrekt.</span><span class="sxs-lookup"><span data-stu-id="8336b-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="8336b-170">Obligatoriska diagnostikdata</span><span class="sxs-lookup"><span data-stu-id="8336b-170">Required diagnostic data</span></span>

<span data-ttu-id="8336b-171">**Obligatoriska diagnostikdata** är de lägsta data som krävs för att hålla Microsoft Defender för Slutpunkt säker, uppdaterad och fungerar som förväntat på den enhet som den är installerad på.</span><span class="sxs-lookup"><span data-stu-id="8336b-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="8336b-172">Obligatoriska diagnostikdata hjälper till att identifiera problem med Microsoft Defender för Endpoint som kan vara relaterade till en enhet eller programvarukonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8336b-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="8336b-173">Den kan till exempel hjälpa till att avgöra om en Microsoft Defender för slutpunkt-funktion kraschar oftare på en viss version av operativsystemet, med nyligen använda funktioner eller när vissa Microsoft Defender för Slutpunkt-funktioner är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="8336b-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="8336b-174">Obligatoriska diagnostikdata hjälper Microsoft identifiera, diagnostisera och åtgärda dessa problem snabbare så att påverkan på användare eller organisationer minskas.</span><span class="sxs-lookup"><span data-stu-id="8336b-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="8336b-175">Programvaruinstallation och lagringshändelser</span><span class="sxs-lookup"><span data-stu-id="8336b-175">Software setup and inventory data events</span></span>

<span data-ttu-id="8336b-176">**Installation/avinstallation av Microsoft Defender för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="8336b-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="8336b-177">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-177">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-178">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-178">Field</span></span>            | <span data-ttu-id="8336b-179">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8336b-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="8336b-180">correlation_id</span></span>   | <span data-ttu-id="8336b-181">Unikt ID associerat med installationen.</span><span class="sxs-lookup"><span data-stu-id="8336b-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="8336b-182">version</span><span class="sxs-lookup"><span data-stu-id="8336b-182">version</span></span>          | <span data-ttu-id="8336b-183">Version av paketet.</span><span class="sxs-lookup"><span data-stu-id="8336b-183">Version of the package.</span></span> |
| <span data-ttu-id="8336b-184">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="8336b-184">severity</span></span>         | <span data-ttu-id="8336b-185">Meddelandets allvarlighetsgrad (till exempel information).</span><span class="sxs-lookup"><span data-stu-id="8336b-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="8336b-186">kod</span><span class="sxs-lookup"><span data-stu-id="8336b-186">code</span></span>             | <span data-ttu-id="8336b-187">Kod som beskriver åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8336b-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="8336b-188">text</span><span class="sxs-lookup"><span data-stu-id="8336b-188">text</span></span>             | <span data-ttu-id="8336b-189">Ytterligare information associerad med produktinstallationen.</span><span class="sxs-lookup"><span data-stu-id="8336b-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="8336b-190">**Microsoft Defender för slutpunktskonfiguration**</span><span class="sxs-lookup"><span data-stu-id="8336b-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="8336b-191">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-191">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-192">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-192">Field</span></span>                                               | <span data-ttu-id="8336b-193">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="8336b-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="8336b-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="8336b-195">Om realtidsskydd är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="8336b-196">antivirus_engine.passivt_läge</span><span class="sxs-lookup"><span data-stu-id="8336b-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="8336b-197">Oavsett om passivt läge är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="8336b-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="8336b-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="8336b-199">Om moln levererat skydd är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="8336b-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="8336b-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="8336b-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span><span class="sxs-lookup"><span data-stu-id="8336b-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="8336b-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="8336b-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="8336b-203">Intervall mellan flera hjärtslag som skickas av produkten till molnet.</span><span class="sxs-lookup"><span data-stu-id="8336b-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="8336b-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="8336b-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="8336b-205">URI som används för att kommunicera med molnet.</span><span class="sxs-lookup"><span data-stu-id="8336b-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="8336b-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="8336b-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="8336b-207">Diagnostiknivå för enheten (obligatoriskt, valfritt).</span><span class="sxs-lookup"><span data-stu-id="8336b-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="8336b-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="8336b-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="8336b-209">Om automatisk exempelinskickning är aktiverat eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="8336b-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="8336b-210">edr.early_preview</span></span>                                   | <span data-ttu-id="8336b-211">Om enheten ska köra EDR-funktioner för tidig förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="8336b-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="8336b-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="8336b-212">edr.group_id</span></span>                                        | <span data-ttu-id="8336b-213">Gruppidentifierare som används av identifierings- och svarskomponenten.</span><span class="sxs-lookup"><span data-stu-id="8336b-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="8336b-214">edr.tags</span><span class="sxs-lookup"><span data-stu-id="8336b-214">edr.tags</span></span>                                            | <span data-ttu-id="8336b-215">Användardefinierade taggar.</span><span class="sxs-lookup"><span data-stu-id="8336b-215">User-defined tags.</span></span> |
| <span data-ttu-id="8336b-216">funktioner. \[ valfritt funktionsnamn\]</span><span class="sxs-lookup"><span data-stu-id="8336b-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="8336b-217">Lista över förhandsgranskningsfunktioner, tillsammans med huruvida de är aktiverade eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="8336b-218">Produkt- och tjänstanvändningshändelser</span><span class="sxs-lookup"><span data-stu-id="8336b-218">Product and service usage data events</span></span>

<span data-ttu-id="8336b-219">**Säkerhetsintelligensuppdateringsrapport**</span><span class="sxs-lookup"><span data-stu-id="8336b-219">**Security intelligence update report**</span></span>

<span data-ttu-id="8336b-220">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-220">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-221">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-221">Field</span></span>            | <span data-ttu-id="8336b-222">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8336b-223">from_version</span><span class="sxs-lookup"><span data-stu-id="8336b-223">from_version</span></span>     | <span data-ttu-id="8336b-224">Ursprunglig säkerhetsintelligensversion.</span><span class="sxs-lookup"><span data-stu-id="8336b-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="8336b-225">to_version</span><span class="sxs-lookup"><span data-stu-id="8336b-225">to_version</span></span>       | <span data-ttu-id="8336b-226">Ny säkerhetsintelligensversion.</span><span class="sxs-lookup"><span data-stu-id="8336b-226">New security intelligence version.</span></span> |
| <span data-ttu-id="8336b-227">status</span><span class="sxs-lookup"><span data-stu-id="8336b-227">status</span></span>           | <span data-ttu-id="8336b-228">Status för uppdateringen som anger framgång eller fel.</span><span class="sxs-lookup"><span data-stu-id="8336b-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="8336b-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="8336b-229">using_proxy</span></span>      | <span data-ttu-id="8336b-230">Om uppdateringen gjordes via en proxyserver.</span><span class="sxs-lookup"><span data-stu-id="8336b-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="8336b-231">fel</span><span class="sxs-lookup"><span data-stu-id="8336b-231">error</span></span>            | <span data-ttu-id="8336b-232">Felkod om uppdateringen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="8336b-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="8336b-233">orsak</span><span class="sxs-lookup"><span data-stu-id="8336b-233">reason</span></span>           | <span data-ttu-id="8336b-234">Felmeddelande om den uppdaterade arkiverade informationen.</span><span class="sxs-lookup"><span data-stu-id="8336b-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="8336b-235">Datahändelser för produkt- och tjänstprestanda</span><span class="sxs-lookup"><span data-stu-id="8336b-235">Product and service performance data events</span></span>

<span data-ttu-id="8336b-236">**Oväntat programavslut (kraschar)**</span><span class="sxs-lookup"><span data-stu-id="8336b-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="8336b-237">Samlar in systeminformation och status för ett program när ett program oväntat avslutas.</span><span class="sxs-lookup"><span data-stu-id="8336b-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="8336b-238">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-238">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-239">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-239">Field</span></span>                          | <span data-ttu-id="8336b-240">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="8336b-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="8336b-241">v1_crash_count</span></span>                 | <span data-ttu-id="8336b-242">Antal gånger som V1-motorprocessen kraschade varje timme på klientdatorn</span><span class="sxs-lookup"><span data-stu-id="8336b-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="8336b-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="8336b-243">v2_crash_count</span></span>                 | <span data-ttu-id="8336b-244">Antal gånger som V2-motorprocessen kraschade varje timme på klientdatorn</span><span class="sxs-lookup"><span data-stu-id="8336b-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="8336b-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="8336b-245">EDR_crash_count</span></span>                | <span data-ttu-id="8336b-246">Antal gånger som EDR-processen kraschade varje timme på klientdatorn</span><span class="sxs-lookup"><span data-stu-id="8336b-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="8336b-247">**Statistik över Kernel-tillägg**</span><span class="sxs-lookup"><span data-stu-id="8336b-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="8336b-248">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-248">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-249">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-249">Field</span></span>            | <span data-ttu-id="8336b-250">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8336b-251">version</span><span class="sxs-lookup"><span data-stu-id="8336b-251">version</span></span>          | <span data-ttu-id="8336b-252">Version av Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="8336b-252">Version of Microsoft Defender for Endpoint for Mac.</span></span> |
| <span data-ttu-id="8336b-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="8336b-253">instance_id</span></span>      | <span data-ttu-id="8336b-254">Unikt ID som genererades vid start av kernel-tillägg.</span><span class="sxs-lookup"><span data-stu-id="8336b-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="8336b-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="8336b-255">trace_level</span></span>      | <span data-ttu-id="8336b-256">Spårningsnivån för kernel-tillägget.</span><span class="sxs-lookup"><span data-stu-id="8336b-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="8336b-257">undersystem</span><span class="sxs-lookup"><span data-stu-id="8336b-257">subsystem</span></span>        | <span data-ttu-id="8336b-258">Det underliggande undersystemet som används för realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="8336b-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="8336b-259">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="8336b-259">ipc.connects</span></span>     | <span data-ttu-id="8336b-260">Antal anslutningsförfrågningar som mottagits av kernel-tilläggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="8336b-261">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="8336b-261">ipc.rejects</span></span>      | <span data-ttu-id="8336b-262">Antal anslutningsbegäranden som avvisats av kernel-tillägget.</span><span class="sxs-lookup"><span data-stu-id="8336b-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="8336b-263">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="8336b-263">ipc.connected</span></span>    | <span data-ttu-id="8336b-264">Om det finns någon aktiv anslutning till kernel-tilläggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="8336b-265">Supportdata</span><span class="sxs-lookup"><span data-stu-id="8336b-265">Support data</span></span>

<span data-ttu-id="8336b-266">**Diagnostikloggar**</span><span class="sxs-lookup"><span data-stu-id="8336b-266">**Diagnostic logs**</span></span>

<span data-ttu-id="8336b-267">Diagnostikloggar samlas bara in med användarens medgivande som en del av funktionen för feedbackinskick.</span><span class="sxs-lookup"><span data-stu-id="8336b-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="8336b-268">Följande filer samlas in som en del av supportloggarna:</span><span class="sxs-lookup"><span data-stu-id="8336b-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="8336b-269">Alla filer under */Bibliotek/Loggar/Microsoft/mdatp/*</span><span class="sxs-lookup"><span data-stu-id="8336b-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="8336b-270">Delmängd av filer under */Bibliotek/Programstöd/Microsoft/Defender/* som skapas och används av Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="8336b-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="8336b-271">Delmängd av filer under */Bibliotek/Hanterade inställningar* som används av Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="8336b-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="8336b-272">/Bibliotek/Loggar/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="8336b-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="8336b-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="8336b-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="8336b-274">Valfria diagnostikdata</span><span class="sxs-lookup"><span data-stu-id="8336b-274">Optional diagnostic data</span></span>

<span data-ttu-id="8336b-275">**Valfria diagnostikdata** är ytterligare data som hjälper Microsoft göra produktförbättringar och ger förbättrad information som hjälper till att identifiera, diagnostisera och åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="8336b-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="8336b-276">Om du väljer att skicka valfria diagnostikdata omfattas även obligatoriska diagnostikdata.</span><span class="sxs-lookup"><span data-stu-id="8336b-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="8336b-277">Exempel på valfria diagnostikdata är data som Microsoft samlar in om produktkonfiguration (till exempel antal undantag som angetts på enheten) och produktprestanda (mängdåtgärder om prestanda för komponenter i produkten).</span><span class="sxs-lookup"><span data-stu-id="8336b-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="8336b-278">Programvaruinstallation och lagringshändelser</span><span class="sxs-lookup"><span data-stu-id="8336b-278">Software setup and inventory data events</span></span>

<span data-ttu-id="8336b-279">**Microsoft Defender för slutpunktskonfiguration**</span><span class="sxs-lookup"><span data-stu-id="8336b-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="8336b-280">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-280">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-281">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-281">Field</span></span>                                              | <span data-ttu-id="8336b-282">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="8336b-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="8336b-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="8336b-284">Anslutningen försöker time out när anslutningen kommunicerar med molnet.</span><span class="sxs-lookup"><span data-stu-id="8336b-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="8336b-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="8336b-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="8336b-286">Storleken på produktcachen.</span><span class="sxs-lookup"><span data-stu-id="8336b-286">Size of the product cache.</span></span> |
| <span data-ttu-id="8336b-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="8336b-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="8336b-288">Begränsningen för kraschloggar som laddas upp dagligen.</span><span class="sxs-lookup"><span data-stu-id="8336b-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="8336b-289">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="8336b-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="8336b-290">Om undantaget från genomsökning är en katalog eller inte.</span><span class="sxs-lookup"><span data-stu-id="8336b-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="8336b-291">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="8336b-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="8336b-292">Sökväg som uteslöts från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="8336b-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="8336b-293">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="8336b-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="8336b-294">Tillägget är inte till förskanning.</span><span class="sxs-lookup"><span data-stu-id="8336b-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="8336b-295">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="8336b-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="8336b-296">Namnet på filen som undantas från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="8336b-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="8336b-297">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="8336b-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="8336b-298">Storleken på produktcachen.</span><span class="sxs-lookup"><span data-stu-id="8336b-298">Size of the product cache.</span></span> |
| <span data-ttu-id="8336b-299">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="8336b-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="8336b-300">Maximalt antal trådar som används för genomsökning.</span><span class="sxs-lookup"><span data-stu-id="8336b-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="8336b-301">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="8336b-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="8336b-302">Time out before a file restored from the quarantine can beected again.</span><span class="sxs-lookup"><span data-stu-id="8336b-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="8336b-303">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="8336b-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="8336b-304">Fullständig genomsökningskatalog.</span><span class="sxs-lookup"><span data-stu-id="8336b-304">Full scan directory.</span></span> |
| <span data-ttu-id="8336b-305">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="8336b-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="8336b-306">Lista med kataloger som används i snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="8336b-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="8336b-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="8336b-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="8336b-308">Svarstidsläge som används av identifierings- och svarskomponenten.</span><span class="sxs-lookup"><span data-stu-id="8336b-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="8336b-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="8336b-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="8336b-310">Proxyadress som används av identifierings- och svarskomponenten.</span><span class="sxs-lookup"><span data-stu-id="8336b-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="8336b-311">**Konfiguration av Microsoft Auto-Update**</span><span class="sxs-lookup"><span data-stu-id="8336b-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="8336b-312">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-312">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-313">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-313">Field</span></span>                       | <span data-ttu-id="8336b-314">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="8336b-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="8336b-315">how_to_check</span></span>                | <span data-ttu-id="8336b-316">Avgör hur produktuppdateringar kontrolleras (till exempel automatiskt eller manuellt).</span><span class="sxs-lookup"><span data-stu-id="8336b-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="8336b-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="8336b-317">channel_name</span></span>                | <span data-ttu-id="8336b-318">Uppdatera kanal som är kopplad till enheten.</span><span class="sxs-lookup"><span data-stu-id="8336b-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="8336b-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="8336b-319">manifest_server</span></span>             | <span data-ttu-id="8336b-320">Den server som används för att ladda ned uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8336b-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="8336b-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="8336b-321">update_cache</span></span>                | <span data-ttu-id="8336b-322">Platsen för cachen som används för att lagra uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8336b-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="8336b-323">Produkt- och tjänstanvändning</span><span class="sxs-lookup"><span data-stu-id="8336b-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="8336b-324">Rapporten Startad diagnostiklogguppladdning</span><span class="sxs-lookup"><span data-stu-id="8336b-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="8336b-325">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-325">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-326">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-326">Field</span></span>            | <span data-ttu-id="8336b-327">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8336b-328">sha256</span><span class="sxs-lookup"><span data-stu-id="8336b-328">sha256</span></span>           | <span data-ttu-id="8336b-329">SHA256-identifierare för supportloggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="8336b-330">storlek</span><span class="sxs-lookup"><span data-stu-id="8336b-330">size</span></span>             | <span data-ttu-id="8336b-331">Storlek på supportloggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-331">Size of the support log.</span></span> |
| <span data-ttu-id="8336b-332">original_path</span><span class="sxs-lookup"><span data-stu-id="8336b-332">original_path</span></span>    | <span data-ttu-id="8336b-333">Sökväg till supportloggen (alltid under */Bibliotek/Programstöd/Microsoft/Defender/wdavdiag/*).</span><span class="sxs-lookup"><span data-stu-id="8336b-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="8336b-334">format</span><span class="sxs-lookup"><span data-stu-id="8336b-334">format</span></span>           | <span data-ttu-id="8336b-335">Format för supportloggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="8336b-336">Rapport om slutförd diagnostiklogguppladdning</span><span class="sxs-lookup"><span data-stu-id="8336b-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="8336b-337">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-337">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-338">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-338">Field</span></span>            | <span data-ttu-id="8336b-339">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8336b-340">request_id</span><span class="sxs-lookup"><span data-stu-id="8336b-340">request_id</span></span>       | <span data-ttu-id="8336b-341">Korrelations-ID för begäran om uppladdning av supportlogg.</span><span class="sxs-lookup"><span data-stu-id="8336b-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="8336b-342">sha256</span><span class="sxs-lookup"><span data-stu-id="8336b-342">sha256</span></span>           | <span data-ttu-id="8336b-343">SHA256-identifierare för supportloggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="8336b-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="8336b-344">blob_sas_uri</span></span>     | <span data-ttu-id="8336b-345">URI som används av programmet för att ladda upp supportloggen.</span><span class="sxs-lookup"><span data-stu-id="8336b-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="8336b-346">Datahändelser för produkt- och tjänstprestanda</span><span class="sxs-lookup"><span data-stu-id="8336b-346">Product and service performance data events</span></span>

<span data-ttu-id="8336b-347">**Oväntat programavslut (kraschar)**</span><span class="sxs-lookup"><span data-stu-id="8336b-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="8336b-348">Oväntat programavslut (krasch) och tillståndet för programmet när det händer.</span><span class="sxs-lookup"><span data-stu-id="8336b-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="8336b-349">**Statistik över Kernel-tillägg**</span><span class="sxs-lookup"><span data-stu-id="8336b-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="8336b-350">Följande fält samlas in:</span><span class="sxs-lookup"><span data-stu-id="8336b-350">The following fields are collected:</span></span>

| <span data-ttu-id="8336b-351">Fält</span><span class="sxs-lookup"><span data-stu-id="8336b-351">Field</span></span>                          | <span data-ttu-id="8336b-352">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8336b-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="8336b-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="8336b-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="8336b-354">Följande egenskaper är aggregerade numeriska värden som representerar antalet händelser som inträffat sedan kernel-tilläggen startades.</span><span class="sxs-lookup"><span data-stu-id="8336b-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="8336b-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="8336b-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="8336b-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="8336b-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="8336b-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="8336b-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="8336b-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="8336b-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="8336b-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="8336b-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="8336b-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="8336b-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="8336b-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="8336b-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="8336b-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="8336b-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="8336b-363">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="8336b-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="8336b-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="8336b-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="8336b-365">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="8336b-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="8336b-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="8336b-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="8336b-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="8336b-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="8336b-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="8336b-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="8336b-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="8336b-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="8336b-370">ipc.thth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="8336b-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="8336b-371">ipc.thth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="8336b-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="8336b-372">ipc.thth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="8336b-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="8336b-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="8336b-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="8336b-374">ipc.thth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="8336b-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="8336b-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="8336b-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="8336b-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="8336b-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="8336b-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="8336b-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="8336b-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="8336b-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="8336b-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="8336b-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="8336b-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="8336b-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="8336b-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="8336b-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="8336b-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="8336b-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="8336b-383">ipc.thth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="8336b-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="8336b-384">ipc.thth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="8336b-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="8336b-385">ipc.thth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="8336b-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="8336b-386">ipc.thth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="8336b-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="8336b-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="8336b-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="8336b-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="8336b-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="8336b-389">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="8336b-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="8336b-390">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="8336b-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="8336b-391">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="8336b-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="8336b-392">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="8336b-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="8336b-393">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="8336b-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="8336b-394">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="8336b-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="8336b-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="8336b-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="8336b-396">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="8336b-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="8336b-397">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="8336b-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="8336b-398">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="8336b-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="8336b-399">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="8336b-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="8336b-400">Resurser</span><span class="sxs-lookup"><span data-stu-id="8336b-400">Resources</span></span>

- [<span data-ttu-id="8336b-401">Sekretess på Microsoft</span><span class="sxs-lookup"><span data-stu-id="8336b-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
