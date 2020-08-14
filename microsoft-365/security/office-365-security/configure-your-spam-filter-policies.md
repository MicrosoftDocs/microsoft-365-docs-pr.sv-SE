---
title: Konfigurera principer för skräppostfilter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hur de visar, skapar, ändrar och tar bort principer för skräppostskydd i Exchange Online Protection (EOP).
ms.openlocfilehash: fea1ae4a43ee3002c49bd6511a55a3d490723fc2
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656821"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="f0075-103">Konfigurera principer för skräppostskydd i EOP</span><span class="sxs-lookup"><span data-stu-id="f0075-103">Configure anti-spam policies in EOP</span></span>

<span data-ttu-id="f0075-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor skyddas automatiskt inkommande e-postmeddelanden mot skräppost av EOP.</span><span class="sxs-lookup"><span data-stu-id="f0075-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="f0075-105">EOP använder principer för skräppostskydd (kallas även för principer för skräppostfilter eller principer för innehållsfilter) som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="f0075-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="f0075-106">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="f0075-107">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f0075-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="f0075-108">För mer detaljerad kontroll kan du också skapa egna principer för skräppostskydd som gäller för vissa användare, grupper eller domäner i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f0075-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f0075-109">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="f0075-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f0075-110">Du kan konfigurera principer för skräppostskydd i Säkerhets- och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="f0075-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="f0075-111">Principer för skräppostskydd i Säkerhets- och efterlevnadscenter jämfört med Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0075-111">Anti-spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="f0075-112">De grundläggande elementen i en princip för skräppostskydd i EOP är:</span><span class="sxs-lookup"><span data-stu-id="f0075-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="f0075-113">**Principen för skräppostfilter**: anger åtgärderna för utfall av skräppostfiltrering och aviseringsalternativen.</span><span class="sxs-lookup"><span data-stu-id="f0075-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="f0075-114">**Regeln för skräppostfilter**: anger prioritets- och mottagarfilter (vem principen gäller för) för en princip för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="f0075-115">Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för skräppostskydd i Säkerhets- och efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="f0075-115">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f0075-116">När du skapar en princip för skräppostskydd i Säkerhets- och efterlevnadscenter skapar du i själva verket en regel för skräppostfilter och samtidigt den associerade principen för skräppostfilter med samma namn för båda två.</span><span class="sxs-lookup"><span data-stu-id="f0075-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="f0075-117">När du ändrar en princip för skräppostskydd i Säkerhets- och efterlevnadscenter ändrar inställningar för namn, prioritet, aktiverat eller inaktiverat och mottagarfilter regeln för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="f0075-118">Alla andra inställningar ändrar den associerade principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="f0075-119">När du tar bort en princip för skräppostskydd från Säkerhets- och efterlevnadscenter tas regeln för skräppostfilter och den associerade principen för skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="f0075-120">I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan principer för skräppostfilter och regler för skräppostfilter uppenbar.</span><span class="sxs-lookup"><span data-stu-id="f0075-120">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="f0075-121">Du hanterar principer för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterPolicy**, och du hanterar regler för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterRule**.</span><span class="sxs-lookup"><span data-stu-id="f0075-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="f0075-122">I PowerShell skapar du först principen för skräppostfilter. Sedan skapar du regeln för skräppostfilter som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f0075-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="f0075-123">I PowerShell ändrar du inställningarna för principen för skräppostfilter och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="f0075-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="f0075-124">När du tar bort en princip för skräppostfilter från PowerShell tas motsvarande regel för skräppostfilter inte automatiskt bort och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="f0075-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="f0075-125">Standardprincip för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-125">Default anti-spam policy</span></span>

<span data-ttu-id="f0075-126">Alla organisationer har en inbyggd princip för skräppostskydd som heter Standard och som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="f0075-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="f0075-127">Principen för skräppostfilter som heter Standard tillämpas för alla mottagare i organisationen, även om det inte finns någon regel för skräppostfilter (mottagarfilter) som är associerade med principen.</span><span class="sxs-lookup"><span data-stu-id="f0075-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="f0075-128">Principen med namnet Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="f0075-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f0075-129">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="f0075-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="f0075-130">Principen som heter Standard är standardprincipen (egenskapen **IsDefault** har värdet `True`), och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="f0075-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f0075-131">Om du vill öka effektiviteten för filtrering av skräppost kan du skapa anpassade principer för skräppostskydd med striktare inställningar som tillämpas för vissa användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="f0075-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0075-132">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f0075-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0075-133">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f0075-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f0075-134">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="f0075-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="f0075-135">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f0075-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f0075-136">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f0075-136">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f0075-137">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="f0075-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f0075-138">Om du vill lägga till, ändra och ta bort skydd mot skräppost måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="f0075-138">To add, modify, and delete anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f0075-139">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f0075-140">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f0075-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f0075-141">För skrivskyddad behörighet till principer för skräppostskydd måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="f0075-141">For read-only access to anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f0075-142">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f0075-143">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f0075-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f0075-144">De rekommenderade inställningarna för principer för program mot skadlig kod finns i avsnittet om [EOP-principer för skräppostskydd](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f0075-144">For our recommended settings for anti-malware policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="f0075-145">Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-145">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="f0075-146">När du skapar en anpassad princip för skräppostskydd i Säkerhets- och efterlevnadscenter skapar du samtidigt en regel för skräppostfilter och den associerade principen för skräppostfilter med samma namn för båda två.</span><span class="sxs-lookup"><span data-stu-id="f0075-146">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f0075-147">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-148">På sidan **Inställningar för skräppostskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="f0075-148">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="f0075-149">I den utfällbara rutan **Ny princip för skräppostfilter** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-149">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f0075-150">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="f0075-150">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="f0075-151">Använd inte följande tecken: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span><span class="sxs-lookup"><span data-stu-id="f0075-151">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="f0075-152">Om du tidigare har skapat principer för skräppostskydd i administrationscenter för Exchange (EAC) som innehåller dessa tecken bör du byta namn på principen för skräppostskydd i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0075-152">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="f0075-153">Instruktioner finns i avsnittet [Använda PowerShell för att ändra regler för skräppostfilter](#use-powershell-to-modify-spam-filter-rules) längre ner i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-153">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="f0075-154">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="f0075-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="f0075-155">(Valfritt) Utöka avsnittet **Åtgärder för skräppost och massutskick** och verifiera eller konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-155">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="f0075-156">**Välj vad som ska göras med skräppost och massutskick**: Välj eller granska åtgärden som ska vidtas för meddelanden baserat på följande utfall av skräppostfiltreringen:</span><span class="sxs-lookup"><span data-stu-id="f0075-156">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="f0075-157">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="f0075-157">**Spam**</span></span>
     - <span data-ttu-id="f0075-158">**Skräppost med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="f0075-158">**High confidence spam**</span></span>
     - <span data-ttu-id="f0075-159">**Nätfiske-e-post**</span><span class="sxs-lookup"><span data-stu-id="f0075-159">**Phishing email**</span></span>
     - <span data-ttu-id="f0075-160">**Nätfiske via e-post med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="f0075-160">**High confidence phishing email**</span></span>
     - <span data-ttu-id="f0075-161">**Massutskick**</span><span class="sxs-lookup"><span data-stu-id="f0075-161">**Bulk email**</span></span>

     <span data-ttu-id="f0075-162">Tillgängliga åtgärder för utfall av skräppostfiltrering beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f0075-162">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="f0075-163">En bockmarkering (</span><span class="sxs-lookup"><span data-stu-id="f0075-163">A check mark (</span></span> ![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="f0075-165">) anger att åtgärden är tillgänglig (alla åtgärder är inte tillgängliga för alla utfall av skräppostfiltrering).</span><span class="sxs-lookup"><span data-stu-id="f0075-165">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="f0075-166">En asterisk ( <sup>\*</sup> ) efter bockmarkeringen anger standardåtgärden för utfallet av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-166">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     ****

     |<span>|<span data-ttu-id="f0075-167">Skräppost</span><span class="sxs-lookup"><span data-stu-id="f0075-167">Spam</span></span>|<span data-ttu-id="f0075-168">Högsta</span><span class="sxs-lookup"><span data-stu-id="f0075-168">High</span></span><br/><span data-ttu-id="f0075-169">konfidens</span><span class="sxs-lookup"><span data-stu-id="f0075-169">confidence</span></span><br/><span data-ttu-id="f0075-170">skräppost</span><span class="sxs-lookup"><span data-stu-id="f0075-170">spam</span></span>|<span data-ttu-id="f0075-171">Fiske</span><span class="sxs-lookup"><span data-stu-id="f0075-171">Phishing</span></span><br/><span data-ttu-id="f0075-172">e-post</span><span class="sxs-lookup"><span data-stu-id="f0075-172">email</span></span>|<span data-ttu-id="f0075-173">Högsta</span><span class="sxs-lookup"><span data-stu-id="f0075-173">High</span></span><br/><span data-ttu-id="f0075-174">konfidens</span><span class="sxs-lookup"><span data-stu-id="f0075-174">confidence</span></span><br/><span data-ttu-id="f0075-175">fiske</span><span class="sxs-lookup"><span data-stu-id="f0075-175">phishing</span></span><br/><span data-ttu-id="f0075-176">e-post</span><span class="sxs-lookup"><span data-stu-id="f0075-176">email</span></span>|<span data-ttu-id="f0075-177">Massutskick</span><span class="sxs-lookup"><span data-stu-id="f0075-177">Bulk</span></span><br/><span data-ttu-id="f0075-178">e-post</span><span class="sxs-lookup"><span data-stu-id="f0075-178">email</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="f0075-179">**Flytta meddelandet till mappen skräppost**: Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-179">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="f0075-180">![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-180">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="f0075-181">![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="f0075-184">![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-184">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="f0075-185">**Lägg till X-rubrik**: Lägger till ett X-huvud i meddelandehuvudet och levererar meddelandet till postlådan.</span><span class="sxs-lookup"><span data-stu-id="f0075-185">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="f0075-186">Du anger fältnamnet för X-huvudet (inte värdet) senare i rutan **Lägg till följande X-sidhuvudtext**.</span><span class="sxs-lookup"><span data-stu-id="f0075-186">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="f0075-187">Om utfallet är **Skräppost** eller **Skräppost med hög konfidens** flyttas meddelandet till mappen Skräppost.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-187">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="f0075-191">![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-191">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="f0075-192">**Lägg till text i ämnesraden**: Lägger till text i början av meddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="f0075-192">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="f0075-193">Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-193">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="f0075-194">Du anger texten senare i rutan **Lägg till den här texten i ämnesraden**.</span><span class="sxs-lookup"><span data-stu-id="f0075-194">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="f0075-199">**Omdirigera meddelandet till e-postadressen**: Skickar meddelandet till andra mottagare istället för till avsedda mottagare.</span><span class="sxs-lookup"><span data-stu-id="f0075-199">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="f0075-200">Du anger mottagarna senare i rutan **Omdirigera till den här e-postadressen**.</span><span class="sxs-lookup"><span data-stu-id="f0075-200">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="f0075-206">**Ta bort meddelande**: Hela meddelandet tas tyst bort, inklusive alla bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="f0075-206">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="f0075-211">**Sätt meddelandet i karantän**: Skickar meddelandet till karantän istället för till avsedda mottagare.</span><span class="sxs-lookup"><span data-stu-id="f0075-211">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="f0075-212">Du anger senare hur länge meddelandet ska hållas kvar i karantänen i rutan **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="f0075-212">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="f0075-215">![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0075-215">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="f0075-218">**Ingen åtgärd**</span><span class="sxs-lookup"><span data-stu-id="f0075-218">**No action**</span></span>|||||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <span data-ttu-id="f0075-220"><sup>1</sup> I Exchange Online flyttas meddelandet till mappen Skräppost om regeln för skräppost har aktiverats för postlådan (den är aktiverad som standard).</span><span class="sxs-lookup"><span data-stu-id="f0075-220"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="f0075-221">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-221">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="f0075-222">I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="f0075-222">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="f0075-223">Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-223">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
     >
     > <span data-ttu-id="f0075-224"><sup>2</sup> Du kan använda det här värdet som ett villkor i e-postflödesregler (kallas även transportregler) för att filtrera eller dirigera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f0075-224"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="f0075-225">**Välj tröskelvärde**: Anger klagomålsnivån på massutskick (BCL) för ett meddelande som utlöser angiven åtgärd för utfallet **Massutskick** av skräppostfiltreringen (större än det angivna värdet, inte större än eller lika med).</span><span class="sxs-lookup"><span data-stu-id="f0075-225">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="f0075-226">Ett högre värde innebär att meddelandet är mindre önskvärt (mer troligt att det liknar skräppost).</span><span class="sxs-lookup"><span data-stu-id="f0075-226">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="f0075-227">Standardvärdet är 7.</span><span class="sxs-lookup"><span data-stu-id="f0075-227">The default value is 7.</span></span> <span data-ttu-id="f0075-228">Mer information finns i [Massklagomålsnivå (BCL) i EOP](bulk-complaint-level-values.md) och [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-228">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="f0075-229">Som standard är PowerShell-inställningen _MarkAsSpamBulkMail_ `On` (På) i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f0075-229">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="f0075-230">Den här inställningen påverkar dramatiskt resultatet av filtreringsutfallet **Massutskick**:</span><span class="sxs-lookup"><span data-stu-id="f0075-230">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="f0075-231">**_MarkAsSpamBulkMail_ är på**: En BCL som är större än tröskelvärdet konverteras till en SCL 6 som motsvarar filtreringsutfallet **Skräppost**, och åtgärden för filtreringsutfallet **Massutskick** vidtas för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f0075-231">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="f0075-232">**_MarkAsSpamBulkMail_ är av**: Meddelandet stämplas med BCL:n, men _ingen åtgärd_ vidtas för filtreringsutfallet **Massutskick**.</span><span class="sxs-lookup"><span data-stu-id="f0075-232">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="f0075-233">I praktiken innebär det att BCL-tröskelvärdet och åtgärden för filtreringsutfallet **Massutskick** är irrelevanta.</span><span class="sxs-lookup"><span data-stu-id="f0075-233">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="f0075-234">**Karantän**: Anger hur lång tid meddelandet ska behållas i karantän om du har valt **Sätt meddelandet i karantän** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-234">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="f0075-235">När tidsperioden går ut tas meddelandet bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-235">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="f0075-236">Standardvärdet är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f0075-236">The default value is 30 days.</span></span> <span data-ttu-id="f0075-237">Giltiga värden är 1 till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f0075-237">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="f0075-238">Mer information om karantän finns i artiklarna om följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="f0075-238">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="f0075-239">Meddelanden i karantän i EOP</span><span class="sxs-lookup"><span data-stu-id="f0075-239">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="f0075-240">Hantera meddelanden och filer i karantän som administratör i EOP</span><span class="sxs-lookup"><span data-stu-id="f0075-240">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="f0075-241">Hitta och släppa meddelanden i karantän som användare i EOP</span><span class="sxs-lookup"><span data-stu-id="f0075-241">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="f0075-242">**Lägg till följande X-sidhuvudtext**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till X-rubrik** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-242">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="f0075-243">Värdet du anger är *namnet* på huvudfältet som läggs till i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="f0075-243">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="f0075-244">Huvudfältets *värde* är alltid `This message appears to be spam` (Det här meddelandet verkar vara skräppost).</span><span class="sxs-lookup"><span data-stu-id="f0075-244">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="f0075-245">Den maximala längden är 255 tecken och värdet får inte innehålla blanksteg eller kolon (:).</span><span class="sxs-lookup"><span data-stu-id="f0075-245">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="f0075-246">Om du till exempel anger värdet `X-This-is-my-custom-header` är X-huvudet som läggs till i meddelandet `X-This-is-my-custom-header: This message appears to be spam.`</span><span class="sxs-lookup"><span data-stu-id="f0075-246">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="f0075-247">Om du anger ett värde som innehåller blanksteg eller kolon (:) ignoreras det värde du anger och standardtexten för X-huvudet läggs till i meddelandet (`X-This-Is-Spam: This message appears to be spam.`).</span><span class="sxs-lookup"><span data-stu-id="f0075-247">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="f0075-248">**Lägg till den här texten i ämnesraden**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till text i ämnesraden** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-248">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="f0075-249">Skriv texten som ska läggas till i början av meddelandets ämnesrad.</span><span class="sxs-lookup"><span data-stu-id="f0075-249">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="f0075-250">**Omdirigera till den här e-postadressen**: Den här rutan krävs och är endast tillgänglig om du har valt **Omdirigera meddelandet till e-postadressen** som åtgärd för ett utfall av skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-250">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="f0075-251">Ange den e-postadress dit du vill leverera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f0075-251">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="f0075-252">Du kan ange flera värden avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="f0075-252">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="f0075-253">**Säkerhetstips**: Säkerhetstips är aktiverade som standard, men du kan inaktivera dem genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="f0075-253">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="f0075-254">Mer information om säkerhetstips finns i [Säkerhetstips i e-postmeddelanden](safety-tips-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-254">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="f0075-255">Inställningar för **Automatisk rensning**: Automatisk rensning identifierar och vidtar åtgärder för meddelanden som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f0075-255">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="f0075-256">Mer information om automatisk rensning finns i [Automatisk rensning – skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-256">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="f0075-257">**Automatisk rensning av skräppost**: Automatisk rensning är aktiverat som standard för upptäckt av skräppost, men du kan inaktivera det genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="f0075-257">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="f0075-258">**Automatisk rensning av nätfiske**: Automatisk rensning är aktiverat som standard för upptäckt av nätfiske, men du kan inaktivera det genom att avmarkera kryssrutan **På**.</span><span class="sxs-lookup"><span data-stu-id="f0075-258">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="f0075-259">(Valfritt) Utöka avsnittet **Tillståndslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som får hoppa över skräppostfiltrering:</span><span class="sxs-lookup"><span data-stu-id="f0075-259">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   >
   > - <span data-ttu-id="f0075-260">Tänk efter noga innan du lägger till domäner här.</span><span class="sxs-lookup"><span data-stu-id="f0075-260">Think very carefully before you add domains here.</span></span> <span data-ttu-id="f0075-261">Mer information finns i [Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-261">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > - <span data-ttu-id="f0075-262">Lägg aldrig till godkända domäner (domäner som du äger) eller vanliga domäner (till exempel microsoft.com eller office.com) i listan över tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="f0075-262">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="f0075-263">Då skulle angripare kunna skicka e-post till din organisation som kringgår skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-263">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="f0075-264">**Tillåt avsändare**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-264">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="f0075-265">I den utfällbara rutan **Lista över tillåtna avsändare** som visas gör du följande:</span><span class="sxs-lookup"><span data-stu-id="f0075-265">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="f0075-266">a.</span><span class="sxs-lookup"><span data-stu-id="f0075-266">a.</span></span> <span data-ttu-id="f0075-267">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="f0075-267">Enter the sender's email address.</span></span> <span data-ttu-id="f0075-268">Du kan ange flera e-postadresser avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="f0075-268">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="f0075-269">b.</span><span class="sxs-lookup"><span data-stu-id="f0075-269">b.</span></span> <span data-ttu-id="f0075-270">Klicka på</span><span class="sxs-lookup"><span data-stu-id="f0075-270">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f0075-272">och lägg till avsändarna.</span><span class="sxs-lookup"><span data-stu-id="f0075-272">to add the senders.</span></span>

      <span data-ttu-id="f0075-273">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-273">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="f0075-274">Avsändarna du har lagt till visas i avsnittet **Tillåten avsändare** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-274">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="f0075-275">Om du vill ta bort en avsändare klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="f0075-275">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="f0075-276">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-276">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f0075-277">**Tillåt domän**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-277">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="f0075-278">I den utfällbara rutan **Lista över tillåtna domäner** som visas gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="f0075-278">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="f0075-279">a.</span><span class="sxs-lookup"><span data-stu-id="f0075-279">a.</span></span> <span data-ttu-id="f0075-280">Ange domänen.</span><span class="sxs-lookup"><span data-stu-id="f0075-280">Enter the domain.</span></span> <span data-ttu-id="f0075-281">Du kan ange flera domäner avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="f0075-281">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="f0075-282">b.</span><span class="sxs-lookup"><span data-stu-id="f0075-282">b.</span></span> <span data-ttu-id="f0075-283">Klicka på</span><span class="sxs-lookup"><span data-stu-id="f0075-283">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f0075-285">och lägg till domänerna.</span><span class="sxs-lookup"><span data-stu-id="f0075-285">to add the domains.</span></span>

      <span data-ttu-id="f0075-286">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-286">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="f0075-287">Domänerna du har lagt till visas i avsnittet **Tillåten domän** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-287">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="f0075-288">Om du vill ta bort en domän klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="f0075-288">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="f0075-289">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-289">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="f0075-290">(Valfritt) Utöka avsnittet **Blockeringslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som alltid ska markeras som skräppost med hög konfidens:</span><span class="sxs-lookup"><span data-stu-id="f0075-290">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="f0075-291">Manuell blockering av domäner är inte farligt, men det kan öka mängden administrativt arbete.</span><span class="sxs-lookup"><span data-stu-id="f0075-291">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="f0075-292">Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-292">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="f0075-293">**Blockera avsändare**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-293">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="f0075-294">I den utfällbara rutan **Lista över blockerade avsändare** som visas gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="f0075-294">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="f0075-295">a.</span><span class="sxs-lookup"><span data-stu-id="f0075-295">a.</span></span> <span data-ttu-id="f0075-296">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="f0075-296">Enter the sender's email address.</span></span> <span data-ttu-id="f0075-297">Du kan ange flera e-postadresser avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="f0075-297">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="f0075-298">Jokertecken (\*) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="f0075-298">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="f0075-299">b.</span><span class="sxs-lookup"><span data-stu-id="f0075-299">b.</span></span> <span data-ttu-id="f0075-300">Klicka på</span><span class="sxs-lookup"><span data-stu-id="f0075-300">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f0075-302">och lägg till avsändarna.</span><span class="sxs-lookup"><span data-stu-id="f0075-302">to add the senders.</span></span>

      <span data-ttu-id="f0075-303">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-303">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="f0075-304">Avsändarna du har lagt till visas i avsnittet **Blockerad avsändare** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-304">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="f0075-305">Om du vill ta bort en avsändare klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="f0075-305">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="f0075-306">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-306">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f0075-307">**Blockera domän**: Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-307">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="f0075-308">I den utfällbara rutan **Lista över blockerade domäner** som visas gör du följande:</span><span class="sxs-lookup"><span data-stu-id="f0075-308">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="f0075-309">a.</span><span class="sxs-lookup"><span data-stu-id="f0075-309">a.</span></span> <span data-ttu-id="f0075-310">Ange domänen.</span><span class="sxs-lookup"><span data-stu-id="f0075-310">Enter the domain.</span></span> <span data-ttu-id="f0075-311">Du kan ange flera domäner avgränsade med semikolon (;).</span><span class="sxs-lookup"><span data-stu-id="f0075-311">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="f0075-312">Jokertecken (\*) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="f0075-312">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="f0075-313">b.</span><span class="sxs-lookup"><span data-stu-id="f0075-313">b.</span></span> <span data-ttu-id="f0075-314">Klicka på</span><span class="sxs-lookup"><span data-stu-id="f0075-314">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="f0075-316">och lägg till domänerna.</span><span class="sxs-lookup"><span data-stu-id="f0075-316">to add the domains.</span></span>

      <span data-ttu-id="f0075-317">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-317">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="f0075-318">Domänerna du har lagt till visas i listan **Blockerad domän** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-318">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="f0075-319">Om du vill ta bort en domän klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="f0075-319">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="f0075-320">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-320">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="f0075-321">(Valfritt) Utöka avsnittet **Internationell skräppost** om du vill konfigurera e-postspråk eller källänder som blockeras av skräppostfiltrering:</span><span class="sxs-lookup"><span data-stu-id="f0075-321">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="f0075-322">**Filtrera e-postmeddelanden skrivna på följande språk**: Den här inställningen är inaktiverad som standard (**Status: AV**).</span><span class="sxs-lookup"><span data-stu-id="f0075-322">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="f0075-323">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-323">Click **Edit**.</span></span> <span data-ttu-id="f0075-324">I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-324">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="f0075-325">**Filtrera e-postmeddelanden skrivna på följande språk**: Markera kryssrutan om du vill aktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="f0075-325">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="f0075-326">Avmarkera kryssrutan om du vill inaktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="f0075-326">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="f0075-327">Klicka i rutan och börja skriva *namnet* på språket.</span><span class="sxs-lookup"><span data-stu-id="f0075-327">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="f0075-328">En filtrerad lista över språk som stöds visas, tillsammans med motsvarande ISO 639-2-språkkod.</span><span class="sxs-lookup"><span data-stu-id="f0075-328">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="f0075-329">När du hittar det språk du letar efter väljer du det.</span><span class="sxs-lookup"><span data-stu-id="f0075-329">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="f0075-330">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-330">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="f0075-331">Listan över språk som du har valt visas i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-331">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="f0075-332">Om du vill ta bort ett språk klickar du</span><span class="sxs-lookup"><span data-stu-id="f0075-332">To delete a language, click</span></span> ![Knappen Ta bort](../../media/scc-remove-icon.png)<span data-ttu-id="f0075-334">.</span><span class="sxs-lookup"><span data-stu-id="f0075-334">.</span></span>

     <span data-ttu-id="f0075-335">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-335">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f0075-336">**Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Den här inställningen är inaktiverad som standard (**Status: AV**).</span><span class="sxs-lookup"><span data-stu-id="f0075-336">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="f0075-337">Om du vill aktivera den klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="f0075-337">To enable it, click **Edit**.</span></span> <span data-ttu-id="f0075-338">I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-338">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="f0075-339">**Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Markera kryssrutan om du vill aktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="f0075-339">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="f0075-340">Avmarkera kryssrutan om du vill inaktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="f0075-340">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="f0075-341">Klicka i rutan och börja skriva *namnet* på landet eller regionen.</span><span class="sxs-lookup"><span data-stu-id="f0075-341">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="f0075-342">En filtrerad lista över länder och regioner som stöds visas, tillsammans med motsvarande ISO 3166-1-landskod med två bokstäver.</span><span class="sxs-lookup"><span data-stu-id="f0075-342">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="f0075-343">När du hittar landet eller regionen du söker efter väljer du det.</span><span class="sxs-lookup"><span data-stu-id="f0075-343">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="f0075-344">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="f0075-344">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="f0075-345">Listan över länder som du har valt visas i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="f0075-345">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="f0075-346">Om du vill ta bort ett land eller en region klickar du på</span><span class="sxs-lookup"><span data-stu-id="f0075-346">To delete a country or region, click</span></span> ![Knappen Ta bort](../../media/scc-remove-icon.png)<span data-ttu-id="f0075-348">.</span><span class="sxs-lookup"><span data-stu-id="f0075-348">.</span></span>

     <span data-ttu-id="f0075-349">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-349">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="f0075-350">Det valfria avsnittet **Egenskaper för skräppost** innehåller inställningar för avancerat skräppostfilter (ASF) som är inaktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="f0075-350">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="f0075-351">ASF-inställningar håller på att fasas ut och deras funktioner läggs till i andra delar av filtreringsstacken.</span><span class="sxs-lookup"><span data-stu-id="f0075-351">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="f0075-352">Vi rekommenderar att du låter alla dessa ASF-inställningar vara inaktiverade i dina principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f0075-352">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="f0075-353">Mer information om inställningarna finns i artikeln om [inställningar för avancerat skräppostfilter (ASF) i EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-353">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="f0075-354">(Obligatoriskt) Utöka avsnittet **Tillämpas på** och ange vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="f0075-354">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="f0075-355">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="f0075-355">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f0075-356">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f0075-356">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f0075-357">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f0075-357">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="f0075-358">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="f0075-358">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="f0075-359">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="f0075-359">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="f0075-360">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f0075-360">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="f0075-361">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="f0075-361">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="f0075-362">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f0075-362">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="f0075-363">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f0075-363">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="f0075-364">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="f0075-364">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f0075-365">Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="f0075-365">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="f0075-366">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f0075-366">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="f0075-367">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="f0075-367">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="f0075-368">Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="f0075-368">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="f0075-369">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="f0075-369">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="f0075-370">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="f0075-370">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="f0075-371">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-371">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="f0075-372">Använda Säkerhets- och efterlevnadscenter för att visa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-372">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="f0075-373">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-373">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-374">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="f0075-374">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="f0075-375">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="f0075-375">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="f0075-376">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-376">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="f0075-377">De viktiga principinställningarna visas i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="f0075-377">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="f0075-378">Visa mer information genom att klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="f0075-378">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="f0075-379">Använda Säkerhets- och efterlevnadscenter för att ändra principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-379">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="f0075-380">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-380">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-381">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="f0075-381">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="f0075-382">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="f0075-382">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="f0075-383">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-383">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="f0075-384">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="f0075-384">Click **Edit policy**.</span></span>

<span data-ttu-id="f0075-385">För anpassade principer för skräppostskydd är de tillgängliga inställningarna i den utfällbara rutan som visas identiska med de som beskrivs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="f0075-385">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="f0075-386">För standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** är avsnittet **Tillämpas på** inte tillgängligt (principen tillämpas på alla), och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="f0075-386">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="f0075-387">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="f0075-387">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="f0075-388">Aktivera eller inaktivera principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-388">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="f0075-389">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-389">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-390">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**).</span><span class="sxs-lookup"><span data-stu-id="f0075-390">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="f0075-391">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="f0075-391">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="f0075-392">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="f0075-392">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="f0075-394">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="f0075-394">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="f0075-396">Du kan inte inaktivera standardprincipen för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f0075-396">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="f0075-397">Ange prioritet för anpassade principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-397">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="f0075-398">Som standard tilldelas principer för skräppostskydd en prioritet baserat på den ordning de har skapats i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="f0075-398">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="f0075-399">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="f0075-399">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f0075-400">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="f0075-400">No two policies can have the same priority.</span></span>

<span data-ttu-id="f0075-401">Anpassade principer för skräppostskydd visas i den ordning som de bearbetas (den första principen har värdet 0 för **Prioritet**).</span><span class="sxs-lookup"><span data-stu-id="f0075-401">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f0075-402">Standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** har prioritetsvärdet **Lägsta**, och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="f0075-402">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="f0075-403">**Obs**! I Säkerhets- och efterlevnadscenter kan du bara ändra prioriteten för principen för skräppostskydd efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="f0075-403">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="f0075-404">I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="f0075-404">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f0075-405">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="f0075-405">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="f0075-406">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-406">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-407">På sidan **Inställningar för skräppostskydd** hittar du principerna där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-407">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="f0075-408">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="f0075-408">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="f0075-409">Den anpassade principen för skräppostskydd med den högsta prioriteten har värdet ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="f0075-409">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="f0075-410">Den anpassade principen för skräppostskydd med den lägsta prioriteten har värdet ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **3**.)</span><span class="sxs-lookup"><span data-stu-id="f0075-410">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="f0075-411">Om du har tre eller fler anpassade principer för skräppostskydd har principerna mellan den högsta och lägsta prioriteten värdena ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="f0075-411">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="f0075-412">Klicka på</span><span class="sxs-lookup"><span data-stu-id="f0075-412">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="f0075-414">eller</span><span class="sxs-lookup"><span data-stu-id="f0075-414">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="f0075-416">om du vill flytta den anpassade principen för skräppostskydd uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="f0075-416">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="f0075-417">Konfigurera skräppostaviseringar för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="f0075-417">Configure end-user spam notifications</span></span>

<span data-ttu-id="f0075-418">När ett utfall av skräppostfiltreringen sätter ett meddelande i karantän kan du konfigurera skräppostaviseringar för slutanvändare så att mottagare får veta vad som har hänt med meddelanden som skickats till dem.</span><span class="sxs-lookup"><span data-stu-id="f0075-418">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="f0075-419">Mer information om aviseringarna finns i artikeln om [skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f0075-419">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="f0075-420">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-420">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-421">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="f0075-421">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="f0075-422">Standardprincipen med namnet **Standardprincip för skräppostfilter**.</span><span class="sxs-lookup"><span data-stu-id="f0075-422">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="f0075-423">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-423">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="f0075-424">I den utökade principinformationen som visas klickar du på **Konfigurera skräppostaviseringar för slutanvändare**.</span><span class="sxs-lookup"><span data-stu-id="f0075-424">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="f0075-425">Konfigurera följande inställningar i dialogrutan **\<Policy Name\>** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="f0075-425">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f0075-426">**Aktivera aviseringar om skräppost för slutanvändare**: Markera kryssrutan om du vill aktivera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="f0075-426">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="f0075-427">Avmarkera kryssrutan om du vill inaktivera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="f0075-427">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="f0075-428">**Skicka skräppostaviseringar till slutanvändare varje (dagar)**: Välj hur ofta aviseringar ska skickas.</span><span class="sxs-lookup"><span data-stu-id="f0075-428">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="f0075-429">Standardvärdet är 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="f0075-429">The default value is 3 days.</span></span> <span data-ttu-id="f0075-430">Du kan ange 1 till 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="f0075-430">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="f0075-431">Det finns tre cykler för skräppostaviseringar för användare inom en 24-timmarsperiod som startar vid följande tidpunkter: 01:00 UTC, 08:00 UTC och 16:00 UTC.</span><span class="sxs-lookup"><span data-stu-id="f0075-431">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f0075-432">Om vi missade en avisering under en tidigare cykel skickas aviseringen under nästföljande cykeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-432">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="f0075-433">Det här kan få det att verka som om flera aviseringar skickas ut samma dag.</span><span class="sxs-lookup"><span data-stu-id="f0075-433">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="f0075-434">**Aviseringsspråk**: Klicka på listrutan och välj ett tillgängligt språk i listan.</span><span class="sxs-lookup"><span data-stu-id="f0075-434">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="f0075-435">Standardvärdet är **Standard**, vilket innebär engelska.</span><span class="sxs-lookup"><span data-stu-id="f0075-435">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="f0075-436">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f0075-436">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="f0075-437">Använda Säkerhets- och efterlevnadscenter för att ta bort principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-437">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="f0075-438">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f0075-438">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f0075-439">På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas den anpassade principen du vill ta bort (kolumnen **Typ** har värdet **Anpassad princip för skräppostskydd**).</span><span class="sxs-lookup"><span data-stu-id="f0075-439">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="f0075-440">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="f0075-440">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="f0075-441">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="f0075-441">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f0075-442">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="f0075-442">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="f0075-443">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-443">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="f0075-444">Följande inställningar för principer för skräppostskydd är endast tillgängliga i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0075-444">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="f0075-445">Parametern _MarkAsSpamBulkMail_ som är `On` (På) som standard.</span><span class="sxs-lookup"><span data-stu-id="f0075-445">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="f0075-446">Effekterna av den här inställningen beskrevs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-446">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="f0075-447">Följande inställningar för skräppostaviseringar för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="f0075-447">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="f0075-448">Parametern _DownloadLink_ som visar eller döljer länken till rapporteringsverktyget för skräppost för Outlook.</span><span class="sxs-lookup"><span data-stu-id="f0075-448">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="f0075-449">Parametern _EndUserSpamNotificationCustomSubject_ som du kan använda för att anpassa ämnesraden i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="f0075-449">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="f0075-450">Använda PowerShell för att skapa principer för skräppostskydd</span><span class="sxs-lookup"><span data-stu-id="f0075-450">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="f0075-451">Du skapar en princip för skräppostskydd i PowerShell i två steg:</span><span class="sxs-lookup"><span data-stu-id="f0075-451">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f0075-452">Skapa principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-452">Create the spam filter policy.</span></span>

2. <span data-ttu-id="f0075-453">Skapa regeln för skräppostfilter som anger den princip för skräppostfilter som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="f0075-453">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="f0075-454">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="f0075-454">**Notes**:</span></span>

- <span data-ttu-id="f0075-455">Du kan skapa en ny regel för skräppostfilter och tilldela en befintlig princip för skräppostfilter som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="f0075-455">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="f0075-456">En regel för skräppostfilter kan inte associeras med fler än en princip för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-456">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="f0075-457">Du kan konfigurera följande inställningar i nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Säkerhets- och efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="f0075-457">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f0075-458">Skapa den nya principen som inaktiverad (_Enabled_ `$false` i cmdleten **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="f0075-458">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="f0075-459">Ange prioriteten för principen när du skapar den (_Priority_ _\<Number\>_) i cmdleten **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="f0075-459">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="f0075-460">En ny princip för skräppostfilter som du skapar i PowerShell är inte synlig i Säkerhets- och efterlevnadscenter förrän du tilldelar principen till en regel för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f0075-460">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="f0075-461">Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-461">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="f0075-462">Om du vill skapa en princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-462">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="f0075-463">I det här exemplet skapas en princip för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-463">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="f0075-464">Karantänmeddelanden när utfallet av skräppostfiltreringen är skräppost eller skräppost med hög konfidens.</span><span class="sxs-lookup"><span data-stu-id="f0075-464">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="f0075-465">BCL 6 utlöser åtgärden för filtreringsutfallet Massutskick.</span><span class="sxs-lookup"><span data-stu-id="f0075-465">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="f0075-466">**New-HostedContentFilterPolicy** och **Set-HostedContentFilterPolicy** innehåller en äldre _ZapEnabled_-parameter, samt nyare _PhishZapEnabled_- och _SpamZapEnabled_-parametrar.</span><span class="sxs-lookup"><span data-stu-id="f0075-466">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="f0075-467">Parametern _ZapEnabled_ blev inaktuell i februari 2020.</span><span class="sxs-lookup"><span data-stu-id="f0075-467">The _ZapEnabled_ parameter was deprecated in February 2020.</span></span> <span data-ttu-id="f0075-468">Parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ brukade ärva sina värden från parametern _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="f0075-468">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="f0075-469">Men om du använder parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ i ett kommando eller om du använder inställningarna för **Automatisk rensning av skräppost** eller **Automatisk rensning av nätfiske** i principen för skräppostskydd i Säkerhets- och efterlevnadscentret ignoreras värdet för parametern _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="f0075-469">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="f0075-470">Använd med andra ord inte parametern _ZapEnabled_. Använd istället parametrarna _PhishZapEnabled_ och _SpamZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="f0075-470">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="f0075-471">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f0075-471">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="f0075-472">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-472">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="f0075-473">Om du vill skapa en regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-473">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f0075-474">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-474">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="f0075-475">Principen för skräppostfilter med namnet Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-475">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="f0075-476">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="f0075-476">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="f0075-477">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="f0075-477">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="f0075-478">Använda PowerShell för att visa principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-478">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="f0075-479">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f0075-479">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="f0075-480">Om du vill returnera detaljerad information om en specifik princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-480">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f0075-481">I det här exemplet returneras alla egenskapsvärden för principen för skräppostfilter med namnet Executives.</span><span class="sxs-lookup"><span data-stu-id="f0075-481">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="f0075-482">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f0075-482">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="f0075-483">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-483">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="f0075-484">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-484">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="f0075-485">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f0075-485">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="f0075-486">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f0075-486">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="f0075-487">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-487">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="f0075-488">I det här exemplet returneras alla egenskapsvärden för regeln för skräppostfilter princip med namnet Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="f0075-488">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="f0075-489">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="f0075-489">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="f0075-490">Använda PowerShell för att ändra principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-490">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="f0075-491">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en princip för filter mot skadlig kod i PowerShell som när du skapar principen enligt beskrivningen i avsnittet [Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter](#step-1-use-powershell-to-create-a-spam-filter-policy) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-491">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="f0075-492">Switchparametern _MakeDefault_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid prioriteten **Lägsta** och du kan inte ta bort den) är endast tillgänglig när du ändrar en princip för skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0075-492">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="f0075-493">Du kan inte byta namn på en princip för skräppostfilter (cmdleten **Set-HostedContentFilterPolicy** har ingen _Name_-parameter).</span><span class="sxs-lookup"><span data-stu-id="f0075-493">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f0075-494">När du byter namn på en princip för skräppostskydd i Säkerhets- och efterlevnadscenter byter du bara namn på _regeln_ för skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="f0075-494">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="f0075-495">Om du vill ändra en princip för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-495">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f0075-496">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f0075-496">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="f0075-497">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-497">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="f0075-498">Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en regel som är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="f0075-498">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f0075-499">Om du vill aktivera eller inaktivera befintliga regler för skräppostfilter läser du mer i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f0075-499">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="f0075-500">Annars är inga ytterligare inställningar tillgängliga när du ändrar en regel för skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0075-500">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="f0075-501">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i avsnittet [Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter](#step-2-use-powershell-to-create-a-spam-filter-rule) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f0075-501">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="f0075-502">Om du vill ändra en regel för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-502">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f0075-503">I det här exemplet ändras namnet på den befintliga regeln för skräppostfilter som heter `{Fabrikam Spam Filter}` som kan orsaka problem i Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="f0075-503">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="f0075-504">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="f0075-504">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="f0075-505">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-505">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="f0075-506">Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen för skräppostfilter (regeln för skräppostfilter och den tilldelade principen för skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="f0075-506">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="f0075-507">Du kan inte aktivera eller inaktivera standardprincipen för skräppostskydd (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="f0075-507">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="f0075-508">Om du vill aktivera eller inaktivera en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-508">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="f0075-509">I det här exemplet inaktiveras regeln för skräppostfilter som heter Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="f0075-509">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f0075-510">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="f0075-510">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f0075-511">Detaljerad information om syntax och parametrar finns i [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) och [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="f0075-511">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="f0075-512">Använda PowerShell för att ange prioriteten för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-512">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="f0075-513">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="f0075-513">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f0075-514">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="f0075-514">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f0075-515">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="f0075-515">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f0075-516">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="f0075-516">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f0075-517">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="f0075-517">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f0075-518">Om du vill ange prioriteten för en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-518">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f0075-519">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="f0075-519">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f0075-520">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="f0075-520">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f0075-521">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="f0075-521">**Notes**:</span></span>

- <span data-ttu-id="f0075-522">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-HostedContentFilterRule** istället.</span><span class="sxs-lookup"><span data-stu-id="f0075-522">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="f0075-523">Standardprincipen för skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid prioritetsvärdet **Lägsta** som inte går att ändra.</span><span class="sxs-lookup"><span data-stu-id="f0075-523">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="f0075-524">Använda PowerShell för att ta bort principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-524">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="f0075-525">När du använder PowerShell för att ta bort en princip för skräppostfilter tas motsvarande regel för skräppostfilter inte bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-525">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="f0075-526">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-526">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f0075-527">I det här exemplet tas principen för skräppostfilter med namnet Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-527">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f0075-528">Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f0075-528">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="f0075-529">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f0075-529">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="f0075-530">När du använder PowerShell för att ta bort en regel för skräppostfilter tas motsvarande princip för skräppostfilter inte bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-530">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="f0075-531">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f0075-531">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="f0075-532">I det här exemplet tas regeln för skräppostfilter med namnet Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="f0075-532">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="f0075-533">Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="f0075-533">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f0075-534">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="f0075-534">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="f0075-535">Skicka ett GTUBE-meddelande för att testa inställningarna för skräppostprinciperna</span><span class="sxs-lookup"><span data-stu-id="f0075-535">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="f0075-536">De här stegen fungerar bara om e-postorganisationen som du skickar GTUBE-meddelandet från inte söker igenom efter utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="f0075-536">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="f0075-537">Om organisationen söker igenom går det inte att skicka testmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="f0075-537">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="f0075-538">GTUBE (Generic Test for Unsolicited Bulk Email – Generiskt test för oönskade massutskick) är en textsträng som du lägger till i ett test meddelande för att verifiera organisationens inställningar för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f0075-538">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="f0075-539">Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="f0075-539">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="f0075-540">Lägg till följande GTUBE text i ett e-postmeddelande på en enskild rad, utan blanksteg eller radbrytningar:</span><span class="sxs-lookup"><span data-stu-id="f0075-540">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="f0075-541">Listor över blockerade eller tillåtna</span><span class="sxs-lookup"><span data-stu-id="f0075-541">Allow/Block Lists</span></span>

<span data-ttu-id="f0075-542">Det kommer att finnas tillfällen när våra filter missar meddelandet eller då det tar tid för våra system att komma ifatt det.</span><span class="sxs-lookup"><span data-stu-id="f0075-542">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="f0075-543">I de här fallen har principen för skräppostskydd en lista över Tillåtna och en lista över Blockerade tillgängliga för att åsidosätta den aktuella bedömningen.</span><span class="sxs-lookup"><span data-stu-id="f0075-543">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="f0075-544">Det här alternativet ska bara användas sparsamt eftersom listor kan bli svåra att hantera, och bara tillfälligt eftersom vår filtreringsstack borde göra vad den ska göra.</span><span class="sxs-lookup"><span data-stu-id="f0075-544">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="f0075-545">Det kan finnas situationer där din organisation kanske inte håller med om den bedömning tjänsten tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="f0075-545">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="f0075-546">I det här fallet kanske du vill behålla listan över tillåtna eller blockerade permanent.</span><span class="sxs-lookup"><span data-stu-id="f0075-546">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="f0075-547">Men om du kommer att lägga till en domän i listan över tillåtna för en längre tid bör du be avsändaren att kontrollera att avsändarens domän har autentiserats och ange den som DMARC-avvisa (reject) om den inte är det.</span><span class="sxs-lookup"><span data-stu-id="f0075-547">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
