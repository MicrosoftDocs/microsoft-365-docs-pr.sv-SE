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
description: Övervakar misslyckade och fördröjda meddelanden som skickas till eller från konton som har stor rörelse påverkan.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477619"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="1cd43-103">Hantera och övervaka prioriterade konton</span><span class="sxs-lookup"><span data-stu-id="1cd43-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="1cd43-104">I alla Microsoft 365-organisationer finns det personer som är nödvändiga, till exempel chefer, ledare, chefer eller andra användare som har till gång till känslig, tillverkarspecifik eller hög prioritets information.</span><span class="sxs-lookup"><span data-stu-id="1cd43-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="1cd43-105">För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och använda programspecifika funktioner som ger dem extra skydd.</span><span class="sxs-lookup"><span data-stu-id="1cd43-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="1cd43-106">I framtiden stöder fler appar och funktioner prioritets konton och för att börja med, har vi meddelat två möjligheter: **prioriterat konto skydd** och **övervakning av e-postflöde**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="1cd43-107">**Prioriterat konto skydd** -Microsoft Defender för Office 365 (tidigare Office 365 Avancerat skydd) stöder prioriterade konton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar.</span><span class="sxs-lookup"><span data-stu-id="1cd43-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="1cd43-108">Mer information finns [i användar koder i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1cd43-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="1cd43-109">**Premium-flödet för e-postflöden** kan vara kritiskt för företags framgångar och leverans fördröjningar och problem kan påverka verksamheten negativt.</span><span class="sxs-lookup"><span data-stu-id="1cd43-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="1cd43-110">Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och se en rapport om e-postproblem för prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="1cd43-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="1cd43-111">För mer information, se [e-postproblem för rapport med prioriterade konton i moderna UK](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span><span class="sxs-lookup"><span data-stu-id="1cd43-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1cd43-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1cd43-112">Before you begin</span></span>

<span data-ttu-id="1cd43-113">Funktionen **prioriterat konto skydd** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="1cd43-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1cd43-114">Microsoft Defender för Office 365 abonnemang 2, inklusive de som har Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="1cd43-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="1cd43-115">Övervaknings funktionen för **Premium mail-flöde** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="1cd43-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1cd43-116">Din organisation måste ha ett licens antal på minst 10 000, antingen från en av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="1cd43-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="1cd43-117">Din organisation kan till exempel ha 3000 Office 365 E3-licenser och 8500 Microsoft 365 E5, för totalt antal 11 500 licenser från kvalificerings produkterna.</span><span class="sxs-lookup"><span data-stu-id="1cd43-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="1cd43-118">Din organisation måste ha minst 50 månads aktiva Exchange Online-användare.</span><span class="sxs-lookup"><span data-stu-id="1cd43-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="1cd43-119">Du kan övervaka upp till 250 prioritets konton.</span><span class="sxs-lookup"><span data-stu-id="1cd43-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="1cd43-120">Lägga till prioritets konton från konfigurations Sidan</span><span class="sxs-lookup"><span data-stu-id="1cd43-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="1cd43-121">Lägga till prioritets konton från **inställnings sidan**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="1cd43-122">Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="1cd43-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1cd43-123">Gå till **Konfigurera**  >  **organisationens kunskap** och välj **Visa** under **övervaka dina mest viktiga konton**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1cd43-124">Välj **komma igång** eller **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="1cd43-125">Skriv namnet eller e-postadressen för den person som du vill lägga till i listan prioritets konton i Sök fältet på sidan **Lägg till prioritets konton** .</span><span class="sxs-lookup"><span data-stu-id="1cd43-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="1cd43-126">Du kan också ange din e-postgräns för misslyckade eller fördröjda e-postmeddelanden och få en vecko rapport om problem med prioritets konton.</span><span class="sxs-lookup"><span data-stu-id="1cd43-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="1cd43-127">Markera användaren och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="1cd43-128">Du kan också lägga till prioritets konton från sidan aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="1cd43-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="1cd43-129">Lägga till prioritets konton från sidan aktiva användare</span><span class="sxs-lookup"><span data-stu-id="1cd43-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="1cd43-130">Lägga till prioritets konton från sidan aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="1cd43-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="1cd43-131">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="1cd43-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1cd43-132">Gå till **användare**  >  **aktiva användare** och välj **...** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="1cd43-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="1cd43-133">Välj **Hantera prioritets konton**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="1cd43-134">Välj **Lägg till konton** och skriv namnet på den person som du vill lägga till i listan med prioriterade konton i Sök fältet på sidan **Lägg till prioritets konton** .</span><span class="sxs-lookup"><span data-stu-id="1cd43-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="1cd43-135">Markera användaren och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="1cd43-136">Ta bort en användare från listan med prioriterade konton</span><span class="sxs-lookup"><span data-stu-id="1cd43-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="1cd43-137">Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="1cd43-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1cd43-138">Gå till **Konfigurera**  >  **organisationens kunskap** och välj **Visa** under **övervaka dina mest viktiga konton**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1cd43-139">Välj **prioritets konton** under **hantera den här funktionen** på sidan **övervaka dina mest konton** .</span><span class="sxs-lookup"><span data-stu-id="1cd43-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="1cd43-140">På sidan **Priority Accounts** väljer du den eller de användare du vill ta bort från listan och väljer **ta bort konton**.</span><span class="sxs-lookup"><span data-stu-id="1cd43-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cd43-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1cd43-141">Related topics</span></span>

[<span data-ttu-id="1cd43-142">Använda prioriterade konton i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1cd43-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)