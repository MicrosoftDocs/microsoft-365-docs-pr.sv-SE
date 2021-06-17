---
title: Exportera utvärdering av säker konfiguration per enhet
description: Returnerar en post för varje unik kombination av DeviceId, ConfigurationId.
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
ms.openlocfilehash: 5742c121b73eb8709e770c9b2c4da6dbfd942276
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984862"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="73fb6-104">Exportera utvärdering av säker konfiguration per enhet</span><span class="sxs-lookup"><span data-stu-id="73fb6-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73fb6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="73fb6-105">**Applies to:**</span></span>

- [<span data-ttu-id="73fb6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="73fb6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73fb6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73fb6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="73fb6-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="73fb6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73fb6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="73fb6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="73fb6-110">Returnerar alla konfigurationer och deras status per enhet.</span><span class="sxs-lookup"><span data-stu-id="73fb6-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="73fb6-111">Det finns olika API-anrop för att få olika typer av data.</span><span class="sxs-lookup"><span data-stu-id="73fb6-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="73fb6-112">Eftersom mängden data kan vara stor kan den hämtas på två sätt:</span><span class="sxs-lookup"><span data-stu-id="73fb6-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="73fb6-113">[Exportera **OData** för säker](#1-export-secure-configuration-assessment-odata)konfigurationsutvärdering: API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet.</span><span class="sxs-lookup"><span data-stu-id="73fb6-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="73fb6-114">Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._</span><span class="sxs-lookup"><span data-stu-id="73fb6-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="73fb6-115">Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.</span><span class="sxs-lookup"><span data-stu-id="73fb6-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="73fb6-116">[Exportera säker konfigurationsbedömning **via filer**](#2-export-secure-configuration-assessment-via-files): Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt.</span><span class="sxs-lookup"><span data-stu-id="73fb6-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="73fb6-117">Därför rekommenderas det för stora organisationer med fler än 100 K-enheter.</span><span class="sxs-lookup"><span data-stu-id="73fb6-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="73fb6-118">Detta API hämtar alla data i organisationen som nedladdningsfiler.</span><span class="sxs-lookup"><span data-stu-id="73fb6-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="73fb6-119">Svaret innehåller URL:er för att ladda ned alla data från Azure-lagring.</span><span class="sxs-lookup"><span data-stu-id="73fb6-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="73fb6-120">Med det här API:t kan du ladda ned alla dina data Azure-lagring enligt följande:</span><span class="sxs-lookup"><span data-stu-id="73fb6-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="73fb6-121">Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="73fb6-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="73fb6-122">Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.</span><span class="sxs-lookup"><span data-stu-id="73fb6-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="73fb6-123">Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data.</span><span class="sxs-lookup"><span data-stu-id="73fb6-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="73fb6-124">För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.</span><span class="sxs-lookup"><span data-stu-id="73fb6-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="73fb6-125">Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**</span><span class="sxs-lookup"><span data-stu-id="73fb6-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="73fb6-126">1. Exportera utvärdering av säker konfiguration (OData)</span><span class="sxs-lookup"><span data-stu-id="73fb6-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="73fb6-127">1.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="73fb6-127">1.1 API method description</span></span>

<span data-ttu-id="73fb6-128">Det här API-svaret innehåller Secure Configuration Assessment på dina exponerade enheter och returnerar en post för varje unik kombination av DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="73fb6-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="73fb6-129">1.1.1 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="73fb6-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="73fb6-130">Maximal sidstorlek är 200 000.</span><span class="sxs-lookup"><span data-stu-id="73fb6-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="73fb6-131">Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="73fb6-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="73fb6-132">1.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="73fb6-132">1.2 Permissions</span></span>

<span data-ttu-id="73fb6-133">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="73fb6-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="73fb6-134">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="73fb6-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="73fb6-135">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="73fb6-135">Permission type</span></span> | <span data-ttu-id="73fb6-136">Behörighet</span><span class="sxs-lookup"><span data-stu-id="73fb6-136">Permission</span></span> | <span data-ttu-id="73fb6-137">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="73fb6-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="73fb6-138">Program</span><span class="sxs-lookup"><span data-stu-id="73fb6-138">Application</span></span> | <span data-ttu-id="73fb6-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="73fb6-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="73fb6-140">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="73fb6-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="73fb6-141">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="73fb6-141">Delegated (work or school account)</span></span> | <span data-ttu-id="73fb6-142">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="73fb6-142">Vulnerability.Read</span></span> | <span data-ttu-id="73fb6-143">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="73fb6-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="73fb6-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="73fb6-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="73fb6-145">1.4 Parametrar</span><span class="sxs-lookup"><span data-stu-id="73fb6-145">1.4 Parameters</span></span>

- <span data-ttu-id="73fb6-146">pageSize \( default = 50,000 \) – antal resultat i svar</span><span class="sxs-lookup"><span data-stu-id="73fb6-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="73fb6-147">\$överst – antalet resultat som ska \( returneras returnerar \@ inte odata.nextLink och hämtar därför inte alla data\)</span><span class="sxs-lookup"><span data-stu-id="73fb6-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="73fb6-148">1.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="73fb6-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="73fb6-149">Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.</span><span class="sxs-lookup"><span data-stu-id="73fb6-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="73fb6-150">När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="73fb6-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="73fb6-151">Vissa ytterligare kolumner kan returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="73fb6-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="73fb6-152">Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="73fb6-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="73fb6-153">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="73fb6-153">Property (ID)</span></span> | <span data-ttu-id="73fb6-154">Datatyp</span><span class="sxs-lookup"><span data-stu-id="73fb6-154">Data type</span></span> | <span data-ttu-id="73fb6-155">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="73fb6-155">Description</span></span> | <span data-ttu-id="73fb6-156">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="73fb6-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="73fb6-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="73fb6-157">ConfigurationCategory</span></span> | <span data-ttu-id="73fb6-158">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-158">string</span></span> | <span data-ttu-id="73fb6-159">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="73fb6-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="73fb6-160">Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="73fb6-160">Security controls</span></span>
<span data-ttu-id="73fb6-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="73fb6-161">ConfigurationId</span></span> | <span data-ttu-id="73fb6-162">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-162">string</span></span> | <span data-ttu-id="73fb6-163">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="73fb6-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="73fb6-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="73fb6-164">scid-10000</span></span>
<span data-ttu-id="73fb6-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="73fb6-165">ConfigurationImpact</span></span> | <span data-ttu-id="73fb6-166">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-166">string</span></span> | <span data-ttu-id="73fb6-167">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="73fb6-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="73fb6-168">9</span><span class="sxs-lookup"><span data-stu-id="73fb6-168">9</span></span>
<span data-ttu-id="73fb6-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="73fb6-169">ConfigurationName</span></span> | <span data-ttu-id="73fb6-170">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-170">string</span></span> | <span data-ttu-id="73fb6-171">Visningsnamn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="73fb6-171">Display name of the configuration</span></span> | <span data-ttu-id="73fb6-172">Registrera enheter till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="73fb6-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="73fb6-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="73fb6-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="73fb6-174">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-174">string</span></span> | <span data-ttu-id="73fb6-175">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="73fb6-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="73fb6-176">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="73fb6-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="73fb6-177">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="73fb6-177">Onboard Devices</span></span>
<span data-ttu-id="73fb6-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="73fb6-178">DeviceId</span></span> | <span data-ttu-id="73fb6-179">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-179">string</span></span> | <span data-ttu-id="73fb6-180">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="73fb6-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="73fb6-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="73fb6-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="73fb6-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="73fb6-182">DeviceName</span></span> | <span data-ttu-id="73fb6-183">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-183">string</span></span> | <span data-ttu-id="73fb6-184">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="73fb6-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="73fb6-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73fb6-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="73fb6-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="73fb6-186">IsApplicable</span></span> | <span data-ttu-id="73fb6-187">bool</span><span class="sxs-lookup"><span data-stu-id="73fb6-187">bool</span></span> | <span data-ttu-id="73fb6-188">Anger om konfigurationen eller principen är tillämplig</span><span class="sxs-lookup"><span data-stu-id="73fb6-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="73fb6-189">true</span><span class="sxs-lookup"><span data-stu-id="73fb6-189">true</span></span>
<span data-ttu-id="73fb6-190">IsCompliet</span><span class="sxs-lookup"><span data-stu-id="73fb6-190">IsCompliant</span></span> | <span data-ttu-id="73fb6-191">bool</span><span class="sxs-lookup"><span data-stu-id="73fb6-191">bool</span></span> | <span data-ttu-id="73fb6-192">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="73fb6-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="73fb6-193">false</span><span class="sxs-lookup"><span data-stu-id="73fb6-193">false</span></span>
<span data-ttu-id="73fb6-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="73fb6-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="73fb6-195">bool</span><span class="sxs-lookup"><span data-stu-id="73fb6-195">bool</span></span> | <span data-ttu-id="73fb6-196">Anger om det kommer att finnas någon påverkan på användaren om konfigurationen ska användas</span><span class="sxs-lookup"><span data-stu-id="73fb6-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="73fb6-197">true</span><span class="sxs-lookup"><span data-stu-id="73fb6-197">true</span></span>
<span data-ttu-id="73fb6-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="73fb6-198">OSPlatform</span></span> | <span data-ttu-id="73fb6-199">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-199">string</span></span> | <span data-ttu-id="73fb6-200">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="73fb6-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="73fb6-201">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="73fb6-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="73fb6-202">Mer information finns i Operativsystem och plattformar som stöds av TVM.</span><span class="sxs-lookup"><span data-stu-id="73fb6-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="73fb6-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="73fb6-203">Windows10</span></span>
<span data-ttu-id="73fb6-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="73fb6-204">RbacGroupName</span></span> | <span data-ttu-id="73fb6-205">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-205">string</span></span> | <span data-ttu-id="73fb6-206">Den rollbaserade åtkomstkontrollgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="73fb6-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="73fb6-207">Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat".</span><span class="sxs-lookup"><span data-stu-id="73fb6-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="73fb6-208">Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen".</span><span class="sxs-lookup"><span data-stu-id="73fb6-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="73fb6-209">Servrar</span><span class="sxs-lookup"><span data-stu-id="73fb6-209">Servers</span></span>
<span data-ttu-id="73fb6-210">RekommendationReference</span><span class="sxs-lookup"><span data-stu-id="73fb6-210">RecommendationReference</span></span> | <span data-ttu-id="73fb6-211">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-211">string</span></span> | <span data-ttu-id="73fb6-212">En referens till det rekommendations-ID som hör till den här programvaran.</span><span class="sxs-lookup"><span data-stu-id="73fb6-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="73fb6-213">sca-_scid-20000</span><span class="sxs-lookup"><span data-stu-id="73fb6-213">sca-_-scid-20000</span></span>
<span data-ttu-id="73fb6-214">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="73fb6-214">Timestamp</span></span> | <span data-ttu-id="73fb6-215">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-215">string</span></span> | <span data-ttu-id="73fb6-216">Senaste gången konfigurationen sågs på enheten</span><span class="sxs-lookup"><span data-stu-id="73fb6-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="73fb6-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="73fb6-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="73fb6-218">1.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="73fb6-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="73fb6-219">1.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="73fb6-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="73fb6-220">1.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="73fb6-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="73fb6-221">2. Exportera utvärdering av säker konfiguration (via filer)</span><span class="sxs-lookup"><span data-stu-id="73fb6-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="73fb6-222">2.1 API-metodbeskrivning</span><span class="sxs-lookup"><span data-stu-id="73fb6-222">2.1 API method description</span></span>

<span data-ttu-id="73fb6-223">Det här API-svaret innehåller Secure Configuration Assessment på dina exponerade enheter och returnerar en post för varje unik kombination av DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="73fb6-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="73fb6-224">2.1.2 Begränsningar</span><span class="sxs-lookup"><span data-stu-id="73fb6-224">2.1.2 Limitations</span></span>

<span data-ttu-id="73fb6-225">Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="73fb6-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="73fb6-226">2.2 Behörigheter</span><span class="sxs-lookup"><span data-stu-id="73fb6-226">2.2 Permissions</span></span>

<span data-ttu-id="73fb6-227">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="73fb6-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="73fb6-228">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="73fb6-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="73fb6-229">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="73fb6-229">Permission type</span></span> | <span data-ttu-id="73fb6-230">Behörighet</span><span class="sxs-lookup"><span data-stu-id="73fb6-230">Permission</span></span> | <span data-ttu-id="73fb6-231">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="73fb6-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="73fb6-232">Program</span><span class="sxs-lookup"><span data-stu-id="73fb6-232">Application</span></span> | <span data-ttu-id="73fb6-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="73fb6-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="73fb6-234">\'Läs "Hantering av hot och säkerhetsrisker" sårbarhetsinformation\'</span><span class="sxs-lookup"><span data-stu-id="73fb6-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="73fb6-235">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="73fb6-235">Delegated (work or school account)</span></span> | <span data-ttu-id="73fb6-236">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="73fb6-236">Vulnerability.Read</span></span> | <span data-ttu-id="73fb6-237">\'Läs "Hantering av hot och säkerhetsrisker" sårbarhetsinformation\'</span><span class="sxs-lookup"><span data-stu-id="73fb6-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="73fb6-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="73fb6-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="73fb6-239">Parametrar</span><span class="sxs-lookup"><span data-stu-id="73fb6-239">Parameters</span></span>

- <span data-ttu-id="73fb6-240">sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar).</span><span class="sxs-lookup"><span data-stu-id="73fb6-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="73fb6-241">2.5 Egenskaper</span><span class="sxs-lookup"><span data-stu-id="73fb6-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="73fb6-242">Filerna är gzip komprimerade & I multiline Json-format.</span><span class="sxs-lookup"><span data-stu-id="73fb6-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="73fb6-243">URL-adresser för nedladdning är endast giltiga i 3 timmar. annars kan du använda parametern.</span><span class="sxs-lookup"><span data-stu-id="73fb6-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="73fb6-244">För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.</span><span class="sxs-lookup"><span data-stu-id="73fb6-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="73fb6-245">Egenskap (ID)</span><span class="sxs-lookup"><span data-stu-id="73fb6-245">Property (ID)</span></span> | <span data-ttu-id="73fb6-246">Datatyp</span><span class="sxs-lookup"><span data-stu-id="73fb6-246">Data type</span></span> | <span data-ttu-id="73fb6-247">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="73fb6-247">Description</span></span> | <span data-ttu-id="73fb6-248">Exempel på ett returnerat värde</span><span class="sxs-lookup"><span data-stu-id="73fb6-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="73fb6-249">Exportera filer</span><span class="sxs-lookup"><span data-stu-id="73fb6-249">Export files</span></span> | <span data-ttu-id="73fb6-250">\[matrissträng\]</span><span class="sxs-lookup"><span data-stu-id="73fb6-250">array\[string\]</span></span> | <span data-ttu-id="73fb6-251">En lista över hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen</span><span class="sxs-lookup"><span data-stu-id="73fb6-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="73fb6-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="73fb6-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="73fb6-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="73fb6-253">GeneratedTime</span></span> | <span data-ttu-id="73fb6-254">sträng</span><span class="sxs-lookup"><span data-stu-id="73fb6-254">string</span></span> | <span data-ttu-id="73fb6-255">Tidpunkten då exporten skapades.</span><span class="sxs-lookup"><span data-stu-id="73fb6-255">The time that the export was generated.</span></span> | <span data-ttu-id="73fb6-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="73fb6-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="73fb6-257">2.6 Exempel</span><span class="sxs-lookup"><span data-stu-id="73fb6-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="73fb6-258">2.6.1 Exempel på begäran</span><span class="sxs-lookup"><span data-stu-id="73fb6-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="73fb6-259">2.6.2 Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="73fb6-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="73fb6-260">Se även</span><span class="sxs-lookup"><span data-stu-id="73fb6-260">See also</span></span>

- [<span data-ttu-id="73fb6-261">Exportera utvärderingsmetoder och egenskaper per enhet</span><span class="sxs-lookup"><span data-stu-id="73fb6-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="73fb6-262">Exportera utvärdering av programvaruinventering per enhet</span><span class="sxs-lookup"><span data-stu-id="73fb6-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="73fb6-263">Exportera bedömningar av säkerhetsproblem för programvara per enhet</span><span class="sxs-lookup"><span data-stu-id="73fb6-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="73fb6-264">Andra relaterade</span><span class="sxs-lookup"><span data-stu-id="73fb6-264">Other related</span></span>

- [<span data-ttu-id="73fb6-265">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="73fb6-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="73fb6-266">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="73fb6-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
