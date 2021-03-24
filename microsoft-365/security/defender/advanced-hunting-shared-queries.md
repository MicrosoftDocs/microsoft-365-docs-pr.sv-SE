---
title: Använda delade frågor i Microsoft 365 Defender avancerad sökning
description: Börja sök hot omedelbart med fördefinierade och delade frågor. Dela dina frågor offentligt eller med din organisation.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: f153e438465d4cacf5293cd6e834e85783601c89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069006"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="07fe3-105">Använda delade frågor för avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="07fe3-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07fe3-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07fe3-106">**Applies to:**</span></span>
- <span data-ttu-id="07fe3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07fe3-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="07fe3-108">[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="07fe3-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="07fe3-109">Du kan också hitta frågor som delats offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="07fe3-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="07fe3-110">Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="07fe3-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild på delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="07fe3-112">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="07fe3-112">Save, modify, and share a query</span></span>
<span data-ttu-id="07fe3-113">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="07fe3-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="07fe3-114">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="07fe3-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="07fe3-115">Klicka på **listrutan** Spara fråga och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="07fe3-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="07fe3-116">Ange ett namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="07fe3-116">Enter a name for the query.</span></span> 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="07fe3-118">Välj den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="07fe3-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="07fe3-119">**Delade frågor –** delas för alla användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="07fe3-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="07fe3-120">**Mina frågor –** endast tillgänglig för dig</span><span class="sxs-lookup"><span data-stu-id="07fe3-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="07fe3-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="07fe3-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="07fe3-122">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="07fe3-122">Delete or rename a query</span></span>
1. <span data-ttu-id="07fe3-123">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="07fe3-123">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfråga](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="07fe3-125">Välj **Ta bort** och bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="07fe3-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="07fe3-126">Eller välj **Byt** namn och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="07fe3-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="07fe3-127">Skapa en direktlänk till en fråga</span><span class="sxs-lookup"><span data-stu-id="07fe3-127">Create a direct link to a query</span></span>
<span data-ttu-id="07fe3-128">Om du vill skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökning slutför du frågan och väljer **Dela länk**.</span><span class="sxs-lookup"><span data-stu-id="07fe3-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="07fe3-129">Åtkomstfrågor på GitHub-lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="07fe3-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="07fe3-130">Microsoft-säkerhetsvakterna delar regelbundet avancerade sökfrågor på en [angiven offentlig lagringsplats på GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="07fe3-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="07fe3-131">Lagringsplatsen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="07fe3-131">This repository is open to contributions.</span></span> <span data-ttu-id="07fe3-132">Delta genom [att kostnadsfritt ansluta till GitHub.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="07fe3-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="07fe3-133">Microsoft-säkerhetsvakter erbjuder också avancerade sökfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot.</span><span class="sxs-lookup"><span data-stu-id="07fe3-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="07fe3-134">Dessa frågor tillhandahålls som en del av rapporterna [över hotanalyser](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="07fe3-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07fe3-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="07fe3-135">Related topics</span></span>
- [<span data-ttu-id="07fe3-136">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="07fe3-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07fe3-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="07fe3-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07fe3-138">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="07fe3-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="07fe3-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="07fe3-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="07fe3-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="07fe3-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="07fe3-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="07fe3-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)