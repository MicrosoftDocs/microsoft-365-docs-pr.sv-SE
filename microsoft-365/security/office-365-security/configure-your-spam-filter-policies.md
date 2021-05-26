---
title: Konfigurera principer för skräppostfilter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hur de visar, skapar, ändrar och tar bort principer för skräppostskydd i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1241e6ebb838938f82fce5dc08ea93a3038f4ace
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624239"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="ff2ae-103">Konfigurera principer för skräppostskydd i EOP</span><span class="sxs-lookup"><span data-stu-id="ff2ae-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff2ae-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-104">**Applies to**</span></span>
- [<span data-ttu-id="ff2ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff2ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff2ae-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ff2ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ff2ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff2ae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ff2ae-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor skyddas automatiskt inkommande e-postmeddelanden mot skräppost av EOP.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="ff2ae-109">EOP använder principer för skräppostskydd (kallas även för principer för skräppostfilter eller principer för innehållsfilter) som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-109">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="ff2ae-110">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-110">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="ff2ae-111">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-111">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="ff2ae-112">För mer detaljerad kontroll kan du också skapa egna principer för skräppostskydd som gäller för vissa användare, grupper eller domäner i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-112">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ff2ae-113">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-113">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ff2ae-114">Du kan konfigurera principer för skräppostskydd i Säkerhets- och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-114">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="ff2ae-115">De grundläggande delarna av en anti-spam-policy är:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-115">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="ff2ae-116">**Principen för skräppostfilter**: anger åtgärderna för utfall av skräppostfiltrering och aviseringsalternativen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-116">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="ff2ae-117">**Regeln för skräppostfilter**: anger prioritets- och mottagarfilter (vem principen gäller för) för en princip för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-117">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="ff2ae-118">Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för skräppostskydd i Säkerhets- och efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-118">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ff2ae-119">När du skapar en anti-spam policy skapar du faktiskt en spamfilterregel och tillhörande spamfilterpolicy samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-119">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ff2ae-p103">När du ändrar en anti-spam-policy ändrar inställningar relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagarfilter spamregeln. Alla andra inställningar ändrar den associerade principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-p103">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule. All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="ff2ae-122">När du tar bort en anti-spam-policy tas spam-filterregeln och tillhörande spamfilterpolicy bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-122">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="ff2ae-123">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-123">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ff2ae-124">Mer information finns i [Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera avsnittet om antispampolicy](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) senare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-124">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this article.</span></span>

<span data-ttu-id="ff2ae-125">Alla organisationer har en inbyggd princip för skräppostskydd som heter Standard och som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-125">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="ff2ae-126">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon regel om skräppostfilter (mottagarfilter) associerade med policyn.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-126">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ff2ae-127">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-127">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ff2ae-128">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-128">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ff2ae-129">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-129">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ff2ae-130">Om du vill öka effektiviteten för filtrering av skräppost kan du skapa anpassade principer för skräppostskydd med striktare inställningar som tillämpas för vissa användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-130">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ff2ae-131">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ff2ae-131">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ff2ae-132">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-132">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ff2ae-133">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-133">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="ff2ae-134">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ff2ae-135">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-135">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ff2ae-136">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-136">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ff2ae-137">Om du vill lägga till, ändra och ta bort principer för skräppostskydd måste du vara medlem i rollgruppen **Organisationshantering** eller **Säkerhetsadministratör**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-137">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ff2ae-138">För skrivskyddad behörighet till principer för skräppostskydd måste du vara medlem i rollgruppen **Global läsare** eller **Säkerhetsläsare**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-138">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ff2ae-139">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-139">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ff2ae-140">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-140">**Notes**:</span></span>

  - <span data-ttu-id="ff2ae-141">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-141">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ff2ae-142">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-142">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ff2ae-143">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-143">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ff2ae-144">De rekommenderade inställningarna för principer för skräppostskydd finns i avsnittet om [Inställningar för EOP-principer för skräppostskydd](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-144">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="ff2ae-145">Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-145">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="ff2ae-146">När du skapar en anpassad princip för skräppostskydd i Säkerhets- och efterlevnadscenter skapar du samtidigt en regel för skräppostfilter och den associerade principen för skräppostfilter med samma namn för båda två.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-146">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ff2ae-147">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-148">På sidan **Inställningar för skräppostskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-148">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="ff2ae-149">I den utfällbara rutan **Ny princip för skräppostfilter** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-149">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ff2ae-150">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-150">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="ff2ae-151">Använd inte följande tecken: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-151">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="ff2ae-152">Om du tidigare har skapat principer för skräppostskydd i administrationscenter för Exchange (EAC) som innehåller dessa tecken bör du byta namn på principen för skräppostskydd i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-152">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="ff2ae-153">Instruktioner finns i avsnittet [Använda PowerShell för att ändra regler för skräppostfilter](#use-powershell-to-modify-spam-filter-rules) längre ner i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-153">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this article.</span></span>

   - <span data-ttu-id="ff2ae-154">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="ff2ae-155">(Valfritt) Utöka avsnittet **Åtgärder för skräppost och massutskick** och verifiera eller konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-155">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="ff2ae-156">**Välj vad som ska göras med skräppost och massutskick**: Välj eller granska åtgärden som ska vidtas för meddelanden baserat på följande utfall av skräppostfiltreringen:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-156">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="ff2ae-157">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-157">**Spam**</span></span>
     - <span data-ttu-id="ff2ae-158">**Skräppost med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-158">**High confidence spam**</span></span>
     - <span data-ttu-id="ff2ae-159">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-159">**Phishing email**</span></span>
     - <span data-ttu-id="ff2ae-160">**Nätfiske via e-post med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-160">**High confidence phishing email**</span></span>
     - <span data-ttu-id="ff2ae-161">**Massutskick**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-161">**Bulk email**</span></span>

     <span data-ttu-id="ff2ae-162">Tillgängliga åtgärder för utfall av skräppostfiltrering beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-162">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="ff2ae-163">En bockmarkering (</span><span class="sxs-lookup"><span data-stu-id="ff2ae-163">A check mark (</span></span> ![Bockmarkering](../../media/checkmark.png)<span data-ttu-id="ff2ae-165">) anger att åtgärden är tillgänglig (alla åtgärder är inte tillgängliga för alla utfall av skräppostfiltrering).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-165">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="ff2ae-166">En asterisk ( <sup>\*</sup> ) efter bockmarkeringen anger standardåtgärden för utfallet av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-166">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     ****

     |<span data-ttu-id="ff2ae-167">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-167">Action</span></span>|<span data-ttu-id="ff2ae-168">Skräppost</span><span class="sxs-lookup"><span data-stu-id="ff2ae-168">Spam</span></span>|<span data-ttu-id="ff2ae-169">Högsta</span><span class="sxs-lookup"><span data-stu-id="ff2ae-169">High</span></span><br><span data-ttu-id="ff2ae-170">konfidens</span><span class="sxs-lookup"><span data-stu-id="ff2ae-170">confidence</span></span><br><span data-ttu-id="ff2ae-171">skräppost</span><span class="sxs-lookup"><span data-stu-id="ff2ae-171">spam</span></span>|<span data-ttu-id="ff2ae-172">Fiske</span><span class="sxs-lookup"><span data-stu-id="ff2ae-172">Phishing</span></span><br><span data-ttu-id="ff2ae-173">e-post</span><span class="sxs-lookup"><span data-stu-id="ff2ae-173">email</span></span>|<span data-ttu-id="ff2ae-174">Högsta</span><span class="sxs-lookup"><span data-stu-id="ff2ae-174">High</span></span><br><span data-ttu-id="ff2ae-175">konfidens</span><span class="sxs-lookup"><span data-stu-id="ff2ae-175">confidence</span></span><br><span data-ttu-id="ff2ae-176">fiske</span><span class="sxs-lookup"><span data-stu-id="ff2ae-176">phishing</span></span><br><span data-ttu-id="ff2ae-177">e-post</span><span class="sxs-lookup"><span data-stu-id="ff2ae-177">email</span></span>|<span data-ttu-id="ff2ae-178">Massutskick</span><span class="sxs-lookup"><span data-stu-id="ff2ae-178">Bulk</span></span><br><span data-ttu-id="ff2ae-179">e-post</span><span class="sxs-lookup"><span data-stu-id="ff2ae-179">email</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="ff2ae-180">**Flytta meddelandet till mappen skräppost**: Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-180">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="ff2ae-181">![Bockmarkering](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-181">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="ff2ae-182">![Bockmarkering](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-182">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|<span data-ttu-id="ff2ae-185">![Bockmarkering](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-185">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="ff2ae-186">**Lägg till X-rubrik**: Lägger till ett X-huvud i meddelandehuvudet och levererar meddelandet till postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-186">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="ff2ae-187">Du anger fältnamnet för X-huvudet (inte värdet) senare i rutan **Lägg till följande X-sidhuvudtext**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-187">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="ff2ae-188">Om utfallet är **Skräppost** eller **Skräppost med hög konfidens** flyttas meddelandet till mappen Skräppost.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-188">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||<span data-ttu-id="ff2ae-192">![Bockmarkering](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-192">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="ff2ae-193">**Lägg till text i ämnesraden**: Lägger till text i början av meddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-193">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="ff2ae-194">Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-194">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="ff2ae-195">Du anger texten senare i rutan **Lägg till den här texten i ämnesraden**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-195">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)|
     |<span data-ttu-id="ff2ae-200">**Omdirigera meddelandet till e-postadressen**: Skickar meddelandet till andra mottagare istället för till avsedda mottagare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-200">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="ff2ae-201">Du anger mottagarna senare i rutan **Omdirigera till den här e-postadressen**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-201">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
     |<span data-ttu-id="ff2ae-207">**Ta bort meddelande**: Hela meddelandet tas tyst bort, inklusive alla bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-207">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)|
     |<span data-ttu-id="ff2ae-212">**Sätt meddelandet i karantän**: Skickar meddelandet till karantän istället för till avsedda mottagare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-212">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="ff2ae-213">Du anger senare hur länge meddelandet ska hållas kvar i karantänen i rutan **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-213">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|<span data-ttu-id="ff2ae-216">![Bockmarkering](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ff2ae-216">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
     |<span data-ttu-id="ff2ae-219">**Ingen åtgärd**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-219">**No action**</span></span>|||||![Bockmarkering](../../media/checkmark.png)|
     |

     > <span data-ttu-id="ff2ae-221"><sup>1</sup> I Exchange Online flyttas meddelandet till mappen Skräppost om regeln för skräppost har aktiverats för postlådan (den är aktiverad som standard).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-221"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="ff2ae-222">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-222">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="ff2ae-223">I hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-223">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="ff2ae-224">Mer information finns i [Konfigurera EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-224">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>
     >
     > <span data-ttu-id="ff2ae-225"><sup>2</sup> Du kan använda det här värdet som ett villkor i e-postflödesregler för att filtrera eller dirigera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-225"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="ff2ae-226">**Välj tröskelvärde**: Anger klagomålsnivån på massutskick (BCL) för ett meddelande som utlöser angiven åtgärd för utfallet **Massutskick** av skräppostfiltreringen (större än det angivna värdet, inte större än eller lika med).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-226">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="ff2ae-227">Ett högre värde innebär att meddelandet är mindre önskvärt (mer troligt att det liknar skräppost).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-227">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="ff2ae-228">Standardvärdet är 7.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-228">The default value is 7.</span></span> <span data-ttu-id="ff2ae-229">Mer information finns i [Massklagomålsnivå (BCL) i EOP](bulk-complaint-level-values.md) och [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-229">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="ff2ae-230">Som standard är PowerShell-inställningen _MarkAsSpamBulkMail_ `On` (På) i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-230">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="ff2ae-231">Den här inställningen påverkar dramatiskt resultatet av filtreringsutfallet **Massutskick**:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-231">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="ff2ae-232">**_MarkAsSpamBulkMail_ är på**: En BCL som är större än tröskelvärdet konverteras till en SCL 6 som motsvarar filtreringsutfallet **Skräppost**, och åtgärden för filtreringsutfallet **Massutskick** vidtas för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-232">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="ff2ae-233">**_MarkAsSpamBulkMail_ är av**: Meddelandet stämplas med BCL:n, men _ingen åtgärd_ vidtas för filtreringsutfallet **Massutskick**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-233">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="ff2ae-234">I praktiken innebär det att BCL-tröskelvärdet och åtgärden för filtreringsutfallet **Massutskick** är irrelevanta.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-234">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="ff2ae-235">**Karantän**: Anger hur lång tid meddelandet ska behållas i karantän om du har valt **Sätt meddelandet i karantän** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-235">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="ff2ae-236">När tidsperioden går ut tas meddelandet bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-236">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="ff2ae-237">Standardvärdet är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-237">The default value is 30 days.</span></span> <span data-ttu-id="ff2ae-238">Giltiga värden är 1 till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-238">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="ff2ae-239">Mer information om karantän finns i artiklarna om följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-239">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="ff2ae-240">Meddelanden i karantän i EOP</span><span class="sxs-lookup"><span data-stu-id="ff2ae-240">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="ff2ae-241">Hantera meddelanden och filer i karantän som administratör i EOP</span><span class="sxs-lookup"><span data-stu-id="ff2ae-241">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="ff2ae-242">Hitta och släppa meddelanden i karantän som användare i EOP</span><span class="sxs-lookup"><span data-stu-id="ff2ae-242">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="ff2ae-243">**Lägg till följande X-sidhuvudtext**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till X-rubrik** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-243">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="ff2ae-244">Värdet du anger är *namnet* på huvudfältet som läggs till i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-244">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="ff2ae-245">Huvudfältets *värde* är alltid `This message appears to be spam` (Det här meddelandet verkar vara skräppost).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-245">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="ff2ae-246">Den maximala längden är 255 tecken och värdet får inte innehålla blanksteg eller kolon (:).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-246">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="ff2ae-247">Om du till exempel anger värdet `X-This-is-my-custom-header` är X-huvudet som läggs till i meddelandet `X-This-is-my-custom-header: This message appears to be spam.`</span><span class="sxs-lookup"><span data-stu-id="ff2ae-247">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="ff2ae-248">Om du anger ett värde som innehåller blanksteg eller kolon (:) ignoreras det värde du anger och standardtexten för X-huvudet läggs till i meddelandet (`X-This-Is-Spam: This message appears to be spam.`).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-248">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="ff2ae-249">**Lägg till den här texten i ämnesraden**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till text i ämnesraden** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-249">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="ff2ae-250">Skriv texten som ska läggas till i början av meddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-250">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="ff2ae-251">**Omdirigera till den här e-postadressen**: Den här rutan krävs och är endast tillgänglig om du har valt **Omdirigera meddelandet till e-postadressen** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-251">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="ff2ae-252">Ange den e-postadress dit du vill leverera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-252">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="ff2ae-253">Du kan ange flera värden avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-253">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="ff2ae-254">**Säkerhetstips**: Säkerhetstips är aktiverade som standard, men du kan inaktivera dem genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-254">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="ff2ae-255">Mer information om säkerhetstips finns i [Säkerhetstips i e-postmeddelanden](safety-tips-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-255">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="ff2ae-256">Inställningar för **Automatisk rensning**: Automatisk rensning identifierar och vidtar åtgärder för meddelanden som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-256">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="ff2ae-257">Mer information om automatisk rensning finns i [Automatisk rensning – skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-257">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="ff2ae-258">**Automatisk rensning av skräppost**: Automatisk rensning är aktiverat som standard för upptäckt av skräppost, men du kan inaktivera det genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-258">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="ff2ae-259">**Automatisk rensning av nätfiske**: Automatisk rensning är aktiverat som standard för upptäckt av nätfiske, men du kan inaktivera det genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-259">**Phish ZAP**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="ff2ae-260">(Valfritt) Utöka avsnittet **Tillståndslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som får hoppa över skräppostfiltrering:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-260">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   >
   > - <span data-ttu-id="ff2ae-261">Tänk efter noga innan du lägger till domäner här.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-261">Think very carefully before you add domains here.</span></span> <span data-ttu-id="ff2ae-262">Mer information finns i [Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-262">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > - <span data-ttu-id="ff2ae-263">Lägg aldrig till godkända domäner (domäner som du äger) eller vanliga domäner (till exempel microsoft.com eller office.com) i listan över tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-263">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="ff2ae-264">Då skulle angripare kunna skicka e-post till din organisation som kringgår skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-264">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="ff2ae-265">**Tillåt avsändare**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-265">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="ff2ae-266">I den utfällbara rutan **Lista över tillåtna avsändare** som visas gör du följande:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-266">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="ff2ae-267">a.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-267">a.</span></span> <span data-ttu-id="ff2ae-268">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-268">Enter the sender's email address.</span></span> <span data-ttu-id="ff2ae-269">Du kan ange flera e-postadresser avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-269">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="ff2ae-270">b.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-270">b.</span></span> <span data-ttu-id="ff2ae-271">Klicka på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-271">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ff2ae-273">och lägg till avsändarna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-273">to add the senders.</span></span>

      <span data-ttu-id="ff2ae-274">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-274">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="ff2ae-275">Avsändarna du har lagt till visas i avsnittet **Tillåten avsändare** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-275">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="ff2ae-276">Om du vill ta bort en avsändare klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-276">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="ff2ae-277">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-277">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ff2ae-278">**Tillåt domän**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-278">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="ff2ae-279">I den utfällbara rutan **Lista över tillåtna domäner** som visas gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-279">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="ff2ae-p130">a. Ange domänen. Du kan ange flera domäner avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-p130">a. Enter the domain. You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="ff2ae-283">b.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-283">b.</span></span> <span data-ttu-id="ff2ae-284">Klicka på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-284">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ff2ae-286">och lägg till domänerna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-286">to add the domains.</span></span>

      <span data-ttu-id="ff2ae-287">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-287">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="ff2ae-288">Domänerna du har lagt till visas i avsnittet **Tillåten domän** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-288">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="ff2ae-289">Om du vill ta bort en domän klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-289">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="ff2ae-290">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-290">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="ff2ae-291">(Valfritt) Utöka avsnittet **Blockeringslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som alltid ska markeras som skräppost med hög konfidens:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-291">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="ff2ae-292">Manuell blockering av domäner är inte farligt, men det kan öka mängden administrativt arbete.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-292">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="ff2ae-293">Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-293">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="ff2ae-294">**Blockera avsändare**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-294">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="ff2ae-295">I den utfällbara rutan **Lista över blockerade avsändare** som visas gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-295">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="ff2ae-296">a.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-296">a.</span></span> <span data-ttu-id="ff2ae-297">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-297">Enter the sender's email address.</span></span> <span data-ttu-id="ff2ae-298">Du kan ange flera e-postadresser avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-298">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="ff2ae-299">Jokertecken (\*) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-299">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="ff2ae-300">b.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-300">b.</span></span> <span data-ttu-id="ff2ae-301">Klicka på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-301">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ff2ae-303">och lägg till avsändarna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-303">to add the senders.</span></span>

      <span data-ttu-id="ff2ae-304">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-304">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="ff2ae-305">Avsändarna du har lagt till visas i avsnittet **Blockerad avsändare** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-305">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="ff2ae-306">Om du vill ta bort en avsändare klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-306">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="ff2ae-307">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-307">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ff2ae-308">**Blockera domän**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-308">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="ff2ae-309">I den utfällbara rutan **Lista över blockerade domäner** som visas gör du följande:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-309">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="ff2ae-310">a.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-310">a.</span></span> <span data-ttu-id="ff2ae-311">Ange domänen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-311">Enter the domain.</span></span> <span data-ttu-id="ff2ae-312">Du kan ange flera domäner avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-312">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="ff2ae-313">Jokertecken (\*) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-313">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="ff2ae-314">b.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-314">b.</span></span> <span data-ttu-id="ff2ae-315">Klicka på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-315">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ff2ae-317">och lägg till domänerna.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-317">to add the domains.</span></span>

      <span data-ttu-id="ff2ae-318">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-318">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="ff2ae-319">Domänerna du har lagt till visas i listan **Blockerad domän** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-319">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="ff2ae-320">Om du vill ta bort en domän klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-320">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="ff2ae-321">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-321">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="ff2ae-322">(Valfritt) Utöka avsnittet **Internationell skräppost** om du vill konfigurera e-postspråk eller källänder som blockeras av skräppostfiltrering:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-322">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="ff2ae-323">**Filtrera e-postmeddelanden skrivna på följande språk**: Den här inställningen är inaktiverad som standard (**Status: AV**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-323">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="ff2ae-324">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-324">Click **Edit**.</span></span> <span data-ttu-id="ff2ae-325">I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-325">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="ff2ae-326">**Filtrera e-postmeddelanden skrivna på följande språk**: Markera kryssrutan om du vill aktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-326">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="ff2ae-327">Avmarkera kryssrutan om du vill inaktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-327">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="ff2ae-328">Klicka i rutan och börja skriva *namnet* på språket.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-328">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="ff2ae-329">En filtrerad lista över språk som stöds visas, tillsammans med motsvarande ISO 639-2-språkkod.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-329">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="ff2ae-330">När du hittar det språk du letar efter väljer du det.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-330">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="ff2ae-331">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-331">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="ff2ae-332">Listan över språk som du har valt visas i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-332">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="ff2ae-333">Om du vill ta bort ett språk klickar du</span><span class="sxs-lookup"><span data-stu-id="ff2ae-333">To delete a language, click</span></span> ![Knappen Ta bort](../../media/scc-remove-icon.png)<span data-ttu-id="ff2ae-335">.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-335">.</span></span>

     <span data-ttu-id="ff2ae-336">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-336">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ff2ae-337">**Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Den här inställningen är inaktiverad som standard (**Status: AV**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-337">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="ff2ae-338">Om du vill aktivera den klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-338">To enable it, click **Edit**.</span></span> <span data-ttu-id="ff2ae-339">I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-339">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="ff2ae-340">**Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Markera kryssrutan om du vill aktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-340">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="ff2ae-341">Avmarkera kryssrutan om du vill inaktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-341">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="ff2ae-342">Klicka i rutan och börja skriva *namnet* på landet eller regionen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-342">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="ff2ae-343">En filtrerad lista över länder och regioner som stöds visas, tillsammans med motsvarande ISO 3166-1-landskod med två bokstäver.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-343">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="ff2ae-344">När du hittar landet eller regionen du söker efter väljer du det.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-344">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="ff2ae-345">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-345">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="ff2ae-346">Listan över länder som du har valt visas i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-346">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="ff2ae-347">Om du vill ta bort ett land eller en region klickar du på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-347">To delete a country or region, click</span></span> ![Knappen Ta bort](../../media/scc-remove-icon.png)<span data-ttu-id="ff2ae-349">.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-349">.</span></span>

     <span data-ttu-id="ff2ae-350">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-350">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="ff2ae-351">Det valfria avsnittet **Egenskaper för skräppost** innehåller inställningar för avancerat skräppostfilter (ASF) som är inaktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-351">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="ff2ae-352">ASF-inställningar håller på att fasas ut och deras funktioner läggs till i andra delar av filtreringsstacken.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-352">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="ff2ae-353">Vi rekommenderar att du låter alla dessa ASF-inställningar vara inaktiverade i dina principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-353">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="ff2ae-354">Mer information om inställningarna finns i artikeln om [inställningar för avancerat skräppostfilter (ASF) i EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-354">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="ff2ae-355">(Obligatoriskt) Utöka avsnittet **Tillämpas på** och ange vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-355">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="ff2ae-356">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-356">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ff2ae-357">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-357">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ff2ae-358">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-358">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="ff2ae-359">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-359">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="ff2ae-360">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-360">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="ff2ae-361">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-361">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="ff2ae-362">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-362">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="ff2ae-363">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-363">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="ff2ae-364">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-364">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="ff2ae-365">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-365">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ff2ae-366">Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-366">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="ff2ae-367">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-367">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="ff2ae-368">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-368">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ff2ae-369">Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-369">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="ff2ae-370">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-370">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="ff2ae-371">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-371">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="ff2ae-372">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-372">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="ff2ae-373">Använda Säkerhets- och efterlevnadscenter för att visa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-373">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="ff2ae-374">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-374">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-375">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-375">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="ff2ae-376">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-376">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="ff2ae-377">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-377">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="ff2ae-378">De viktiga principinställningarna visas i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-378">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="ff2ae-379">Visa mer information genom att klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-379">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="ff2ae-380">Använda Säkerhets- och efterlevnadscenter för att ändra principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-380">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="ff2ae-381">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-381">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-382">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-382">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="ff2ae-383">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-383">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="ff2ae-384">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-384">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="ff2ae-385">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-385">Click **Edit policy**.</span></span>

<span data-ttu-id="ff2ae-386">För anpassade principer för skräppostskydd är de tillgängliga inställningarna i den utfällbara rutan som visas identiska med de som beskrivs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-386">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="ff2ae-387">För standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** är avsnittet **Tillämpas på** inte tillgängligt (principen tillämpas på alla), och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-387">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="ff2ae-388">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-388">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="ff2ae-389">Aktivera eller inaktivera principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-389">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="ff2ae-390">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-390">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-391">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-391">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="ff2ae-392">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-392">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="ff2ae-393">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-393">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="ff2ae-395">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-395">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)

<span data-ttu-id="ff2ae-397">Du kan inte inaktivera standardprincipen för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-397">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="ff2ae-398">Ange prioritet för anpassade principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-398">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="ff2ae-399">Som standard tilldelas principer för skräppostskydd en prioritet baserat på den ordning de har skapats i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-399">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="ff2ae-400">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-400">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ff2ae-401">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-401">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ff2ae-402">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-402">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ff2ae-403">Anpassade principer för skräppostskydd visas i den ordning som de bearbetas (den första principen har värdet 0 för **Prioritet**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-403">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ff2ae-404">Standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** har prioritetsvärdet **Lägsta**, och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-404">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ff2ae-405">**Obs**! I Säkerhets- och efterlevnadscenter kan du bara ändra prioriteten för principen för skräppostskydd efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-405">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="ff2ae-406">I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-406">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ff2ae-407">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-407">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="ff2ae-408">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-408">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-409">På sidan **Inställningar för skräppostskydd** hittar du principerna där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-409">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="ff2ae-410">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-410">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="ff2ae-411">Den anpassade principen för skräppostskydd med den högsta prioriteten har värdet ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-411">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="ff2ae-412">Den anpassade principen för skräppostskydd med den lägsta prioriteten har värdet ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **3**.)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-412">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="ff2ae-413">Om du har tre eller fler anpassade principer för skräppostskydd har principerna mellan den högsta och lägsta prioriteten värdena ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-413">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="ff2ae-414">Klicka på</span><span class="sxs-lookup"><span data-stu-id="ff2ae-414">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="ff2ae-416">eller</span><span class="sxs-lookup"><span data-stu-id="ff2ae-416">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="ff2ae-418">om du vill flytta den anpassade principen för skräppostskydd uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-418">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="ff2ae-419">Konfigurera skräppostaviseringar för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="ff2ae-419">Configure end-user spam notifications</span></span>

<span data-ttu-id="ff2ae-420">När ett utfall av skräppostfiltreringen sätter ett meddelande i karantän kan du konfigurera skräppostaviseringar för slutanvändare så att mottagare får veta vad som har hänt med meddelanden som skickats till dem.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-420">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="ff2ae-421">Mer information om aviseringarna finns i artikeln om [skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-421">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="ff2ae-422">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-422">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-423">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-423">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="ff2ae-424">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-424">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="ff2ae-425">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-425">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="ff2ae-426">I den utökade principinformationen som visas klickar du på **Konfigurera skräppostaviseringar för slutanvändare**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-426">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="ff2ae-427">Konfigurera följande inställningar i dialogrutan **\<Policy Name\>** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-427">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ff2ae-428">**Aktivera aviseringar om skräppost för slutanvändare**: Markera kryssrutan om du vill aktivera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-428">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="ff2ae-429">Avmarkera kryssrutan om du vill inaktivera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-429">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="ff2ae-430">**Skicka skräppostaviseringar till slutanvändare varje (dagar)**: Välj hur ofta aviseringar ska skickas.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-430">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="ff2ae-431">Standardvärdet är 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-431">The default value is 3 days.</span></span> <span data-ttu-id="ff2ae-432">Du kan ange 1 till 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-432">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="ff2ae-433">Det finns tre cykler för skräppostaviseringar för användare inom en 24-timmarsperiod som startar vid följande tidpunkter: 01:00 UTC, 08:00 UTC och 16:00 UTC.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-433">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ff2ae-434">Om vi missade en avisering under en tidigare cykel skickas aviseringen under nästföljande cykeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-434">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="ff2ae-435">Det här kan få det att verka som om flera aviseringar skickas ut samma dag.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-435">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="ff2ae-436">**Aviseringsspråk**: Klicka på listrutan och välj ett tillgängligt språk i listan.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-436">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="ff2ae-437">Standardvärdet är **Standard**, vilket innebär engelska.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-437">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="ff2ae-438">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-438">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="ff2ae-439">Använda Säkerhets- och efterlevnadscenter för att ta bort principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-439">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="ff2ae-440">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-440">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ff2ae-441">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas den anpassade principen du vill ta bort (kolumnen **Typ** har värdet **Anpassad princip för skräppostskydd**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-441">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="ff2ae-442">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-442">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="ff2ae-443">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-443">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ff2ae-444">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-444">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="ff2ae-445">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-445">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="ff2ae-446">Som tidigare beskrivits består en anti-spam policy av en policy för spamfilter och en regel för spamfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-446">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="ff2ae-447">I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan principer för skräppostfilter och regler för skräppostfilter uppenbar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-447">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="ff2ae-448">Du hanterar principer för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterPolicy**, och du hanterar regler för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterRule**.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-448">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="ff2ae-449">I PowerShell skapar du först principen för skräppostfilter. Sedan skapar du regeln för skräppostfilter som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-449">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ff2ae-450">I PowerShell ändrar du inställningarna för principen för skräppostfilter och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-450">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="ff2ae-451">När du tar bort en princip för skräppostfilter från PowerShell tas motsvarande regel för skräppostfilter inte automatiskt bort och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-451">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="ff2ae-452">Följande inställningar för principer för skräppostskydd är endast tillgängliga i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-452">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="ff2ae-453">Parametern _MarkAsSpamBulkMail_ som är `On` (På) som standard.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-453">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="ff2ae-454">Effekterna av den här inställningen beskrevs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-454">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this article.</span></span>

- <span data-ttu-id="ff2ae-455">Följande inställningar för skräppostaviseringar för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-455">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="ff2ae-456">Parametern _DownloadLink_ som visar eller döljer länken till rapporteringsverktyget för skräppost för Outlook.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-456">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="ff2ae-457">Parametern _EndUserSpamNotificationCustomSubject_ som du kan använda för att anpassa ämnesraden i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-457">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="ff2ae-458">Använda PowerShell för att skapa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="ff2ae-458">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="ff2ae-459">Du skapar en princip för skräppostskydd i PowerShell i två steg:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-459">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ff2ae-460">Skapa principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-460">Create the spam filter policy.</span></span>
2. <span data-ttu-id="ff2ae-461">Skapa regeln för skräppostfilter som anger den princip för skräppostfilter som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-461">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="ff2ae-462">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-462">**Notes**:</span></span>

- <span data-ttu-id="ff2ae-463">Du kan skapa en ny regel för skräppostfilter och tilldela en befintlig princip för skräppostfilter som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-463">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="ff2ae-464">En regel för skräppostfilter kan inte associeras med fler än en princip för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-464">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="ff2ae-465">Du kan konfigurera följande inställningar i nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Säkerhets- och efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-465">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ff2ae-466">Skapa den nya principen som inaktiverad (_Enabled_ `$false` i cmdleten **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-466">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="ff2ae-467">Ange prioriteten för principen när du skapar den (_Priority_ _\<Number\>_) i cmdleten **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-467">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="ff2ae-468">En ny princip för skräppostfilter som du skapar i PowerShell är inte synlig i Säkerhets- och efterlevnadscenter förrän du tilldelar principen till en regel för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-468">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="ff2ae-469">Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-469">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="ff2ae-470">Om du vill skapa en princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-470">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ff2ae-471">I det här exemplet skapas en princip för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-471">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="ff2ae-472">Karantänmeddelanden när utfallet av skräppostfiltreringen är skräppost eller skräppost med hög konfidens.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-472">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="ff2ae-473">BCL 6 utlöser åtgärden för filtreringsutfallet Massutskick.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-473">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="ff2ae-474">**New-HostedContentFilterPolicy** och **Set-HostedContentFilterPolicy** innehåller en äldre _ZapEnabled_-parameter, samt nyare _PhishZapEnabled_- och _SpamZapEnabled_-parametrar.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-474">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="ff2ae-475">Parametern _ZapEnabled_ blev inaktuell i februari 2020.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-475">The _ZapEnabled_ parameter was deprecated in February 2020.</span></span> <span data-ttu-id="ff2ae-476">Parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ brukade ärva sina värden från parametern _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-476">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="ff2ae-477">Men om du använder parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ i ett kommando eller om du använder inställningarna för **Automatisk rensning av skräppost** eller **Automatisk rensning av nätfiske** i principen för skräppostskydd i Säkerhets- och efterlevnadscentret ignoreras värdet för parametern _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-477">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="ff2ae-478">Använd med andra ord inte parametern _ZapEnabled_. Använd istället parametrarna _PhishZapEnabled_ och _SpamZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-478">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="ff2ae-479">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-479">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="ff2ae-480">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-480">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="ff2ae-481">Om du vill skapa en regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-481">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ff2ae-482">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-482">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="ff2ae-483">Principen för skräppostfilter med namnet Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-483">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="ff2ae-484">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-484">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="ff2ae-485">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-485">For detailed syntax and parameter information, see [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="ff2ae-486">Använda PowerShell för att visa principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-486">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="ff2ae-487">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-487">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="ff2ae-488">Om du vill returnera detaljerad information om en specifik princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-488">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ff2ae-489">I det här exemplet returneras alla egenskapsvärden för principen för skräppostfilter med namnet Executives.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-489">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="ff2ae-490">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-490">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="ff2ae-491">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-491">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="ff2ae-492">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-492">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="ff2ae-493">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-493">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="ff2ae-494">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-494">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="ff2ae-495">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-495">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ff2ae-496">I det här exemplet returneras alla egenskapsvärden för regeln för skräppostfilter princip med namnet Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-496">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ff2ae-497">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-497">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="ff2ae-498">Använda PowerShell för att ändra principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-498">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="ff2ae-499">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en princip för skräppostfilter i PowerShell som när du skapar principen enligt beskrivningen i avsnittet [Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter](#step-1-use-powershell-to-create-a-spam-filter-policy) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-499">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this article.</span></span>

- <span data-ttu-id="ff2ae-500">Switchparametern _MakeDefault_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid prioriteten **Lägsta** och du kan inte ta bort den) är endast tillgänglig när du ändrar en princip för skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-500">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="ff2ae-501">Du kan inte byta namn på en princip för skräppostfilter (cmdleten **Set-HostedContentFilterPolicy** har ingen _Name_-parameter).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-501">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ff2ae-502">När du byter namn på en princip för skräppostskydd i Säkerhets- och efterlevnadscenter byter du bara namn på _regeln_ för skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-502">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="ff2ae-503">Om du vill ändra en princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-503">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ff2ae-504">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-504">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="ff2ae-505">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-505">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="ff2ae-506">Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en regel som är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-506">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ff2ae-507">Om du vill aktivera eller inaktivera befintliga regler för skräppostfilter läser du mer i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-507">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="ff2ae-508">Annars är inga ytterligare inställningar tillgängliga när du ändrar en regel för skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-508">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="ff2ae-509">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i avsnittet [Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter](#step-2-use-powershell-to-create-a-spam-filter-rule) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-509">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="ff2ae-510">Om du vill ändra en regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-510">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ff2ae-511">I det här exemplet ändras namnet på den befintliga regeln för skräppostfilter som heter `{Fabrikam Spam Filter}` som kan orsaka problem i Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-511">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="ff2ae-512">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-512">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="ff2ae-513">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-513">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="ff2ae-514">Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen för skräppostfilter (regeln för skräppostfilter och den tilldelade principen för skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-514">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="ff2ae-515">Du kan inte aktivera eller inaktivera standardprincipen för skräppostskydd (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-515">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="ff2ae-516">Om du vill aktivera eller inaktivera en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-516">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="ff2ae-517">I det här exemplet inaktiveras regeln för skräppostfilter som heter Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-517">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ff2ae-518">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-518">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ff2ae-519">Detaljerad information om syntax och parametrar finns i [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) och [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-519">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="ff2ae-520">Använda PowerShell för att ange prioriteten för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-520">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="ff2ae-521">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-521">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ff2ae-522">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-522">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ff2ae-523">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-523">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ff2ae-524">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-524">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ff2ae-525">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-525">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ff2ae-526">Om du vill ange prioriteten för en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-526">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ff2ae-527">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-527">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ff2ae-528">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="ff2ae-528">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ff2ae-529">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-529">**Notes**:</span></span>

- <span data-ttu-id="ff2ae-530">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-HostedContentFilterRule** istället.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-530">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="ff2ae-531">Standardprincipen för skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid prioritetsvärdet **Lägsta** som inte går att ändra.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-531">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="ff2ae-532">Använda PowerShell för att ta bort principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-532">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="ff2ae-533">När du använder PowerShell för att ta bort en princip för skräppostfilter tas motsvarande regel för skräppostfilter inte bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-533">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="ff2ae-534">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-534">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ff2ae-535">I det här exemplet tas principen för skräppostfilter med namnet Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-535">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ff2ae-536">Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-536">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="ff2ae-537">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="ff2ae-537">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="ff2ae-538">När du använder PowerShell för att ta bort en regel för skräppostfilter tas motsvarande princip för skräppostfilter inte bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-538">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="ff2ae-539">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-539">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="ff2ae-540">I det här exemplet tas regeln för skräppostfilter med namnet Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-540">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ff2ae-541">Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="ff2ae-541">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ff2ae-542">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="ff2ae-542">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="ff2ae-543">Skicka ett GTUBE-meddelande för att testa inställningarna för skräppostprinciperna</span><span class="sxs-lookup"><span data-stu-id="ff2ae-543">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="ff2ae-p177">De här stegen fungerar bara om e-postorganisationen som du skickar GTUBE-meddelandet från inte söker igenom efter utgående skräppost. Om organisationen söker igenom går det inte att skicka testmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-p177">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam. If it does, the test message can't be sent.</span></span>

<span data-ttu-id="ff2ae-546">GTUBE (Generic Test for Unsolicited Bulk Email – Generiskt test för oönskade massutskick) är en textsträng som du lägger till i ett test meddelande för att verifiera organisationens inställningar för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-546">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="ff2ae-547">Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-547">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="ff2ae-548">Lägg till följande GTUBE text i ett e-postmeddelande på en enskild rad, utan blanksteg eller radbrytningar:</span><span class="sxs-lookup"><span data-stu-id="ff2ae-548">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="ff2ae-549">Listor över blockerade eller tillåtna</span><span class="sxs-lookup"><span data-stu-id="ff2ae-549">Allow/Block Lists</span></span>

<span data-ttu-id="ff2ae-550">Det kommer att finnas tillfällen när våra filter missar meddelandet eller då det tar tid för våra system att komma ifatt det.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-550">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="ff2ae-551">I de här fallen har principen för skräppostskydd en lista över Tillåtna och en lista över Blockerade tillgängliga för att åsidosätta den aktuella bedömningen.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-551">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="ff2ae-552">Det här alternativet ska bara användas sparsamt eftersom listor kan bli svåra att hantera, och bara tillfälligt eftersom vår filtreringsstack borde göra vad den ska göra.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-552">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="ff2ae-553">Det kan finnas situationer där din organisation kanske inte håller med om den bedömning tjänsten tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-553">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="ff2ae-554">I det här fallet kanske du vill behålla listan över tillåtna eller blockerade permanent.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-554">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="ff2ae-555">Men om du kommer att lägga till en domän i listan över tillåtna för en längre tid bör du be avsändaren att kontrollera att avsändarens domän har autentiserats och ange den som DMARC-avvisa (reject) om den inte är det.</span><span class="sxs-lookup"><span data-stu-id="ff2ae-555">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>