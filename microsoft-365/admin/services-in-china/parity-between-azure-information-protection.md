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
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519347"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="2658b-103">Paritet mellan Azure information Protection för Office 365 som drivs av 21Vianet och kommersiella offerter</span><span class="sxs-lookup"><span data-stu-id="2658b-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="2658b-104">När vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure information Protection för Office 365 som drivs av 21Vianet-bud, finns det en del funktioner som vi vill framhäva.</span><span class="sxs-lookup"><span data-stu-id="2658b-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="2658b-105">Följande lista innehåller befintliga luckor mellan Azure information Protection for Office 365 som drivs av 21Vianet och våra kommersiella bud från och med den 2019 juli:</span><span class="sxs-lookup"><span data-stu-id="2658b-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="2658b-106">IRM (Information Rights Management) stöds endast för Microsoft 365-program för företag (version 11731,10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="2658b-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="2658b-107">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="2658b-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="2658b-108">Migrering från AD RMS (Active Directory Rights Management Services) till Azure information Protection är för närvarande inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2658b-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="2658b-109">Det går att dela skyddade e-postmeddelanden till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="2658b-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="2658b-110">Det går för närvarande inte att dela dokument och e-postbilagor till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="2658b-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="2658b-111">Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en licens för en person.</span><span class="sxs-lookup"><span data-stu-id="2658b-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="2658b-112">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="2658b-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="2658b-113">Mobil enhets tillägget för AD RMS är för närvarande inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="2658b-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="2658b-114">Konfigurera Azure information Protection för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="2658b-114">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="2658b-115">Aktivera rättighets hantering för klient organisationen</span><span class="sxs-lookup"><span data-stu-id="2658b-115">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="2658b-116">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="2658b-116">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="2658b-117">Kontrol lera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="2658b-117">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="2658b-118">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="2658b-118">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2658b-119">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2658b-119">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2658b-120">Importera modulen med `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2658b-120">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="2658b-121">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="2658b-121">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="2658b-122">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrol lera om tillståndet är `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="2658b-122">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="2658b-123">Kör om det funktionella läget är `Disabled` `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="2658b-123">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="2658b-124">DNS-konfiguration för kryptering (Windows)</span><span class="sxs-lookup"><span data-stu-id="2658b-124">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="2658b-125">För att krypteringen ska fungera korrekt måste Office-klientprogrammet ansluta till Kina-instansen av tjänsten och starta därifrån.</span><span class="sxs-lookup"><span data-stu-id="2658b-125">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="2658b-126">För att omdirigera klient program till den högra tjänst instansen måste klient organisationens administratör konfigurera en DNS SRV-post med information om URL-adressen för Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="2658b-126">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="2658b-127">Utan DNS SRV-posten försöker klient programmet ansluta till den offentliga moln instansen som standard och kommer inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="2658b-127">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="2658b-128">Dessutom är antagandet att användare loggar in med ett användar namn som baseras på den klient organisationens domän (till exempel `joe@contoso.cn` ) och inte `onmschina` användar namnet (till exempel `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="2658b-128">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="2658b-129">Domän namnet från username används för DNS-omdirigering till rätt tjänst instans.</span><span class="sxs-lookup"><span data-stu-id="2658b-129">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="2658b-130">Hämta RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="2658b-130">Get the RMS ID:</span></span>
  1. <span data-ttu-id="2658b-131">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="2658b-131">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2658b-132">Om AIPService-modulen inte är installerad kör du `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2658b-132">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2658b-133">Anslut till tjänsten med `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="2658b-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="2658b-134">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID.</span><span class="sxs-lookup"><span data-stu-id="2658b-134">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="2658b-135">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="2658b-135">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2658b-136">Tjänst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="2658b-136">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="2658b-137">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="2658b-137">Protocol = `_http`</span></span>
  - <span data-ttu-id="2658b-138">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2658b-138">Name = `_tcp`</span></span>
  - <span data-ttu-id="2658b-139">Target = `[GUID].rms.aadrm.cn` (där GUID är ett RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="2658b-139">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="2658b-140">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="2658b-140">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="2658b-141">Koppla den anpassade domänen till klient organisationen i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="2658b-141">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="2658b-142">Detta lägger till en post i DNS som kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2658b-142">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="2658b-143">Logga in i administrations centret för Microsoft 365 med motsvarande globala administratörs behörighet och Lägg till domänen (till exempel `contoso.cn` ) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="2658b-143">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="2658b-144">I verifierings processen kanske ytterligare DNS-ändringar krävs.</span><span class="sxs-lookup"><span data-stu-id="2658b-144">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="2658b-145">När verifieringen är klar kan du skapa användare.</span><span class="sxs-lookup"><span data-stu-id="2658b-145">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="2658b-146">DNS-konfiguration för kryptering (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="2658b-146">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="2658b-147">Logga in på din DNS-leverantör, gå till DNS-inställningarna för domänen och Lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="2658b-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2658b-148">Tjänst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="2658b-148">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="2658b-149">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="2658b-149">Protocol = `_http`</span></span>
  - <span data-ttu-id="2658b-150">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2658b-150">Name = `_tcp`</span></span>
  - <span data-ttu-id="2658b-151">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="2658b-151">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="2658b-152">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="2658b-152">Port = `80`</span></span>
  - <span data-ttu-id="2658b-153">Prioritet, vikt, sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="2658b-153">Priority, Weight, Seconds, TTL = default values</span></span>
