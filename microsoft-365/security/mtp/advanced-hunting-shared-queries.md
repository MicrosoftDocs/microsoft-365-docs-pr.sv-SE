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
ms.openlocfilehash: 38eb3c39c5473d0a729b12771b61e965dbc81931
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929486"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="3784c-105">Använda delade frågor i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="3784c-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="3784c-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="3784c-106">**Applies to:**</span></span>
- <span data-ttu-id="3784c-107">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="3784c-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="3784c-108">[Avancerade jaktfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="3784c-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="3784c-109">Du kan också hitta frågor som delas offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="3784c-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="3784c-110">Med de här frågorna kan du snabbt driva specifika hotjaktsscenarier utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="3784c-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="3784c-112">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="3784c-112">Save, modify, and share a query</span></span>
<span data-ttu-id="3784c-113">Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3784c-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="3784c-114">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="3784c-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="3784c-115">Klicka på listrutan **Spara fråga** och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="3784c-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="3784c-116">Ange ett namn på frågan.</span><span class="sxs-lookup"><span data-stu-id="3784c-116">Enter a name for the query.</span></span> 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="3784c-118">Markera den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="3784c-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="3784c-119">**Delade frågor** – delas med alla användare som organisationen</span><span class="sxs-lookup"><span data-stu-id="3784c-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="3784c-120">**Mina frågor** – endast tillgängliga för dig</span><span class="sxs-lookup"><span data-stu-id="3784c-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="3784c-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3784c-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="3784c-122">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="3784c-122">Delete or rename a query</span></span>
1. <span data-ttu-id="3784c-123">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="3784c-123">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av borttagningsfrågan](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="3784c-125">Välj **Ta bort** och bekräfta borttagning.</span><span class="sxs-lookup"><span data-stu-id="3784c-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="3784c-126">Du kan också välja **Byt namn** och ange ett nytt namn för frågan.</span><span class="sxs-lookup"><span data-stu-id="3784c-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="3784c-127">Komma åt frågor i GitHub-databasen</span><span class="sxs-lookup"><span data-stu-id="3784c-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="3784c-128">Microsofts säkerhetsforskare delar regelbundet avancerade jaktfrågor i ett [angivet offentligt arkiv på GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="3784c-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="3784c-129">Databasen är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="3784c-129">This repository is open to contributions.</span></span> <span data-ttu-id="3784c-130">För att [bidra, gå med GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="3784c-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="3784c-131">Microsofts säkerhetsforskare tillhandahåller också avancerade jaktfrågor som du kan använda för att hitta aktiviteter och indikatorer som är kopplade till nya hot.</span><span class="sxs-lookup"><span data-stu-id="3784c-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="3784c-132">Dessa frågor tillhandahålls som en del av [hotanalysrapporterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3784c-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3784c-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3784c-133">Related topics</span></span>
- [<span data-ttu-id="3784c-134">Avancerad jaktöversikt</span><span class="sxs-lookup"><span data-stu-id="3784c-134">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3784c-135">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="3784c-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3784c-136">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="3784c-136">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3784c-137">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="3784c-137">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3784c-138">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="3784c-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3784c-139">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="3784c-139">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
