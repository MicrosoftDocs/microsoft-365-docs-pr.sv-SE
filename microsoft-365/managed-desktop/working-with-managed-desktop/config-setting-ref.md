---
title: Konfigurations bara referens inställningar för Microsoft Managed Desktop
description: Ställa in kategorier för konfigurerbara inställningar på Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104494"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="2808e-104">Referens för konfigurerbara inställningar – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2808e-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="2808e-105">I det här avsnittet visas de inställnings kategorier som kunder kan konfigurera med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2808e-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="2808e-106">Alla inställnings kategorier innehåller information om krav, metod tips och hur du anpassar inställnings kategorin.</span><span class="sxs-lookup"><span data-stu-id="2808e-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="2808e-107">Skriv bords bakgrund</span><span class="sxs-lookup"><span data-stu-id="2808e-107">Desktop background picture</span></span>
<span data-ttu-id="2808e-108">Du kan anpassa Skriv bords bakgrund för Microsoft Managed Station ära enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="2808e-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="2808e-109">Du kan använda det här om du vill använda ett företags varumärkes-eller marknadsförings material.</span><span class="sxs-lookup"><span data-stu-id="2808e-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="2808e-110">Krav</span><span class="sxs-lookup"><span data-stu-id="2808e-110">Requirements</span></span>

<span data-ttu-id="2808e-111">Dessa krav måste uppfyllas för en Skriv bords bakgrund:</span><span class="sxs-lookup"><span data-stu-id="2808e-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="2808e-112">Bild fil format-. jpg, JPEG eller. png</span><span class="sxs-lookup"><span data-stu-id="2808e-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="2808e-113">Fil Sök väg-värd på en betrodd säker http-plats (https).</span><span class="sxs-lookup"><span data-stu-id="2808e-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="2808e-114">Ej tillåtna-http-och fildelnings platser (UNC) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="2808e-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="2808e-115">Anpassa och distribuera Skriv bords bakgrund</span><span class="sxs-lookup"><span data-stu-id="2808e-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="2808e-116">**Så här lägger du till en egen Skriv bords bakgrund**</span><span class="sxs-lookup"><span data-stu-id="2808e-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="2808e-117">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-117">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-118">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-118">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-119">I arbets ytan **Inställningar** väljer du **Skriv bords bakgrund**.</span><span class="sxs-lookup"><span data-stu-id="2808e-119">In **Settings** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="2808e-120">Ange platsen för den bild du vill använda.</span><span class="sxs-lookup"><span data-stu-id="2808e-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="2808e-121">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="2808e-122">Webbläsarens start sidor</span><span class="sxs-lookup"><span data-stu-id="2808e-122">Browser start pages</span></span>
<span data-ttu-id="2808e-123">Webbläsarens start sidor öppnas på enskilda flikar när användarna startar Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2808e-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="2808e-124">Om du vill göra det lättare för dina användare att öppna en uppsättning webbplatser som de använder ofta, kan du lägga till en webb läsar start sida för varje webbplats.</span><span class="sxs-lookup"><span data-stu-id="2808e-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="2808e-125">Krav</span><span class="sxs-lookup"><span data-stu-id="2808e-125">Requirements</span></span>

<span data-ttu-id="2808e-126">Du måste ange det fullständigt kvalificerade domän namnet (FQDN) för intranät-eller Internet-webbplatser för webbläsarens start sidor.</span><span class="sxs-lookup"><span data-stu-id="2808e-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="2808e-127">Om interna webbplatser är konfigurerade kan användarna veta att åtkomsten till dessa webbplatser endast tillåts när du är ansluten till det interna nätverket när du befinner dig på kontoret eller när du är ansluten till en VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="2808e-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="2808e-128">Anpassa och distribuera webbläsarens start sidor</span><span class="sxs-lookup"><span data-stu-id="2808e-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="2808e-129">**Så här lägger du till en webbläsares start sida**</span><span class="sxs-lookup"><span data-stu-id="2808e-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="2808e-130">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-130">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-131">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-131">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-132">I arbets ytan **Inställningar** väljer du **webbläsarens start sidor**.</span><span class="sxs-lookup"><span data-stu-id="2808e-132">In **Settings** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="2808e-133">Välj **Lägg till start sidan**.</span><span class="sxs-lookup"><span data-stu-id="2808e-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="2808e-134">På **sidan Lägg till Start sida**anger du webb adressen till den webbplats som du vill använda och väljer sedan **Lägg till Start sida**.</span><span class="sxs-lookup"><span data-stu-id="2808e-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="2808e-135">Upprepa steg 1-5 för ytterligare start sidor i webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2808e-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="2808e-136">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="2808e-137">Plats för webbplats lista för företags läge</span><span class="sxs-lookup"><span data-stu-id="2808e-137">Enterprise mode site list location</span></span>

<span data-ttu-id="2808e-138">Om du har särskilda webbplatser och program som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplats listan för företags läge så att webbplatserna öppnas automatiskt med Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="2808e-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="2808e-139">Om du vet att dina intranät platser inte fungerar korrekt med Microsoft Edge kan du också ställa in alla intranät webbplatser att öppna via Internet Explorer 11 automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2808e-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="2808e-140">Om du använder företags läget kan du fortsätta att använda Microsoft Edge som standard webbläsare, samtidigt som du ser till att dina appar fortsätter fungera med Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="2808e-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="2808e-141">Mer information om webbplats listor för företags läge finns i avsnittet [företags läge och webbplats listor för företags](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)läge.</span><span class="sxs-lookup"><span data-stu-id="2808e-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="2808e-142">Du kan ange en https://-plats eller platsen för en intern resurs där du har en värd lista för webbplats listan.</span><span class="sxs-lookup"><span data-stu-id="2808e-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="2808e-143">Krav</span><span class="sxs-lookup"><span data-stu-id="2808e-143">Requirements</span></span>

<span data-ttu-id="2808e-144">Dessa krav måste uppfyllas för webbplats listan för företags läget:</span><span class="sxs-lookup"><span data-stu-id="2808e-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="2808e-145">Fil format-XML-fil som uppfyller [fil kraven](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="2808e-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="2808e-146">Fil Sök väg – värd fil på en intern https-plats.</span><span class="sxs-lookup"><span data-stu-id="2808e-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="2808e-147">Inte tillåten-värd på en intern fil resurs, till exempel *//ShareName*, är inte tillåten</span><span class="sxs-lookup"><span data-stu-id="2808e-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="2808e-148">Metodtips</span><span class="sxs-lookup"><span data-stu-id="2808e-148">Best practices</span></span>

<span data-ttu-id="2808e-149">De här bästa metoderna är att hjälpa kunder att modernisera sin IT-infrastruktur:</span><span class="sxs-lookup"><span data-stu-id="2808e-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="2808e-150">**Välj ett begränsat antal webbplatser** – Microsoft Managed Desktop använder Microsoft Edge som standard webbläsare för att förbättra den övergripande säkerheten för din organisation och användbarhet för dina användare.</span><span class="sxs-lookup"><span data-stu-id="2808e-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="2808e-151">De flesta webbplatser i den här listan är för gamla webb program som behöver en äldre version av en webbläsare som inte innehåller några säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="2808e-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="2808e-152">**Överväg** att överväga en annan webbplats eller webbprogram som inte kräver en äldre webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2808e-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="2808e-153">Eller Överväg att uppdatera webbplatsen så att den kan använda nyare webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2808e-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="2808e-154">Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.</span><span class="sxs-lookup"><span data-stu-id="2808e-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="2808e-155">Sidan anpassa och distribuera listans plats med företagets webbplats läge</span><span class="sxs-lookup"><span data-stu-id="2808e-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="2808e-156">**Så här lägger du till en plats för en lista med företagets webbplats lägen**</span><span class="sxs-lookup"><span data-stu-id="2808e-156">**To add an enterprise site mode list location**</span></span>

1. <span data-ttu-id="2808e-157">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-157">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-158">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-158">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-159">I arbets ytan **Inställningar** väljer du **platsen för webbplats listan för företags läget**.</span><span class="sxs-lookup"><span data-stu-id="2808e-159">In **Settings** workspace, select **Enterprise mode site list location**.</span></span> 
4. <span data-ttu-id="2808e-160">Ange https-platsen för din webbplats lista.</span><span class="sxs-lookup"><span data-stu-id="2808e-160">Enter the https location for your site list.</span></span> 
5. <span data-ttu-id="2808e-161">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="2808e-162">Tillförlitliga platser</span><span class="sxs-lookup"><span data-stu-id="2808e-162">Trusted sites</span></span>

<span data-ttu-id="2808e-163">Med tillförlitliga webbplatser kan du anpassa säkerhets zoner eller var en webbplats ska användas, för olika webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2808e-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="2808e-164">Säkerhets zoner inkluderar:</span><span class="sxs-lookup"><span data-stu-id="2808e-164">Security zones include:</span></span> 
- <span data-ttu-id="2808e-165">Zon 1 – zonen Lokalt intranät</span><span class="sxs-lookup"><span data-stu-id="2808e-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="2808e-166">Zone 2 – zonen Tillförlitliga platser</span><span class="sxs-lookup"><span data-stu-id="2808e-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="2808e-167">Zon 3 – zonen Internet</span><span class="sxs-lookup"><span data-stu-id="2808e-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="2808e-168">Zone 4 – zonen Ej tillförlitliga platser</span><span class="sxs-lookup"><span data-stu-id="2808e-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="2808e-169">Krav</span><span class="sxs-lookup"><span data-stu-id="2808e-169">Requirements</span></span>

<span data-ttu-id="2808e-170">Ange det fullständigt kvalificerade domän namnet (FQDN) för intranät-eller Internet webbplatser för varje betrodd webbplats.</span><span class="sxs-lookup"><span data-stu-id="2808e-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="2808e-171">Anpassa och distribuera tillförlitliga webbplatser</span><span class="sxs-lookup"><span data-stu-id="2808e-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="2808e-172">**Så här lägger du till en betrodd webbplats**</span><span class="sxs-lookup"><span data-stu-id="2808e-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="2808e-173">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-173">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-174">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-174">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-175">I **inställnings** arbets ytan väljer du **tillförlitliga platser**och väljer sedan **Lägg till betrodd webbplats**.</span><span class="sxs-lookup"><span data-stu-id="2808e-175">In **Settings** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="2808e-176">På **Lägg till betrodd webbplats**anger du webb adressen, väljer en säkerhets zon och väljer sedan **Lägg till betrodd webbplats**.</span><span class="sxs-lookup"><span data-stu-id="2808e-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="2808e-177">Upprepa steg 1-4 för varje betrodd webbplats du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="2808e-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="2808e-178">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="2808e-179">**Så här tar du bort en betrodd webbplats**</span><span class="sxs-lookup"><span data-stu-id="2808e-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="2808e-180">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-180">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-181">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-181">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-182">Välj **tillförlitliga platser**i arbets ytan **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="2808e-182">In **Settings** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="2808e-183">Markera den webbplats du vill ta bort och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="2808e-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="2808e-184">Upprepa steg 1-4 för varje betrodd webbplats du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="2808e-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="2808e-185">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="2808e-186">Identifiera</span><span class="sxs-lookup"><span data-stu-id="2808e-186">Proxy</span></span>
<span data-ttu-id="2808e-187">Du kan hantera nätverks-proxyinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="2808e-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="2808e-188">Lägg till proxyserver och port nummer och Lägg sedan till dina webbplats undantag.</span><span class="sxs-lookup"><span data-stu-id="2808e-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="2808e-189">Microsoft Managed Desktop innehåller en uppsättning standardproxy-undantag som krävs för att tjänsten ska fungera.</span><span class="sxs-lookup"><span data-stu-id="2808e-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="2808e-190">Standard uteslutnings listan kan bara ändras av Microsoft Managed Desktop-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2808e-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="2808e-191">Mer information finns i [nätverks konfiguration för Microsoft Managed Desktop](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="2808e-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="2808e-192">De undantag som du lägger till i Microsoft Managed Desktop-portalen läggs till i standardvärden för proxy-undantag som ingår i Microsoft Managed Desktop-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2808e-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="2808e-193">Uppdatering av standard listan över undantag är alltid prioriterad över kund distributioner.</span><span class="sxs-lookup"><span data-stu-id="2808e-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="2808e-194">Det innebär att din stegvisa distribution kommer att pausas om det finns en distribution för standard listan över undantag.</span><span class="sxs-lookup"><span data-stu-id="2808e-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="2808e-195">Krav</span><span class="sxs-lookup"><span data-stu-id="2808e-195">Requirements</span></span>

<span data-ttu-id="2808e-196">De här kraven måste uppfyllas för proxy server-och proxy webbplats undantag:</span><span class="sxs-lookup"><span data-stu-id="2808e-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="2808e-197">Måste vara en giltig server adress och port nummer</span><span class="sxs-lookup"><span data-stu-id="2808e-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="2808e-198">URL: er måste vara en giltig http-webbplats</span><span class="sxs-lookup"><span data-stu-id="2808e-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="2808e-199">Anpassa och distribuera proxyservrar</span><span class="sxs-lookup"><span data-stu-id="2808e-199">Customize and deploy proxies</span></span>

<span data-ttu-id="2808e-200">**Lägga till ett enskilt fel i en webbplats**</span><span class="sxs-lookup"><span data-stu-id="2808e-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="2808e-201">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="2808e-201">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="2808e-202">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2808e-202">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="2808e-203">Välj **proxy**i arbets ytan **Inställningar** .</span><span class="sxs-lookup"><span data-stu-id="2808e-203">In **Settings** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="2808e-204">Ange **adress** och **port nummer** för din proxyserver och välj sedan **Lägg till ett proxy-undantag**.</span><span class="sxs-lookup"><span data-stu-id="2808e-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="2808e-205">Ange URL: en till en giltig http-plats och välj sedan **Lägg till ett proxy-undantag**.</span><span class="sxs-lookup"><span data-stu-id="2808e-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="2808e-206">Upprepa steg 1-5 för varje betrodd webbplats du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="2808e-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="2808e-207">Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.</span><span class="sxs-lookup"><span data-stu-id="2808e-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2808e-208">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2808e-208">Additional resources</span></span>
- [<span data-ttu-id="2808e-209">Inställningar för konfigurerings bara översikt</span><span class="sxs-lookup"><span data-stu-id="2808e-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="2808e-210">Distribuera inställningar som kan konfigureras</span><span class="sxs-lookup"><span data-stu-id="2808e-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
