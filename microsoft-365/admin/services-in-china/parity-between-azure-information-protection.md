---
title: Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Lär dig mer om Azure information Protection (AIP) för Office 365 som drivs av 21Vianet och hur du konfigurerar den för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840307"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="de33b-103">Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter</span><span class="sxs-lookup"><span data-stu-id="de33b-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="de33b-104">När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure information Protection (AIP) för Office 365 som drivs av 21Vianet-bud finns det en del funktioner som vi vill framhäva.</span><span class="sxs-lookup"><span data-stu-id="de33b-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="de33b-105">Följande lista innehåller befintliga luckor mellan Azure information Protection for Office 365 som drivs av 21Vianet och våra kommersiella bud per den 2021 januari:</span><span class="sxs-lookup"><span data-stu-id="de33b-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="de33b-106">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="de33b-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="de33b-107">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="de33b-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="de33b-108">Migrering från AD RMS (Active Directory Rights Management Services) till Azure information Protection är för närvarande inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="de33b-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="de33b-109">Det går att dela skyddade e-postmeddelanden till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="de33b-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="de33b-110">Det går för närvarande inte att dela dokument och e-postbilagor till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="de33b-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="de33b-111">Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.</span><span class="sxs-lookup"><span data-stu-id="de33b-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="de33b-112">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="de33b-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="de33b-113">Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="de33b-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="de33b-114">[Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) stöds inte av Azure Kina 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="de33b-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="de33b-115">Konfigurera Azure information Protection för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="de33b-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="de33b-116">Aktivera rättighets hantering för klient organisationen</span><span class="sxs-lookup"><span data-stu-id="de33b-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="de33b-117">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="de33b-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="de33b-118">Kontrol lera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="de33b-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="de33b-119">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="de33b-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="de33b-120">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="de33b-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="de33b-121">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="de33b-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="de33b-122">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="de33b-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="de33b-123">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrol lera om tillståndet är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="de33b-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="de33b-124">Kör om det funktionella läget är `Disabled` `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="de33b-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="de33b-125">DNS-konfiguration för kryptering (Windows)</span><span class="sxs-lookup"><span data-stu-id="de33b-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="de33b-126">För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån.</span><span class="sxs-lookup"><span data-stu-id="de33b-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="de33b-127">För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="de33b-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="de33b-128">Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="de33b-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="de33b-129">Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="de33b-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="de33b-130">Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.</span><span class="sxs-lookup"><span data-stu-id="de33b-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="de33b-131">Hämta RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="de33b-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="de33b-132">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="de33b-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="de33b-133">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="de33b-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="de33b-134">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="de33b-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="de33b-135">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID.</span><span class="sxs-lookup"><span data-stu-id="de33b-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="de33b-136">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="de33b-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="de33b-137">Tjänst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="de33b-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="de33b-138">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="de33b-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="de33b-139">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="de33b-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="de33b-140">Target = `[GUID].rms.aadrm.cn` (där GUID är ett RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="de33b-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="de33b-141">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="de33b-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="de33b-142">Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="de33b-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="de33b-143">Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="de33b-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="de33b-144">Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="de33b-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="de33b-145">I verifierings processen kanske ytterligare DNS-ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="de33b-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="de33b-146">När verifieringen är klar kan du skapa användare.</span><span class="sxs-lookup"><span data-stu-id="de33b-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="de33b-147">DNS-konfiguration för kryptering (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="de33b-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="de33b-148">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="de33b-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="de33b-149">Tjänst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="de33b-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="de33b-150">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="de33b-150">Protocol = `_http`</span></span>
- <span data-ttu-id="de33b-151">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="de33b-151">Name = `_tcp`</span></span>
- <span data-ttu-id="de33b-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="de33b-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="de33b-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="de33b-153">Port = `80`</span></span>
- <span data-ttu-id="de33b-154">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="de33b-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="de33b-155">AIP klient konfiguration</span><span class="sxs-lookup"><span data-stu-id="de33b-155">AIP client configuration</span></span>

<span data-ttu-id="de33b-156">Den enhetliga AIP-klienten kan hämtas från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="de33b-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="de33b-157">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="de33b-157">For more information, see:</span></span>

- [<span data-ttu-id="de33b-158">Dokumentation för Azure information Protection</span><span class="sxs-lookup"><span data-stu-id="de33b-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="de33b-159">Versions historik och support policy för AIP</span><span class="sxs-lookup"><span data-stu-id="de33b-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="de33b-160">System krav för AIP</span><span class="sxs-lookup"><span data-stu-id="de33b-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="de33b-161">AIP snabb start: Distribuera AIP-klienten</span><span class="sxs-lookup"><span data-stu-id="de33b-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="de33b-162">AIP administratörs guide</span><span class="sxs-lookup"><span data-stu-id="de33b-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="de33b-163">AIP användar guide</span><span class="sxs-lookup"><span data-stu-id="de33b-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="de33b-164">Lär dig mer om Microsoft 365-känslighets etiketter</span><span class="sxs-lookup"><span data-stu-id="de33b-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="de33b-165">Konfiguration av AIP-appar (endast enhetlig etikett klient)</span><span class="sxs-lookup"><span data-stu-id="de33b-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="de33b-166">För den enhetliga etikett lösningen behöver AIP-apparna i Windows följande register nyckel för att peka dem på rätt kraft-moln för Azure Kina:</span><span class="sxs-lookup"><span data-stu-id="de33b-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="de33b-167">Registry Node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="de33b-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="de33b-168">Namn = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="de33b-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="de33b-169">Värde = `6` (standardvärde = 0)</span><span class="sxs-lookup"><span data-stu-id="de33b-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="de33b-170">Skriv = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="de33b-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de33b-171">Se till att du inte tar bort register nyckel efter en avinstallation.</span><span class="sxs-lookup"><span data-stu-id="de33b-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="de33b-172">Om knappen är tom, felaktig eller inte finns, fungerar funktionerna som standardvärde (standardvärde = 0 för det kommersiella molnet).</span><span class="sxs-lookup"><span data-stu-id="de33b-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="de33b-173">Om tangenten är tom eller felaktig läggs ett utskrifts fel till i loggen.</span><span class="sxs-lookup"><span data-stu-id="de33b-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="de33b-174">Hantera innehålls skannings jobb för Azure information Protection</span><span class="sxs-lookup"><span data-stu-id="de33b-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="de33b-175">Om du vill hantera dina Sök jobb för Azure information Protection-innehåll med en Azure Kina-skanner Server använder du följande cmdlet i stället för Azure-portalen:</span><span class="sxs-lookup"><span data-stu-id="de33b-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="de33b-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="de33b-176">Cmdlet</span></span> | <span data-ttu-id="de33b-177">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="de33b-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="de33b-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="de33b-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="de33b-179">Lägger till en ny lagrings plats i innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="de33b-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="de33b-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="de33b-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="de33b-181">Hämtar information om ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="de33b-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="de33b-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="de33b-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="de33b-183">Hämtar information om databaserna som har definierats för innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="de33b-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="de33b-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="de33b-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="de33b-185">Tar bort ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="de33b-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="de33b-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="de33b-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="de33b-187">Tar bort en databas från ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="de33b-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="de33b-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="de33b-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="de33b-189">Definierar inställningar för innehålls genomsöknings jobbet.</span><span class="sxs-lookup"><span data-stu-id="de33b-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="de33b-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="de33b-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="de33b-191">Definierar inställningar för en befintlig databas i innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="de33b-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="de33b-192">Mer information finns i [Hantera dina innehålls genomsöknings jobb endast med PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="de33b-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>