---
title: Förbereda Office-distribution genom Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du installerar 32-bitars Office-program automatiskt på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580063"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="8ac4f-103">Förbereda Office-distribution genom Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="8ac4f-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="8ac4f-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="8ac4f-105">Förbereda för automatisk installation av Office-program på klientdatorer</span><span class="sxs-lookup"><span data-stu-id="8ac4f-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="8ac4f-106">Du kan använda Microsoft 365 Business Premium för att automatiskt installera 32-bitars Office-program på Windows 10-datorer och hålla dem aktuella med uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="8ac4f-107">Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:</span><span class="sxs-lookup"><span data-stu-id="8ac4f-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="8ac4f-108">Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).</span><span class="sxs-lookup"><span data-stu-id="8ac4f-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="8ac4f-109">eller</span><span class="sxs-lookup"><span data-stu-id="8ac4f-109">or</span></span>
    
- <span data-ttu-id="8ac4f-110">har en befintlig Klicka-och-kör-version av Office installerad.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="8ac4f-111">Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="8ac4f-112">Om du ser **Office-uppdateringar** enligt följande bild har installationen utförts med Klicka-och-kör.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="8ac4f-114">**Vem drar nytta av den här funktionen?**</span><span class="sxs-lookup"><span data-stu-id="8ac4f-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="8ac4f-115">Användaren vars dator:</span><span class="sxs-lookup"><span data-stu-id="8ac4f-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="8ac4f-116">**Har**  en användarlicens för Windows 10 Business, en aktiv Microsoft 365 för företag-licens, Windows 10 Creators Update och är ansluten till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="8ac4f-117">**Inte har** 64-bitars Office-program (exempel: Word, Excel och PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="8ac4f-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="8ac4f-118">Den här funktionen är inget bra alternativ om 64-bitarsversionen av Office-programmen är ett krav eftersom det inte finns något stöd för att starta en 64-bitars Klicka-och-kör-version av Office 2016 från administratörskonsolen för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="8ac4f-119">**Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project).</span><span class="sxs-lookup"><span data-stu-id="8ac4f-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="8ac4f-120">Microsoft 365 för företag uppgraderar Office till Klicka-och-kör-versionen av Office 2016 och det fungerar inte med fristående Office 2016 MSI-program.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="8ac4f-121">I följande tabell visas vilka åtgärder som slutanvändare/administratörer kan behöva vidta, beroende på starttillståndet, för att få en lyckad 32-bitars Klicka-och-kör-version av Office-distribution från administratörskonsolen för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="8ac4f-122">**Status vid start av Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="8ac4f-122">**Starting Office install status**</span></span>|<span data-ttu-id="8ac4f-123">**Åtgärd att vidta innan Office-installationen av Microsoft 365 för företag**</span><span class="sxs-lookup"><span data-stu-id="8ac4f-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="8ac4f-124">**Slutstatus**</span><span class="sxs-lookup"><span data-stu-id="8ac4f-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ac4f-125">Ingen Office-programsvit installerad</span><span class="sxs-lookup"><span data-stu-id="8ac4f-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="8ac4f-126">Ingen</span><span class="sxs-lookup"><span data-stu-id="8ac4f-126">None</span></span>  <br/> |<span data-ttu-id="8ac4f-127">32-bitars office 2016 installeras med Klicka-och-kör</span><span class="sxs-lookup"><span data-stu-id="8ac4f-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="8ac4f-128">Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="8ac4f-129">Ingen</span><span class="sxs-lookup"><span data-stu-id="8ac4f-129">None</span></span>  <br/> |<span data-ttu-id="8ac4f-130">Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\***</span><span class="sxs-lookup"><span data-stu-id="8ac4f-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="8ac4f-131">Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-bitarsversionen av fristående Office-program (till exempel Visio och Project)</span><span class="sxs-lookup"><span data-stu-id="8ac4f-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="8ac4f-132">Ingen</span><span class="sxs-lookup"><span data-stu-id="8ac4f-132">None</span></span>  <br/> |<span data-ttu-id="8ac4f-133">Fristående program påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="8ac4f-134">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="8ac4f-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="8ac4f-135">Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="8ac4f-136">Ingen</span><span class="sxs-lookup"><span data-stu-id="8ac4f-136">None</span></span>  <br/> |<span data-ttu-id="8ac4f-137">Fristående program påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="8ac4f-138">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="8ac4f-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="8ac4f-139">Alla befintliga 64-bitars Klicka-och-kör-versioner av Office</span><span class="sxs-lookup"><span data-stu-id="8ac4f-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="8ac4f-140">Avinstallera 64-bitars Office-programmen om det går bra att ersätta dem med 32-bitars Office-program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="8ac4f-141">Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016</span><span class="sxs-lookup"><span data-stu-id="8ac4f-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="8ac4f-142">En befintlig MSI-installation av Office 2016 med eller utan fristående program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="8ac4f-143">Avinstallera MSI-versionen av Office 2016.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="8ac4f-p106">32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="8ac4f-146">En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program</span><span class="sxs-lookup"><span data-stu-id="8ac4f-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="8ac4f-147">Ingen</span><span class="sxs-lookup"><span data-stu-id="8ac4f-147">None</span></span>  <br/> |<span data-ttu-id="8ac4f-148">32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)</span><span class="sxs-lookup"><span data-stu-id="8ac4f-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="8ac4f-149">**( \* ) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt programfel.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="8ac4f-150">En korrigering pågår.</span><span class="sxs-lookup"><span data-stu-id="8ac4f-150">A fix is in progress.</span></span> 
  
