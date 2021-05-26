---
title: Hantera Relevanskonfigurationen i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Läs rekommendationerna för hur du konfigurerar Relevansträning i Advanced eDiscovery, så att du kan betygsätta filer efter relevans och ta fram analysresultat.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161722"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="f8ff0-103">Hantera Relevanskonfigurationen i Advanced eDiscovery (klassisk version)</span><span class="sxs-lookup"><span data-stu-id="f8ff0-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="f8ff0-104">För Advanced eDiscovery krävs Office 365 E3 med tillägget Advanced Compliance eller en E5-prenumeration för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="f8ff0-105">Om du inte har detta abonnemang men vill prova Advanced eDiscovery kan du [registrera dig för en utvärderingsversion av Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f8ff0-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="f8ff0-106">Tekniken bakom Advanced eDiscovery Relevans använder expertledd programvara till att betygsätta filer efter relevans.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-106">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance.</span></span> <span data-ttu-id="f8ff0-107">Advanced eDiscovery Relevans kan användas till tidig aktutvärdering (Early Case Assessment – ECA), gallring och granskning av exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-107">Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="f8ff0-108">Advanced eDiscovery innehåller komponenter för Relevansträning och märkning av filer som hör till en akt.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-108">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case.</span></span> <span data-ttu-id="f8ff0-109">Med hjälp av träningsexempel på relevanta och ej relevanta filer lär sig Advanced eDiscovery att sätta relevanspoäng på olika filer och att skapa analysresultat som kan användas under och efter filgranskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-109">Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="f8ff0-110">Riktlinjer för att konfigurera Relevansträning</span><span class="sxs-lookup"><span data-stu-id="f8ff0-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="f8ff0-111">I Advanced eDiscovery går du till fönstret **Akter**, väljer en akt och klickar på **Gå till akten**.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-111">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**.</span></span> <span data-ttu-id="f8ff0-112">Klicka på **Relevans** \> **Relevanskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-112">Click **Relevance** \> **Relevance setup**.</span></span> <span data-ttu-id="f8ff0-113">Följ riktlinjerna för att konfigurera Relevans.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-113">Follow these recommended guidelines to set up Relevance.</span></span> 
  
- <span data-ttu-id="f8ff0-114">**Märkning:** Effektiviteten hos den iterativa processen för Relevansträning beror på expertens förmåga att märka filexemplen med precision och konsekvens.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>

- <span data-ttu-id="f8ff0-115">**Problem med akter**:</span><span class="sxs-lookup"><span data-stu-id="f8ff0-115">**Case issues**:</span></span>
  
  - <span data-ttu-id="f8ff0-116">För varje problem ska samma expert användas under hela Relevansträningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-116">For each issue, use the same expert throughout the entire Relevance training process.</span></span> <span data-ttu-id="f8ff0-117">Det är inte tillåtet att använda flera experter för att markera ett och samma problem flera gånger.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-117">Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
  
  - <span data-ttu-id="f8ff0-118">Avgör om varje grupp av filer är relevant endast för ett visst problem.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-118">Determine if each group of files is pertinent only to a specific issue.</span></span>

  - <span data-ttu-id="f8ff0-119">Om ett problem är för brett definierat kan Advanced eDiscovery returnera för många irrelevanta filer.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-119">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are not relevant.</span></span> <span data-ttu-id="f8ff0-120">Om ett problem är för smalt definierat kan Relevansträningsprocessen ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-120">If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 

  - <span data-ttu-id="f8ff0-121">Under varje Relevansträningscykel fokuserar Advanced eDiscovery på ett enskilt aktivt problem och interimsresultat från exemplen visas i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>

  - <span data-ttu-id="f8ff0-122">I ett scenario med flera problem går det att välja vilka problem som ska ingå i bearbetningen med hjälp av Urvalsläge.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-122">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing.</span></span> <span data-ttu-id="f8ff0-123">Problem som definieras som ”av” bearbetas inte förrän deras urvalsläge ändras.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-123">Issues defined as "off" are not handled until their Sampling mode is changed.</span></span> <span data-ttu-id="f8ff0-124">Ett problem kan endast vara ”inaktivt” eller ”på” för en expert.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-124">An issue can be "idle" or "on" for only one expert.</span></span>

  - <span data-ttu-id="f8ff0-125">Advanced eDiscovery kan användas till att skapa kandidatprivilegiefiler.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-125">Advanced eDiscovery can be used to generate candidate privilege files.</span></span> <span data-ttu-id="f8ff0-126">Konfigurera ett separat problem för privilegier.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-126">Set up a separate issue for privilege.</span></span> <span data-ttu-id="f8ff0-127">Om möjligt bör du träna och gallra för relevans innan du använder endast den gallrade uppsättningen till privilegieträning (läs in den gallrade uppsättningen på nytt som en separat akt).</span><span class="sxs-lookup"><span data-stu-id="f8ff0-127">If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 

  - <span data-ttu-id="f8ff0-128">Batchberäkningar kan endast utföras om det inte finns några öppna exempel (när du klickar på Batchberäkning visas en lista över användare med öppna exempel).</span><span class="sxs-lookup"><span data-stu-id="f8ff0-128">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples).</span></span> <span data-ttu-id="f8ff0-129">För att ”stänga” exempel åt andra användare (detta bör endast utföras om användarna inte håller på att markera dessa exempel) kan administratören använda funktionen ”Ändra relevans” med alternativet ”Alla användares exempel”.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-129">To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>

- <span data-ttu-id="f8ff0-130">**Metadata**: Advanced eDiscovery fokuserar på innehållet.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-130">**Metadata**: Advanced eDiscovery focuses on content.</span></span> <span data-ttu-id="f8ff0-131">Metadata tas inte i beaktande för relevanskriteriet.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-131">It does not consider metadata as part of the relevance criteria.</span></span>

- <span data-ttu-id="f8ff0-132">**Relevansgrad**: Om relevansgraden för ett problem är lägre än 3 % efter värdering, bör du överväga att använda seeding med kända relevanta och ej relevanta filer på Relevansträningen.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>

- <span data-ttu-id="f8ff0-133">**Filstorlek**: Stora filer (över 5 242 880 tecken i extraherad text) ignoreras i Relevans.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-133">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance.</span></span> <span data-ttu-id="f8ff0-134">Filerna ingår inte i Relevansträningsprocessen och får inga relevanspoäng efter Batchberäkning.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-134">The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation.</span></span> <span data-ttu-id="f8ff0-135">Filer som är större än 5 MB kan inkluderas i värderingsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-135">Files over 5 MB can be included in the Assessment set.</span></span>

## <a name="setting-up-case-issues"></a><span data-ttu-id="f8ff0-136">Konfigurera aktproblem</span><span class="sxs-lookup"><span data-stu-id="f8ff0-136">Setting up case issues</span></span>

<span data-ttu-id="f8ff0-137">De parametrar som beskrivs i det här avsnittet finns tillgängliga i Advanced eDiscovery, via **Relevans** \> **Relevanskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span>
  
- <span data-ttu-id="f8ff0-138">Problemen måste tilldelas till en användare som ska träna filerna.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-138">Issues must be assigned to a user who will train the files.</span></span>

- <span data-ttu-id="f8ff0-139">Därefter måste importerade filer läggas till i den dossier som ska behandlas.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-139">Imported files must then be added to the load being processed.</span></span>

- <span data-ttu-id="f8ff0-140">Var noggrann när du definierar och organiserar problem, eftersom detta påverkar resultaten från Relevansträningen.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>

<span data-ttu-id="f8ff0-141">När alla parametrar har angivits kan granskaren/experten börja träna filerna under fliken **Relevans**.</span><span class="sxs-lookup"><span data-stu-id="f8ff0-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span>
