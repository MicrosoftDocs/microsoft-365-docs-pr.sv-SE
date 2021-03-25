---
title: Använda delade frågor för avancerad sökning
description: Börja sök hot omedelbart med fördefinierade och delade frågor. Dela dina frågor offentligt eller med din organisation.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075466"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="c253f-105">Använda delade frågor för avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="c253f-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c253f-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c253f-106">**Applies to:**</span></span>
- [<span data-ttu-id="c253f-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c253f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="c253f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c253f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c253f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c253f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="c253f-110">[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="c253f-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="c253f-111">Du kan också hitta frågor som delats offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="c253f-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="c253f-112">Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="c253f-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild på delade frågor](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="c253f-114">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="c253f-114">Save, modify, and share a query</span></span>
<span data-ttu-id="c253f-115">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c253f-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="c253f-116">Skriv en ny fråga eller läs in en befintlig fråga under **Delade frågor** eller **Mina frågor.**</span><span class="sxs-lookup"><span data-stu-id="c253f-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="c253f-117">Välj **Spara** eller **Spara som** bland alternativen för Att spara.</span><span class="sxs-lookup"><span data-stu-id="c253f-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="c253f-118">Du undviker att skriva över en befintlig fråga genom att **välja Spara som**.</span><span class="sxs-lookup"><span data-stu-id="c253f-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="c253f-119">Ange ett namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="c253f-119">Enter a name for the query.</span></span>

   ![Bild av att spara en fråga](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="c253f-121">Välj den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="c253f-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="c253f-122">**Delade frågor –** delas för alla användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="c253f-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="c253f-123">**Mina frågor –** endast tillgänglig för dig</span><span class="sxs-lookup"><span data-stu-id="c253f-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="c253f-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c253f-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="c253f-125">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="c253f-125">Delete or rename a query</span></span>
1. <span data-ttu-id="c253f-126">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="c253f-126">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfråga](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="c253f-128">Välj **Ta bort** och bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="c253f-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="c253f-129">Eller välj **Byt** namn och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="c253f-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="c253f-130">Skapa en direktlänk till en fråga</span><span class="sxs-lookup"><span data-stu-id="c253f-130">Create a direct link to a query</span></span>
<span data-ttu-id="c253f-131">Om du vill skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökning slutför du frågan och väljer **Dela länk**.</span><span class="sxs-lookup"><span data-stu-id="c253f-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="c253f-132">Åtkomstfrågor på GitHub-lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="c253f-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="c253f-133">Microsoft-säkerhetsvakterna delar regelbundet avancerade sökfrågor på en [angiven offentlig lagringsplats på GitHub.](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)</span><span class="sxs-lookup"><span data-stu-id="c253f-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="c253f-134">Lagringsplatsen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="c253f-134">This repository is open to contributions.</span></span> <span data-ttu-id="c253f-135">Delta genom [att kostnadsfritt ansluta till GitHub.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="c253f-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="c253f-136">Microsoft-säkerhetsvakter erbjuder också avancerade sökfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot.</span><span class="sxs-lookup"><span data-stu-id="c253f-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="c253f-137">Dessa frågor tillhandahålls som en del av rapporterna [över hotanalyser](threat-analytics.md) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="c253f-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c253f-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c253f-138">Related topics</span></span>
- [<span data-ttu-id="c253f-139">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c253f-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c253f-140">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c253f-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c253f-141">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="c253f-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c253f-142">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c253f-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="c253f-143">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c253f-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c253f-144">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="c253f-144">Custom detections overview</span></span>](overview-custom-detections.md)
