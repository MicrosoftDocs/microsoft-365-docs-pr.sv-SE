---
title: Använda delade frågor i Microsoft Threat Protection Advanced jakt
description: Starta hotet jakt direkt med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, GitHub repo, mina frågor, delade frågor
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
ms.openlocfilehash: 3682044ab100d396719e3b7ffe5a6331852d0d55
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201225"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="66ba5-105">Använda delade frågor i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="66ba5-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66ba5-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="66ba5-106">**Applies to:**</span></span>
- <span data-ttu-id="66ba5-107">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="66ba5-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="66ba5-108">[Avancerade jakt](advanced-hunting-overview.md) frågor kan delas mellan användare i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="66ba5-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="66ba5-109">Du kan också hitta frågor som delas offentligt på GitHub.</span><span class="sxs-lookup"><span data-stu-id="66ba5-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="66ba5-110">De här frågorna gör det möjligt för dig att snabbt hitta speciella hot om hotet utan att behöva skriva frågor från grunden.</span><span class="sxs-lookup"><span data-stu-id="66ba5-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="66ba5-112">Spara, ändra och dela en fråga</span><span class="sxs-lookup"><span data-stu-id="66ba5-112">Save, modify, and share a query</span></span>
<span data-ttu-id="66ba5-113">Du kan spara en ny eller befintlig fråga så att den är tillgänglig för dig eller delas med andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="66ba5-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="66ba5-114">Skapa eller ändra en fråga.</span><span class="sxs-lookup"><span data-stu-id="66ba5-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="66ba5-115">Klicka på den nedrullningsbara List rutan **Spara fråga** och välj **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="66ba5-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="66ba5-116">Ange ett namn på frågan.</span><span class="sxs-lookup"><span data-stu-id="66ba5-116">Enter a name for the query.</span></span> 

   ![Bild av hur du sparar en fråga](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="66ba5-118">Välj den mapp där du vill spara frågan.</span><span class="sxs-lookup"><span data-stu-id="66ba5-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="66ba5-119">**Delade frågor** – delas till alla användare i organisationen</span><span class="sxs-lookup"><span data-stu-id="66ba5-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="66ba5-120">**Mina frågor** – endast tillgängligt för dig</span><span class="sxs-lookup"><span data-stu-id="66ba5-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="66ba5-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="66ba5-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="66ba5-122">Ta bort eller byta namn på en fråga</span><span class="sxs-lookup"><span data-stu-id="66ba5-122">Delete or rename a query</span></span>
1. <span data-ttu-id="66ba5-123">Högerklicka på en fråga som du vill byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="66ba5-123">Right-click on a query you want to rename or delete.</span></span>

    ![Bild av en borttagnings fråga](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="66ba5-125">Välj **ta bort** och bekräfta borttagning.</span><span class="sxs-lookup"><span data-stu-id="66ba5-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="66ba5-126">Eller Välj **Byt namn** och ange ett nytt namn på frågan.</span><span class="sxs-lookup"><span data-stu-id="66ba5-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="66ba5-127">Skapa en direkt länk till en fråga</span><span class="sxs-lookup"><span data-stu-id="66ba5-127">Create a direct link to a query</span></span>
<span data-ttu-id="66ba5-128">Om du vill skapa en länk som öppnar frågan direkt i den avancerade Frågeredigeraren kan du slutföra frågan och välja **Dela länk**.</span><span class="sxs-lookup"><span data-stu-id="66ba5-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="66ba5-129">Åtkomst frågor i GitHub-databasen</span><span class="sxs-lookup"><span data-stu-id="66ba5-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="66ba5-130">Microsofts säkerhets forskare delar regelbundet avancerade frågor i en [angiven offentlig lagrings plats på GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="66ba5-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="66ba5-131">Denna databas är öppen för bidrag.</span><span class="sxs-lookup"><span data-stu-id="66ba5-131">This repository is open to contributions.</span></span> <span data-ttu-id="66ba5-132">[Delta i GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="66ba5-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="66ba5-133">Microsofts säkerhets forskare tillhandahåller också avancerade frågor som du kan använda för att hitta aktiviteter och indikatorer som är kopplade till nya hot.</span><span class="sxs-lookup"><span data-stu-id="66ba5-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="66ba5-134">Dessa frågor tillhandahålls som en del av [Threat Analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) -rapporterna i Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="66ba5-134">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66ba5-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="66ba5-135">Related topics</span></span>
- [<span data-ttu-id="66ba5-136">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="66ba5-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="66ba5-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="66ba5-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="66ba5-138">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="66ba5-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="66ba5-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="66ba5-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="66ba5-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="66ba5-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="66ba5-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="66ba5-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
