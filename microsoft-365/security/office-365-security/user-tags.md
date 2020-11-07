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
ms.openlocfilehash: 9c83a323a3116b3da61a133c7fb449978ca13841
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945324"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a8a8c-104">Användarmallar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="a8a8c-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="a8a8c-105">Funktionen användar koder är i förhands granskning, inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="a8a8c-106">Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="a8a8c-107">User-taggar är identifierare för specifika grupper med användare i [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="a8a8c-108">Det finns två typer av användar flaggor:</span><span class="sxs-lookup"><span data-stu-id="a8a8c-108">There are two types of user tags:</span></span>

- <span data-ttu-id="a8a8c-109">**System märkning** : [prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är för närvarande den enda typen av system märkning.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="a8a8c-110">**Anpassade taggar** : du skapar dem själv.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="a8a8c-111">Om din organisation har Defender för Office 365 abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen Priority accounts.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="a8a8c-112">När du har använt system koder eller anpassade taggar för användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="a8a8c-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="a8a8c-113">Aviseringar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="a8a8c-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="a8a8c-114">Threat Explorer och real tids identifiering</span><span class="sxs-lookup"><span data-stu-id="a8a8c-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="a8a8c-115">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="a8a8c-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="a8a8c-116">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="a8a8c-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="a8a8c-117">I den här artikeln förklaras hur du konfigurerar användar koder i fältet säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="a8a8c-118">Det finns inga cmdletar i säkerhets & kompatibilitetstillstånd för att hantera användar koder.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a8a8c-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a8a8c-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a8a8c-120">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a8a8c-121">Öppna för att gå direkt till sidan **User Tags** <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="a8a8c-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="a8a8c-122">För att skapa, ändra eller ta bort **anpassade användar flaggor** måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a8a8c-123">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a8a8c-124">Du måste vara [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)för att kunna konfigurera prioritets konton (systemtaggar).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="a8a8c-125">Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a8a8c-126">Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="a8a8c-127">Använda säkerhets Center för att skapa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="a8a8c-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="a8a8c-128">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a8a8c-129">På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="a8a8c-130">Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8a8c-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="a8a8c-131">**Name** : Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="a8a8c-132">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="a8a8c-133">**Beskrivning** : Ange en valfri beskrivning för märket.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="a8a8c-134">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a8a8c-135">Gör något av följande på sidan **tilldela post lådor** :</span><span class="sxs-lookup"><span data-stu-id="a8a8c-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="a8a8c-136">Klicka på **Lägg till post lådor**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="a8a8c-137">Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:</span><span class="sxs-lookup"><span data-stu-id="a8a8c-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="a8a8c-138">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="a8a8c-139">Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="a8a8c-140">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="a8a8c-141">Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="a8a8c-142">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="a8a8c-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="a8a8c-143">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="a8a8c-144">Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="a8a8c-145">Kontrol lera att text filen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="a8a8c-146">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a8a8c-147">På sidan **Granska tagg** granskar du dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="a8a8c-148">Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="a8a8c-149">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="a8a8c-150">Använda säkerhets Center för att Visa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="a8a8c-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="a8a8c-151">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a8a8c-152">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="a8a8c-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="a8a8c-153">I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="a8a8c-154">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="a8a8c-155">Använda säkerhets Center för att ändra användar flaggor</span><span class="sxs-lookup"><span data-stu-id="a8a8c-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="a8a8c-156">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a8a8c-157">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="a8a8c-158">Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="a8a8c-159">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="a8a8c-160">Använda säkerhets Center för att ta bort taggar</span><span class="sxs-lookup"><span data-stu-id="a8a8c-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="a8a8c-161">**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="a8a8c-162">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a8a8c-163">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga** och väljer sedan **Ja, ta bort** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
