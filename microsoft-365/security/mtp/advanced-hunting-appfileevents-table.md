---
title: AppFileEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser som är associerade med molnappar och molntjänster i tabellen AppFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899345"
---
# <a name="appfileevents"></a><span data-ttu-id="f409e-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f409e-104">AppFileEvents</span></span>

<span data-ttu-id="f409e-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="f409e-105">**Applies to:**</span></span>
- <span data-ttu-id="f409e-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="f409e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f409e-107">`AppFileEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="f409e-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f409e-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="f409e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f409e-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f409e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f409e-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="f409e-110">Column name</span></span> | <span data-ttu-id="f409e-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="f409e-111">Data type</span></span> | <span data-ttu-id="f409e-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f409e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f409e-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="f409e-113">datetime</span></span> | <span data-ttu-id="f409e-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="f409e-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f409e-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-115">string</span></span> | <span data-ttu-id="f409e-116">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="f409e-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="f409e-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-117">string</span></span> | <span data-ttu-id="f409e-118">Ansökan som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="f409e-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="f409e-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-119">string</span></span> | <span data-ttu-id="f409e-120">Namnet på den fil som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="f409e-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f409e-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-121">string</span></span> | <span data-ttu-id="f409e-122">Mapp som innehåller filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="f409e-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="f409e-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-123">string</span></span> | <span data-ttu-id="f409e-124">Det ursprungliga namnet på filen som har bytt namn till följd av åtgärden</span><span class="sxs-lookup"><span data-stu-id="f409e-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="f409e-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-125">string</span></span> | <span data-ttu-id="f409e-126">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="f409e-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f409e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-127">string</span></span> | <span data-ttu-id="f409e-128">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="f409e-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f409e-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-129">string</span></span> | <span data-ttu-id="f409e-130">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="f409e-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f409e-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-131">string</span></span> | <span data-ttu-id="f409e-132">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="f409e-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f409e-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-133">string</span></span> | <span data-ttu-id="f409e-134">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="f409e-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f409e-135">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="f409e-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="f409e-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-136">string</span></span> | <span data-ttu-id="f409e-137">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="f409e-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="f409e-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="f409e-138">string</span></span> | <span data-ttu-id="f409e-139">Ort, land eller annan geografisk plats som är associerad med händelsen</span><span class="sxs-lookup"><span data-stu-id="f409e-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f409e-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f409e-140">Related topics</span></span>
- [<span data-ttu-id="f409e-141">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f409e-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f409e-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="f409e-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f409e-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="f409e-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f409e-144">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="f409e-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f409e-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="f409e-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f409e-146">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="f409e-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
