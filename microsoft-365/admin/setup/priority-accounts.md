---
title: Hantera och övervaka prioriterade konton
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Övervaka misslyckade och fördröjda e-postmeddelanden som skickas till eller från konton med stor inverkan på verksamheten.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233368"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="868c5-103">Hantera och övervaka prioriterade konton</span><span class="sxs-lookup"><span data-stu-id="868c5-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="868c5-104">I alla Microsoft 365-organisationer finns det personer som är viktiga, till exempel chefer, chefer eller andra användare som har tillgång till känslig information, äganderätt eller information med hög prioritet.</span><span class="sxs-lookup"><span data-stu-id="868c5-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="868c5-105">För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och utnyttja appspecifika funktioner som ger dem extra skydd.</span><span class="sxs-lookup"><span data-stu-id="868c5-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="868c5-106">I framtiden kommer fler appar och funktioner att stödja prioriterade konton och till en början har vi meddelat två **funktioner:** prioriterat kontoskydd och övervakning av **premium e-postflöden.**</span><span class="sxs-lookup"><span data-stu-id="868c5-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="868c5-107">**Skydd för prioriterade** konton – Microsoft Defender för Office 365 (tidigare Office 365 Advanced Threat Protection) stöder prioritetskonton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar.</span><span class="sxs-lookup"><span data-stu-id="868c5-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="868c5-108">Mer information finns i [Användartaggar i Microsoft Defender för Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)</span><span class="sxs-lookup"><span data-stu-id="868c5-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="868c5-109">**Övervakning av premium e-postflöde** – Ett felfritt e-postflöde kan vara viktigt för framgången i verksamheten, och leveransfördröjningar och fel kan ha en negativ inverkan på verksamheten.</span><span class="sxs-lookup"><span data-stu-id="868c5-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="868c5-110">Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och visa en rapport med e-postproblem för prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="868c5-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="868c5-111">Mer information finns i rapporten [E-postproblem för prioritetskonton i moderna EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="868c5-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="868c5-112">Metodtips för säkerhet på prioriterade konton finns i [säkerhetsrekommendationer för prioriterade konton.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="868c5-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="868c5-113">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="868c5-113">Before you begin</span></span>

<span data-ttu-id="868c5-114">Skyddsfunktionen **för prioritetskontot** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="868c5-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="868c5-115">Microsoft Defender för Office 365 abonnemang 2, inklusive de med Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="868c5-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="868c5-116">**Premium-funktionen** E-postflödesövervakning som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="868c5-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="868c5-117">Organisationen måste ha ett licensantal på minst 10 000, från någon av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="868c5-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="868c5-118">Din organisation kan till exempel ha 3 000 Office 365 E3-licenser och 8500 Microsoft 365 E5, sammanlagt 11 500 licenser från de kvalificerande produkterna.</span><span class="sxs-lookup"><span data-stu-id="868c5-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="868c5-119">Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.</span><span class="sxs-lookup"><span data-stu-id="868c5-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="868c5-120">Du kan övervaka upp till 250 prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="868c5-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="868c5-121">Lägga till prioritetskonton från sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="868c5-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="868c5-122">Lägg till prioritetskonton från **sidan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="868c5-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="868c5-123">Gå till administrationscentret för Microsoft 365 i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="868c5-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="868c5-124">Gå till **Konfigurationen**  >  **av organisationens** kunskap och **välj Visa** under Övervaka dina **viktigaste konton.**</span><span class="sxs-lookup"><span data-stu-id="868c5-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="868c5-125">Välj **Komma igång** eller **Hantera.**</span><span class="sxs-lookup"><span data-stu-id="868c5-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="868c5-126">Skriv namnet **eller e-postadressen** till den person du vill lägga till i listan med prioriterade konton i sökfältet på sidan Lägg till prioritet-konton.</span><span class="sxs-lookup"><span data-stu-id="868c5-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="868c5-127">Du kan också ange tröskelvärdet för e-post för misslyckade eller fördröjda e-postmeddelanden och få en veckorapport med problem för prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="868c5-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="868c5-128">Markera användaren och välj **Spara.**</span><span class="sxs-lookup"><span data-stu-id="868c5-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="868c5-129">Du kan också lägga till prioriterade konton på sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="868c5-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="868c5-130">Lägg till prioritetskonton från sidan Aktiva användare</span><span class="sxs-lookup"><span data-stu-id="868c5-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="868c5-131">Lägg till prioritetskonton från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="868c5-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="868c5-132">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="868c5-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="868c5-133">Gå till **Användare**  >  **aktiva** användare och **välj ...** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="868c5-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="868c5-134">Välj **Hantera prioritetskonton.**</span><span class="sxs-lookup"><span data-stu-id="868c5-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="868c5-135">Välj **Lägg till** konton  och skriv namnet på den person du vill lägga till i listan med prioriterade konton i sökfältet på sidan Lägg till prioritet-konton.</span><span class="sxs-lookup"><span data-stu-id="868c5-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="868c5-136">Markera användaren och välj **Spara.**</span><span class="sxs-lookup"><span data-stu-id="868c5-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="868c5-137">Ta bort en användare från listan med prioriterade konton</span><span class="sxs-lookup"><span data-stu-id="868c5-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="868c5-138">Gå till administrationscentret för Microsoft 365 i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="868c5-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="868c5-139">Gå till **Konfigurationen**  >  **av organisationens** kunskap och **välj Visa** under Övervaka dina **viktigaste konton.**</span><span class="sxs-lookup"><span data-stu-id="868c5-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="868c5-140">På sidan **Övervaka dina mest konton** väljer du **Prioritet-konton** under **Hantera den här funktionen.**</span><span class="sxs-lookup"><span data-stu-id="868c5-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="868c5-141">På sidan **Priority-konton** väljer du den eller de användare som du vill ta bort från listan och väljer Ta **bort konton.**</span><span class="sxs-lookup"><span data-stu-id="868c5-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="868c5-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="868c5-142">Related topics</span></span>

[<span data-ttu-id="868c5-143">Använda prioritetskonton i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="868c5-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)