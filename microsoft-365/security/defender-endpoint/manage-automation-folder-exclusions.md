---
title: Hantera undantag från automationsmappar
description: Lägg till undantag för automatiseringsmappar för att styra filer som är undantagna från en automatiserad undersökning.
keywords: hantera, automatisering, undantag, blockera, rensa, skadlig
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185843"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="af5ff-104">Hantera undantag från automationsmappar</span><span class="sxs-lookup"><span data-stu-id="af5ff-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="af5ff-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af5ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="af5ff-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="af5ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af5ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af5ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af5ff-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="af5ff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="af5ff-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="af5ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="af5ff-110">Med undantag för automatiseringsmappar kan du ange mappar som automatisk undersökning ska hoppa över.</span><span class="sxs-lookup"><span data-stu-id="af5ff-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="af5ff-111">Du kan kontrollera följande attribut om mappen som du vill hoppa över:</span><span class="sxs-lookup"><span data-stu-id="af5ff-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="af5ff-112">Mappar</span><span class="sxs-lookup"><span data-stu-id="af5ff-112">Folders</span></span> 
- <span data-ttu-id="af5ff-113">Filtillägg</span><span class="sxs-lookup"><span data-stu-id="af5ff-113">Extensions of the files</span></span>
- <span data-ttu-id="af5ff-114">Filnamn</span><span class="sxs-lookup"><span data-stu-id="af5ff-114">File names</span></span>


<span data-ttu-id="af5ff-115">**Mappar**</span><span class="sxs-lookup"><span data-stu-id="af5ff-115">**Folders**</span></span><br>
<span data-ttu-id="af5ff-116">Du kan ange en mapp och dess undermappar som ska hoppas över.</span><span class="sxs-lookup"><span data-stu-id="af5ff-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="af5ff-117">För närvarande stöds inte användning av jokertecken som ett sätt att utesluta filer i en katalog ännu.</span><span class="sxs-lookup"><span data-stu-id="af5ff-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="af5ff-118">**Tillägg**</span><span class="sxs-lookup"><span data-stu-id="af5ff-118">**Extensions**</span></span><br>
<span data-ttu-id="af5ff-119">Du kan ange tillägg som ska undantas i en viss katalog.</span><span class="sxs-lookup"><span data-stu-id="af5ff-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="af5ff-120">Tilläggen är ett sätt att förhindra en attack från att använda en undantagen mapp för att dölja en sårbarhet.</span><span class="sxs-lookup"><span data-stu-id="af5ff-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="af5ff-121">Tilläggen definierar uttryckligen vilka filer som ska ignoreras.</span><span class="sxs-lookup"><span data-stu-id="af5ff-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="af5ff-122">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="af5ff-122">**File names**</span></span><br>
<span data-ttu-id="af5ff-123">Du kan ange vilka filnamn som ska undantas i en viss katalog.</span><span class="sxs-lookup"><span data-stu-id="af5ff-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="af5ff-124">Namnen är ett sätt att förhindra en attack från att använda en undantagen mapp för att dölja en sårbarhet.</span><span class="sxs-lookup"><span data-stu-id="af5ff-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="af5ff-125">Namnen definierar uttryckligen vilka filer som ska ignoreras.</span><span class="sxs-lookup"><span data-stu-id="af5ff-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="af5ff-126">Lägga till ett undantag för automatiseringsmappar</span><span class="sxs-lookup"><span data-stu-id="af5ff-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="af5ff-127">Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="af5ff-128">Klicka **på Undantag för ny mapp.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="af5ff-129">Ange mappinformationen:</span><span class="sxs-lookup"><span data-stu-id="af5ff-129">Enter the folder details:</span></span>

    - <span data-ttu-id="af5ff-130">Mapp</span><span class="sxs-lookup"><span data-stu-id="af5ff-130">Folder</span></span>
    - <span data-ttu-id="af5ff-131">Tillägg</span><span class="sxs-lookup"><span data-stu-id="af5ff-131">Extensions</span></span>
    - <span data-ttu-id="af5ff-132">Filnamn</span><span class="sxs-lookup"><span data-stu-id="af5ff-132">File names</span></span>
    - <span data-ttu-id="af5ff-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="af5ff-133">Description</span></span>
    

4. <span data-ttu-id="af5ff-134">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="af5ff-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="af5ff-135">Kommandon i Live Response för att samla in eller undersöka uteslutna filer misslyckas och felmeddelandet: "Filen är undantagen".</span><span class="sxs-lookup"><span data-stu-id="af5ff-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="af5ff-136">Dessutom ignorerar automatiska undersökningar uteslutna objekt.</span><span class="sxs-lookup"><span data-stu-id="af5ff-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="af5ff-137">Redigera ett undantag för automatiseringsmappar</span><span class="sxs-lookup"><span data-stu-id="af5ff-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="af5ff-138">Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="af5ff-139">Klicka **på** Redigera för undantag för mappen.</span><span class="sxs-lookup"><span data-stu-id="af5ff-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="af5ff-140">Uppdatera informationen om regeln och klicka på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="af5ff-141">Ta bort ett undantag för automatiseringsmappar</span><span class="sxs-lookup"><span data-stu-id="af5ff-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="af5ff-142">Välj Undantaget för **automatiseringsmappen Inställningar**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="af5ff-143">Klicka på **Ta bort undantag.**</span><span class="sxs-lookup"><span data-stu-id="af5ff-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="af5ff-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="af5ff-144">Related topics</span></span>
- [<span data-ttu-id="af5ff-145">Hantera automatisering av tillåtna/blockerade listor</span><span class="sxs-lookup"><span data-stu-id="af5ff-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="af5ff-146">Hantera uppladdningar av automationsfil</span><span class="sxs-lookup"><span data-stu-id="af5ff-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
