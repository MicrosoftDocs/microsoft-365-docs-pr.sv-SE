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
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663613"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="04a9e-104">Användarmallar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="04a9e-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="04a9e-105">Funktionen användar koder är i förhands granskning, inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="04a9e-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="04a9e-106">Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="04a9e-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="04a9e-107">User-taggar är identifierare för specifika grupper med användare i [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="04a9e-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="04a9e-108">Det finns två typer av användar flaggor:</span><span class="sxs-lookup"><span data-stu-id="04a9e-108">There are two types of user tags:</span></span>

- <span data-ttu-id="04a9e-109">**System märkning**: [prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är för närvarande den enda typen av system märkning.</span><span class="sxs-lookup"><span data-stu-id="04a9e-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="04a9e-110">**Anpassade taggar**: du skapar dem själv.</span><span class="sxs-lookup"><span data-stu-id="04a9e-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="04a9e-111">Om din organisation har Defender för Office 365 abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen Priority accounts.</span><span class="sxs-lookup"><span data-stu-id="04a9e-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="04a9e-112">När du har använt system koder eller anpassade taggar för användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="04a9e-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="04a9e-113">Aviseringar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="04a9e-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="04a9e-114">Threat Explorer och real tids identifiering</span><span class="sxs-lookup"><span data-stu-id="04a9e-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="04a9e-115">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="04a9e-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="04a9e-116">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="04a9e-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="04a9e-117">För prioriterade konton kan du använda rapporten med [e-postproblem för prioriterade konton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrations centret för Exchange (UK).</span><span class="sxs-lookup"><span data-stu-id="04a9e-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="04a9e-118">I den här artikeln förklaras hur du konfigurerar användar koder i fältet säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="04a9e-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="04a9e-119">Det finns inga cmdletar i säkerhets & kompatibilitetstillstånd för att hantera användar koder.</span><span class="sxs-lookup"><span data-stu-id="04a9e-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04a9e-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="04a9e-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04a9e-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="04a9e-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="04a9e-122">Öppna för att gå direkt till sidan **User Tags** <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="04a9e-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="04a9e-123">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="04a9e-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="04a9e-124">Om du vill skapa, ändra och ta bort användar flaggor måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="04a9e-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="04a9e-125">För att lägga till och ta bort medlemmar från befintliga användar flaggor måste du vara medlem i roll grupperna **organisations ledning**, **säkerhets administratör** eller **säkerhets ansvarig**</span><span class="sxs-lookup"><span data-stu-id="04a9e-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="04a9e-126">För skrivskyddad åtkomst till användar flaggor måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .</span><span class="sxs-lookup"><span data-stu-id="04a9e-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="04a9e-127">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04a9e-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="04a9e-128">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="04a9e-128">**Notes**:</span></span>

  - <span data-ttu-id="04a9e-129">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04a9e-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="04a9e-130">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="04a9e-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="04a9e-131">Hantering av användar märkning styrs av rollerna **etikett läsare**, **tagga deltagare** och **taggredigerare** .</span><span class="sxs-lookup"><span data-stu-id="04a9e-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="04a9e-132">Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04a9e-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="04a9e-133">Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="04a9e-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="04a9e-134">Använda säkerhets Center för att skapa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="04a9e-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="04a9e-135">Gå till användar märkning för **Threat Management** i säkerhets Center \> .</span><span class="sxs-lookup"><span data-stu-id="04a9e-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="04a9e-136">På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="04a9e-137">Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="04a9e-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="04a9e-138">**Name**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="04a9e-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="04a9e-139">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="04a9e-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="04a9e-140">**Beskrivning**: Ange en valfri beskrivning för märket.</span><span class="sxs-lookup"><span data-stu-id="04a9e-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="04a9e-141">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="04a9e-142">Gör något av följande på sidan **tilldela användare** :</span><span class="sxs-lookup"><span data-stu-id="04a9e-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="04a9e-143">Klicka på **Lägg till användare**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-143">Click **Add users**.</span></span> <span data-ttu-id="04a9e-144">Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:</span><span class="sxs-lookup"><span data-stu-id="04a9e-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="04a9e-145">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="04a9e-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="04a9e-146">Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="04a9e-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="04a9e-147">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="04a9e-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="04a9e-148">Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.</span><span class="sxs-lookup"><span data-stu-id="04a9e-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="04a9e-149">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="04a9e-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="04a9e-150">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="04a9e-151">Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="04a9e-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="04a9e-152">Kontrol lera att text filen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="04a9e-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="04a9e-153">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="04a9e-154">På sidan **Granska tagg** granskar du dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="04a9e-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="04a9e-155">Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="04a9e-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="04a9e-156">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="04a9e-157">Använda säkerhets Center för att Visa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="04a9e-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="04a9e-158">Gå till användar märkning för **Threat Management** i säkerhets Center \> .</span><span class="sxs-lookup"><span data-stu-id="04a9e-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="04a9e-159">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="04a9e-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="04a9e-160">I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.</span><span class="sxs-lookup"><span data-stu-id="04a9e-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="04a9e-161">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="04a9e-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="04a9e-162">Använda säkerhets Center för att ändra användar flaggor</span><span class="sxs-lookup"><span data-stu-id="04a9e-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="04a9e-163">Gå till användar märkning för **Threat Management** i säkerhets Center \> .</span><span class="sxs-lookup"><span data-stu-id="04a9e-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="04a9e-164">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="04a9e-165">Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="04a9e-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="04a9e-166">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="04a9e-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="04a9e-167">Använda säkerhets Center för att ta bort taggar</span><span class="sxs-lookup"><span data-stu-id="04a9e-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="04a9e-168">**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.</span><span class="sxs-lookup"><span data-stu-id="04a9e-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="04a9e-169">Gå till användar märkning för **Threat Management** i säkerhets Center \> .</span><span class="sxs-lookup"><span data-stu-id="04a9e-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="04a9e-170">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga** och väljer sedan **Ja, ta bort** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="04a9e-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
