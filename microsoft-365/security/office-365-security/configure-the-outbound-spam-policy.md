---
title: Konfigurera utgående skräppostfiltrering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur du visar, skapar, ändrar och tar bort utgående skräppostpolicyer i Exchange Online Protection (EOP).
ms.openlocfilehash: 12f2936530a300cf79556ebf02533c187caa23d5
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761724"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="14ef3-103">Konfigurera skräppostfiltrering utanför eu i EOP</span><span class="sxs-lookup"><span data-stu-id="14ef3-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="14ef3-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras utgående e-postmeddelanden som skickas via EOP automatiskt efter skräppost och ovanlig sändningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="14ef3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="14ef3-105">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="14ef3-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="14ef3-106">Misstänkta utgående meddelanden markeras som skräppost (oavsett skräppostförtroendenivå eller SCL) och dirigeras genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill än att hålla Microsoft 365-källe-postservrar borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="14ef3-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="14ef3-107">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [varningsprinciper](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="14ef3-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="14ef3-108">EOP använder utgående skräppostpolicyer som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="14ef3-109">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="14ef3-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="14ef3-110">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="14ef3-111">För större granularitet kan du också skapa anpassade principer för skräppost som är tillämpliga på specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="14ef3-112">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="14ef3-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="14ef3-113">Du kan konfigurera principer för utgående skräppost i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="14ef3-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="14ef3-114">Principer för skräppost från utgående Säkerhets- & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="14ef3-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="14ef3-115">De grundläggande inslagen i en utgående spam-policy i EOP är:</span><span class="sxs-lookup"><span data-stu-id="14ef3-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="14ef3-116">**Principen för skräppostfilter**: Anger åtgärder för utgående skräppostfiltreringsutslag och meddelandealternativen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="14ef3-117">**Regeln för skräppostfilter:** Anger prioritets- och mottagarfilter (vem principen gäller för) för en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="14ef3-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="14ef3-118">Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående skräppostpoliser i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="14ef3-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="14ef3-119">När du skapar en utgående skräppostprincip i Security & Compliance Center skapar du faktiskt en utgående skräppostfilterregel och den tillhörande principen för skräppostfilter samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="14ef3-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="14ef3-120">När du ändrar en utgående skräppostprincip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter regeln för skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="14ef3-121">Alla andra inställningar ändrar den associerade principen för skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="14ef3-122">När du tar bort en utgående skräppostprincip från Security & Compliance Center tas regeln för skräppostfilter och den tillhörande principen för skräppost från skräppost bort.</span><span class="sxs-lookup"><span data-stu-id="14ef3-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="14ef3-123">I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan utgående skräppostfilterprinciper och utgående skräppostfilterregler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="14ef3-124">Du hanterar principer för skräppostutgående skräppost med hjälp av cmdleterna \*\* \* -HostedOutboundSpamFilterPolicy\*\* och du hanterar regler för skräppostfilter med hjälp av cmdlets \*\* \* -HostedOutboundSpamFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="14ef3-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="14ef3-125">I PowerShell skapar du först principen för skräppostfilter och skapar först den utgående skräppostfilterregeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="14ef3-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="14ef3-126">I PowerShell ändrar du inställningarna i principen för skräppost och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="14ef3-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="14ef3-127">När du tar bort en utgående skräppostfilterprincip från PowerShell tas inte motsvarande utgående skräppostfilterregel automatiskt bort och vice versa.</span><span class="sxs-lookup"><span data-stu-id="14ef3-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="14ef3-128">Standardpolicy för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-128">Default outbound spam policy</span></span>

<span data-ttu-id="14ef3-129">Varje organisation har en inbyggd utgående skräppostprincip med namnet Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="14ef3-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="14ef3-130">Principen för skräppostfilter med namnet Standard tillämpas på alla mottagare i organisationen, även om det inte finns någon regel för utgående skräppostfilter (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="14ef3-131">Principen med namnet Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="14ef3-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="14ef3-132">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="14ef3-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="14ef3-133">Principen som heter Standard är standardprincipen (egenskapen **IsDefault** har värdet `True`), och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="14ef3-134">Om du vill öka effektiviteten i skräppostfiltrering kan du skapa anpassade principer för skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="14ef3-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="14ef3-135">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="14ef3-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="14ef3-136">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="14ef3-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="14ef3-137">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="14ef3-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="14ef3-138">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="14ef3-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="14ef3-139">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="14ef3-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="14ef3-140">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="14ef3-140">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="14ef3-141">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="14ef3-141">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="14ef3-142">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="14ef3-142">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="14ef3-143">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="14ef3-143">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="14ef3-144">För skrivskyddad åtkomst till principer för skräppost från utgående skräppost måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="14ef3-144">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="14ef3-145">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="14ef3-145">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="14ef3-146">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="14ef3-146">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="14ef3-147">Våra rekommenderade inställningar för utgående skräppostpolicyer finns i [EOP:s policyinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)för skräppostfilter .</span><span class="sxs-lookup"><span data-stu-id="14ef3-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="14ef3-148">[Standardvarningsprinciperna](../../compliance/alert-policies.md) med namnet **E-sändningsgräns överskred**, **Misstänkta e-postsändningsmönster har upptäckts**och **användaren har begränsat till att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) om ovanlig utgående e-postaktivitet och blockerade användare på grund av utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="14ef3-149">Mer information finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="14ef3-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="14ef3-150">Vi rekommenderar att du använder dessa varningsprinciper i stället för meddelandealternativen i principer för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="14ef3-151">Använd Security & Compliance Center för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="14ef3-152">Genom att skapa en anpassad utgående skräppostprincip i Security & Compliance Center skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="14ef3-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="14ef3-153">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-154">Klicka på **Skapa en utgående princip**på sidan Inställningar för **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="14ef3-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="14ef3-155">Konfigurera följande inställningar i **principen För skräppostutgående skräppost** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="14ef3-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="14ef3-156">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="14ef3-157">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="14ef3-158">(Valfritt) Expandera avsnittet **Meddelanden** om du vill konfigurera ytterligare användare som ska ta emot kopior och meddelanden om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="14ef3-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="14ef3-159">**Skicka en kopia av misstänkta utgående e-postmeddelanden till specifika personer:** Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="14ef3-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="14ef3-160">Den här inställningen fungerar bara i standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="14ef3-161">Det fungerar inte i anpassade utgående skräppostpolicyer som du skapar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="14ef3-162">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-162">To enable this setting:</span></span>

     <span data-ttu-id="14ef3-163">a.</span><span class="sxs-lookup"><span data-stu-id="14ef3-163">a.</span></span> <span data-ttu-id="14ef3-164">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-164">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="14ef3-165">b.</span><span class="sxs-lookup"><span data-stu-id="14ef3-165">b.</span></span> <span data-ttu-id="14ef3-166">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-166">Click **Add people**.</span></span> <span data-ttu-id="14ef3-167">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="14ef3-167">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="14ef3-168">c.</span><span class="sxs-lookup"><span data-stu-id="14ef3-168">c.</span></span> <span data-ttu-id="14ef3-169">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="14ef3-169">Enter the sender's email address.</span></span> <span data-ttu-id="14ef3-170">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="14ef3-170">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="14ef3-171">d.</span><span class="sxs-lookup"><span data-stu-id="14ef3-171">d.</span></span> <span data-ttu-id="14ef3-172">Klicka på</span><span class="sxs-lookup"><span data-stu-id="14ef3-172">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="14ef3-174">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="14ef3-174">to add the recipients.</span></span>

        <span data-ttu-id="14ef3-175">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="14ef3-175">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="14ef3-176">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** på utfällbara.</span><span class="sxs-lookup"><span data-stu-id="14ef3-176">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="14ef3-177">Om du vill ta bort en mottagare klickar du på ![ Knappen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="14ef3-177">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="14ef3-178">e.</span><span class="sxs-lookup"><span data-stu-id="14ef3-178">e.</span></span> <span data-ttu-id="14ef3-179">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-179">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="14ef3-180">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="14ef3-180">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="14ef3-181">**Meddela specifika personer om en avsändare blockeras på grund av att skicka skräppost som skickas:**</span><span class="sxs-lookup"><span data-stu-id="14ef3-181">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="14ef3-182">[Standardvarningsprincipen](../../compliance/alert-policies.md) **Användaren har begränsat från att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) när användare blockeras på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="14ef3-182">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="14ef3-183">Vi rekommenderar att du använder aviseringsprincipen i stället för den här inställningen i principen för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="14ef3-183">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="14ef3-184">Instruktioner finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="14ef3-184">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="14ef3-185">Den här inställningen fungerar bara i standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-185">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="14ef3-186">Det fungerar inte i anpassade utgående skräppostpolicyer som du skapar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-186">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="14ef3-187">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-187">To enable this setting:</span></span>

     <span data-ttu-id="14ef3-188">a.</span><span class="sxs-lookup"><span data-stu-id="14ef3-188">a.</span></span> <span data-ttu-id="14ef3-189">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-189">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="14ef3-190">b.</span><span class="sxs-lookup"><span data-stu-id="14ef3-190">b.</span></span> <span data-ttu-id="14ef3-191">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-191">Click **Add people**.</span></span> <span data-ttu-id="14ef3-192">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="14ef3-192">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="14ef3-193">c.</span><span class="sxs-lookup"><span data-stu-id="14ef3-193">c.</span></span> <span data-ttu-id="14ef3-194">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="14ef3-194">Enter the sender's email address.</span></span> <span data-ttu-id="14ef3-195">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="14ef3-195">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="14ef3-196">d.</span><span class="sxs-lookup"><span data-stu-id="14ef3-196">d.</span></span> <span data-ttu-id="14ef3-197">Klicka på</span><span class="sxs-lookup"><span data-stu-id="14ef3-197">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="14ef3-199">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="14ef3-199">to add the recipients.</span></span>

        <span data-ttu-id="14ef3-200">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="14ef3-200">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="14ef3-201">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** på utfällbara.</span><span class="sxs-lookup"><span data-stu-id="14ef3-201">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="14ef3-202">Om du vill ta bort en mottagare klickar du på ![ Knappen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="14ef3-202">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="14ef3-203">e.</span><span class="sxs-lookup"><span data-stu-id="14ef3-203">e.</span></span> <span data-ttu-id="14ef3-204">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-204">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="14ef3-205">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="14ef3-205">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="14ef3-206">(Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="14ef3-206">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="14ef3-207">Dessa inställningar gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="14ef3-207">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="14ef3-208">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="14ef3-208">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="14ef3-209">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="14ef3-209">A valid value is 0 to 10000.</span></span> <span data-ttu-id="14ef3-210">Standardvärdet är 0, vilket innebär att tjänsten som standard används.</span><span class="sxs-lookup"><span data-stu-id="14ef3-210">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="14ef3-211">Mer information finns i [Skicka gränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="14ef3-211">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="14ef3-212">**Extern timgräns**: Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="14ef3-212">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="14ef3-213">**Intern timgräns**: Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="14ef3-213">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="14ef3-214">**Daglig gräns**: Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="14ef3-214">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="14ef3-215">**Åtgärd när en användare överskrider gränserna ovan**: Konfigurera åtgärden så att den vidtas när någon av **mottagargränserna** överskrids.</span><span class="sxs-lookup"><span data-stu-id="14ef3-215">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="14ef3-216">För alla åtgärder får mottagarna som anges i **användaren begränsade från att skicka e-postaviseringspolicy** (och i den nu redundanta Meddela specifika personer om en **avsändare blockeras på grund av att skicka utgående skräppost** i principen för utgående skräppost får e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="14ef3-216">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="14ef3-217">**Begränsa användaren från att skicka e-post till följande dag:** Detta är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="14ef3-217">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="14ef3-218">E-postmeddelanden skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="14ef3-218">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="14ef3-219">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="14ef3-219">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="14ef3-220">Aktivitetsaviseringen **Användaren har begränsat från att skicka e-post** meddelar administratörer (via e-post och på sidan Visa **aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="14ef3-220">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="14ef3-221">Alla mottagare som anges i **meddela specifika personer om en avsändare blockeras på grund av att skicka utgående skräppost** i policyn meddelas också.</span><span class="sxs-lookup"><span data-stu-id="14ef3-221">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="14ef3-222">Användaren kommer inte att kunna skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="14ef3-222">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="14ef3-223">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="14ef3-223">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="14ef3-224">**Begränsa användaren från att skicka e-post:** E-postmeddelanden skickas, användaren läggs till i portalen \*\*[Begränsade användare] <https://sip.protection.office.com/restrictedusers> \*\* i Security & Compliance Center och användaren kan inte skicka e-post förrän de har tagits bort från portalen **Begränsade användare** av en administratör. När en administratör har tagit bort användaren från listan begränsas användaren inte igen för den dagen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-224">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="14ef3-225">Instruktioner finns i [Ta bort en användare från portalen Begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="14ef3-225">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="14ef3-226">**Ingen åtgärd, endast avisering:** E-postmeddelanden skickas.</span><span class="sxs-lookup"><span data-stu-id="14ef3-226">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="14ef3-227">(Obligatoriskt) Expandera avsnittet **Tillämpat på** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="14ef3-227">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="14ef3-228">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="14ef3-228">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="14ef3-229">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="14ef3-229">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="14ef3-230">Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="14ef3-230">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="14ef3-231">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="14ef3-231">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="14ef3-232">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="14ef3-232">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="14ef3-233">**Avsändarendomänen är**: Anger avsändare i en eller flera av de konfigurerade accepterade domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-233">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="14ef3-234">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="14ef3-234">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="14ef3-235">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="14ef3-235">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="14ef3-236">**Avsändaren är**: Anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-236">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="14ef3-237">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="14ef3-237">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="14ef3-238">Klicka igen i rutan **Lägg till en tagg** för att markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="14ef3-238">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="14ef3-239">**Avsändaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-239">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="14ef3-240">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="14ef3-240">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="14ef3-241">Klicka igen i rutan **Lägg till en tagg** för att markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="14ef3-241">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="14ef3-242">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="14ef3-242">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="14ef3-243">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="14ef3-243">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="14ef3-244">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="14ef3-244">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="14ef3-245">Använda Security & Compliance Center för att visa principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-245">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="14ef3-246">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-246">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-247">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera om du vill expandera en ![ ](../../media/scc-expand-icon.png) utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="14ef3-247">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="14ef3-248">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-248">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="14ef3-249">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-249">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="14ef3-250">Principinställningarna visas i den utökade principinformation som visas eller klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-250">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="14ef3-251">Använda Security & Compliance Center för att ändra principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-251">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="14ef3-252">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-252">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-253">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera om du vill expandera en ![ ](../../media/scc-expand-icon.png) utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="14ef3-253">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="14ef3-254">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-254">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="14ef3-255">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-255">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="14ef3-256">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-256">Click **Edit policy**.</span></span>

<span data-ttu-id="14ef3-257">För anpassade principer för skräppost från utgående är de tillgängliga inställningarna i det utfällbara resultatet som visas identiska med de som beskrivs i avsnittet [Använd säkerhets- & Compliance Center för att skapa utgående skräppostprinciper.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="14ef3-257">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="14ef3-258">För standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip**är avsnittet **Tillämpad på** inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-258">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="14ef3-259">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="14ef3-259">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="14ef3-260">Aktivera eller inaktivera principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-260">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="14ef3-261">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-261">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-262">På sidan **Inställningar för skräppost** klickar du på Expandera ikonen för att expandera en anpassad princip som du har skapat ![ ](../../media/scc-expand-icon.png) (värdet i kolumnen **Typ** är principen **Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="14ef3-262">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="14ef3-263">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="14ef3-263">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="14ef3-264">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-264">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="14ef3-266">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-266">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="14ef3-268">Du kan inte inaktivera standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="14ef3-268">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="14ef3-269">Ange prioritet för anpassade principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-269">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="14ef3-270">Som standard prioriteras principer för utgående skräppost som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="14ef3-270">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="14ef3-271">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="14ef3-271">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="14ef3-272">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="14ef3-272">No two policies can have the same priority.</span></span>

<span data-ttu-id="14ef3-273">Principer för anpassad skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="14ef3-273">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="14ef3-274">Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="14ef3-274">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="14ef3-275">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="14ef3-275">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="14ef3-276">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-276">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-277">På sidan **Inställningar för skräppost** hittar du de principer där värdet i kolumnen **Typ** är **anpassad utgående skräppostpolicy**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-277">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="14ef3-278">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="14ef3-278">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="14ef3-279">Den anpassade utgående skräppostprincipen med högst prioritet har värde ![ nedåtpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **ikon 0**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-279">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="14ef3-280">Den anpassade utgående skräppostprincipen med den lägsta prioriteten har ![ värdeupppilen ](../../media/ITPro-EAC-UpArrowIcon.png) **ikon n** (till exempel ![ up arrow-ikonen ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="14ef3-280">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="14ef3-281">Om du har tre eller flera anpassade utgående skräppostprinciper har principerna mellan högsta och lägsta prioritet värden ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ikon nedåtpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **ikon n** (till exempel ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ nedåtpilens nedåtpil ikon ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="14ef3-281">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="14ef3-282">Klicka på</span><span class="sxs-lookup"><span data-stu-id="14ef3-282">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="14ef3-284">eller</span><span class="sxs-lookup"><span data-stu-id="14ef3-284">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="14ef3-286">om du vill flytta den anpassade principen för utgående skräppost uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="14ef3-286">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="14ef3-287">Använd Security & Compliance Center för att ta bort principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-287">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="14ef3-288">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-288">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="14ef3-289">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera för att expandera den anpassade principen som du vill ta bort ![ ](../../media/scc-expand-icon.png) (kolumnen **Typ** är principen **Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="14ef3-289">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="14ef3-290">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-290">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="14ef3-291">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="14ef3-291">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="14ef3-292">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-292">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="14ef3-293">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppost för utgående information</span><span class="sxs-lookup"><span data-stu-id="14ef3-293">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="14ef3-294">Använda PowerShell för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="14ef3-294">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="14ef3-295">Att skapa en utgående skräppostprincip i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="14ef3-295">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="14ef3-296">Skapa principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="14ef3-296">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="14ef3-297">Skapa den utgående skräppostfilterregeln som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="14ef3-297">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="14ef3-298">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="14ef3-298">**Notes**:</span></span>

- <span data-ttu-id="14ef3-299">Du kan skapa en ny regel för skräppostfilter och tilldela den en befintlig, oassocierad utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="14ef3-299">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="14ef3-300">En regel för skräppostfilter kan inte associeras med mer än en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="14ef3-300">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="14ef3-301">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-301">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="14ef3-302">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="14ef3-302">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="14ef3-303">Ange prioritet för principen när du skapar (_Prioritet_ _\<Number\>_ ) på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="14ef3-303">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="14ef3-304">En ny princip för skräppostfilter som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en skräppostfilterregel.</span><span class="sxs-lookup"><span data-stu-id="14ef3-304">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="14ef3-305">Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-305">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="14ef3-306">Om du vill skapa en princip för skräppostfilter för att skapa en utgående skräppostfilt</span><span class="sxs-lookup"><span data-stu-id="14ef3-306">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="14ef3-307">I det här exemplet skapas en ny utgående skräppostfilterprincip med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="14ef3-307">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="14ef3-308">Mottagarhastighetsgränserna är begränsade till mindre värden som standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="14ef3-308">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="14ef3-309">Mer information finns i [Skicka gränser för Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="14ef3-309">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="14ef3-310">När en av gränserna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="14ef3-310">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="14ef3-311">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="14ef3-311">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="14ef3-312">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-312">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="14ef3-313">Om du vill skapa en regel för skräppostfilter för att skapa ett utgående skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-313">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="14ef3-314">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="14ef3-314">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="14ef3-315">Den utgående skräppostfilterprincipen Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="14ef3-315">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="14ef3-316">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="14ef3-316">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="14ef3-317">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="14ef3-317">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="14ef3-318">Använda PowerShell för att visa principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="14ef3-318">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="14ef3-319">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="14ef3-319">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="14ef3-320">Om du vill returnera detaljerad information om en specifik utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-320">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="14ef3-321">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterprincipen Chefer.</span><span class="sxs-lookup"><span data-stu-id="14ef3-321">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="14ef3-322">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="14ef3-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="14ef3-323">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-323">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="14ef3-324">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="14ef3-324">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="14ef3-325">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="14ef3-325">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="14ef3-326">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="14ef3-326">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="14ef3-327">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-327">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="14ef3-328">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="14ef3-328">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="14ef3-329">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="14ef3-329">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="14ef3-330">Använda PowerShell för att ändra principer för skräppost från inkommande skräppost</span><span class="sxs-lookup"><span data-stu-id="14ef3-330">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="14ef3-331">Samma inställningar är tillgängliga när du ändrar en policy för skadlig kodfilter i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett utgående skräppostfilterprincipavsnitt](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="14ef3-331">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="14ef3-332">**Du**kan inte byta namn på en utgående skräppostfilterprincip (cmdleten **Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="14ef3-332">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="14ef3-333">När du byter namn på en utgående skräppostprincip i Security & Compliance Center byter du bara namn på _regeln för_skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="14ef3-333">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="14ef3-334">Om du vill ändra en utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-334">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="14ef3-335">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="14ef3-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="14ef3-336">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-336">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="14ef3-337">Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern Aktiverad som gör att du kan skapa en _inaktiverad_ regel.</span><span class="sxs-lookup"><span data-stu-id="14ef3-337">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="14ef3-338">Information om hur du aktiverar eller inaktiverar befintliga regler för skräppostfilter finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="14ef3-338">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="14ef3-339">Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående skräppostfilterregel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14ef3-339">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="14ef3-340">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett utgående skräppostfilterregelavsnitt](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="14ef3-340">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="14ef3-341">Om du vill ändra en regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-341">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="14ef3-342">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="14ef3-342">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="14ef3-343">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-343">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="14ef3-344">Om du aktiverar eller inaktiverar en regel för utgående skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen för utgående skräppost (regeln för utgående skräppostfilter och den tilldelade utgående skräppostfilterprincipen).</span><span class="sxs-lookup"><span data-stu-id="14ef3-344">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="14ef3-345">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="14ef3-345">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="14ef3-346">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-346">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="14ef3-347">I det här exemplet inaktiveras den utgående skräppostfilterregeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="14ef3-347">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="14ef3-348">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="14ef3-348">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="14ef3-349">Detaljerad syntax- och parameterinformation finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [Inaktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="14ef3-349">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="14ef3-350">Använd PowerShell för att ange prioritet för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-350">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="14ef3-351">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="14ef3-351">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="14ef3-352">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="14ef3-352">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="14ef3-353">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="14ef3-353">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="14ef3-354">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="14ef3-354">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="14ef3-355">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="14ef3-355">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="14ef3-356">Om du vill ange prioritet för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="14ef3-356">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="14ef3-357">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="14ef3-357">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="14ef3-358">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="14ef3-358">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="14ef3-359">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="14ef3-359">**Notes**:</span></span>

- <span data-ttu-id="14ef3-360">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **New-HostedOutboundSpamFilterRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="14ef3-360">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="14ef3-361">Principen för det utgående standardfiltfilteret har ingen motsvarande skräppostfilterregel och har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="14ef3-361">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="14ef3-362">Använda PowerShell för att ta bort principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="14ef3-362">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="14ef3-363">När du använder PowerShell för att ta bort en utgående skräppostfilterprincip tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="14ef3-363">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="14ef3-364">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-364">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="14ef3-365">I det här exemplet tas den utgående skräppostfilterprincipen marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="14ef3-365">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="14ef3-366">Detaljerad syntax- och parameterinformation finns i [Ta bort värdbaseradeOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="14ef3-366">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="14ef3-367">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="14ef3-367">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="14ef3-368">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande utgående skräppostfilterprincip bort.</span><span class="sxs-lookup"><span data-stu-id="14ef3-368">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="14ef3-369">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="14ef3-369">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="14ef3-370">I det här exemplet tas den utgående skräppostfilterregeln marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="14ef3-370">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="14ef3-371">Detaljerad syntax- och parameterinformation finns i [Ta bort värdbaseradeOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="14ef3-371">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="14ef3-372">Mer information</span><span class="sxs-lookup"><span data-stu-id="14ef3-372">For more information</span></span>

[<span data-ttu-id="14ef3-373">Ta bort blockerade användare från portalen med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="14ef3-373">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="14ef3-374">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="14ef3-374">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="14ef3-375">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="14ef3-375">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
