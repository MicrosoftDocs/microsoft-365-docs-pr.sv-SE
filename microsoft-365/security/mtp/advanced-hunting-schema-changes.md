---
title: Namnändringar i det avancerade sökschemat i Microsoft 365 Defender
description: Spåra och granska namnändringar – tabeller och kolumner i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, data, namnändringar, namnbyte, Microsoft Threat Protection
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932208"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="8942a-104">Avancerat schema för sök – namnändringar</span><span class="sxs-lookup"><span data-stu-id="8942a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8942a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8942a-105">**Applies to:**</span></span>
- <span data-ttu-id="8942a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8942a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8942a-107">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="8942a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="8942a-108">I vissa fall byter befintliga kolumnnamn namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="8942a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="8942a-109">I den här artikeln kan du läsa om vilka namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="8942a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="8942a-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="8942a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="8942a-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="8942a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="8942a-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="8942a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="8942a-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="8942a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="8942a-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="8942a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="8942a-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="8942a-115">December 2020</span></span>

| <span data-ttu-id="8942a-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="8942a-116">Table name</span></span> | <span data-ttu-id="8942a-117">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8942a-117">Original column name</span></span> | <span data-ttu-id="8942a-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8942a-118">New column name</span></span> | <span data-ttu-id="8942a-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="8942a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="8942a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8942a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8942a-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="8942a-121">FinalEmailAction</span></span> | <span data-ttu-id="8942a-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="8942a-122">EmailAction</span></span> | <span data-ttu-id="8942a-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8942a-123">Customer feedback</span></span> |
| [<span data-ttu-id="8942a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8942a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8942a-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="8942a-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="8942a-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="8942a-126">EmailActionPolicy</span></span> | <span data-ttu-id="8942a-127">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8942a-127">Customer feedback</span></span> |
| [<span data-ttu-id="8942a-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8942a-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8942a-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="8942a-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="8942a-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="8942a-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="8942a-131">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8942a-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8942a-132">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8942a-132">Related topics</span></span>
- [<span data-ttu-id="8942a-133">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8942a-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8942a-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8942a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)