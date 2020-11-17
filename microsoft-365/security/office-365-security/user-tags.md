---
title: Användarmallar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att identifiera specifika grupper med användare med användar koder i Microsoft Defender för Office 365 abonnemang 2. För att snabbt identifiera taggade användare kan du använda tagg filtrering för meddelanden, rapporter och undersökningar i Microsoft Defender för Office 365.
ms.openlocfilehash: 14ebcebeb8081a2de341fd06facabd9f7d55b119
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123625"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4daea-104">Användarmallar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4daea-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="4daea-105">Funktionen användar koder är i förhands granskning, inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="4daea-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="4daea-106">Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="4daea-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="4daea-107">User-taggar är identifierare för specifika grupper med användare i [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="4daea-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="4daea-108">Det finns två typer av användar flaggor:</span><span class="sxs-lookup"><span data-stu-id="4daea-108">There are two types of user tags:</span></span>

- <span data-ttu-id="4daea-109">**System märkning**: [prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är för närvarande den enda typen av system märkning.</span><span class="sxs-lookup"><span data-stu-id="4daea-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="4daea-110">**Anpassade taggar**: du skapar dem själv.</span><span class="sxs-lookup"><span data-stu-id="4daea-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="4daea-111">Om din organisation har Defender för Office 365 abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen Priority accounts.</span><span class="sxs-lookup"><span data-stu-id="4daea-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="4daea-112">När du har använt system koder eller anpassade taggar för användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="4daea-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="4daea-113">Aviseringar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="4daea-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="4daea-114">Threat Explorer och real tids identifiering</span><span class="sxs-lookup"><span data-stu-id="4daea-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="4daea-115">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="4daea-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="4daea-116">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="4daea-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="4daea-117">För prioriterade konton kan du använda rapporten med [e-postproblem för prioriterade konton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrations centret för Exchange (UK).</span><span class="sxs-lookup"><span data-stu-id="4daea-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="4daea-118">I den här artikeln förklaras hur du konfigurerar användar koder i fältet säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4daea-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="4daea-119">Det finns inga cmdletar i säkerhets & kompatibilitetstillstånd för att hantera användar koder.</span><span class="sxs-lookup"><span data-stu-id="4daea-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4daea-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4daea-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4daea-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4daea-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4daea-122">Öppna för att gå direkt till sidan **User Tags** <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="4daea-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="4daea-123">För att skapa, ändra eller ta bort **anpassade användar flaggor** måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4daea-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="4daea-124">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4daea-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4daea-125">Du måste vara [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)för att kunna konfigurera prioritets konton (systemtaggar).</span><span class="sxs-lookup"><span data-stu-id="4daea-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="4daea-126">Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4daea-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4daea-127">Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="4daea-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="4daea-128">Använda säkerhets Center för att skapa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4daea-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="4daea-129">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4daea-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4daea-130">På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.</span><span class="sxs-lookup"><span data-stu-id="4daea-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="4daea-131">Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4daea-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="4daea-132">**Name**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="4daea-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="4daea-133">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="4daea-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="4daea-134">**Beskrivning**: Ange en valfri beskrivning för märket.</span><span class="sxs-lookup"><span data-stu-id="4daea-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="4daea-135">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4daea-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4daea-136">Gör något av följande på sidan **tilldela post lådor** :</span><span class="sxs-lookup"><span data-stu-id="4daea-136">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="4daea-137">Klicka på **Lägg till post lådor**.</span><span class="sxs-lookup"><span data-stu-id="4daea-137">Click **Add mailboxes**.</span></span> <span data-ttu-id="4daea-138">Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:</span><span class="sxs-lookup"><span data-stu-id="4daea-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="4daea-139">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="4daea-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="4daea-140">Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="4daea-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="4daea-141">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="4daea-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="4daea-142">Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.</span><span class="sxs-lookup"><span data-stu-id="4daea-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="4daea-143">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="4daea-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="4daea-144">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4daea-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="4daea-145">Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="4daea-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="4daea-146">Kontrol lera att text filen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="4daea-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="4daea-147">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4daea-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4daea-148">På sidan **Granska tagg** granskar du dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="4daea-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="4daea-149">Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="4daea-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="4daea-150">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4daea-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="4daea-151">Använda säkerhets Center för att Visa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4daea-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="4daea-152">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4daea-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4daea-153">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="4daea-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="4daea-154">I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.</span><span class="sxs-lookup"><span data-stu-id="4daea-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="4daea-155">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4daea-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="4daea-156">Använda säkerhets Center för att ändra användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4daea-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="4daea-157">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4daea-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4daea-158">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="4daea-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="4daea-159">Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="4daea-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="4daea-160">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4daea-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="4daea-161">Använda säkerhets Center för att ta bort taggar</span><span class="sxs-lookup"><span data-stu-id="4daea-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="4daea-162">**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.</span><span class="sxs-lookup"><span data-stu-id="4daea-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="4daea-163">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4daea-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4daea-164">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga** och väljer sedan **Ja, ta bort** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="4daea-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
