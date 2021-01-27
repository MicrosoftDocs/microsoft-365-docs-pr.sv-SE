---
title: Support för Azure information Protection för Office 365 som drivs av 21Vianet
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
description: Lär dig mer om Azure information Protection (AIP) för Office 365 som drivs av 21Vianet och hur du konfigurerar den för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988050"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="dcbcb-103">Support för Azure information Protection för Office 365 som drivs av 21Vianet</span><span class="sxs-lookup"><span data-stu-id="dcbcb-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="dcbcb-104">I den här artikeln beskrivs skillnaderna mellan Azure information Protection (AIP)-stöd för Office 365 som drivs av 21Vianet och kommersiella bud samt särskilda anvisningar för hur du konfigurerar AIP för kunder i Kina, &mdash; inklusive hur du installerar den lokala skannern för AIP och hanterar innehålls genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="dcbcb-105">Skillnader mellan AIP för Office 365 som drivs av 21Vianet och kommersiella bud</span><span class="sxs-lookup"><span data-stu-id="dcbcb-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="dcbcb-106">När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt AIP för Office 365 som drivs av 21Vianet-bud finns det en del av de funktioner som vi vill framhäva.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="dcbcb-107">Följande lista innehåller befintliga luckor mellan AIP för Office 365 som drivs av 21Vianet och våra kommersiella bud per den 2021 januari:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="dcbcb-108">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="dcbcb-109">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="dcbcb-110">Migrering från AD RMS (Active Directory Rights Management Services) till AIP är inte tillgängligt för tillfället.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="dcbcb-111">Det går att dela skyddade e-postmeddelanden med användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="dcbcb-112">Det går för närvarande inte att dela dokument och bifogade filer med användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="dcbcb-113">Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="dcbcb-114">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="dcbcb-115">Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="dcbcb-116">[Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) stöds inte av Azure Kina 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="dcbcb-117">Konfigurera AIP för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="dcbcb-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="dcbcb-118">Så här konfigurerar du AIP för kunder i Kina:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="dcbcb-119">[Aktivera rättighets hantering för innehavaren](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="dcbcb-120">[Konfigurera DNS-kryptering](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="dcbcb-121">[Installera och konfigurera AIP Unified Labeling-klienten](#step-3-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="dcbcb-122">[Konfigurera AIP-appar i Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="dcbcb-123">[Installera AIP lokala skanner och hantera innehålls genomsöknings jobb](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="dcbcb-124">Steg 1: Aktivera rättighets hantering för klient organisationen</span><span class="sxs-lookup"><span data-stu-id="dcbcb-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="dcbcb-125">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="dcbcb-126">Kontrol lera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="dcbcb-127">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="dcbcb-128">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="dcbcb-129">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="dcbcb-130">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="dcbcb-131">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrol lera om tillståndet är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="dcbcb-132">Kör om det funktionella läget är `Disabled` `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="dcbcb-133">Steg 2: Konfigurera DNS-kryptering</span><span class="sxs-lookup"><span data-stu-id="dcbcb-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="dcbcb-134">För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="dcbcb-135">För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="dcbcb-136">Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="dcbcb-137">Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="dcbcb-138">Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="dcbcb-139">Konfigurera DNS-kryptering – Windows</span><span class="sxs-lookup"><span data-stu-id="dcbcb-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="dcbcb-140">Hämta RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="dcbcb-141">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="dcbcb-142">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="dcbcb-143">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="dcbcb-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="dcbcb-144">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="dcbcb-145">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="dcbcb-146">Tjänst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="dcbcb-147">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="dcbcb-148">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="dcbcb-149">Target = `[GUID].rms.aadrm.cn` (där GUID är ett RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="dcbcb-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="dcbcb-150">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="dcbcb-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="dcbcb-151">Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="dcbcb-152">Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="dcbcb-153">Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="dcbcb-154">I verifierings processen kanske ytterligare DNS-ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="dcbcb-155">När verifieringen är klar kan du skapa användare.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="dcbcb-156">Konfigurera DNS-kryptering-Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="dcbcb-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="dcbcb-157">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="dcbcb-158">Tjänst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="dcbcb-159">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-159">Protocol = `_http`</span></span>
- <span data-ttu-id="dcbcb-160">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-160">Name = `_tcp`</span></span>
- <span data-ttu-id="dcbcb-161">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="dcbcb-162">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-162">Port = `80`</span></span>
- <span data-ttu-id="dcbcb-163">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="dcbcb-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="dcbcb-164">Steg 3: installera och konfigurera AIP Unified etiketting-klienten</span><span class="sxs-lookup"><span data-stu-id="dcbcb-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="dcbcb-165">Ladda ned AIP Unified Labeling-klienten från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="dcbcb-166">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-166">For more information, see:</span></span>

- [<span data-ttu-id="dcbcb-167">AIP dokumentation</span><span class="sxs-lookup"><span data-stu-id="dcbcb-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="dcbcb-168">Versions historik och support policy för AIP</span><span class="sxs-lookup"><span data-stu-id="dcbcb-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="dcbcb-169">System krav för AIP</span><span class="sxs-lookup"><span data-stu-id="dcbcb-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="dcbcb-170">AIP snabb start: Distribuera AIP-klienten</span><span class="sxs-lookup"><span data-stu-id="dcbcb-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="dcbcb-171">AIP administratörs guide</span><span class="sxs-lookup"><span data-stu-id="dcbcb-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="dcbcb-172">AIP användar guide</span><span class="sxs-lookup"><span data-stu-id="dcbcb-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="dcbcb-173">Lär dig mer om Microsoft 365-känslighets etiketter</span><span class="sxs-lookup"><span data-stu-id="dcbcb-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="dcbcb-174">Steg 4: Konfigurera AIP-appar i Windows</span><span class="sxs-lookup"><span data-stu-id="dcbcb-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="dcbcb-175">AIP-appar i Windows behöver följande register nyckel för att kunna peka på rätt kraft-moln för Azure Kina:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="dcbcb-176">Registry Node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="dcbcb-177">Namn = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="dcbcb-178">Värde = `6` (standardvärde = 0)</span><span class="sxs-lookup"><span data-stu-id="dcbcb-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="dcbcb-179">Skriv = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="dcbcb-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcbcb-180">Se till att du inte tar bort register nyckel efter en avinstallation.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="dcbcb-181">Om knappen är tom, felaktig eller inte finns, fungerar funktionerna som standardvärde (standardvärde = 0 för det kommersiella molnet).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="dcbcb-182">Om tangenten är tom eller felaktig läggs ett utskrifts fel till i loggen.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="dcbcb-183">Steg 5: installera den lokala skannern för AIP och hantera innehålls genomsöknings jobb</span><span class="sxs-lookup"><span data-stu-id="dcbcb-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="dcbcb-184">Installera den lokala skannern i AIP för att söka igenom dina nätverks-och innehålls resurser för att Visa känsliga data och tillämpa klassificerings-och skydds etiketter enligt organisationens princip.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="dcbcb-185">När du installerar skannern och hanterar dina innehålls genomsöknings jobb kan du använda följande cmdletar i stället för Azure Portal-gränssnittet som används av de kommersiella medarbetarna:</span><span class="sxs-lookup"><span data-stu-id="dcbcb-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="dcbcb-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dcbcb-186">Cmdlet</span></span> | <span data-ttu-id="dcbcb-187">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dcbcb-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="dcbcb-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="dcbcb-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="dcbcb-189">Lägger till en ny lagrings plats i innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="dcbcb-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="dcbcb-191">Hämtar information om ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="dcbcb-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="dcbcb-193">Hämtar information om databaserna som har definierats för innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="dcbcb-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="dcbcb-195">Tar bort ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="dcbcb-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="dcbcb-197">Tar bort en databas från ditt innehålls genomsöknings jobb.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="dcbcb-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="dcbcb-199">Definierar inställningar för innehålls genomsöknings jobbet.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="dcbcb-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="dcbcb-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="dcbcb-201">Definierar inställningar för en befintlig databas i innehålls genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="dcbcb-202">Mer information finns i [Vad är Azure information Protection Unified etiketting-skannern?](/azure/information-protection/deploy-aip-scanner) och [Hantera dina innehålls genomsöknings jobb med bara PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>