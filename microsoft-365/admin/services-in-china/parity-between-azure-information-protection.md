---
title: Office 365 med 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Läs mer om Azure Information Protection för Office 365 som drivs av 21Vianet och hur du konfigurerar det för kunder i Kina.
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808703"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="745ab-103">Paritet mellan Azure Information Protection for Office 365 som drivs av 21Vianet och kommersiella erbjudanden</span><span class="sxs-lookup"><span data-stu-id="745ab-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="745ab-104">Vårt mål är att leverera alla kommersiella funktioner och funktioner till kunder i Kina med vårt Azure Information Protection for Office 365 som drivs av 21Vianet-erbjudandet, men det finns vissa funktioner som saknas som vi vill lyfta fram.</span><span class="sxs-lookup"><span data-stu-id="745ab-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="745ab-105">Det här är de befintliga luckorna mellan Azure Information Protection for Office 365 som drivs av 21Vianet och våra kommersiella erbjudanden från och med juli 2019:</span><span class="sxs-lookup"><span data-stu-id="745ab-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="745ab-106">IRM (Information Rights Management) stöds endast för Office 365 ProPlus (version 11731.10000 eller senare).</span><span class="sxs-lookup"><span data-stu-id="745ab-106">Information Rights Management (IRM) is supported only for Office 365 ProPlus (build 11731.10000 or higher).</span></span> <span data-ttu-id="745ab-107">Office 2010, Office 2013 och andra Office 2016-versioner stöds inte.</span><span class="sxs-lookup"><span data-stu-id="745ab-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="745ab-108">Migrering från AD RMS (Active Directory Rights Management Services) till Azure Information Protection är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="745ab-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="745ab-109">Delning av skyddade e-postmeddelanden till användare i det kommersiella molnet stöds.</span><span class="sxs-lookup"><span data-stu-id="745ab-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="745ab-110">Det är för närvarande inte tillgängligt att dela dokument och e-postbilagor till användare i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="745ab-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="745ab-111">Detta inkluderar Office 365 som drivs av 21Vianet-användare i det kommersiella molnet, icke-Office 365 som drivs av 21Vianet-användare i det kommersiella molnet och användare med en RMS for Individuals-licens.</span><span class="sxs-lookup"><span data-stu-id="745ab-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="745ab-112">IRM med SharePoint (IRM-skyddade webbplatser och bibliotek) är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="745ab-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="745ab-113">Rights Management Connector är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="745ab-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="745ab-114">Tillägget för mobila enheter för AD RMS är inte tillgängligt för närvarande.</span><span class="sxs-lookup"><span data-stu-id="745ab-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="745ab-115">Konfigurera Azure Information Protection för kunder i Kina</span><span class="sxs-lookup"><span data-stu-id="745ab-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="745ab-116">Aktivera rättighetshantering för klienten</span><span class="sxs-lookup"><span data-stu-id="745ab-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="745ab-117">För att krypteringen ska fungera korrekt måste RMS vara aktiverat för klienten.</span><span class="sxs-lookup"><span data-stu-id="745ab-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="745ab-118">Kontrollera om RMS är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="745ab-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="745ab-119">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="745ab-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="745ab-120">Om AIPService-modulen inte `Install-Module AipService`är installerad kör du .</span><span class="sxs-lookup"><span data-stu-id="745ab-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="745ab-121">Importera modulen `Import-Module AipService`med .</span><span class="sxs-lookup"><span data-stu-id="745ab-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="745ab-122">Anslut till tjänsten `Connect-AipService -environmentname azurechinacloud`med .</span><span class="sxs-lookup"><span data-stu-id="745ab-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="745ab-123">Kör `(Get-AipServiceConfiguration).FunctionalState` och kontrollera om `Enabled`tillståndet är .</span><span class="sxs-lookup"><span data-stu-id="745ab-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="745ab-124">Om funktionstillståndet `Disabled` `Enable-AipService`är kör du .</span><span class="sxs-lookup"><span data-stu-id="745ab-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="745ab-125">DNS-konfiguration för kryptering (Windows)</span><span class="sxs-lookup"><span data-stu-id="745ab-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="745ab-126">För att kryptering ska fungera korrekt måste Office-klientprogram ansluta till Kina-instansen av tjänsten och bootstrap därifrån.</span><span class="sxs-lookup"><span data-stu-id="745ab-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="745ab-127">Om du vill omdirigera klientprogram till rätt tjänstinstans måste klientadministratören konfigurera en DNS SRV-post med information om Azure RMS-URL:en.</span><span class="sxs-lookup"><span data-stu-id="745ab-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="745ab-128">Utan DNS SRV-posten försöker klientprogrammet som standard ansluta till den offentliga molninstansen och misslyckas.</span><span class="sxs-lookup"><span data-stu-id="745ab-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="745ab-129">Antagandet är också att användare ska logga in med ett användarnamn baserat `joe@contoso.cn`utanför den `onmschina` bostadsrättsägda domänen (till exempel ), och inte användarnamnet (till exempel `joe@contoso.onmschina.cn`).</span><span class="sxs-lookup"><span data-stu-id="745ab-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="745ab-130">Domännamnet från användarnamnet används för DNS-omdirigering till rätt tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="745ab-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="745ab-131">Hämta RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="745ab-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="745ab-132">Starta PowerShell som administratör.</span><span class="sxs-lookup"><span data-stu-id="745ab-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="745ab-133">Om AIPService-modulen inte `Install-Module AipService`är installerad kör du .</span><span class="sxs-lookup"><span data-stu-id="745ab-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="745ab-134">Anslut till tjänsten `Connect-AipService -environmentname azurechinacloud`med .</span><span class="sxs-lookup"><span data-stu-id="745ab-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="745ab-135">Kör `(Get-AipServiceConfiguration).RightsManagementServiceId` för att hämta RMS-ID: et.</span><span class="sxs-lookup"><span data-stu-id="745ab-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="745ab-136">Logga in på DNS-leverantören, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="745ab-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="745ab-137">Tjänst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="745ab-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="745ab-138">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="745ab-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="745ab-139">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="745ab-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="745ab-140">Mål `[GUID].rms.aadrm.cn` = (där GUID är RMS-ID)</span><span class="sxs-lookup"><span data-stu-id="745ab-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="745ab-141">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="745ab-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="745ab-142">Associera den anpassade domänen med klienten i [Azure-portalen](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="745ab-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="745ab-143">Detta lägger till en post i DNS, vilket kan ta flera minuter att verifiera när du har lagt till värdet i DNS-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="745ab-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="745ab-144">Logga in i Microsoft 365-administrationscentret med motsvarande globala administratörsautentiseringsuppgifter och lägg till domänen (till `contoso.cn`exempel) för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="745ab-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="745ab-145">I verifieringsprocessen kan ytterligare DNS-ändringar krävas.</span><span class="sxs-lookup"><span data-stu-id="745ab-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="745ab-146">När verifieringen är klar kan användare skapas.</span><span class="sxs-lookup"><span data-stu-id="745ab-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="745ab-147">DNS-konfiguration för kryptering (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="745ab-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="745ab-148">Logga in på DNS-leverantören, navigera till DNS-inställningarna för domänen och lägg sedan till en ny SRV-post.</span><span class="sxs-lookup"><span data-stu-id="745ab-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="745ab-149">Tjänst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="745ab-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="745ab-150">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="745ab-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="745ab-151">Namn = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="745ab-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="745ab-152">Mål = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="745ab-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="745ab-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="745ab-153">Port = `80`</span></span>
  - <span data-ttu-id="745ab-154">Prioritet, Vikt, Sekunder, TTL = standardvärden</span><span class="sxs-lookup"><span data-stu-id="745ab-154">Priority, Weight, Seconds, TTL = default values</span></span>
