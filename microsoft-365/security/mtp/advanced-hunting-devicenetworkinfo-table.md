---
title: DeviceNetworkInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om nätverks konfigurations information i tabellen DeviceNetworkInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, machinenetworkinfo, DeviceNetworkInfo, enhet, dator, Mac, IP, adapter, DNS, DHCP, Gateway, tunnel
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 36edb4c1da63949b1ec8b914f831c1c5d36b7c7c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429925"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="31928-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="31928-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="31928-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="31928-105">**Applies to:**</span></span>
- <span data-ttu-id="31928-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="31928-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="31928-107">`DeviceNetworkInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om nätverks konfiguration för datorer, inklusive nätverkskort, IP-adresser och Mac-adress samt anslutna nätverk eller domäner.</span><span class="sxs-lookup"><span data-stu-id="31928-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="31928-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="31928-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="31928-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="31928-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="31928-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="31928-110">Column name</span></span> | <span data-ttu-id="31928-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="31928-111">Data type</span></span> | <span data-ttu-id="31928-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="31928-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="31928-113">datetime</span><span class="sxs-lookup"><span data-stu-id="31928-113">datetime</span></span> | <span data-ttu-id="31928-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="31928-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="31928-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-115">string</span></span> | <span data-ttu-id="31928-116">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="31928-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="31928-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-117">string</span></span> | <span data-ttu-id="31928-118">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="31928-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="31928-119">tids</span><span class="sxs-lookup"><span data-stu-id="31928-119">long</span></span> | <span data-ttu-id="31928-120">Händelse identifierare baserad på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="31928-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="31928-121">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="31928-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="31928-122">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-122">string</span></span> | <span data-ttu-id="31928-123">Namn på nätverkskortet</span><span class="sxs-lookup"><span data-stu-id="31928-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="31928-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-124">string</span></span> | <span data-ttu-id="31928-125">MAC-adress för nätverkskortet</span><span class="sxs-lookup"><span data-stu-id="31928-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="31928-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-126">string</span></span> | <span data-ttu-id="31928-127">Typ av nätverkskort.</span><span class="sxs-lookup"><span data-stu-id="31928-127">Network adapter type.</span></span> <span data-ttu-id="31928-128">För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="31928-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="31928-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-129">string</span></span> | <span data-ttu-id="31928-130">Drift status för nätverkskortet.</span><span class="sxs-lookup"><span data-stu-id="31928-130">Operational status of the network adapter.</span></span> <span data-ttu-id="31928-131">För möjliga värden, se [den här uppräkningen](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="31928-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="31928-132">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-132">string</span></span> | <span data-ttu-id="31928-133">Tunnel protokoll, om gränssnittet används för detta ändamål, till exempel 6to4, Teredo, ISATAP, PPTP, SSTP och SSH</span><span class="sxs-lookup"><span data-stu-id="31928-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="31928-134">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-134">string</span></span> | <span data-ttu-id="31928-135">Nätverk som adaptern är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="31928-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="31928-136">Varje JSON-matris innehåller nätverks namnet, kategorin (offentlig, privat eller domän), en beskrivning och en flagga som anger om den är ansluten offentligt till Internet</span><span class="sxs-lookup"><span data-stu-id="31928-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="31928-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-137">string</span></span> | <span data-ttu-id="31928-138">DNS-serveradresser i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="31928-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="31928-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-139">string</span></span> | <span data-ttu-id="31928-140">IPv4-adress för DHCP-server</span><span class="sxs-lookup"><span data-stu-id="31928-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="31928-141">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-141">string</span></span> | <span data-ttu-id="31928-142">IPv6-adress för DHCP-server</span><span class="sxs-lookup"><span data-stu-id="31928-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="31928-143">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-143">string</span></span> | <span data-ttu-id="31928-144">Standardgateway-adresser i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="31928-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="31928-145">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="31928-145">string</span></span> | <span data-ttu-id="31928-146">JSON-matris som innehåller alla IP-adresser som tilldelats kortet samt deras respektive prefix och IP-adressutrymmet, till exempel offentligt, privat eller länk-lokal</span><span class="sxs-lookup"><span data-stu-id="31928-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="31928-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="31928-147">Related topics</span></span>
- [<span data-ttu-id="31928-148">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="31928-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="31928-149">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="31928-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="31928-150">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="31928-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="31928-151">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="31928-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="31928-152">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="31928-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="31928-153">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="31928-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
