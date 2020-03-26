---
title: Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams
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
description: Lär dig var du kan visa information om skadliga filer som identifierats i SharePoint, OneDrive eller Teams och hur du vidtar åtgärder för dessa filer.
ms.openlocfilehash: 3a14c7d69c7081be6bd08840eb8f52c5e11d4be7
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955561"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="531c1-103">Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="531c1-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="531c1-104">[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokumentbibliotek och gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="531c1-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="531c1-105">När en skadlig fil upptäcks blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den förrän ytterligare åtgärder vidtas av organisationens säkerhetsteam.</span><span class="sxs-lookup"><span data-stu-id="531c1-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="531c1-106">Läs den här artikeln om du vill lära dig hur du visar information om identifierade filer och vilka åtgärder som ska vidtas.</span><span class="sxs-lookup"><span data-stu-id="531c1-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="531c1-107">För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha de behörigheter som krävs [för Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="531c1-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="531c1-108">Visa rapporter med information om identifierade filer</span><span class="sxs-lookup"><span data-stu-id="531c1-108">View reports with information about detected files</span></span>

<span data-ttu-id="531c1-109">Om du vill visa status och detaljerad information om filer som har identifierats av Office 365 ATP kan du använda rapporten Status för hotskydd.</span><span class="sxs-lookup"><span data-stu-id="531c1-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="531c1-110">I [Säkerhetsefterlevnadscenter &amp; för Office 365](https://protection.office.com)väljer du **Rapporter om** \> **skydd av instrumentpanelshotskydd** **Dashboard** \> .</span><span class="sxs-lookup"><span data-stu-id="531c1-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="531c1-111">I det övre högra hörnet av rapporten väljer du **Visa informationstabell**.</span><span class="sxs-lookup"><span data-stu-id="531c1-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="531c1-112">Visa listan över filer som har identifierats i rapporten.</span><span class="sxs-lookup"><span data-stu-id="531c1-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="531c1-113">Markera ett objekt i listan om du vill visa detaljerad information, inklusive vidtagna åtgärder, filnamnet, filsökvägen med mera.</span><span class="sxs-lookup"><span data-stu-id="531c1-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="531c1-114">Välj fliken **Avancerad analys** om du vill visa information, till exempel observerad beteende- och analysinformation.</span><span class="sxs-lookup"><span data-stu-id="531c1-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="531c1-115">Visa och vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="531c1-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="531c1-116">I Office 365 &amp; Security Compliance Center väljer du **Review** \> **Karantän** **för granskning av hothantering** \> .</span><span class="sxs-lookup"><span data-stu-id="531c1-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="531c1-117">(Du kan också [https://protection.office.com/quarantine](https://protection.office.com/quarantine)gå direkt till .)</span><span class="sxs-lookup"><span data-stu-id="531c1-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="531c1-118">I det övre vänstra hörnet ändrar du rullgardinsmenyn från **e-post** till **filer**.</span><span class="sxs-lookup"><span data-stu-id="531c1-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="531c1-119">Om resultatlistan innehåller för många objekt använder du **funktionen Filter** för att begränsa markeringen.</span><span class="sxs-lookup"><span data-stu-id="531c1-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="531c1-120">Markera ett objekt i listan om du vill visa detaljerad information, inklusive filens URL.</span><span class="sxs-lookup"><span data-stu-id="531c1-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="531c1-121">Välj en tillgänglig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="531c1-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="531c1-122">Välj **Släpp-fil** för att avblockera filen.</span><span class="sxs-lookup"><span data-stu-id="531c1-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="531c1-123">Välj **Skicka rapport till Microsoft** om du vill rapportera filen som ett falskt positivt till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="531c1-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="531c1-124">Välj **Hämta fil** för att undersöka filen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="531c1-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="531c1-125">Välj **Ta bort från karantänen** om du vill ta bort filen från listan över objekt i karantän.</span><span class="sxs-lookup"><span data-stu-id="531c1-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="531c1-126">Om du väljer det här alternativet måste du också ta bort filen från respektive bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="531c1-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="531c1-127">Det här alternativet avblockerar inte en fil från att öppnas eller delas.</span><span class="sxs-lookup"><span data-stu-id="531c1-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="531c1-128">Välj **Stäng** om du vill stänga informationen för ett markerat objekt.</span><span class="sxs-lookup"><span data-stu-id="531c1-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

