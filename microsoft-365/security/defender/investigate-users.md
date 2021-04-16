---
title: Undersöka användare i Microsoft 365 Säkerhetscenter
description: undersöka användare i Säkerhetscenter för Microsoft 365
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861279"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="ed582-104">Undersöka användare i Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="ed582-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ed582-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ed582-105">**Applies to:**</span></span>

- <span data-ttu-id="ed582-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed582-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ed582-107">En del av incidentundersökningen kan omfatta användarkonton.</span><span class="sxs-lookup"><span data-stu-id="ed582-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="ed582-108">Börja med fliken **Användare** för ett incident från Incidenter **& aviseringar >** *incident* **> Användare.**</span><span class="sxs-lookup"><span data-stu-id="ed582-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

<span data-ttu-id="ed582-110">Om du vill få en snabb sammanfattning av ett användarkonto för incidenten väljer du bockmarkeringen bredvid användarnamnet.</span><span class="sxs-lookup"><span data-stu-id="ed582-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="ed582-111">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ed582-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkontot för en incident i säkerhetscentret i Microsoft 365":::

<span data-ttu-id="ed582-113">Härifrån kan du välja Gå **till användarsida om** du vill visa information om ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="ed582-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="ed582-114">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ed582-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="ed582-116">Du kan även visa den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.</span><span class="sxs-lookup"><span data-stu-id="ed582-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="ed582-117">Användarsidan för Microsoft 365 säkerhetscenter kombinerar information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet (beroende på vilka licenser du har).</span><span class="sxs-lookup"><span data-stu-id="ed582-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="ed582-118">På den här sidan visas information som är specifik för säkerhetsrisken för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="ed582-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="ed582-119">Detta omfattar en poäng som hjälper till att utvärdera risker och nya händelser och varningar som bidragit till den totala risken för användaren.</span><span class="sxs-lookup"><span data-stu-id="ed582-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="ed582-120">Från den här sidan kan du utföra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="ed582-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="ed582-121">Markera användarkontot som komprometterat</span><span class="sxs-lookup"><span data-stu-id="ed582-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="ed582-122">Kräv att användaren loggar in igen</span><span class="sxs-lookup"><span data-stu-id="ed582-122">Require the user to sign in again</span></span>
- <span data-ttu-id="ed582-123">Stäng av användarkontot</span><span class="sxs-lookup"><span data-stu-id="ed582-123">Suspend the user account</span></span>
- <span data-ttu-id="ed582-124">Se inställningar för användarkonton i Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ed582-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="ed582-125">Visa de filer som ägs av användarkontot</span><span class="sxs-lookup"><span data-stu-id="ed582-125">View the files owned by the user account</span></span>
- <span data-ttu-id="ed582-126">Visa filer som delats med den här användaren.</span><span class="sxs-lookup"><span data-stu-id="ed582-126">View files shared with this user.</span></span> 

<span data-ttu-id="ed582-127">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ed582-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder för ett användarkonto för en händelse i Säkerhetscenter för Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="ed582-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ed582-129">Related topics</span></span>

- [<span data-ttu-id="ed582-130">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="ed582-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ed582-131">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="ed582-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ed582-132">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="ed582-132">Manage incidents</span></span>](manage-incidents.md)