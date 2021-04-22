---
title: AlertInfo-tabell i det avancerade sökschemat
description: Läs mer om händelser för aviseringsgenerering i tabellen AlertInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, varning, allvarlighetsgrad, kategori, MITRE, ATT&CK, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security, MCAS och Microsoft Defender för identitet
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933703"
---
# <a name="alertinfo"></a><span data-ttu-id="cc057-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="cc057-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cc057-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cc057-105">**Applies to:**</span></span>
- <span data-ttu-id="cc057-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc057-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="cc057-107">Tabellen i det avancerade sökschemat innehåller information om aviseringar från Microsoft Defender för Slutpunkt, Microsoft Defender för `AlertInfo` Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cc057-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="cc057-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="cc057-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="cc057-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="cc057-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cc057-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="cc057-110">Column name</span></span> | <span data-ttu-id="cc057-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="cc057-111">Data type</span></span> | <span data-ttu-id="cc057-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cc057-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cc057-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cc057-113">datetime</span></span> | <span data-ttu-id="cc057-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="cc057-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="cc057-115">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-115">string</span></span> | <span data-ttu-id="cc057-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="cc057-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="cc057-117">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-117">string</span></span> | <span data-ttu-id="cc057-118">Aviseringens rubrik</span><span class="sxs-lookup"><span data-stu-id="cc057-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="cc057-119">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-119">string</span></span> | <span data-ttu-id="cc057-120">Typ av hotindikator eller intrångsaktivitet som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="cc057-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="cc057-121">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-121">string</span></span> | <span data-ttu-id="cc057-122">Anger den potentiella påverkan (hög, medium eller låg) av hotindikatorn eller intrångsaktiviteten som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="cc057-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="cc057-123">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-123">string</span></span> | <span data-ttu-id="cc057-124">Produkt eller tjänst som tillhandahöll aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="cc057-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="cc057-125">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-125">string</span></span> | <span data-ttu-id="cc057-126">Identifieringsteknik eller sensor som identifierat den märkbara komponenten eller aktiviteten</span><span class="sxs-lookup"><span data-stu-id="cc057-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="cc057-127">sträng</span><span class="sxs-lookup"><span data-stu-id="cc057-127">string</span></span> | <span data-ttu-id="cc057-128">MITRE ATT&CK-tekniker som är kopplade till aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="cc057-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cc057-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="cc057-129">Related topics</span></span>
- [<span data-ttu-id="cc057-130">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="cc057-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cc057-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="cc057-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cc057-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="cc057-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cc057-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="cc057-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cc057-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="cc057-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cc057-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="cc057-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
