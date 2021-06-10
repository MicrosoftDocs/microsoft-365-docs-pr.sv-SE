---
title: Använda delade frågor i Microsoft 365 Defender avancerad sökning
description: Börja sök hot omedelbart med fördefinierade och delade frågor. Dela dina frågor offentligt eller med din organisation.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952590"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="59aa7-105">Använda delade frågor för avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="59aa7-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59aa7-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="59aa7-106">**Applies to:**</span></span>
- <span data-ttu-id="59aa7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59aa7-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="59aa7-108">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="59aa7-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="59aa7-109">[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="59aa7-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="59aa7-110">Du kan också hitta frågor som delats offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="59aa7-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="59aa7-111">Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="59aa7-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild på delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="59aa7-113">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="59aa7-113">Save, modify, and share a query</span></span>
<span data-ttu-id="59aa7-114">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="59aa7-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="59aa7-115">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="59aa7-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="59aa7-116">Klicka på **listrutan** Spara fråga och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="59aa7-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="59aa7-117">Ange ett namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="59aa7-117">Enter a name for the query.</span></span> 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="59aa7-119">Välj den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="59aa7-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="59aa7-120">**Delade frågor –** delas för alla användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="59aa7-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="59aa7-121">**Mina frågor –** endast tillgänglig för dig</span><span class="sxs-lookup"><span data-stu-id="59aa7-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="59aa7-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59aa7-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="59aa7-123">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="59aa7-123">Delete or rename a query</span></span>
1. <span data-ttu-id="59aa7-124">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="59aa7-124">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfråga](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="59aa7-126">Välj **Ta bort** och bekräfta borttagningen.</span><span class="sxs-lookup"><span data-stu-id="59aa7-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="59aa7-127">Eller välj **Byt** namn och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="59aa7-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="59aa7-128">Skapa en direktlänk till en fråga</span><span class="sxs-lookup"><span data-stu-id="59aa7-128">Create a direct link to a query</span></span>
<span data-ttu-id="59aa7-129">Om du vill skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökning slutför du frågan och väljer **Dela länk**.</span><span class="sxs-lookup"><span data-stu-id="59aa7-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="59aa7-130">Åtkomstfrågor på den GitHub lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="59aa7-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="59aa7-131">Microsoft-säkerhetsvakterna delar regelbundet avancerade sökfrågor på en [angiven offentlig lagringsplats i GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="59aa7-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="59aa7-132">Lagringsplatsen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="59aa7-132">This repository is open to contributions.</span></span> <span data-ttu-id="59aa7-133">Delta utan kostnad [GitHub delta.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="59aa7-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="59aa7-134">Microsoft-säkerhetsvakter erbjuder också avancerade sökfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot.</span><span class="sxs-lookup"><span data-stu-id="59aa7-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="59aa7-135">Dessa frågor tillhandahålls som en del av rapporterna [för hotanalys](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="59aa7-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="59aa7-136">Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="59aa7-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="59aa7-137">[Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor.</span><span class="sxs-lookup"><span data-stu-id="59aa7-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="59aa7-138">Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="59aa7-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="59aa7-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="59aa7-139">Related topics</span></span>
- [<span data-ttu-id="59aa7-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="59aa7-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59aa7-141">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="59aa7-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="59aa7-142">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="59aa7-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="59aa7-143">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="59aa7-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="59aa7-144">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="59aa7-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="59aa7-145">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="59aa7-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)