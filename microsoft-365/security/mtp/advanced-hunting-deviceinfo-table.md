---
title: DeviceInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om operativsystem, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, machineinfo, DeviceInfo, enhet, maskin, OS, plattform Användare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 71bd9e9ff1dfb17e4a9266d9ee351799e18888c9
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811877"
---
# <a name="deviceinfo"></a><span data-ttu-id="53871-104">DeviceInfo (på plats)</span><span class="sxs-lookup"><span data-stu-id="53871-104">DeviceInfo</span></span>

<span data-ttu-id="53871-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="53871-105">**Applies to:**</span></span>
- <span data-ttu-id="53871-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="53871-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="53871-107">Tabellen `DeviceInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om datorer i organisationen, inklusive OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="53871-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="53871-108">Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="53871-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="53871-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="53871-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="53871-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="53871-110">Column name</span></span> | <span data-ttu-id="53871-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="53871-111">Data type</span></span> | <span data-ttu-id="53871-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="53871-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="53871-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="53871-113">datetime</span></span> | <span data-ttu-id="53871-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="53871-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="53871-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-115">string</span></span> | <span data-ttu-id="53871-116">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="53871-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="53871-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-117">string</span></span> | <span data-ttu-id="53871-118">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="53871-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="53871-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-119">string</span></span> | <span data-ttu-id="53871-120">Version av slutpunktsagenten eller sensorn som körs på maskinen</span><span class="sxs-lookup"><span data-stu-id="53871-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="53871-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-121">string</span></span> | <span data-ttu-id="53871-122">Offentlig IP-adress som används av den inbyggda datorn för att ansluta till Microsoft Defender ATP-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="53871-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="53871-123">Detta kan vara IP-adressen för själva maskinen, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="53871-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="53871-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-124">string</span></span> | <span data-ttu-id="53871-125">Arkitektur av operativsystemet som körs på maskinen</span><span class="sxs-lookup"><span data-stu-id="53871-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="53871-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-126">string</span></span> | <span data-ttu-id="53871-127">Plattformen för operativsystemet som körs på maskinen.</span><span class="sxs-lookup"><span data-stu-id="53871-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="53871-128">Detta anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="53871-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="53871-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-129">string</span></span> | <span data-ttu-id="53871-130">Skapa version av operativsystemet som körs på maskinen</span><span class="sxs-lookup"><span data-stu-id="53871-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="53871-131">Boolean</span><span class="sxs-lookup"><span data-stu-id="53871-131">boolean</span></span> | <span data-ttu-id="53871-132">Boolesk indikator på om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="53871-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="53871-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-133">string</span></span> | <span data-ttu-id="53871-134">Lista över alla användare som är inloggade på datorn vid tidpunkten för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="53871-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="53871-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-135">string</span></span> | <span data-ttu-id="53871-136">Maskintagg som lagts till via registret</span><span class="sxs-lookup"><span data-stu-id="53871-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="53871-137">Lång</span><span class="sxs-lookup"><span data-stu-id="53871-137">long</span></span> | <span data-ttu-id="53871-138">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="53871-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="53871-139">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="53871-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="53871-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-140">string</span></span> | <span data-ttu-id="53871-141">Version av operativsystemet som körs på maskinen</span><span class="sxs-lookup"><span data-stu-id="53871-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="53871-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="53871-142">string</span></span> | <span data-ttu-id="53871-143">Maskinens maskingrupp.</span><span class="sxs-lookup"><span data-stu-id="53871-143">Machine group of the machine.</span></span> <span data-ttu-id="53871-144">Den här gruppen används av rollbaserad åtkomstkontroll för att bestämma åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="53871-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="53871-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="53871-145">Related topics</span></span>
- [<span data-ttu-id="53871-146">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="53871-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="53871-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="53871-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="53871-148">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="53871-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="53871-149">Jaga hot mellan enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="53871-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="53871-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="53871-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="53871-151">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="53871-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
