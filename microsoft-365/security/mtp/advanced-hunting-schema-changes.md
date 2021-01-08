---
title: Namnge ändringar i Microsoft 365 Defender Advanced jakt-schemat
description: Spåra och granska namn ändrings tabeller och kolumner i det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, data, namn ändringar, Byt namn, Microsoft Threat Protection
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780827"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="d22de-104">Avancerat schema för att ändra namn på ändringar</span><span class="sxs-lookup"><span data-stu-id="d22de-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d22de-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d22de-105">**Applies to:**</span></span>
- <span data-ttu-id="d22de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d22de-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d22de-107">Det [avancerade jakt schemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="d22de-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="d22de-108">I vissa fall byts namn på befintliga kolumn namn eller ersättas för att förbättra användar upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="d22de-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="d22de-109">I den här artikeln finns information om hur du granskar namn ändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="d22de-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="d22de-110">Namn ändringar används automatiskt för frågor som sparas i säkerhets Center, inklusive frågor som används av anpassade identifierings regler.</span><span class="sxs-lookup"><span data-stu-id="d22de-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="d22de-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="d22de-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="d22de-112">Men du måste uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="d22de-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="d22de-113">Frågor som körs med API</span><span class="sxs-lookup"><span data-stu-id="d22de-113">Queries that are run using the API</span></span>
- <span data-ttu-id="d22de-114">Frågor som sparas någonstans utanför säkerhets Center</span><span class="sxs-lookup"><span data-stu-id="d22de-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="d22de-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="d22de-115">December 2020</span></span>

| <span data-ttu-id="d22de-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="d22de-116">Table name</span></span> | <span data-ttu-id="d22de-117">Ursprungligt kolumn namn</span><span class="sxs-lookup"><span data-stu-id="d22de-117">Original column name</span></span> | <span data-ttu-id="d22de-118">Nytt kolumn namn</span><span class="sxs-lookup"><span data-stu-id="d22de-118">New column name</span></span> | <span data-ttu-id="d22de-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="d22de-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="d22de-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d22de-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d22de-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="d22de-121">FinalEmailAction</span></span> | <span data-ttu-id="d22de-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="d22de-122">EmailAction</span></span> | <span data-ttu-id="d22de-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d22de-123">Customer feedback</span></span> |
| [<span data-ttu-id="d22de-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d22de-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d22de-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="d22de-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="d22de-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="d22de-126">EmailActionPolicy</span></span> | <span data-ttu-id="d22de-127">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d22de-127">Customer feedback</span></span> |
| [<span data-ttu-id="d22de-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d22de-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d22de-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="d22de-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="d22de-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="d22de-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="d22de-131">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d22de-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d22de-132">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d22de-132">Related topics</span></span>
- [<span data-ttu-id="d22de-133">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d22de-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d22de-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d22de-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)