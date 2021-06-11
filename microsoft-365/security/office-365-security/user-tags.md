---
title: Användartaggar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879174"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="28dff-104">Användartaggar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="28dff-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="28dff-105">Funktionen för användartaggar är inte tillgänglig för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="28dff-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="28dff-106">Mer information om lanseringsschemat finns i översikten [över Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="28dff-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="28dff-107">Användartaggar är identifierare för specifika användargrupper i [Microsoft Defender för Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="28dff-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="28dff-108">Det finns två typer av användartaggar:</span><span class="sxs-lookup"><span data-stu-id="28dff-108">There are two types of user tags:</span></span>

- <span data-ttu-id="28dff-109">**Systemtaggar:** För närvarande [är Prioritet-konton](../../admin/setup/priority-accounts.md) den enda typen av systemtagg.</span><span class="sxs-lookup"><span data-stu-id="28dff-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="28dff-110">**Anpassade taggar:** Du skapar de här användartaggarna själv.</span><span class="sxs-lookup"><span data-stu-id="28dff-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="28dff-111">Om din organisation har Defender för Office 365 abonnemang 2 (ingår i din prenumeration eller som ett tillägg) kan du skapa anpassade användartaggar utöver att använda taggen för prioritetskonton.</span><span class="sxs-lookup"><span data-stu-id="28dff-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="28dff-112">För närvarande kan du bara använda användartaggar för postlådeanvändare.</span><span class="sxs-lookup"><span data-stu-id="28dff-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="28dff-113">När du har tillämpat systemtaggar eller anpassade taggar för användare kan du använda de taggarna som filter i aviseringar, rapporter och undersökningar:</span><span class="sxs-lookup"><span data-stu-id="28dff-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="28dff-114">Varningar</span><span class="sxs-lookup"><span data-stu-id="28dff-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="28dff-115">Hotutforskaren och identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="28dff-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="28dff-116">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="28dff-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="28dff-117">Kampanjvyer</span><span class="sxs-lookup"><span data-stu-id="28dff-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="28dff-118">För prioritetskonton kan du använda rapporten [E-postproblem](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) för prioritetskonton Exchange administrationscenter (EAC).</span><span class="sxs-lookup"><span data-stu-id="28dff-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="28dff-119">I den här artikeln förklarar vi hur du konfigurerar användartaggar Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="28dff-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="28dff-120">Det finns inga cmdlets i Microsoft 365 Defender-portalen för att hantera användartaggar.</span><span class="sxs-lookup"><span data-stu-id="28dff-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="28dff-121">Information om hur användartaggar ingår i strategin för att skydda användarkonton med hög effekt finns i Säkerhetsrekommendationer för [prioriterade konton i Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="28dff-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="28dff-122">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="28dff-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="28dff-123">Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="28dff-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="28dff-124">Gå direkt till sidan **Användartaggar** genom att öppna <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="28dff-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="28dff-125">Du måste ha tilldelats behörigheter i Microsoft 365 Defender-portalen innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="28dff-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="28dff-126">Om du vill skapa, ändra och ta bort användartaggar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="28dff-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="28dff-127">Om du vill lägga till och ta bort medlemmar från befintliga användartaggar måste du vara medlem i rollgrupperna Organisationshantering, **Säkerhetsadministratör** eller **Säkerhetsoperator**</span><span class="sxs-lookup"><span data-stu-id="28dff-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="28dff-128">För skrivskyddade åtkomst till användartaggar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="28dff-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="28dff-129">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="28dff-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="28dff-130">Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28dff-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="28dff-131">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="28dff-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="28dff-132">Hantering av användartaggar styrs av **rollerna Taggläsare** **och Tagghanteraren.**</span><span class="sxs-lookup"><span data-stu-id="28dff-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="28dff-133">Du kan också hantera och övervaka konton med prioritet Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="28dff-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="28dff-134">Anvisningar finns i Hantera [och övervaka prioritetskonton.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="28dff-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="28dff-135">Information om hur du skyddar _behöriga konton_ (administratörskonton) finns i det [här avsnittet.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="28dff-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="28dff-136">Använda Defender Microsoft 365 portalen för att skapa användartaggar</span><span class="sxs-lookup"><span data-stu-id="28dff-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="28dff-137">Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**</span><span class="sxs-lookup"><span data-stu-id="28dff-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="28dff-138">Klicka på **Skapa taggikon** skapa ![ tagg på sidan ](../../media/m365-cc-sc-create-icon.png) **Användartaggar.**</span><span class="sxs-lookup"><span data-stu-id="28dff-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="28dff-139">Guiden **Skapa tagg** öppnas i en ny utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="28dff-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="28dff-140">På sidan **Definiera tagg** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="28dff-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="28dff-141">**Namn**: Ange ett unikt, beskrivande namn för taggen.</span><span class="sxs-lookup"><span data-stu-id="28dff-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="28dff-142">Det här är det värde som du kommer att se och använda.</span><span class="sxs-lookup"><span data-stu-id="28dff-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="28dff-143">Observera att du inte kan byta namn på en tagg när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="28dff-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="28dff-144">**Beskrivning**: Ange en valfri beskrivning för taggen.</span><span class="sxs-lookup"><span data-stu-id="28dff-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="28dff-145">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="28dff-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="28dff-146">Gör **något av följande** på sidan Tilldela medlemmar:</span><span class="sxs-lookup"><span data-stu-id="28dff-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="28dff-147">Klicka på ![ ikonen Lägg till medlemmar Lägg till ](../../media/m365-cc-sc-create-icon.png) **medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="28dff-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="28dff-148">I den flygblad som visas gör du något av följande för att lägga till enskilda användare eller grupper:</span><span class="sxs-lookup"><span data-stu-id="28dff-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="28dff-149">Klicka i rutan och bläddra igenom listan för att välja en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="28dff-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="28dff-150">Klicka i rutan och börja skriva för att filtrera listan och välj en användare eller grupp.</span><span class="sxs-lookup"><span data-stu-id="28dff-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="28dff-151">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="28dff-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="28dff-152">Om du vill ta bort enskilda poster klickar du på</span><span class="sxs-lookup"><span data-stu-id="28dff-152">To remove individual entries, click</span></span> ![Ta bort post-ikon](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="28dff-154">bredvid posten i rutan.</span><span class="sxs-lookup"><span data-stu-id="28dff-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="28dff-155">Om du vill ta bort alla poster klickar du på ta bort postikonen i markerade ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn-användare och nn-grupper** under rutan.</span><span class="sxs-lookup"><span data-stu-id="28dff-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="28dff-156">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="28dff-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="28dff-157">På sidan **Tilldela medlemmar kan** du också ta bort poster genom att klicka på Ta ![ ](../../media/m365-cc-sc-delete-icon.png) bort-ikonen bredvid posten.</span><span class="sxs-lookup"><span data-stu-id="28dff-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="28dff-158">Klicka **på Importera** för att markera en textfil som innehåller e-postadresserna till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="28dff-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="28dff-159">Kontrollera att textfilen innehåller en post per rad.</span><span class="sxs-lookup"><span data-stu-id="28dff-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="28dff-160">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="28dff-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="28dff-161">Granska **inställningarna på** taggsidan Granska som visas.</span><span class="sxs-lookup"><span data-stu-id="28dff-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="28dff-162">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="28dff-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="28dff-163">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="28dff-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="28dff-164">När du är klar klickar du på **Skicka** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="28dff-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="28dff-165">Använda Defender Microsoft 365 portalen för att visa användartaggar</span><span class="sxs-lookup"><span data-stu-id="28dff-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="28dff-166">Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**</span><span class="sxs-lookup"><span data-stu-id="28dff-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="28dff-167">På **sidan Användartaggar** visas följande egenskaper i listan med användartaggar:</span><span class="sxs-lookup"><span data-stu-id="28dff-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="28dff-168">**Tagg:** Namnet på användartaggen.</span><span class="sxs-lookup"><span data-stu-id="28dff-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="28dff-169">Observera att detta inkluderar den inbyggda **systemtaggen för priority-kontot.**</span><span class="sxs-lookup"><span data-stu-id="28dff-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="28dff-170">**Applied to**: Antalet medlemmar</span><span class="sxs-lookup"><span data-stu-id="28dff-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="28dff-171">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="28dff-171">**Last modified**</span></span>
   - <span data-ttu-id="28dff-172">**Skapades**</span><span class="sxs-lookup"><span data-stu-id="28dff-172">**Created on**</span></span>

3. <span data-ttu-id="28dff-173">När du väljer en användartagg genom att klicka på namnet visas informationen i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="28dff-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="28dff-174">Använda Defender Microsoft 365 portalen för att ändra användartaggar</span><span class="sxs-lookup"><span data-stu-id="28dff-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="28dff-175">Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**</span><span class="sxs-lookup"><span data-stu-id="28dff-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="28dff-176">På sidan **Användartaggar** väljer du användartaggen i listan och klickar sedan på Redigera ![ ](../../media/m365-cc-sc-edit-icon.png) **taggikonEn redigera-tagg.**</span><span class="sxs-lookup"><span data-stu-id="28dff-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="28dff-177">I den utfällklara informationen som visas är samma guide och inställningar tillgängliga enligt beskrivningen i [avsnittet använda Microsoft 365 Defender-portalen](#use-the-microsoft-365-defender-portal-to-create-user-tags) för att skapa användartaggar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="28dff-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="28dff-178">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="28dff-178">**Notes**:</span></span>

   - <span data-ttu-id="28dff-179">Sidan **Definiera tagg** är inte tillgänglig för den inbyggda systemtaggen för **Priority-kontot,** så du kan inte byta namn på taggen eller ändra beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="28dff-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="28dff-180">Du kan inte byta namn på en anpassad tagg, men du kan ändra beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="28dff-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="28dff-181">Använda Defender Microsoft 365 portalen för att ta bort användartaggar</span><span class="sxs-lookup"><span data-stu-id="28dff-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="28dff-182">Du kan inte ta bort systemtaggen för det **inbyggda prioritetskontot.**</span><span class="sxs-lookup"><span data-stu-id="28dff-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="28dff-183">Gå till Microsoft 365-post och e-Inställningar och **&** \> **i** \> **Defender-portalen.**</span><span class="sxs-lookup"><span data-stu-id="28dff-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="28dff-184">På sidan **Användartaggar** väljer du användartaggen i listan och klickar sedan på Ta bort ![ taggikon Ta ](../../media/m365-cc-sc-delete-icon.png) **bort tagg.**</span><span class="sxs-lookup"><span data-stu-id="28dff-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="28dff-185">Läs varningen i bekräftelsedialogrutan som visas och klicka sedan på **Ja, ta bort**.</span><span class="sxs-lookup"><span data-stu-id="28dff-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
