---
title: Exportera utvärdering av programvaruinventering per enhet
description: Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.
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
ms.openlocfilehash: 3a65fb6d5d3e5c6e68e100aa3ea2b4cf896dc281
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789404"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="48032-104">Exportera utvärdering av programvaruinventering per enhet</span><span class="sxs-lookup"><span data-stu-id="48032-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48032-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="48032-105">**Applies to:**</span></span>

- [<span data-ttu-id="48032-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="48032-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48032-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48032-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="48032-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="48032-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48032-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="48032-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="48032-110">Det finns olika API-anrop för att få olika typer av data.</span><span class="sxs-lookup"><span data-stu-id="48032-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="48032-111">Eftersom mängden data kan vara stor kan den hämtas på två sätt:</span><span class="sxs-lookup"><span data-stu-id="48032-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="48032-112">[Exportera utvärdering av programvaruinventering **av OData**](#1-export-software-inventory-assessment-odata)  API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet.</span><span class="sxs-lookup"><span data-stu-id="48032-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="48032-113">Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._</span><span class="sxs-lookup"><span data-stu-id="48032-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="48032-114">Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="48032-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="48032-115">[Exportera utvärdering av programvaruinventering **via filer**](#2-export-software-inventory-assessment-via-files)  Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt.</span><span class="sxs-lookup"><span data-stu-id="48032-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="48032-116">Därför rekommenderas det för stora organisationer med fler än 100 K-enheter.</span><span class="sxs-lookup"><span data-stu-id="48032-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="48032-117">Detta API hämtar alla data i organisationen som nedladdningsfiler.</span><span class="sxs-lookup"><span data-stu-id="48032-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="48032-118">Svaret innehåller URL:er för att ladda ned alla data från Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="48032-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="48032-119">Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:</span><span class="sxs-lookup"><span data-stu-id="48032-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="48032-120">Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="48032-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="48032-121">Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.</span><span class="sxs-lookup"><span data-stu-id="48032-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="48032-122">Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data.</span><span class="sxs-lookup"><span data-stu-id="48032-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="48032-123">För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.</span><span class="sxs-lookup"><span data-stu-id="48032-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="48032-124">Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**</span><span class="sxs-lookup"><span data-stu-id="48032-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="48032-125">1. Exportera utvärdering av programvara för lager (OData)</span><span class="sxs-lookup"><span data-stu-id="48032-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="48032-126">1.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="48032-126">1.1 API method description</span></span>

<span data-ttu-id="48032-127">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="48032-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="48032-128">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="48032-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="48032-129">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="48032-129">Limitations</span></span>

- <span data-ttu-id="48032-130">Maximal sidstorlek är 200 000.</span><span class="sxs-lookup"><span data-stu-id="48032-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="48032-131">Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="48032-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="48032-132">1.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="48032-132">1.2 Permissions</span></span>

<span data-ttu-id="48032-133">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="48032-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="48032-134">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="48032-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="48032-135">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="48032-135">Permission type</span></span> | <span data-ttu-id="48032-136">Behörighet</span><span class="sxs-lookup"><span data-stu-id="48032-136">Permission</span></span> | <span data-ttu-id="48032-137">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="48032-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="48032-138">Program</span><span class="sxs-lookup"><span data-stu-id="48032-138">Application</span></span> | <span data-ttu-id="48032-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="48032-139">Software.Read.All</span></span> | <span data-ttu-id="48032-140">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="48032-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="48032-141">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="48032-141">Delegated (work or school account)</span></span> | <span data-ttu-id="48032-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="48032-142">Software.Read</span></span> | <span data-ttu-id="48032-143">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="48032-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="48032-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="48032-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="48032-145">1.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="48032-145">1.4 Parameters</span></span>

- <span data-ttu-id="48032-146">pageSize (standard = 50 000) – antal resultat som svar.</span><span class="sxs-lookup"><span data-stu-id="48032-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="48032-147">$top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)</span><span class="sxs-lookup"><span data-stu-id="48032-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="48032-148">1.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="48032-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="48032-149">-Varje post är cirka 0,5 kB data.</span><span class="sxs-lookup"><span data-stu-id="48032-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="48032-150">Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.</span><span class="sxs-lookup"><span data-stu-id="48032-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="48032-151">-Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.</span><span class="sxs-lookup"><span data-stu-id="48032-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="48032-152">När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="48032-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="48032-153">-Några ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="48032-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="48032-154">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="48032-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="48032-155">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="48032-155">Property (ID)</span></span> | <span data-ttu-id="48032-156">Datatyp</span><span class="sxs-lookup"><span data-stu-id="48032-156">Data type</span></span> | <span data-ttu-id="48032-157">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="48032-157">Description</span></span> | <span data-ttu-id="48032-158">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="48032-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="48032-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="48032-159">DeviceId</span></span> | <span data-ttu-id="48032-160">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-160">string</span></span> | <span data-ttu-id="48032-161">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="48032-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="48032-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="48032-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="48032-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="48032-163">DeviceName</span></span> | <span data-ttu-id="48032-164">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-164">string</span></span> | <span data-ttu-id="48032-165">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="48032-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="48032-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48032-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="48032-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="48032-167">DiskPaths</span></span> | <span data-ttu-id="48032-168">Matris[sträng]</span><span class="sxs-lookup"><span data-stu-id="48032-168">Array[string]</span></span>  | <span data-ttu-id="48032-169">Disk bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="48032-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="48032-170">[ "C: \\ Program files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="48032-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="48032-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="48032-171">EndOfSupportDate</span></span> | <span data-ttu-id="48032-172">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-172">string</span></span> | <span data-ttu-id="48032-173">Datumet då supporten för den här programvaran har eller kommer att upphöra.</span><span class="sxs-lookup"><span data-stu-id="48032-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="48032-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="48032-174">2020-12-30</span></span>
<span data-ttu-id="48032-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="48032-175">EndOfSupportStatus</span></span> | <span data-ttu-id="48032-176">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-176">string</span></span> | <span data-ttu-id="48032-177">Supportstatusen avslutas.</span><span class="sxs-lookup"><span data-stu-id="48032-177">End of support status.</span></span> <span data-ttu-id="48032-178">Kan innehålla följande möjliga värden: Ingen, EOS-version, Kommande EOS-version, EOS-programvara, kommande EOS-programvara.</span><span class="sxs-lookup"><span data-stu-id="48032-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="48032-179">Kommande EOS</span><span class="sxs-lookup"><span data-stu-id="48032-179">Upcoming EOS</span></span>
<span data-ttu-id="48032-180">ID</span><span class="sxs-lookup"><span data-stu-id="48032-180">Id</span></span> | <span data-ttu-id="48032-181">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-181">string</span></span> | <span data-ttu-id="48032-182">Unikt ID för posten.</span><span class="sxs-lookup"><span data-stu-id="48032-182">Unique identifier for the record.</span></span> | <span data-ttu-id="48032-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="48032-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="48032-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="48032-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="48032-185">int</span><span class="sxs-lookup"><span data-stu-id="48032-185">int</span></span> | <span data-ttu-id="48032-186">Antal svagheter på den här programvaran på den här enheten</span><span class="sxs-lookup"><span data-stu-id="48032-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="48032-187">3</span><span class="sxs-lookup"><span data-stu-id="48032-187">3</span></span>
<span data-ttu-id="48032-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="48032-188">OSPlatform</span></span> | <span data-ttu-id="48032-189">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-189">string</span></span> | <span data-ttu-id="48032-190">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="48032-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="48032-191">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="48032-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="48032-192">Mer information finns i Operativsystem och plattformar som stöds av TVM.</span><span class="sxs-lookup"><span data-stu-id="48032-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="48032-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="48032-193">Windows10</span></span>
<span data-ttu-id="48032-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="48032-194">RbacGroupName</span></span> | <span data-ttu-id="48032-195">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-195">string</span></span> | <span data-ttu-id="48032-196">Den rollbaserade åtkomstkontrollgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="48032-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="48032-197">Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat".</span><span class="sxs-lookup"><span data-stu-id="48032-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="48032-198">Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".</span><span class="sxs-lookup"><span data-stu-id="48032-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="48032-199">Servrar</span><span class="sxs-lookup"><span data-stu-id="48032-199">Servers</span></span>
<span data-ttu-id="48032-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="48032-200">RegistryPaths</span></span> | <span data-ttu-id="48032-201">Matris[sträng]</span><span class="sxs-lookup"><span data-stu-id="48032-201">Array[string]</span></span> | <span data-ttu-id="48032-202">Register bevis för att produkten är installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="48032-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="48032-203">[ "HKEY_LOCAL_MACHINE \\ PROGRAMVARA \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Avinstallera Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="48032-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="48032-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="48032-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="48032-205">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-205">string</span></span> | <span data-ttu-id="48032-206">Första gången programvaran sågs på enheten.</span><span class="sxs-lookup"><span data-stu-id="48032-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="48032-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="48032-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="48032-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="48032-208">SoftwareName</span></span> | <span data-ttu-id="48032-209">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-209">string</span></span> | <span data-ttu-id="48032-210">Namnet på programvaruprodukten.</span><span class="sxs-lookup"><span data-stu-id="48032-210">Name of the software product.</span></span> | <span data-ttu-id="48032-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="48032-211">Silverlight</span></span>
<span data-ttu-id="48032-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="48032-212">SoftwareVendor</span></span> | <span data-ttu-id="48032-213">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-213">string</span></span> | <span data-ttu-id="48032-214">Namnet på programvaruleverantören.</span><span class="sxs-lookup"><span data-stu-id="48032-214">Name of the software vendor.</span></span> | <span data-ttu-id="48032-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="48032-215">microsoft</span></span>
<span data-ttu-id="48032-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="48032-216">SoftwareVersion</span></span> | <span data-ttu-id="48032-217">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-217">string</span></span> | <span data-ttu-id="48032-218">Versionsnummer för programvaran.</span><span class="sxs-lookup"><span data-stu-id="48032-218">Version number of the software product.</span></span> | <span data-ttu-id="48032-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="48032-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="48032-220">1.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="48032-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="48032-221">1.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="48032-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="48032-222">1.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="48032-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="48032-223">2. Exportera utvärdering av programvara för lager (via filer)</span><span class="sxs-lookup"><span data-stu-id="48032-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="48032-224">2.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="48032-224">2.1 API method description</span></span>

<span data-ttu-id="48032-225">Det här API-svaret innehåller alla data om installerad programvara per enhet.</span><span class="sxs-lookup"><span data-stu-id="48032-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="48032-226">Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="48032-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="48032-227">2.1.1 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="48032-227">2.1.1 Limitations</span></span>

<span data-ttu-id="48032-228">Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="48032-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="48032-229">2.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="48032-229">2.2 Permissions</span></span>

<span data-ttu-id="48032-230">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="48032-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="48032-231">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="48032-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="48032-232">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="48032-232">Permission type</span></span> | <span data-ttu-id="48032-233">Behörighet</span><span class="sxs-lookup"><span data-stu-id="48032-233">Permission</span></span> | <span data-ttu-id="48032-234">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="48032-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="48032-235">Program</span><span class="sxs-lookup"><span data-stu-id="48032-235">Application</span></span> | <span data-ttu-id="48032-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="48032-236">Software.Read.All</span></span> | <span data-ttu-id="48032-237">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="48032-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="48032-238">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="48032-238">Delegated (work or school account)</span></span> | <span data-ttu-id="48032-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="48032-239">Software.Read</span></span> | <span data-ttu-id="48032-240">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="48032-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="48032-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="48032-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="48032-242">Parametrar</span><span class="sxs-lookup"><span data-stu-id="48032-242">Parameters</span></span>

- <span data-ttu-id="48032-243">sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar)</span><span class="sxs-lookup"><span data-stu-id="48032-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="48032-244">2.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="48032-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="48032-245">Filerna är gzip komprimerade & I multiline Json-format.</span><span class="sxs-lookup"><span data-stu-id="48032-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="48032-246">Url:erna för nedladdning är endast giltiga i 3 timmar.</span><span class="sxs-lookup"><span data-stu-id="48032-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="48032-247">Annars kan du använda parametern.</span><span class="sxs-lookup"><span data-stu-id="48032-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="48032-248">_ För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.</span><span class="sxs-lookup"><span data-stu-id="48032-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="48032-249">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="48032-249">Property (ID)</span></span> | <span data-ttu-id="48032-250">Datatyp</span><span class="sxs-lookup"><span data-stu-id="48032-250">Data type</span></span> | <span data-ttu-id="48032-251">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="48032-251">Description</span></span> | <span data-ttu-id="48032-252">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="48032-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="48032-253">Exportera filer</span><span class="sxs-lookup"><span data-stu-id="48032-253">Export files</span></span> | <span data-ttu-id="48032-254">\[matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="48032-254">array\[string\]</span></span> | <span data-ttu-id="48032-255">En lista över hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen</span><span class="sxs-lookup"><span data-stu-id="48032-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="48032-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="48032-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="48032-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="48032-257">GeneratedTime</span></span> | <span data-ttu-id="48032-258">sträng</span><span class="sxs-lookup"><span data-stu-id="48032-258">string</span></span> | <span data-ttu-id="48032-259">Tidpunkten då exporten skapades.</span><span class="sxs-lookup"><span data-stu-id="48032-259">The time that the export was generated.</span></span> | <span data-ttu-id="48032-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="48032-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="48032-261">2.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="48032-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="48032-262">2.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="48032-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="48032-263">2.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="48032-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="48032-264">Se även</span><span class="sxs-lookup"><span data-stu-id="48032-264">See also</span></span>

- [<span data-ttu-id="48032-265">Exportera utvärderingsmetoder och egenskaper per enhet</span><span class="sxs-lookup"><span data-stu-id="48032-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="48032-266">Exportera utvärdering av säker konfiguration per enhet</span><span class="sxs-lookup"><span data-stu-id="48032-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="48032-267">Exportera bedömningar av säkerhetsproblem för programvara per enhet</span><span class="sxs-lookup"><span data-stu-id="48032-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="48032-268">Andra relaterade</span><span class="sxs-lookup"><span data-stu-id="48032-268">Other related</span></span>

- [<span data-ttu-id="48032-269">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="48032-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="48032-270">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="48032-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
