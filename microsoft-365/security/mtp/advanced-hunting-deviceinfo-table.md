---
title: DeviceInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om operativsystem, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, maskininfo, DeviceInfo, enhet, maskin, OS, plattform, användare
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
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899285"
---
# <a name="deviceinfo"></a><span data-ttu-id="d61d6-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="d61d6-104">DeviceInfo</span></span>

<span data-ttu-id="d61d6-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="d61d6-105">**Applies to:**</span></span>
- <span data-ttu-id="d61d6-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d61d6-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d61d6-107">`DeviceInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om datorer i organisationen, inklusive OS-version, aktiva användare och datornamn.</span><span class="sxs-lookup"><span data-stu-id="d61d6-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="d61d6-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="d61d6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="d61d6-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d61d6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d61d6-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d61d6-110">Column name</span></span> | <span data-ttu-id="d61d6-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d61d6-111">Data type</span></span> | <span data-ttu-id="d61d6-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d61d6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d61d6-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="d61d6-113">datetime</span></span> | <span data-ttu-id="d61d6-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="d61d6-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d61d6-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-115">string</span></span> | <span data-ttu-id="d61d6-116">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="d61d6-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d61d6-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-117">string</span></span> | <span data-ttu-id="d61d6-118">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="d61d6-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="d61d6-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-119">string</span></span> | <span data-ttu-id="d61d6-120">Version av slutpunktsagenten eller sensorn som körs på maskinen</span><span class="sxs-lookup"><span data-stu-id="d61d6-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="d61d6-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-121">string</span></span> | <span data-ttu-id="d61d6-122">Offentlig IP-adress som används av den inbyggda datorn för att ansluta till Microsoft Defender ATP-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d61d6-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="d61d6-123">Detta kan vara IP-adressen för själva maskinen, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="d61d6-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="d61d6-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-124">string</span></span> | <span data-ttu-id="d61d6-125">Arkitektur för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="d61d6-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="d61d6-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-126">string</span></span> | <span data-ttu-id="d61d6-127">Plattform för operativsystemet som körs på maskinen.</span><span class="sxs-lookup"><span data-stu-id="d61d6-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="d61d6-128">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="d61d6-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="d61d6-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-129">string</span></span> | <span data-ttu-id="d61d6-130">Skapa version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="d61d6-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="d61d6-131">Boolean</span><span class="sxs-lookup"><span data-stu-id="d61d6-131">boolean</span></span> | <span data-ttu-id="d61d6-132">Boolesk indikator på om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d61d6-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="d61d6-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-133">string</span></span> | <span data-ttu-id="d61d6-134">Lista över alla användare som är inloggade på datorn vid tidpunkten för händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="d61d6-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="d61d6-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-135">string</span></span> | <span data-ttu-id="d61d6-136">Maskintagg som lagts till i registret</span><span class="sxs-lookup"><span data-stu-id="d61d6-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="d61d6-137">Lång</span><span class="sxs-lookup"><span data-stu-id="d61d6-137">long</span></span> | <span data-ttu-id="d61d6-138">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="d61d6-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d61d6-139">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="d61d6-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="d61d6-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-140">string</span></span> | <span data-ttu-id="d61d6-141">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="d61d6-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="d61d6-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="d61d6-142">string</span></span> | <span data-ttu-id="d61d6-143">Maskinens maskingrupp.</span><span class="sxs-lookup"><span data-stu-id="d61d6-143">Machine group of the machine.</span></span> <span data-ttu-id="d61d6-144">Den här gruppen används av rollbaserad åtkomstkontroll för att fastställa åtkomst till datorn</span><span class="sxs-lookup"><span data-stu-id="d61d6-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d61d6-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d61d6-145">Related topics</span></span>
- [<span data-ttu-id="d61d6-146">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d61d6-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d61d6-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d61d6-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d61d6-148">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="d61d6-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d61d6-149">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d61d6-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d61d6-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d61d6-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d61d6-151">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="d61d6-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
