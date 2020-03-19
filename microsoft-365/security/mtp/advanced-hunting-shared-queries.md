---
title: Använda delade frågor i Microsoft Threat Protection avancerad jakt
description: Börja hotjakt omedelbart med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808278"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="8d7c4-105">Använda delade frågor i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8d7c4-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="8d7c4-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="8d7c4-106">**Applies to:**</span></span>
- <span data-ttu-id="8d7c4-107">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d7c4-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="8d7c4-108">[Avancerade jaktfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="8d7c4-109">Du kan också hitta frågor som delas offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="8d7c4-110">Med de här frågorna kan du snabbt fortsätta med specifika hotjaktsscenarier utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="8d7c4-112">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="8d7c4-112">Save, modify, and share a query</span></span>
<span data-ttu-id="8d7c4-113">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="8d7c4-114">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="8d7c4-115">Klicka på listrutan **Spara fråga** och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="8d7c4-116">Ange ett namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-116">Enter a name for the query.</span></span> 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="8d7c4-118">Markera mappen där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="8d7c4-119">**Delade frågor** – delas med alla användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="8d7c4-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="8d7c4-120">**Mina frågor** – endast tillgängliga för dig</span><span class="sxs-lookup"><span data-stu-id="8d7c4-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="8d7c4-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="8d7c4-122">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="8d7c4-122">Delete or rename a query</span></span>
1. <span data-ttu-id="8d7c4-123">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-123">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfrågan](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="8d7c4-125">Välj **Ta bort** och bekräfta borttagning.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="8d7c4-126">Eller välj **Byt namn** och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="8d7c4-127">Komma åt frågor i GitHub-databasen</span><span class="sxs-lookup"><span data-stu-id="8d7c4-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="8d7c4-128">Microsofts säkerhetsforskare delar regelbundet avancerade jaktfrågor i en [utsedd offentlig databas på GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="8d7c4-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="8d7c4-129">Den här databasen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-129">This repository is open to contributions.</span></span> <span data-ttu-id="8d7c4-130">För att [bidra, gå med GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="8d7c4-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="8d7c4-131">Microsofts säkerhetsforskare tillhandahåller också avancerade jaktfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="8d7c4-132">Dessa frågor tillhandahålls som en del av [hotanalysrapporterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d7c4-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8d7c4-133">Related topics</span></span>
- [<span data-ttu-id="8d7c4-134">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="8d7c4-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d7c4-135">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="8d7c4-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8d7c4-136">Jaga hot mellan enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="8d7c4-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8d7c4-137">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8d7c4-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8d7c4-138">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="8d7c4-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
