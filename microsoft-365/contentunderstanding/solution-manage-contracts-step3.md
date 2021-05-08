---
title: Steg 3. Använd Power Automate för att skapa ett flöde för att bearbeta dina kontrakt
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
description: Lär dig hur du Power Automate skapa ett flöde för att bearbeta kontrakt med en Microsoft 365 lösning.
ms.openlocfilehash: d9892110d6aebd3eaae6fbc21d453b7eb14d7f7e
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281363"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="fc6b8-104">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-104">Step 3.</span></span> <span data-ttu-id="fc6b8-105">Använd Power Automate för att skapa ett flöde för att bearbeta dina kontrakt</span><span class="sxs-lookup"><span data-stu-id="fc6b8-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="fc6b8-106">Du har skapat din kanal för kontraktshantering och bifogat ditt SharePoint dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="fc6b8-107">Nästa steg är att skapa ett Power Automate flöde för att bearbeta de kontrakt som din SharePoint Syntex-modell identifierar och klassificerar.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="fc6b8-108">Du kan göra det här steget genom [att skapa Power Automate ett flöde i SharePoint-dokumentbiblioteket](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span><span class="sxs-lookup"><span data-stu-id="fc6b8-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="fc6b8-109">För din lösning för kontraktshantering vill du skapa ett Power Automate för att göra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="fc6b8-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="fc6b8-110">När ett kontrakt har klassificerats av din SharePoint Syntex-modell ändrar du kontraktsstatusen till **Vid granskning.**</span><span class="sxs-lookup"><span data-stu-id="fc6b8-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="fc6b8-111">Avtalet granskas sedan och godkänns eller avvisas.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="fc6b8-112">För godkända kontrakt publiceras kontraktsinformationen på en flik för betalningsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="fc6b8-113">För avvisade kontrakt meddelas teamet för vidare analys.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="fc6b8-114">Följande diagram visar Power Automate för kontraktshanteringslösningen.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow som visar hela lösningen.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="fc6b8-116">Förbered ditt kontrakt för granskning</span><span class="sxs-lookup"><span data-stu-id="fc6b8-116">Prepare your contract for review</span></span>

<span data-ttu-id="fc6b8-117">När ett kontrakt identifieras och klassificeras av din förstå-modell för SharePoint Syntex-dokument ändrar Power Automate-flödet först statusen till "Granskad".</span><span class="sxs-lookup"><span data-stu-id="fc6b8-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to "In review."</span></span>

![Uppdateringsstatus.](../media/content-understanding/flow-overview.png)

<span data-ttu-id="fc6b8-119">När du har checkat ut filen ändrar du statusvärdet till "Granska".</span><span class="sxs-lookup"><span data-stu-id="fc6b8-119">After checking out the file, change the status value to "In review."</span></span>

![I granskningsstatus.](../media/content-understanding/in-review.png)

<span data-ttu-id="fc6b8-121">Nästa steg är att skapa ett adaptivt kort som anger att avtalet väntar på granskning och publicerar det i kanalen Kontraktshantering.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![Granskning av avtal.](../media/content-understanding/contract-approval-post.png)


![Skapa adaptiva kort för granskning.](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="fc6b8-124">Följande kod är det JSON som används för det här steget i Power Automate flöde.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a><span data-ttu-id="fc6b8-125">Villkorsstyrd</span><span class="sxs-lookup"><span data-stu-id="fc6b8-125">Conditional</span></span>

<span data-ttu-id="fc6b8-126">I flödet måste du sedan skapa ett villkor där avtalet antingen godkänns eller avvisas.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-126">In your flow, next you need to create a condition in which your contract will be either  approved or rejected.</span></span>

![Villkorsstyrd.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="fc6b8-128">Om avtalet godkänns</span><span class="sxs-lookup"><span data-stu-id="fc6b8-128">If the contract is approved</span></span>

<span data-ttu-id="fc6b8-129">När ett kontrakt har godkänts inträffar följande:</span><span class="sxs-lookup"><span data-stu-id="fc6b8-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="fc6b8-130">På **fliken** Kontrakt ändras statusen i kontraktskortet till **Godkänd.**</span><span class="sxs-lookup"><span data-stu-id="fc6b8-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![Kortstatus godkänd.](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="fc6b8-132">I flödet ändras statusen till "Godkänd".</span><span class="sxs-lookup"><span data-stu-id="fc6b8-132">In your flow, the status is changed to "Approved."</span></span>

   ![Flow status godkänd.](../media/content-understanding/status-approved.png)

- <span data-ttu-id="fc6b8-134">I den här lösningen läggs kontraktsdata till på **fliken För** utbetalning så att utbetalningarna kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="fc6b8-135">Den här processen kan utökas så att flödet kan skicka in avtal om betalning med en ekonomisk tredje part-app (till exempel Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="fc6b8-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![Avtalet flyttas till Betala ut.](../media/content-understanding/for-payout.png)

- <span data-ttu-id="fc6b8-137">I flödet skapar du följande objekt för att flytta godkända kontrakt till **fliken För utbetalning.**</span><span class="sxs-lookup"><span data-stu-id="fc6b8-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flow att flytta till Betala ut.](../media/content-understanding/ready-for-payout.png)

- <span data-ttu-id="fc6b8-139">Ett adaptivt kort som anger att avtalet har godkänts skapas och publiceras i kanalen Kontraktshantering.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-139">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![Godkännande av avtal publicerat.](../media/content-understanding/adaptive-card-approval.png)

   ![Adaptivt kortgodkännande.](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="fc6b8-142">Följande kod är det JSON som används för det här steget i Power Automate flöde.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-142">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="fc6b8-143">Om avtalet avvisas</span><span class="sxs-lookup"><span data-stu-id="fc6b8-143">If the contract is rejected</span></span>

<span data-ttu-id="fc6b8-144">När ett kontrakt har avvisats inträffar följande:</span><span class="sxs-lookup"><span data-stu-id="fc6b8-144">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="fc6b8-145">På **fliken** Kontrakt ändras statusen i kontraktskortet till **Avvisad**.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-145">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![Kortstatus avvisades.](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="fc6b8-147">I flödet checkar du ut kontraktsfilen, ändrar status till **Avvisat** och checkar sedan in filen igen.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-147">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow status avvisades.](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="fc6b8-149">I flödet skapar du ett adaptivt kort som säger att avtalet har avvisats.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-149">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow status avvisades.](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="fc6b8-151">Följande kod är det JSON som används för det här steget i Power Automate flöde.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-151">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- <span data-ttu-id="fc6b8-152">Kortet publiceras i kanalen Kontraktshantering.</span><span class="sxs-lookup"><span data-stu-id="fc6b8-152">The card is posted in the Contract Management channel.</span></span>

   ![Flow adaptivt kort att avvisa.](../media/content-understanding/rejected.png)