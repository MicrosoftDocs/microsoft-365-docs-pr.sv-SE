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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du installerar 32-bitars Office-appar automatiskt på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: b5f01bc9bb10765929f3c6bdd5908e8b48a51a11
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633108"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="fc8bd-103">Förbereda för Office-klientdistribution av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fc8bd-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="fc8bd-104">Förbereda för automatisk installation av Office-program på klientdatorer</span><span class="sxs-lookup"><span data-stu-id="fc8bd-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="fc8bd-105">Du kan använda Microsoft 365 för företag för att automatiskt installera 32-bitars Office-appar på Windows 10-datorer och hålla dem aktuella med uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-105">You can use Microsoft 365 for business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="fc8bd-106">Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:</span><span class="sxs-lookup"><span data-stu-id="fc8bd-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="fc8bd-107">Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).</span><span class="sxs-lookup"><span data-stu-id="fc8bd-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="fc8bd-108">eller</span><span class="sxs-lookup"><span data-stu-id="fc8bd-108">or</span></span>
    
- <span data-ttu-id="fc8bd-109">har en befintlig Klicka-och-kör-version av Office installerad.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="fc8bd-110">Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="fc8bd-111">Om **Office-uppdateringar** visas i följande bild gjordes installationen med Klicka-och-kör.If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="fc8bd-113">**Vem drar nytta av att ha den här funktionen**</span><span class="sxs-lookup"><span data-stu-id="fc8bd-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="fc8bd-114">Användaren vars dator:</span><span class="sxs-lookup"><span data-stu-id="fc8bd-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="fc8bd-115">**Har** en Windows 10 Business-användarlicens, en aktiv Microsoft 365 för företag-licens, Windows 10 Creators Update och ansluts till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="fc8bd-116">**Har inte** 64-bitars Office-program (t.ex.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="fc8bd-117">Om 64-bitars Office-appar krävs passar den här funktionen inte bra eftersom det inte finns något stöd för att utlösa en 64-bitars 2016 Click-to-Run-version av Office från administratörskonsolen Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="fc8bd-118">**Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project).</span><span class="sxs-lookup"><span data-stu-id="fc8bd-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="fc8bd-119">Microsoft 365 för företag uppgraderar Office till Click-to-Run-versionen av Office 2016 och det fungerar inte med fristående OFFICE 2016-appar.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-119">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="fc8bd-120">I följande tabell visas vilken åtgärd slutanvändarna/administratörerna kan behöva vidta, beroende på deras starttillstånd, för att ha en lyckad 32-bitars Click-to-Run-version av Office-distribution från microsoft 365 för företag-administratörskonsolen.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="fc8bd-121">**Status vid start av Office-installationen**</span><span class="sxs-lookup"><span data-stu-id="fc8bd-121">**Starting Office install status**</span></span>|<span data-ttu-id="fc8bd-122">**Åtgärder som ska vidtas innan Microsoft 365 för företag Office installeras**</span><span class="sxs-lookup"><span data-stu-id="fc8bd-122">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="fc8bd-123">**Slutstatus**</span><span class="sxs-lookup"><span data-stu-id="fc8bd-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc8bd-124">Ingen Office-programsvit installerad</span><span class="sxs-lookup"><span data-stu-id="fc8bd-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="fc8bd-125">Ingen</span><span class="sxs-lookup"><span data-stu-id="fc8bd-125">None</span></span>  <br/> |<span data-ttu-id="fc8bd-126">Office 2016 32-bitars installeras med Klicka-och-kör</span><span class="sxs-lookup"><span data-stu-id="fc8bd-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="fc8bd-127">Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="fc8bd-128">Ingen</span><span class="sxs-lookup"><span data-stu-id="fc8bd-128">None</span></span>  <br/> |<span data-ttu-id="fc8bd-129">Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\***</span><span class="sxs-lookup"><span data-stu-id="fc8bd-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="fc8bd-130">Befintlig Klicka-och-kör 32-bitarsversion av Office och Klicka-och-kör 32-bitars eller 64-bitars fristående Office-appar (till exempel Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="fc8bd-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="fc8bd-131">Ingen</span><span class="sxs-lookup"><span data-stu-id="fc8bd-131">None</span></span>  <br/> |<span data-ttu-id="fc8bd-132">Fristående appar påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="fc8bd-133">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fc8bd-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="fc8bd-134">Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="fc8bd-135">Ingen</span><span class="sxs-lookup"><span data-stu-id="fc8bd-135">None</span></span>  <br/> |<span data-ttu-id="fc8bd-136">Fristående appar påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="fc8bd-137">Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fc8bd-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="fc8bd-138">Alla befintliga 64-bitars Klicka-och-kör-versioner av Office</span><span class="sxs-lookup"><span data-stu-id="fc8bd-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="fc8bd-139">Avinstallera 64-bitars Office-programmen om det är OK att ersätta dem med 32-bitars Office-program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="fc8bd-140">Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016</span><span class="sxs-lookup"><span data-stu-id="fc8bd-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="fc8bd-141">En befintlig MSI-installation av Office 2016 med eller utan fristående program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="fc8bd-142">Avinstallera MSI-versionen av Office 2016.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="fc8bd-p106">32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="fc8bd-145">En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program</span><span class="sxs-lookup"><span data-stu-id="fc8bd-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="fc8bd-146">Ingen</span><span class="sxs-lookup"><span data-stu-id="fc8bd-146">None</span></span>  <br/> |<span data-ttu-id="fc8bd-147">32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)</span><span class="sxs-lookup"><span data-stu-id="fc8bd-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="fc8bd-148">**(\*) Anmärkning:** Uppgraderar inte till Click-to-Run 32-bitarsversion av Office 2016 på grund av ett känt fel.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="fc8bd-149">En lösning pågår.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-149">A fix is in progress.</span></span> 
  
