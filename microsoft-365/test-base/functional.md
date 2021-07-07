---
title: Funktionstestning på testbas
description: Information om hur du testar programmet med befintliga automatiska funktionstester
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323229"
---
# <a name="functional-testing"></a><span data-ttu-id="3e4cd-103">Funktionstestning</span><span class="sxs-lookup"><span data-stu-id="3e4cd-103">Functional testing</span></span>

<span data-ttu-id="3e4cd-104">Som programvaruleverantör kan du nu utföra anpassade funktionstester med valfri testram – via självbetjäning för M365-portalen.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="3e4cd-105">När vi först startade tjänsten erbjöd vi de färdiga testerna, som är en fördefinierad uppsättning tester som drivs via standardiserade skript.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="3e4cd-106">Detta kunde dock inte få fullständig testtäckning för många oberoende programvaruleverantörer (ISV).</span><span class="sxs-lookup"><span data-stu-id="3e4cd-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="3e4cd-107">Som svar på din feedback ger vi våra ISV möjlighet att ladda upp automatiska funktionstest.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="3e4cd-108">Följ stegen nedan om du vill använda den här funktionen:</span><span class="sxs-lookup"><span data-stu-id="3e4cd-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="3e4cd-109">Upload dina filer (binärfiler, beroenden och skript) som ett enda .zip paket.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="3e4cd-110">Välj om du vill starta om virtuella testdatorer vid olika körningspunkter.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="3e4cd-111">Hantera tillgängliga alternativ för dina skript.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="3e4cd-112">Välj när den ska Windows på den virtuella maskinerna under körning.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="3e4cd-113">Detaljerade beskrivningar av stegen ovan är markerade nedan:</span><span class="sxs-lookup"><span data-stu-id="3e4cd-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="3e4cd-114">**Upload ett funktionellt testpaket**</span><span class="sxs-lookup"><span data-stu-id="3e4cd-114">**Upload a functional test package**</span></span>

<span data-ttu-id="3e4cd-115">Kom igång genom att gå till Upload-sidan genom att välja Upload nytt program under Programkatalog på navigeringsmenyn till vänster på Testbas för M365-portalen i Azure.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="3e4cd-116">Därifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="3e4cd-116">From there:</span></span>

<span data-ttu-id="3e4cd-117">Flik 1 – Ange grundläggande information.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="3e4cd-118">Ange namnet på och versionen av programmet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-118">Provide the name and version of your application.</span></span> <span data-ttu-id="3e4cd-119">I alternativet Typ av test väljer du ```Functional tests``` .</span><span class="sxs-lookup"><span data-stu-id="3e4cd-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="3e4cd-120">*Observera att alternativet OOB (out-of-Box) är obligatoriskt som standard.*</span><span class="sxs-lookup"><span data-stu-id="3e4cd-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Välj fliken funktionstestning](Media/functional_testing_tab1.png)

<span data-ttu-id="3e4cd-122">Flik 2 – Upload de olika komponenterna i paketet genom att ladda upp en ZIP-fil med hela testet (binärfiler, beroenden, skript osv.).</span><span class="sxs-lookup"><span data-stu-id="3e4cd-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="3e4cd-123">Se aka.ms/usl-package-outline för mer information.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="3e4cd-124">(Obs! Både in-box-testskripten och innehållet i funktionstestet bör placeras i samma zip-fil).</span><span class="sxs-lookup"><span data-stu-id="3e4cd-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="3e4cd-125">För närvarande är filstorleken begränsad till 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="3e4cd-126">Flik 3 – Konfigurera de inflikar- och funktionstestaktiviteterna.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="3e4cd-127">Välj sökvägarna till PowerShell-skripten som installerar, startar, stänger och avinstallerar programmet (för In-of-Box) samt sökvägarna till alla dina egna skript för att utföra funktionstestet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="3e4cd-128">**(Obs! Ett skript för att avinstallera programmet är valfritt).**</span><span class="sxs-lookup"><span data-stu-id="3e4cd-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="3e4cd-129">För närvarande kan du ladda upp mellan 1 och 8 skript för dina funktionstester.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="3e4cd-130">(Kommentera det här inlägget på ett bra sätt om du behöver fler skript!)</span><span class="sxs-lookup"><span data-stu-id="3e4cd-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Upload upp till 8 skript med funktionstester](Media/functional_testing_tab3.png)

<span data-ttu-id="3e4cd-132">(Valfritt) Konfigurera en omstart efter installationen.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="3e4cd-133">För vissa program krävs en omstart efter installationen.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="3e4cd-134">Välj för det specifika skriptet på fliken Uppgifter om du vill att en ```Reboot After Execution``` omstart ska ske efter körningen av skriptet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="3e4cd-135">Flik 4 – Välj när Windows-uppdateringen installeras: Programmet för korrigeringen Windows Uppdatering utförs innan något skript som du väljer.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="3e4cd-136">Vi rekommenderar att du installerar en Windows uppdatering efter programmets installation för att nära efterlikna dina verkliga användningsscenarier.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![Uppdateringen Windows kan installeras efter ett visst skript](Media/functional_testing_tab4.png)

<span data-ttu-id="3e4cd-138">Flik 5 – Granska och skapa paketet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="3e4cd-139">När du har utfört stegen ovan väljer du att ```Create``` slutföra uppladdningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="3e4cd-140">När paketet har skapats kan du kontrollera verifieringsstatus för paketet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="3e4cd-141">Vi kör ett första test för att installera, starta, stänga och avinstallera programmet.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="3e4cd-142">Det gör att vi kan verifiera att ditt paket kan installeras på vår tjänst utan fel.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="3e4cd-143">Verifieringsprocessen kan ta upp till 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="3e4cd-144">När verifieringen är klar kan du se status i ```Manage packages``` menyn, vilket är en av två poster:</span><span class="sxs-lookup"><span data-stu-id="3e4cd-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="3e4cd-145">Verifieringen lyckas: Paketet testas automatiskt mot förhandsuppdateringar Windows de OS-versioner du valt.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="3e4cd-146">eller</span><span class="sxs-lookup"><span data-stu-id="3e4cd-146">or</span></span>
2. <span data-ttu-id="3e4cd-147">Verifieringen misslyckas: Du måste undersöka orsakerna till felet, åtgärda problemet och ladda upp paketet på ny plats.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="3e4cd-148">Du får också ett meddelande om båda resultaten via meddelandeikonen i Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="3e4cd-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
