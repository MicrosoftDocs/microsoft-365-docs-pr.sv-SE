---
title: Exportera bedömningar av säkerhetsproblem för programvara per enhet
description: API-svaret är per enhet och innehåller sårbar programvara som installeras på dina exponerade enheter samt alla kända säkerhetsproblem i dessa programvaruprodukter. Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.
keywords: api, apis, exportutvärdering, per enhetsutvärdering, sårbarhetsutvärderingsrapport, enhetsbristbedömning, enhetsproblemrapport, säker konfigurationsutvärdering, säker konfigurationsrapport, utvärdering av programvarubrister, programsäkerhetsproblemsrapport, sårbarhetsrapport efter maskin,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022876"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="0703e-105">Exportera bedömningar av säkerhetsproblem för programvara per enhet</span><span class="sxs-lookup"><span data-stu-id="0703e-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0703e-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0703e-106">**Applies to:**</span></span>

- [<span data-ttu-id="0703e-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0703e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0703e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0703e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0703e-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0703e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0703e-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0703e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="0703e-111">Returnerar alla kända säkerhetsproblem i programvaran och deras information för alla enheter, per enhet.</span><span class="sxs-lookup"><span data-stu-id="0703e-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="0703e-112">Det finns olika API-anrop för att få olika typer av data.</span><span class="sxs-lookup"><span data-stu-id="0703e-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="0703e-113">Eftersom mängden data kan vara mycket stor kan den hämtas på två sätt:</span><span class="sxs-lookup"><span data-stu-id="0703e-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="0703e-114">[Exportera säkerhetsproblem för programvara, **bedömning JSON-svar**](#1-export-software-vulnerabilities-assessment-json-response)  API:t hämtar alla data i organisationen som Json-svar.</span><span class="sxs-lookup"><span data-stu-id="0703e-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="0703e-115">Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._</span><span class="sxs-lookup"><span data-stu-id="0703e-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="0703e-116">Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="0703e-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="0703e-117">[Exportera utvärdering av säkerhetsproblem för programvara **via filer**](#2-export-software-vulnerabilities-assessment-via-files) Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt.</span><span class="sxs-lookup"><span data-stu-id="0703e-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="0703e-118">Via-filer rekommenderas för stora organisationer med fler än 100 K-enheter.</span><span class="sxs-lookup"><span data-stu-id="0703e-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="0703e-119">Detta API hämtar alla data i organisationen som nedladdningsfiler.</span><span class="sxs-lookup"><span data-stu-id="0703e-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="0703e-120">Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring.</span><span class="sxs-lookup"><span data-stu-id="0703e-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="0703e-121">Med det här API:t kan du ladda ned alla dina data Azure-lagring enligt följande:</span><span class="sxs-lookup"><span data-stu-id="0703e-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="0703e-122">Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="0703e-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="0703e-123">Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.</span><span class="sxs-lookup"><span data-stu-id="0703e-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="0703e-124">[Delta i export av säkerhetsproblem vid **bedömning av JSON-svar**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returnerar en tabell med en post för varje unik kombination av: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId och EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="0703e-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="0703e-125">API:t hämtar data i organisationen som Json-svar.</span><span class="sxs-lookup"><span data-stu-id="0703e-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="0703e-126">Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="0703e-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="0703e-127">Till skillnad från den fullständiga utvärderingen av säkerhetsproblem för programvara (JSON-svar) – som används för att erhålla en hel ögonblicksbild av svagheter i programvarans bedömning av organisationen efter enhet – används deltaexport-OData API-anropet för att bara hämta de ändringar som har inträffat mellan ett valt datum och dagens datum (delta-API-anropet).</span><span class="sxs-lookup"><span data-stu-id="0703e-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="0703e-128">I stället för att få en fullständig export med en stor mängd data varje gång får du bara specifik information om nya, korrigerade och uppdaterade svagheter.</span><span class="sxs-lookup"><span data-stu-id="0703e-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="0703e-129">Deltaexportera JSON-svars-API-anrop kan också användas för att beräkna olika KPI:er, till exempel "hur många säkerhetsproblem har åtgärdats?"</span><span class="sxs-lookup"><span data-stu-id="0703e-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="0703e-130">eller "hur många nya säkerhetsproblem lades till i organisationen?"</span><span class="sxs-lookup"><span data-stu-id="0703e-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="0703e-131">Eftersom deltaexporten av JSON-svars-API:t för svagheter i programvaran returnerar data endast för ett måldatumintervall anses det inte vara _en fullständig export._</span><span class="sxs-lookup"><span data-stu-id="0703e-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="0703e-132">Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data.</span><span class="sxs-lookup"><span data-stu-id="0703e-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="0703e-133">För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.</span><span class="sxs-lookup"><span data-stu-id="0703e-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="0703e-134">Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**</span><span class="sxs-lookup"><span data-stu-id="0703e-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="0703e-135">1. Exportera utvärdering av säkerhetsproblem för programvara (JSON-svar)</span><span class="sxs-lookup"><span data-stu-id="0703e-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="0703e-136">1.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-136">1.1 API method description</span></span>

<span data-ttu-id="0703e-137">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="0703e-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="0703e-138">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="0703e-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="0703e-139">1.1.1 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="0703e-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="0703e-140">Maximal sidstorlek är 200 000.</span><span class="sxs-lookup"><span data-stu-id="0703e-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="0703e-141">Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="0703e-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="0703e-142">1.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="0703e-142">1.2 Permissions</span></span>

<span data-ttu-id="0703e-143">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="0703e-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0703e-144">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0703e-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="0703e-145">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="0703e-145">Permission type</span></span> | <span data-ttu-id="0703e-146">Behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-146">Permission</span></span> | <span data-ttu-id="0703e-147">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="0703e-148">Program</span><span class="sxs-lookup"><span data-stu-id="0703e-148">Application</span></span> | <span data-ttu-id="0703e-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="0703e-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="0703e-150">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="0703e-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="0703e-151">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="0703e-151">Delegated (work or school account)</span></span> | <span data-ttu-id="0703e-152">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="0703e-152">Vulnerability.Read</span></span> | <span data-ttu-id="0703e-153">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="0703e-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="0703e-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="0703e-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="0703e-155">1.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="0703e-155">1.4 Parameters</span></span>

- <span data-ttu-id="0703e-156">pageSize (standard = 50 000) – antal resultat som svar</span><span class="sxs-lookup"><span data-stu-id="0703e-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="0703e-157">$top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)</span><span class="sxs-lookup"><span data-stu-id="0703e-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="0703e-158">1.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="0703e-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="0703e-159">Varje post är cirka 1 kB data.</span><span class="sxs-lookup"><span data-stu-id="0703e-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="0703e-160">Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.</span><span class="sxs-lookup"><span data-stu-id="0703e-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="0703e-161">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="0703e-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="0703e-162">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="0703e-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="0703e-163">Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.</span><span class="sxs-lookup"><span data-stu-id="0703e-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="0703e-164">När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0703e-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="0703e-165">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="0703e-165">Property (ID)</span></span> | <span data-ttu-id="0703e-166">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0703e-166">Data type</span></span> | <span data-ttu-id="0703e-167">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-167">Description</span></span> | <span data-ttu-id="0703e-168">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="0703e-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0703e-169">CveId</span><span class="sxs-lookup"><span data-stu-id="0703e-169">CveId</span></span> | <span data-ttu-id="0703e-170">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-170">string</span></span> | <span data-ttu-id="0703e-171">Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE).</span><span class="sxs-lookup"><span data-stu-id="0703e-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="0703e-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="0703e-172">CVE-2020-15992</span></span>
<span data-ttu-id="0703e-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="0703e-173">CvssScore</span></span> | <span data-ttu-id="0703e-174">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-174">string</span></span> | <span data-ttu-id="0703e-175">CVSS-poäng för CVE.</span><span class="sxs-lookup"><span data-stu-id="0703e-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="0703e-176">6.2</span><span class="sxs-lookup"><span data-stu-id="0703e-176">6.2</span></span>
<span data-ttu-id="0703e-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0703e-177">DeviceId</span></span> | <span data-ttu-id="0703e-178">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-178">string</span></span> | <span data-ttu-id="0703e-179">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0703e-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="0703e-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="0703e-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="0703e-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="0703e-181">DeviceName</span></span> | <span data-ttu-id="0703e-182">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-182">string</span></span> | <span data-ttu-id="0703e-183">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="0703e-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0703e-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="0703e-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="0703e-185">DiskPaths</span></span>  | <span data-ttu-id="0703e-186">\[Matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="0703e-186">Array\[string\]</span></span> | <span data-ttu-id="0703e-187">Disk bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="0703e-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="0703e-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="0703e-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="0703e-189">ExploitabilityLevel</span></span> | <span data-ttu-id="0703e-190">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-190">string</span></span> | <span data-ttu-id="0703e-191">Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="0703e-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="0703e-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="0703e-192">ExploitIsInKit</span></span>
<span data-ttu-id="0703e-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="0703e-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="0703e-194">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-194">string</span></span> | <span data-ttu-id="0703e-195">Första gången CVE för den här produkten sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="0703e-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="0703e-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="0703e-197">ID</span><span class="sxs-lookup"><span data-stu-id="0703e-197">Id</span></span> | <span data-ttu-id="0703e-198">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-198">string</span></span> | <span data-ttu-id="0703e-199">Unikt ID för posten.</span><span class="sxs-lookup"><span data-stu-id="0703e-199">Unique identifier for the record.</span></span> | <span data-ttu-id="0703e-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="0703e-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="0703e-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="0703e-201">LastSeenTimestamp</span></span> | <span data-ttu-id="0703e-202">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-202">string</span></span> | <span data-ttu-id="0703e-203">Senaste gången CVE sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="0703e-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="0703e-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="0703e-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="0703e-205">OSPlatform</span></span> | <span data-ttu-id="0703e-206">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-206">string</span></span> | <span data-ttu-id="0703e-207">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0703e-208">Den här egenskapen anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0703e-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="0703e-209">Mer information finns i Operativsystem och plattformar som stöds av TVM.</span><span class="sxs-lookup"><span data-stu-id="0703e-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="0703e-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="0703e-210">Windows10</span></span>
<span data-ttu-id="0703e-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="0703e-211">RbacGroupName</span></span>  | <span data-ttu-id="0703e-212">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-212">string</span></span> | <span data-ttu-id="0703e-213">Den rollbaserade åtkomstkontrollgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0703e-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="0703e-214">Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat".</span><span class="sxs-lookup"><span data-stu-id="0703e-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="0703e-215">Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".</span><span class="sxs-lookup"><span data-stu-id="0703e-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="0703e-216">Servrar</span><span class="sxs-lookup"><span data-stu-id="0703e-216">Servers</span></span>
<span data-ttu-id="0703e-217">RekommendationReference</span><span class="sxs-lookup"><span data-stu-id="0703e-217">RecommendationReference</span></span> | <span data-ttu-id="0703e-218">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-218">string</span></span> | <span data-ttu-id="0703e-219">En referens till det rekommendations-ID som hör till den här programvaran.</span><span class="sxs-lookup"><span data-stu-id="0703e-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="0703e-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="0703e-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="0703e-221">RecommendedSecurityUpdate (valfritt)</span><span class="sxs-lookup"><span data-stu-id="0703e-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="0703e-222">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-222">string</span></span> | <span data-ttu-id="0703e-223">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet.</span><span class="sxs-lookup"><span data-stu-id="0703e-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="0703e-224">Säkerhetsuppdateringar för april 2020</span><span class="sxs-lookup"><span data-stu-id="0703e-224">April 2020 Security Updates</span></span>
<span data-ttu-id="0703e-225">RecommendedSecurityUpdateId (valfritt)</span><span class="sxs-lookup"><span data-stu-id="0703e-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="0703e-226">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-226">string</span></span> | <span data-ttu-id="0703e-227">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="0703e-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="0703e-228">4550961</span><span class="sxs-lookup"><span data-stu-id="0703e-228">4550961</span></span>
<span data-ttu-id="0703e-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="0703e-229">RegistryPaths</span></span>  | <span data-ttu-id="0703e-230">\[Matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="0703e-230">Array\[string\]</span></span> | <span data-ttu-id="0703e-231">Register bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="0703e-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="0703e-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="0703e-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="0703e-233">SoftwareName</span></span> | <span data-ttu-id="0703e-234">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-234">string</span></span> | <span data-ttu-id="0703e-235">Namnet på programvaruprodukten.</span><span class="sxs-lookup"><span data-stu-id="0703e-235">Name of the software product.</span></span> | <span data-ttu-id="0703e-236">chrome</span><span class="sxs-lookup"><span data-stu-id="0703e-236">chrome</span></span>
<span data-ttu-id="0703e-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="0703e-237">SoftwareVendor</span></span> | <span data-ttu-id="0703e-238">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-238">string</span></span> | <span data-ttu-id="0703e-239">Namnet på programvaruleverantören.</span><span class="sxs-lookup"><span data-stu-id="0703e-239">Name of the software vendor.</span></span> | <span data-ttu-id="0703e-240">google</span><span class="sxs-lookup"><span data-stu-id="0703e-240">google</span></span>
<span data-ttu-id="0703e-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="0703e-241">SoftwareVersion</span></span> | <span data-ttu-id="0703e-242">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-242">string</span></span> | <span data-ttu-id="0703e-243">Versionsnummer för programvaran.</span><span class="sxs-lookup"><span data-stu-id="0703e-243">Version number of the software product.</span></span> | <span data-ttu-id="0703e-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="0703e-244">81.0.4044.138</span></span>
<span data-ttu-id="0703e-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="0703e-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="0703e-246">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-246">string</span></span> | <span data-ttu-id="0703e-247">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden.</span><span class="sxs-lookup"><span data-stu-id="0703e-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="0703e-248">Medel</span><span class="sxs-lookup"><span data-stu-id="0703e-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="0703e-249">1.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="0703e-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="0703e-250">1.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="0703e-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="0703e-251">1.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="0703e-251">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="0703e-252">2. Exportera utvärdering av säkerhetsproblem för programvara (via filer)</span><span class="sxs-lookup"><span data-stu-id="0703e-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="0703e-253">2.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-253">2.1 API method description</span></span>

<span data-ttu-id="0703e-254">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="0703e-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="0703e-255">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="0703e-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="0703e-256">2.1.2 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="0703e-256">2.1.2 Limitations</span></span>

<span data-ttu-id="0703e-257">Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="0703e-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="0703e-258">2.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="0703e-258">2.2 Permissions</span></span>

<span data-ttu-id="0703e-259">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="0703e-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0703e-260">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0703e-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="0703e-261">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="0703e-261">Permission type</span></span> | <span data-ttu-id="0703e-262">Behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-262">Permission</span></span> | <span data-ttu-id="0703e-263">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="0703e-264">Program</span><span class="sxs-lookup"><span data-stu-id="0703e-264">Application</span></span> | <span data-ttu-id="0703e-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="0703e-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="0703e-266">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="0703e-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="0703e-267">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="0703e-267">Delegated (work or school account)</span></span> | <span data-ttu-id="0703e-268">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="0703e-268">Vulnerability.Read</span></span> | <span data-ttu-id="0703e-269">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="0703e-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="0703e-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="0703e-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="0703e-271">2.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="0703e-271">2.4 Parameters</span></span>

- <span data-ttu-id="0703e-272">sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar)</span><span class="sxs-lookup"><span data-stu-id="0703e-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="0703e-273">2.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="0703e-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="0703e-274">Filerna är gzip komprimerade & I multiline Json-format.</span><span class="sxs-lookup"><span data-stu-id="0703e-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="0703e-275">URL-adresser för nedladdning är endast giltiga i 3 timmar. annars kan du använda parametern.</span><span class="sxs-lookup"><span data-stu-id="0703e-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="0703e-276">För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.</span><span class="sxs-lookup"><span data-stu-id="0703e-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="0703e-277">Varje post motsvarar ungefär 1 kB data.</span><span class="sxs-lookup"><span data-stu-id="0703e-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="0703e-278">Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.</span><span class="sxs-lookup"><span data-stu-id="0703e-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="0703e-279">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="0703e-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="0703e-280">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="0703e-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="0703e-281">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="0703e-281">Property (ID)</span></span> | <span data-ttu-id="0703e-282">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0703e-282">Data type</span></span> | <span data-ttu-id="0703e-283">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-283">Description</span></span> | <span data-ttu-id="0703e-284">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="0703e-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0703e-285">Exportera filer</span><span class="sxs-lookup"><span data-stu-id="0703e-285">Export files</span></span> | <span data-ttu-id="0703e-286">\[matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="0703e-286">array\[string\]</span></span>  | <span data-ttu-id="0703e-287">En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen.</span><span class="sxs-lookup"><span data-stu-id="0703e-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="0703e-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="0703e-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="0703e-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="0703e-289">GeneratedTime</span></span> | <span data-ttu-id="0703e-290">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-290">string</span></span> | <span data-ttu-id="0703e-291">Tidpunkten då exporten skapades.</span><span class="sxs-lookup"><span data-stu-id="0703e-291">The time that the export was generated.</span></span> | <span data-ttu-id="0703e-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="0703e-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="0703e-293">2.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="0703e-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="0703e-294">2.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="0703e-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="0703e-295">2.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="0703e-295">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="0703e-296">3. Sårbarhetsbedömning av deltaexportprogramvara (JSON-svar)</span><span class="sxs-lookup"><span data-stu-id="0703e-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="0703e-297">3.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-297">3.1 API method description</span></span>

<span data-ttu-id="0703e-298">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="0703e-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="0703e-299">API:t hämtar data i organisationen som Json-svar.</span><span class="sxs-lookup"><span data-stu-id="0703e-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="0703e-300">Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="0703e-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="0703e-301">Till skillnad från den fullständiga utvärderingen av säkerhetsproblem för programvara (JSON-svar), som används för att erhålla en hel ögonblicksbild av säkerhetsproblem i programvarans bedömning av organisationen efter enhet, används deltaexports-JSON-svars-API-anropet för att bara hämta ändringar som har skett mellan ett valt datum och dagens datum (delta-API-anropet).</span><span class="sxs-lookup"><span data-stu-id="0703e-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="0703e-302">I stället för att få en fullständig export med en stor mängd data varje gång får du bara specifik information om nya, korrigerade och uppdaterade svagheter.</span><span class="sxs-lookup"><span data-stu-id="0703e-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="0703e-303">Deltaexportera JSON-svars-API-anrop kan också användas för att beräkna olika KPI:er, till exempel "hur många säkerhetsproblem har åtgärdats?"</span><span class="sxs-lookup"><span data-stu-id="0703e-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="0703e-304">eller "hur många nya säkerhetsproblem lades till i organisationen?"</span><span class="sxs-lookup"><span data-stu-id="0703e-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="0703e-305">Vi rekommenderar starkt att du använder säkerhetsproblemen vid export av programvara genom enhets-API-anrop minst en gång i veckan, och detta ytterligare säkerhetsproblem vid export av programvara ändras efter enhet (delta) API-anrop alla övriga dagar i veckan.</span><span class="sxs-lookup"><span data-stu-id="0703e-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="0703e-306">Till skillnad från andra JSON-svars-API:er för utvärderingar är "deltaexporten" inte en fullständig export.</span><span class="sxs-lookup"><span data-stu-id="0703e-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="0703e-307">Deltaexporten innehåller bara de ändringar som har skett mellan ett valt datum och dagens datum (API-anropet "delta").</span><span class="sxs-lookup"><span data-stu-id="0703e-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="0703e-308">3.1.1 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="0703e-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="0703e-309">Maximal sidstorlek är 200 000.</span><span class="sxs-lookup"><span data-stu-id="0703e-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="0703e-310">Parametern sinceTime har högst 14 dagar.</span><span class="sxs-lookup"><span data-stu-id="0703e-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="0703e-311">Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="0703e-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="0703e-312">3.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="0703e-312">3.2 Permissions</span></span>

<span data-ttu-id="0703e-313">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="0703e-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0703e-314">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0703e-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="0703e-315">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="0703e-315">Permission type</span></span> | <span data-ttu-id="0703e-316">Behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-316">Permission</span></span> | <span data-ttu-id="0703e-317">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="0703e-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="0703e-318">Program</span><span class="sxs-lookup"><span data-stu-id="0703e-318">Application</span></span> | <span data-ttu-id="0703e-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="0703e-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="0703e-320">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="0703e-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="0703e-321">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="0703e-321">Delegated (work or school account)</span></span> | <span data-ttu-id="0703e-322">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="0703e-322">Vulnerability.Read</span></span> | <span data-ttu-id="0703e-323">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="0703e-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="0703e-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="0703e-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="0703e-325">3.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="0703e-325">3.4 Parameters</span></span>

- <span data-ttu-id="0703e-326">sinceTime (obligatoriskt) – Data mellan en vald tid och idag.</span><span class="sxs-lookup"><span data-stu-id="0703e-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="0703e-327">pageSize (standard = 50 000) – antal resultat som svar</span><span class="sxs-lookup"><span data-stu-id="0703e-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="0703e-328">$top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)</span><span class="sxs-lookup"><span data-stu-id="0703e-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="0703e-329">3.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="0703e-329">3.5 Properties</span></span>

<span data-ttu-id="0703e-330">Varje returnerad post innehåller alla data från säkerhetsproblem i exportprogramvaran som bedöms av enhets-OData API plus ytterligare två fält:  _**EventTimestamp**_ och _**Status**_.</span><span class="sxs-lookup"><span data-stu-id="0703e-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="0703e-331">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="0703e-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="0703e-332">Kolumnerna är tillfälliga och kan komma att tas bort, så använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="0703e-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="0703e-333">Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.</span><span class="sxs-lookup"><span data-stu-id="0703e-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="0703e-334">När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0703e-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="0703e-335">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="0703e-335">Property (ID)</span></span> | <span data-ttu-id="0703e-336">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0703e-336">Data type</span></span> | <span data-ttu-id="0703e-337">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0703e-337">Description</span></span> | <span data-ttu-id="0703e-338">Exempel på returnerat värde</span><span class="sxs-lookup"><span data-stu-id="0703e-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0703e-339">CveId</span><span class="sxs-lookup"><span data-stu-id="0703e-339">CveId</span></span> | <span data-ttu-id="0703e-340">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-340">string</span></span> | <span data-ttu-id="0703e-341">Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE).</span><span class="sxs-lookup"><span data-stu-id="0703e-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="0703e-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="0703e-342">CVE-2020-15992</span></span>  
<span data-ttu-id="0703e-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="0703e-343">CvssScore</span></span> | <span data-ttu-id="0703e-344">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-344">string</span></span> | <span data-ttu-id="0703e-345">CVSS-poäng för CVE.</span><span class="sxs-lookup"><span data-stu-id="0703e-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="0703e-346">6.2</span><span class="sxs-lookup"><span data-stu-id="0703e-346">6.2</span></span>  
<span data-ttu-id="0703e-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0703e-347">DeviceId</span></span> | <span data-ttu-id="0703e-348">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-348">string</span></span> | <span data-ttu-id="0703e-349">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0703e-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="0703e-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="0703e-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="0703e-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="0703e-351">DeviceName</span></span> | <span data-ttu-id="0703e-352">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-352">string</span></span> | <span data-ttu-id="0703e-353">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="0703e-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0703e-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="0703e-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="0703e-355">DiskPaths</span></span> | <span data-ttu-id="0703e-356">Matris[sträng]</span><span class="sxs-lookup"><span data-stu-id="0703e-356">Array[string]</span></span> | <span data-ttu-id="0703e-357">Disk bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="0703e-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="0703e-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="0703e-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="0703e-359">EventTimestamp</span></span> | <span data-ttu-id="0703e-360">Sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-360">String</span></span> | <span data-ttu-id="0703e-361">Tidpunkten då deltahändelsen hittades.</span><span class="sxs-lookup"><span data-stu-id="0703e-361">The time this delta event was found.</span></span> | <span data-ttu-id="0703e-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="0703e-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="0703e-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="0703e-363">ExploitabilityLevel</span></span> | <span data-ttu-id="0703e-364">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-364">string</span></span> | <span data-ttu-id="0703e-365">Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="0703e-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="0703e-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="0703e-366">ExploitIsInKit</span></span>  
<span data-ttu-id="0703e-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="0703e-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="0703e-368">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-368">string</span></span> | <span data-ttu-id="0703e-369">Första gången CVE för den här produkten sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="0703e-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="0703e-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="0703e-371">ID</span><span class="sxs-lookup"><span data-stu-id="0703e-371">Id</span></span> | <span data-ttu-id="0703e-372">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-372">string</span></span> | <span data-ttu-id="0703e-373">Unikt ID för posten.</span><span class="sxs-lookup"><span data-stu-id="0703e-373">Unique identifier for the record.</span></span> | <span data-ttu-id="0703e-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="0703e-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="0703e-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="0703e-375">LastSeenTimestamp</span></span> | <span data-ttu-id="0703e-376">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-376">string</span></span> | <span data-ttu-id="0703e-377">Senaste gången CVE sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="0703e-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="0703e-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="0703e-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="0703e-379">OSPlatform</span></span> | <span data-ttu-id="0703e-380">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-380">string</span></span> | <span data-ttu-id="0703e-381">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0703e-382">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0703e-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="0703e-383">Mer information finns i Operativsystem och plattformar som stöds av TVM.</span><span class="sxs-lookup"><span data-stu-id="0703e-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="0703e-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="0703e-384">Windows10</span></span>  
<span data-ttu-id="0703e-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="0703e-385">RbacGroupName</span></span> | <span data-ttu-id="0703e-386">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-386">string</span></span> | <span data-ttu-id="0703e-387">Den rollbaserade åtkomstkontrollgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0703e-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="0703e-388">Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat".</span><span class="sxs-lookup"><span data-stu-id="0703e-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="0703e-389">Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".</span><span class="sxs-lookup"><span data-stu-id="0703e-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="0703e-390">Servrar</span><span class="sxs-lookup"><span data-stu-id="0703e-390">Servers</span></span>  
<span data-ttu-id="0703e-391">RekommendationReference</span><span class="sxs-lookup"><span data-stu-id="0703e-391">RecommendationReference</span></span> | <span data-ttu-id="0703e-392">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-392">string</span></span> | <span data-ttu-id="0703e-393">En referens till det rekommendations-ID som hör till den här programvaran.</span><span class="sxs-lookup"><span data-stu-id="0703e-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="0703e-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="0703e-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="0703e-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="0703e-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="0703e-396">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-396">string</span></span> | <span data-ttu-id="0703e-397">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet.</span><span class="sxs-lookup"><span data-stu-id="0703e-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="0703e-398">Säkerhetsuppdateringar för april 2020</span><span class="sxs-lookup"><span data-stu-id="0703e-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="0703e-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="0703e-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="0703e-400">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-400">string</span></span> | <span data-ttu-id="0703e-401">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="0703e-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="0703e-402">4550961</span><span class="sxs-lookup"><span data-stu-id="0703e-402">4550961</span></span>  
<span data-ttu-id="0703e-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="0703e-403">RegistryPaths</span></span>  | <span data-ttu-id="0703e-404">Matris[sträng]</span><span class="sxs-lookup"><span data-stu-id="0703e-404">Array[string]</span></span> | <span data-ttu-id="0703e-405">Register bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="0703e-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="0703e-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="0703e-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="0703e-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="0703e-407">SoftwareName</span></span> | <span data-ttu-id="0703e-408">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-408">string</span></span> | <span data-ttu-id="0703e-409">Namnet på programvaruprodukten.</span><span class="sxs-lookup"><span data-stu-id="0703e-409">Name of the software product.</span></span> | <span data-ttu-id="0703e-410">chrome</span><span class="sxs-lookup"><span data-stu-id="0703e-410">chrome</span></span>  
<span data-ttu-id="0703e-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="0703e-411">SoftwareVendor</span></span> | <span data-ttu-id="0703e-412">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-412">string</span></span> | <span data-ttu-id="0703e-413">Namnet på programvaruleverantören.</span><span class="sxs-lookup"><span data-stu-id="0703e-413">Name of the software vendor.</span></span> | <span data-ttu-id="0703e-414">google</span><span class="sxs-lookup"><span data-stu-id="0703e-414">google</span></span>  
<span data-ttu-id="0703e-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="0703e-415">SoftwareVersion</span></span> | <span data-ttu-id="0703e-416">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-416">string</span></span> | <span data-ttu-id="0703e-417">Versionsnummer för programvaran.</span><span class="sxs-lookup"><span data-stu-id="0703e-417">Version number of the software product.</span></span> | <span data-ttu-id="0703e-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="0703e-418">81.0.4044.138</span></span>  
<span data-ttu-id="0703e-419">Status</span><span class="sxs-lookup"><span data-stu-id="0703e-419">Status</span></span> | <span data-ttu-id="0703e-420">Sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-420">String</span></span> | <span data-ttu-id="0703e-421">**Ny**   (för en ny säkerhetsrisk som introducerades på en enhet)  (1) **Åtgärdat**(om det här problemet inte finns längre på   enheten, vilket innebär att det har åtgärdats).</span><span class="sxs-lookup"><span data-stu-id="0703e-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="0703e-422">(2)  **Uppdaterad**   (om ett sårbarhetsproblem på en enhet har ändrats.</span><span class="sxs-lookup"><span data-stu-id="0703e-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="0703e-423">De möjliga ändringarna är: CVSS-poäng, sårbarhetsnivå, allvarlighetsnivå, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="0703e-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="0703e-424">Åtgärdat</span><span class="sxs-lookup"><span data-stu-id="0703e-424">Fixed</span></span>
<span data-ttu-id="0703e-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="0703e-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="0703e-426">sträng</span><span class="sxs-lookup"><span data-stu-id="0703e-426">string</span></span> | <span data-ttu-id="0703e-427">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden.</span><span class="sxs-lookup"><span data-stu-id="0703e-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="0703e-428">Medel</span><span class="sxs-lookup"><span data-stu-id="0703e-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="0703e-429">Förtydligande</span><span class="sxs-lookup"><span data-stu-id="0703e-429">Clarifications</span></span>

- <span data-ttu-id="0703e-430">Om programvaran uppdaterades från version 1.0 till version 2.0 och båda versionerna exponeras för CVE-A, får du 2 separata händelser:</span><span class="sxs-lookup"><span data-stu-id="0703e-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="0703e-431">Åtgärdat – CVE-A i version 1.0 har åtgärdats</span><span class="sxs-lookup"><span data-stu-id="0703e-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="0703e-432">Nytt – CVE-A på version 2.0 lades till</span><span class="sxs-lookup"><span data-stu-id="0703e-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="0703e-433">Om ett specifikt problem (till exempel CVE-A) först sågs vid en viss tidpunkt (till exempel 10 januari) på programvara med version 1.0, och några dagar senare uppdaterades programvaran till version 2.0 som också exponerades för samma CVE-A, får du dessa två separata händelser:</span><span class="sxs-lookup"><span data-stu-id="0703e-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="0703e-434">Åtgärdat – CVE-X, FirstSeenTimestamp 10 januari, version 1,0.</span><span class="sxs-lookup"><span data-stu-id="0703e-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="0703e-435">Nytt – CVE-X, FirstSeenTimestamp 10 januari, version 2.0.</span><span class="sxs-lookup"><span data-stu-id="0703e-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="0703e-436">3.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="0703e-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="0703e-437">3.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="0703e-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="0703e-438">3.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="0703e-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="0703e-439">Se även</span><span class="sxs-lookup"><span data-stu-id="0703e-439">See also</span></span>

- [<span data-ttu-id="0703e-440">Exportera utvärderingsmetoder och egenskaper per enhet</span><span class="sxs-lookup"><span data-stu-id="0703e-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="0703e-441">Exportera utvärdering av säker konfiguration per enhet</span><span class="sxs-lookup"><span data-stu-id="0703e-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="0703e-442">Exportera utvärdering av programvaruinventering per enhet</span><span class="sxs-lookup"><span data-stu-id="0703e-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="0703e-443">Andra relaterade</span><span class="sxs-lookup"><span data-stu-id="0703e-443">Other related</span></span>

- [<span data-ttu-id="0703e-444">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="0703e-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="0703e-445">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="0703e-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
