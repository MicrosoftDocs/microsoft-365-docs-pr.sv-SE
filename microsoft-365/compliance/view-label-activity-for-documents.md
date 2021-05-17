---
title: Visa etikettaktivitet för dokument
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Lär dig att använda utforskaren för etikettaktivitet i Säkerhets- och efterlevnadscenter för Microsoft 365 för att söka efter och visa etikettaktivitet.
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2020
ms.locfileid: "52161589"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="45534-103">Visa etikettaktivitet för dokument</span><span class="sxs-lookup"><span data-stu-id="45534-103">View label activity for documents</span></span>

<span data-ttu-id="45534-104">När du har skapat dina etiketter bör du kontrollera att de används på innehållet som du tänkt dig.</span><span class="sxs-lookup"><span data-stu-id="45534-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="45534-105">Med utforskaren för etikettaktivitet i Säkerhets- &amp; efterlevnadscenter kan du snabbt söka efter och visa etikettaktivitet för allt innehåll i SharePoint och OneDrive för företag under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="45534-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="45534-106">Det här är realtidsdata som ger dig en tydlig bild av vad som händer i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="45534-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="45534-107">Med utforskaren för etikettaktivitet kan du till exempel:</span><span class="sxs-lookup"><span data-stu-id="45534-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="45534-108">Se hur många gånger varje etikett har använts varje dag (upp till 30 dagar).</span><span class="sxs-lookup"><span data-stu-id="45534-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="45534-109">Se vem som har etiketterat exakt vilken fil på vilket datum, samt en länk till webbplatsen där filen finns.</span><span class="sxs-lookup"><span data-stu-id="45534-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="45534-110">Se vilka filer där etiketterna har ändrats eller tagits bort, vilka de gamla och nya etiketterna är och vem som har gjort ändringen.</span><span class="sxs-lookup"><span data-stu-id="45534-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="45534-111">Filtrera data för att se all etikettaktivitet för en viss etikett, fil eller användare.</span><span class="sxs-lookup"><span data-stu-id="45534-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="45534-112">Du kan också filtrera etikettaktiviteten efter plats (SharePoint eller OneDrive för företag) och om etiketten har använts manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="45534-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="45534-113">Se etikettaktiviteten för både mappar och enskilda dokument.</span><span class="sxs-lookup"><span data-stu-id="45534-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="45534-114">Snart kommer även möjligheten att se hur många filer i mappen som har etiketterats när mappen etiketterades.</span><span class="sxs-lookup"><span data-stu-id="45534-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="45534-115">Du hittar utforskaren för etikettaktivitet i Säkerhets- &amp; efterlevnadscenter > **Informationsstyrning** > **Utforskaren för etikettaktivitet**.</span><span class="sxs-lookup"><span data-stu-id="45534-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="45534-116">Observera att utforskaren för etikettaktivitet kräver en Office 365 Enterprise E5-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="45534-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Utforskaren för etikettaktivitet](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="45534-118">Visa etikettaktiviteter för filer eller mappar</span><span class="sxs-lookup"><span data-stu-id="45534-118">View label activities for files or folders</span></span>

<span data-ttu-id="45534-119">Längst upp i utforskaren för etikettaktivitet kan du välja om du vill visa aktiviteter för filer eller mappar.</span><span class="sxs-lookup"><span data-stu-id="45534-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="45534-120">Observera att mappaktiviteten bara omfattar själva mappen, inte filerna i mappen.</span><span class="sxs-lookup"><span data-stu-id="45534-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="45534-121">Du kanske vill se etikettaktiviteten för mappar eftersom om du anger en etikett för en mapp får även alla filer i mappen den etiketten (förutom filer där en etikett uttryckligen har tillämpats).</span><span class="sxs-lookup"><span data-stu-id="45534-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="45534-122">Därför kan etikettering av mappar påverka ett betydande antal filer.</span><span class="sxs-lookup"><span data-stu-id="45534-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="45534-123">Mer information finns i [Använda en standardkvarhållningsetikett på allt innehåll i ett SharePoint-bibliotek, en mapp eller en dokumentuppsättning](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="45534-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Listmeny som visar etikettaktiviteter för filer och mappar](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="45534-125">Etikettaktiviteter</span><span class="sxs-lookup"><span data-stu-id="45534-125">Label activities</span></span>

 <span data-ttu-id="45534-126">**Etikettaktiviteter** inkluderar alla etikettåtgärder: **lägga till**, **ta bort** eller **ändra** en etikett.</span><span class="sxs-lookup"><span data-stu-id="45534-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="45534-127">Du kan använda vyn för att få en översikt för hur många filer varje etikett har tillämpats på per dag.</span><span class="sxs-lookup"><span data-stu-id="45534-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="45534-128">Etikettändringar</span><span class="sxs-lookup"><span data-stu-id="45534-128">Label changes</span></span>

 <span data-ttu-id="45534-129">**Etikettändringar** omfattar potentiellt riskabla åtgärder för att **ta bort** eller **ändra** en etikett.</span><span class="sxs-lookup"><span data-stu-id="45534-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="45534-130">Du kan använda vyn för att snabbt se sådana riskabla åtgärder och användaren som utförde dem.</span><span class="sxs-lookup"><span data-stu-id="45534-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="45534-131">I aktivitetslistan under diagrammet kan du markera en fil och sedan klicka på en länk till filen i informationsfönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="45534-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Informationsfönster för etikettaktivitet](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="45534-133">Filtrera etikettaktivitet</span><span class="sxs-lookup"><span data-stu-id="45534-133">Filter label activity</span></span>

<span data-ttu-id="45534-134">Du kan snabbt filtrera data för att se all etikettaktivitet för en viss etikett, fil eller användare.</span><span class="sxs-lookup"><span data-stu-id="45534-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="45534-135">Du kan också filtrera etikettaktiviteten efter plats (SharePoint eller OneDrive för företag) och om etiketten har använts manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="45534-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filter för etikettaktivitet](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

