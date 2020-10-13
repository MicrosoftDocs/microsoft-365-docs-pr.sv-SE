---
title: AlertInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser för aviseringar i AlertInfo-tabellen för det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, varning, allvarlighets grad, kategori, MITRE, att&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
ms.openlocfilehash: 739ee33b162c1e701603a17e59f0d0c2611c064c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430181"
---
# <a name="alertinfo"></a><span data-ttu-id="7fe48-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="7fe48-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7fe48-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7fe48-105">**Applies to:**</span></span>
- <span data-ttu-id="7fe48-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7fe48-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7fe48-107">`AlertInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="7fe48-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="7fe48-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="7fe48-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7fe48-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7fe48-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7fe48-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="7fe48-110">Column name</span></span> | <span data-ttu-id="7fe48-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="7fe48-111">Data type</span></span> | <span data-ttu-id="7fe48-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7fe48-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7fe48-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7fe48-113">datetime</span></span> | <span data-ttu-id="7fe48-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="7fe48-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="7fe48-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-115">string</span></span> | <span data-ttu-id="7fe48-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="7fe48-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="7fe48-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-117">string</span></span> | <span data-ttu-id="7fe48-118">Aviseringens rubrik</span><span class="sxs-lookup"><span data-stu-id="7fe48-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="7fe48-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-119">string</span></span> | <span data-ttu-id="7fe48-120">Typ av hot indikator eller överträdelse aktivitet som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="7fe48-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="7fe48-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-121">string</span></span> | <span data-ttu-id="7fe48-122">Anger den potentiella effekten (hög, medel eller lågt) för hotets indikatorn eller överträdelse aktiviteten som identifieras av varningen</span><span class="sxs-lookup"><span data-stu-id="7fe48-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="7fe48-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-123">string</span></span> | <span data-ttu-id="7fe48-124">Produkt eller tjänst som tillhandahöll aviserings informationen</span><span class="sxs-lookup"><span data-stu-id="7fe48-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="7fe48-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-125">string</span></span> | <span data-ttu-id="7fe48-126">Identifierings teknik eller sensor som identifierar den mest viktiga komponenten eller aktiviteten</span><span class="sxs-lookup"><span data-stu-id="7fe48-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="7fe48-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="7fe48-127">string</span></span> | <span data-ttu-id="7fe48-128">MITRE to&CK tekniker som är kopplade till aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="7fe48-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fe48-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7fe48-129">Related topics</span></span>
- [<span data-ttu-id="7fe48-130">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7fe48-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fe48-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="7fe48-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fe48-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="7fe48-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7fe48-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="7fe48-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7fe48-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7fe48-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7fe48-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="7fe48-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
