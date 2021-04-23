---
title: Analysera användare i Microsoft 365 Säkerhetscenter
description: Analysera användare i Säkerhetscenter för Microsoft 365
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar, incident, analysera, svar
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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957613"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="a1e48-104">Analysera användare i Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="a1e48-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a1e48-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a1e48-105">**Applies to:**</span></span>

- <span data-ttu-id="a1e48-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1e48-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a1e48-107">En del av incidentanalysen kan omfatta användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a1e48-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="a1e48-108">Börja med fliken **Användare** för ett incident från Incidenter **& aviseringar >** *incident* **> Användare.**</span><span class="sxs-lookup"><span data-stu-id="a1e48-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

<span data-ttu-id="a1e48-110">Om du vill få en snabb sammanfattning av ett användarkonto för incidenten väljer du bockmarkeringen bredvid användarnamnet.</span><span class="sxs-lookup"><span data-stu-id="a1e48-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="a1e48-111">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a1e48-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkontot för en incident i säkerhetscentret i Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="a1e48-113">På användarsidan visas organisationen i Azure Active Directory (AD) samt grupper, vilket hjälper dig att förstå vilka grupper och behörigheter som är kopplade till en användare.</span><span class="sxs-lookup"><span data-stu-id="a1e48-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="a1e48-114">På den här utfällande sidan kan du granska information om användarhot, inklusive aktuella incidenter, aktiva varningar och risknivå samt exponering av användare, konton, enheter med mera.</span><span class="sxs-lookup"><span data-stu-id="a1e48-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="a1e48-115">Dessutom kan du vidta åtgärder direkt i Microsoft 365 säkerhetscenter för att adressera en komprometterad användare, bekräfta att användaren har komprometterats eller att de måste logga in igen.</span><span class="sxs-lookup"><span data-stu-id="a1e48-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="a1e48-116">Härifrån kan du välja Gå **till användarsida om** du vill visa information om ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="a1e48-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="a1e48-117">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a1e48-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="a1e48-119">Du kan även visa den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.</span><span class="sxs-lookup"><span data-stu-id="a1e48-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="a1e48-120">Användarsidan för Microsoft 365 säkerhetscenter kombinerar information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet (beroende på vilka licenser du har).</span><span class="sxs-lookup"><span data-stu-id="a1e48-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="a1e48-121">På den här sidan visas information som är specifik för säkerhetsrisken för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="a1e48-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="a1e48-122">Detta omfattar en poäng som hjälper till att utvärdera risker och nya händelser och varningar som bidragit till den totala risken för användaren.</span><span class="sxs-lookup"><span data-stu-id="a1e48-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="a1e48-123">Från den här sidan kan du utföra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a1e48-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="a1e48-124">Markera användarkontot som komprometterat</span><span class="sxs-lookup"><span data-stu-id="a1e48-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="a1e48-125">Kräv att användaren loggar in igen</span><span class="sxs-lookup"><span data-stu-id="a1e48-125">Require the user to sign in again</span></span>
- <span data-ttu-id="a1e48-126">Stäng av användarkontot</span><span class="sxs-lookup"><span data-stu-id="a1e48-126">Suspend the user account</span></span>
- <span data-ttu-id="a1e48-127">Se inställningar för användarkonton i Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a1e48-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="a1e48-128">Visa de filer som ägs av användarkontot</span><span class="sxs-lookup"><span data-stu-id="a1e48-128">View the files owned by the user account</span></span>
- <span data-ttu-id="a1e48-129">Visa filer som delats med den här användaren.</span><span class="sxs-lookup"><span data-stu-id="a1e48-129">View files shared with this user.</span></span> 

<span data-ttu-id="a1e48-130">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="a1e48-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder för ett användarkonto för en händelse i Säkerhetscenter för Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="a1e48-132">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a1e48-132">Related topics</span></span>

- [<span data-ttu-id="a1e48-133">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="a1e48-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a1e48-134">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="a1e48-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a1e48-135">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="a1e48-135">Manage incidents</span></span>](manage-incidents.md)