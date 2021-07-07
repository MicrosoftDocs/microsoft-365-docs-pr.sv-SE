---
title: Riktlinjer för testpaket
description: Läs riktlinjerna för testpaket
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
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323049"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="ca8ab-103">Riktlinjer för testpaket</span><span class="sxs-lookup"><span data-stu-id="ca8ab-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="ca8ab-104">1. Skript som refererar</span><span class="sxs-lookup"><span data-stu-id="ca8ab-104">1.   Script referencing</span></span>

<span data-ttu-id="ca8ab-105">När du överför .zip en fil till portalen packas allt innehåll i filen upp i en rotmapp.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="ca8ab-106">Du behöver inte skriva någon kod för att göra den här första packa upp åtgärden.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="ca8ab-107">Du kan också referera till alla filer .zip filen genom att använda sökvägen i förhållande till zip-filen som laddats upp.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="ca8ab-108">I exemplet nedan visar vi hur du kan referera till binärvärden/skript från inmatningsfältet på fliken Uppgifter. Texten i blått ska skrivas in i **fältet Skriptsökväg** **utan citattecken.**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="ca8ab-109">Det är viktigt att du är medveten om innehållet i ZIP-filen innan du laddar upp den.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="ca8ab-110">När du zippar en mapp skapar din lokala dator ofta en huvudmapp under ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="ca8ab-111">I det här fallet visas referensen i fetstil **nedan:**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="ca8ab-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="ca8ab-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="ca8ab-114">Script.ps1 – **"Contoso_App_Folder/mapp1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="ca8ab-115">Ibland kan zip-filen ha filer eller innehåll direkt under det, det vill säga ingen mapp på andra nivån:</span><span class="sxs-lookup"><span data-stu-id="ca8ab-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="ca8ab-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="ca8ab-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="ca8ab-118">Script.ps1 – **"mapp1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="ca8ab-119">2. Körning av skript</span><span class="sxs-lookup"><span data-stu-id="ca8ab-119">2.   Script execution</span></span>

<span data-ttu-id="ca8ab-120">**In-box-tester:** Programpaketet måste innehålla minst tre PowerShell-skript som kör oövervakad installation, start och stängning av programmet och dess beroenden.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="ca8ab-121">Varje skript ska hantera kontroll av egna krav, verifiera att det har lyckats och rensa efter sig själv (om det behövs).</span><span class="sxs-lookup"><span data-stu-id="ca8ab-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="ca8ab-122">**Funktionstester:** Programpaketet måste innehålla minst ett PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="ca8ab-123">Där mer än ett skript tillhandahålls körs skripten i överföringssekvens och ett fel i ett visst skript stoppar efterföljande skript från att köras.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="ca8ab-124">Skriptkrav</span><span class="sxs-lookup"><span data-stu-id="ca8ab-124">Script requirements</span></span>

<span data-ttu-id="ca8ab-125">• PowerShell version 5.1+</span><span class="sxs-lookup"><span data-stu-id="ca8ab-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="ca8ab-126">• Ej uppövervakad körning</span><span class="sxs-lookup"><span data-stu-id="ca8ab-126">•   Unattended execution</span></span>    

<span data-ttu-id="ca8ab-127">• Felreturkod</span><span class="sxs-lookup"><span data-stu-id="ca8ab-127">•   Error return code</span></span>               

<span data-ttu-id="ca8ab-128">• Validera framgången</span><span class="sxs-lookup"><span data-stu-id="ca8ab-128">•   Validate success</span></span>            

<span data-ttu-id="ca8ab-129">• Loggning för skriptspecifik loggmapp</span><span class="sxs-lookup"><span data-stu-id="ca8ab-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="ca8ab-130">Varje skript måste köras helt oövervakat för att köras i testpipelinet.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="ca8ab-131">Skripten bör returnera "0" när de har slutförts och en felkod som inte är noll om det uppstår fel vid körning.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="ca8ab-132">Varje skript bör verifiera att det har körts.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="ca8ab-133">T.ex.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-133">E.g.</span></span> <span data-ttu-id="ca8ab-134">Installationsskriptet bör kontrollera om det finns vissa binärfiler och/eller registernycklar i systemet, efter att binär installationsprogrammet har avslutats, för att säkerställa att installationen lyckades.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="ca8ab-135">Detta är nödvändigt för att korrekt diagnostisera var fel uppstår under en testkörning, t.ex. det går inte att installera programmet jämfört med att starta det.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="ca8ab-136">**Undvik följande:** Skript bör inte starta om datorn. Om det behövs en omstart anger du detta under uppladdningen av dina skript.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="ca8ab-137">3. Loggsamling</span><span class="sxs-lookup"><span data-stu-id="ca8ab-137">3.   Log collection</span></span>

<span data-ttu-id="ca8ab-138">Varje skript bör mata ut alla loggar som genereras i en mapp med namnet ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="ca8ab-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="ca8ab-139">Alla mappar i katalogen ```logs``` kopieras och presenteras för nedladdning på ```Test Results``` sidan.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="ca8ab-140">Installationsskriptet (som kan finnas i **app-/skript/installationskatalogen)** kan till exempel mata ut sina loggar till: **loggar/install.log,** så att den slutliga loggen blir på: **Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="ca8ab-141">Systemet hämtar filen tillsammans med ```install.log``` andra filer i andra mappar och ```logs``` sorterar den för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="ca8ab-142">4. Binärfiler för program</span><span class="sxs-lookup"><span data-stu-id="ca8ab-142">4.   Application binaries</span></span>

<span data-ttu-id="ca8ab-143">Eventuella binärfiler och beroenden bör inkluderas i den enda zip-filen.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="ca8ab-144">De bör omfatta allt som behövs för installationen av programmet (t.ex. programinstallationsprogrammet). Om programmet är beroende av något ramverk, till exempel .NET Core/Standard eller .NET Framework, bör dessa inkluderas i filen och refereras till korrekt i de angivna skripten.</span><span class="sxs-lookup"><span data-stu-id="ca8ab-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="ca8ab-145">Den uppladdade ZIP-filen får inte ha några blanksteg eller specialtecken i namnet</span><span class="sxs-lookup"><span data-stu-id="ca8ab-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca8ab-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ca8ab-146">Next steps</span></span>

<span data-ttu-id="ca8ab-147">Gå till nästa artikel för att visa några **vanliga frågor och svar**</span><span class="sxs-lookup"><span data-stu-id="ca8ab-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ca8ab-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ca8ab-148">Next step</span></span>](faq.md)
