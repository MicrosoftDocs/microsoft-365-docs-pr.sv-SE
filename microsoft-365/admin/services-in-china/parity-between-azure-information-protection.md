---
title: Azure Information Protection-support för Office 365 som drivs av 21Vianet
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
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099684"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="25b58-103">Azure Information Protection-support för Office 365 som drivs av 21Vianet</span><span class="sxs-lookup"><span data-stu-id="25b58-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="25b58-104">I den här artikeln beskrivs skillnaderna mellan stöd för Azure Information Protection (AIP) för Office 365 som drivs av 21Vianet och kommersiella erbjudanden, samt specifika instruktioner för hur du konfigurerar AIP för kunder i Kina, inklusive hur du installerar en lokal AIP-skanner och hanterar snabbsökningsjobb för &mdash; innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="25b58-105">Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella erbjudanden</span><span class="sxs-lookup"><span data-stu-id="25b58-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="25b58-106">Även om vårt mål är att leverera alla kommersiella funktioner till kunder i Kina med AIP för Office 365 som drivs av 21Vianet-erbjudandet finns det några funktioner som vi vill lyfta fram.</span><span class="sxs-lookup"><span data-stu-id="25b58-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="25b58-107">Följande lista innehåller de befintliga luckorna mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med januari 2021:</span><span class="sxs-lookup"><span data-stu-id="25b58-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="25b58-108">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731.10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="25b58-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="25b58-109">Office 2010, Office 2013 och andra versioner av Office 2016 stöds inte.</span><span class="sxs-lookup"><span data-stu-id="25b58-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="25b58-110">Migrering från AD RMS (Active Directory Rights Management Services) till AIP är för närvarande inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="25b58-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="25b58-111">Delning av skyddade e-postmeddelanden med användare i det kommersiella molnet stöds.</span><span class="sxs-lookup"><span data-stu-id="25b58-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="25b58-112">Delning av dokument och e-postbilagor med användare i det kommersiella molnet är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="25b58-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="25b58-113">Detta omfattar Office 365 som drivs av 21Vianet-användare i kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i kommersiella molnet och användare med en RMS för individer-licens.</span><span class="sxs-lookup"><span data-stu-id="25b58-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="25b58-114">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="25b58-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="25b58-115">Tillägget för mobila enheter för AD RMS är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="25b58-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="25b58-116">[Mobile Viewer stöds](/azure/information-protection/rms-client/mobile-app-faq) inte av Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="25b58-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="25b58-117">Området AIP på Azure-portalen är inte tillgängligt för kunder i Kina.</span><span class="sxs-lookup"><span data-stu-id="25b58-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="25b58-118">Använd [PowerShell-kommandon](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) i stället för att utföra åtgärder i portalen, till exempel installera den lokala skannern och hantera sökjobben för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="25b58-119">Konfigurera AIP för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="25b58-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="25b58-120">Så här konfigurerar du AIP för kunder i Kina:</span><span class="sxs-lookup"><span data-stu-id="25b58-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="25b58-121">[Aktivera rättighetshantering för klientorganisationen.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="25b58-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="25b58-122">[Konfigurera DNS-kryptering.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="25b58-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="25b58-123">[Installera och konfigurera klient för enhetliga etiketter i AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="25b58-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="25b58-124">[Konfigurera AIP-appar i Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="25b58-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="25b58-125">[Installera den lokala AIP-skannern och hantera genomsökningsjobb för innehåll.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="25b58-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="25b58-126">Steg 1: Aktivera rättighetshantering för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="25b58-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="25b58-127">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="25b58-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="25b58-128">Kontrollera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="25b58-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="25b58-129">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="25b58-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="25b58-130">Om AIPService-modulen inte är installerad kör `Install-Module AipService` du.</span><span class="sxs-lookup"><span data-stu-id="25b58-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="25b58-131">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="25b58-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="25b58-132">Anslut till tjänsten med hjälp av `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="25b58-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="25b58-133">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om statusen är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="25b58-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="25b58-134">Om funktionstillståndet är `Disabled` , kör `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="25b58-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="25b58-135">Steg 2: Konfigurera DNS-kryptering</span><span class="sxs-lookup"><span data-stu-id="25b58-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="25b58-136">För att krypteringen ska fungera måste Office-klientprogrammen ansluta till Kina-instansen av tjänsten och bootstrap därifrån.</span><span class="sxs-lookup"><span data-stu-id="25b58-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="25b58-137">För att omdirigera klientprogram till rätt tjänstinstans måste innehavaradministratören konfigurera en DNS SRV-post med information om Azure RMS URL.</span><span class="sxs-lookup"><span data-stu-id="25b58-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="25b58-138">Utan DNS SRV-posten försöker klientprogrammet ansluta till den offentliga molninstansen som standard och kommer att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="25b58-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="25b58-139">Antagandet är också att användare loggar in med ett användarnamn baserat på den klientägda domänen (t.ex. ) och inte `joe@contoso.cn` `onmschina` användarnamnet (t.ex. `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="25b58-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="25b58-140">Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="25b58-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="25b58-141">Konfigurera DNS-kryptering – Windows</span><span class="sxs-lookup"><span data-stu-id="25b58-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="25b58-142">Skaffa RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="25b58-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="25b58-143">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="25b58-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="25b58-144">Om AIPService-modulen inte är installerad kör `Install-Module AipService` du.</span><span class="sxs-lookup"><span data-stu-id="25b58-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="25b58-145">Anslut till tjänsten med hjälp av `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="25b58-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="25b58-146">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att få RMS-ID.</span><span class="sxs-lookup"><span data-stu-id="25b58-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="25b58-147">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="25b58-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="25b58-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="25b58-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="25b58-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="25b58-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="25b58-150">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="25b58-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="25b58-151">Target = `[GUID].rms.aadrm.cn` (där GUID är RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="25b58-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="25b58-152">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="25b58-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="25b58-153">Koppla den anpassade domänen till klientorganisationen i [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="25b58-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="25b58-154">Då kommer en post i DNS att läggas till, vilket kan ta flera minuter att verifieras när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="25b58-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="25b58-155">Logga in på administrationscentret för Microsoft 365 med motsvarande autentiseringsuppgifter som global administratör och lägg till domänen (till `contoso.cn` exempel) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="25b58-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="25b58-156">I verifieringsprocessen kan ytterligare DNS-ändringar krävas.</span><span class="sxs-lookup"><span data-stu-id="25b58-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="25b58-157">När verifieringen är klar kan användarna skapas.</span><span class="sxs-lookup"><span data-stu-id="25b58-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="25b58-158">Konfigurera DNS-kryptering – Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="25b58-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="25b58-159">Logga in på din DNS-leverantör, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="25b58-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="25b58-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="25b58-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="25b58-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="25b58-161">Protocol = `_http`</span></span>
- <span data-ttu-id="25b58-162">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="25b58-162">Name = `_tcp`</span></span>
- <span data-ttu-id="25b58-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="25b58-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="25b58-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="25b58-164">Port = `80`</span></span>
- <span data-ttu-id="25b58-165">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="25b58-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="25b58-166">Steg 3: Installera och konfigurera den enhetliga AIP-etikettklienten</span><span class="sxs-lookup"><span data-stu-id="25b58-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="25b58-167">Ladda ned AIP Unified Labeling Client från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="25b58-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="25b58-168">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="25b58-168">For more information, see:</span></span>

- [<span data-ttu-id="25b58-169">AIP-dokumentation</span><span class="sxs-lookup"><span data-stu-id="25b58-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="25b58-170">AIP-versionshistorik och supportpolicy</span><span class="sxs-lookup"><span data-stu-id="25b58-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="25b58-171">Systemkrav för AIP</span><span class="sxs-lookup"><span data-stu-id="25b58-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="25b58-172">Snabbstartsguide för AIP: Distribuera AIP-klienten</span><span class="sxs-lookup"><span data-stu-id="25b58-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="25b58-173">AIP-administratörsguide</span><span class="sxs-lookup"><span data-stu-id="25b58-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="25b58-174">Användarhandbok för AIP</span><span class="sxs-lookup"><span data-stu-id="25b58-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="25b58-175">Läs mer om känslighetsetiketter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25b58-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="25b58-176">Steg 4: Konfigurera AIP-appar i Windows</span><span class="sxs-lookup"><span data-stu-id="25b58-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="25b58-177">AIP-appar i Windows behöver följande registernyckel för att kunna peka dem till rätt självständig moln för Azure China:</span><span class="sxs-lookup"><span data-stu-id="25b58-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="25b58-178">Registernod = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="25b58-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="25b58-179">Namn = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="25b58-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="25b58-180">Värde = `6` (standard = 0)</span><span class="sxs-lookup"><span data-stu-id="25b58-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="25b58-181">Typ = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="25b58-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25b58-182">Se till att du inte tar bort registernyckeln efter en avinstallation.</span><span class="sxs-lookup"><span data-stu-id="25b58-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="25b58-183">Om nyckeln är tom, felaktig eller inte finns fungerar funktionen som standardvärdet (standardvärdet = 0 för det kommersiella molnet).</span><span class="sxs-lookup"><span data-stu-id="25b58-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="25b58-184">Om nyckeln är tom eller felaktig läggs även ett utskriftsfel till i loggen.</span><span class="sxs-lookup"><span data-stu-id="25b58-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="25b58-185">Steg 5: Installera den lokala AIP-skannern och hantera genomsökningsjobb för innehåll</span><span class="sxs-lookup"><span data-stu-id="25b58-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="25b58-186">Installera den lokala AIP-skannern för att söka igenom nätverks- och innehållsresurser efter känsliga data och tillämpa klassificerings- och skyddsetiketter enligt organisationens policy.</span><span class="sxs-lookup"><span data-stu-id="25b58-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="25b58-187">När du installerar skannern och hanterar genomsökningsjobben för innehåll ska du använda följande cmdlets i stället för Azure Portal-gränssnittet som används av kommersiella erbjudanden:</span><span class="sxs-lookup"><span data-stu-id="25b58-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="25b58-188">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="25b58-188">Cmdlet</span></span> | <span data-ttu-id="25b58-189">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="25b58-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="25b58-190">Add-AIPDatabasnerRepository</span><span class="sxs-lookup"><span data-stu-id="25b58-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="25b58-191">Lägger till en ny lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="25b58-192">Get-AIPKonventionnerContent Entledig</span><span class="sxs-lookup"><span data-stu-id="25b58-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="25b58-193">Hämtar information om ditt genomsökningsjobb för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="25b58-194">Get-AIPDatabasnerRepository</span><span class="sxs-lookup"><span data-stu-id="25b58-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="25b58-195">Hämtar information om lagringsplatsen som definierats för genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="25b58-196">Remove-AIPKonventionnerContent Entledig</span><span class="sxs-lookup"><span data-stu-id="25b58-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="25b58-197">Tar bort genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="25b58-198">Remove-AIPDatabaserRepository</span><span class="sxs-lookup"><span data-stu-id="25b58-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="25b58-199">Tar bort en lagringsplats från genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="25b58-200">Set-AIP Det här är Set-AIPKonventionnerContentNyckel</span><span class="sxs-lookup"><span data-stu-id="25b58-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="25b58-201">Definierar inställningar för genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="25b58-202">Set-AIPDatabasnerRepository</span><span class="sxs-lookup"><span data-stu-id="25b58-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="25b58-203">Definierar inställningar för en befintlig lagringsplats i genomsökningsjobbet för innehåll.</span><span class="sxs-lookup"><span data-stu-id="25b58-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="25b58-204">Mer information finns i Vad är en enhetlig [azure Information Protection-skanner?](/azure/information-protection/deploy-aip-scanner) och Hantera sökjobben för innehåll [med endast PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="25b58-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
