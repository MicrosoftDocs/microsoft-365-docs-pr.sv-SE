---
title: Undersök användare i Microsoft 365 Defender
description: Undersök användare för en incident i Microsoft 365 säkerhetscenter.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, övervaka, rapportera, identiteter, data, enheter, appar, incident, analysera, svar
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572807"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="4391f-104">Undersök användare i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4391f-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4391f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4391f-105">**Applies to:**</span></span>

- <span data-ttu-id="4391f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4391f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4391f-107">En del av din incidentutredning kan innehålla användarkonton.</span><span class="sxs-lookup"><span data-stu-id="4391f-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="4391f-108">Börja med fliken **Användare** för en incident från **incidenter & aviseringar >** *incident* **> användare**.</span><span class="sxs-lookup"><span data-stu-id="4391f-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en användarsida för en incident":::

<span data-ttu-id="4391f-110">Om du vill få en snabb sammanfattning av ett användarkonto för incidenten markerar du kryssrutan bredvid användarkontots namn.</span><span class="sxs-lookup"><span data-stu-id="4391f-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="4391f-111">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="4391f-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exempel på sammanfattningsfönstret för användarkonto för en incident i Microsoft 365 säkerhetscenter":::

> [!NOTE]
> <span data-ttu-id="4391f-113">På sidan Användare visas Azure Active Directory (Azure AD) samt grupper, vilket hjälper dig att förstå de grupper och behörigheter som är associerade med en användare.</span><span class="sxs-lookup"><span data-stu-id="4391f-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="4391f-114">På den här utfällningssidan kan du granska information om användarhot, inklusive aktuella incidenter, aktiva aviseringar och risknivå samt användarexponering, konton, enheter med mera.</span><span class="sxs-lookup"><span data-stu-id="4391f-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="4391f-115">Dessutom kan du vidta åtgärder direkt i Microsoft 365 säkerhetscenter för att adressera en komprometterad användare, bekräfta att användaren komprometteras eller kräva att de loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="4391f-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="4391f-116">Härifrån kan du välja Gå **till användarsidan för** att se information om ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="4391f-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="4391f-117">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="4391f-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exempel på användarkontosidan för en incident i Microsoft 365 säkerhetscenter":::

<span data-ttu-id="4391f-119">Du kan också se den här sidan genom att välja namnet på användarkontot i listan på **sidan** Användare.</span><span class="sxs-lookup"><span data-stu-id="4391f-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="4391f-120">Användarsidan Microsoft 365 Säkerhetscenter kombinerar information från Microsoft Defender för slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App Security (beroende på vilka licenser du har).</span><span class="sxs-lookup"><span data-stu-id="4391f-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="4391f-121">Den här sidan visar information som är specifik för säkerhetsrisken för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="4391f-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="4391f-122">Detta inkluderar en poäng som hjälper till att bedöma risker och senaste händelser och aviseringar som bidrog till användarens totala risk.</span><span class="sxs-lookup"><span data-stu-id="4391f-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="4391f-123">På den här sidan kan du göra följande ytterligare åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4391f-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="4391f-124">Markera användarkontot som komprometterat</span><span class="sxs-lookup"><span data-stu-id="4391f-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="4391f-125">Kräv att användaren loggar in igen</span><span class="sxs-lookup"><span data-stu-id="4391f-125">Require the user to sign in again</span></span>
- <span data-ttu-id="4391f-126">Stänga av användarkontot</span><span class="sxs-lookup"><span data-stu-id="4391f-126">Suspend the user account</span></span>
- <span data-ttu-id="4391f-127">Se Azure Active Directory (Azure AD) användarkontoinställningar</span><span class="sxs-lookup"><span data-stu-id="4391f-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="4391f-128">Visa de filer som ägs av användarkontot</span><span class="sxs-lookup"><span data-stu-id="4391f-128">View the files owned by the user account</span></span>
- <span data-ttu-id="4391f-129">Visa filer som delas med den här användaren.</span><span class="sxs-lookup"><span data-stu-id="4391f-129">View files shared with this user.</span></span> 

<span data-ttu-id="4391f-130">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="4391f-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exempel på åtgärder på ett användarkonto för en incident i Microsoft 365 säkerhetscenter":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="4391f-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4391f-132">Next steps</span></span>

<span data-ttu-id="4391f-133">Om det behövs för incidenter i processen fortsätter du [din undersökning](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="4391f-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4391f-134">Se även</span><span class="sxs-lookup"><span data-stu-id="4391f-134">See also</span></span>

- [<span data-ttu-id="4391f-135">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="4391f-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4391f-136">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="4391f-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="4391f-137">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="4391f-137">Manage incidents</span></span>](manage-incidents.md)