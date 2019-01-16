---
title: Förbereda Office-distribution genom Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du automatiskt installera 32-bitars Office apps på Windows 10 datorer och hålla dem uppdaterade.
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982159"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="fd87b-103">Förbereda Office-distribution genom Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fd87b-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="fd87b-104">Förbereda för automatisk installation av Office-program på klientdatorer</span><span class="sxs-lookup"><span data-stu-id="fd87b-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="fd87b-105">Du kan använda Microsoft 365 Business för att automatiskt installera 32-bitars Office-program på datorer med Windows 10 och för att automatiskt uppdatera dem till de senaste versionerna.</span><span class="sxs-lookup"><span data-stu-id="fd87b-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="fd87b-106">Det här fungerar bäst om användarens dator kör Windows 10 Business och:</span><span class="sxs-lookup"><span data-stu-id="fd87b-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="fd87b-107">Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).</span><span class="sxs-lookup"><span data-stu-id="fd87b-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="fd87b-108">eller</span><span class="sxs-lookup"><span data-stu-id="fd87b-108">or</span></span>
    
- <span data-ttu-id="fd87b-109">har en befintlig Klicka-och-kör-version av Office installerad.</span><span class="sxs-lookup"><span data-stu-id="fd87b-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="fd87b-p101">Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du ser Office-uppdateringar enligt följande bild utfördes installationen med Klicka-och-kör.</span><span class="sxs-lookup"><span data-stu-id="fd87b-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="fd87b-113">**Vem kan dra fördel av den här funktionen**</span><span class="sxs-lookup"><span data-stu-id="fd87b-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="fd87b-114">Användaren vars dator:</span><span class="sxs-lookup"><span data-stu-id="fd87b-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="fd87b-115">**har** en användarlicens för Windows 10 Business, en aktiv Microsoft 365 Business-licens och Windows 10 Creators Update samt är ansluten till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd87b-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="fd87b-p102">**inte har** 64-bitars Office-program (exempel: Word, Excel och Powerpoint). Den här funktionen är inget bra alternativ om 64-bitarsversionen av Office-programmen är ett krav eftersom funktionen saknar stöd för att starta en 64-bitars Klicka-och-kör-version av Office 2016 från Microsoft 365 Business-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="fd87b-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="fd87b-p103">**Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 Business uppgraderar Office till Klicka-och-kör-versionen av Office 2016 och det fungerar inte med Office 2016 MSI fristående program.</span><span class="sxs-lookup"><span data-stu-id="fd87b-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="fd87b-120">Följande tabell visar, beroende på startstatus, de åtgärder som användaren eller administratören behöver vidta för en lyckad distribution av 32-bitars Klicka-och-kör-version av Office från Microsoft 365 Business-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="fd87b-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="fd87b-121">**Status vid start av Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="fd87b-121">**Starting Office install status**</span></span>|<span data-ttu-id="fd87b-122">**Åtgärd att vidta före Microsoft 365 Business Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="fd87b-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="fd87b-123">**Slutstatus**</span><span class="sxs-lookup"><span data-stu-id="fd87b-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd87b-124">Ingen Office-programsvit installerad</span><span class="sxs-lookup"><span data-stu-id="fd87b-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="fd87b-125">Ingen</span><span class="sxs-lookup"><span data-stu-id="fd87b-125">None</span></span>  <br/> |<span data-ttu-id="fd87b-126">32-bitarsversionen av Office 2016 installeras med Klicka-och-kör</span><span class="sxs-lookup"><span data-stu-id="fd87b-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="fd87b-127">Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program</span><span class="sxs-lookup"><span data-stu-id="fd87b-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="fd87b-128">Ingen</span><span class="sxs-lookup"><span data-stu-id="fd87b-128">None</span></span>  <br/> |<span data-ttu-id="fd87b-129">Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\***</span><span class="sxs-lookup"><span data-stu-id="fd87b-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="fd87b-130">Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-versioner av fristående Office-program (till exempel Visio och Project)</span><span class="sxs-lookup"><span data-stu-id="fd87b-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="fd87b-131">Ingen</span><span class="sxs-lookup"><span data-stu-id="fd87b-131">None</span></span>  <br/> |<span data-ttu-id="fd87b-p104">Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fd87b-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="fd87b-134">Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program</span><span class="sxs-lookup"><span data-stu-id="fd87b-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="fd87b-135">Ingen</span><span class="sxs-lookup"><span data-stu-id="fd87b-135">None</span></span>  <br/> |<span data-ttu-id="fd87b-p105">Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fd87b-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="fd87b-138">Alla befintliga 64-bitars Klicka-och-kör-versioner av Office</span><span class="sxs-lookup"><span data-stu-id="fd87b-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="fd87b-139">Avinstallera 64-bitars Office-program om det går bra att ersätta dem med 32-bitars Office-program</span><span class="sxs-lookup"><span data-stu-id="fd87b-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="fd87b-140">Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fd87b-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="fd87b-141">En befintlig MSI-installation av Office 2016 med eller utan fristående program</span><span class="sxs-lookup"><span data-stu-id="fd87b-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="fd87b-142">Avinstallera MSI-versionen av Office 2016.</span><span class="sxs-lookup"><span data-stu-id="fd87b-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="fd87b-p106">32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program</span><span class="sxs-lookup"><span data-stu-id="fd87b-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="fd87b-145">En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program</span><span class="sxs-lookup"><span data-stu-id="fd87b-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="fd87b-146">Ingen</span><span class="sxs-lookup"><span data-stu-id="fd87b-146">None</span></span>  <br/> |<span data-ttu-id="fd87b-147">32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)</span><span class="sxs-lookup"><span data-stu-id="fd87b-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="fd87b-p107">**(\*) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt programfel. En programkorrigering är under utveckling.</span><span class="sxs-lookup"><span data-stu-id="fd87b-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


