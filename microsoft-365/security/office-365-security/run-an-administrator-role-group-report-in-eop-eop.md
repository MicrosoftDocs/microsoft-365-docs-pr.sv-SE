---
title: 'Köra en administratörsrollgruppsrapport i EOP '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Administratörer kan lära sig hur du kör en administratörsrollgrupprapport i Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper, Loggar EOP (Microsoft Exchange Online Protection) varje förekomst.
ms.openlocfilehash: d9e7db8accae259b3eb332ce17c52c6749c2bec2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808116"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="6478c-104">Köra en administratörsrollgruppsrapport i EOP</span><span class="sxs-lookup"><span data-stu-id="6478c-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="6478c-105">När en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper loggar EOP -loggningar (Exchange Online Protection) varje förekomst.</span><span class="sxs-lookup"><span data-stu-id="6478c-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="6478c-106">När du kör en administratörsrollgrupprapport i Administrationscentret för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, som ändrade rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes.</span><span class="sxs-lookup"><span data-stu-id="6478c-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="6478c-107">Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6478c-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6478c-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6478c-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6478c-109">Beräknad tid att slutföra: 2 minuter</span><span class="sxs-lookup"><span data-stu-id="6478c-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="6478c-110">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6478c-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6478c-111">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="6478c-111">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="6478c-112">Om du vill se vilka behörigheter du behöver läser du avsnittet "Rapporter" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6478c-112">To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="6478c-113">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6478c-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6478c-114">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="6478c-114">Having problems?</span></span> <span data-ttu-id="6478c-115">Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="6478c-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="6478c-116">Använda EAC för att köra en administratörsrollgrupprapport</span><span class="sxs-lookup"><span data-stu-id="6478c-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="6478c-117">Kör rapport för administratörsrollgruppen för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.</span><span class="sxs-lookup"><span data-stu-id="6478c-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="6478c-118">I EAC navigerar du till **Granskning** **av efterlevnadshantering** \> och väljer Kör en rapport över **en administratörsrollgrupp**.</span><span class="sxs-lookup"><span data-stu-id="6478c-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="6478c-119">Välj **startdatum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="6478c-119">Choose the **Start date** and **End date**.</span></span> <span data-ttu-id="6478c-120">Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.</span><span class="sxs-lookup"><span data-stu-id="6478c-120">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="6478c-121">Om du vill visa ändringarna för en viss rollgrupp klickar du på **Välj rollgrupper**.</span><span class="sxs-lookup"><span data-stu-id="6478c-121">To view the changes for a specific role group, click **Select role groups**.</span></span> <span data-ttu-id="6478c-122">Markera rollgruppen (eller grupperna) i den efterföljande dialogrutan och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6478c-122">Select the role group (or groups) in the subsequent dialog box, and click **OK**.</span></span> <span data-ttu-id="6478c-123">Du kan också lämna fältet tomt för att hitta alla ändrade rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="6478c-123">You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="6478c-124">Klicka på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="6478c-124">Click **Search**.</span></span>

<span data-ttu-id="6478c-125">Om några ändringar hittas med de villkor som du har angett visas de i resultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="6478c-125">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="6478c-126">Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6478c-126">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6478c-127">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="6478c-127">How do you know this worked?</span></span>

<span data-ttu-id="6478c-128">Om du har kört en rapport över en administratörsrollgrupp visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="6478c-128">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="6478c-129">Om det inte finns några resultat har inga ändringar av rollgrupper ägt rum inom det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="6478c-129">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="6478c-130">Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör sedan rapporten igen.</span><span class="sxs-lookup"><span data-stu-id="6478c-130">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="6478c-131">Övervaka ändringar i rollgruppsmedlemskap</span><span class="sxs-lookup"><span data-stu-id="6478c-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="6478c-132">När medlemmar läggs till eller tas bort från en rollgrupp visar sökresultaten i informationsfönstret att rollgruppsmedlemskapet har uppdaterats och visar de aktuella medlemmarna.</span><span class="sxs-lookup"><span data-stu-id="6478c-132">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="6478c-133">Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.</span><span class="sxs-lookup"><span data-stu-id="6478c-133">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="6478c-134">För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata transaktioner i rapporten.</span><span class="sxs-lookup"><span data-stu-id="6478c-134">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="6478c-135">Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**</span><span class="sxs-lookup"><span data-stu-id="6478c-135">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="6478c-136">1/27/2018 16:43</span><span class="sxs-lookup"><span data-stu-id="6478c-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="6478c-137">Administratör</span><span class="sxs-lookup"><span data-stu-id="6478c-137">Administrator</span></span> <br> <span data-ttu-id="6478c-138">Uppdaterade medlemmar: Administratör;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="6478c-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="6478c-139">2/06/2018 10:09</span><span class="sxs-lookup"><span data-stu-id="6478c-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="6478c-140">Administratör</span><span class="sxs-lookup"><span data-stu-id="6478c-140">Administrator</span></span> <br> <span data-ttu-id="6478c-141">Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="6478c-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="6478c-142">2/19/2018 14:12</span><span class="sxs-lookup"><span data-stu-id="6478c-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="6478c-143">Administratör</span><span class="sxs-lookup"><span data-stu-id="6478c-143">Administrator</span></span> <br> <span data-ttu-id="6478c-144">Uppdaterade medlemmar: Administratör;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="6478c-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="6478c-145">I det här exemplet gjorde administratörsanvändarkontot följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="6478c-145">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="6478c-146">Den 2/06/2018 lade de till användaren tonip.</span><span class="sxs-lookup"><span data-stu-id="6478c-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="6478c-147">Den 2/19/2018 tog de bort användaren.</span><span class="sxs-lookup"><span data-stu-id="6478c-147">On 2/19/2018, they removed the user pilarp.</span></span>
