---
title: Användartaggar i Office 365 ATP
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
description: Administratörer kan lära sig att identifiera specifika grupper med användare med användar koder i Office 365 ATP-abonnemang 2. Filtrering av märkningar är tillgängligt för aviseringar, rapporter och undersökningar i Office 365 ATP för att snabbt identifiera taggade användare.
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399391"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="4cb49-104">Användartaggar i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4cb49-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="4cb49-105">User-taggar är identifierare för specifika grupper med användare i [Office 365 Avancerat skydd (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="4cb49-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="4cb49-106">Det finns två typer av användar flaggor:</span><span class="sxs-lookup"><span data-stu-id="4cb49-106">There are two types of user tags:</span></span>

- <span data-ttu-id="4cb49-107">**System märkning**: [prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är för närvarande den enda typen av system märkning.</span><span class="sxs-lookup"><span data-stu-id="4cb49-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="4cb49-108">**Anpassade taggar**: du skapar dem själv.</span><span class="sxs-lookup"><span data-stu-id="4cb49-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="4cb49-109">Om din organisation har Office 365 ATP-abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen för prioritets konton.</span><span class="sxs-lookup"><span data-stu-id="4cb49-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="4cb49-110">När du har använt system koder eller anpassade taggar för användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="4cb49-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="4cb49-111">Aviseringar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="4cb49-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="4cb49-112">Threat Explorer och real tids identifiering</span><span class="sxs-lookup"><span data-stu-id="4cb49-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="4cb49-113">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="4cb49-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="4cb49-114">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="4cb49-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="4cb49-115">I den här artikeln förklaras hur du konfigurerar användar koder i fältet säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4cb49-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="4cb49-116">Det finns inga cmdletar i säkerhets & kompatibilitetstillstånd för att hantera användar koder.</span><span class="sxs-lookup"><span data-stu-id="4cb49-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4cb49-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4cb49-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4cb49-118">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4cb49-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4cb49-119">Öppna för att gå direkt till sidan **User Tags** <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="4cb49-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="4cb49-120">För att skapa, ändra eller ta bort **anpassade användar flaggor**måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4cb49-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="4cb49-121">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4cb49-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4cb49-122">Du måste vara [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)för att kunna konfigurera prioritets konton (systemtaggar).</span><span class="sxs-lookup"><span data-stu-id="4cb49-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="4cb49-123">Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cb49-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4cb49-124">Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="4cb49-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="4cb49-125">Använda säkerhets Center för att skapa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4cb49-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="4cb49-126">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4cb49-127">På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="4cb49-128">Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4cb49-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="4cb49-129">**Name**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="4cb49-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="4cb49-130">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="4cb49-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="4cb49-131">**Beskrivning**: Ange en valfri beskrivning för märket.</span><span class="sxs-lookup"><span data-stu-id="4cb49-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="4cb49-132">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4cb49-133">Gör något av följande på sidan **tilldela post lådor** :</span><span class="sxs-lookup"><span data-stu-id="4cb49-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="4cb49-134">Klicka på **Lägg till post lådor**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="4cb49-135">Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:</span><span class="sxs-lookup"><span data-stu-id="4cb49-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="4cb49-136">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="4cb49-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="4cb49-137">Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="4cb49-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="4cb49-138">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="4cb49-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="4cb49-139">Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.</span><span class="sxs-lookup"><span data-stu-id="4cb49-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="4cb49-140">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="4cb49-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="4cb49-141">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="4cb49-142">Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="4cb49-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="4cb49-143">Kontrol lera att text filen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="4cb49-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="4cb49-144">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4cb49-145">På sidan **Granska tagg** granskar du dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="4cb49-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="4cb49-146">Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="4cb49-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="4cb49-147">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="4cb49-148">Använda säkerhets Center för att Visa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4cb49-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="4cb49-149">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4cb49-150">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="4cb49-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="4cb49-151">I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.</span><span class="sxs-lookup"><span data-stu-id="4cb49-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="4cb49-152">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4cb49-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="4cb49-153">Använda säkerhets Center för att ändra användar flaggor</span><span class="sxs-lookup"><span data-stu-id="4cb49-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="4cb49-154">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4cb49-155">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="4cb49-156">Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="4cb49-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="4cb49-157">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="4cb49-158">Använda säkerhets Center för att ta bort taggar</span><span class="sxs-lookup"><span data-stu-id="4cb49-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="4cb49-159">**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.</span><span class="sxs-lookup"><span data-stu-id="4cb49-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="4cb49-160">Gå till användar märkning för **Threat Management** i säkerhets Center \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4cb49-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4cb49-161">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga**och väljer sedan **Ja, ta bort** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="4cb49-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
