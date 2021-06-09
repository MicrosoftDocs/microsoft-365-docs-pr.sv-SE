---
title: Distribuera uppdateringar för Microsoft Defender för slutpunkt på Mac
description: Kontrollera uppdateringar för Microsoft Defender för Slutpunkt på Mac i företagsmiljöer.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, uppdateringar, distribuera
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
ms.openlocfilehash: 6447aa4182846020312e9be870c5548d9415ac71
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842836"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="29a80-104">Distribuera uppdateringar för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="29a80-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="29a80-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="29a80-105">**Applies to:**</span></span>

- [<span data-ttu-id="29a80-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="29a80-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="29a80-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="29a80-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29a80-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29a80-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="29a80-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="29a80-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29a80-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="29a80-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="29a80-111">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="29a80-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="29a80-112">För att uppdatera Microsoft Defender för slutpunkt i macOS används ett program med namnet Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="29a80-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="29a80-113">Som standard söker MAU automatiskt efter uppdateringar varje dag, men du kan ändra det till varje vecka, varje månad eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="29a80-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU skärmbild](images/MDATP-34-MAU.png)

<span data-ttu-id="29a80-115">Om du bestämmer dig för att distribuera uppdateringar med dina verktyg för programvarudistribution bör du konfigurera MAU att manuellt söka efter programuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="29a80-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="29a80-116">Du kan distribuera inställningar för att konfigurera hur och när MAU söker efter uppdateringar för Mac-datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="29a80-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="29a80-117">Använda msupdate</span><span class="sxs-lookup"><span data-stu-id="29a80-117">Use msupdate</span></span>

<span data-ttu-id="29a80-118">MAU innehåller ett kommandoradsverktyg, *msupdate,* som är utformat för IT-administratörer så att de får mer exakt kontroll över när uppdateringar tillämpas.</span><span class="sxs-lookup"><span data-stu-id="29a80-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="29a80-119">Instruktioner för hur du använder verktyget finns i Uppdaterings- och [Office för Mac med hjälp av msupdate.](/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="29a80-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="29a80-120">I MAU är programidentifieraren för Microsoft Defender för Slutpunkt i macOS *WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="29a80-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="29a80-121">Ladda ned och installera de senaste uppdateringarna för Microsoft Defender för Slutpunkt i macOS genom att köra följande kommando från ett terminalfönster:</span><span class="sxs-lookup"><span data-stu-id="29a80-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="29a80-122">Ange inställningar för Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="29a80-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="29a80-123">I det här avsnittet beskrivs de vanligaste inställningarna som kan användas för att konfigurera MAU.</span><span class="sxs-lookup"><span data-stu-id="29a80-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="29a80-124">De här inställningarna kan distribueras som en konfigurationsprofil via hanteringskonsolen som ditt företag använder.</span><span class="sxs-lookup"><span data-stu-id="29a80-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="29a80-125">Ett exempel på en konfigurationsprofil visas i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="29a80-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="29a80-126">Ange kanalnamn</span><span class="sxs-lookup"><span data-stu-id="29a80-126">Set the channel name</span></span>

<span data-ttu-id="29a80-127">Kanalen avgör typ och frekvens för uppdateringar som erbjuds via MAU.</span><span class="sxs-lookup"><span data-stu-id="29a80-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="29a80-128">Enheter i `Beta` kan prova nya funktioner före enheter i och `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="29a80-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="29a80-129">Kanalen `Current` innehåller den mest stabila versionen av produkten.</span><span class="sxs-lookup"><span data-stu-id="29a80-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="29a80-130">Före Microsoft AutoUpdate version 4.29 hade kanaler olika namn:</span><span class="sxs-lookup"><span data-stu-id="29a80-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="29a80-131">`Beta` hette `InsiderFast` (Insider – snabbt)</span><span class="sxs-lookup"><span data-stu-id="29a80-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="29a80-132">`Preview` hette `External` (Insider – långsamt)</span><span class="sxs-lookup"><span data-stu-id="29a80-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="29a80-133">`Current` hette `Production`</span><span class="sxs-lookup"><span data-stu-id="29a80-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="29a80-134">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag `Beta` för eller `Preview` .</span><span class="sxs-lookup"><span data-stu-id="29a80-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="29a80-135">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-135">Section</span></span>|<span data-ttu-id="29a80-136">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-137">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-138">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-138">**Key**</span></span> | <span data-ttu-id="29a80-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="29a80-139">ChannelName</span></span> |
| <span data-ttu-id="29a80-140">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-140">**Data type**</span></span> | <span data-ttu-id="29a80-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="29a80-141">String</span></span> |
| <span data-ttu-id="29a80-142">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="29a80-142">**Possible values**</span></span> | <span data-ttu-id="29a80-143">Beta</span><span class="sxs-lookup"><span data-stu-id="29a80-143">Beta</span></span> <br/> <span data-ttu-id="29a80-144">Förhandsgranska</span><span class="sxs-lookup"><span data-stu-id="29a80-144">Preview</span></span> <br/> <span data-ttu-id="29a80-145">Aktuell</span><span class="sxs-lookup"><span data-stu-id="29a80-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="29a80-146">Den här inställningen ändrar kanalen för alla program som uppdateras via Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="29a80-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="29a80-147">Om du vill ändra endast kanalen för Microsoft Defender för slutpunkt i macOS kör du följande kommando efter att `[channel-name]` du har ersatt med önskad kanal:</span><span class="sxs-lookup"><span data-stu-id="29a80-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="29a80-148">Ange uppdateringsintervall</span><span class="sxs-lookup"><span data-stu-id="29a80-148">Set update check frequency</span></span>

<span data-ttu-id="29a80-149">Ändra hur ofta MAU söker efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="29a80-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="29a80-150">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-150">Section</span></span>|<span data-ttu-id="29a80-151">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-152">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-153">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-153">**Key**</span></span> | <span data-ttu-id="29a80-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="29a80-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="29a80-155">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-155">**Data type**</span></span> | <span data-ttu-id="29a80-156">Heltal</span><span class="sxs-lookup"><span data-stu-id="29a80-156">Integer</span></span> |
| <span data-ttu-id="29a80-157">**Standardvärde**</span><span class="sxs-lookup"><span data-stu-id="29a80-157">**Default value**</span></span> | <span data-ttu-id="29a80-158">720 (minuter)</span><span class="sxs-lookup"><span data-stu-id="29a80-158">720 (minutes)</span></span> |
| <span data-ttu-id="29a80-159">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="29a80-159">**Comment**</span></span> | <span data-ttu-id="29a80-160">Det här värdet anges i minuter.</span><span class="sxs-lookup"><span data-stu-id="29a80-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="29a80-161">Ändra hur MAU interagerar med uppdateringar</span><span class="sxs-lookup"><span data-stu-id="29a80-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="29a80-162">Ändra hur MAU söker efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="29a80-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="29a80-163">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-163">Section</span></span>|<span data-ttu-id="29a80-164">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-165">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-166">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-166">**Key**</span></span> | <span data-ttu-id="29a80-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="29a80-167">HowToCheck</span></span> |
| <span data-ttu-id="29a80-168">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-168">**Data type**</span></span> | <span data-ttu-id="29a80-169">Sträng</span><span class="sxs-lookup"><span data-stu-id="29a80-169">String</span></span> |
| <span data-ttu-id="29a80-170">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="29a80-170">**Possible values**</span></span> | <span data-ttu-id="29a80-171">Manuellt</span><span class="sxs-lookup"><span data-stu-id="29a80-171">Manual</span></span> <br/> <span data-ttu-id="29a80-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="29a80-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="29a80-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="29a80-173">AutomaticDownload</span></span> |
| <span data-ttu-id="29a80-174">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="29a80-174">**Comment**</span></span> |  <span data-ttu-id="29a80-175">Observera att AutomaticDownload gör en nedladdning och installation utan att du behöver göra det.</span><span class="sxs-lookup"><span data-stu-id="29a80-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="29a80-176">Ändra om knappen Sök efter uppdateringar ska vara aktiverad</span><span class="sxs-lookup"><span data-stu-id="29a80-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="29a80-177">Ändra om lokala användare ska kunna klicka på alternativet "Sök efter uppdateringar" i användargränssnittet för Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="29a80-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="29a80-178">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-178">Section</span></span>|<span data-ttu-id="29a80-179">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-180">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-181">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-181">**Key**</span></span> | <span data-ttu-id="29a80-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="29a80-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="29a80-183">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-183">**Data type**</span></span> | <span data-ttu-id="29a80-184">Boolesk</span><span class="sxs-lookup"><span data-stu-id="29a80-184">Boolean</span></span> |
| <span data-ttu-id="29a80-185">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="29a80-185">**Possible values**</span></span> | <span data-ttu-id="29a80-186">True (standard)</span><span class="sxs-lookup"><span data-stu-id="29a80-186">True (default)</span></span> <br/> <span data-ttu-id="29a80-187">False</span><span class="sxs-lookup"><span data-stu-id="29a80-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="29a80-188">Kryssrutan Inaktivera Insider</span><span class="sxs-lookup"><span data-stu-id="29a80-188">Disable Insider checkbox</span></span>

<span data-ttu-id="29a80-189">Inställd på sant för att göra "Gå med i Office Insider Program..." inte tillgänglig/nedtonad för användare.</span><span class="sxs-lookup"><span data-stu-id="29a80-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="29a80-190">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-190">Section</span></span>|<span data-ttu-id="29a80-191">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-192">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-193">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-193">**Key**</span></span> | <span data-ttu-id="29a80-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="29a80-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="29a80-195">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-195">**Data type**</span></span> | <span data-ttu-id="29a80-196">Boolesk</span><span class="sxs-lookup"><span data-stu-id="29a80-196">Boolean</span></span> |
| <span data-ttu-id="29a80-197">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="29a80-197">**Possible values**</span></span> | <span data-ttu-id="29a80-198">False (standard)</span><span class="sxs-lookup"><span data-stu-id="29a80-198">False (default)</span></span> <br/> <span data-ttu-id="29a80-199">True</span><span class="sxs-lookup"><span data-stu-id="29a80-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="29a80-200">Begränsa telemetrin som skickas från MAU</span><span class="sxs-lookup"><span data-stu-id="29a80-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="29a80-201">Ange falskt om du vill skicka minimalt med data om hjärtslag, ingen programanvändning och ingen miljöinformation.</span><span class="sxs-lookup"><span data-stu-id="29a80-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="29a80-202">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="29a80-202">Section</span></span>|<span data-ttu-id="29a80-203">Värde</span><span class="sxs-lookup"><span data-stu-id="29a80-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="29a80-204">**Domän**</span><span class="sxs-lookup"><span data-stu-id="29a80-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="29a80-205">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="29a80-205">**Key**</span></span> | <span data-ttu-id="29a80-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="29a80-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="29a80-207">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="29a80-207">**Data type**</span></span> | <span data-ttu-id="29a80-208">Boolesk</span><span class="sxs-lookup"><span data-stu-id="29a80-208">Boolean</span></span> |
| <span data-ttu-id="29a80-209">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="29a80-209">**Possible values**</span></span> | <span data-ttu-id="29a80-210">True (standard)</span><span class="sxs-lookup"><span data-stu-id="29a80-210">True (default)</span></span> <br/> <span data-ttu-id="29a80-211">False</span><span class="sxs-lookup"><span data-stu-id="29a80-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="29a80-212">Exempel på konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="29a80-212">Example configuration profile</span></span>

<span data-ttu-id="29a80-213">Följande konfigurationsprofil används för att:</span><span class="sxs-lookup"><span data-stu-id="29a80-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="29a80-214">Placera enheten i produktionskanalen</span><span class="sxs-lookup"><span data-stu-id="29a80-214">Place the device in the Production channel</span></span>
- <span data-ttu-id="29a80-215">Ladda ned och installera uppdateringar automatiskt</span><span class="sxs-lookup"><span data-stu-id="29a80-215">Automatically download and install updates</span></span>
- <span data-ttu-id="29a80-216">Aktivera knappen Sök efter uppdateringar i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="29a80-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="29a80-217">Tillåt användare på enheten att registrera sig i Insider-kanalerna</span><span class="sxs-lookup"><span data-stu-id="29a80-217">Allow users on the device to enroll into the Insider channels</span></span>


>[!WARNING]
><span data-ttu-id="29a80-218">Nedanstående konfiguration är en exempelkonfiguration och bör inte användas i produktionen utan en korrekt granskning av inställningar och skräddarsy konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="29a80-218">The below configuration is an example configuration and should not be used in production without proper review of settings and tailor of configurations.</span></span>

>[!TIP]
><span data-ttu-id="29a80-219">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag `Beta` för eller `Preview` .</span><span class="sxs-lookup"><span data-stu-id="29a80-219">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

### <a name="jamf"></a><span data-ttu-id="29a80-220">JAMF</span><span class="sxs-lookup"><span data-stu-id="29a80-220">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="29a80-221">Intune</span><span class="sxs-lookup"><span data-stu-id="29a80-221">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="29a80-222">Om du vill konfigurera MAU kan du distribuera den här konfigurationsprofilen från det hanteringsverktyg som företaget använder:</span><span class="sxs-lookup"><span data-stu-id="29a80-222">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="29a80-223">Från JAMF laddar du upp den här konfigurationsprofilen och anger preference domain *till com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="29a80-223">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="29a80-224">Från Intune laddar du upp den här konfigurationsprofilen och anger namnet på den anpassade konfigurationsprofilen *på com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="29a80-224">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="29a80-225">Resurser</span><span class="sxs-lookup"><span data-stu-id="29a80-225">Resources</span></span>

- [<span data-ttu-id="29a80-226">referens för msupdate</span><span class="sxs-lookup"><span data-stu-id="29a80-226">msupdate reference</span></span>](/deployoffice/mac/update-office-for-mac-using-msupdate)
