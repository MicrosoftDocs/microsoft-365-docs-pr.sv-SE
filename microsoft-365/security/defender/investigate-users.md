---
title: Undersök användare i Microsoft 365 Defender
description: Undersök om det är ett problem i Microsoft 365 säkerhetscenter.
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
ms.openlocfilehash: 7084b9370a0dd83265b37ff1d152e2164fe32813
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539137"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="74b26-104">Undersök användare i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74b26-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74b26-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74b26-105">**Applies to:**</span></span>

- <span data-ttu-id="74b26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74b26-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="74b26-107">En del av incidentundersökningen kan omfatta användarkonton.</span><span class="sxs-lookup"><span data-stu-id="74b26-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="74b26-108">Börja med fliken **Användare** för ett incident från Incidenter **& aviseringar >** *incident* **> Användare.**</span><span class="sxs-lookup"><span data-stu-id="74b26-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

<span data-ttu-id="74b26-110">Om du vill få en snabb sammanfattning av ett användarkonto för incidenten väljer du bockmarkeringen bredvid användarnamnet.</span><span class="sxs-lookup"><span data-stu-id="74b26-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="74b26-111">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="74b26-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkontot för en händelse i Microsoft 365 säkerhetscenter":::

> [!NOTE]
> <span data-ttu-id="74b26-113">Användarsidan visar organisationen Azure Active Directory (AD) samt grupper, vilket hjälper dig att förstå vilka grupper och behörigheter som är kopplade till en användare.</span><span class="sxs-lookup"><span data-stu-id="74b26-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="74b26-114">På den här utfällande sidan kan du granska information om användarhot, inklusive aktuella incidenter, aktiva varningar och risknivå samt exponering av användare, konton, enheter med mera.</span><span class="sxs-lookup"><span data-stu-id="74b26-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="74b26-115">Dessutom kan du vidta åtgärder direkt i säkerhetscentret i Microsoft 365 för att adressera en komprometterad användare, bekräfta att användaren har komprometterats eller att han eller hon måste logga in igen.</span><span class="sxs-lookup"><span data-stu-id="74b26-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="74b26-116">Härifrån kan du välja Gå **till användarsida om** du vill visa information om ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="74b26-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="74b26-117">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="74b26-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="74b26-119">Du kan även visa den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.</span><span class="sxs-lookup"><span data-stu-id="74b26-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="74b26-120">Användarsidan Microsoft 365 Säkerhetscenter kombinerar information från Microsoft Defender för Endpoint, Microsoft Defender för identitet och Microsoft Cloud App Security (beroende på vilka licenser du har).</span><span class="sxs-lookup"><span data-stu-id="74b26-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="74b26-121">På den här sidan visas information som är specifik för säkerhetsrisken för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="74b26-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="74b26-122">Detta omfattar en poäng som hjälper till att utvärdera risker och nya händelser och varningar som bidragit till den totala risken för användaren.</span><span class="sxs-lookup"><span data-stu-id="74b26-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="74b26-123">Från den här sidan kan du utföra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="74b26-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="74b26-124">Markera användarkontot som komprometterat</span><span class="sxs-lookup"><span data-stu-id="74b26-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="74b26-125">Kräv att användaren loggar in igen</span><span class="sxs-lookup"><span data-stu-id="74b26-125">Require the user to sign in again</span></span>
- <span data-ttu-id="74b26-126">Stäng av användarkontot</span><span class="sxs-lookup"><span data-stu-id="74b26-126">Suspend the user account</span></span>
- <span data-ttu-id="74b26-127">Se inställningar Azure Active Directory för användarkonton i Azure AD</span><span class="sxs-lookup"><span data-stu-id="74b26-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="74b26-128">Visa de filer som ägs av användarkontot</span><span class="sxs-lookup"><span data-stu-id="74b26-128">View the files owned by the user account</span></span>
- <span data-ttu-id="74b26-129">Visa filer som delats med den här användaren.</span><span class="sxs-lookup"><span data-stu-id="74b26-129">View files shared with this user.</span></span> 

<span data-ttu-id="74b26-130">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="74b26-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder för ett användarkonto för en händelse i Microsoft 365 säkerhetscenter":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="74b26-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="74b26-132">Next steps</span></span>

<span data-ttu-id="74b26-133">Fortsätt din undersökning om det behövs för händelser i [processen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="74b26-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74b26-134">Se även</span><span class="sxs-lookup"><span data-stu-id="74b26-134">See also</span></span>

- [<span data-ttu-id="74b26-135">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="74b26-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="74b26-136">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="74b26-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="74b26-137">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="74b26-137">Manage incidents</span></span>](manage-incidents.md)