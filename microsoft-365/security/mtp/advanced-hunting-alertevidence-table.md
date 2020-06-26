---
title: AlertEvidence-tabellen i det avancerade jaktschemat
description: Lär dig mer om fil-, nätverksadress-, användar- eller enhetsinformation som är associerad med genererade aviseringar i tabellen AlertEvidence i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, enheter, bevis, fil, IP-adress, enhet, maskin, användare, konto
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
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899357"
---
# <a name="alertevidence"></a><span data-ttu-id="a9777-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a9777-104">AlertEvidence</span></span>

<span data-ttu-id="a9777-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="a9777-105">**Applies to:**</span></span>
- <span data-ttu-id="a9777-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="a9777-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a9777-107">`AlertEvidence`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om olika entiteter – filer, IP-adresser, webbadresser, användare eller enheter – som är associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="a9777-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a9777-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="a9777-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a9777-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a9777-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a9777-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="a9777-110">Column name</span></span> | <span data-ttu-id="a9777-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="a9777-111">Data type</span></span> | <span data-ttu-id="a9777-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a9777-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a9777-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="a9777-113">datetime</span></span> | <span data-ttu-id="a9777-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="a9777-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="a9777-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-115">string</span></span> | <span data-ttu-id="a9777-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="a9777-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="a9777-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-117">string</span></span> | <span data-ttu-id="a9777-118">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="a9777-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="a9777-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-119">string</span></span> | <span data-ttu-id="a9777-120">Hur företaget deltar i en registrering, som anger om den påverkas eller endast är relaterad till</span><span class="sxs-lookup"><span data-stu-id="a9777-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="a9777-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-121">string</span></span> | <span data-ttu-id="a9777-122">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="a9777-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="a9777-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-123">string</span></span> | <span data-ttu-id="a9777-124">SHA-256 i filen som den inspelade åtgärden tillämpades på.</span><span class="sxs-lookup"><span data-stu-id="a9777-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="a9777-125">Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="a9777-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="a9777-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-126">string</span></span> | <span data-ttu-id="a9777-127">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="a9777-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="a9777-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-128">string</span></span> | <span data-ttu-id="a9777-129">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="a9777-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="a9777-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-130">string</span></span> | <span data-ttu-id="a9777-131">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="a9777-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a9777-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-132">string</span></span> | <span data-ttu-id="a9777-133">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="a9777-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="a9777-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-134">string</span></span> | <span data-ttu-id="a9777-135">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="a9777-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="a9777-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-136">string</span></span> | <span data-ttu-id="a9777-137">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9777-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="a9777-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-138">string</span></span> | <span data-ttu-id="a9777-139">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="a9777-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="a9777-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-140">string</span></span> | <span data-ttu-id="a9777-141">Malware familj att den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="a9777-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="a9777-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-142">string</span></span> | <span data-ttu-id="a9777-143">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="a9777-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="a9777-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="a9777-144">string</span></span> | <span data-ttu-id="a9777-145">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="a9777-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a9777-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a9777-146">Related topics</span></span>
- [<span data-ttu-id="a9777-147">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="a9777-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a9777-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="a9777-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a9777-149">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="a9777-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a9777-150">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="a9777-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a9777-151">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="a9777-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a9777-152">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="a9777-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
