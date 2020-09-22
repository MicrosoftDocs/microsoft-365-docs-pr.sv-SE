---
title: Visa information om skadliga filer som identifieras av Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Lär dig hur du kan visa information om skadliga filer som identifieras i SharePoint, OneDrive eller teams och hur du åtgärdar dessa filer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e6cd0363b546fad063290ae20e8c6c82fd6d0dea
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202001"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="7d228-103">Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d228-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7d228-104">[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokument bibliotek och grupp webbplatser.</span><span class="sxs-lookup"><span data-stu-id="7d228-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="7d228-105">När en skadlig fil identifieras blockeras den så att ingen kan öppna, kopiera, flytta eller dela den innan ytterligare åtgärder vidtas av organisationens säkerhets team.</span><span class="sxs-lookup"><span data-stu-id="7d228-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="7d228-106">Läs den här artikeln om du vill veta mer om hur du visar information om upptäckta filer och vilka åtgärder som ska vidtas.</span><span class="sxs-lookup"><span data-stu-id="7d228-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="7d228-107">För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha nödvändig [behörighet för säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7d228-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="7d228-108">Visa rapporter med information om identifierade filer</span><span class="sxs-lookup"><span data-stu-id="7d228-108">View reports with information about detected files</span></span>

<span data-ttu-id="7d228-109">Om du vill visa status och detaljerad information om filer som upptäckts av Office 365 ATP kan du använda status rapporten för hotets skydd.</span><span class="sxs-lookup"><span data-stu-id="7d228-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="7d228-110">Välj **rapport** [ &amp; ](https://protection.office.com) \> **Dashboard** \> **skydds status**för instrument panel för säkerhets kontroll.</span><span class="sxs-lookup"><span data-stu-id="7d228-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="7d228-111">I det övre högra hörnet i rapporten väljer du **tabellen Visa information**.</span><span class="sxs-lookup"><span data-stu-id="7d228-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="7d228-112">Visa listan över filer som upptäcktes i rapporten.</span><span class="sxs-lookup"><span data-stu-id="7d228-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="7d228-113">Välj ett objekt i listan för att visa detaljerad information, inklusive utförda åtgärder, fil namnet, fil Sök vägen och annat.</span><span class="sxs-lookup"><span data-stu-id="7d228-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="7d228-114">Välj fliken **Avancerad analys** för att visa information, till exempel observerat beteende och analys information.</span><span class="sxs-lookup"><span data-stu-id="7d228-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="7d228-115">Visa och vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="7d228-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="7d228-116">&amp;Välj **Threat Management** \> **granskning** \> **Quarantine**i Center för säkerhets kontroll.</span><span class="sxs-lookup"><span data-stu-id="7d228-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="7d228-117">(Du kan också gå direkt till [https://protection.office.com/quarantine](https://protection.office.com/quarantine) .)</span><span class="sxs-lookup"><span data-stu-id="7d228-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="7d228-118">I det övre vänstra hörnet ändrar du den nedrullningsbara menyn från **e-post** till **filer**.</span><span class="sxs-lookup"><span data-stu-id="7d228-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="7d228-119">Om resultat listan innehåller för många objekt använder du **filter** funktionen för att begränsa markeringen.</span><span class="sxs-lookup"><span data-stu-id="7d228-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="7d228-120">Välj ett objekt i listan för att visa detaljerad information, inklusive filens URL.</span><span class="sxs-lookup"><span data-stu-id="7d228-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="7d228-121">Välj en tillgänglig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="7d228-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="7d228-122">Välj **släpp filen** för att häva blockeringen av filen.</span><span class="sxs-lookup"><span data-stu-id="7d228-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="7d228-123">Välj **Skicka rapport till Microsoft** för att rapportera filen som en falsk positiv till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d228-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="7d228-124">Välj **Ladda ner fil** för att undersöka filen.</span><span class="sxs-lookup"><span data-stu-id="7d228-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="7d228-125">Välj **ta bort från karantän** för att ta bort filen från listan med objekt i karantän.</span><span class="sxs-lookup"><span data-stu-id="7d228-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="7d228-126">Om du väljer det här alternativet måste du även ta bort filen från dess bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d228-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="7d228-127">Det här alternativet avblockerar inte en fil från att öppnas eller delas.</span><span class="sxs-lookup"><span data-stu-id="7d228-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="7d228-128">Välj **Stäng** för att stänga informationen för ett markerat objekt.</span><span class="sxs-lookup"><span data-stu-id="7d228-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

