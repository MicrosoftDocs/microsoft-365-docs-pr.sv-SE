---
title: Köra en rapport om administratörsrollgrupp i EOP
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du kör en rapport över en administratörsrollgrupp i Exchange Online Protection (EOP).
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034462"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="a3b32-103">Köra en rapport om administratörsrollgrupp i EOP</span><span class="sxs-lookup"><span data-stu-id="a3b32-103">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="a3b32-104">När en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper loggar EOP (Exchange Online Protection) varje förekomst.</span><span class="sxs-lookup"><span data-stu-id="a3b32-104">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="a3b32-105">När du kör en administratörsrollgruppsrapport i Administrationscenter för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, vem som har ändrat rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes.</span><span class="sxs-lookup"><span data-stu-id="a3b32-105">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="a3b32-106">Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3b32-106">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3b32-107">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a3b32-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3b32-108">Beräknad tid att slutföra: 2 minuter</span><span class="sxs-lookup"><span data-stu-id="a3b32-108">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="a3b32-109">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a3b32-109">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a3b32-110">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="a3b32-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="a3b32-111">Information om vilka behörigheter du behöver finns i avsnittet "Rapporter" [i funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a3b32-111">To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="a3b32-112">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a3b32-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="a3b32-113">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="a3b32-113">Having problems?</span></span> <span data-ttu-id="a3b32-114">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="a3b32-114">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="a3b32-115">Använda EAC för att köra en administratörsrollgruppsrapport</span><span class="sxs-lookup"><span data-stu-id="a3b32-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="a3b32-116">Kör rapporten administratörsrollgrupp för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.</span><span class="sxs-lookup"><span data-stu-id="a3b32-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="a3b32-117">I EAC navigerar du till **granskning av** **efterlevnadshantering** \> och väljer Kör en **administratörsrollgruppsrapport**.</span><span class="sxs-lookup"><span data-stu-id="a3b32-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="a3b32-118">Välj **startdatum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="a3b32-118">Choose the **Start date** and **End date**.</span></span> <span data-ttu-id="a3b32-119">Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.</span><span class="sxs-lookup"><span data-stu-id="a3b32-119">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="a3b32-120">Om du vill visa ändringarna för en viss rollgrupp klickar du på **Välj rollgrupper**.</span><span class="sxs-lookup"><span data-stu-id="a3b32-120">To view the changes for a specific role group, click **Select role groups**.</span></span> <span data-ttu-id="a3b32-121">Markera rollgruppen (eller grupperna) i den efterföljande dialogrutan och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3b32-121">Select the role group (or groups) in the subsequent dialog box, and click **OK**.</span></span> <span data-ttu-id="a3b32-122">Du kan också lämna fältet tomt för att hitta alla ändrade rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="a3b32-122">You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="a3b32-123">Klicka på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="a3b32-123">Click **Search**.</span></span>

<span data-ttu-id="a3b32-124">Om några ändringar hittas med hjälp av de angivna villkoren visas de i resultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="a3b32-124">If any changes are found using the criteria you specified, they will appear in the results pane.</span></span> <span data-ttu-id="a3b32-125">Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a3b32-125">Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a3b32-126">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="a3b32-126">How do you know this worked?</span></span>

<span data-ttu-id="a3b32-127">Om du har kört en rapport över administratörsrollgrupper visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="a3b32-127">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane.</span></span> <span data-ttu-id="a3b32-128">Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="a3b32-128">If there are no results, then no changes to role groups have taken place within the specified date range.</span></span> <span data-ttu-id="a3b32-129">Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör rapporten igen.</span><span class="sxs-lookup"><span data-stu-id="a3b32-129">If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="a3b32-130">Övervaka ändringar i rollgruppsmedlemskap</span><span class="sxs-lookup"><span data-stu-id="a3b32-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="a3b32-131">När medlemmar läggs till eller tas bort från en rollgrupp anger sökresultaten i informationsfönstret att rollgruppens medlemskap har uppdaterats och de aktuella medlemmarna visas.</span><span class="sxs-lookup"><span data-stu-id="a3b32-131">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members.</span></span> <span data-ttu-id="a3b32-132">Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.</span><span class="sxs-lookup"><span data-stu-id="a3b32-132">The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="a3b32-133">För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a3b32-133">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="a3b32-134">Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**</span><span class="sxs-lookup"><span data-stu-id="a3b32-134">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="a3b32-135">2018-01-27 16:43</span><span class="sxs-lookup"><span data-stu-id="a3b32-135">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="a3b32-136">Administratör</span><span class="sxs-lookup"><span data-stu-id="a3b32-136">Administrator</span></span> <br> <span data-ttu-id="a3b32-137">Uppdaterade medlemmar: Administratör;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="a3b32-137">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="a3b32-138">2018-06-06 10:09</span><span class="sxs-lookup"><span data-stu-id="a3b32-138">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="a3b32-139">Administratör</span><span class="sxs-lookup"><span data-stu-id="a3b32-139">Administrator</span></span> <br> <span data-ttu-id="a3b32-140">Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="a3b32-140">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="a3b32-141">2018-02-19 14:12</span><span class="sxs-lookup"><span data-stu-id="a3b32-141">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="a3b32-142">Administratör</span><span class="sxs-lookup"><span data-stu-id="a3b32-142">Administrator</span></span> <br> <span data-ttu-id="a3b32-143">Uppdaterade medlemmar: Administratör;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="a3b32-143">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="a3b32-144">I det här exemplet har administratörsanvändarkontot gjort följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="a3b32-144">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="a3b32-145">Den 2018-02-06 lade de till användarens tonip.</span><span class="sxs-lookup"><span data-stu-id="a3b32-145">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="a3b32-146">Den 2018-02-19 tog de bort användarens pilarp.</span><span class="sxs-lookup"><span data-stu-id="a3b32-146">On 2/19/2018, they removed the user pilarp.</span></span>
