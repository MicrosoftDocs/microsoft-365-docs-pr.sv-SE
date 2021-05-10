---
title: Steg 2. Använd Microsoft Teams för att skapa din kanal för kontraktshantering
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du Microsoft Teams skapa din kanal för kontraktshantering med hjälp av en Microsoft 365 lösning.
ms.openlocfilehash: d703f6f7286a6d9584e8b18d4e283174f42a95bd
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301806"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="d3910-104">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="d3910-104">Step 2.</span></span> <span data-ttu-id="d3910-105">Använd Microsoft Teams för att skapa din kanal för kontraktshantering</span><span class="sxs-lookup"><span data-stu-id="d3910-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="d3910-106">När din organisation skapar en lösning för kontraktshantering behöver du en central plats där intressenter kan granska och hantera kontrakt.</span><span class="sxs-lookup"><span data-stu-id="d3910-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="d3910-107">För detta ändamål kan du använda [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) konfigurera en kanal Teams och använda funktionerna i Teams för att:</span><span class="sxs-lookup"><span data-stu-id="d3910-107">For this purpose, you can use [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="d3910-108">**Skapa en plats för intressenter för att enkelt kunna se alla kontrakt som kräver åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="d3910-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="d3910-109">I Teams kan du till exempel  skapa fliken Kontrakt i kanalen Kontraktshantering där medlemmarna kan se en användbar panelvy över alla kontrakt som kräver godkännande.</span><span class="sxs-lookup"><span data-stu-id="d3910-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="d3910-110">Du kan också konfigurera vyn så att varje "kort" visar viktig information som är viktig för dig (t.ex. *klient,* leverantörer och *avgiftsbelopp).*</span><span class="sxs-lookup"><span data-stu-id="d3910-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Fliken Kontrakt.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="d3910-112">**Ha en plats där medlemmarna kan interagera med varandra och se viktiga händelser.**</span><span class="sxs-lookup"><span data-stu-id="d3910-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="d3910-113">I Teams till exempel kan  fliken Inlägg användas för att ha konversationer, få uppdateringar och visa åtgärder (till exempel en medlem som avvisar ett kontrakt).</span><span class="sxs-lookup"><span data-stu-id="d3910-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="d3910-114">När något har hänt (till exempel om  ett nytt avtal har skickats in för godkännande) kan fliken Inlägg inte bara användas för att meddela den, utan också för att spara den.</span><span class="sxs-lookup"><span data-stu-id="d3910-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="d3910-115">Och om medlemmarna prenumererar på aviseringar får de ett meddelande när det finns en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="d3910-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span> 

     ![Fliken Inlägg.](../media/content-understanding/posts.png)</br> 

- <span data-ttu-id="d3910-117">**Ha en plats där medlemmarna kan se godkända kontrakt för att veta när de kan skickas in för betalning.**</span><span class="sxs-lookup"><span data-stu-id="d3910-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="d3910-118">I Teams kan du skapa en <b>för</b> betalningskanal som visar alla kontrakt som ska skickas till betalningen.</span><span class="sxs-lookup"><span data-stu-id="d3910-118">In Teams, you can create a <b>For Payment</b> channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="d3910-119">Du kan enkelt utöka den här lösningen så att den istället skriver den här informationen direkt till en ekonomisk app från tredje part (till exempel Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="d3910-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="d3910-120">Bifoga ditt SharePoint dokumentbibliotek på fliken Kontrakt</span><span class="sxs-lookup"><span data-stu-id="d3910-120">Attach your SharePoint document library to the Contracts tab</span></span> 

<span data-ttu-id="d3910-121">När du har skapat **fliken** Kontrakt i kanalen Kontraktshantering måste du bifoga ditt SharePoint [till det](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span><span class="sxs-lookup"><span data-stu-id="d3910-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="d3910-122">Den SharePoint dokumentbibliotek som du vill bifoga är den där du SharePoint med förstå-modellen för Syntex-dokument i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d3910-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="d3910-123">När du bifogat SharePoint-dokumentbiblioteket kan du visa alla klassificerade kontrakt i en standardlistvy.</span><span class="sxs-lookup"><span data-stu-id="d3910-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Listvy.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="d3910-125">Anpassa panelvyn på fliken Kontrakt</span><span class="sxs-lookup"><span data-stu-id="d3910-125">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="d3910-126">Det här avsnittet refererar till kodexempel som **finns iContractCard.js** filen som ingår i **zip-filen solutionfiles.**</span><span class="sxs-lookup"><span data-stu-id="d3910-126">This section references code examples that are contained in the **ContractCard.json** file that is included in the **solutionfiles** zip file.</span></span>

<span data-ttu-id="d3910-127">Även Teams visa kontrakten i en panelvy kan du anpassa dem för att visa de kontraktsdata du vill göra synliga på kontraktskortet.</span><span class="sxs-lookup"><span data-stu-id="d3910-127">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="d3910-128">För fliken Kontrakt är **det till** exempel viktigt att medlemmarna ser klienten, leverantören och avgiftsbeloppet på kontraktskortet.</span><span class="sxs-lookup"><span data-stu-id="d3910-128">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="d3910-129">Alla dessa fält har extraherats från varje kontrakt via din SharePoint Syntex-modell som tillämpats på ditt dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="d3910-129">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="d3910-130">Du vill också kunna ändra panelrubrikfältet till olika färger för varje status så att medlemmarna enkelt kan se var avtalet ligger i godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="d3910-130">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="d3910-131">Alla godkända kontrakt kommer till exempel att ha en blå rubrikfält.</span><span class="sxs-lookup"><span data-stu-id="d3910-131">For example, all approved contracts will have a blue header bar.</span></span>

   ![Listvy.](../media/content-understanding/tile.png)

<span data-ttu-id="d3910-133">Den anpassade panelvyn du använder kräver att du gör ändringar i JSON-filen som används för att formatera den aktuella panelvyn.</span><span class="sxs-lookup"><span data-stu-id="d3910-133">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="d3910-134">Du kan referera till den JSON-fil som används för att skapa kortvyn genom att hämta **filenContractCard.jsfilen.**</span><span class="sxs-lookup"><span data-stu-id="d3910-134">You can reference the JSON file used to create the card view by downloading the **ContractCard.json** file.</span></span> <span data-ttu-id="d3910-135">I följande avsnitt visas specifika avsnitt i koden för funktioner som finns på kontraktskorten.</span><span class="sxs-lookup"><span data-stu-id="d3910-135">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="d3910-136">Om du vill se eller göra ändringar i JSON-koden för vyn i din Teams-kanal går du till Teams-kanalen, väljer listrutan Vy och väljer sedan **Formatera aktuell vy.**</span><span class="sxs-lookup"><span data-stu-id="d3910-136">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![json-format.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a><span data-ttu-id="d3910-138">Kortstorlek och -form</span><span class="sxs-lookup"><span data-stu-id="d3910-138">Card size and shape</span></span>

<span data-ttu-id="d3910-139">I **ContractCard.js** filen du laddade ned i referensen zip-filen, tittar du i följande avsnitt för att se koden för hur kortets storlek och form är formaterade.</span><span class="sxs-lookup"><span data-stu-id="d3910-139">In the **ContractCard.json** file that you downloaded in the reference zip file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a><span data-ttu-id="d3910-140">Kontraktsstatus</span><span class="sxs-lookup"><span data-stu-id="d3910-140">Contract status</span></span>

<span data-ttu-id="d3910-141">Med följande kod kan du ange status för varje titelkort.</span><span class="sxs-lookup"><span data-stu-id="d3910-141">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="d3910-142">Observera att varje statusvärde *(Ny,* *I* *granskning,* Godkänd och *Avvisad)* visar olika färgkoder för varje statusvärde.</span><span class="sxs-lookup"><span data-stu-id="d3910-142">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="d3910-143">Titta **iContractCard.jsfilen** du laddade ned i avsnittet som definierar statusen.</span><span class="sxs-lookup"><span data-stu-id="d3910-143">In the **ContractCard.json** file that you downloaded, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a><span data-ttu-id="d3910-144">Extraherade fält</span><span class="sxs-lookup"><span data-stu-id="d3910-144">Extracted fields</span></span>

<span data-ttu-id="d3910-145">Varje kontraktskort visar tre fält som har extraherats för varje kontrakt *(klient,* *leverantörer* och *avgiftsbelopp).*</span><span class="sxs-lookup"><span data-stu-id="d3910-145">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="d3910-146">Dessutom vill du visa det tid/datum då filen klassificerades av den SharePoint Syntex-modellen som använts för att identifiera den.</span><span class="sxs-lookup"><span data-stu-id="d3910-146">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span> 

<span data-ttu-id="d3910-147">IContractCard.js **filen** du laddade ned definierar följande avsnitt var och en av dessa.</span><span class="sxs-lookup"><span data-stu-id="d3910-147">In the **ContractCard.json** file that you downloaded, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="d3910-148">Klient</span><span class="sxs-lookup"><span data-stu-id="d3910-148">Client</span></span>

<span data-ttu-id="d3910-149">Det här avsnittet definierar hur "Klient" visas på kortet och använder värdet för det specifika avtalet.</span><span class="sxs-lookup"><span data-stu-id="d3910-149">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="d3910-150">Entreprenör</span><span class="sxs-lookup"><span data-stu-id="d3910-150">Contractor</span></span>

<span data-ttu-id="d3910-151">Det här avsnittet definierar hur "Entreprenör" visas på kortet och använder värdet för det specifika avtalet.</span><span class="sxs-lookup"><span data-stu-id="d3910-151">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a><span data-ttu-id="d3910-152">Avgiftsbelopp</span><span class="sxs-lookup"><span data-stu-id="d3910-152">Fee Amount</span></span>

<span data-ttu-id="d3910-153">Det här avsnittet definierar hur "Avgiftsbelopp" visas på kortet och använder värdet för det specifika avtalet.</span><span class="sxs-lookup"><span data-stu-id="d3910-153">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a><span data-ttu-id="d3910-154">Klassificeringsdatum</span><span class="sxs-lookup"><span data-stu-id="d3910-154">Classification date</span></span>

<span data-ttu-id="d3910-155">Det här avsnittet definierar hur "Klassificering" visas på kortet och använder värdet för det specifika avtalet.</span><span class="sxs-lookup"><span data-stu-id="d3910-155">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="d3910-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d3910-156">Next step</span></span>

[<span data-ttu-id="d3910-157">Steg 3. Använd Power Automate för att skapa ett flöde för att bearbeta dina kontrakt</span><span class="sxs-lookup"><span data-stu-id="d3910-157">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
