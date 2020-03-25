---
title: AlertInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om händelser för aviseringsgenerering i alertinfo-tabellen i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, allvarlighetsgrad, kategori, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929522"
---
# <a name="alertinfo"></a><span data-ttu-id="fb741-104">AlertInfo (varningInfo)</span><span class="sxs-lookup"><span data-stu-id="fb741-104">AlertInfo</span></span>

<span data-ttu-id="fb741-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="fb741-105">**Applies to:**</span></span>
- <span data-ttu-id="fb741-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="fb741-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="fb741-107">Tabellen `AlertInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="fb741-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="fb741-108">Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="fb741-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="fb741-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fb741-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fb741-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="fb741-110">Column name</span></span> | <span data-ttu-id="fb741-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="fb741-111">Data type</span></span> | <span data-ttu-id="fb741-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fb741-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="fb741-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="fb741-113">datetime</span></span> | <span data-ttu-id="fb741-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="fb741-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="fb741-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-115">string</span></span> | <span data-ttu-id="fb741-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="fb741-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="fb741-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-117">string</span></span> | <span data-ttu-id="fb741-118">Registreringens namn</span><span class="sxs-lookup"><span data-stu-id="fb741-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="fb741-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-119">string</span></span> | <span data-ttu-id="fb741-120">Typ av hotindikator eller överträdelseaktivitet som identifierats av registreringen</span><span class="sxs-lookup"><span data-stu-id="fb741-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="fb741-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-121">string</span></span> | <span data-ttu-id="fb741-122">Anger den potentiella påverkan (hög, medel eller låg) av hotindikatorn eller brottsaktiviteten som identifierats av</span><span class="sxs-lookup"><span data-stu-id="fb741-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="fb741-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-123">string</span></span> | <span data-ttu-id="fb741-124">Produkt eller tjänst som tillhandahöll varningsinformationen</span><span class="sxs-lookup"><span data-stu-id="fb741-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="fb741-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-125">string</span></span> | <span data-ttu-id="fb741-126">Detektionsteknik eller sensor som identifierade den anmärkningsvärda komponenten eller aktiviteten</span><span class="sxs-lookup"><span data-stu-id="fb741-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="fb741-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="fb741-127">string</span></span> | <span data-ttu-id="fb741-128">MITRE ATT&CK-tekniker som är associerade med aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="fb741-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fb741-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fb741-129">Related topics</span></span>
- [<span data-ttu-id="fb741-130">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="fb741-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fb741-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="fb741-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fb741-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="fb741-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fb741-133">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="fb741-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fb741-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="fb741-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fb741-135">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="fb741-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
