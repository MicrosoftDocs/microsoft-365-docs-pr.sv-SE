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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778360"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="54aab-105">Exportera bedömningar av säkerhetsproblem för programvara per enhet</span><span class="sxs-lookup"><span data-stu-id="54aab-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54aab-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="54aab-106">**Applies to:**</span></span>

- [<span data-ttu-id="54aab-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="54aab-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54aab-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54aab-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="54aab-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="54aab-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54aab-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="54aab-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="54aab-111">Returnerar alla kända säkerhetsproblem i programvaran och deras information för alla enheter, per enhet.</span><span class="sxs-lookup"><span data-stu-id="54aab-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="54aab-112">Det finns olika API-anrop för att få olika typer av data.</span><span class="sxs-lookup"><span data-stu-id="54aab-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="54aab-113">Eftersom mängden data kan vara mycket stor kan den hämtas på två sätt:</span><span class="sxs-lookup"><span data-stu-id="54aab-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="54aab-114">[Exportera säkerhetsproblem med programvara, utvärdering av OData](#1-export-software-vulnerabilities-assessment-odata)  API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet.</span><span class="sxs-lookup"><span data-stu-id="54aab-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="54aab-115">Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._</span><span class="sxs-lookup"><span data-stu-id="54aab-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="54aab-116">Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="54aab-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="54aab-117">[Exportera utvärdering av säkerhetsproblem för programvara via filer](#2-export-software-vulnerabilities-assessment-via-files) Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt.</span><span class="sxs-lookup"><span data-stu-id="54aab-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="54aab-118">Därför rekommenderas det för stora organisationer med fler än 100 K-enheter.</span><span class="sxs-lookup"><span data-stu-id="54aab-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="54aab-119">Detta API hämtar alla data i organisationen som nedladdningsfiler.</span><span class="sxs-lookup"><span data-stu-id="54aab-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="54aab-120">Svaret innehåller URL:er för att ladda ned alla data från Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="54aab-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="54aab-121">Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:</span><span class="sxs-lookup"><span data-stu-id="54aab-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="54aab-122">Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="54aab-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="54aab-123">Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.</span><span class="sxs-lookup"><span data-stu-id="54aab-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="54aab-124">Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data.</span><span class="sxs-lookup"><span data-stu-id="54aab-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="54aab-125">För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.</span><span class="sxs-lookup"><span data-stu-id="54aab-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="54aab-126">Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**</span><span class="sxs-lookup"><span data-stu-id="54aab-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="54aab-127">1. Utvärdering av säkerhetsproblem med programvara (OData)</span><span class="sxs-lookup"><span data-stu-id="54aab-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="54aab-128">1.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="54aab-128">1.1 API method description</span></span>

<span data-ttu-id="54aab-129">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="54aab-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="54aab-130">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="54aab-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="54aab-131">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="54aab-131">Limitations</span></span>

>- <span data-ttu-id="54aab-132">Maximal sidstorlek är 200 000.</span><span class="sxs-lookup"><span data-stu-id="54aab-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="54aab-133">Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="54aab-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="54aab-134">1.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="54aab-134">1.2 Permissions</span></span>

<span data-ttu-id="54aab-135">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="54aab-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="54aab-136">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="54aab-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="54aab-137">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="54aab-137">Permission type</span></span> | <span data-ttu-id="54aab-138">Behörighet</span><span class="sxs-lookup"><span data-stu-id="54aab-138">Permission</span></span> | <span data-ttu-id="54aab-139">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="54aab-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="54aab-140">Program</span><span class="sxs-lookup"><span data-stu-id="54aab-140">Application</span></span> | <span data-ttu-id="54aab-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="54aab-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="54aab-142">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="54aab-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="54aab-143">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="54aab-143">Delegated (work or school account)</span></span> | <span data-ttu-id="54aab-144">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="54aab-144">Vulnerability.Read</span></span> | <span data-ttu-id="54aab-145">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="54aab-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="54aab-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="54aab-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="54aab-147">1.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="54aab-147">1.4 Parameters</span></span>

- <span data-ttu-id="54aab-148">pageSize (standard = 50 000) – antal resultat som svar</span><span class="sxs-lookup"><span data-stu-id="54aab-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="54aab-149">$top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)</span><span class="sxs-lookup"><span data-stu-id="54aab-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="54aab-150">1.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="54aab-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="54aab-151">Varje post motsvarar ungefär 1 kB data.</span><span class="sxs-lookup"><span data-stu-id="54aab-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="54aab-152">Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.</span><span class="sxs-lookup"><span data-stu-id="54aab-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="54aab-153">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="54aab-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="54aab-154">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="54aab-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="54aab-155">Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.</span><span class="sxs-lookup"><span data-stu-id="54aab-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="54aab-156">När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="54aab-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="54aab-157">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="54aab-157">Property (ID)</span></span> | <span data-ttu-id="54aab-158">Datatyp</span><span class="sxs-lookup"><span data-stu-id="54aab-158">Data type</span></span> | <span data-ttu-id="54aab-159">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="54aab-159">Description</span></span> | <span data-ttu-id="54aab-160">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="54aab-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="54aab-161">CveId</span><span class="sxs-lookup"><span data-stu-id="54aab-161">CveId</span></span> | <span data-ttu-id="54aab-162">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-162">string</span></span> | <span data-ttu-id="54aab-163">Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE).</span><span class="sxs-lookup"><span data-stu-id="54aab-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="54aab-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="54aab-164">CVE-2020-15992</span></span>
<span data-ttu-id="54aab-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="54aab-165">CvssScore</span></span> | <span data-ttu-id="54aab-166">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-166">string</span></span> | <span data-ttu-id="54aab-167">CVSS-poäng för CVE.</span><span class="sxs-lookup"><span data-stu-id="54aab-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="54aab-168">6.2</span><span class="sxs-lookup"><span data-stu-id="54aab-168">6.2</span></span>
<span data-ttu-id="54aab-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="54aab-169">DeviceId</span></span> | <span data-ttu-id="54aab-170">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-170">string</span></span> | <span data-ttu-id="54aab-171">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="54aab-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="54aab-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="54aab-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="54aab-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="54aab-173">DeviceName</span></span> | <span data-ttu-id="54aab-174">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-174">string</span></span> | <span data-ttu-id="54aab-175">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="54aab-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54aab-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="54aab-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="54aab-177">DiskPaths</span></span>  | <span data-ttu-id="54aab-178">\[Matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="54aab-178">Array\[string\]</span></span> | <span data-ttu-id="54aab-179">Disk bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="54aab-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="54aab-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="54aab-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="54aab-181">ExploitabilityLevel</span></span> | <span data-ttu-id="54aab-182">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-182">string</span></span> | <span data-ttu-id="54aab-183">Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="54aab-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="54aab-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="54aab-184">ExploitIsInKit</span></span>
<span data-ttu-id="54aab-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="54aab-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="54aab-186">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-186">string</span></span> | <span data-ttu-id="54aab-187">Första gången CVE för den här produkten sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="54aab-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="54aab-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="54aab-189">ID</span><span class="sxs-lookup"><span data-stu-id="54aab-189">Id</span></span> | <span data-ttu-id="54aab-190">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-190">string</span></span> | <span data-ttu-id="54aab-191">Unikt ID för posten.</span><span class="sxs-lookup"><span data-stu-id="54aab-191">Unique identifier for the record.</span></span> | <span data-ttu-id="54aab-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="54aab-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="54aab-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="54aab-193">LastSeenTimestamp</span></span> | <span data-ttu-id="54aab-194">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-194">string</span></span> | <span data-ttu-id="54aab-195">Senaste gången CVE sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="54aab-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="54aab-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="54aab-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="54aab-197">OSPlatform</span></span> | <span data-ttu-id="54aab-198">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-198">string</span></span> | <span data-ttu-id="54aab-199">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="54aab-200">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="54aab-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="54aab-201">Mer information finns i Operativsystem och plattformar som stöds av TVM.</span><span class="sxs-lookup"><span data-stu-id="54aab-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="54aab-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="54aab-202">Windows10</span></span>
<span data-ttu-id="54aab-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="54aab-203">RbacGroupName</span></span>  | <span data-ttu-id="54aab-204">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-204">string</span></span> | <span data-ttu-id="54aab-205">Den rollbaserade åtkomstkontrollgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="54aab-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="54aab-206">Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat".</span><span class="sxs-lookup"><span data-stu-id="54aab-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="54aab-207">Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".</span><span class="sxs-lookup"><span data-stu-id="54aab-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="54aab-208">Servrar</span><span class="sxs-lookup"><span data-stu-id="54aab-208">Servers</span></span>
<span data-ttu-id="54aab-209">RekommendationReference</span><span class="sxs-lookup"><span data-stu-id="54aab-209">RecommendationReference</span></span> | <span data-ttu-id="54aab-210">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-210">string</span></span> | <span data-ttu-id="54aab-211">En referens till det rekommendations-ID som hör till den här programvaran.</span><span class="sxs-lookup"><span data-stu-id="54aab-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="54aab-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="54aab-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="54aab-213">RecommendedSecurityUpdate (valfritt)</span><span class="sxs-lookup"><span data-stu-id="54aab-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="54aab-214">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-214">string</span></span> | <span data-ttu-id="54aab-215">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet.</span><span class="sxs-lookup"><span data-stu-id="54aab-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="54aab-216">Säkerhetsuppdateringar för april 2020</span><span class="sxs-lookup"><span data-stu-id="54aab-216">April 2020 Security Updates</span></span>
<span data-ttu-id="54aab-217">RecommendedSecurityUpdateId (valfritt)</span><span class="sxs-lookup"><span data-stu-id="54aab-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="54aab-218">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-218">string</span></span> | <span data-ttu-id="54aab-219">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="54aab-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="54aab-220">4550961</span><span class="sxs-lookup"><span data-stu-id="54aab-220">4550961</span></span>
<span data-ttu-id="54aab-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="54aab-221">RegistryPaths</span></span>  | <span data-ttu-id="54aab-222">\[Matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="54aab-222">Array\[string\]</span></span> | <span data-ttu-id="54aab-223">Register bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="54aab-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="54aab-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="54aab-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="54aab-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="54aab-225">SoftwareName</span></span> | <span data-ttu-id="54aab-226">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-226">string</span></span> | <span data-ttu-id="54aab-227">Namnet på programvaruprodukten.</span><span class="sxs-lookup"><span data-stu-id="54aab-227">Name of the software product.</span></span> | <span data-ttu-id="54aab-228">chrome</span><span class="sxs-lookup"><span data-stu-id="54aab-228">chrome</span></span>
<span data-ttu-id="54aab-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="54aab-229">SoftwareVendor</span></span> | <span data-ttu-id="54aab-230">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-230">string</span></span> | <span data-ttu-id="54aab-231">Namnet på programvaruleverantören.</span><span class="sxs-lookup"><span data-stu-id="54aab-231">Name of the software vendor.</span></span> | <span data-ttu-id="54aab-232">google</span><span class="sxs-lookup"><span data-stu-id="54aab-232">google</span></span>
<span data-ttu-id="54aab-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="54aab-233">SoftwareVersion</span></span> | <span data-ttu-id="54aab-234">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-234">string</span></span> | <span data-ttu-id="54aab-235">Versionsnummer för programvaran.</span><span class="sxs-lookup"><span data-stu-id="54aab-235">Version number of the software product.</span></span> | <span data-ttu-id="54aab-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="54aab-236">81.0.4044.138</span></span>
<span data-ttu-id="54aab-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="54aab-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="54aab-238">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-238">string</span></span> | <span data-ttu-id="54aab-239">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden.</span><span class="sxs-lookup"><span data-stu-id="54aab-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="54aab-240">Medel</span><span class="sxs-lookup"><span data-stu-id="54aab-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="54aab-241">1.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="54aab-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="54aab-242">1.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="54aab-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="54aab-243">1.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="54aab-243">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="54aab-244">2. Exportera utvärdering av säkerhetsproblem för programvara (via filer)</span><span class="sxs-lookup"><span data-stu-id="54aab-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="54aab-245">2.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="54aab-245">2.1 API method description</span></span>

<span data-ttu-id="54aab-246">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="54aab-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="54aab-247">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="54aab-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="54aab-248">2.1.2 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="54aab-248">2.1.2 Limitations</span></span>

<span data-ttu-id="54aab-249">Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="54aab-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="54aab-250">2.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="54aab-250">2.2 Permissions</span></span>

<span data-ttu-id="54aab-251">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="54aab-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="54aab-252">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="54aab-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="54aab-253">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="54aab-253">Permission type</span></span> | <span data-ttu-id="54aab-254">Behörighet</span><span class="sxs-lookup"><span data-stu-id="54aab-254">Permission</span></span> | <span data-ttu-id="54aab-255">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="54aab-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="54aab-256">Program</span><span class="sxs-lookup"><span data-stu-id="54aab-256">Application</span></span> | <span data-ttu-id="54aab-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="54aab-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="54aab-258">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="54aab-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="54aab-259">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="54aab-259">Delegated (work or school account)</span></span> | <span data-ttu-id="54aab-260">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="54aab-260">Vulnerability.Read</span></span> | <span data-ttu-id="54aab-261">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="54aab-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="54aab-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="54aab-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="54aab-263">2.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="54aab-263">2.4 Parameters</span></span>

- <span data-ttu-id="54aab-264">sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar)</span><span class="sxs-lookup"><span data-stu-id="54aab-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="54aab-265">2.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="54aab-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="54aab-266">Filerna är gzip komprimerade & I multiline Json-format.</span><span class="sxs-lookup"><span data-stu-id="54aab-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="54aab-267">URL-adresser för nedladdning är endast giltiga i 3 timmar. annars kan du använda parametern.</span><span class="sxs-lookup"><span data-stu-id="54aab-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="54aab-268">För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.</span><span class="sxs-lookup"><span data-stu-id="54aab-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="54aab-269">Varje post motsvarar ungefär 1 kB data.</span><span class="sxs-lookup"><span data-stu-id="54aab-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="54aab-270">Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.</span><span class="sxs-lookup"><span data-stu-id="54aab-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="54aab-271">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="54aab-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="54aab-272">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="54aab-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="54aab-273">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="54aab-273">Property (ID)</span></span> | <span data-ttu-id="54aab-274">Datatyp</span><span class="sxs-lookup"><span data-stu-id="54aab-274">Data type</span></span> | <span data-ttu-id="54aab-275">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="54aab-275">Description</span></span> | <span data-ttu-id="54aab-276">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="54aab-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="54aab-277">Exportera filer</span><span class="sxs-lookup"><span data-stu-id="54aab-277">Export files</span></span> | <span data-ttu-id="54aab-278">\[matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="54aab-278">array\[string\]</span></span>  | <span data-ttu-id="54aab-279">En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen.</span><span class="sxs-lookup"><span data-stu-id="54aab-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="54aab-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="54aab-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="54aab-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="54aab-281">GeneratedTime</span></span> | <span data-ttu-id="54aab-282">sträng</span><span class="sxs-lookup"><span data-stu-id="54aab-282">string</span></span> | <span data-ttu-id="54aab-283">Tidpunkten då exporten skapades.</span><span class="sxs-lookup"><span data-stu-id="54aab-283">The time that the export was generated.</span></span> | <span data-ttu-id="54aab-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="54aab-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="54aab-285">2.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="54aab-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="54aab-286">2.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="54aab-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="54aab-287">2.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="54aab-287">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54aab-288">Se även</span><span class="sxs-lookup"><span data-stu-id="54aab-288">See also</span></span>

- [<span data-ttu-id="54aab-289">Exportera utvärderingsmetoder och egenskaper per enhet</span><span class="sxs-lookup"><span data-stu-id="54aab-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="54aab-290">Exportera utvärdering av säker konfiguration per enhet</span><span class="sxs-lookup"><span data-stu-id="54aab-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="54aab-291">Exportera utvärdering av programvaruinventering per enhet</span><span class="sxs-lookup"><span data-stu-id="54aab-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="54aab-292">Andra relaterade</span><span class="sxs-lookup"><span data-stu-id="54aab-292">Other related</span></span>

- [<span data-ttu-id="54aab-293">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="54aab-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="54aab-294">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="54aab-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
