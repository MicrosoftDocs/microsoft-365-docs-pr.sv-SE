---
title: Azure Information Protection-stöd för Office 365 som drivs av 21Vianet
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
description: Läs mer om AIP (Azure Information Protection) för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535848"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="75f4a-103">Azure Information Protection-stöd för Office 365 som drivs av 21Vianet</span><span class="sxs-lookup"><span data-stu-id="75f4a-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="75f4a-104">Den här artikeln beskriver skillnaderna mellan Azure Information Protection-stöd (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för att konfigurera AIP för kunder i Kina, inklusive hur du installerar den lokala AIP-skannern och hanterar jobb för &mdash; innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="75f4a-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="75f4a-105">Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden</span><span class="sxs-lookup"><span data-stu-id="75f4a-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="75f4a-106">Även om vårt mål är att tillhandahålla alla kommersiella funktioner till kunder i Kina med vårt AIP för Office 365 som drivs av 21Vianet-erbjudandet finns det några funktioner som saknas och som vi vill lyfta fram.</span><span class="sxs-lookup"><span data-stu-id="75f4a-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="75f4a-107">Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:</span><span class="sxs-lookup"><span data-stu-id="75f4a-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="75f4a-108">IRM (Information Rights Management) stöds endast för Microsoft 365-appar för företag (version 11731.10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="75f4a-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="75f4a-109">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="75f4a-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="75f4a-110">Migrering från Active Directory Rights Management Services (AD RMS) till AIP är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="75f4a-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="75f4a-111">Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.</span><span class="sxs-lookup"><span data-stu-id="75f4a-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="75f4a-112">Det går för närvarande inte att dela dokument och e-postbilagor med användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="75f4a-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="75f4a-113">Detta omfattar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS för individer-licens.</span><span class="sxs-lookup"><span data-stu-id="75f4a-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="75f4a-114">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="75f4a-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="75f4a-115">Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.</span><span class="sxs-lookup"><span data-stu-id="75f4a-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="75f4a-116">[Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="75f4a-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="75f4a-117">Området AIP i Azure Portal är inte tillgängligt för kunder i Kina.</span><span class="sxs-lookup"><span data-stu-id="75f4a-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="75f4a-118">Använd [PowerShell-kommandon](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel hantera och köra genomsökningsjobben för innehåll.</span><span class="sxs-lookup"><span data-stu-id="75f4a-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="75f4a-119">Konfigurera AIP för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="75f4a-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="75f4a-120">Så här konfigurerar du AIP för kunder i Kina:</span><span class="sxs-lookup"><span data-stu-id="75f4a-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="75f4a-121">[Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="75f4a-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="75f4a-122">[Lägg till Microsoft Information Protection Sync Service-tjänstens huvudnamn.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="75f4a-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="75f4a-123">[Konfigurera DNS-kryptering](#step-3-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="75f4a-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="75f4a-124">[Installera och konfigurera AIP unified labeling-klienten.](#step-4-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="75f4a-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="75f4a-125">[Konfigurera AIP-appar på Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="75f4a-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="75f4a-126">[Installera den lokala AIP-skannern och hantera sökjobb för innehåll.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="75f4a-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="75f4a-127">Steg 1: Aktivera rättighetshantering för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="75f4a-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="75f4a-128">För att krypteringen ska fungera måste RMS vara aktiverat för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75f4a-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="75f4a-129">Kontrollera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="75f4a-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="75f4a-130">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="75f4a-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="75f4a-131">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="75f4a-132">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="75f4a-133">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="75f4a-134">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="75f4a-135">Om funktionstillståndet är `Disabled` kör du `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="75f4a-136">Steg 2: Lägg till microsofts huvudnamn för synkroniseringstjänsten för informationsskydd</span><span class="sxs-lookup"><span data-stu-id="75f4a-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="75f4a-137">Microsoft **Information Protection-synkroniseringstjänstens** huvudnamn är inte tillgängligt i Azure China-klientorganisationen som standard och krävs för Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="75f4a-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="75f4a-138">Skapa den här tjänstens huvudnamn manuellt med cmdleten [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) och program-ID:t `870c4f2e-85b6-4d43-bdda-6ed9a579b725` för Synkroniseringstjänsten för Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="75f4a-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="75f4a-139">När du har lagt till tjänstens huvudnamn lägger du till de relevanta behörigheter som krävs för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="75f4a-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="75f4a-140">Steg 3: Konfigurera DNS-kryptering</span><span class="sxs-lookup"><span data-stu-id="75f4a-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="75f4a-141">För att krypteringen ska fungera Office måste klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån.</span><span class="sxs-lookup"><span data-stu-id="75f4a-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="75f4a-142">Om klientprogrammen ska omdirigeras till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS-URL: en.</span><span class="sxs-lookup"><span data-stu-id="75f4a-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="75f4a-143">Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="75f4a-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="75f4a-144">Antagandet är också att användare loggar in med ett användarnamn baserat på den klientorganisationsägda domänen (till exempel ), och inte `joe@contoso.cn` `onmschina` användarnamnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="75f4a-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="75f4a-145">Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="75f4a-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="75f4a-146">Konfigurera DNS-kryptering – Windows</span><span class="sxs-lookup"><span data-stu-id="75f4a-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="75f4a-147">Skaffa RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="75f4a-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="75f4a-148">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="75f4a-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="75f4a-149">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="75f4a-150">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="75f4a-151">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att få RMS-ID: t.</span><span class="sxs-lookup"><span data-stu-id="75f4a-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="75f4a-152">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="75f4a-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="75f4a-153">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="75f4a-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="75f4a-154">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="75f4a-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="75f4a-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="75f4a-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="75f4a-156">Mål = `[GUID].rms.aadrm.cn` (där GUID är RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="75f4a-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="75f4a-157">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="75f4a-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="75f4a-158">Associera den anpassade domänen med klientorganisationen i [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="75f4a-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="75f4a-159">Då lägger du till en post i DNS, vilket kan ta flera minuter att verifieras när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="75f4a-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="75f4a-160">Logga in på Microsoft 365-administrationscentret med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="75f4a-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="75f4a-161">I verifieringsprocessen kan du behöva göra ytterligare DNS-ändringar.</span><span class="sxs-lookup"><span data-stu-id="75f4a-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="75f4a-162">När verifieringen är klar kan användarna skapas.</span><span class="sxs-lookup"><span data-stu-id="75f4a-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="75f4a-163">Konfigurera DNS-kryptering – Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="75f4a-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="75f4a-164">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="75f4a-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="75f4a-165">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="75f4a-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="75f4a-166">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="75f4a-166">Protocol = `_http`</span></span>
- <span data-ttu-id="75f4a-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="75f4a-167">Name = `_tcp`</span></span>
- <span data-ttu-id="75f4a-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="75f4a-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="75f4a-169">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="75f4a-169">Port = `80`</span></span>
- <span data-ttu-id="75f4a-170">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="75f4a-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="75f4a-171">Steg 4: Installera och konfigurera den enhetliga AIP-etikettklienten</span><span class="sxs-lookup"><span data-stu-id="75f4a-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="75f4a-172">Ladda ned och installera AIP Unified Labeling-klienten från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="75f4a-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="75f4a-173">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="75f4a-173">For more information, see:</span></span>

- [<span data-ttu-id="75f4a-174">AIP-dokumentation</span><span class="sxs-lookup"><span data-stu-id="75f4a-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="75f4a-175">AIP-versionshistorik och supportpolicy</span><span class="sxs-lookup"><span data-stu-id="75f4a-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="75f4a-176">Systemkrav för AIP</span><span class="sxs-lookup"><span data-stu-id="75f4a-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="75f4a-177">Snabbstart för AIP: Distribuera AIP-klienten</span><span class="sxs-lookup"><span data-stu-id="75f4a-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="75f4a-178">AIP-administratörsguide</span><span class="sxs-lookup"><span data-stu-id="75f4a-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="75f4a-179">AIP-användarhandbok</span><span class="sxs-lookup"><span data-stu-id="75f4a-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="75f4a-180">Läs mer Microsoft 365 känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="75f4a-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="75f4a-181">Steg 5: Konfigurera AIP-appar på Windows</span><span class="sxs-lookup"><span data-stu-id="75f4a-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="75f4a-182">AIP-appar Windows behöver följande registernyckel för att de ska kunna peka på rätt suveränt moln för Azure Kina:</span><span class="sxs-lookup"><span data-stu-id="75f4a-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="75f4a-183">Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="75f4a-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="75f4a-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="75f4a-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="75f4a-185">Värde = `6` (standard = 0)</span><span class="sxs-lookup"><span data-stu-id="75f4a-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="75f4a-186">Skriv = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="75f4a-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75f4a-187">Se till att du inte tar bort registernyckeln efter en avinstallation.</span><span class="sxs-lookup"><span data-stu-id="75f4a-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="75f4a-188">Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet).</span><span class="sxs-lookup"><span data-stu-id="75f4a-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="75f4a-189">Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.</span><span class="sxs-lookup"><span data-stu-id="75f4a-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="75f4a-190">Steg 6: Installera den lokala AIP-skannern och hantera genomsökningsjobb</span><span class="sxs-lookup"><span data-stu-id="75f4a-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="75f4a-191">Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.</span><span class="sxs-lookup"><span data-stu-id="75f4a-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="75f4a-192">När du konfigurerar och hanterar innehållssökningsjobben ska du använda följande procedur i stället för [det Azure Portal-gränssnitt](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) som används av de kommersiella erbjudandena.</span><span class="sxs-lookup"><span data-stu-id="75f4a-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="75f4a-193">Mer information finns i Vad [är en enhetlig skanner](/azure/information-protection/deploy-aip-scanner) för Azure Information Protection? och Hantera genomsökningsjobb med bara [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="75f4a-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="75f4a-194">**Installera och konfigurera skannern:**</span><span class="sxs-lookup"><span data-stu-id="75f4a-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="75f4a-195">Logga in på Windows Server-datorn som kör skannern.</span><span class="sxs-lookup"><span data-stu-id="75f4a-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="75f4a-196">Använd ett konto med lokala administratörsrättigheter och som har behörighet att skriva till SQL Server huvuddatabasen.</span><span class="sxs-lookup"><span data-stu-id="75f4a-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="75f4a-197">Börja med att stänga PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75f4a-197">Start with PowerShell closed.</span></span> <span data-ttu-id="75f4a-198">Om du tidigare har installerat AIP-klienten och skannern ska du kontrollera att **AIP Scannerner-tjänsten** stoppas.</span><span class="sxs-lookup"><span data-stu-id="75f4a-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="75f4a-199">Öppna Windows PowerShell en session med **alternativet Kör som** administratör.</span><span class="sxs-lookup"><span data-stu-id="75f4a-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="75f4a-200">Kör cmdleten [Install-AIP Scannerner,](/powershell/module/azureinformationprotection/Install-AIPScanner) ange din SQL Server-instans där du ska skapa en databas för Azure Information Protection-skannern och ett beskrivande namn på skannerkluster.</span><span class="sxs-lookup"><span data-stu-id="75f4a-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="75f4a-201">Du kan använda samma klusternamn i kommandot [Install-AIP Scannerner för](/powershell/module/azureinformationprotection/install-aipscanner) att koppla flera skannernoder till samma kluster.</span><span class="sxs-lookup"><span data-stu-id="75f4a-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="75f4a-202">Med samma kluster för flera skannernoder kan flera skannrar arbeta tillsammans för att utföra genomsökningarna.</span><span class="sxs-lookup"><span data-stu-id="75f4a-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="75f4a-203">Kontrollera att tjänsten nu är installerad med hjälp av  >  **Administrationsverktygstjänster.**</span><span class="sxs-lookup"><span data-stu-id="75f4a-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="75f4a-204">Den installerade tjänsten heter **Azure Information Protection Scanner och** är konfigurerad att köras med hjälp av det skannertjänstkonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="75f4a-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="75f4a-205">Hämta en Azure-token som ska användas med skannern.</span><span class="sxs-lookup"><span data-stu-id="75f4a-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="75f4a-206">Med en Azure AD-token kan skannern autentiseras i Azure Information Protection-tjänsten, vilket gör att skannern kan köras icke-interaktivt.</span><span class="sxs-lookup"><span data-stu-id="75f4a-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="75f4a-207">Öppna Azure-portalen och skapa ett Azure AD-program för att ange en åtkomsttoken för autentisering.</span><span class="sxs-lookup"><span data-stu-id="75f4a-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="75f4a-208">Mer information finns i Så [här märks filer icke-interaktivt för Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="75f4a-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="75f4a-209">När du skapar och konfigurerar Azure AD-program för kommandot [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) visas i fönstret Begär **API-behörigheter** de **API:er** som min organisation använder flik i stället för fliken Microsoft-API:er.  Välj de **API:er som min organisation använder** för att sedan välja Azure Rights Management **Services.**</span><span class="sxs-lookup"><span data-stu-id="75f4a-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="75f4a-210">Från Windows-serverdatorn loggar du in med det här  kontot och startar en PowerShell-session om ditt skannertjänstkonto har beviljats logga in lokalt direkt för installationen.</span><span class="sxs-lookup"><span data-stu-id="75f4a-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="75f4a-211">Om ditt skannertjänstkonto  inte kan beviljas logga in lokalt direkt för installationen använder du parametern *OnBehalfOf* med [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)enligt beskrivningen i Så här etiketterar du filer icke-interaktivt för [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="75f4a-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="75f4a-212">Kör [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), ange värden som kopieras från Ditt Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="75f4a-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="75f4a-213">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="75f4a-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="75f4a-214">Skannern har nu en token som autentiseras i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75f4a-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="75f4a-215">Denna token är giltig i ett år, två år eller aldrig, enligt konfigurationen av webbappen **/API-klienthemligheten** i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75f4a-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="75f4a-216">När token går ut måste du upprepa proceduren.</span><span class="sxs-lookup"><span data-stu-id="75f4a-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="75f4a-217">Kör [cmdleten Set-AIP ScannernerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) för att ställa in skannern så att den fungerar i offlineläge.</span><span class="sxs-lookup"><span data-stu-id="75f4a-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="75f4a-218">Kör:</span><span class="sxs-lookup"><span data-stu-id="75f4a-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="75f4a-219">Kör [cmdleten Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) för att skapa ett standardjobb för innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="75f4a-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="75f4a-220">Den enda obligatoriska parametern i **cmdleten Set-AIPScannerContentJob är** **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="75f4a-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="75f4a-221">Men du kanske vill definiera andra inställningar för genomsökningsjobbet för innehåll just nu.</span><span class="sxs-lookup"><span data-stu-id="75f4a-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="75f4a-222">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="75f4a-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="75f4a-223">Syntaxen ovan konfigurerar följande inställningar när du fortsätter konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="75f4a-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="75f4a-224">Gör så att schemaläggningen av skannern körs *manuellt*</span><span class="sxs-lookup"><span data-stu-id="75f4a-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="75f4a-225">Anger vilka informationstyper som ska identifieras utifrån känslighetsetiketts princip</span><span class="sxs-lookup"><span data-stu-id="75f4a-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="75f4a-226">Tillämpar *inte* en princip för känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="75f4a-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="75f4a-227">Automatiskt etiketterar filer baserat på innehåll med hjälp av standardetiketten som definierats för känslighetsetikettsprincipen</span><span class="sxs-lookup"><span data-stu-id="75f4a-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="75f4a-228">Tillåter  inte att filer relabels</span><span class="sxs-lookup"><span data-stu-id="75f4a-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="75f4a-229">Bevarar filinformation vid genomsökning och automatisk etikettering, inklusive *senast ändrad,* *senast ändrad* och *ändrad av* värden</span><span class="sxs-lookup"><span data-stu-id="75f4a-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="75f4a-230">Ställer in skannern till att utesluta .msg- och .tmp-filer när den körs</span><span class="sxs-lookup"><span data-stu-id="75f4a-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="75f4a-231">Anger standardägaren till det konto som du vill använda när skannern körs</span><span class="sxs-lookup"><span data-stu-id="75f4a-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="75f4a-232">Använd cmdleten [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) till att definiera de lagringsgränser du vill söka igenom i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="75f4a-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="75f4a-233">Kör till exempel:</span><span class="sxs-lookup"><span data-stu-id="75f4a-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="75f4a-234">Använd någon av följande syntaxer, beroende på vilken typ av lagringsplats du lägger till:</span><span class="sxs-lookup"><span data-stu-id="75f4a-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="75f4a-235">För en nätverksresurs använder du `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="75f4a-236">För ett SharePoint använder du `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="75f4a-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="75f4a-237">För en lokal sökväg: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="75f4a-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="75f4a-238">För en UNC-sökväg: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="75f4a-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="75f4a-239">Jokertecken stöds inte och WebDav-platser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="75f4a-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="75f4a-240">Om du vill ändra lagringsplatsen senare använder du cmdleten [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) i stället.</span><span class="sxs-lookup"><span data-stu-id="75f4a-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="75f4a-241">Fortsätt med följande steg efter behov:</span><span class="sxs-lookup"><span data-stu-id="75f4a-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="75f4a-242">Köra en identifieringscykel och visa rapporter för skannern</span><span class="sxs-lookup"><span data-stu-id="75f4a-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="75f4a-243">Använda PowerShell för att konfigurera skannern att tillämpa klassificering och skydd</span><span class="sxs-lookup"><span data-stu-id="75f4a-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="75f4a-244">Använda PowerShell för att konfigurera en DLP-princip med skannern</span><span class="sxs-lookup"><span data-stu-id="75f4a-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="75f4a-245">I följande tabell visas PowerShell-cmdlets som är relevanta för installation av skannern och hantering av innehållssökningsjobb:</span><span class="sxs-lookup"><span data-stu-id="75f4a-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="75f4a-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="75f4a-246">Cmdlet</span></span> | <span data-ttu-id="75f4a-247">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="75f4a-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="75f4a-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="75f4a-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="75f4a-249">Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="75f4a-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="75f4a-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="75f4a-251">Returnerar information om klustret.</span><span class="sxs-lookup"><span data-stu-id="75f4a-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="75f4a-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="75f4a-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="75f4a-253">Hämtar information om ditt innehållssökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="75f4a-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="75f4a-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="75f4a-255">Hämtar information om lagringsplatsen som definierats för ditt genomsökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="75f4a-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-256">Remove-AIPScannerContentScan Job</span><span class="sxs-lookup"><span data-stu-id="75f4a-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="75f4a-257">Tar bort ditt genomsökningsjobb.</span><span class="sxs-lookup"><span data-stu-id="75f4a-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="75f4a-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="75f4a-259">Tar bort en lagringsplats från innehållssökningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="75f4a-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="75f4a-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="75f4a-261">Definierar inställningar för innehållssökningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="75f4a-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="75f4a-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="75f4a-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="75f4a-263">Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="75f4a-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="75f4a-264">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="75f4a-264">For more information, see:</span></span>

- [<span data-ttu-id="75f4a-265">Vad är en enhetlig azure Information Protection-skanner?</span><span class="sxs-lookup"><span data-stu-id="75f4a-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="75f4a-266">Konfigurera och installera en enhetlig AIP-skanner (Azure Information Protection)</span><span class="sxs-lookup"><span data-stu-id="75f4a-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="75f4a-267">[Hantera genomsökningsjobb med bara PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="75f4a-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
