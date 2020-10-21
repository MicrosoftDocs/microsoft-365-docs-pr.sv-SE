---
title: Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter
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
description: Läs mer om Azure information Protection för Office 365 som drivs av 21Vianet och hur du konfigurerar den för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: ad3420483701c83ffef65994996047de56a7085c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644669"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="bf024-103">Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter</span><span class="sxs-lookup"><span data-stu-id="bf024-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="bf024-104">När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure information Protection för Office 365 som drivs av 21Vianet-bud, finns det en del funktioner som vi vill framhäva.</span><span class="sxs-lookup"><span data-stu-id="bf024-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="bf024-105">Följande lista innehåller befintliga luckor mellan Azure information Protection for Office 365 som drivs av 21Vianet och våra kommersiella bud från och med den 2019 juli:</span><span class="sxs-lookup"><span data-stu-id="bf024-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="bf024-106">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="bf024-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="bf024-107">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="bf024-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="bf024-108">Migrering från AD RMS (Active Directory Rights Management Services) till Azure information Protection är för närvarande inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="bf024-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="bf024-109">Det går att dela skyddade e-postmeddelanden till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="bf024-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="bf024-110">Det går för närvarande inte att dela dokument och e-postbilagor till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="bf024-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="bf024-111">Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.</span><span class="sxs-lookup"><span data-stu-id="bf024-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="bf024-112">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="bf024-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="bf024-113">Rights Management Connector är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="bf024-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="bf024-114">Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="bf024-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="bf024-115">Konfigurera Azure information Protection för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="bf024-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="bf024-116">Aktivera rättighets hantering för klient organisationen</span><span class="sxs-lookup"><span data-stu-id="bf024-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="bf024-117">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="bf024-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="bf024-118">Kontrol lera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="bf024-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="bf024-119">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="bf024-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="bf024-120">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="bf024-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="bf024-121">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="bf024-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="bf024-122">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="bf024-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="bf024-123">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrol lera om tillståndet är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="bf024-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="bf024-124">Kör om det funktionella läget är `Disabled` `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="bf024-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="bf024-125">DNS-konfiguration för kryptering (Windows)</span><span class="sxs-lookup"><span data-stu-id="bf024-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="bf024-126">För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån.</span><span class="sxs-lookup"><span data-stu-id="bf024-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="bf024-127">För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="bf024-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="bf024-128">Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="bf024-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="bf024-129">Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="bf024-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="bf024-130">Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.</span><span class="sxs-lookup"><span data-stu-id="bf024-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="bf024-131">Hämta RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="bf024-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="bf024-132">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="bf024-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="bf024-133">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="bf024-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="bf024-134">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="bf024-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="bf024-135">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID.</span><span class="sxs-lookup"><span data-stu-id="bf024-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="bf024-136">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="bf024-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="bf024-137">Tjänst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="bf024-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="bf024-138">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="bf024-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="bf024-139">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="bf024-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="bf024-140">Target = `[GUID].rms.aadrm.cn` (där GUID är ett RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="bf024-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="bf024-141">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="bf024-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="bf024-142">Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="bf024-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="bf024-143">Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="bf024-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="bf024-144">Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="bf024-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="bf024-145">I verifierings processen kanske ytterligare DNS-ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="bf024-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="bf024-146">När verifieringen är klar kan du skapa användare.</span><span class="sxs-lookup"><span data-stu-id="bf024-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="bf024-147">DNS-konfiguration för kryptering (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="bf024-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="bf024-148">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="bf024-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="bf024-149">Tjänst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="bf024-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="bf024-150">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="bf024-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="bf024-151">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="bf024-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="bf024-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="bf024-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="bf024-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="bf024-153">Port = `80`</span></span>
  - <span data-ttu-id="bf024-154">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="bf024-154">Priority, Weight, Seconds, TTL = default values</span></span>
