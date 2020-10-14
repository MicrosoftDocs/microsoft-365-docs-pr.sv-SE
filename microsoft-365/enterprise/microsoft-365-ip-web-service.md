---
title: Webbtjänsten Office 365 IP-adress och URL
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Lär dig hur du använder webbtjänsten Office 365 IP-adress and URL för att hjälpa dig att bättre identifiera och skilja Office 365 nätverkstrafik.
ms.openlocfilehash: 03e6eac86e66db6f9e94c3f98e6d7b565ffa0f14
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456465"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="87e37-103">Webbtjänsten Office 365 IP-adress och URL</span><span class="sxs-lookup"><span data-stu-id="87e37-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="87e37-104">Webbtjänsten Office 365 IP-adress och URL hjälper dig att bättre identifiera och särskilja Office 365-nätverkstrafik vilket gör det enklare för dig att utvärdera, konfigurera och hålla dig uppdaterad om ändringarna.</span><span class="sxs-lookup"><span data-stu-id="87e37-104">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes.</span></span> <span data-ttu-id="87e37-105">Den här REST-baserade webbtjänsten ersätter de tidigare nedladdningsbara XML-filerna, som fasades ut den 2 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="87e37-105">This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="87e37-106">Som kund eller leverantör av perimeternätverksenheter kan du bygga mot den webbtjänsten för Office 365 IP-adress och FQDN-poster.</span><span class="sxs-lookup"><span data-stu-id="87e37-106">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries.</span></span> <span data-ttu-id="87e37-107">Du kan komma åt data direkt i en webbläsare med hjälp av följande URL:er:</span><span class="sxs-lookup"><span data-stu-id="87e37-107">You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="87e37-108">Använd [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) för den senaste versionen av Office 365 URL:er och IP-adressintervaller.</span><span class="sxs-lookup"><span data-stu-id="87e37-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="87e37-109">Använd [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) för data på sidan Office 365 URL:er och IP-adressintervaller för brandväggar och proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="87e37-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="87e37-110">Om du vill få de senaste ändringarna sedan juli 2018 när webbtjänsten först var tillgänglig använder du [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="87e37-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="87e37-111">Som kund kan du använda den här webbtjänsten till att:</span><span class="sxs-lookup"><span data-stu-id="87e37-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="87e37-112">Uppdatera PowerShell-skript för att hämta Office 365-slutpunktsdata och ändra eventuell formatering för dina nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="87e37-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="87e37-113">Använd informationen för att uppdatera PAC-filer som distribueras till klientdatorer.</span><span class="sxs-lookup"><span data-stu-id="87e37-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="87e37-114">Som leverantör av perimeternätverksenheter kan du använda den här webbtjänsten till att:</span><span class="sxs-lookup"><span data-stu-id="87e37-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="87e37-115">Skapa och testa enhetsprogramvara för att ladda ned listan för automatiserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="87e37-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="87e37-116">Sök efter den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="87e37-116">Check for the current version.</span></span>
- <span data-ttu-id="87e37-117">Hämta de aktuella ändringarna.</span><span class="sxs-lookup"><span data-stu-id="87e37-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="87e37-118">Om du använder Microsoft Azure ExpressRoute för att ansluta till Office 365 ska du läsa [Azure ExpressRoute for Office 365](azure-expressroute.md) och bekanta dig med de Office 365-tjänster som stöds över Microsoft Azure ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="87e37-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="87e37-119">Läs även artikeln [Office 365 URL:er och IP-adressintervaller](urls-and-ip-address-ranges.md) för att förstå på vilka nätverksbegäranden för Office 365-program som kräver internetanslutning.</span><span class="sxs-lookup"><span data-stu-id="87e37-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="87e37-120">På så sätt kan du konfigurera dina gränssäkerhetsenheter bättre.</span><span class="sxs-lookup"><span data-stu-id="87e37-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="87e37-121">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="87e37-121">For more information, see:</span></span>

- [<span data-ttu-id="87e37-122">Blogginlägg med meddelandet i Office 365 Tech Community-forumet</span><span class="sxs-lookup"><span data-stu-id="87e37-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="87e37-123">Office 365 Tech Community-forumet för frågor om användningen av webbtjänster</span><span class="sxs-lookup"><span data-stu-id="87e37-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="87e37-124">Vanliga parametrar</span><span class="sxs-lookup"><span data-stu-id="87e37-124">Common parameters</span></span>

<span data-ttu-id="87e37-125">Dessa parametrar är gemensamma för alla metoder i webbtjänsten:</span><span class="sxs-lookup"><span data-stu-id="87e37-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="87e37-126">**format–<JSON | CSV>** – Som standard är det returnerade dataformatet JSON.</span><span class="sxs-lookup"><span data-stu-id="87e37-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="87e37-127">Använd den här valfria parametern för att returnera data i en fil med kommaavgränsade värden (CSV).</span><span class="sxs-lookup"><span data-stu-id="87e37-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="87e37-128">**ClientRequestId-\<guid>** – En obligatorisk GUID som du genererar för klientassociation.</span><span class="sxs-lookup"><span data-stu-id="87e37-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="87e37-129">Generera ett unikt GUID för varje dator som anropar webbtjänsten (de skript som finns på den här sidan genererar ett GUID åt dig).</span><span class="sxs-lookup"><span data-stu-id="87e37-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="87e37-130">Använd inte de GUID som visas i följande exempel eftersom de kan blockeras av webbtjänsten i framtiden.</span><span class="sxs-lookup"><span data-stu-id="87e37-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="87e37-131">GUID-formatet är _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, där x representerar ett hexadecimalt tal.</span><span class="sxs-lookup"><span data-stu-id="87e37-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="87e37-132">Om du vill generera ett GUID kan du använda [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) Windows PowerShell-kommandot eller använda en onlinetjänst som [online GUID Generator](https://www.guidgenerator.com/).</span><span class="sxs-lookup"><span data-stu-id="87e37-132">To generate a GUID, you can use the [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="87e37-133">Versionswebbmetod</span><span class="sxs-lookup"><span data-stu-id="87e37-133">Version web method</span></span>

<span data-ttu-id="87e37-134">Microsoft uppdaterar Office 365 IP-adresser och FQDN-poster i slutet av varje månad.</span><span class="sxs-lookup"><span data-stu-id="87e37-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="87e37-135">Out-of-band-uppdateringar publiceras ibland på grund av supportproblem, säkerhetsuppdateringar och andra operativkrav.</span><span class="sxs-lookup"><span data-stu-id="87e37-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="87e37-136">Data för varje publicerad instans tilldelas ett versionsnummer och versionswebbmetoden gör att du kan söka efter den senaste versionen av varje instans av Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-136">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="87e37-137">Vi rekommenderar att du kontrollerar versionen inte är oftare än en gång i timmen.</span><span class="sxs-lookup"><span data-stu-id="87e37-137">We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="87e37-138">Parametrarna för versionswebbmetoden är:</span><span class="sxs-lookup"><span data-stu-id="87e37-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="87e37-139">**AllVersions = <true | false>** – versionen som returneras är den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="87e37-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="87e37-140">Ta med den här valfria parametern för att begära alla publicerade versioner sedan webbtjänsten släpptes.</span><span class="sxs-lookup"><span data-stu-id="87e37-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="87e37-141">**Format = <JSON | CSV | RSS>** – förutom JSON- och CSV-format kan du även använda versionswebbmetoden av RSS.</span><span class="sxs-lookup"><span data-stu-id="87e37-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="87e37-142">Du kan använda den här valfria parametern tillsammans med parametern _AllVersions = True_ för att begära en RSS-feed som kan användas med Outlook eller andra RSS-läsare.</span><span class="sxs-lookup"><span data-stu-id="87e37-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="87e37-143">**Instance = <Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** – i den här valfria parametern anges vilken instans som ska returnera versionen för.</span><span class="sxs-lookup"><span data-stu-id="87e37-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="87e37-144">Om den utelämnas returneras alla instanser.</span><span class="sxs-lookup"><span data-stu-id="87e37-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="87e37-145">Giltiga instanser är: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="87e37-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="87e37-146">Versionswebbmetoden är inte begränsat och returnerar aldrig 429 HTTP-svarskod.</span><span class="sxs-lookup"><span data-stu-id="87e37-146">The version web method is not rate limited and does not ever return 429 HTTP Response Codes.</span></span> <span data-ttu-id="87e37-147">Svaret på versionswebbmetoden innehåller ett huvud för cache-kontroll som rekommenderar cachelagring av data i 1 timme.</span><span class="sxs-lookup"><span data-stu-id="87e37-147">The response to the version web method does include a cache-control header recommending caching of the data for 1 hour.</span></span> <span data-ttu-id="87e37-148">Resultatet av versionswebbmetoden kan vara en enskild post eller en matris med poster.</span><span class="sxs-lookup"><span data-stu-id="87e37-148">The result from the version web method can be a single record or an array of records.</span></span> <span data-ttu-id="87e37-149">Elementen i varje post är:</span><span class="sxs-lookup"><span data-stu-id="87e37-149">The elements of each record are:</span></span>

- <span data-ttu-id="87e37-150">instans – Office 365-tjänstinstansens kortnamn.</span><span class="sxs-lookup"><span data-stu-id="87e37-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="87e37-151">senaste – Den senaste versionen för den angivna instansens slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="87e37-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="87e37-152">versioner – En lista över alla tidigare versioner för den angivna instansen.</span><span class="sxs-lookup"><span data-stu-id="87e37-152">versions — A list of all previous versions for the specified instance.</span></span> <span data-ttu-id="87e37-153">Det här elementet ingår endast om parametern _Allaversioner_ är sann.</span><span class="sxs-lookup"><span data-stu-id="87e37-153">This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="87e37-154">Exempel:</span><span class="sxs-lookup"><span data-stu-id="87e37-154">Examples:</span></span>

<span data-ttu-id="87e37-155">Exempel 1 begär URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-156">Denna URI returnerar den senaste versionen av varje Office 365-tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="87e37-156">This URI returns the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="87e37-157">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-157">Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="87e37-158">GUID för parametern ClientRequestID i dessa URI:er är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="87e37-158">The GUID for the ClientRequestID parameter in these URIs are only an example.</span></span> <span data-ttu-id="87e37-159">Om du vill prova webbtjänstens URI:er måste du generera en egen GUID.</span><span class="sxs-lookup"><span data-stu-id="87e37-159">To try the web service URIs out, generate your own GUID.</span></span> <span data-ttu-id="87e37-160">De GUID som visas i dessa exempel kan blockeras av webbtjänsten i framtiden.</span><span class="sxs-lookup"><span data-stu-id="87e37-160">The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="87e37-161">Exempel 2 begär URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-162">Denna URI returnerar den senaste versionen av den angivna Office 365-tjänstinstansen.</span><span class="sxs-lookup"><span data-stu-id="87e37-162">This URI returns the latest version of the specified Office 365 service instance.</span></span> <span data-ttu-id="87e37-163">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-163">Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="87e37-164">Exempel 3 begär URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-165">Denna URI visas resultatet i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="87e37-165">This URI shows output in CSV format.</span></span> <span data-ttu-id="87e37-166">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-166">Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="87e37-167">Exempel 4 begär URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-168">Denna URI visar alla tidigare versioner som har publicerats för den globala Office 365-tjänstinstansen.</span><span class="sxs-lookup"><span data-stu-id="87e37-168">This URI shows all prior versions that have been published for the Office 365 worldwide service instance.</span></span> <span data-ttu-id="87e37-169">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-169">Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="87e37-170">Exempel 5 RSS feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="87e37-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="87e37-171">Den här URI:n visar ett RSS-flöde av publicerade versioner som innehåller länkar till listan över ändringar för varje version.</span><span class="sxs-lookup"><span data-stu-id="87e37-171">This URI shows an RSS feed of the published versions that include links to the list of changes for each version.</span></span> <span data-ttu-id="87e37-172">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-172">Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="87e37-173">Slutpunktswebbmetod</span><span class="sxs-lookup"><span data-stu-id="87e37-173">Endpoints web method</span></span>

<span data-ttu-id="87e37-174">Slutpunktswebbmetoden returnerar alla poster för IP-adressintervall och URL-adresser som utgör Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="87e37-175">De senaste data från webbmetoden för slutpunkter ska alltid användas för nätverksenhetskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="87e37-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="87e37-176">Microsoft ger dig ett meddelande 30 dagar innan de publicerar nya tillägg för att ge dig tid att uppdatera listor för åtkomstkontroll och förbikopplingslistor för proxyserver.</span><span class="sxs-lookup"><span data-stu-id="87e37-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="87e37-177">Vi rekommenderar att du bara anropar webbmetoden för slutpunkter igen när versionswebbmetoden anger att en ny version av data är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="87e37-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="87e37-178">Parametrarna för slutpunktswebbmetoden är:</span><span class="sxs-lookup"><span data-stu-id="87e37-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="87e37-179">**ServiceAreas = <Gemensamma | Exchange | SharePoint | Skype>** – en kommaavgränsad lista med tjänstområden.</span><span class="sxs-lookup"><span data-stu-id="87e37-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="87e37-180">Giltiga objekt är _Gemensamma_, _Exchange_, _SharePoint_, _Skype_.</span><span class="sxs-lookup"><span data-stu-id="87e37-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="87e37-181">Eftersom _Gemensamma_ tjänstområdesobjekt är en förutsättning för alla andra tjänstområden inkluderar webbtjänsten alltid dem.</span><span class="sxs-lookup"><span data-stu-id="87e37-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="87e37-182">Om du inte tar med den här parametern returneras alla tjänstområden.</span><span class="sxs-lookup"><span data-stu-id="87e37-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="87e37-183">**Klientorganisationsnamn = <tenant_name>** – ditt Office 365-klientorganisationsnamn.</span><span class="sxs-lookup"><span data-stu-id="87e37-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="87e37-184">Webbtjänsten tar det angivna namnet och infogar det i delar av URL-adresser som innehåller klientnamnet.</span><span class="sxs-lookup"><span data-stu-id="87e37-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="87e37-185">Om du inte anger ett klientnamn har de delarna av URL-adresserna jokertecken (\*).</span><span class="sxs-lookup"><span data-stu-id="87e37-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="87e37-186">**NoIPv6=<true | false>** – Ange detta som _sant_ för att utelämna IPv6-adresser från resultatet om du inte använder IPv6 i nätverket.</span><span class="sxs-lookup"><span data-stu-id="87e37-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="87e37-187">**Instance = <Worldwide| China | Germany | USGovDoD | USGovGCCHigh>** – den nödvändiga parametern anger vilken instans som ska returnera slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="87e37-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="87e37-188">Giltiga instanser är: _Worldwide_, _China_, _Germany_, _USGovDoD_ och _USGovGCCHigh_.</span><span class="sxs-lookup"><span data-stu-id="87e37-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="87e37-189">Om du anropar webbmetoden för slutpunkter för många gånger från samma IP-adress för klient, kan det hända att du får HTTP-svarskod _429 (för många begäranden)_.</span><span class="sxs-lookup"><span data-stu-id="87e37-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="87e37-190">Om du får svarskoden väntar du i en timme innan du upprepar begäran eller genererar ett nytt GUID för begäran.</span><span class="sxs-lookup"><span data-stu-id="87e37-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="87e37-191">Som en allmän metod är att bara anropa webbmetoden för slutpunkter när versionswebbmetoden anger att en ny version är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="87e37-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="87e37-192">Resultatet från slutpunktswebbmetoden är en matris med poster där varje post representerar en specifik slutpunktsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="87e37-192">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set.</span></span> <span data-ttu-id="87e37-193">Elementen för varje post är:</span><span class="sxs-lookup"><span data-stu-id="87e37-193">The elements for each record are:</span></span>

- <span data-ttu-id="87e37-194">id – Det oföränderliga ID-numret för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="87e37-195">serviceArea – Tjänstområdet som detta är en del av: _Gemensamma_, _Exchange_, _SharePoint_ eller _Skype_.</span><span class="sxs-lookup"><span data-stu-id="87e37-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="87e37-196">URL:er – Webbadresser för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-196">urls — URLs for the endpoint set.</span></span> <span data-ttu-id="87e37-197">En JSON-matris med DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="87e37-197">A JSON array of DNS records.</span></span> <span data-ttu-id="87e37-198">Utelämnas om tomt.</span><span class="sxs-lookup"><span data-stu-id="87e37-198">Omitted if blank.</span></span>
- <span data-ttu-id="87e37-199">tcpPorts – TCP-portar för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-199">tcpPorts — TCP ports for the endpoint set.</span></span> <span data-ttu-id="87e37-200">Alla portelement är formaterade som en kommaavgränsad lista med portar eller portintervaller avgränsade med ett bindestreck (-).</span><span class="sxs-lookup"><span data-stu-id="87e37-200">All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-).</span></span> <span data-ttu-id="87e37-201">Portar gäller för alla IP-adresser och alla URL-adresser i slutpunktsuppsättningen för en specifik kategori.</span><span class="sxs-lookup"><span data-stu-id="87e37-201">Ports apply to all IP addresses and all URLs in the endpoint set for a given category.</span></span> <span data-ttu-id="87e37-202">Utelämnas om tomt.</span><span class="sxs-lookup"><span data-stu-id="87e37-202">Omitted if blank.</span></span>
- <span data-ttu-id="87e37-203">udpPorts – UDP-portar för IP-adressintervallerna i den här slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-203">udpPorts — UDP ports for the IP address ranges in this endpoint set.</span></span> <span data-ttu-id="87e37-204">Utelämnas om tomt.</span><span class="sxs-lookup"><span data-stu-id="87e37-204">Omitted if blank.</span></span>
- <span data-ttu-id="87e37-205">ips – IP-adressintervallen som är kopplade till den här slutpunktsuppsättningen som är kopplade till de angivna TCP- eller UDP-portarna.</span><span class="sxs-lookup"><span data-stu-id="87e37-205">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports.</span></span> <span data-ttu-id="87e37-206">En JSON-matris med IP-adressintervall.</span><span class="sxs-lookup"><span data-stu-id="87e37-206">A JSON array of IP address ranges.</span></span> <span data-ttu-id="87e37-207">Utelämnas om tomt.</span><span class="sxs-lookup"><span data-stu-id="87e37-207">Omitted if blank.</span></span>
- <span data-ttu-id="87e37-208">kategori – Anslutningskategorin för slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="87e37-209">Giltiga värden är _Optimera_, _Tillåta_ och _Standard_.</span><span class="sxs-lookup"><span data-stu-id="87e37-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="87e37-210">Om du söker i webbmetoden för slutpunkter för en viss IP-adress eller URL är det möjligt att frågan returnerar flera olika kategorier.</span><span class="sxs-lookup"><span data-stu-id="87e37-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="87e37-211">I så fall följer du rekommendationer för kategorin med högsta prioritet.</span><span class="sxs-lookup"><span data-stu-id="87e37-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="87e37-212">Om till exempel slutpunkten visas i båda _Optimera_ och _Tillåta_ ska du följa kraven för _Optimera_.</span><span class="sxs-lookup"><span data-stu-id="87e37-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="87e37-213">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="87e37-213">Required.</span></span>
- <span data-ttu-id="87e37-214">expressRoute – _Sant_ om den här slutpunktsuppsättningen dirigeras över Microsoft Azure ExpressRoute annars _Falskt_.</span><span class="sxs-lookup"><span data-stu-id="87e37-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="87e37-215">obligatoriskt – _Sant_ om den här slutpunktsuppsättningen kräver anslutningar om Office 365 ska stödjas.</span><span class="sxs-lookup"><span data-stu-id="87e37-215">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported.</span></span> <span data-ttu-id="87e37-216">_False_ om denna slutpunktsuppsättning är valfri.</span><span class="sxs-lookup"><span data-stu-id="87e37-216">_False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="87e37-217">anteckningar – För valfria slutpunktsuppsättningar beskriver den här texten Office 365-funktioner som inte skulle vara tillgänglig om IP-adresserna eller webbadresserna i den här slutpunktsuppsättningen inte kan nås i nätverket.</span><span class="sxs-lookup"><span data-stu-id="87e37-217">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer.</span></span> <span data-ttu-id="87e37-218">Utelämnas om tomt.</span><span class="sxs-lookup"><span data-stu-id="87e37-218">Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="87e37-219">Exempel:</span><span class="sxs-lookup"><span data-stu-id="87e37-219">Examples:</span></span>

<span data-ttu-id="87e37-220">Exempel 1 begär URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-221">Denna URI hämtar alla slutpunkter för den globala Office 365-instansen för alla arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="87e37-221">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads.</span></span> <span data-ttu-id="87e37-222">Exempelresultat som visar ett utdrag av utdata:</span><span class="sxs-lookup"><span data-stu-id="87e37-222">Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="87e37-223">Observera att den fullständiga utskriften av begäran i det här exemplet skulle innehålla andra slutpunktsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="87e37-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="87e37-224">Exempel 2 begär URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-225">Det här exemplet hämtar slutpunkter för den globala Office 365-instansen för endast Exchange Online och beroenden.</span><span class="sxs-lookup"><span data-stu-id="87e37-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="87e37-226">Utdata för exempel 2 liknar exempel 1, förutom att resultatet inte innehåller slutpunkter för SharePoint Online eller Skype för företag – Online.</span><span class="sxs-lookup"><span data-stu-id="87e37-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="87e37-227">Ändringswebbmetod</span><span class="sxs-lookup"><span data-stu-id="87e37-227">Changes web method</span></span>

<span data-ttu-id="87e37-228">Ändringswebbmetoden returnerar de senaste uppdateringarna som har publicerats är vanligtvis föregående månads ändringar av IP-adressintervall och URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="87e37-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="87e37-229">De mest kritiska ändringarna av slutpunkternas data är nya URL:er och IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="87e37-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="87e37-230">Om det inte går att lägga till en IP-adress i en kontrollista för en brandvägg eller en URL-adress till en förbikopplingslista för proxyserver kan orsaka driftavbrott för Office 365-användare bakom nätverksenheten.</span><span class="sxs-lookup"><span data-stu-id="87e37-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="87e37-231">Trots operativ krav publiceras nya slutpunkter till webbtjänsten 30 dagar före det datum då slutpunkterna allokeras för att ge dig tid att uppdatera listor för åtkomstkontroll och förbikopplingslistor för proxyserver.</span><span class="sxs-lookup"><span data-stu-id="87e37-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="87e37-232">Den obligatoriska parametern för ändringswebbmetoden är:</span><span class="sxs-lookup"><span data-stu-id="87e37-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="87e37-233">**Version-\<YYYYMMDDNN>** – Obligatorisk URL-dirigeringsparameter.</span><span class="sxs-lookup"><span data-stu-id="87e37-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="87e37-234">Det här värdet är versionen som du för närvarande har implementerat.</span><span class="sxs-lookup"><span data-stu-id="87e37-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="87e37-235">Webbtjänsten kommer att returnera ändringarna sedan den versionen.</span><span class="sxs-lookup"><span data-stu-id="87e37-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="87e37-236">Formatet är _YYYYMMDDNN_, där _NN_ är ett naturligt tal som ökas om det finns flera versioner som måste publiceras på en enda dag och _00_ som representerar den första uppdateringen för en viss dag.</span><span class="sxs-lookup"><span data-stu-id="87e37-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="87e37-237">Webbtjänsten kräver att _version_-parametern innehåller exakt 10 siffror.</span><span class="sxs-lookup"><span data-stu-id="87e37-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="87e37-238">Ändringswebbmetoden är begränsad på samma sätt som webbmetoden för slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="87e37-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="87e37-239">Om du får en 429 HTTP-svarskod väntar du i 1 timme innan du upprepar begäran eller genererar ett nytt GUID för begäran.</span><span class="sxs-lookup"><span data-stu-id="87e37-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="87e37-240">Resultatet från ändringswebbmetoden är en matris med poster där varje post representerar en ändring i en specifik version av slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="87e37-240">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints.</span></span> <span data-ttu-id="87e37-241">Elementen för varje post är:</span><span class="sxs-lookup"><span data-stu-id="87e37-241">The elements for each record are:</span></span>

- <span data-ttu-id="87e37-242">id – Oföränderligt ID för ändringsposten.</span><span class="sxs-lookup"><span data-stu-id="87e37-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="87e37-243">endpointSetId – ID för slutpunktsuppsättningsposten som har ändrats.</span><span class="sxs-lookup"><span data-stu-id="87e37-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="87e37-244">disposition – beskriver vad ändringen gjorde till i slutpunktsuppsättningens post.</span><span class="sxs-lookup"><span data-stu-id="87e37-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="87e37-245">Värdena är _ändra_, _lägga till_ eller _ta bort_.</span><span class="sxs-lookup"><span data-stu-id="87e37-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="87e37-246">impact – alla förändringar blir inte lika viktiga för alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="87e37-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="87e37-247">Det här elementet beskriver den förväntade effekten på en företagsnätverksgräns som ett resultat av ändringen.</span><span class="sxs-lookup"><span data-stu-id="87e37-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="87e37-248">Det här elementet inkluderas bara i ändringsposter av versionen **2018112800** och senare.</span><span class="sxs-lookup"><span data-stu-id="87e37-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="87e37-249">Alternativ som påverkar effekten är: – AddedIp – en IP-adress har lagts till i Office 365 och kommer snart att vara aktiv för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="87e37-250">Det här är en ändring som du måste utföra på en brandvägg eller annan nätverksgränsenhet för nivå 3.</span><span class="sxs-lookup"><span data-stu-id="87e37-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="87e37-251">Om du inte lägger till det innan vi börjar använda det kan du uppleva ett avbrott.</span><span class="sxs-lookup"><span data-stu-id="87e37-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="87e37-252">– AddedUrl – en URL-adress har lagts till i Office 365 och kommer snart att finnas kvar i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="87e37-253">Det här är en ändring som du måste utföra på en proxyserver eller URL-tolkande nätverksgränsenhet.</span><span class="sxs-lookup"><span data-stu-id="87e37-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="87e37-254">Om du inte lägger till den här URL:en innan vi börjar använda den, kan du uppleva ett avbrott.</span><span class="sxs-lookup"><span data-stu-id="87e37-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="87e37-255">– AddedIpAndUrl – både en IP-adress och en URL lades till.</span><span class="sxs-lookup"><span data-stu-id="87e37-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="87e37-256">Det här är en ändring som du måste utföra antingen på en brandväggsenhet på nivå 3 eller proxyserver eller URL-tolkande enhet.</span><span class="sxs-lookup"><span data-stu-id="87e37-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="87e37-257">Om du inte lägger till detta IP/URL-par innan vi börjar använda det kan du uppleva ett avbrott.</span><span class="sxs-lookup"><span data-stu-id="87e37-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="87e37-258">– RemovedIpOrUrl – minst en IP-adress eller URL har tagits bort från Office 365.</span><span class="sxs-lookup"><span data-stu-id="87e37-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="87e37-259">Ta bort nätverksslutpunkterna från dina gränsenheter, men det finns ingen deadline för dig att göra det.</span><span class="sxs-lookup"><span data-stu-id="87e37-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="87e37-260">– ChangedIsExpressRoute – Microsoft Azure ExpressRoutens supportattribut har ändrats.</span><span class="sxs-lookup"><span data-stu-id="87e37-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="87e37-261">Om du använder Microsoft Azure ExpressRoute kan du behöva vidta åtgärder beroende på din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="87e37-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="87e37-262">– MovedIpOrUrl – vi har flyttat en IP-adress eller URL mellan den här slutpunktsuppsättningen och en annan.</span><span class="sxs-lookup"><span data-stu-id="87e37-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="87e37-263">Generellt krävs ingen åtgärd.</span><span class="sxs-lookup"><span data-stu-id="87e37-263">Generally no action is required.</span></span>
  <span data-ttu-id="87e37-264">– RemovedDuplicateIpOrUrl – vi har tagit bort en dubblett av IP-adressen eller URL:en, men den är fortfarande publicerad för Office 365.</span><span class="sxs-lookup"><span data-stu-id="87e37-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="87e37-265">Generellt krävs ingen åtgärd.</span><span class="sxs-lookup"><span data-stu-id="87e37-265">Generally no action is required.</span></span>
  <span data-ttu-id="87e37-266">– OtherNonPriorityChanges – vi har ändrat något som är mindre kritiskt än alla andra alternativ, t. ex. innehållet i ett anteckningsfält.</span><span class="sxs-lookup"><span data-stu-id="87e37-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="87e37-267">version – Version av den publicerade slutpunktsuppsättningen i vilken ändringen infördes.</span><span class="sxs-lookup"><span data-stu-id="87e37-267">version — The version of the published endpoint set in which the change was introduced.</span></span> <span data-ttu-id="87e37-268">Versionsnummer är i formatet _ÅÅÅÅMMDDNN_, där _NN_ är ett naturligt tal som ökas automatiskt om det finns flera obligatoriska versioner som ska publiceras på samma dag.</span><span class="sxs-lookup"><span data-stu-id="87e37-268">Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="87e37-269">previous – En underordnad struktur med information om tidigare värden för ändrade element i slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="87e37-270">Det här inkluderas inte för nyligen tillagda slutpunktsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="87e37-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="87e37-271">Innehåller  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ och _notes_.</span><span class="sxs-lookup"><span data-stu-id="87e37-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="87e37-272">aktuella – En underordnad struktur med information om uppdaterade värden för ändrade element i slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="87e37-273">Innehåller _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ och _notes_.</span><span class="sxs-lookup"><span data-stu-id="87e37-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="87e37-274">add – En underordnad struktur med information om objekt som ska läggas till i slutpunktsuppsättningssamlingar.</span><span class="sxs-lookup"><span data-stu-id="87e37-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="87e37-275">Utelämnas om det inte finns några tillägg.</span><span class="sxs-lookup"><span data-stu-id="87e37-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="87e37-276">– effectiveDate – Definierar data när tilläggen börjar gälla i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="87e37-277">– ips – Objekt som ska läggas till i _ips_-matrisen.</span><span class="sxs-lookup"><span data-stu-id="87e37-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="87e37-278">– urls – Objekt som ska läggas till i _url_-matrisen.</span><span class="sxs-lookup"><span data-stu-id="87e37-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="87e37-279">remove – En underordnad struktur med information om objekt som ska tas bort från slutpunktsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="87e37-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="87e37-280">Utelämnas om det inte finns några borttagningar.</span><span class="sxs-lookup"><span data-stu-id="87e37-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="87e37-281">ips – Objekt som ska tas bort från _ips_-matrisen.</span><span class="sxs-lookup"><span data-stu-id="87e37-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="87e37-282">urls – Objekt som ska tas bort från _urls_-matrisen.</span><span class="sxs-lookup"><span data-stu-id="87e37-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="87e37-283">Exempel:</span><span class="sxs-lookup"><span data-stu-id="87e37-283">Examples:</span></span>

<span data-ttu-id="87e37-284">Exempel 1 begär URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-285">Detta begär alla tidigare ändringar i den globala Office 365-tjänstinstansen.</span><span class="sxs-lookup"><span data-stu-id="87e37-285">This requests all previous changes to the Office 365 worldwide service instance.</span></span> <span data-ttu-id="87e37-286">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-286">Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="87e37-287">Exempel 2 begär URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87e37-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="87e37-288">Detta begär ändringar sedan den angivna versionen för den globala Office 365-instansen.</span><span class="sxs-lookup"><span data-stu-id="87e37-288">This requests changes since the specified version to the Office 365 Worldwide instance.</span></span> <span data-ttu-id="87e37-289">I det här fallet är den senaste versionen den som anges.</span><span class="sxs-lookup"><span data-stu-id="87e37-289">In this case, the version specified is the latest.</span></span> <span data-ttu-id="87e37-290">Exempelresultat:</span><span class="sxs-lookup"><span data-stu-id="87e37-290">Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="87e37-291">Exempel på Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="87e37-291">Example PowerShell Script</span></span>

<span data-ttu-id="87e37-292">Du kan köra detta Windows PowerShell-skript för att se om det finns åtgärder du ska vidta för uppdaterade data.</span><span class="sxs-lookup"><span data-stu-id="87e37-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="87e37-293">Du kan köra det här skriptet som en schemalagd aktivitet för att söka efter en versionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="87e37-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="87e37-294">Om du vill undvika överdriven belastning på webbtjänsten försöker du inte köra skriptet mer än en gång i timmen.</span><span class="sxs-lookup"><span data-stu-id="87e37-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="87e37-295">Skriptet gör följande:</span><span class="sxs-lookup"><span data-stu-id="87e37-295">The script does the following:</span></span>

- <span data-ttu-id="87e37-296">Kontrollera versionsnumret för aktuella Office 365-slutpunkter för hela instansen genom att anropa webbtjänstens REST API.</span><span class="sxs-lookup"><span data-stu-id="87e37-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="87e37-297">Söker efter en aktuell versionsfil på _$Env:TEMP\O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="87e37-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="87e37-298">Sökvägen till den globala variabeln **$Env:TEMP** är vanligtvis _C:\Users\\<username\>\AppData\Local\Temp_.</span><span class="sxs-lookup"><span data-stu-id="87e37-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="87e37-299">Om det här är första gången skriptet körs returnerar skriptet den aktuella versionen och alla aktuella IP-adresser och URL-adresser och skriver slutpunktsversionen till fil _$Env:TEMP\O365_endpoints_latestversion.txt_ och slutpunktsdata kommer att skrivas till filen _$Env:TEMP\O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="87e37-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="87e37-300">Du kan ändra sökvägen och/eller namnet på utdatafilen genom att redigera dessa rader:</span><span class="sxs-lookup"><span data-stu-id="87e37-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="87e37-301">För varje efterföljande körning av skriptet, om den senaste webbtjänstversionen är identisk med versionen i filen _O365_endpoints_latestversion.txt_ avslutas skriptet utan att några ändringar görs.</span><span class="sxs-lookup"><span data-stu-id="87e37-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="87e37-302">När den senaste webbtjänstversionen är nyare än den version som finns i filen _O365_endpoints_latestversion.txt_ returnerar skriptet slutpunkterna och filter för kategorislutpunkterna **Tillåta** och **Optimera**, uppdaterar versionen i filen _O365_endpoints_latestversion.txt_ och skriver uppdaterad data till _O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="87e37-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="87e37-303">Skriptet genererar ett unikt _ClientRequestId_ för den dator som körs och återanvänder detta ID för flera samtal.</span><span class="sxs-lookup"><span data-stu-id="87e37-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="87e37-304">Detta ID finns i filen _O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="87e37-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="87e37-305">Om du vill köra Windows PowerShell-skriptet</span><span class="sxs-lookup"><span data-stu-id="87e37-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="87e37-306">Kopiera skriptet och spara det till den lokala hårddisken eller till en skriptplats som _Get-O365WebServiceUpdates.ps1_.</span><span class="sxs-lookup"><span data-stu-id="87e37-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="87e37-307">Kör skriptet i önskad skriptredigerare, t. ex. Windows PowerShell ISE eller VS-koden eller från en Windows PowerShell-konsol med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="87e37-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="87e37-308">Det finns inga parametrar att skicka till skriptet.</span><span class="sxs-lookup"><span data-stu-id="87e37-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="87e37-309">Exempel på Python-skript</span><span class="sxs-lookup"><span data-stu-id="87e37-309">Example Python Script</span></span>

<span data-ttu-id="87e37-310">Här är ett Python-skript, testat med Python 3.6.3 på Windows 10, som du kan köra för att se om det finns åtgärder du ska vidta för de uppdaterade data.</span><span class="sxs-lookup"><span data-stu-id="87e37-310">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="87e37-311">Det här skriptet kontrollerar versionsnumret för den globala Office 365-instansens slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="87e37-311">This script checks the version number for the Office 365 Worldwide instance endpoints.</span></span> <span data-ttu-id="87e37-312">När det finns en ändring laddar det ned slutpunkterna och filtrerar för slutpunkterna i kategorin _Tillåt_ och _Optimera_.</span><span class="sxs-lookup"><span data-stu-id="87e37-312">When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints.</span></span> <span data-ttu-id="87e37-313">Det använder även en unik ClientRequestId på flera anrop och sparar den senaste versionen som finns i en tillfällig fil.</span><span class="sxs-lookup"><span data-stu-id="87e37-313">It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file.</span></span> <span data-ttu-id="87e37-314">Du ska anropa skriptet en gång i timmen för att söka efter en versionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="87e37-314">You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="87e37-315">Versionshantering av webbtjänstgränssnitt</span><span class="sxs-lookup"><span data-stu-id="87e37-315">Web Service interface versioning</span></span>

<span data-ttu-id="87e37-316">Uppdateringar av parametrar eller resultat för de här webbtjänstmetoderna kan bli obligatoriska i framtiden.</span><span class="sxs-lookup"><span data-stu-id="87e37-316">Updates to the parameters or results for these web service methods may be required in the future.</span></span> <span data-ttu-id="87e37-317">När den allmänt tillgängliga versionen av dessa webbtjänster har publicerats utför Microsoft rimliga åtgärder för att tillhandahålla förhandsinformation om viktiga uppdateringar av webbtjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-317">After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service.</span></span> <span data-ttu-id="87e37-318">När Microsoft anser att en uppdatering kräver ändringar av de klienter som använder webbtjänsten, behåller Microsoft den tidigare versionen (en version bakåt) av webbtjänsten tillgänglig under minst 12 månader efter lanseringen av den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="87e37-318">When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version.</span></span> <span data-ttu-id="87e37-319">Kunder som inte uppgraderar under tiden kommer kanske inte att kunna komma åt webbtjänsten och dess metoder.</span><span class="sxs-lookup"><span data-stu-id="87e37-319">Customers who do not upgrade during that time may be unable to access the web service and its methods.</span></span> <span data-ttu-id="87e37-320">Kunderna måste säkerställa att klienter i webbtjänsten fortsätter att fungera utan fel om följande ändringar görs i webbtjänstens gränssnittssignatur:</span><span class="sxs-lookup"><span data-stu-id="87e37-320">Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="87e37-321">Tillägg av en ny valfri parameter i en befintlig webbmetod som inte behöver tillhandahållas av äldre klienter och inte påverkar det resultat en äldre klient får.</span><span class="sxs-lookup"><span data-stu-id="87e37-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="87e37-322">Tillägg av ett nytt namngivet attribut i något av REST-svarsobjekten eller fler kolumner i CSV-svarsfilen.</span><span class="sxs-lookup"><span data-stu-id="87e37-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="87e37-323">Tillägg av en ny webbmetod med ett nytt namn som inte anropas av äldre klienter.</span><span class="sxs-lookup"><span data-stu-id="87e37-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="87e37-324">Uppdateringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="87e37-324">Update notifications</span></span>

<span data-ttu-id="87e37-325">Du kan använda några olika metoder för att få e-postmeddelanden när ändringar av IP-adresser och URL-adresser publiceras i webbtjänsten.</span><span class="sxs-lookup"><span data-stu-id="87e37-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="87e37-326">Information om hur du använder en Microsoft Flow-lösning finns i [Använda Microsoft Flow för att få ett e-postmeddelande om ändringar i Office 365 IP-adresser och URL:er](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span><span class="sxs-lookup"><span data-stu-id="87e37-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="87e37-327">För att distribuera en Azure Logic-app med en ARM-mall finns i [Office 365 uppdateringsmeddelande (v 1.1)](https://aka.ms/ipurlws-updates-template).</span><span class="sxs-lookup"><span data-stu-id="87e37-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="87e37-328">Om du vill skriva ett eget meddelandeskript med Windows PowerShell kan du läsa [Skicka med e-postmeddelande](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span><span class="sxs-lookup"><span data-stu-id="87e37-328">To write your own notification script using PowerShell, see [Send-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="87e37-329">Exportera en proxy-PAC-fil</span><span class="sxs-lookup"><span data-stu-id="87e37-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="87e37-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) är ett Windows PowerShell-skript som läser de senaste nätverksslutpunkterna från webbtjänsten 365 Office IP-adress och URL och skapar ett exempel på en PAC-fil.</span><span class="sxs-lookup"><span data-stu-id="87e37-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="87e37-331">Information om hur du använder Get-PacFile finns i [Använda en PAC-fil för direkt routning av vitala Office 365-trafik](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="87e37-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="87e37-332">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="87e37-332">Related Topics</span></span>
  
[<span data-ttu-id="87e37-333">URL-adresser och IP-adressintervall för Office 365</span><span class="sxs-lookup"><span data-stu-id="87e37-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="87e37-334">Hantera Office 365-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="87e37-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="87e37-335">Office 365-slutpunkter – vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="87e37-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="87e37-336">Office 365 principer för nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="87e37-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="87e37-337">Office 365 nätverks- och prestandajustering</span><span class="sxs-lookup"><span data-stu-id="87e37-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="87e37-338">Utvärdera Nätverksanslutningar för Office 365</span><span class="sxs-lookup"><span data-stu-id="87e37-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="87e37-339">Prestanda för mediekvalitet och nätverksanslutning i Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="87e37-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="87e37-340">Optimera ditt nätverk för Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="87e37-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="87e37-341">Prestandajustering för Office 365 med baslinjer och prestandahistorik</span><span class="sxs-lookup"><span data-stu-id="87e37-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
<span data-ttu-id="87e37-342">[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).</span><span class="sxs-lookup"><span data-stu-id="87e37-342">[Performance troubleshooting plan for Office 365](performance-troubleshooting-plan.md)</span></span>
