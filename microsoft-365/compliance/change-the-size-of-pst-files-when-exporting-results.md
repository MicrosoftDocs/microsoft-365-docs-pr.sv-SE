---
title: Ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Du kan ändra standardstorleken för PST-filer som laddas ned till datorn när du exporterar eDiscovery-sökresultat.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "52161513"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="b38c8-103">Ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat</span><span class="sxs-lookup"><span data-stu-id="b38c8-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="b38c8-104">När du använder verktyget för eDiscovery-export för att exportera e-postresultaten från en eDiscovery-sökning från de olika Microsoft eDiscovery-verktygen är standardstorleken för en PST-fil som kan exporteras 10 GB.</span><span class="sxs-lookup"><span data-stu-id="b38c8-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="b38c8-105">Om du vill ändra den här standardstorleken kan du redigera Windows-registret på den dator som du använder för att exportera sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="b38c8-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="b38c8-106">En orsak till det är att en PST-fil får plats på ett flyttbart medium, en DVD-skiva, en cd-skiva eller en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="b38c8-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b38c8-107">Verktyget för eDiscovery-export används för att exportera sökresultaten när de använder verktyget Innehållssökning i säkerhets- och efterlevnadscentret för &, In-Place eDiscovery i Exchange Online och eDiscovery Center i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b38c8-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="b38c8-108">Skapa en registerinställning för att ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat</span><span class="sxs-lookup"><span data-stu-id="b38c8-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="b38c8-109">Utför följande procedur på den dator som du använder för att exportera resultatet av en eDiscovery-sökning.</span><span class="sxs-lookup"><span data-stu-id="b38c8-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="b38c8-110">Stäng verktyget eDiscovery Export om det är öppet.</span><span class="sxs-lookup"><span data-stu-id="b38c8-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="b38c8-111">Spara följande text i en Window-registerfil med filnamnssuffixet .reg. till exempel PstExportera.reg.</span><span class="sxs-lookup"><span data-stu-id="b38c8-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="b38c8-112">I exemplet ovan är värdet inställt på  `PstSizeLimitInBytes` 1 073 741 824 byte eller ungefär 1 GB.</span><span class="sxs-lookup"><span data-stu-id="b38c8-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="b38c8-113">Här är några andra exempelvärden för  `PstSizeLimitInBytes` inställningen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="b38c8-114">**Storlek i GB (ca.)**</span><span class="sxs-lookup"><span data-stu-id="b38c8-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="b38c8-115">**Storlek i byte**</span><span class="sxs-lookup"><span data-stu-id="b38c8-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b38c8-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="b38c8-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="b38c8-117">751619277</span><span class="sxs-lookup"><span data-stu-id="b38c8-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="b38c8-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="b38c8-118">2 GB</span></span>  <br/> |<span data-ttu-id="b38c8-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="b38c8-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="b38c8-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="b38c8-120">4 GB</span></span>  <br/> |<span data-ttu-id="b38c8-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="b38c8-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="b38c8-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="b38c8-122">8 GB</span></span>  <br/> |<span data-ttu-id="b38c8-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="b38c8-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="b38c8-124">Ändra `PstSizeLimitInBytes` värdet till önskad maxstorlek för en PST-fil när du exporterar sökresultatet och spara sedan filen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="b38c8-125">I Windows i Utforskaren klickar eller dubbelklickar du på REG-filen som du skapade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="b38c8-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="b38c8-126">I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="b38c8-127">När du uppmanas att fortsätta klickar du på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="b38c8-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="b38c8-128">Registereditorn visar ett meddelande om att inställningen har lagts till i registret.</span><span class="sxs-lookup"><span data-stu-id="b38c8-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="b38c8-129">Du kan upprepa steg 3–6 om du vill ändra värdet för  `PstSizeLimitInBytes` registerinställningen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="b38c8-130">Vanliga frågor och svar om hur du ändrar standardstorleken för PST-filer när du exporterar eDiscovery-sökresultat</span><span class="sxs-lookup"><span data-stu-id="b38c8-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="b38c8-131">**Varför är standardstorleken 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="b38c8-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="b38c8-132">Standardstorleken på 10 GB baseras på feedback från kunder. 10 GB är en bra balans mellan den optimala mängden innehåll i en enda PST-fil och med minsta risk för skadade filer.</span><span class="sxs-lookup"><span data-stu-id="b38c8-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="b38c8-133">**Ska jag öka eller minska standardstorleken på PST-filer?**</span><span class="sxs-lookup"><span data-stu-id="b38c8-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="b38c8-134">Kunder tenderar att minska storleksgränsen så att sökresultaten får plats på ett flyttbart medium som de fysiskt kan skicka till andra platser inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="b38c8-135">Vi rekommenderar inte att du ökar standardstorleken eftersom problem med skadade PST-filer som är större än 10 GB kan ha problem med skadade filer.</span><span class="sxs-lookup"><span data-stu-id="b38c8-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="b38c8-136">**Vilken dator måste jag göra detta på?**</span><span class="sxs-lookup"><span data-stu-id="b38c8-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="b38c8-137">Du måste ändra registerinställningen på alla lokala datorer där du kör verktyget för eDiscovery-export.</span><span class="sxs-lookup"><span data-stu-id="b38c8-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="b38c8-138">**Måste jag starta om datorn när jag har ändrat den här inställningen?**</span><span class="sxs-lookup"><span data-stu-id="b38c8-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="b38c8-139">Nej, du behöver inte starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="b38c8-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="b38c8-140">Men om verktyget för eDiscovery-export körs måste du stänga det och starta om det när du har ändrat den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="b38c8-141">**Redigeras en befintlig registernyckel, eller skapas en ny nyckel?**</span><span class="sxs-lookup"><span data-stu-id="b38c8-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="b38c8-142">En ny registernyckel skapas första gången du kör REG-filen som du skapade i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="b38c8-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="b38c8-143">Sedan redigeras inställningen varje gång du ändrar och kör REG-redigeringsfilen igen.</span><span class="sxs-lookup"><span data-stu-id="b38c8-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
