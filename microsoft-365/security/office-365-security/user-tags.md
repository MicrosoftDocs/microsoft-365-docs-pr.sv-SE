---
title: Användartaggar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att identifiera specifika grupper av användare med användartaggar i Microsoft Defender för Office 365 abonnemang 2. Taggfiltrering är tillgängligt för aviseringar, rapporter och undersökningar i Microsoft Defender för Office 365 för att snabbt identifiera taggade användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e5ddffad6405f48a9af55b5123729eb256064a7
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453651"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bb054-104">Användartaggar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="bb054-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="bb054-105">Funktionen med användartaggar är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="bb054-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="bb054-106">Mer information om versionsschemat finns i Microsoft [365-översikten.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="bb054-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="bb054-107">Användartaggar är identifierare för specifika användargrupper i [Microsoft Defender för Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="bb054-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="bb054-108">Det finns två typer av användartaggar:</span><span class="sxs-lookup"><span data-stu-id="bb054-108">There are two types of user tags:</span></span>

- <span data-ttu-id="bb054-109">**Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.</span><span class="sxs-lookup"><span data-stu-id="bb054-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="bb054-110">**Anpassade taggar:** Du skapar dessa användartaggar själv.</span><span class="sxs-lookup"><span data-stu-id="bb054-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="bb054-111">Om din organisation har Defender för Office 365 Abonnemang 2 (ingår i din prenumeration eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioriterade konton.</span><span class="sxs-lookup"><span data-stu-id="bb054-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="bb054-112">När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="bb054-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="bb054-113">Varningar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="bb054-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="bb054-114">Hotutforskaren och identifieringar i realtid</span><span class="sxs-lookup"><span data-stu-id="bb054-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="bb054-115">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="bb054-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="bb054-116">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="bb054-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="bb054-117">För prioriterade konton kan du använda rapporten [E-postproblem för prioritetskonton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="bb054-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="bb054-118">I den här artikeln förklaras hur du konfigurerar användartaggar & Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="bb054-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="bb054-119">Det finns inga cmdlets i Säkerhets- & för att hantera användartaggar.</span><span class="sxs-lookup"><span data-stu-id="bb054-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bb054-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="bb054-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bb054-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="bb054-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bb054-122">Gå direkt till sidan **med användartaggar** genom att <https://protection.office.com/userTags> öppna.</span><span class="sxs-lookup"><span data-stu-id="bb054-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="bb054-123">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="bb054-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bb054-124">Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="bb054-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bb054-125">Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller **Säkerhetsoperator**</span><span class="sxs-lookup"><span data-stu-id="bb054-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="bb054-126">För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** **eller** Säkerhetsläsare.</span><span class="sxs-lookup"><span data-stu-id="bb054-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bb054-127">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bb054-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="bb054-128">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="bb054-128">**Notes**:</span></span>

  - <span data-ttu-id="bb054-129">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb054-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bb054-130">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb054-130">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="bb054-131">Hantering av användartaggar styrs av **rollerna Taggläsare** **och Tagghanteraren.**</span><span class="sxs-lookup"><span data-stu-id="bb054-131">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="bb054-132">Du kan också hantera och övervaka prioriterade konton i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb054-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bb054-133">Instruktioner finns i Hantera [och övervaka prioriterade konton.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="bb054-133">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="bb054-134">Använda Säkerhetscenter för att skapa användartaggar</span><span class="sxs-lookup"><span data-stu-id="bb054-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="bb054-135">Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="bb054-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="bb054-136">Klicka på **Skapa tagg** på sidan Med **användartaggar som öppnas.**</span><span class="sxs-lookup"><span data-stu-id="bb054-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="bb054-137">Guiden **Skapa tagg** öppnas i en ny flyg utfällning. Konfigurera följande **inställningar** på sidan Definiera tagg:</span><span class="sxs-lookup"><span data-stu-id="bb054-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="bb054-138">**Namn:** Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="bb054-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="bb054-139">Det här är det värde som visas och används.</span><span class="sxs-lookup"><span data-stu-id="bb054-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="bb054-140">**Beskrivning:** Ange en valfri beskrivning för taggen.</span><span class="sxs-lookup"><span data-stu-id="bb054-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="bb054-141">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="bb054-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bb054-142">Gör något **av följande** på sidan Tilldela användare:</span><span class="sxs-lookup"><span data-stu-id="bb054-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="bb054-143">Klicka **på Lägg till användare.**</span><span class="sxs-lookup"><span data-stu-id="bb054-143">Click **Add users**.</span></span> <span data-ttu-id="bb054-144">I den utfälling som visas gör du något av följande för att lägga till enskilda användare eller grupper:</span><span class="sxs-lookup"><span data-stu-id="bb054-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="bb054-145">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="bb054-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="bb054-146">Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="bb054-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="bb054-147">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="bb054-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="bb054-148">Om du vill ta bort enskilda poster i rutan klickar du **på ikonen** Ta bort för användaren eller gruppen ![ i ](../../media/scc-remove-icon.png) rutan.</span><span class="sxs-lookup"><span data-stu-id="bb054-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="bb054-149">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta** ![ bort-ikonen ](../../media/scc-remove-icon.png) för posten.</span><span class="sxs-lookup"><span data-stu-id="bb054-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="bb054-150">Klicka på Lägg till när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="bb054-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="bb054-151">Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="bb054-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="bb054-152">Kontrollera att textfilen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="bb054-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="bb054-153">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="bb054-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bb054-154">Granska **inställningarna på taggsidan** Granska.</span><span class="sxs-lookup"><span data-stu-id="bb054-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="bb054-155">Du kan klicka **på Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="bb054-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="bb054-156">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="bb054-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="bb054-157">Använda Säkerhetscenter för att visa användartaggar</span><span class="sxs-lookup"><span data-stu-id="bb054-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="bb054-158">Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="bb054-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="bb054-159">På sidan **med användartaggar** som öppnas väljer du den användartagg som du vill visa (klicka inte i kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="bb054-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="bb054-160">Granska inställningarna i den skrivskyddade informationen som visas.</span><span class="sxs-lookup"><span data-stu-id="bb054-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="bb054-161">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="bb054-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="bb054-162">Använda Säkerhetscenter för att ändra användartaggar</span><span class="sxs-lookup"><span data-stu-id="bb054-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="bb054-163">Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="bb054-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="bb054-164">På sidan **med användartaggar** som öppnas väljer du den användartagg som du vill visa och klickar sedan på **Redigera tagg.**</span><span class="sxs-lookup"><span data-stu-id="bb054-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="bb054-165">Principguiden öppnas i en **redigeringstagg.** Klicka **på** Nästa för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="bb054-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="bb054-166">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="bb054-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="bb054-167">Använda Säkerhetscenter för att ta bort användartaggar</span><span class="sxs-lookup"><span data-stu-id="bb054-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="bb054-168">**Obs!** Du kan inte ta bort den inbyggda taggen **Priority-konto.**</span><span class="sxs-lookup"><span data-stu-id="bb054-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="bb054-169">Gå till Användartaggar för hantering **av** hot i \> **Säkerhetscenter.**</span><span class="sxs-lookup"><span data-stu-id="bb054-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="bb054-170">På sidan **med användartaggar** som öppnas markerar du den användartagg du vill ta bort, klickar på Ta bort tagg och väljer Sedan **Ja,** ta bort i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="bb054-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
