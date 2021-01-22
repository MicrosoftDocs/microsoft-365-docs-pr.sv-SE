---
title: AlertInfo-tabell i det avancerade sökschemat
description: Läs mer om aviseringsgenereringshändelser i tabellen AlertInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning på cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, varning, allvarlighetsgrad, kategori, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929976"
---
# <a name="alertinfo"></a><span data-ttu-id="1d7dd-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="1d7dd-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d7dd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1d7dd-105">**Applies to:**</span></span>
- <span data-ttu-id="1d7dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d7dd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="1d7dd-107">Tabellen i det avancerade utbildningsschemat innehåller information om aviseringar från Microsoft Defender för Slutpunkt, Microsoft Defender för `AlertInfo` Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1d7dd-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="1d7dd-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="1d7dd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="1d7dd-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="1d7dd-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1d7dd-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="1d7dd-110">Column name</span></span> | <span data-ttu-id="1d7dd-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="1d7dd-111">Data type</span></span> | <span data-ttu-id="1d7dd-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d7dd-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1d7dd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1d7dd-113">datetime</span></span> | <span data-ttu-id="1d7dd-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="1d7dd-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="1d7dd-115">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-115">string</span></span> | <span data-ttu-id="1d7dd-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="1d7dd-117">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-117">string</span></span> | <span data-ttu-id="1d7dd-118">Aviseringens rubrik</span><span class="sxs-lookup"><span data-stu-id="1d7dd-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="1d7dd-119">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-119">string</span></span> | <span data-ttu-id="1d7dd-120">Typ av hotindikator eller intrångsaktivitet som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="1d7dd-121">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-121">string</span></span> | <span data-ttu-id="1d7dd-122">Anger den potentiella påverkan (hög, medium eller låg) av hotindikatorn eller intrångsaktiviteten som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="1d7dd-123">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-123">string</span></span> | <span data-ttu-id="1d7dd-124">Produkt eller tjänst som tillhandahållit aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="1d7dd-125">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-125">string</span></span> | <span data-ttu-id="1d7dd-126">Identifieringsteknik eller sensor som identifierat den märkbara komponenten eller aktiviteten</span><span class="sxs-lookup"><span data-stu-id="1d7dd-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="1d7dd-127">sträng</span><span class="sxs-lookup"><span data-stu-id="1d7dd-127">string</span></span> | <span data-ttu-id="1d7dd-128">MITRE ATT&CK-tekniker som är associerade med aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1d7dd-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1d7dd-129">Related topics</span></span>
- [<span data-ttu-id="1d7dd-130">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1d7dd-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1d7dd-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="1d7dd-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1d7dd-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="1d7dd-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1d7dd-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="1d7dd-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1d7dd-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="1d7dd-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1d7dd-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="1d7dd-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
