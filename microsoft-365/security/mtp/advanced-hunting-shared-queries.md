---
title: Använda delade frågor i avancerad jakt på Microsoft Threat Protection
description: Starta hotjakt omedelbart med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade identifieringar, schema, kusto, github repo, mina frågor, delade frågor
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
ms.openlocfilehash: 3fd497ce1733dd4770b9bbc8f699bbccf3237fbd
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781523"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="61e49-105">Använda delade frågor i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="61e49-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="61e49-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="61e49-106">**Applies to:**</span></span>
- <span data-ttu-id="61e49-107">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="61e49-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="61e49-108">[Avancerade jaktfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="61e49-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="61e49-109">Du kan också hitta frågor som delas offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="61e49-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="61e49-110">Med de här frågorna kan du snabbt driva specifika hotjaktsscenarier utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="61e49-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="61e49-112">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="61e49-112">Save, modify, and share a query</span></span>
<span data-ttu-id="61e49-113">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="61e49-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="61e49-114">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="61e49-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="61e49-115">Klicka på listrutan **Spara fråga** och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="61e49-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="61e49-116">Ange ett namn på frågan.</span><span class="sxs-lookup"><span data-stu-id="61e49-116">Enter a name for the query.</span></span> 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="61e49-118">Markera den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="61e49-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="61e49-119">**Delade frågor** – delas med alla användare som organisationen</span><span class="sxs-lookup"><span data-stu-id="61e49-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="61e49-120">**Mina frågor** – endast tillgängliga för dig</span><span class="sxs-lookup"><span data-stu-id="61e49-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="61e49-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="61e49-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="61e49-122">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="61e49-122">Delete or rename a query</span></span>
1. <span data-ttu-id="61e49-123">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="61e49-123">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfrågan](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="61e49-125">Välj **Ta bort** och bekräfta borttagning.</span><span class="sxs-lookup"><span data-stu-id="61e49-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="61e49-126">Du kan också välja **Byt namn** och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="61e49-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="61e49-127">Komma åt frågor i GitHub-databasen</span><span class="sxs-lookup"><span data-stu-id="61e49-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="61e49-128">Microsofts säkerhetsforskare delar regelbundet avancerade jaktfrågor i ett [angivet offentligt arkiv på GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="61e49-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="61e49-129">Databasen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="61e49-129">This repository is open to contributions.</span></span> <span data-ttu-id="61e49-130">För att [bidra, gå med GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="61e49-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="61e49-131">Microsofts säkerhetsforskare tillhandahåller också avancerade jaktfrågor som du kan använda för att hitta aktiviteter och indikatorer som är kopplade till nya hot.</span><span class="sxs-lookup"><span data-stu-id="61e49-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="61e49-132">Dessa frågor tillhandahålls som en del av [hotanalysrapporterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="61e49-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="61e49-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="61e49-133">Related topics</span></span>
- [<span data-ttu-id="61e49-134">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="61e49-134">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61e49-135">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="61e49-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61e49-136">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="61e49-136">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="61e49-137">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="61e49-137">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="61e49-138">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="61e49-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="61e49-139">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="61e49-139">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
