---
title: Användar flaggor
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
description: Administratörer kan lära sig att identifiera specifika grupper med användare med User-Taggar i Oiffce 365 ATP 2. Filtrering av märkningar är tillgängligt för aviseringar, rapporter och undersökningar i Office 365 ATP för att snabbt identifiera taggade användare.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210036"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="730fe-104">Användar koder i Microsoft säkerhets Center</span><span class="sxs-lookup"><span data-stu-id="730fe-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="730fe-105">User-taggar är identifierare för specifika grupper med användare i [Office 365 Avancerat skydd (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="730fe-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="730fe-106">[Prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) är en typ av användar märkning.</span><span class="sxs-lookup"><span data-stu-id="730fe-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="730fe-107">Om din organisation har Office 365 ATP-abonnemang 2 (ingår i ditt abonnemang eller som ett tillägg) kan du skapa anpassade användar flaggor förutom att använda taggen för prioritets konton.</span><span class="sxs-lookup"><span data-stu-id="730fe-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="730fe-108">När du har använt taggar för specifika användare kan du använda taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="730fe-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="730fe-109">Aviseringar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="730fe-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="730fe-110">Threat Explorer och real tids identifiering</span><span class="sxs-lookup"><span data-stu-id="730fe-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="730fe-111">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="730fe-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="730fe-112">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="730fe-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="730fe-113">I den här artikeln förklaras hur du konfigurerar användar koder i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="730fe-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="730fe-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="730fe-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="730fe-115">Du öppnar säkerhets Center på <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="730fe-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="730fe-116">Öppna för att gå direkt till sidan **User Tags** <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="730fe-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="730fe-117">Om du vill skapa, ändra eller ta bort användar flaggor måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="730fe-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="730fe-118">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="730fe-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="730fe-119">Du kan också hantera och övervaka prioriterade konton i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="730fe-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="730fe-120">Anvisningar finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="730fe-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="730fe-121">Använda säkerhets Center för att skapa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="730fe-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="730fe-122">I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.</span><span class="sxs-lookup"><span data-stu-id="730fe-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="730fe-123">På sidan med **användar Taggar** som öppnas klickar du på **skapa tagg**.</span><span class="sxs-lookup"><span data-stu-id="730fe-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="730fe-124">Guiden **skapa tagg** öppnas i ett nytt flyg ut. På sidan **definiera etikett** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="730fe-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="730fe-125">**Name**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="730fe-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="730fe-126">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="730fe-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="730fe-127">**Beskrivning**: Ange en valfri beskrivning för märket.</span><span class="sxs-lookup"><span data-stu-id="730fe-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="730fe-128">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="730fe-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="730fe-129">Gör något av följande på sidan **tilldela post lådor** :</span><span class="sxs-lookup"><span data-stu-id="730fe-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="730fe-130">Klicka på **Lägg till post lådor**.</span><span class="sxs-lookup"><span data-stu-id="730fe-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="730fe-131">Gör något av följande för att lägga till enskilda användare eller grupper i rutan Lägg på som visas:</span><span class="sxs-lookup"><span data-stu-id="730fe-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="730fe-132">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="730fe-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="730fe-133">Klicka i rutan och börja skriva för att filtrera listan och välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="730fe-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="730fe-134">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="730fe-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="730fe-135">Om du vill ta bort enskilda poster från rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) för användaren eller gruppen i rutan.</span><span class="sxs-lookup"><span data-stu-id="730fe-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="730fe-136">Om du vill ta bort befintliga poster från listan under rutan klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="730fe-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="730fe-137">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="730fe-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="730fe-138">Klicka på **Importera** för att välja en textfil som innehåller e-postadresserna för användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="730fe-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="730fe-139">Kontrol lera att text filen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="730fe-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="730fe-140">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="730fe-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="730fe-141">På sidan **Granska tagg** granskar du dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="730fe-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="730fe-142">Du kan klicka på **Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="730fe-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="730fe-143">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="730fe-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="730fe-144">Använda säkerhets Center för att Visa användar flaggor</span><span class="sxs-lookup"><span data-stu-id="730fe-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="730fe-145">I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.</span><span class="sxs-lookup"><span data-stu-id="730fe-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="730fe-146">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa (Klicka inte på kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="730fe-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="730fe-147">I den skrivskyddade informationen, flyger ut som visas kontrollerar du inställningarna.</span><span class="sxs-lookup"><span data-stu-id="730fe-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="730fe-148">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="730fe-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="730fe-149">Använda säkerhets Center för att ändra användar flaggor</span><span class="sxs-lookup"><span data-stu-id="730fe-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="730fe-150">I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.</span><span class="sxs-lookup"><span data-stu-id="730fe-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="730fe-151">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="730fe-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="730fe-152">Princip guiden öppnas i en **Edit-tagg** . Klicka på **Nästa** för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="730fe-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="730fe-153">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="730fe-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="730fe-154">Använda säkerhets Center för att ta bort taggar</span><span class="sxs-lookup"><span data-stu-id="730fe-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="730fe-155">**Obs!** du kan inte ta bort den inbyggda **prioritets konto** typen.</span><span class="sxs-lookup"><span data-stu-id="730fe-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="730fe-156">I säkerhets Center går du till **Inställningar** \> **e-&** \> **användar märkning**för samarbete.</span><span class="sxs-lookup"><span data-stu-id="730fe-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="730fe-157">På sidan med **användar Taggar** som öppnas väljer du den användar tagg som du vill ta bort, klickar på **ta bort flagga**och väljer sedan **Ja, ta bort** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="730fe-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
