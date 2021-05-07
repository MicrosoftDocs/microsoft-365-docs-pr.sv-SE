---
title: Ta bort en tidigare anställd – översikt
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ stegen i den här lösningen för att ta bort en tidigare anställd Microsoft 365 och skydda organisationens data.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241742"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="6a1f2-103">Översikt: Ta bort en tidigare anställd och säkra data</span><span class="sxs-lookup"><span data-stu-id="6a1f2-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="6a1f2-104">En fråga vi ofta får är "Vad ska jag göra för att skydda data och skydda åtkomsten när en anställd lämnar organisationen?"</span><span class="sxs-lookup"><span data-stu-id="6a1f2-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="6a1f2-105">I den här artikeln förklarar vi hur du blockerar åtkomst till Microsoft 365, åtgärder du bör vidta för att skydda dina data och hur du ger andra anställda åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="6a1f2-106">Titta på en kort video om att ta bort en anställd.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="6a1f2-107">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="6a1f2-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="6a1f2-108">Så här hindrar du en anställd från att logga in:</span><span class="sxs-lookup"><span data-stu-id="6a1f2-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="6a1f2-109">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6a1f2-110">Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="6a1f2-111">Ange ett nytt lösenord och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="6a1f2-112">(Skicka det inte till dem.)</span><span class="sxs-lookup"><span data-stu-id="6a1f2-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="6a1f2-113">Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** </span><span class="sxs-lookup"><span data-stu-id="6a1f2-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a1f2-114">Du måste vara global administratör för att kunna starta ut logga ut.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="6a1f2-115">Inom en timme – eller efter att han eller hon lämnar den Microsoft 365 aktuella sidan de befinner sig på – uppmanas de att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="6a1f2-116">En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår för den tokenen och om de navigerar från den aktuella webbsidan.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a1f2-117">Vi har numrerat stegen i den här lösningen och du inte behöver slutföra lösningen i exakt ordning, men vi rekommenderar att du utför stegen så här.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6a1f2-118">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6a1f2-118">Before you begin</span></span>

<span data-ttu-id="6a1f2-119">Du måste vara global administratör för att slutföra stegen i den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6a1f2-120">**Steg**</span><span class="sxs-lookup"><span data-stu-id="6a1f2-120">**Step**</span></span> <br/> |<span data-ttu-id="6a1f2-121">**Varför**</span><span class="sxs-lookup"><span data-stu-id="6a1f2-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="6a1f2-122">Steg 1 – Förhindra en tidigare anställd från att logga in och blockera åtkomst Microsoft 365 tjänster</span><span class="sxs-lookup"><span data-stu-id="6a1f2-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="6a1f2-123">Då blockeras den tidigare anställda från att logga in Microsoft 365 och hindrar personen från att komma Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="6a1f2-124">Steg 2 - Spara innehållet i en tidigare anställds postlåda</span><span class="sxs-lookup"><span data-stu-id="6a1f2-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="6a1f2-125">Det är användbart för den person som ska ta över den anställdas arbete, eller om det finns tvister.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="6a1f2-126">Steg 3 - Vidarebefordra en tidigare anställds e-post till en annan anställd eller konvertera till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="6a1f2-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="6a1f2-p104">Då kan du hålla den före detta anställdas e-postadress aktiv. Om du har kunder eller partners som fortfarande skickar e-post till den före detta anställdas e-postadress hamnar den hos den person som har tagit över arbetet.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="6a1f2-129">Steg 4 – Ge en annan anställd tillgång OneDrive och Outlook data</span><span class="sxs-lookup"><span data-stu-id="6a1f2-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="6a1f2-130">Om du bara tar bort en användares licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="6a1f2-131">Innan du tar bort kontot bör du ge en annan användare åtkomst OneDrive Outlook användare.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="6a1f2-132">Efter att du tagit bort en anställds konto sparas innehållet i OneDrive och Outlook i **30** dagar.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="6a1f2-133">Under de 30 dagarna kan du dock återställa användarens konto och få åtkomst till deras innehåll.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="6a1f2-134">Om du återställer användarens konto förblir OneDrive och Outlook tillgängligt för dig även efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="6a1f2-135">Steg 5 – Rensa och blockera en tidigare anställds mobila enhet</span><span class="sxs-lookup"><span data-stu-id="6a1f2-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="6a1f2-136">Tar bort affärsdata från telefonen eller surfplattan.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="6a1f2-137">Steg 6 - Ta bort och radera Microsoft 365 från en tidigare anställd</span><span class="sxs-lookup"><span data-stu-id="6a1f2-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="6a1f2-p106">När du tar bort en licens kan du tilldela någon annan den. Du kan också radera licensen så att du inte behöver betala för den förrän du anställer någon ny.  </span><span class="sxs-lookup"><span data-stu-id="6a1f2-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="6a1f2-p107">När du tar bort eller raderar en licens sparas användarens gamla e-post, kontakter och kalender i **30 dagar**, och tas sedan bort permanent. Om du tar bort eller raderar en licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.  </span><span class="sxs-lookup"><span data-stu-id="6a1f2-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="6a1f2-142">Steg 7 – Ta bort en tidigare anställds användarkonto</span><span class="sxs-lookup"><span data-stu-id="6a1f2-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="6a1f2-143">Det här tar bort kontot från administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-143">This removes the account from your admin center.</span></span> <span data-ttu-id="6a1f2-144">Hjälper dig att hålla ordning och reda.</span><span class="sxs-lookup"><span data-stu-id="6a1f2-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="6a1f2-145">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6a1f2-145">Related articles</span></span>

[<span data-ttu-id="6a1f2-146">Återställa en användare</span><span class="sxs-lookup"><span data-stu-id="6a1f2-146">Restore a user</span></span>](restore-user.md)
