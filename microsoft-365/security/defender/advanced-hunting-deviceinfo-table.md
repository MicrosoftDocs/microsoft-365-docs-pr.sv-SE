---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Mer information om OS, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689115"
---
# <a name="deviceinfo"></a><span data-ttu-id="603ea-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="603ea-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="603ea-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="603ea-105">**Applies to:**</span></span>
- <span data-ttu-id="603ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="603ea-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="603ea-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="603ea-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="603ea-108">Tabellen `DeviceInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om enheter i organisationen, till exempel OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="603ea-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="603ea-109">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="603ea-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="603ea-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="603ea-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="603ea-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="603ea-111">Column name</span></span> | <span data-ttu-id="603ea-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="603ea-112">Data type</span></span> | <span data-ttu-id="603ea-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="603ea-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="603ea-114">datetime</span><span class="sxs-lookup"><span data-stu-id="603ea-114">datetime</span></span> | <span data-ttu-id="603ea-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="603ea-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="603ea-116">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-116">string</span></span> | <span data-ttu-id="603ea-117">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="603ea-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="603ea-118">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-118">string</span></span> | <span data-ttu-id="603ea-119">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="603ea-120">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-120">string</span></span> | <span data-ttu-id="603ea-121">Version av slutpunktsagenten eller sensorn som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="603ea-122">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-122">string</span></span> | <span data-ttu-id="603ea-123">Offentlig IP-adress som används av den onboarded machine för att ansluta till Microsoft Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="603ea-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="603ea-124">Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="603ea-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="603ea-125">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-125">string</span></span> | <span data-ttu-id="603ea-126">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="603ea-127">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-127">string</span></span> | <span data-ttu-id="603ea-128">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="603ea-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="603ea-129">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="603ea-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="603ea-130">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-130">string</span></span> | <span data-ttu-id="603ea-131">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="603ea-132">boolesk</span><span class="sxs-lookup"><span data-stu-id="603ea-132">boolean</span></span> | <span data-ttu-id="603ea-133">Boolesk indikator på om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="603ea-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="603ea-134">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-134">string</span></span> | <span data-ttu-id="603ea-135">Unikt ID för enheten i Azure AD</span><span class="sxs-lookup"><span data-stu-id="603ea-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="603ea-136">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-136">string</span></span> | <span data-ttu-id="603ea-137">Lista över alla användare som är inloggade på datorn vid tiden för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="603ea-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="603ea-138">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-138">string</span></span> | <span data-ttu-id="603ea-139">Maskintagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="603ea-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="603ea-140">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-140">string</span></span> | <span data-ttu-id="603ea-141">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="603ea-142">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-142">string</span></span> | <span data-ttu-id="603ea-143">Datorgruppen på datorn.</span><span class="sxs-lookup"><span data-stu-id="603ea-143">Machine group of the machine.</span></span> <span data-ttu-id="603ea-144">Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="603ea-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="603ea-145">long</span><span class="sxs-lookup"><span data-stu-id="603ea-145">long</span></span> | <span data-ttu-id="603ea-146">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="603ea-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="603ea-147">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="603ea-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="603ea-148">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-148">string</span></span> | <span data-ttu-id="603ea-149">Anger om enheten är onboarded eller inte i Microsoft Defender för Endpoint eller om enheten inte stöds</span><span class="sxs-lookup"><span data-stu-id="603ea-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="603ea-150">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-150">string</span></span> | <span data-ttu-id="603ea-151">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="603ea-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="603ea-152">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-152">string</span></span> | <span data-ttu-id="603ea-153">Bredare klassificering som grupperar vissa enhetstyper under följande kategorier: Slutpunkt, Nätverksenhet, IoT, Okänd</span><span class="sxs-lookup"><span data-stu-id="603ea-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="603ea-154">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-154">string</span></span> | <span data-ttu-id="603ea-155">Typ av enhet baserat på syfte och funktionalitet, till exempel nätverksenhet, arbetsstation, server, mobil, spelkonsol eller skrivare</span><span class="sxs-lookup"><span data-stu-id="603ea-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="603ea-156">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-156">string</span></span> | <span data-ttu-id="603ea-157">Ytterligare modifierare för vissa typer av enheter, till exempel kan en mobil enhet vara en surfplatta eller smartphone</span><span class="sxs-lookup"><span data-stu-id="603ea-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="603ea-158">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-158">string</span></span> | <span data-ttu-id="603ea-159">Modellnamn eller produktnummer från leverantören eller tillverkaren</span><span class="sxs-lookup"><span data-stu-id="603ea-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="603ea-160">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-160">string</span></span> | <span data-ttu-id="603ea-161">Namnet på produktleverantören eller tillverkaren</span><span class="sxs-lookup"><span data-stu-id="603ea-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="603ea-162">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-162">string</span></span> | <span data-ttu-id="603ea-163">Distribution av OS-plattformen, till exempel Ubuntu eller RedHat för Linux-plattformarna</span><span class="sxs-lookup"><span data-stu-id="603ea-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="603ea-164">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-164">string</span></span> | <span data-ttu-id="603ea-165">Ytterligare information om OS-versionen, till exempel populärt namn, kodnamn eller versionsnummer</span><span class="sxs-lookup"><span data-stu-id="603ea-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="603ea-166">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-166">string</span></span> | <span data-ttu-id="603ea-167">Tidigare enhets-ID som har tilldelats till samma enhet</span><span class="sxs-lookup"><span data-stu-id="603ea-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="603ea-168">sträng</span><span class="sxs-lookup"><span data-stu-id="603ea-168">string</span></span> | <span data-ttu-id="603ea-169">Det senaste enhets-ID:t som tilldelats en enhet</span><span class="sxs-lookup"><span data-stu-id="603ea-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="603ea-170">Tabellen `DeviceInfo` innehåller enhetsinformation baserad på hjärtslag, som är periodiska rapporter eller signaler från en enhet.</span><span class="sxs-lookup"><span data-stu-id="603ea-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="603ea-171">Var femtonde minut skickar enheten ett partiellt hjärtslag som innehåller ofta ändrar attribut som `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="603ea-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="603ea-172">En gång om dagen skickas ett fullständigt hjärtslag som innehåller enhetens attribut.</span><span class="sxs-lookup"><span data-stu-id="603ea-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="603ea-173">Du kan använda följande exempelfråga för att få den senaste statusen för en enhet:</span><span class="sxs-lookup"><span data-stu-id="603ea-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="603ea-174">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="603ea-174">Related topics</span></span>
- [<span data-ttu-id="603ea-175">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="603ea-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="603ea-176">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="603ea-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="603ea-177">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="603ea-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="603ea-178">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="603ea-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="603ea-179">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="603ea-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="603ea-180">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="603ea-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
