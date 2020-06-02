---
title: Förbereda för Office-klientdistribution av Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du installerar 32-bitars Office-appar automatiskt på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470956"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="96ce0-103">Förbereda för Office-klientdistribution av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="96ce0-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="96ce0-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="96ce0-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="96ce0-105">Förbereda för automatisk installation av Office-program på klientdatorer</span><span class="sxs-lookup"><span data-stu-id="96ce0-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="96ce0-106">Du kan använda Microsoft 365 Business Premium för att automatiskt installera 32-bitars Office-appar på Windows 10-datorer och hålla dem aktuella med uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="96ce0-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="96ce0-107">Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:</span><span class="sxs-lookup"><span data-stu-id="96ce0-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="96ce0-108">Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).</span><span class="sxs-lookup"><span data-stu-id="96ce0-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="96ce0-109">eller</span><span class="sxs-lookup"><span data-stu-id="96ce0-109">or</span></span>
    
- <span data-ttu-id="96ce0-110">har en befintlig Klicka-och-kör-version av Office installerad.</span><span class="sxs-lookup"><span data-stu-id="96ce0-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="96ce0-111">Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program.</span><span class="sxs-lookup"><span data-stu-id="96ce0-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="96ce0-112">Om **Office-uppdateringar** visas i följande bild gjordes installationen med Klicka-och-kör.If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="96ce0-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="96ce0-114">**Vem drar nytta av att ha den här funktionen**</span><span class="sxs-lookup"><span data-stu-id="96ce0-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="96ce0-115">Användaren vars dator:</span><span class="sxs-lookup"><span data-stu-id="96ce0-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="96ce0-116">**Har** en Windows 10 Business-användarlicens, en aktiv Microsoft 365 för företag-licens, Windows 10 Creators Update och ansluts till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96ce0-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="96ce0-117">**Har inte** 64-bitars Office-program (t.ex.</span><span class="sxs-lookup"><span data-stu-id="96ce0-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="96ce0-118">Om 64-bitars Office-appar krävs passar den här funktionen inte bra eftersom det inte finns något stöd för att utlösa en 64-bitars 2016 Click-to-Run-version av Office från administratörskonsolen Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="96ce0-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="96ce0-119">**Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project).</span><span class="sxs-lookup"><span data-stu-id="96ce0-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="96ce0-120">Microsoft 365 för företag uppgraderar Office till Click-to-Run-versionen av Office 2016 och det fungerar inte med fristående OFFICE 2016-appar.</span><span class="sxs-lookup"><span data-stu-id="96ce0-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="96ce0-121">I följande tabell visas vilken åtgärd slutanvändarna/administratörerna kan behöva vidta, beroende på deras starttillstånd, för att ha en lyckad 32-bitars Click-to-Run-version av Office-distribution från microsoft 365 för företag-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="96ce0-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="96ce0-122">**Status vid start av Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="96ce0-122">**Starting Office install status**</span></span>|<span data-ttu-id="96ce0-123">**Åtgärder som ska vidtas innan Microsoft 365 för företag Office installeras**</span><span class="sxs-lookup"><span data-stu-id="96ce0-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="96ce0-124">**Slutstatus**</span><span class="sxs-lookup"><span data-stu-id="96ce0-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96ce0-125">Ingen Office-programsvit installerad</span><span class="sxs-lookup"><span data-stu-id="96ce0-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="96ce0-126">Inga</span><span class="sxs-lookup"><span data-stu-id="96ce0-126">None</span></span>  <br/> |<span data-ttu-id="96ce0-127">Office 2016 32-bitars installeras med Klicka-och-kör</span><span class="sxs-lookup"><span data-stu-id="96ce0-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="96ce0-128">Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program</span><span class="sxs-lookup"><span data-stu-id="96ce0-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="96ce0-129">Inga</span><span class="sxs-lookup"><span data-stu-id="96ce0-129">None</span></span>  <br/> |<span data-ttu-id="96ce0-130">Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\***</span><span class="sxs-lookup"><span data-stu-id="96ce0-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="96ce0-131">Befintlig Klicka-och-kör 32-bitarsversion av Office och Klicka-och-kör 32-bitars eller 64-bitars fristående Office-appar (till exempel Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="96ce0-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="96ce0-132">Inga</span><span class="sxs-lookup"><span data-stu-id="96ce0-132">None</span></span>  <br/> |<span data-ttu-id="96ce0-133">Fristående appar påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="96ce0-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="96ce0-134">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="96ce0-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="96ce0-135">Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program</span><span class="sxs-lookup"><span data-stu-id="96ce0-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="96ce0-136">Inga</span><span class="sxs-lookup"><span data-stu-id="96ce0-136">None</span></span>  <br/> |<span data-ttu-id="96ce0-137">Fristående appar påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="96ce0-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="96ce0-138">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="96ce0-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="96ce0-139">Alla befintliga 64-bitars Klicka-och-kör-versioner av Office</span><span class="sxs-lookup"><span data-stu-id="96ce0-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="96ce0-140">Avinstallera 64-bitars Office-programmen om det är OK att ersätta dem med 32-bitars Office-program</span><span class="sxs-lookup"><span data-stu-id="96ce0-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="96ce0-141">Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016</span><span class="sxs-lookup"><span data-stu-id="96ce0-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="96ce0-142">En befintlig MSI-installation av Office 2016 med eller utan fristående program</span><span class="sxs-lookup"><span data-stu-id="96ce0-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="96ce0-143">Avinstallera MSI-versionen av Office 2016.</span><span class="sxs-lookup"><span data-stu-id="96ce0-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="96ce0-p106">32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program</span><span class="sxs-lookup"><span data-stu-id="96ce0-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="96ce0-146">En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program</span><span class="sxs-lookup"><span data-stu-id="96ce0-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="96ce0-147">Ingen</span><span class="sxs-lookup"><span data-stu-id="96ce0-147">None</span></span>  <br/> |<span data-ttu-id="96ce0-148">32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)</span><span class="sxs-lookup"><span data-stu-id="96ce0-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="96ce0-149">**( \* ) Obs:** Uppgraderar inte till Click-to-Run 32-bitars version av Office 2016 på grund av ett känt fel.</span><span class="sxs-lookup"><span data-stu-id="96ce0-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="96ce0-150">En lösning pågår.</span><span class="sxs-lookup"><span data-stu-id="96ce0-150">A fix is in progress.</span></span> 
  
