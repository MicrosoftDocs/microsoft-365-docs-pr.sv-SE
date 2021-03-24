---
title: AlertInfo-tabell i det avancerade sökschemat
description: Läs mer om händelser för aviseringsgenerering i tabellen AlertInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, datatyp, description, AlertInfo, alert, severity, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bc81c9c8406a6e70df6ec38e3896ef9977a120e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071642"
---
# <a name="alertinfo"></a><span data-ttu-id="ec217-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="ec217-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec217-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ec217-105">**Applies to:**</span></span>
- <span data-ttu-id="ec217-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec217-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ec217-107">Tabellen i det avancerade sökschemat innehåller information om aviseringar från Microsoft Defender för Slutpunkt, Microsoft Defender för `AlertInfo` Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ec217-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="ec217-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="ec217-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ec217-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="ec217-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ec217-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="ec217-110">Column name</span></span> | <span data-ttu-id="ec217-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="ec217-111">Data type</span></span> | <span data-ttu-id="ec217-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ec217-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ec217-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ec217-113">datetime</span></span> | <span data-ttu-id="ec217-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="ec217-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="ec217-115">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-115">string</span></span> | <span data-ttu-id="ec217-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="ec217-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="ec217-117">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-117">string</span></span> | <span data-ttu-id="ec217-118">Aviseringens rubrik</span><span class="sxs-lookup"><span data-stu-id="ec217-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="ec217-119">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-119">string</span></span> | <span data-ttu-id="ec217-120">Typ av hotindikator eller intrångsaktivitet som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="ec217-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="ec217-121">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-121">string</span></span> | <span data-ttu-id="ec217-122">Anger den potentiella påverkan (hög, medium eller låg) av hotindikatorn eller intrångsaktiviteten som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="ec217-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="ec217-123">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-123">string</span></span> | <span data-ttu-id="ec217-124">Produkt eller tjänst som tillhandahöll aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="ec217-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="ec217-125">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-125">string</span></span> | <span data-ttu-id="ec217-126">Identifieringsteknik eller sensor som identifierat den märkbara komponenten eller aktiviteten</span><span class="sxs-lookup"><span data-stu-id="ec217-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="ec217-127">sträng</span><span class="sxs-lookup"><span data-stu-id="ec217-127">string</span></span> | <span data-ttu-id="ec217-128">MITRE ATT&CK-tekniker som är kopplade till aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="ec217-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ec217-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ec217-129">Related topics</span></span>
- [<span data-ttu-id="ec217-130">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ec217-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec217-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="ec217-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ec217-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="ec217-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ec217-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="ec217-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ec217-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="ec217-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ec217-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="ec217-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
