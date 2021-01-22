---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Läs mer om OS, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, maskininfo, Enhetsinfo, enhet, dator, OS, plattform, användare
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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931284"
---
# <a name="deviceinfo"></a><span data-ttu-id="4833f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="4833f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4833f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4833f-105">**Applies to:**</span></span>
- <span data-ttu-id="4833f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4833f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4833f-107">Tabellen `DeviceInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om maskiner i organisationen, inklusive OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="4833f-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="4833f-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="4833f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4833f-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4833f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4833f-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="4833f-110">Column name</span></span> | <span data-ttu-id="4833f-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4833f-111">Data type</span></span> | <span data-ttu-id="4833f-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4833f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4833f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4833f-113">datetime</span></span> | <span data-ttu-id="4833f-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="4833f-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4833f-115">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-115">string</span></span> | <span data-ttu-id="4833f-116">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="4833f-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4833f-117">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-117">string</span></span> | <span data-ttu-id="4833f-118">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="4833f-119">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-119">string</span></span> | <span data-ttu-id="4833f-120">Version av slutpunktsagenten eller sensorn som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="4833f-121">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-121">string</span></span> | <span data-ttu-id="4833f-122">Offentlig IP-adress som används av den onboarded machine för att ansluta till Tjänsten Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="4833f-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="4833f-123">Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="4833f-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="4833f-124">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-124">string</span></span> | <span data-ttu-id="4833f-125">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="4833f-126">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-126">string</span></span> | <span data-ttu-id="4833f-127">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="4833f-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="4833f-128">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="4833f-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="4833f-129">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-129">string</span></span> | <span data-ttu-id="4833f-130">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="4833f-131">boolesk</span><span class="sxs-lookup"><span data-stu-id="4833f-131">boolean</span></span> | <span data-ttu-id="4833f-132">Boolesk indikator om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4833f-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="4833f-133">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-133">string</span></span> | <span data-ttu-id="4833f-134">Lista över alla användare som är inloggade på datorn vid tidpunkten för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="4833f-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="4833f-135">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-135">string</span></span> | <span data-ttu-id="4833f-136">Maskintagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="4833f-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="4833f-137">long</span><span class="sxs-lookup"><span data-stu-id="4833f-137">long</span></span> | <span data-ttu-id="4833f-138">Händelseidentifierare baserade på en återkommande räknare.</span><span class="sxs-lookup"><span data-stu-id="4833f-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4833f-139">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="4833f-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="4833f-140">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-140">string</span></span> | <span data-ttu-id="4833f-141">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="4833f-142">sträng</span><span class="sxs-lookup"><span data-stu-id="4833f-142">string</span></span> | <span data-ttu-id="4833f-143">Datorgruppen på datorn.</span><span class="sxs-lookup"><span data-stu-id="4833f-143">Machine group of the machine.</span></span> <span data-ttu-id="4833f-144">Den här gruppen används av rollbaserad åtkomstkontroll för att fastställa åtkomsten till datorn</span><span class="sxs-lookup"><span data-stu-id="4833f-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4833f-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4833f-145">Related topics</span></span>
- [<span data-ttu-id="4833f-146">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="4833f-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4833f-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="4833f-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4833f-148">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="4833f-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4833f-149">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="4833f-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4833f-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="4833f-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4833f-151">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="4833f-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
