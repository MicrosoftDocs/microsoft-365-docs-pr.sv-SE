---
title: DeviceNetworkInfo-tabell i det avancerade sökschemat
description: Läs mer om information om nätverkskonfiguration i tabellen DeviceNetworkInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, dator, mac, ip, adapter, dns, gateway, tunnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931212"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="4e075-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="4e075-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4e075-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4e075-105">**Applies to:**</span></span>
- <span data-ttu-id="4e075-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e075-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4e075-107">Tabellen `DeviceNetworkInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om nätverkskonfiguration av maskiner, inklusive nätverkskort, IP- och MAC-adresser och anslutna nätverk eller domäner.</span><span class="sxs-lookup"><span data-stu-id="4e075-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="4e075-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="4e075-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4e075-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4e075-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4e075-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="4e075-110">Column name</span></span> | <span data-ttu-id="4e075-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4e075-111">Data type</span></span> | <span data-ttu-id="4e075-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4e075-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4e075-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4e075-113">datetime</span></span> | <span data-ttu-id="4e075-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="4e075-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4e075-115">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-115">string</span></span> | <span data-ttu-id="4e075-116">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="4e075-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4e075-117">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-117">string</span></span> | <span data-ttu-id="4e075-118">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="4e075-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="4e075-119">long</span><span class="sxs-lookup"><span data-stu-id="4e075-119">long</span></span> | <span data-ttu-id="4e075-120">Händelseidentifierare baserade på en återkommande räknare.</span><span class="sxs-lookup"><span data-stu-id="4e075-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4e075-121">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="4e075-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="4e075-122">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-122">string</span></span> | <span data-ttu-id="4e075-123">Namn på nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="4e075-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="4e075-124">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-124">string</span></span> | <span data-ttu-id="4e075-125">MAC-adressen för nätverksadaptern</span><span class="sxs-lookup"><span data-stu-id="4e075-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="4e075-126">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-126">string</span></span> | <span data-ttu-id="4e075-127">Nätverksadaptertyp.</span><span class="sxs-lookup"><span data-stu-id="4e075-127">Network adapter type.</span></span> <span data-ttu-id="4e075-128">Referera till den här uppräkningen [för möjliga värden](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="4e075-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="4e075-129">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-129">string</span></span> | <span data-ttu-id="4e075-130">Driftstatus för nätverksadaptern.</span><span class="sxs-lookup"><span data-stu-id="4e075-130">Operational status of the network adapter.</span></span> <span data-ttu-id="4e075-131">Referera till den här uppräkningen [för möjliga värden](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="4e075-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="4e075-132">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-132">string</span></span> | <span data-ttu-id="4e075-133">Tunnelprotokoll, om gränssnittet används för detta ändamål, till exempel 6to4,Certifikatedo, ISATAP, PPTP, SSTP och SSH</span><span class="sxs-lookup"><span data-stu-id="4e075-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="4e075-134">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-134">string</span></span> | <span data-ttu-id="4e075-135">Nätverk som adaptern är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="4e075-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="4e075-136">Varje JSON-matris innehåller nätverksnamn, kategori (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="4e075-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="4e075-137">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-137">string</span></span> | <span data-ttu-id="4e075-138">DNS-serveradresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="4e075-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="4e075-139">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-139">string</span></span> | <span data-ttu-id="4e075-140">IPv4-adressen till DEN HÄR SERVERN</span><span class="sxs-lookup"><span data-stu-id="4e075-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="4e075-141">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-141">string</span></span> | <span data-ttu-id="4e075-142">IPv6-adressen till DEN HÄR SERVERN</span><span class="sxs-lookup"><span data-stu-id="4e075-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="4e075-143">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-143">string</span></span> | <span data-ttu-id="4e075-144">Standardgatewayadresser i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="4e075-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="4e075-145">sträng</span><span class="sxs-lookup"><span data-stu-id="4e075-145">string</span></span> | <span data-ttu-id="4e075-146">JSON-matris som innehåller alla IP-adresser som tilldelats adaptern, tillsammans med respektive undernätsprefix och IP-adressutrymme, till exempel offentliga, privata eller länk-lokala</span><span class="sxs-lookup"><span data-stu-id="4e075-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4e075-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4e075-147">Related topics</span></span>
- [<span data-ttu-id="4e075-148">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="4e075-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4e075-149">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="4e075-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4e075-150">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="4e075-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4e075-151">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="4e075-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4e075-152">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="4e075-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4e075-153">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="4e075-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
