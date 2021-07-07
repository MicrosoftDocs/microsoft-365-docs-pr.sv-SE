---
title: Upload Binärfiler för program
description: Komma igång med Test Base för M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323169"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="85b30-103">Steg 3: Upload dina binärfiler, beroenden och skript</span><span class="sxs-lookup"><span data-stu-id="85b30-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="85b30-104">På den här fliken laddar du upp ett enda zip-paket som innehåller dina binärfiler, beroenden och skript som används för att köra testpaketet.</span><span class="sxs-lookup"><span data-stu-id="85b30-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="85b30-105">Upload zip-fil med paket</span><span class="sxs-lookup"><span data-stu-id="85b30-105">Upload package zip file</span></span>

![Upload dina binärfiler](Media/AddBinaries.png)

  - <span data-ttu-id="85b30-107">Uppladdade beroenden kan inkludera testramar, skriptmotorer eller data som kan användas för att köra programmet eller testfall.</span><span class="sxs-lookup"><span data-stu-id="85b30-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="85b30-108">Du kan till exempel ladda upp Selenium och ett webdriver-installationsprogram för att köra webbläsarbaserade tester.</span><span class="sxs-lookup"><span data-stu-id="85b30-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="85b30-109">Det är bäst att se till att skriptaktiviteterna hålls i moduler, t.ex.</span><span class="sxs-lookup"><span data-stu-id="85b30-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="85b30-110">Skriptet ```Install``` utför bara installationsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="85b30-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="85b30-111">Skriptet ```Launch``` startar bara programmet.</span><span class="sxs-lookup"><span data-stu-id="85b30-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="85b30-112">Skriptet ```Close``` stänger bara programmet.</span><span class="sxs-lookup"><span data-stu-id="85b30-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="85b30-113">Det ```Uninstall``` valfria skriptet avinstallerar bara programmet.</span><span class="sxs-lookup"><span data-stu-id="85b30-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="85b30-114">**För närvarande har portalen endast stöd för PowerShell-skript.**</span><span class="sxs-lookup"><span data-stu-id="85b30-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="85b30-115">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="85b30-115">Next steps</span></span> 

<span data-ttu-id="85b30-116">Gå vidare till nästa artikel för att gå till Steg 4: **Ange testaktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="85b30-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="85b30-117">Gå tillbaka</span><span class="sxs-lookup"><span data-stu-id="85b30-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="85b30-118">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="85b30-118">Next step</span></span>](testtask.md)

