---
title: Konfigurerbar inställningsreferens för Microsoft Managed Desktop
description: Ange kategorier för konfigurerbara inställningar i Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a405f96ee7a113197fbc9c237779db3e3e5e5ca
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812935"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="79f0c-104">Konfigurerbar inställningsreferens - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79f0c-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="79f0c-105">I det här avsnittet visas de inställningskategorier som kunder kan konfigurera med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="79f0c-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="79f0c-106">Varje inställningskategori innehåller information om krav, metodtips och hur du anpassar inställningskategorin.</span><span class="sxs-lookup"><span data-stu-id="79f0c-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="79f0c-107">Bakgrundsbild på skrivbordet</span><span class="sxs-lookup"><span data-stu-id="79f0c-107">Desktop background picture</span></span>
<span data-ttu-id="79f0c-108">Du kan anpassa skrivbordsbakgrundsbilden för Microsoft Hanterade stationära enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="79f0c-109">Du kan använda detta för att tillämpa ett företags varumärke eller marknadsföringsmaterial.</span><span class="sxs-lookup"><span data-stu-id="79f0c-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="79f0c-110">Krav</span><span class="sxs-lookup"><span data-stu-id="79f0c-110">Requirements</span></span>

<span data-ttu-id="79f0c-111">Dessa krav måste uppfyllas för en skrivbordsbakgrundsbild:</span><span class="sxs-lookup"><span data-stu-id="79f0c-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="79f0c-112">Bildfilformat - .jpg, jpeg eller .png</span><span class="sxs-lookup"><span data-stu-id="79f0c-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="79f0c-113">Filplats - Värd på en betrodd säker http-plats (https).</span><span class="sxs-lookup"><span data-stu-id="79f0c-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="79f0c-114">Tillåts inte - Http- och fildelningsplatser (unc) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="79f0c-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="79f0c-115">Anpassa och distribuera skrivbordsbakgrundsbild</span><span class="sxs-lookup"><span data-stu-id="79f0c-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="79f0c-116">**Så här lägger du till en anpassad skrivbordsbakgrundsbild**</span><span class="sxs-lookup"><span data-stu-id="79f0c-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="79f0c-117">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-117">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="79f0c-118">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="79f0c-119">I **Konfigurerbar** arbetsyta väljer du **Skrivbordsbakgrundsbild**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="79f0c-120">Ange platsen för den bild som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="79f0c-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="79f0c-121">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="79f0c-122">Startsidor för webbläsare</span><span class="sxs-lookup"><span data-stu-id="79f0c-122">Browser start pages</span></span>
<span data-ttu-id="79f0c-123">Startsidor i webbläsaren öppnas på enskilda flikar när användarna startar Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="79f0c-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="79f0c-124">Om du vill göra det enkelt för användarna att öppna en uppsättning webbplatser som de använder ofta lägger du till en startsida för webbläsaren för varje webbplats.</span><span class="sxs-lookup"><span data-stu-id="79f0c-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="79f0c-125">Krav</span><span class="sxs-lookup"><span data-stu-id="79f0c-125">Requirements</span></span>

<span data-ttu-id="79f0c-126">Du måste ange det fullständigt kvalificerade domännamnet (FQDN) för intranät eller webbplatser för din webbläsares startsidor.</span><span class="sxs-lookup"><span data-stu-id="79f0c-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="79f0c-127">Om interna platser är konfigurerade meddelar du användarna att åtkomst till dessa platser endast är tillåten när den är ansluten till det interna nätverket när de är på kontoret eller när de är anslutna till en VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="79f0c-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="79f0c-128">Anpassa och distribuera startsidor för webbläsare</span><span class="sxs-lookup"><span data-stu-id="79f0c-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="79f0c-129">**Så här lägger du till en startsida för webbläsaren**</span><span class="sxs-lookup"><span data-stu-id="79f0c-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="79f0c-130">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-130">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="79f0c-131">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="79f0c-132">I **Konfigurerbar** arbetsyta väljer du **Startsidor för webbläsare**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="79f0c-133">Välj **Lägg till startsida**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="79f0c-134">På **Startsidan För Lägg till webbläsare**anger du URL:en för den webbplats som du vill använda och väljer sedan Lägg till **startsida**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="79f0c-135">Upprepa steg 1-5 för ytterligare startsidor i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="79f0c-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="79f0c-136">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="79f0c-137">Plats för plats i företagslägeslistan</span><span class="sxs-lookup"><span data-stu-id="79f0c-137">Enterprise mode site list location</span></span>

<span data-ttu-id="79f0c-138">Om du har specifika webbplatser och appar som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplatslistan för Företagsläge så att webbplatserna öppnas automatiskt med Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="79f0c-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="79f0c-139">Om du vet att intranätplatserna inte fungerar korrekt med Microsoft Edge kan du dessutom ställa in alla intranätplatser så att de öppnas automatiskt med Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="79f0c-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="79f0c-140">Att använda Företagsläge innebär att du kan fortsätta att använda Microsoft Edge som standardwebbläsare, samtidigt som du ser till att dina appar fortsätter att fungera i Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="79f0c-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="79f0c-141">Mer information om webbplatslistor för företagsläge finns i [Platslistor för företagsläge och företagsläge](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span><span class="sxs-lookup"><span data-stu-id="79f0c-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="79f0c-142">Du kan ange en https:// plats eller platsen för en intern resurs där du har varit värd för webbplatslistan för företagsläge.</span><span class="sxs-lookup"><span data-stu-id="79f0c-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="79f0c-143">Krav</span><span class="sxs-lookup"><span data-stu-id="79f0c-143">Requirements</span></span>

<span data-ttu-id="79f0c-144">Dessa krav måste uppfyllas för platsfilen för företagsläge:</span><span class="sxs-lookup"><span data-stu-id="79f0c-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="79f0c-145">Filformat - XML-fil som uppfyller [filkraven](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="79f0c-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="79f0c-146">Filplats - Värdfil på en intern https-plats.</span><span class="sxs-lookup"><span data-stu-id="79f0c-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="79f0c-147">Inte tillåtet - Hosting på en intern filresurs, till *exempel //sharename*, är inte tillåtet</span><span class="sxs-lookup"><span data-stu-id="79f0c-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="79f0c-148">Metodtips</span><span class="sxs-lookup"><span data-stu-id="79f0c-148">Best practices</span></span>

<span data-ttu-id="79f0c-149">Dessa bästa metoder erbjuds för att hjälpa kunderna att fatta beslut om att modernisera sin IT-infrastruktur:</span><span class="sxs-lookup"><span data-stu-id="79f0c-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="79f0c-150">**Välj ett begränsat antal webbplatser** – Microsoft Managed Desktop använder Microsoft Edge som den webbläsare som föredras för att förbättra den övergripande säkerheten för din organisation och användbarheten för användarna.</span><span class="sxs-lookup"><span data-stu-id="79f0c-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="79f0c-151">De flesta webbplatser i den här listan är för äldre webbappar som behöver en äldre version av en webbläsare som inte innehåller så många säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="79f0c-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="79f0c-152">**Överväg en alternativ** – Överväg en annan webbplats eller en annan webbapp som inte kräver en äldre webbläsare.</span><span class="sxs-lookup"><span data-stu-id="79f0c-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="79f0c-153">Du kan också uppdatera webbplatsen så att den kan använda nyare webbläsare.</span><span class="sxs-lookup"><span data-stu-id="79f0c-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="79f0c-154">Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="79f0c-155">Anpassa och distribuera plats för plats för företagsplatsläge</span><span class="sxs-lookup"><span data-stu-id="79f0c-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="79f0c-156">**Så här lägger du till en plats för en företagsplatsplatslista**</span><span class="sxs-lookup"><span data-stu-id="79f0c-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="79f0c-157">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-157">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="79f0c-158">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="79f0c-159">I **Konfigurerbar** arbetsyta väljer du **Plats för webbplats i företagsläge**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="79f0c-160">Ange https-platsen för din webbplatslista.</span><span class="sxs-lookup"><span data-stu-id="79f0c-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="79f0c-161">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="79f0c-162">Betrodda platser</span><span class="sxs-lookup"><span data-stu-id="79f0c-162">Trusted sites</span></span>

<span data-ttu-id="79f0c-163">Med betrodda platser kan du anpassa säkerhetszoner eller där en plats kan användas för olika platser.</span><span class="sxs-lookup"><span data-stu-id="79f0c-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="79f0c-164">Säkerhetszoner inkluderar:</span><span class="sxs-lookup"><span data-stu-id="79f0c-164">Security zones include:</span></span> 
- <span data-ttu-id="79f0c-165">Zon 1 – Zonen Lokalt intranät</span><span class="sxs-lookup"><span data-stu-id="79f0c-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="79f0c-166">Zon 2 – Zonen Betrodda platser</span><span class="sxs-lookup"><span data-stu-id="79f0c-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="79f0c-167">Zon 3 – Zonen Internet</span><span class="sxs-lookup"><span data-stu-id="79f0c-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="79f0c-168">Zon 4 – Zon restriktion</span><span class="sxs-lookup"><span data-stu-id="79f0c-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="79f0c-169">Krav</span><span class="sxs-lookup"><span data-stu-id="79f0c-169">Requirements</span></span>

<span data-ttu-id="79f0c-170">Ange fullständigt kvalificerat domännamn (FQDN) för intranät eller Internet-platser för varje betrodd plats.</span><span class="sxs-lookup"><span data-stu-id="79f0c-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="79f0c-171">Anpassa och distribuera betrodda platser</span><span class="sxs-lookup"><span data-stu-id="79f0c-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="79f0c-172">**Så här lägger du till en betrodd plats**</span><span class="sxs-lookup"><span data-stu-id="79f0c-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="79f0c-173">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-173">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="79f0c-174">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="79f0c-175">I **Konfigurerbar** arbetsyta väljer du **Betrodda platser**och väljer sedan **Lägg till betrodd plats**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="79f0c-176">På **Lägg till betrodd plats**anger du URL:en, väljer en säkerhetszon och väljer sedan Lägg till betrodd **plats**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="79f0c-177">Upprepa steg 1-4 för varje betrodd plats som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="79f0c-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="79f0c-178">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="79f0c-179">**Så här tar du bort en betrodd plats**</span><span class="sxs-lookup"><span data-stu-id="79f0c-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="79f0c-180">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-180">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="79f0c-181">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="79f0c-182">I **Konfigurerbar** arbetsyta väljer du **Betrodda platser**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="79f0c-183">Markera den webbplats som du vill ta bort och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="79f0c-184">Upprepa steg 1-4 för varje betrodd plats som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="79f0c-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="79f0c-185">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="79f0c-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="79f0c-186">Proxy</span></span>
<span data-ttu-id="79f0c-187">Du kan hantera nätverksproxyinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="79f0c-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="79f0c-188">Lägg till proxyservern och portnumret och lägg sedan till undantag från proxywebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="79f0c-189">Microsoft Managed Desktop innehåller en uppsättning standardproxyundantag som krävs för att tjänsten ska fungera.</span><span class="sxs-lookup"><span data-stu-id="79f0c-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="79f0c-190">Standardundansuteskapslistan får endast ändras av tjänsten Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="79f0c-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="79f0c-191">Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="79f0c-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="79f0c-192">De proxywebbplatsundantag som du lägger till i Microsoft Managed Desktop-portalen läggs till i standardproxyundantagen som ingår i Microsoft Managed Desktop-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="79f0c-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="79f0c-193">Att uppdatera standardundantagslistan för proxy prioriteras alltid framför kunddistributioner.</span><span class="sxs-lookup"><span data-stu-id="79f0c-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="79f0c-194">Det innebär att den stegvisa distributionen pausas om det finns en distribution för standardundantagslistan för proxy.</span><span class="sxs-lookup"><span data-stu-id="79f0c-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="79f0c-195">Krav</span><span class="sxs-lookup"><span data-stu-id="79f0c-195">Requirements</span></span>

<span data-ttu-id="79f0c-196">Dessa krav måste uppfyllas för proxyserver- och proxyplatsundantag:</span><span class="sxs-lookup"><span data-stu-id="79f0c-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="79f0c-197">Måste vara en giltig serveradress och portnummer</span><span class="sxs-lookup"><span data-stu-id="79f0c-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="79f0c-198">Webbadresser måste vara en giltig http-webbplats</span><span class="sxs-lookup"><span data-stu-id="79f0c-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="79f0c-199">Anpassa och distribuera proxyservrar</span><span class="sxs-lookup"><span data-stu-id="79f0c-199">Customize and deploy proxies</span></span>

<span data-ttu-id="79f0c-200">**Så här lägger du till ett enskilt proxyplatsundantag**</span><span class="sxs-lookup"><span data-stu-id="79f0c-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="79f0c-201">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="79f0c-201">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="79f0c-202">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="79f0c-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="79f0c-203">I **Konfigurerbar** arbetsyta väljer du **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="79f0c-204">Ange **adress-** och **portnumret** för din proxyserver och välj sedan **Lägg till proxyundantag**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="79f0c-205">Ange URL:en för en giltig http-webbplats och välj sedan **Lägg till proxyundantag**.</span><span class="sxs-lookup"><span data-stu-id="79f0c-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="79f0c-206">Upprepa steg 1-5 för varje betrodd plats som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="79f0c-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="79f0c-207">Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.</span><span class="sxs-lookup"><span data-stu-id="79f0c-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79f0c-208">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="79f0c-208">Additional resources</span></span>
- [<span data-ttu-id="79f0c-209">Översikt över konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="79f0c-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="79f0c-210">Distribuera konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="79f0c-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
