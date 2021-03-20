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
description: Administratörer kan lära sig att identifiera särskilda grupper av användare med användartaggar i Microsoft Defender för Office 365 abonnemang 2. Taggfiltrering är tillgängligt i aviseringar, rapporter och undersökningar i Microsoft Defender för Office 365 för att snabbt identifiera de taggade användarna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9bb6a233f21268df860974549ecffbfd7154045
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916412"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="96249-104">Användartaggar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="96249-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="96249-105">Funktionen för användartaggar är inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="96249-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="96249-106">Mer information om lanseringsschemat finns i Översikt över [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="96249-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="96249-107">Användartaggar är identifierare för specifika grupper av användare [i Microsoft Defender för Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="96249-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="96249-108">Det finns två typer av användartaggar:</span><span class="sxs-lookup"><span data-stu-id="96249-108">There are two types of user tags:</span></span>

- <span data-ttu-id="96249-109">**Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.</span><span class="sxs-lookup"><span data-stu-id="96249-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="96249-110">**Anpassade taggar:** Du skapar de här användartaggarna själv.</span><span class="sxs-lookup"><span data-stu-id="96249-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="96249-111">Om din organisation har Defender för Office 365 abonnemang 2 (ingår i prenumerationen eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioritetskonton.</span><span class="sxs-lookup"><span data-stu-id="96249-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="96249-112">När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="96249-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="96249-113">Varningar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="96249-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="96249-114">Hotutforskaren och identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="96249-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="96249-115">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="96249-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="96249-116">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="96249-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="96249-117">För prioritetskonton kan du använda rapporten [E-postproblem för prioritetskonton](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="96249-117">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="96249-118">I den här artikeln förklaras hur du konfigurerar användartaggar & Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="96249-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="96249-119">Det finns inga cmdlets i Säkerhets- & för att hantera användartaggar.</span><span class="sxs-lookup"><span data-stu-id="96249-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="96249-120">Information om hur användartaggar är en del av strategin för att skydda användarkonton med hög effekt finns i Säkerhetsrekommendationer för [prioriterade konton i Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="96249-120">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96249-121">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="96249-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96249-122">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="96249-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="96249-123">Gå direkt till sidan **Användartaggar** genom att öppna <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="96249-123">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="96249-124">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="96249-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="96249-125">Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="96249-125">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="96249-126">Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, **Säkerhetsadministratör** eller **Säkerhetsoperator**</span><span class="sxs-lookup"><span data-stu-id="96249-126">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="96249-127">För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="96249-127">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="96249-128">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="96249-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="96249-129">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="96249-129">**Notes**:</span></span>

  - <span data-ttu-id="96249-130">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96249-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="96249-131">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="96249-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="96249-132">Hantering av användartaggar styrs av **rollerna Taggläsare** **och Tagghanteraren.**</span><span class="sxs-lookup"><span data-stu-id="96249-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="96249-133">Du kan också hantera och övervaka konton med prioritet i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96249-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="96249-134">Anvisningar finns i Hantera [och övervaka prioritetskonton.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="96249-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="96249-135">Använda Säkerhets- & efterlevnadscenter för att skapa användartaggar</span><span class="sxs-lookup"><span data-stu-id="96249-135">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="96249-136">Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="96249-136">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="96249-137">På sidan **Användartaggar** som öppnas klickar du på **Skapa tagg.**</span><span class="sxs-lookup"><span data-stu-id="96249-137">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="96249-138">Guiden **Skapa tagg** öppnas i en ny farten. På sidan **Definiera tagg** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="96249-138">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="96249-139">**Namn**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="96249-139">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="96249-140">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="96249-140">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="96249-141">**Beskrivning**: Ange en valfri beskrivning för taggen.</span><span class="sxs-lookup"><span data-stu-id="96249-141">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="96249-142">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="96249-142">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="96249-143">Gör **något av** följande på sidan Tilldela användare:</span><span class="sxs-lookup"><span data-stu-id="96249-143">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="96249-144">Klicka på **Lägg till användare.**</span><span class="sxs-lookup"><span data-stu-id="96249-144">Click **Add users**.</span></span> <span data-ttu-id="96249-145">I den flygblad som visas gör du något av följande för att lägga till enskilda användare eller grupper:</span><span class="sxs-lookup"><span data-stu-id="96249-145">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="96249-146">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="96249-146">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="96249-147">Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="96249-147">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="96249-148">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="96249-148">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="96249-149">Om du vill ta bort enskilda poster från rutan klickar du **på Ikonen** Ta bort för användaren eller gruppen ![ i ](../../media/scc-remove-icon.png) rutan.</span><span class="sxs-lookup"><span data-stu-id="96249-149">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="96249-150">Om du vill ta bort befintliga poster från listan under rutan klickar du på **Ta** ![ bort-ikonen ](../../media/scc-remove-icon.png) för posten.</span><span class="sxs-lookup"><span data-stu-id="96249-150">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="96249-151">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="96249-151">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="96249-152">Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="96249-152">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="96249-153">Kontrollera att textfilen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="96249-153">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="96249-154">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="96249-154">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="96249-155">Granska **inställningarna på** taggsidan Granska.</span><span class="sxs-lookup"><span data-stu-id="96249-155">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="96249-156">Du kan klicka **på Redigera** i det specifika avsnittet för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="96249-156">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="96249-157">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="96249-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="96249-158">Använda Säkerhets- & efterlevnadscenter för att visa användartaggar</span><span class="sxs-lookup"><span data-stu-id="96249-158">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="96249-159">Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="96249-159">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="96249-160">På sidan **Användartaggar** som öppnas väljer du den användartagg som du vill visa (klicka inte i kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="96249-160">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="96249-161">Granska inställningarna i den skrivskyddade informationen som visas.</span><span class="sxs-lookup"><span data-stu-id="96249-161">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="96249-162">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="96249-162">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="96249-163">Använda Säkerhets- & efterlevnadscenter för att ändra användartaggar</span><span class="sxs-lookup"><span data-stu-id="96249-163">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="96249-164">Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="96249-164">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="96249-165">På sidan **Användartaggar** som öppnas väljer du den användartagg som du vill visa och klickar sedan på **Redigera tagg**.</span><span class="sxs-lookup"><span data-stu-id="96249-165">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="96249-166">Principguiden öppnas i en **utfälls fönster för** redigeringstagg. Klicka **på** Nästa för att granska och ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="96249-166">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="96249-167">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="96249-167">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="96249-168">Använda Säkerhets- och & för att ta bort användartaggar</span><span class="sxs-lookup"><span data-stu-id="96249-168">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="96249-169">**Obs!** Du kan inte ta bort den inbyggda **prioritetskontotaggen.**</span><span class="sxs-lookup"><span data-stu-id="96249-169">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="96249-170">Gå till Användartaggar för & skydd mot **hothantering** \> **i Säkerhets- och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="96249-170">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="96249-171">På sidan **Användartaggar** som öppnas väljer du den användartagg du vill ta bort, klickar på Ta bort tagg och väljer sedan  **Ja,** ta bort i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="96249-171">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>