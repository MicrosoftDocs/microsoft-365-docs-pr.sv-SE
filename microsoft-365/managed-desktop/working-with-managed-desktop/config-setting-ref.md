---
title: Referens för konfigurerbara inställningar för Microsoft Managed Desktop
description: Ange kategorier för konfigurerbara inställningar i Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917710"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="a7b26-104">Referens för konfigurerbara inställningar – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a7b26-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a7b26-105">Det här avsnittet innehåller de inställningskategorier som kunder kan konfigurera med Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="a7b26-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a7b26-106">Varje inställningskategori innehåller information om krav, metodtips och hur du anpassar inställningskategorin.</span><span class="sxs-lookup"><span data-stu-id="a7b26-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="a7b26-107">Bild av skrivbordsbakgrund</span><span class="sxs-lookup"><span data-stu-id="a7b26-107">Desktop background picture</span></span>
<span data-ttu-id="a7b26-108">Du kan anpassa skrivbordsbakgrunden för Microsoft Managed Desktop-enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a7b26-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="a7b26-109">Du kan använda detta för att tillämpa ett företags varumärke eller marknadsföringsmaterial.</span><span class="sxs-lookup"><span data-stu-id="a7b26-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a7b26-110">Krav</span><span class="sxs-lookup"><span data-stu-id="a7b26-110">Requirements</span></span>

<span data-ttu-id="a7b26-111">Dessa krav måste vara uppfyllda för en bakgrundsbild på skrivbordet:</span><span class="sxs-lookup"><span data-stu-id="a7b26-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="a7b26-112">Bildfilformat – .jpg, jpeg eller .png</span><span class="sxs-lookup"><span data-stu-id="a7b26-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="a7b26-113">Filplats – värd för en betrodd säker http (https)-plats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="a7b26-114">Tillåts inte – Http- och filresursplatser (unc) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="a7b26-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="a7b26-115">Anpassa och distribuera skrivbordsbakgrund</span><span class="sxs-lookup"><span data-stu-id="a7b26-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="a7b26-116">**Så här lägger du till en egen bakgrundsbild på skrivbordet**</span><span class="sxs-lookup"><span data-stu-id="a7b26-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="a7b26-117">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-117">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-118">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-118">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-119">Välj  Skrivbordsbakgrundsbild **i arbetsytan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-119">In **Settings** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="a7b26-120">Ange platsen för den bild du vill använda.</span><span class="sxs-lookup"><span data-stu-id="a7b26-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="a7b26-121">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="a7b26-122">Startsidor för webbläsare</span><span class="sxs-lookup"><span data-stu-id="a7b26-122">Browser start pages</span></span>
<span data-ttu-id="a7b26-123">Webbläsaren startar sidor öppna på enskilda flikar när användarna startar Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a7b26-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="a7b26-124">Om du vill göra det enkelt för användarna att öppna en uppsättning webbplatser som de använder ofta kan du lägga till en startsida för webbläsaren för varje webbplats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a7b26-125">Krav</span><span class="sxs-lookup"><span data-stu-id="a7b26-125">Requirements</span></span>

<span data-ttu-id="a7b26-126">Du måste ange det fullständigt kvalificerade domännamnet (FQDN) för intranätwebbplatser eller internetwebbplatser för webbläsarens startsidor.</span><span class="sxs-lookup"><span data-stu-id="a7b26-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="a7b26-127">Om interna webbplatser konfigureras bör du meddela användarna att åtkomst till dessa webbplatser endast är tillåten när de är anslutna till det interna nätverket på kontoret, eller när de är anslutna till en VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="a7b26-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="a7b26-128">Anpassa och distribuera startsidor i webbläsare</span><span class="sxs-lookup"><span data-stu-id="a7b26-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="a7b26-129">**Så här lägger du till en startsida för en webbläsare**</span><span class="sxs-lookup"><span data-stu-id="a7b26-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="a7b26-130">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-130">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-131">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-131">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-132">Välj **Webbläsarens** startsidor **i arbetsytan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-132">In **Settings** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="a7b26-133">Välj **Lägg till startsida.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="a7b26-134">På **startsidan för Lägg till webbläsare** anger du URL-adressen för den webbplats du vill använda och väljer sedan Lägg till **startsida.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="a7b26-135">Upprepa steg 1–5 för ytterligare startsidor i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="a7b26-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="a7b26-136">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="a7b26-137">Plats för webbplatslista i företagsläge</span><span class="sxs-lookup"><span data-stu-id="a7b26-137">Enterprise mode site list location</span></span>

<span data-ttu-id="a7b26-138">Om du har specifika webbplatser och program som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplatslistan i Företagsläge så att webbplatserna öppnas automatiskt med hjälp av Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a7b26-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="a7b26-139">Om du vet att dina intranätplatser inte fungerar som de ska med Microsoft Edge kan du ställa in så att alla intranätwebbplatser öppnas med hjälp av Internet Explorer 11 automatiskt.</span><span class="sxs-lookup"><span data-stu-id="a7b26-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="a7b26-140">Om du använder företagsläget kan du fortsätta att använda Microsoft Edge som standardwebbläsare, samtidigt som du ser till att dina program fortsätter att arbeta med Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a7b26-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="a7b26-141">Mer information om webbplatslistor för företagsläge finns i [Webbplatslistor för företagsläge och Företagsläge.](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)</span><span class="sxs-lookup"><span data-stu-id="a7b26-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="a7b26-142">Du kan ange https:// plats eller plats för en intern delning där du har lagrat webbplatslistan i företagsläget.</span><span class="sxs-lookup"><span data-stu-id="a7b26-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a7b26-143">Krav</span><span class="sxs-lookup"><span data-stu-id="a7b26-143">Requirements</span></span>

<span data-ttu-id="a7b26-144">De här kraven måste uppfyllas för listfilen för företagswebbplatser:</span><span class="sxs-lookup"><span data-stu-id="a7b26-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="a7b26-145">Filformat – XML-fil som uppfyller [filkraven](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="a7b26-145">File format - XML file that meets [file requirements](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="a7b26-146">Filplats – värdfil på en intern https-plats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="a7b26-147">Tillåts inte – Värd för en intern filresurs, t.ex. *//sharename,* är inte tillåtet</span><span class="sxs-lookup"><span data-stu-id="a7b26-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="a7b26-148">Metodtips</span><span class="sxs-lookup"><span data-stu-id="a7b26-148">Best practices</span></span>

<span data-ttu-id="a7b26-149">Dessa metodtips erbjuds för att hjälpa kunder fatta beslut om att modernisera IT-infrastrukturen:</span><span class="sxs-lookup"><span data-stu-id="a7b26-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="a7b26-150">**Välj ett begränsat antal webbplatser** – Microsoft Managed Desktop använder Microsoft Edge som standardwebbläsare för att förbättra organisationens säkerhet och användbarhet för användarna.</span><span class="sxs-lookup"><span data-stu-id="a7b26-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="a7b26-151">De flesta webbplatser i den här listan gäller äldre webbappar som behöver en äldre version av en webbläsare som inte innehåller lika många säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="a7b26-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="a7b26-152">**Det kan vara** en alternativ metod – du kan överväga en annan webbplats eller ett annat webbapp som inte kräver en äldre webbläsare.</span><span class="sxs-lookup"><span data-stu-id="a7b26-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="a7b26-153">Du kan även uppdatera webbplatsen så att den kan använda nyare webbläsare.</span><span class="sxs-lookup"><span data-stu-id="a7b26-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="a7b26-154">Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.</span><span class="sxs-lookup"><span data-stu-id="a7b26-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="a7b26-155">Anpassa och distribuera listplats för webbplatsläge för företag</span><span class="sxs-lookup"><span data-stu-id="a7b26-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="a7b26-156">**Så här lägger du till en plats för en företagswebbplatslista**</span><span class="sxs-lookup"><span data-stu-id="a7b26-156">**To add an enterprise site mode list location**</span></span>

1. <span data-ttu-id="a7b26-157">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-157">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-158">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-158">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-159">I **arbetsytan Inställningar** väljer du Plats för **webbplatslista i företagsläge.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-159">In **Settings** workspace, select **Enterprise mode site list location**.</span></span> 
4. <span data-ttu-id="a7b26-160">Ange webbplatslistans https-plats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-160">Enter the https location for your site list.</span></span> 
5. <span data-ttu-id="a7b26-161">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="a7b26-162">Betrodda platser</span><span class="sxs-lookup"><span data-stu-id="a7b26-162">Trusted sites</span></span>

<span data-ttu-id="a7b26-163">Med betrodda platser kan du anpassa säkerhetszoner eller var en webbplats kan användas för olika webbplatser.</span><span class="sxs-lookup"><span data-stu-id="a7b26-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="a7b26-164">Säkerhetszoner omfattar:</span><span class="sxs-lookup"><span data-stu-id="a7b26-164">Security zones include:</span></span> 
- <span data-ttu-id="a7b26-165">Zon 1 – Lokalt intranät</span><span class="sxs-lookup"><span data-stu-id="a7b26-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="a7b26-166">Zon 2 – Betrodda platser</span><span class="sxs-lookup"><span data-stu-id="a7b26-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="a7b26-167">Zon 3 – Internetzon</span><span class="sxs-lookup"><span data-stu-id="a7b26-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="a7b26-168">Zon 4 – zonen Begränsade platser</span><span class="sxs-lookup"><span data-stu-id="a7b26-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="a7b26-169">Krav</span><span class="sxs-lookup"><span data-stu-id="a7b26-169">Requirements</span></span>

<span data-ttu-id="a7b26-170">Ange det fullständigt kvalificerade domännamnet (FQDN) för intranätwebbplatser eller Internetwebbplatser för varje betrodd webbplats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="a7b26-171">Anpassa och distribuera betrodda webbplatser</span><span class="sxs-lookup"><span data-stu-id="a7b26-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="a7b26-172">**Lägga till en betrodd webbplats**</span><span class="sxs-lookup"><span data-stu-id="a7b26-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="a7b26-173">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-173">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-174">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-174">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-175">I **arbetsytan** Inställningar väljer du **Betrodda platser** och sedan Lägg till betrodd **webbplats**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-175">In **Settings** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="a7b26-176">På **Lägg till betrodd** webbplats anger du URL-adressen, väljer en säkerhetszon och väljer sedan Lägg till betrodd **webbplats.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="a7b26-177">Upprepa steg 1–4 för varje betrodd webbplats som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="a7b26-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="a7b26-178">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="a7b26-179">**Ta bort en betrodd webbplats**</span><span class="sxs-lookup"><span data-stu-id="a7b26-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="a7b26-180">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-180">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-181">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-181">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-182">Välj **Betrodda** platser **i arbetsytan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-182">In **Settings** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="a7b26-183">Markera den webbplats du vill ta bort och välj sedan Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="a7b26-184">Upprepa steg 1–4 för varje betrodd webbplats som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="a7b26-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="a7b26-185">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="a7b26-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="a7b26-186">Proxy</span></span>
<span data-ttu-id="a7b26-187">Du kan hantera nätverkets proxyinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a7b26-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="a7b26-188">Lägg till din proxyserver och portnummer och lägg sedan till undantag för din proxywebbplats.</span><span class="sxs-lookup"><span data-stu-id="a7b26-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="a7b26-189">Microsoft Managed Desktop innehåller en uppsättning standardundantag för proxy som krävs för att tjänsten ska fungera.</span><span class="sxs-lookup"><span data-stu-id="a7b26-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="a7b26-190">Standard undantagslistan kan bara ändras av Microsofts tjänst för hanterad dator.</span><span class="sxs-lookup"><span data-stu-id="a7b26-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="a7b26-191">Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop.](../get-ready/network.md)</span><span class="sxs-lookup"><span data-stu-id="a7b26-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="a7b26-192">Undantagen för proxywebbplatser som du lägger till i Microsoft Managed Desktop-portalen läggs till i standardproxyundantagen som ingår i Microsoft Managed Desktop-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a7b26-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="a7b26-193">Uppdatering av standardlistan över proxyservrar prioriteras alltid före kunddistributioner.</span><span class="sxs-lookup"><span data-stu-id="a7b26-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="a7b26-194">Det innebär att den fasade distributionen pausas om det finns en distribution för standardlistan med proxy-undantag.</span><span class="sxs-lookup"><span data-stu-id="a7b26-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="a7b26-195">Krav</span><span class="sxs-lookup"><span data-stu-id="a7b26-195">Requirements</span></span>

<span data-ttu-id="a7b26-196">De här kraven måste vara uppfyllda för proxyserver- och proxywebbplatsundantag:</span><span class="sxs-lookup"><span data-stu-id="a7b26-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="a7b26-197">Måste vara en giltig serveradress och ett giltigt portnummer</span><span class="sxs-lookup"><span data-stu-id="a7b26-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="a7b26-198">URL-adresser måste vara giltiga på http-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="a7b26-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="a7b26-199">Anpassa och distribuera proxy proxy</span><span class="sxs-lookup"><span data-stu-id="a7b26-199">Customize and deploy proxies</span></span>

<span data-ttu-id="a7b26-200">**Lägga till ett enskilt proxywebbplatsantag**</span><span class="sxs-lookup"><span data-stu-id="a7b26-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="a7b26-201">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="a7b26-201">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a7b26-202">Titta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-202">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a7b26-203">Välj **Proxy** i arbetsytan **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="a7b26-203">In **Settings** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="a7b26-204">Ange **adress-** och **portnumret för** proxyservern och välj sedan Lägg **till proxy-undantag**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="a7b26-205">Ange URL-adressen till en giltig http-webbplats och välj sedan **Lägg till proxy-undantag**.</span><span class="sxs-lookup"><span data-stu-id="a7b26-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="a7b26-206">Upprepa steg 1–5 för varje betrodd webbplats som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="a7b26-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="a7b26-207">Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="a7b26-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7b26-208">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a7b26-208">Additional resources</span></span>
- [<span data-ttu-id="a7b26-209">Översikt över konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="a7b26-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="a7b26-210">Distribuera inställningar som kan konfigureras</span><span class="sxs-lookup"><span data-stu-id="a7b26-210">Deploy configurable settings</span></span>](config-setting-deploy.md)