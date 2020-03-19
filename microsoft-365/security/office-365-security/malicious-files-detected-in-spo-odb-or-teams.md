---
title: Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Läs om var du kan visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Teams och hur du vidtar åtgärder för dessa filer.
ms.openlocfilehash: 49c7e1668602a63b8b82339ad0cc7823146212a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807798"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="9e14e-103">Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams</span><span class="sxs-lookup"><span data-stu-id="9e14e-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="9e14e-104">[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokumentbibliotek och gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="9e14e-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="9e14e-105">När en skadlig fil identifieras blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den tills ytterligare åtgärder vidtas av organisationens säkerhetsteam.</span><span class="sxs-lookup"><span data-stu-id="9e14e-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="9e14e-106">Läs den här artikeln om du vill lära dig hur du visar information om identifierade filer och vilka åtgärder som ska vidtas.</span><span class="sxs-lookup"><span data-stu-id="9e14e-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="9e14e-107">För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha de behörigheter som krävs [för Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9e14e-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="9e14e-108">Visa rapporter med information om identifierade filer</span><span class="sxs-lookup"><span data-stu-id="9e14e-108">View reports with information about detected files</span></span>

<span data-ttu-id="9e14e-109">Om du vill visa status och detaljerad information om filer som har upptäckts av Office 365 ATP kan du använda rapporten Status för hotskydd.</span><span class="sxs-lookup"><span data-stu-id="9e14e-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="9e14e-110">I [Office 365 &amp; Security Compliance Center](https://protection.office.com)väljer du **Status för rapporter** \> som skydd av **instrumentpanelen** \> **Threat Protection Status**.</span><span class="sxs-lookup"><span data-stu-id="9e14e-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="9e14e-111">Välj **Visa informationstabell**i det övre högra hörnet av rapporten .</span><span class="sxs-lookup"><span data-stu-id="9e14e-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="9e14e-112">Visa listan över filer som har upptäckts i rapporten.</span><span class="sxs-lookup"><span data-stu-id="9e14e-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="9e14e-113">Markera ett objekt i listan om du vill visa detaljerad information, inklusive åtgärder som vidtagits, filnamnet, filsökvägen med mera.</span><span class="sxs-lookup"><span data-stu-id="9e14e-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="9e14e-114">Välj fliken **Avancerad analys** om du vill visa information, till exempel observerat beteende och analysinformation.</span><span class="sxs-lookup"><span data-stu-id="9e14e-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="9e14e-115">Visa och vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="9e14e-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="9e14e-116">I Office 365 &amp; Security Compliance Center väljer du \> **Review** \> **Quarantine** **Hothanteringsgranskningskarantän** .</span><span class="sxs-lookup"><span data-stu-id="9e14e-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="9e14e-117">(Du kan också [https://protection.office.com/quarantine](https://protection.office.com/quarantine)gå direkt till .)</span><span class="sxs-lookup"><span data-stu-id="9e14e-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="9e14e-118">I det övre vänstra hörnet ändrar du rullgardinsmenyn från **E-post** till **Filer**.</span><span class="sxs-lookup"><span data-stu-id="9e14e-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="9e14e-119">Om listan med resultat innehåller för många objekt använder du **filterfunktionen** för att begränsa markeringen.</span><span class="sxs-lookup"><span data-stu-id="9e14e-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="9e14e-120">Markera ett objekt i listan om du vill visa detaljerad information, inklusive filens URL.</span><span class="sxs-lookup"><span data-stu-id="9e14e-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="9e14e-121">Välj en tillgänglig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9e14e-121">Choose an available action.</span></span>
    
  - <span data-ttu-id="9e14e-122">Välj **Släpp fil** om du vill avblockera filen.</span><span class="sxs-lookup"><span data-stu-id="9e14e-122">Choose **Release file** to unblock the file.</span></span> 
    
    <span data-ttu-id="9e14e-123">Välj **Skicka rapport till Microsoft** om du vill rapportera filen som ett falskt positivt till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e14e-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="9e14e-124">Välj **Hämta fil** om du vill undersöka filen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9e14e-124">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="9e14e-125">Välj **Ta bort från karantän** om du vill ta bort filen från listan över objekt i karantän.</span><span class="sxs-lookup"><span data-stu-id="9e14e-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="9e14e-126">Om du väljer det här alternativet måste du också ta bort filen från respektive bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e14e-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="9e14e-127">Det här alternativet avblockerar inte en fil från att öppnas eller delas.</span><span class="sxs-lookup"><span data-stu-id="9e14e-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="9e14e-128">Välj **Stäng** om du vill stänga informationen för ett markerat objekt.</span><span class="sxs-lookup"><span data-stu-id="9e14e-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

