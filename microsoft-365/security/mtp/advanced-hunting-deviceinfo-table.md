---
title: DeviceInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om operativ system, dator namn och annan information om datorn i DeviceInfo-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, machineinfo, DeviceInfo, enhet, maskin, OS, plattform, användare
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1fa093798b4e7704d5c6c5368dce7cb4081df48b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413240"
---
# <a name="deviceinfo"></a><span data-ttu-id="08fb1-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="08fb1-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08fb1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="08fb1-105">**Applies to:**</span></span>
- <span data-ttu-id="08fb1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="08fb1-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="08fb1-107">`DeviceInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om datorerna i organisationen, inklusive OS-version, aktiva användare och dator namn.</span><span class="sxs-lookup"><span data-stu-id="08fb1-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="08fb1-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="08fb1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="08fb1-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="08fb1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="08fb1-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="08fb1-110">Column name</span></span> | <span data-ttu-id="08fb1-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="08fb1-111">Data type</span></span> | <span data-ttu-id="08fb1-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="08fb1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="08fb1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="08fb1-113">datetime</span></span> | <span data-ttu-id="08fb1-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="08fb1-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="08fb1-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-115">string</span></span> | <span data-ttu-id="08fb1-116">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="08fb1-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="08fb1-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-117">string</span></span> | <span data-ttu-id="08fb1-118">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="08fb1-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-119">string</span></span> | <span data-ttu-id="08fb1-120">Version av slut punkts agenten eller sensorn som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="08fb1-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-121">string</span></span> | <span data-ttu-id="08fb1-122">Offentlig IP-adress som används av den inbyggda datorn för att ansluta till Microsoft Defender ATP-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="08fb1-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="08fb1-123">Det här kan vara IP-adressen till själva datorn, en NAT-enhet eller en proxy</span><span class="sxs-lookup"><span data-stu-id="08fb1-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="08fb1-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-124">string</span></span> | <span data-ttu-id="08fb1-125">Arkitekturen för operativ systemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="08fb1-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-126">string</span></span> | <span data-ttu-id="08fb1-127">Plattformen för det operativ system som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="08fb1-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="08fb1-128">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7</span><span class="sxs-lookup"><span data-stu-id="08fb1-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="08fb1-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-129">string</span></span> | <span data-ttu-id="08fb1-130">Version av operativ systemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="08fb1-131">returtyp</span><span class="sxs-lookup"><span data-stu-id="08fb1-131">boolean</span></span> | <span data-ttu-id="08fb1-132">Boolesk indikator för om datorn är ansluten till Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="08fb1-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="08fb1-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-133">string</span></span> | <span data-ttu-id="08fb1-134">Lista över alla användare som är inloggade på datorn när händelsen inträffar i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="08fb1-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="08fb1-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-135">string</span></span> | <span data-ttu-id="08fb1-136">Dator tag gen läggs till genom registret</span><span class="sxs-lookup"><span data-stu-id="08fb1-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="08fb1-137">tids</span><span class="sxs-lookup"><span data-stu-id="08fb1-137">long</span></span> | <span data-ttu-id="08fb1-138">Händelse identifierare baserad på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="08fb1-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="08fb1-139">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="08fb1-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="08fb1-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-140">string</span></span> | <span data-ttu-id="08fb1-141">Version av operativ systemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="08fb1-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="08fb1-142">string</span></span> | <span data-ttu-id="08fb1-143">Dator grupp.</span><span class="sxs-lookup"><span data-stu-id="08fb1-143">Machine group of the machine.</span></span> <span data-ttu-id="08fb1-144">Den här gruppen används av rollbaserad åtkomst kontroll för att bestämma åtkomst till datorn</span><span class="sxs-lookup"><span data-stu-id="08fb1-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="08fb1-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="08fb1-145">Related topics</span></span>
- [<span data-ttu-id="08fb1-146">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="08fb1-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="08fb1-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="08fb1-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="08fb1-148">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="08fb1-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="08fb1-149">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="08fb1-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="08fb1-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="08fb1-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="08fb1-151">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="08fb1-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
