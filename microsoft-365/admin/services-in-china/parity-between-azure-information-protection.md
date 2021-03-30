---
title: Stöd för Azure Information Protection för Office 365 som drivs av 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Läs mer om Azure Information Protection (AIP) för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418038"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="42593-103">Stöd för Azure Information Protection för Office 365 som drivs av 21Vianet</span><span class="sxs-lookup"><span data-stu-id="42593-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="42593-104">Den här artikeln beskriver skillnaderna mellan Azure Information Protection-stöd (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för att konfigurera AIP för kunder i Kina, inklusive hur du installerar den lokala AIP-skannern och hanterar jobb för &mdash; innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="42593-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="42593-105">Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden</span><span class="sxs-lookup"><span data-stu-id="42593-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="42593-106">Även om vårt mål är att tillhandahålla alla kommersiella funktioner till kunder i Kina med erbjudandet AIP för Office 365 som drivs av 21Vianet finns det några funktioner som vi vill lyfta fram.</span><span class="sxs-lookup"><span data-stu-id="42593-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="42593-107">Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:</span><span class="sxs-lookup"><span data-stu-id="42593-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="42593-108">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731.10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="42593-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="42593-109">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="42593-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="42593-110">Migrering från AD RMS (Active Directory Rights Management Services) till AIP är för närvarande inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="42593-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="42593-111">Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.</span><span class="sxs-lookup"><span data-stu-id="42593-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="42593-112">Det går för närvarande inte att dela dokument och e-postbilagor med användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="42593-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="42593-113">Detta omfattar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS för individer-licens.</span><span class="sxs-lookup"><span data-stu-id="42593-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="42593-114">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="42593-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="42593-115">Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.</span><span class="sxs-lookup"><span data-stu-id="42593-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="42593-116">[Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="42593-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="42593-117">Området AIP i Azure Portal är inte tillgängligt för kunder i Kina.</span><span class="sxs-lookup"><span data-stu-id="42593-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="42593-118">Använd [PowerShell-kommandon](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel installera den lokala skannern och hantera genomsökningsjobben.</span><span class="sxs-lookup"><span data-stu-id="42593-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="42593-119">Konfigurera AIP för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="42593-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="42593-120">Så här konfigurerar du AIP för kunder i Kina:</span><span class="sxs-lookup"><span data-stu-id="42593-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="42593-121">[Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="42593-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="42593-122">[Konfigurera DNS-kryptering](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="42593-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="42593-123">[Installera och konfigurera AIP unified labeling-klienten.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="42593-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="42593-124">[Konfigurera AIP-appar i Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="42593-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="42593-125">[Installera den lokala AIP-skannern och hantera sökjobb för innehåll.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="42593-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="42593-126">Steg 1: Aktivera rättighetshantering för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="42593-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="42593-127">För att krypteringen ska fungera måste RMS vara aktiverat för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="42593-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="42593-128">Kontrollera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="42593-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="42593-129">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="42593-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="42593-130">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="42593-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="42593-131">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="42593-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="42593-132">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="42593-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="42593-133">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="42593-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="42593-134">Om funktionstillståndet är `Disabled` kör du `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="42593-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="42593-135">Steg 2: Konfigurera DNS-kryptering</span><span class="sxs-lookup"><span data-stu-id="42593-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="42593-136">För att krypteringen ska fungera korrekt måste Office-klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån.</span><span class="sxs-lookup"><span data-stu-id="42593-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="42593-137">Om klientprogrammen ska omdirigeras till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS-URL: en.</span><span class="sxs-lookup"><span data-stu-id="42593-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="42593-138">Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="42593-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="42593-139">Antagandet är också att användare loggar in med ett användarnamn baserat på den klientorganisationsägda domänen (till exempel ), och inte `joe@contoso.cn` `onmschina` användarnamnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="42593-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="42593-140">Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="42593-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="42593-141">Konfigurera DNS-kryptering – Windows</span><span class="sxs-lookup"><span data-stu-id="42593-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="42593-142">Skaffa RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="42593-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="42593-143">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="42593-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="42593-144">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="42593-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="42593-145">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="42593-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="42593-146">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att få RMS-ID: t.</span><span class="sxs-lookup"><span data-stu-id="42593-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="42593-147">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="42593-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="42593-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="42593-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="42593-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="42593-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="42593-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="42593-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="42593-151">Mål = `[GUID].rms.aadrm.cn` (där GUID är RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="42593-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="42593-152">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="42593-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="42593-153">Associera den anpassade domänen med klientorganisationen i [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="42593-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="42593-154">Då lägger du till en post i DNS, vilket kan ta flera minuter att verifieras när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="42593-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="42593-155">Logga in på administrationscentret för Microsoft 365 med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="42593-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="42593-156">I verifieringsprocessen kan du behöva göra ytterligare DNS-ändringar.</span><span class="sxs-lookup"><span data-stu-id="42593-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="42593-157">När verifieringen är klar kan användarna skapas.</span><span class="sxs-lookup"><span data-stu-id="42593-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="42593-158">Konfigurera DNS-kryptering – Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="42593-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="42593-159">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="42593-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="42593-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="42593-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="42593-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="42593-161">Protocol = `_http`</span></span>
- <span data-ttu-id="42593-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="42593-162">Name = `_tcp`</span></span>
- <span data-ttu-id="42593-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="42593-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="42593-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="42593-164">Port = `80`</span></span>
- <span data-ttu-id="42593-165">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="42593-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="42593-166">Steg 3: Installera och konfigurera den enhetliga AIP-etikettklienten</span><span class="sxs-lookup"><span data-stu-id="42593-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="42593-167">Ladda ned AIP Unified Labeling Client från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="42593-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="42593-168">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="42593-168">For more information, see:</span></span>

- [<span data-ttu-id="42593-169">AIP-dokumentation</span><span class="sxs-lookup"><span data-stu-id="42593-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="42593-170">AIP-versionshistorik och supportpolicy</span><span class="sxs-lookup"><span data-stu-id="42593-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="42593-171">Systemkrav för AIP</span><span class="sxs-lookup"><span data-stu-id="42593-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="42593-172">Snabbstart för AIP: Distribuera AIP-klienten</span><span class="sxs-lookup"><span data-stu-id="42593-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="42593-173">AIP-administratörsguide</span><span class="sxs-lookup"><span data-stu-id="42593-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="42593-174">AIP-användarhandbok</span><span class="sxs-lookup"><span data-stu-id="42593-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="42593-175">Läs mer om känslighetsetiketter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42593-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="42593-176">Steg 4: Konfigurera AIP-appar i Windows</span><span class="sxs-lookup"><span data-stu-id="42593-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="42593-177">AIP-appar i Windows behöver följande registernyckel för att de ska kunna peka på rätt suveränt moln för Azure Kina:</span><span class="sxs-lookup"><span data-stu-id="42593-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="42593-178">Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="42593-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="42593-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="42593-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="42593-180">Värde = `6` (standard = 0)</span><span class="sxs-lookup"><span data-stu-id="42593-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="42593-181">Skriv = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="42593-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42593-182">Se till att du inte tar bort registernyckeln efter en avinstallation.</span><span class="sxs-lookup"><span data-stu-id="42593-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="42593-183">Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet).</span><span class="sxs-lookup"><span data-stu-id="42593-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="42593-184">Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.</span><span class="sxs-lookup"><span data-stu-id="42593-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="42593-185">Steg 5: Installera den lokala AIP-skannern och hantera jobb för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="42593-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="42593-186">Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.</span><span class="sxs-lookup"><span data-stu-id="42593-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="42593-187">När du skapar och konfigurerar Azure AD-program för kommandot [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) visas i fönstret Begär **API-behörigheter** de **API:er** som min organisation använder flik i stället för fliken Microsoft-API:er.  Välj de **API:er som min organisation använder** för att sedan välja Azure Rights Management **Services.**</span><span class="sxs-lookup"><span data-stu-id="42593-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="42593-188">När du installerar skannern och hanterar dina innehållssökningsjobb ska du använda följande cmdlets i stället för Azure Portal-gränssnittet som används av kommersiella erbjudanden:</span><span class="sxs-lookup"><span data-stu-id="42593-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="42593-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="42593-189">Cmdlet</span></span> | <span data-ttu-id="42593-190">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="42593-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="42593-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="42593-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="42593-192">Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="42593-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="42593-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="42593-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="42593-194">Hämtar information om ditt innehållssökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="42593-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="42593-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="42593-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="42593-196">Hämtar information om lagringsplatsen som definierats för ditt genomsökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="42593-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="42593-197">Remove-AIPScannerContentScan Job</span><span class="sxs-lookup"><span data-stu-id="42593-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="42593-198">Tar bort ditt genomsökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="42593-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="42593-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="42593-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="42593-200">Tar bort en lagringsplats från innehållssökningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="42593-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="42593-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="42593-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="42593-202">Definierar inställningar för innehållssökningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="42593-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="42593-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="42593-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="42593-204">Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="42593-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="42593-205">När [du installerar skannern](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)använder du samma klusternamn i kommandot [Install-AIP Scannerner](/powershell/module/azureinformationprotection/install-aipscanner) för att koppla flera skannernoder till samma kluster.</span><span class="sxs-lookup"><span data-stu-id="42593-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="42593-206">Med samma kluster för flera skannernoder kan flera skannrar arbeta tillsammans för att utföra genomsökningarna.</span><span class="sxs-lookup"><span data-stu-id="42593-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="42593-207">Använd [cmdleten Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) för att returnera information om ditt kluster.</span><span class="sxs-lookup"><span data-stu-id="42593-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="42593-208">Mer information finns i Vad [är en enhetlig skanner](/azure/information-protection/deploy-aip-scanner) för Azure Information Protection? och Hantera genomsökningsjobb med bara [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="42593-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>