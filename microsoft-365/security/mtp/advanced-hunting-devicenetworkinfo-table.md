---
title: DeviceNetworkInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om information om nätverkskonfiguration i tabellen DeviceNetworkInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, maskin, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 0fd6000f4d3a4b9fafb0eede74cbbe4e6c3d494e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899249"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="c8df9-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="c8df9-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="c8df9-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c8df9-105">**Applies to:**</span></span>
- <span data-ttu-id="c8df9-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c8df9-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c8df9-107">`DeviceNetworkInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av datorer, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner.</span><span class="sxs-lookup"><span data-stu-id="c8df9-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="c8df9-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="c8df9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c8df9-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c8df9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c8df9-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="c8df9-110">Column name</span></span> | <span data-ttu-id="c8df9-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="c8df9-111">Data type</span></span> | <span data-ttu-id="c8df9-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8df9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c8df9-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="c8df9-113">datetime</span></span> | <span data-ttu-id="c8df9-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="c8df9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c8df9-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-115">string</span></span> | <span data-ttu-id="c8df9-116">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="c8df9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c8df9-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-117">string</span></span> | <span data-ttu-id="c8df9-118">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="c8df9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="c8df9-119">Lång</span><span class="sxs-lookup"><span data-stu-id="c8df9-119">long</span></span> | <span data-ttu-id="c8df9-120">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="c8df9-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c8df9-121">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="c8df9-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="c8df9-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-122">string</span></span> | <span data-ttu-id="c8df9-123">Nätverkskortets namn</span><span class="sxs-lookup"><span data-stu-id="c8df9-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="c8df9-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-124">string</span></span> | <span data-ttu-id="c8df9-125">MAC-adressen till nätverkskortet</span><span class="sxs-lookup"><span data-stu-id="c8df9-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="c8df9-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-126">string</span></span> | <span data-ttu-id="c8df9-127">Typ av nätverkskort.</span><span class="sxs-lookup"><span data-stu-id="c8df9-127">Network adapter type.</span></span> <span data-ttu-id="c8df9-128">För möjliga värden, se [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="c8df9-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="c8df9-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-129">string</span></span> | <span data-ttu-id="c8df9-130">Nätverkskortets driftstatus.</span><span class="sxs-lookup"><span data-stu-id="c8df9-130">Operational status of the network adapter.</span></span> <span data-ttu-id="c8df9-131">För möjliga värden, se [denna uppräkning](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="c8df9-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="c8df9-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-132">string</span></span> | <span data-ttu-id="c8df9-133">Tunnelprotokoll, om gränssnittet används för detta ändamål, till exempel 6to4, Teredo, ISATAP, PPTP, SSTP och SSH</span><span class="sxs-lookup"><span data-stu-id="c8df9-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="c8df9-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-134">string</span></span> | <span data-ttu-id="c8df9-135">Nätverk som kortet är anslutet till.</span><span class="sxs-lookup"><span data-stu-id="c8df9-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="c8df9-136">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till internet</span><span class="sxs-lookup"><span data-stu-id="c8df9-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="c8df9-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-137">string</span></span> | <span data-ttu-id="c8df9-138">DNS-serveradresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="c8df9-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="c8df9-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-139">string</span></span> | <span data-ttu-id="c8df9-140">IPv4-adress för DHCP-servern</span><span class="sxs-lookup"><span data-stu-id="c8df9-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="c8df9-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-141">string</span></span> | <span data-ttu-id="c8df9-142">IPv6-adress för DHCP-servern</span><span class="sxs-lookup"><span data-stu-id="c8df9-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="c8df9-143">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-143">string</span></span> | <span data-ttu-id="c8df9-144">Standardgatewayadresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="c8df9-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="c8df9-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="c8df9-145">string</span></span> | <span data-ttu-id="c8df9-146">JSON-matris som innehåller alla IP-adresser som tilldelats kortet, tillsammans med deras respektive prefix för undernät och IP-adressutrymme, till exempel offentliga, privata eller länklokala</span><span class="sxs-lookup"><span data-stu-id="c8df9-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c8df9-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c8df9-147">Related topics</span></span>
- [<span data-ttu-id="c8df9-148">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c8df9-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c8df9-149">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c8df9-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c8df9-150">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="c8df9-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c8df9-151">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c8df9-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c8df9-152">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c8df9-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c8df9-153">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c8df9-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
