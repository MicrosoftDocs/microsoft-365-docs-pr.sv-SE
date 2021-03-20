---
title: Hantera och övervaka prioritetskonton
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
description: Övervaka misslyckades och fördröjda e-postmeddelanden som skickas till eller från konton som har stor inverkan på verksamheten.
ms.openlocfilehash: b31cbf79b5b1b8f882c4c7bc8926779410baefe3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914060"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="eb168-103">Hantera och övervaka prioritetskonton</span><span class="sxs-lookup"><span data-stu-id="eb168-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="eb168-104">I varje Microsoft 365-organisation finns det personer som är viktiga, t.ex. chefer, chefer eller andra användare som har tillgång till känslig, egenutvecklad eller högprioriterad information.</span><span class="sxs-lookup"><span data-stu-id="eb168-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="eb168-105">För att hjälpa din organisation att skydda dessa konton kan du nu ange specifika användare som prioriterade konton och utnyttja appspecifika funktioner som ger dem extra skydd.</span><span class="sxs-lookup"><span data-stu-id="eb168-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="eb168-106">I framtiden kommer fler appar och funktioner att stödja prioritetskonton, och till en början har vi meddelat två **funktioner:** prioriterat kontoskydd och övervakning av **premium-e-postflöden.**</span><span class="sxs-lookup"><span data-stu-id="eb168-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="eb168-107">**Skydd av prioriterade** konton – Microsoft Defender för Office 365 (tidigare Office 365 Advanced Threat Protection) har stöd för prioritetskonton som taggar som kan användas i filter i aviseringar, rapporter och undersökningar.</span><span class="sxs-lookup"><span data-stu-id="eb168-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="eb168-108">Mer information finns i [Användartaggar i Microsoft Defender för Office 365.](../../security/office-365-security/user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="eb168-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>
- <span data-ttu-id="eb168-109">**Premium övervakning av e-postflöde** – Felfritt e-postflöde kan vara viktigt för att verksamheten ska lyckas, och leveransfördröjningar och fel kan påverka verksamheten negativt.</span><span class="sxs-lookup"><span data-stu-id="eb168-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="eb168-110">Du kan välja ett tröskelvärde för misslyckade eller fördröjda e-postmeddelanden, få aviseringar när tröskelvärdet överskrids och visa en rapport om e-postproblem för prioritetskonton.</span><span class="sxs-lookup"><span data-stu-id="eb168-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="eb168-111">Mer information finns i rapporten [E-postproblem för prioritetskonton i den moderna EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="eb168-111">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="eb168-112">Information om metodtips för säkerhet på prioriterade konton finns i [Säkerhetsrekommendationer för prioritetskonton.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="eb168-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eb168-113">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="eb168-113">Before you begin</span></span>

<span data-ttu-id="eb168-114">Funktionen **för att skydda** ett Priority-konto som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="eb168-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eb168-115">Microsoft Defender för Office 365 abonnemang 2, inklusive de med Office 365 E3, Office 365 E5, Microsoft 365 E5 eller Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="eb168-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="eb168-116">Den **premiumfunktion för e-postflödesövervakning** som beskrivs i det här avsnittet är endast tillgänglig för organisationer som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="eb168-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eb168-117">Organisationen måste ha ett antal licenser på minst 10 000, från en av eller en kombination av följande produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eb168-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="eb168-118">Din organisation kan till exempel ha 3 000 Office 365 E3-licenser och 8500 Microsoft 365 E5, sammanlagt 11 500 licenser från de kvalificerande produkterna.</span><span class="sxs-lookup"><span data-stu-id="eb168-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="eb168-119">Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.</span><span class="sxs-lookup"><span data-stu-id="eb168-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="eb168-120">Du kan övervaka upp till 250 prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="eb168-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="eb168-121">Lägg till prioritetskonton från sidan Inställningar</span><span class="sxs-lookup"><span data-stu-id="eb168-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="eb168-122">Lägg till prioritetskonton från **sidan Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="eb168-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="eb168-123">Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eb168-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb168-124">Gå till **Kunskap**  >  **om konfigurationen** av organisationen och välj **Visa** under Övervaka dina **viktigaste konton.**</span><span class="sxs-lookup"><span data-stu-id="eb168-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eb168-125">Välj **Komma igång** eller **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="eb168-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="eb168-126">På sidan **Lägg till prioritetskonton** skriver du namnet eller e-postadressen för den person du vill lägga till i listan med prioritetskonton i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="eb168-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="eb168-127">Du kan också ange tröskelvärdet för e-post för misslyckade eller fördröjda e-postmeddelanden och få en veckorapport med problem för prioritetskonton.</span><span class="sxs-lookup"><span data-stu-id="eb168-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="eb168-128">Markera användaren och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb168-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="eb168-129">Du kan också lägga till prioritetskonton från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="eb168-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="eb168-130">Lägg till prioritetskonton från sidan Aktiva användare</span><span class="sxs-lookup"><span data-stu-id="eb168-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="eb168-131">Lägg till prioritetskonton från sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="eb168-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="eb168-132">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="eb168-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb168-133">Gå **till Användare**  >  **aktiva** användare och **välj ...** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="eb168-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="eb168-134">Välj **Hantera prioritetskonton.**</span><span class="sxs-lookup"><span data-stu-id="eb168-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="eb168-135">Välj **Lägg till** konton  och skriv namnet på den person du vill lägga till i listan prioritetskonton i sökfältet på sidan Lägg till prioritetskonton.</span><span class="sxs-lookup"><span data-stu-id="eb168-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="eb168-136">Markera användaren och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="eb168-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="eb168-137">Ta bort en användare från listan med prioriterade konton</span><span class="sxs-lookup"><span data-stu-id="eb168-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="eb168-138">Gå till administrationscentret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eb168-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb168-139">Gå till **Kunskap**  >  **om konfigurationen** av organisationen och välj **Visa** under Övervaka dina **viktigaste konton.**</span><span class="sxs-lookup"><span data-stu-id="eb168-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eb168-140">På sidan **Övervaka dina konton mest** väljer du **Prioritet-konton** under **Hantera den här funktionen.**</span><span class="sxs-lookup"><span data-stu-id="eb168-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="eb168-141">På sidan **Priority accounts** väljer du den eller de användare du vill ta bort från listan och väljer Ta **bort konton.**</span><span class="sxs-lookup"><span data-stu-id="eb168-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb168-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="eb168-142">Related topics</span></span>

[<span data-ttu-id="eb168-143">Använda prioritetskonton i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb168-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)