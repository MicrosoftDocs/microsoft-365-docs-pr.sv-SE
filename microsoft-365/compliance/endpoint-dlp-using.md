---
title: Använda Dataförlustskydd för slutpunkt
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Lär dig hur du konfigurerar principer för dataförlustskydd (DLP) så att platser för Dataförlustskydd för slutpunkt i Microsoft 365 används.
ms.openlocfilehash: cbd95ed3ee70b69b395f73c83852a9f37a269f0b
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259493"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="66d28-103">Använda Dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="66d28-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="66d28-104">Den här artikeln beskriver tre scenarier där du skapar och ändrar en DLP-princip som använder enheter som plats.</span><span class="sxs-lookup"><span data-stu-id="66d28-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="66d28-105">DLP-inställningar</span><span class="sxs-lookup"><span data-stu-id="66d28-105">DLP settings</span></span>

<span data-ttu-id="66d28-106">Innan du börjar bör du konfigurera DLP-inställningarna som tillämpas för alla DLP-principer för enheter.</span><span class="sxs-lookup"><span data-stu-id="66d28-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="66d28-107">Du måste konfigurera dessa om du tänker skapa principer som tillämpar:</span><span class="sxs-lookup"><span data-stu-id="66d28-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="66d28-108">begränsningar för utgående moln</span><span class="sxs-lookup"><span data-stu-id="66d28-108">cloud egress restrictions</span></span>
- <span data-ttu-id="66d28-109">begränsningar för otillåtna appar</span><span class="sxs-lookup"><span data-stu-id="66d28-109">unallowed apps restrictions</span></span>

<span data-ttu-id="66d28-110">Eller</span><span class="sxs-lookup"><span data-stu-id="66d28-110">Or</span></span>

- <span data-ttu-id="66d28-111">Om du vill utesluta störande filsökvägar från övervakning</span><span class="sxs-lookup"><span data-stu-id="66d28-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="66d28-112">![DLP-inställningar](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="66d28-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="66d28-113">Sökvägsundantag</span><span class="sxs-lookup"><span data-stu-id="66d28-113">File path exclusions</span></span>

<span data-ttu-id="66d28-114">Du kanske vill utesluta vissa sökvägar från DLP-övervakning, DLP-aviseringar och tillämpning av DLP-principen på dina enheter eftersom de är för störande eller inte innehåller filer som du är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="66d28-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="66d28-115">Filer på dessa platser granskas inte och filer som skapas eller ändras på dessa platser omfattas inte av tillämpningen av DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="66d28-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="66d28-116">Du kan konfigurera sökvägsundantag i DLP-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="66d28-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="66d28-117">Du kan använda den här logiken för att skapa undantagssökvägarna:</span><span class="sxs-lookup"><span data-stu-id="66d28-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="66d28-118">Giltig sökväg som slutar med ”\”, vilket innebär endast filer direkt under mappen.</span><span class="sxs-lookup"><span data-stu-id="66d28-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="66d28-119">Till exempel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="66d28-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="66d28-120">Giltig sökväg som slutar med ”\*”, vilket innebär endast filer under undermappar, förutom filerna direkt under mappen.</span><span class="sxs-lookup"><span data-stu-id="66d28-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="66d28-121">Till exempel: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="66d28-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="66d28-122">Giltig sökväg som slutar utan ”\” eller ”\*”, vilket innebär alla filer direkt under mappen och alla undermappar.</span><span class="sxs-lookup"><span data-stu-id="66d28-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="66d28-123">Till exempel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="66d28-123">For example: C:\Temp</span></span>

- <span data-ttu-id="66d28-124">En sökväg med jokertecken mellan ”\” på varje sida.</span><span class="sxs-lookup"><span data-stu-id="66d28-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="66d28-125">Till exempel: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="66d28-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="66d28-126">En sökväg med jokertecken mellan ”\” på varje sida och med ”(siffra)” för att ge exakt antal undermappar.</span><span class="sxs-lookup"><span data-stu-id="66d28-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="66d28-127">Till exempel: C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="66d28-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="66d28-128">En sökväg med SYSTEM-miljövariabler.</span><span class="sxs-lookup"><span data-stu-id="66d28-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="66d28-129">Till exempel: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="66d28-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="66d28-130">En blandning av ovanstående alternativ.</span><span class="sxs-lookup"><span data-stu-id="66d28-130">A mix of all the above.</span></span> <br/><span data-ttu-id="66d28-131">Till exempel: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="66d28-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="66d28-132">Otillåtna appar</span><span class="sxs-lookup"><span data-stu-id="66d28-132">Unallowed apps</span></span>

<span data-ttu-id="66d28-133">När en princips inställning för **åtkomst via appar och webbläsare som inte tillåts** är aktiverad och användare försöker använda apparna för att få åtkomst till en skyddad fil kommer aktiviteten att tillåtas, blockeras eller blockeras med möjlighet för användare att åsidosätta begränsningen.</span><span class="sxs-lookup"><span data-stu-id="66d28-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="66d28-134">Alla aktiviteter granskas och är tillgängliga för granskning i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66d28-135">Ta inte med sökvägen för den körbara filen utan bara den körbara filens namn (till exempel browser.exe).</span><span class="sxs-lookup"><span data-stu-id="66d28-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="66d28-136">Begränsningar för webbläsare och domäner</span><span class="sxs-lookup"><span data-stu-id="66d28-136">Browser and domain restrictions</span></span>
<span data-ttu-id="66d28-137">Begränsa känsliga filer som matchar dina principer från att delas med obegränsade molntjänstdomäner.</span><span class="sxs-lookup"><span data-stu-id="66d28-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="66d28-138">Tjänstdomäner</span><span class="sxs-lookup"><span data-stu-id="66d28-138">Service domains</span></span>

<span data-ttu-id="66d28-139">Du kan styra om känsliga filer som skyddas av dina principer kan laddas upp till specifika tjänstdomäner från Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="66d28-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="66d28-140">Om listläget är inställt på **Blockera** kan användaren inte ladda upp känsliga objekt till dessa domäner.</span><span class="sxs-lookup"><span data-stu-id="66d28-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="66d28-141">När en uppladdningsåtgärd blockeras på grund av att ett objekt matchar en DLP-princip genererar DLP antingen en varning eller blockerar uppladdningen av det känsliga objektet.</span><span class="sxs-lookup"><span data-stu-id="66d28-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="66d28-142">Om listläget är inställt på **Tillåt** kan användarna **_bara_** ladda upp känsliga objekt till de domänerna, och uppladdningsåtkomst till alla andra domäner tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="66d28-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66d28-143">När tjänstens begränsningsläge är inställd på ”Tillåt” måste du ha minst en tjänstdomän konfigurerad innan begränsningarna tillämpas.</span><span class="sxs-lookup"><span data-stu-id="66d28-143">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="66d28-144">Otillåtna webbläsare</span><span class="sxs-lookup"><span data-stu-id="66d28-144">Unallowed browsers</span></span>

<span data-ttu-id="66d28-145">Du lägger till webbläsare, som identifieras av sina körbara filnamn, som blockeras från att komma åt filer som matchar villkoren för en tillämpad DLP-princip där begränsningen för uppladdning till molntjänster är inställd på blockering eller blockering och åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="66d28-145">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="66d28-146">När dessa webbläsare blockeras från att komma åt en fil får slutanvändarna ett popup-meddelande om att de ska öppna filen via Microsoft Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="66d28-146">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="66d28-147">Affärsmotivering i principtips</span><span class="sxs-lookup"><span data-stu-id="66d28-147">Business justification in policy tips</span></span>

<span data-ttu-id="66d28-148">Du kan styra hur användare interagerar med alternativet för affärsmotivering i DLP-principtipsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="66d28-148">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="66d28-149">Det här alternativet visas när användare utför en aktivitet som skyddas av inställningen **Blockera med åsidosättning** i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="66d28-149">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="66d28-150">Du kan välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="66d28-150">You can choose from one the following options:</span></span>

- <span data-ttu-id="66d28-151">Som standard kan användare välja antingen en inbyggd motivering eller ange egen text.</span><span class="sxs-lookup"><span data-stu-id="66d28-151">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="66d28-152">Användare kan bara välja en inbyggd motivering.</span><span class="sxs-lookup"><span data-stu-id="66d28-152">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="66d28-153">Användare kan bara ange en egen motivering.</span><span class="sxs-lookup"><span data-stu-id="66d28-153">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="66d28-154">Binda samman DLP-inställningar</span><span class="sxs-lookup"><span data-stu-id="66d28-154">Tying DLP settings together</span></span>

<span data-ttu-id="66d28-155">Med DLP för slutpunkt och Microsoft Edge Chromium-webbläsaren kan du begränsa oavsiktlig delning av känsliga objekt till otillåtna molnappar och tjänster.</span><span class="sxs-lookup"><span data-stu-id="66d28-155">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="66d28-156">Microsoft Edge Chromium vet när ett objekt begränsas av en DLP-princip för slutpunkt och tillämpar åtkomstbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="66d28-156">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="66d28-157">Om du använder DLP för slutpunkt som en plats i en korrekt konfigurerad DLP-princip och Microsoft Edge Chromium-webbläsaren förhindras de otillåtna webbläsare som du har definierat i de här inställningarna från att komma åt känsliga objekt som matchar dina DLP-principkontroller.</span><span class="sxs-lookup"><span data-stu-id="66d28-157">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="66d28-158">Istället omdirigeras användarna till att använda Microsoft Edge Chromium och Microsoft Edge Chromium, som med sin förståelse av DLP-införda begränsningar kan blockera eller begränsa aktiviteter när villkoren i DLP-principen uppfylls.</span><span class="sxs-lookup"><span data-stu-id="66d28-158">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="66d28-159">För att använda den här begränsningen måste du konfigurera tre viktiga delar:</span><span class="sxs-lookup"><span data-stu-id="66d28-159">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="66d28-160">Ange platser – tjänster, domäner, IP-adresser – som du vill förhindra att känsliga objekt delas till.</span><span class="sxs-lookup"><span data-stu-id="66d28-160">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="66d28-161">Lägg till de webbläsare som inte tillåts komma åt vissa känsliga objekt när en DLP-principmatchning inträffar.</span><span class="sxs-lookup"><span data-stu-id="66d28-161">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="66d28-162">Konfigurera DLP-principer för att definiera typerna av känsliga objekt vars uppladdning ska begränsas till endast dessa platser genom att aktivera alternativet för att **ladda upp till molntjänster** och **åtkomst av otillåten webbläsare**.</span><span class="sxs-lookup"><span data-stu-id="66d28-162">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="66d28-163">Du kan fortsätta att lägga till nya tjänster, program och principer för att utöka begränsningarna så att de uppfyller verksamhetens behov och skyddar känsliga data.</span><span class="sxs-lookup"><span data-stu-id="66d28-163">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="66d28-164">Den här konfigurationen säkerställer att dina data förblir säkra samtidigt som du undviker onödiga begränsningar som förhindrar eller begränsar användare från att komma åt och dela icke-känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="66d28-164">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="66d28-165">Scenarier för DLP-principer för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="66d28-165">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="66d28-166">För att bekanta dig med DLP-funktioner för slutpunkt, och hur de visar sig i DLP-principer, har vi skapat scenarier som du kan följa.</span><span class="sxs-lookup"><span data-stu-id="66d28-166">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66d28-167">De här DLP-scenarierna för slutpunkt är inte officiella procedurer för att skapa och justera DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="66d28-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="66d28-168">Läs följande avsnitt om du behöver arbeta med DLP-principer i allmänna situationer:</span><span class="sxs-lookup"><span data-stu-id="66d28-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>

>- [<span data-ttu-id="66d28-169">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="66d28-169">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="66d28-170">Kom igång med DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="66d28-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="66d28-171">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="66d28-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="66d28-172">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="66d28-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="66d28-173">Scenario 1: Skapa en princip från en mall, endast granskning</span><span class="sxs-lookup"><span data-stu-id="66d28-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="66d28-174">De här scenarierna kräver att du redan har enheter som har registrerats och rapporterar till aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="66d28-175">Om du inte har registrerat enheter än kan du läsa mer i [Komma igång med dataförlustskydd för slutpunkter](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="66d28-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="66d28-176">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="66d28-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="66d28-177">Välj **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="66d28-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="66d28-178">I det här scenariot väljer du **Sekretess** och **Amerikanska PII-data (personligt identifierbar information)**, och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="66d28-179">Inaktivera fältet **Status** för alla platser utom **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="66d28-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="66d28-180">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-180">Choose **Next**.</span></span>

5. <span data-ttu-id="66d28-181">Acceptera standardalternativet för att **granska och anpassa inställningarna från mallen** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="66d28-182">Acceptera standardvärdena för **Skyddsåtgärder** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="66d28-183">Välj **Granska eller begränsa aktiviteter på Windows-enheter** och låt åtgärderna vara inställda på **Granska endast**.</span><span class="sxs-lookup"><span data-stu-id="66d28-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="66d28-184">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-184">Choose **Next**.</span></span>

8. <span data-ttu-id="66d28-185">Acceptera standardvärdet **Jag vill testa först** och välj **Visa principtips när testläge används**.</span><span class="sxs-lookup"><span data-stu-id="66d28-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="66d28-186">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="66d28-186">Choose **Next**.</span></span>

9. <span data-ttu-id="66d28-187">Granska inställningarna och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="66d28-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="66d28-188">Den nya DLP-principen visas i principlistan.</span><span class="sxs-lookup"><span data-stu-id="66d28-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="66d28-189">Sök efter data från de övervakade slutpunkterna i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="66d28-190">Ange platsfiltret för enheter och lägg till principen. Filtrera sedan efter principnamn om du vill se den här principens påverkan.</span><span class="sxs-lookup"><span data-stu-id="66d28-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="66d28-191">Du kan läsa mer i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) om det behövs.</span><span class="sxs-lookup"><span data-stu-id="66d28-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="66d28-192">Försök dela ett test som innehåller innehåll som utlöser villkoret för amerikanska PII-data (personligt identifierbar information) med någon utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="66d28-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="66d28-193">Det här borde utlösa principen.</span><span class="sxs-lookup"><span data-stu-id="66d28-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="66d28-194">Sök efter händelsen i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="66d28-195">Scenario 2: Ändra den befintliga principen, ange en avisering</span><span class="sxs-lookup"><span data-stu-id="66d28-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="66d28-196">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="66d28-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="66d28-197">Välj principen **Amerikanska PII-data (personligt identifierbar information)** som du skapade i det första scenariot.</span><span class="sxs-lookup"><span data-stu-id="66d28-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="66d28-198">Välj **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="66d28-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="66d28-199">Gå till sidan **Avancerade DLP-regler** och redigera alternativet för **En liten mängd innehåll upptäcktes. USA:s PII**.</span><span class="sxs-lookup"><span data-stu-id="66d28-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="66d28-200">Bläddra ned till avsnittet **Incidentrapporter** och ställ in **Skicka en varning till administratörer när en regelmatchning inträffar** på **På**.</span><span class="sxs-lookup"><span data-stu-id="66d28-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="66d28-201">E-postaviseringar skickas automatiskt till administratören och alla andra du lägger till i listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="66d28-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66d28-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="66d28-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="66d28-203">Välj **Skicka en avisering varje gång en aktivitet matchar regeln** för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="66d28-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="66d28-204">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="66d28-204">Choose **Save**.</span></span>

8. <span data-ttu-id="66d28-205">Behåll alla tidigare inställningar genom att välja **Nästa** och **Skicka** sedan principändringarna.</span><span class="sxs-lookup"><span data-stu-id="66d28-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="66d28-206">Försök dela ett test som innehåller innehåll som utlöser villkoret för amerikanska PII-data (personligt identifierbar information) med någon utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="66d28-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="66d28-207">Det här borde utlösa principen.</span><span class="sxs-lookup"><span data-stu-id="66d28-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="66d28-208">Sök efter händelsen i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="66d28-209">Scenario 3: Ändra den befintliga principen, blockera åtgärden med tillåten åsidosättning</span><span class="sxs-lookup"><span data-stu-id="66d28-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="66d28-210">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="66d28-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="66d28-211">Välj principen **Amerikanska PII-data (personligt identifierbar information)** som du skapade i det första scenariot.</span><span class="sxs-lookup"><span data-stu-id="66d28-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="66d28-212">Välj **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="66d28-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="66d28-213">Gå till sidan **Avancerade DLP-regler** och redigera alternativet för **En liten mängd innehåll upptäcktes. USA:s PII**.</span><span class="sxs-lookup"><span data-stu-id="66d28-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="66d28-214">Bläddra ned till avsnittet **Granska eller begränsa aktiviteter på Windows-enheter**. För varje aktivitet anger du motsvarande åtgärd till  **Blockera med åsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="66d28-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66d28-215">![ange åtgärd för att blockera med åsidosättning](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="66d28-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="66d28-216">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="66d28-216">Choose **Save**.</span></span>

7. <span data-ttu-id="66d28-217">Upprepa steg 4–7 för **En stor mängd innehåll upptäcktes. USA:s PII**.</span><span class="sxs-lookup"><span data-stu-id="66d28-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="66d28-218">Behåll alla tidigare inställningar genom att välja **Nästa** och **Skicka** sedan principändringarna.</span><span class="sxs-lookup"><span data-stu-id="66d28-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="66d28-219">Försök dela ett test som innehåller innehåll som utlöser villkoret för amerikanska PII-data (personligt identifierbar information) med någon utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="66d28-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="66d28-220">Det här borde utlösa principen.</span><span class="sxs-lookup"><span data-stu-id="66d28-220">This should trigger the policy.</span></span>

   <span data-ttu-id="66d28-221">Ett popup-fönster som det här visas på klientenheten:</span><span class="sxs-lookup"><span data-stu-id="66d28-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66d28-222">![blockeringsmeddelande med åsidosättning i klienten för dlp för slutpunkt](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="66d28-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="66d28-223">Sök efter händelsen i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="66d28-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d28-224">Se även</span><span class="sxs-lookup"><span data-stu-id="66d28-224">See also</span></span>

- [<span data-ttu-id="66d28-225">Mer information om dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="66d28-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="66d28-226">Komma igång med dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="66d28-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="66d28-227">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="66d28-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="66d28-228">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="66d28-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="66d28-229">Kom igång med Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="66d28-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="66d28-230">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="66d28-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="66d28-231">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="66d28-231">Onboarding tools and methods for Windows 10 machines</span></span>](/microsoft-365/compliance/dlp-configure-endpoints)
- [<span data-ttu-id="66d28-232">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="66d28-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="66d28-233">Azure Active Directory (AAD)-ansluten</span><span class="sxs-lookup"><span data-stu-id="66d28-233">Azure Active Directory (AAD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="66d28-234">Ladda ned nya Microsoft Edge som baseras på Chromium</span><span class="sxs-lookup"><span data-stu-id="66d28-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="66d28-235">Kom igång med DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="66d28-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="66d28-236">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="66d28-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
