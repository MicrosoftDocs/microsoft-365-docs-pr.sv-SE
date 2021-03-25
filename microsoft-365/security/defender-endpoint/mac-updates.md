---
title: Distribuera uppdateringar för Microsoft Defender ATP för Mac
description: Kontrollera uppdateringar för Microsoft Defender ATP för Mac i företagsmiljöer.
keywords: microsoft, defender, atp, mac, uppdateringar, distribuera
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
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074345"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="a71f3-104">Distribuera uppdateringar för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="a71f3-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a71f3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a71f3-105">**Applies to:**</span></span>

- [<span data-ttu-id="a71f3-106">Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="a71f3-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="a71f3-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a71f3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a71f3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a71f3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a71f3-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a71f3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a71f3-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a71f3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a71f3-111">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="a71f3-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="a71f3-112">För att uppdatera Microsoft Defender för Slutpunkt för Mac används ett program med namnet Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="a71f3-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="a71f3-113">Som standard söker MAU automatiskt efter uppdateringar varje dag, men du kan ändra det till varje vecka, varje månad eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="a71f3-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU skärmbild](images/MDATP-34-MAU.png)

<span data-ttu-id="a71f3-115">Om du bestämmer dig för att distribuera uppdateringar med dina verktyg för programvarudistribution bör du konfigurera MAU att manuellt söka efter programuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a71f3-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="a71f3-116">Du kan distribuera inställningar för att konfigurera hur och när MAU söker efter uppdateringar för Mac-datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a71f3-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="a71f3-117">Använda msupdate</span><span class="sxs-lookup"><span data-stu-id="a71f3-117">Use msupdate</span></span>

<span data-ttu-id="a71f3-118">MAU innehåller ett kommandoradsverktyg, *msupdate,* som är utformat för IT-administratörer så att de får mer exakt kontroll över när uppdateringar tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a71f3-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="a71f3-119">Anvisningar för hur du använder verktyget finns i Uppdatera [Office för Mac med hjälp av msupdate.](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="a71f3-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="a71f3-120">I MAU är programidentifieraren för Microsoft Defender för Endpoint för Mac *WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="a71f3-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="a71f3-121">Ladda ned och installera de senaste uppdateringarna för Microsoft Defender för Slutpunkt för Mac genom att köra följande kommando från ett terminalfönster:</span><span class="sxs-lookup"><span data-stu-id="a71f3-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="a71f3-122">Ange inställningar för Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="a71f3-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="a71f3-123">I det här avsnittet beskrivs de vanligaste inställningarna som kan användas för att konfigurera MAU.</span><span class="sxs-lookup"><span data-stu-id="a71f3-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="a71f3-124">De här inställningarna kan distribueras som en konfigurationsprofil via hanteringskonsolen som ditt företag använder.</span><span class="sxs-lookup"><span data-stu-id="a71f3-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="a71f3-125">Ett exempel på en konfigurationsprofil visas i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="a71f3-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="a71f3-126">Ange kanalnamn</span><span class="sxs-lookup"><span data-stu-id="a71f3-126">Set the channel name</span></span>

<span data-ttu-id="a71f3-127">Kanalen avgör typ och frekvens för uppdateringar som erbjuds via MAU.</span><span class="sxs-lookup"><span data-stu-id="a71f3-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="a71f3-128">Enheter i `Beta` kan prova nya funktioner före enheter i och `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="a71f3-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="a71f3-129">Kanalen `Current` innehåller den mest stabila versionen av produkten.</span><span class="sxs-lookup"><span data-stu-id="a71f3-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a71f3-130">Före Microsoft AutoUpdate version 4.29 hade kanaler olika namn:</span><span class="sxs-lookup"><span data-stu-id="a71f3-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="a71f3-131">`Beta` hette `InsiderFast` (Insider – snabbt)</span><span class="sxs-lookup"><span data-stu-id="a71f3-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="a71f3-132">`Preview` hette `External` (Insider – långsamt)</span><span class="sxs-lookup"><span data-stu-id="a71f3-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="a71f3-133">`Current` hette `Production`</span><span class="sxs-lookup"><span data-stu-id="a71f3-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="a71f3-134">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag `Beta` för eller `Preview` .</span><span class="sxs-lookup"><span data-stu-id="a71f3-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-135">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-135">**Domain**</span></span> | <span data-ttu-id="a71f3-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-137">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-137">**Key**</span></span> | <span data-ttu-id="a71f3-138">ChannelName</span><span class="sxs-lookup"><span data-stu-id="a71f3-138">ChannelName</span></span> |
| <span data-ttu-id="a71f3-139">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-139">**Data type**</span></span> | <span data-ttu-id="a71f3-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="a71f3-140">String</span></span> |
| <span data-ttu-id="a71f3-141">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="a71f3-141">**Possible values**</span></span> | <span data-ttu-id="a71f3-142">Beta</span><span class="sxs-lookup"><span data-stu-id="a71f3-142">Beta</span></span> <br/> <span data-ttu-id="a71f3-143">Förhandsgranska</span><span class="sxs-lookup"><span data-stu-id="a71f3-143">Preview</span></span> <br/> <span data-ttu-id="a71f3-144">Aktuell</span><span class="sxs-lookup"><span data-stu-id="a71f3-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="a71f3-145">Den här inställningen ändrar kanalen för alla program som uppdateras via Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="a71f3-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="a71f3-146">Om du vill ändra endast kanalen för Microsoft Defender för Endpoint för Mac kör du följande kommando efter att du `[channel-name]` har bytt ut mot önskad kanal:</span><span class="sxs-lookup"><span data-stu-id="a71f3-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="a71f3-147">Ange uppdateringsintervall</span><span class="sxs-lookup"><span data-stu-id="a71f3-147">Set update check frequency</span></span>

<span data-ttu-id="a71f3-148">Ändra hur ofta MAU söker efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a71f3-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-149">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-149">**Domain**</span></span> | <span data-ttu-id="a71f3-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-151">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-151">**Key**</span></span> | <span data-ttu-id="a71f3-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="a71f3-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="a71f3-153">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-153">**Data type**</span></span> | <span data-ttu-id="a71f3-154">Heltal</span><span class="sxs-lookup"><span data-stu-id="a71f3-154">Integer</span></span> |
| <span data-ttu-id="a71f3-155">**Standardvärde**</span><span class="sxs-lookup"><span data-stu-id="a71f3-155">**Default value**</span></span> | <span data-ttu-id="a71f3-156">720 (minuter)</span><span class="sxs-lookup"><span data-stu-id="a71f3-156">720 (minutes)</span></span> |
| <span data-ttu-id="a71f3-157">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="a71f3-157">**Comment**</span></span> | <span data-ttu-id="a71f3-158">Det här värdet anges i minuter.</span><span class="sxs-lookup"><span data-stu-id="a71f3-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="a71f3-159">Ändra hur MAU interagerar med uppdateringar</span><span class="sxs-lookup"><span data-stu-id="a71f3-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="a71f3-160">Ändra hur MAU söker efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a71f3-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-161">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-161">**Domain**</span></span> | <span data-ttu-id="a71f3-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-163">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-163">**Key**</span></span> | <span data-ttu-id="a71f3-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="a71f3-164">HowToCheck</span></span> |
| <span data-ttu-id="a71f3-165">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-165">**Data type**</span></span> | <span data-ttu-id="a71f3-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="a71f3-166">String</span></span> |
| <span data-ttu-id="a71f3-167">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="a71f3-167">**Possible values**</span></span> | <span data-ttu-id="a71f3-168">Manuellt</span><span class="sxs-lookup"><span data-stu-id="a71f3-168">Manual</span></span> <br/> <span data-ttu-id="a71f3-169">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="a71f3-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="a71f3-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="a71f3-170">AutomaticDownload</span></span> |
| <span data-ttu-id="a71f3-171">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="a71f3-171">**Comment**</span></span> |  <span data-ttu-id="a71f3-172">Observera att AutomaticDownload gör en nedladdning och installation utan att du behöver göra det.</span><span class="sxs-lookup"><span data-stu-id="a71f3-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="a71f3-173">Ändra om knappen Sök efter uppdateringar ska vara aktiverad</span><span class="sxs-lookup"><span data-stu-id="a71f3-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="a71f3-174">Ändra om lokala användare ska kunna klicka på alternativet "Sök efter uppdateringar" i användargränssnittet för Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="a71f3-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-175">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-175">**Domain**</span></span> | <span data-ttu-id="a71f3-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-177">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-177">**Key**</span></span> | <span data-ttu-id="a71f3-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="a71f3-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="a71f3-179">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-179">**Data type**</span></span> | <span data-ttu-id="a71f3-180">Boolesk</span><span class="sxs-lookup"><span data-stu-id="a71f3-180">Boolean</span></span> |
| <span data-ttu-id="a71f3-181">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="a71f3-181">**Possible values**</span></span> | <span data-ttu-id="a71f3-182">True (standard)</span><span class="sxs-lookup"><span data-stu-id="a71f3-182">True (default)</span></span> <br/> <span data-ttu-id="a71f3-183">False</span><span class="sxs-lookup"><span data-stu-id="a71f3-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="a71f3-184">Kryssrutan Inaktivera Insider</span><span class="sxs-lookup"><span data-stu-id="a71f3-184">Disable Insider checkbox</span></span>

<span data-ttu-id="a71f3-185">Inställd på sant för att göra "Gå med i Office Insider Program..." inte tillgänglig/nedtonad för användare.</span><span class="sxs-lookup"><span data-stu-id="a71f3-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-186">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-186">**Domain**</span></span> | <span data-ttu-id="a71f3-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-188">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-188">**Key**</span></span> | <span data-ttu-id="a71f3-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="a71f3-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="a71f3-190">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-190">**Data type**</span></span> | <span data-ttu-id="a71f3-191">Boolesk</span><span class="sxs-lookup"><span data-stu-id="a71f3-191">Boolean</span></span> |
| <span data-ttu-id="a71f3-192">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="a71f3-192">**Possible values**</span></span> | <span data-ttu-id="a71f3-193">False (standard)</span><span class="sxs-lookup"><span data-stu-id="a71f3-193">False (default)</span></span> <br/> <span data-ttu-id="a71f3-194">True</span><span class="sxs-lookup"><span data-stu-id="a71f3-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="a71f3-195">Begränsa telemetrin som skickas från MAU</span><span class="sxs-lookup"><span data-stu-id="a71f3-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="a71f3-196">Ange falskt om du vill skicka minimalt med data om hjärtslag, ingen programanvändning och ingen miljöinformation.</span><span class="sxs-lookup"><span data-stu-id="a71f3-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a71f3-197">**Domain**</span><span class="sxs-lookup"><span data-stu-id="a71f3-197">**Domain**</span></span> | <span data-ttu-id="a71f3-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a71f3-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a71f3-199">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="a71f3-199">**Key**</span></span> | <span data-ttu-id="a71f3-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="a71f3-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="a71f3-201">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="a71f3-201">**Data type**</span></span> | <span data-ttu-id="a71f3-202">Boolesk</span><span class="sxs-lookup"><span data-stu-id="a71f3-202">Boolean</span></span> |
| <span data-ttu-id="a71f3-203">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="a71f3-203">**Possible values**</span></span> | <span data-ttu-id="a71f3-204">True (standard)</span><span class="sxs-lookup"><span data-stu-id="a71f3-204">True (default)</span></span> <br/> <span data-ttu-id="a71f3-205">False</span><span class="sxs-lookup"><span data-stu-id="a71f3-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="a71f3-206">Exempel på konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="a71f3-206">Example configuration profile</span></span>

<span data-ttu-id="a71f3-207">Följande konfigurationsprofil används för att:</span><span class="sxs-lookup"><span data-stu-id="a71f3-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="a71f3-208">Placera enheten i Beta-kanalen</span><span class="sxs-lookup"><span data-stu-id="a71f3-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="a71f3-209">Ladda ned och installera uppdateringar automatiskt</span><span class="sxs-lookup"><span data-stu-id="a71f3-209">Automatically download and install updates</span></span>
- <span data-ttu-id="a71f3-210">Aktivera knappen Sök efter uppdateringar i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="a71f3-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="a71f3-211">Tillåt användare på enheten att registrera sig i Insider-kanalerna</span><span class="sxs-lookup"><span data-stu-id="a71f3-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="a71f3-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="a71f3-212">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
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

### <a name="intune"></a><span data-ttu-id="a71f3-213">Intune</span><span class="sxs-lookup"><span data-stu-id="a71f3-213">Intune</span></span>

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
            <string>Beta</string>
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

<span data-ttu-id="a71f3-214">Om du vill konfigurera MAU kan du distribuera den här konfigurationsprofilen från det hanteringsverktyg som företaget använder:</span><span class="sxs-lookup"><span data-stu-id="a71f3-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="a71f3-215">Från JAMF laddar du upp den här konfigurationsprofilen och anger preference domain *till com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="a71f3-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="a71f3-216">Från Intune laddar du upp den här konfigurationsprofilen och anger namnet på den anpassade konfigurationsprofilen *på com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="a71f3-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="a71f3-217">Resurser</span><span class="sxs-lookup"><span data-stu-id="a71f3-217">Resources</span></span>

- [<span data-ttu-id="a71f3-218">referens för msupdate</span><span class="sxs-lookup"><span data-stu-id="a71f3-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
