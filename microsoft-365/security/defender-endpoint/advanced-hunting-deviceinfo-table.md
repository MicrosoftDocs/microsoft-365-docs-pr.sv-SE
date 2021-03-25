---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Mer information om OS, datornamn och annan enhetsinformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceinfo, device, OS, platform, users, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075105"
---
# <a name="deviceinfo"></a><span data-ttu-id="492db-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="492db-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="492db-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="492db-105">**Applies to:**</span></span>
- [<span data-ttu-id="492db-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="492db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="492db-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="492db-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="492db-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="492db-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="492db-109">Tabellen i det avancerade sökschemat innehåller information om enheter i organisationen, bland annat `DeviceInfo` deras OS-version, aktiva användare och datornamn. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="492db-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="492db-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="492db-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="492db-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="492db-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="492db-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="492db-112">Column name</span></span> | <span data-ttu-id="492db-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="492db-113">Data type</span></span> | <span data-ttu-id="492db-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="492db-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="492db-115">datetime</span><span class="sxs-lookup"><span data-stu-id="492db-115">datetime</span></span> | <span data-ttu-id="492db-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="492db-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="492db-117">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-117">string</span></span> | <span data-ttu-id="492db-118">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="492db-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="492db-119">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-119">string</span></span> | <span data-ttu-id="492db-120">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="492db-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="492db-121">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-121">string</span></span> | <span data-ttu-id="492db-122">Version av slutpunktsagenten eller sensorn som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="492db-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="492db-123">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-123">string</span></span> | <span data-ttu-id="492db-124">Offentlig IP-adress som används av den onboarded enheten för att ansluta till Defender för Slutpunkt-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="492db-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="492db-125">Detta kan vara IP-adressen för enheten själv, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="492db-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="492db-126">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-126">string</span></span> | <span data-ttu-id="492db-127">Arkitekturen för operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="492db-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="492db-128">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-128">string</span></span> | <span data-ttu-id="492db-129">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="492db-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="492db-130">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="492db-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="492db-131">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-131">string</span></span> | <span data-ttu-id="492db-132">Version av operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="492db-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="492db-133">boolesk</span><span class="sxs-lookup"><span data-stu-id="492db-133">boolean</span></span> | <span data-ttu-id="492db-134">Boolesk indikator om enheten är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="492db-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="492db-135">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-135">string</span></span> | <span data-ttu-id="492db-136">Lista över alla användare som är inloggade på enheten vid tiden för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="492db-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="492db-137">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-137">string</span></span> | <span data-ttu-id="492db-138">Enhetstagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="492db-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="492db-139">long</span><span class="sxs-lookup"><span data-stu-id="492db-139">long</span></span> | <span data-ttu-id="492db-140">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="492db-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="492db-141">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="492db-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="492db-142">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-142">string</span></span> | <span data-ttu-id="492db-143">Version av operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="492db-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="492db-144">sträng</span><span class="sxs-lookup"><span data-stu-id="492db-144">string</span></span> | <span data-ttu-id="492db-145">Datorgruppen på datorn.</span><span class="sxs-lookup"><span data-stu-id="492db-145">Machine group of the machine.</span></span> <span data-ttu-id="492db-146">Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="492db-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="492db-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="492db-147">Related topics</span></span>
- [<span data-ttu-id="492db-148">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="492db-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="492db-149">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="492db-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="492db-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="492db-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
