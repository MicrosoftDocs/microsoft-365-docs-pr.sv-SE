---
title: Förbereda Office-distribution genom Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du automatiskt installerar 32-bitars Office-apparna på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: fe1f946e4a216050e533604afa7c6e74e7b5980f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288404"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="e407e-103">Förbereda Office-distribution genom Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e407e-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="e407e-104">Förbereda för automatisk installation av Office-program på klientdatorer</span><span class="sxs-lookup"><span data-stu-id="e407e-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="e407e-105">Du kan använda Microsoft 365 Business för att automatiskt installera 32-bitars Office-program på datorer med Windows 10 och för att automatiskt uppdatera dem till de senaste versionerna.</span><span class="sxs-lookup"><span data-stu-id="e407e-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="e407e-106">Det här fungerar bäst om användarens dator kör Windows 10 Business och:</span><span class="sxs-lookup"><span data-stu-id="e407e-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="e407e-107">Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).</span><span class="sxs-lookup"><span data-stu-id="e407e-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="e407e-108">eller</span><span class="sxs-lookup"><span data-stu-id="e407e-108">or</span></span>
    
- <span data-ttu-id="e407e-109">har en befintlig Klicka-och-kör-version av Office installerad.</span><span class="sxs-lookup"><span data-stu-id="e407e-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="e407e-p101">Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du ser Office-uppdateringar enligt följande bild utfördes installationen med Klicka-och-kör.</span><span class="sxs-lookup"><span data-stu-id="e407e-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="e407e-113">**Vem kan dra fördel av den här funktionen**</span><span class="sxs-lookup"><span data-stu-id="e407e-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="e407e-114">Användaren vars dator:</span><span class="sxs-lookup"><span data-stu-id="e407e-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="e407e-115">**har** en användarlicens för Windows 10 Business, en aktiv Microsoft 365 Business-licens och Windows 10 Creators Update samt är ansluten till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e407e-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="e407e-p102">**inte har** 64-bitars Office-program (exempel: Word, Excel och Powerpoint). Den här funktionen är inget bra alternativ om 64-bitarsversionen av Office-programmen är ett krav eftersom funktionen saknar stöd för att starta en 64-bitars Klicka-och-kör-version av Office 2016 från Microsoft 365 Business-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="e407e-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="e407e-p103">**Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 Business uppgraderar Office till Klicka-och-kör-versionen av Office 2016 och det fungerar inte med Office 2016 MSI fristående program.</span><span class="sxs-lookup"><span data-stu-id="e407e-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="e407e-120">Följande tabell visar, beroende på startstatus, de åtgärder som användaren eller administratören behöver vidta för en lyckad distribution av 32-bitars Klicka-och-kör-version av Office från Microsoft 365 Business-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="e407e-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="e407e-121">**Status vid start av Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="e407e-121">**Starting Office install status**</span></span>|<span data-ttu-id="e407e-122">**Åtgärd att vidta före Microsoft 365 Business Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="e407e-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="e407e-123">**Slutstatus**</span><span class="sxs-lookup"><span data-stu-id="e407e-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e407e-124">Ingen Office-programsvit installerad</span><span class="sxs-lookup"><span data-stu-id="e407e-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="e407e-125">Ingen</span><span class="sxs-lookup"><span data-stu-id="e407e-125">None</span></span>  <br/> |<span data-ttu-id="e407e-126">32-bitarsversionen av Office 2016 installeras med Klicka-och-kör</span><span class="sxs-lookup"><span data-stu-id="e407e-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="e407e-127">Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program</span><span class="sxs-lookup"><span data-stu-id="e407e-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="e407e-128">Ingen</span><span class="sxs-lookup"><span data-stu-id="e407e-128">None</span></span>  <br/> |<span data-ttu-id="e407e-129">Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\***</span><span class="sxs-lookup"><span data-stu-id="e407e-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="e407e-130">Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-versioner av fristående Office-program (till exempel Visio och Project)</span><span class="sxs-lookup"><span data-stu-id="e407e-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="e407e-131">Ingen</span><span class="sxs-lookup"><span data-stu-id="e407e-131">None</span></span>  <br/> |<span data-ttu-id="e407e-p104">Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="e407e-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="e407e-134">Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program</span><span class="sxs-lookup"><span data-stu-id="e407e-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="e407e-135">Ingen</span><span class="sxs-lookup"><span data-stu-id="e407e-135">None</span></span>  <br/> |<span data-ttu-id="e407e-p105">Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="e407e-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="e407e-138">Alla befintliga 64-bitars Klicka-och-kör-versioner av Office</span><span class="sxs-lookup"><span data-stu-id="e407e-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="e407e-139">Avinstallera 64-bitars Office-program om det går bra att ersätta dem med 32-bitars Office-program</span><span class="sxs-lookup"><span data-stu-id="e407e-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="e407e-140">Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016</span><span class="sxs-lookup"><span data-stu-id="e407e-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="e407e-141">En befintlig MSI-installation av Office 2016 med eller utan fristående program</span><span class="sxs-lookup"><span data-stu-id="e407e-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="e407e-142">Avinstallera MSI-versionen av Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e407e-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="e407e-p106">32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program</span><span class="sxs-lookup"><span data-stu-id="e407e-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="e407e-145">En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program</span><span class="sxs-lookup"><span data-stu-id="e407e-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="e407e-146">Ingen</span><span class="sxs-lookup"><span data-stu-id="e407e-146">None</span></span>  <br/> |<span data-ttu-id="e407e-147">32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)</span><span class="sxs-lookup"><span data-stu-id="e407e-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="e407e-p107">**(\*) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt programfel. En programkorrigering är under utveckling.</span><span class="sxs-lookup"><span data-stu-id="e407e-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


