---
title: 'Tillgänglighetsläge för SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du använder hjälpmedelsläget när du utbildar en modell i SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515154"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="785cc-103">Tillgänglighetsläge för SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="785cc-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="785cc-104">I [SharePoint Syntex](index.md)kan användare aktivera hjälpmedelsläge i alla steg av modellutbildning (etikett, utbildare, test) när de arbetar med exempeldokument.</span><span class="sxs-lookup"><span data-stu-id="785cc-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="785cc-105">Med hjälpmedelsläget kan användare med låg syn få enklare tangentbordstillgänglighet när de navigerar och etikettobjekt i dokumentvisningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="785cc-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="785cc-106">Det hjälper användarna att använda tangentbordet för att navigera genom texten i dokumentvisningsprogrammet och höra en berättarröst om inte bara de valda värdena, utan även åtgärder (t.ex. etiketter eller ta bort etiketter från markerad text) eller förväntade etikettvärden när du utbildar modellen med ytterligare exempeldokument.</span><span class="sxs-lookup"><span data-stu-id="785cc-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Hjälpmedelsläge](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="785cc-108">Krav</span><span class="sxs-lookup"><span data-stu-id="785cc-108">Requirements</span></span>

<span data-ttu-id="785cc-109">Om du vill höra ljudet från berättarrösten [](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) måste du aktivera Skärmläsaren i inställningarna för Skärmläsaren i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="785cc-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Aktivera Skärmläsaren](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="785cc-111">Märkning för tangentbordsanvändare</span><span class="sxs-lookup"><span data-stu-id="785cc-111">Labeling for keyboard users</span></span>

<span data-ttu-id="785cc-112">För tangentbordsanvändare som använder hjälpmedelsläge kan du använda följande tangenter om du etiketterar text i ett exempeldokument i visningsprogrammet:</span><span class="sxs-lookup"><span data-stu-id="785cc-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="785cc-113">Tabb: Flyttar dig framåt och markerar nästa ord.</span><span class="sxs-lookup"><span data-stu-id="785cc-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="785cc-114">Tabb + Skift: Flyttar dig bakåt och markerar föregående ord.</span><span class="sxs-lookup"><span data-stu-id="785cc-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="785cc-115">Retur: Etiketten eller tar bort en etikett från det markerade ordet.</span><span class="sxs-lookup"><span data-stu-id="785cc-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="785cc-116">Högerpil: Du går framåt mellan enskilda tecken i ett markerat ord.</span><span class="sxs-lookup"><span data-stu-id="785cc-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="785cc-117">Vänsterpil: Flyttar dig bakåt mellan enskilda tecken i ett markerat ord.</span><span class="sxs-lookup"><span data-stu-id="785cc-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="785cc-118">Om du märk flera ord för en enstaka etikett måste du märka varje ord.</span><span class="sxs-lookup"><span data-stu-id="785cc-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="785cc-119">Berättarröst</span><span class="sxs-lookup"><span data-stu-id="785cc-119">Narration</span></span>

<span data-ttu-id="785cc-120">För användare av Skärmläsaren som använder hjälpmedelsläge använder du samma tangentbordsnavigering som beskrivs för tangentbordsanvändare för att gå igenom exempeldokumentet i visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="785cc-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="785cc-121">När du navigerar i exempeldokumenten och etikettsträngvärdena ger Skärmläsaren användaren följande ljuduppmaning:</span><span class="sxs-lookup"><span data-stu-id="785cc-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="785cc-122">När du använder tangentbordet för att navigera i dokumentvisningsprogrammet styr Skärmläsaren upp den markerade strängen.</span><span class="sxs-lookup"><span data-stu-id="785cc-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="785cc-123">Inom en markerad sträng anger Skärmläsaren ljud för varje tecken i strängen när du markerar dem med hjälp av vänster- eller högerpilen.</span><span class="sxs-lookup"><span data-stu-id="785cc-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="785cc-124">Om du väljer en sträng som har etiketterats, uppger Skärmläsaren värdet och säger sedan "märkt".</span><span class="sxs-lookup"><span data-stu-id="785cc-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="785cc-125">Om etikettvärdet till exempel är "Contoso" står det "Costoso märkt".</span><span class="sxs-lookup"><span data-stu-id="785cc-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="785cc-126">Om du väljer en sträng i dokumentvisningsprogrammet som bara har förutsagts på fliken Utbildning, kommer Skärmläsaren att ange värdet och sedan "förutsäga".</span><span class="sxs-lookup"><span data-stu-id="785cc-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="785cc-127">Detta inträffar när utbildningen förutsäger ett värde i filen som inte matchar det som har märkts av användaren.</span><span class="sxs-lookup"><span data-stu-id="785cc-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="785cc-128">Om du väljer en sträng i dokumentvisningsprogrammet som har etiketterats och prognosterats på fliken Utbildning, kommer Skärmläsaren att ange värdet och sedan "märkas och förutsägas".</span><span class="sxs-lookup"><span data-stu-id="785cc-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="785cc-129">Detta inträffar när utbildningen lyckas och det finns en matchning mellan ett förutsagt värde och användaretiketten.</span><span class="sxs-lookup"><span data-stu-id="785cc-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="785cc-130">När en sträng har etiketterats eller en etikett har tagits bort i visningsprogrammet får du en varning från Skärmläsaren om att ändringarna ska sparas innan du avslutar.</span><span class="sxs-lookup"><span data-stu-id="785cc-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="785cc-131">Se även</span><span class="sxs-lookup"><span data-stu-id="785cc-131">See Also</span></span>

[<span data-ttu-id="785cc-132">Skapa en extraherare</span><span class="sxs-lookup"><span data-stu-id="785cc-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="785cc-133">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="785cc-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



