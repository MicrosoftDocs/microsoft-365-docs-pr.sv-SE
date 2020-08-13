---
title: AlertEvidence-tabell i det avancerade jakt-schemat
description: Lär dig mer om fil-, nätverks adress-, användar-eller enhets information som är kopplad till genererade aviseringar i AlertEvidence-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto
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
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649517"
---
# <a name="alertevidence"></a><span data-ttu-id="d4eb1-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="d4eb1-104">AlertEvidence</span></span>

<span data-ttu-id="d4eb1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d4eb1-105">**Applies to:**</span></span>
- <span data-ttu-id="d4eb1-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d4eb1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d4eb1-107">`AlertEvidence`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika enheter — filer, IP-adresser, URL: er, användare eller enheter – associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="d4eb1-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="d4eb1-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="d4eb1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="d4eb1-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d4eb1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d4eb1-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d4eb1-110">Column name</span></span> | <span data-ttu-id="d4eb1-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d4eb1-111">Data type</span></span> | <span data-ttu-id="d4eb1-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d4eb1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d4eb1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d4eb1-113">datetime</span></span> | <span data-ttu-id="d4eb1-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="d4eb1-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="d4eb1-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-115">string</span></span> | <span data-ttu-id="d4eb1-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="d4eb1-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="d4eb1-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-117">string</span></span> | <span data-ttu-id="d4eb1-118">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="d4eb1-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="d4eb1-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-119">string</span></span> | <span data-ttu-id="d4eb1-120">Hur enheten är involverad i en avisering och visar om den påverkas eller bara är relaterad</span><span class="sxs-lookup"><span data-stu-id="d4eb1-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="d4eb1-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-121">string</span></span> | <span data-ttu-id="d4eb1-122">SHA-1 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="d4eb1-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="d4eb1-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-123">string</span></span> | <span data-ttu-id="d4eb1-124">SHA-256 av filen som den registrerade åtgärden tillämpades på.</span><span class="sxs-lookup"><span data-stu-id="d4eb1-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="d4eb1-125">Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="d4eb1-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="d4eb1-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-126">string</span></span> | <span data-ttu-id="d4eb1-127">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="d4eb1-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="d4eb1-128">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-128">string</span></span> | <span data-ttu-id="d4eb1-129">URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till</span><span class="sxs-lookup"><span data-stu-id="d4eb1-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="d4eb1-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-130">string</span></span> | <span data-ttu-id="d4eb1-131">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="d4eb1-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="d4eb1-132">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-132">string</span></span> | <span data-ttu-id="d4eb1-133">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="d4eb1-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="d4eb1-134">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-134">string</span></span> | <span data-ttu-id="d4eb1-135">Kontots säkerhets identifierare (SID)</span><span class="sxs-lookup"><span data-stu-id="d4eb1-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="d4eb1-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-136">string</span></span> | <span data-ttu-id="d4eb1-137">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4eb1-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="d4eb1-138">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-138">string</span></span> | <span data-ttu-id="d4eb1-139">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="d4eb1-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="d4eb1-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-140">string</span></span> | <span data-ttu-id="d4eb1-141">Familjen skadlig program vara som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="d4eb1-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="d4eb1-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-142">string</span></span> | <span data-ttu-id="d4eb1-143">Anger om enheten är källa eller mål för en nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="d4eb1-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="d4eb1-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="d4eb1-144">string</span></span> | <span data-ttu-id="d4eb1-145">Ytterligare information om händelsen i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="d4eb1-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d4eb1-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d4eb1-146">Related topics</span></span>
- [<span data-ttu-id="d4eb1-147">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d4eb1-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4eb1-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d4eb1-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4eb1-149">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="d4eb1-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d4eb1-150">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="d4eb1-150">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d4eb1-151">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d4eb1-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4eb1-152">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="d4eb1-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
