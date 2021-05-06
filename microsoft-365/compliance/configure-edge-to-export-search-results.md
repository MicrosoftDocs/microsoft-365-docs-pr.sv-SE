---
title: Använda eDiscovery-exportverktyget i Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Du måste aktivera ClickOnce för att kunna använda den senaste versionen av Microsoft Edge för att ladda ned sökresultat från Innehållssökning och eDiscovery i säkerhets- och efterlevnadscentret.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "52161605"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="56973-103">Använda eDiscovery-exportverktyget i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="56973-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="56973-104">På grund av de senaste ändringarna av den senaste Microsoft Edge är ClickOnce inte längre aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="56973-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="56973-105">Om du vill fortsätta att använda verktyget för eDiscovery-export för att ladda ned innehållssökning eller eDiscovery-sökresultat måste du antingen använda [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) eller aktivera ClickOnce stöd i den senaste versionen Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="56973-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="56973-106">Aktivera ClickOnce i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="56973-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="56973-107">I Microsoft Edge går du till **edge://flags/#edge-click-once**.</span><span class="sxs-lookup"><span data-stu-id="56973-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="56973-108">Om det befintliga värdet är **Inställt på Standard** **eller** Inaktiverat i listrutan ändrar du det till **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="56973-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Välj Aktiverad i listrutan](../media/ClickOnceimage1.png)

3. <span data-ttu-id="56973-110">Rulla ned till slutet av webbläsarfönstret och klicka på Starta om **för att** starta om Edge.</span><span class="sxs-lookup"><span data-stu-id="56973-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Klicka på Starta om](../media/ClickOnceimage2.png)

<span data-ttu-id="56973-112">**Obs!** Organisationer kan använda grupprinciper för att inaktivera ClickOnce support.</span><span class="sxs-lookup"><span data-stu-id="56973-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="56973-113">Om du vill kontrollera om det finns en organisationspolicy för ClickOnce support går du till **edge://policy**.</span><span class="sxs-lookup"><span data-stu-id="56973-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="56973-114">Följande skärmbild visar att ClickOnce är aktiverat i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="56973-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="56973-115">Om värdet för den här principen **är falskt** måste du kontakta en administratör i organisationen.</span><span class="sxs-lookup"><span data-stu-id="56973-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Lista över Edge organisationspolicyer](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="56973-117">Installera och köra eDiscovery-exportverktyget</span><span class="sxs-lookup"><span data-stu-id="56973-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="56973-118">Klicka **på Ladda** ned resultat på den utfällsbara sidan för en export i Innehållssökning eller ett eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="56973-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Klicka på Ladda ned resultat på den utfällsbara sidan för att ladda ned sökresultat](../media/ClickOnceExport1.png)

2. <span data-ttu-id="56973-120">Du uppmanas att bekräfta att du vill starta verktyget genom att klicka på **Öppna.**</span><span class="sxs-lookup"><span data-stu-id="56973-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Klicka på Öppna för att starta eDiscovery-exportverktyget](../media/ClickOnceimage4.png)

   <span data-ttu-id="56973-122">Om verktyget för eDiscovery-export inte är installerat visas en säkerhetsvarning där</span><span class="sxs-lookup"><span data-stu-id="56973-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Klicka på Installera för att installera eDiscovery-exportverktyget](../media/ClickOnceimage5.png)

3. <span data-ttu-id="56973-124">Klicka på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="56973-124">Click **Install**.</span></span> <span data-ttu-id="56973-125">När det har installerats startas exportverktyget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="56973-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="56973-126">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="56973-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="56973-127">Exportera resultat för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="56973-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="56973-128">Så här aktiverar du experimentflaggor i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="56973-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
