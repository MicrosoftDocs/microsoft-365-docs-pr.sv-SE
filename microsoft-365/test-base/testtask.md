---
title: Ställa in testaktiviteterna
description: Ställa in testaktiviteterna
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322947"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="f0178-103">Steg 4: Fliken Uppgifter</span><span class="sxs-lookup"><span data-stu-id="f0178-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="f0178-104">På fliken uppgifter ska du ange sökvägar till testskripten som finns i zip-mappen som du har laddat upp under fliken binärfiler.</span><span class="sxs-lookup"><span data-stu-id="f0178-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="f0178-105">**In of Box-testskript:** Ange de relativa sökvägarna till installationen, starta, stäng och avinstallera skript.</span><span class="sxs-lookup"><span data-stu-id="f0178-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="f0178-106">Du kan också välja ytterligare inställningar för installationsskriptet.</span><span class="sxs-lookup"><span data-stu-id="f0178-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="f0178-107">**Funktionstestskript:** Skriv den relativa sökvägen till varje funktionstestskript som laddas upp.</span><span class="sxs-lookup"><span data-stu-id="f0178-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="f0178-108">Ytterligare funktionstestskript kan läggas till med ```Add Script``` knappen.</span><span class="sxs-lookup"><span data-stu-id="f0178-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="f0178-109">Du behöver minst ett (1) skript och kan lägga till upp till åtta (8) funktionstestskript.</span><span class="sxs-lookup"><span data-stu-id="f0178-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="f0178-110">Skripten körs i överföringssekvens och ett fel i ett visst skript stoppar efterföljande skript att köras.</span><span class="sxs-lookup"><span data-stu-id="f0178-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="f0178-111">Du kan också välja ytterligare inställningar för varje skript som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="f0178-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="f0178-112">Ange skriptsökväg</span><span class="sxs-lookup"><span data-stu-id="f0178-112">Set script path</span></span>

![Bild av testaktivitet](Media/testtask.png)

<span data-ttu-id="f0178-114">Exempel på hur du anger den relativa sökvägen till en mappstruktur nedan:</span><span class="sxs-lookup"><span data-stu-id="f0178-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="f0178-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="f0178-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="f0178-116">**ScriptX.ps1** skulle ha gjort det.</span><span class="sxs-lookup"><span data-stu-id="f0178-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="f0178-117">_ScriptX.ps1_ som den relativa sökvägen.</span><span class="sxs-lookup"><span data-stu-id="f0178-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="f0178-118">**Script.ps1** kunde ha _mapp1/script.ps1_ som den relativa sökvägen.</span><span class="sxs-lookup"><span data-stu-id="f0178-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f0178-119">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f0178-119">Next steps</span></span>

<span data-ttu-id="f0178-120">Visa information om fliken Testalternativ i nästa artikel</span><span class="sxs-lookup"><span data-stu-id="f0178-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="f0178-121">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f0178-121">Next step</span></span>](testoptions.md)
