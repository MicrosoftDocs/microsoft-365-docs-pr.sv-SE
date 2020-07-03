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
ms.openlocfilehash: 7102f858e0293f2a55fe68a55d4dc2cf3ab38a33
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024588"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="33066-103">Konfigurera skräppostfiltrering utanför eu i EOP</span><span class="sxs-lookup"><span data-stu-id="33066-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="33066-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras utgående e-postmeddelanden som skickas via EOP automatiskt efter skräppost och ovanlig sändningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="33066-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="33066-105">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="33066-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="33066-106">Misstänkta utgående meddelanden markeras som skräppost (oavsett skräppostförtroendenivå eller SCL) och dirigeras genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill än att hålla Microsoft 365-källe-postservrar borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="33066-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="33066-107">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [varningsprinciper](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="33066-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="33066-108">EOP använder utgående skräppostpolicyer som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="33066-109">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="33066-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="33066-110">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="33066-111">För större granularitet kan du också skapa anpassade principer för skräppost som är tillämpliga på specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33066-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="33066-112">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="33066-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="33066-113">Du kan konfigurera principer för utgående skräppost i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="33066-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="33066-114">Principer för skräppost från utgående Säkerhets- & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="33066-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="33066-115">De grundläggande inslagen i en utgående spam-policy i EOP är:</span><span class="sxs-lookup"><span data-stu-id="33066-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="33066-116">**Principen för skräppostfilter**: Anger åtgärder för utgående skräppostfiltreringsutslag och meddelandealternativen.</span><span class="sxs-lookup"><span data-stu-id="33066-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="33066-117">**Regeln för skräppostfilter:** Anger prioritets- och mottagarfilter (vem principen gäller för) för en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="33066-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="33066-118">Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående skräppostpoliser i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="33066-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="33066-119">När du skapar en utgående skräppostprincip i Security & Compliance Center skapar du faktiskt en utgående skräppostfilterregel och den tillhörande principen för skräppostfilter samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="33066-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="33066-120">När du ändrar en utgående skräppostprincip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter regeln för skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="33066-121">Alla andra inställningar ändrar den associerade principen för skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="33066-122">När du tar bort en utgående skräppostprincip från Security & Compliance Center tas regeln för skräppostfilter och den tillhörande principen för skräppost från skräppost bort.</span><span class="sxs-lookup"><span data-stu-id="33066-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="33066-123">I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan utgående skräppostfilterprinciper och utgående skräppostfilterregler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="33066-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="33066-124">Du hanterar principer för skräppostutgående skräppost med hjälp av cmdleterna \*\* \* -HostedOutboundSpamFilterPolicy\*\* och du hanterar regler för skräppostfilter med hjälp av cmdlets \*\* \* -HostedOutboundSpamFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="33066-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="33066-125">I PowerShell skapar du först principen för skräppostfilter och skapar först den utgående skräppostfilterregeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="33066-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="33066-126">I PowerShell ändrar du inställningarna i principen för skräppost och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="33066-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="33066-127">När du tar bort en utgående skräppostfilterprincip från PowerShell tas inte motsvarande utgående skräppostfilterregel automatiskt bort och vice versa.</span><span class="sxs-lookup"><span data-stu-id="33066-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="33066-128">Standardpolicy för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="33066-128">Default outbound spam policy</span></span>

<span data-ttu-id="33066-129">Varje organisation har en inbyggd utgående skräppostprincip med namnet Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="33066-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="33066-130">Principen för skräppostfilter med namnet Standard tillämpas på alla mottagare i organisationen, även om det inte finns någon regel för utgående skräppostfilter (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="33066-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="33066-131">Principen med namnet Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="33066-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="33066-132">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="33066-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="33066-133">Principen som heter Standard är standardprincipen (egenskapen **IsDefault** har värdet `True`), och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="33066-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="33066-134">Om du vill öka effektiviteten i skräppostfiltrering kan du skapa anpassade principer för skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="33066-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33066-135">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="33066-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33066-136">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="33066-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="33066-137">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="33066-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="33066-138">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="33066-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="33066-139">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="33066-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="33066-140">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="33066-140">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="33066-141">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="33066-141">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="33066-142">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="33066-142">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="33066-143">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="33066-143">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="33066-144">För skrivskyddad åtkomst till principer för skräppost från utgående skräppost måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="33066-144">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="33066-145">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="33066-145">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="33066-146">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="33066-146">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="33066-147">Våra rekommenderade inställningar för utgående skräppostpolicyer finns i [EOP:s policyinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)för skräppostfilter .</span><span class="sxs-lookup"><span data-stu-id="33066-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="33066-148">[Standardvarningsprinciperna](../../compliance/alert-policies.md) med namnet **E-sändningsgräns överskred**, **Misstänkta e-postsändningsmönster har upptäckts**och **användaren har begränsat till att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) om ovanlig utgående e-postaktivitet och blockerade användare på grund av utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="33066-149">Mer information finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="33066-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="33066-150">Vi rekommenderar att du använder dessa varningsprinciper i stället för meddelandealternativen i principer för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="33066-151">Använd Security & Compliance Center för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="33066-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="33066-152">Genom att skapa en anpassad utgående skräppostprincip i Security & Compliance Center skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="33066-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="33066-153">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-154">Klicka på **Skapa en utgående princip**på sidan Inställningar för **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="33066-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="33066-155">Konfigurera följande inställningar i **principen För skräppostutgående skräppost** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="33066-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="33066-156">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="33066-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="33066-157">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="33066-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="33066-158">(Valfritt) Expandera avsnittet **Meddelanden** om du vill konfigurera ytterligare användare som ska ta emot kopior och meddelanden om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="33066-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="33066-159">**Skicka en kopia av misstänkta utgående e-postmeddelanden till specifika personer:** Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="33066-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="33066-160">Den här inställningen fungerar bara i standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="33066-161">Det fungerar inte i anpassade utgående skräppostpolicyer som du skapar.</span><span class="sxs-lookup"><span data-stu-id="33066-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="33066-162">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="33066-162">To enable this setting:</span></span>

     1. <span data-ttu-id="33066-163">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="33066-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="33066-164">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="33066-164">Click **Add people**.</span></span> <span data-ttu-id="33066-165">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="33066-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="33066-166">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33066-166">Enter the sender's email address.</span></span> <span data-ttu-id="33066-167">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="33066-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="33066-168">Klicka på</span><span class="sxs-lookup"><span data-stu-id="33066-168">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="33066-170">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="33066-170">to add the recipients.</span></span>

        <span data-ttu-id="33066-171">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="33066-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="33066-172">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** på utfällbara.</span><span class="sxs-lookup"><span data-stu-id="33066-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="33066-173">Om du vill ta bort en mottagare klickar du på ![ Knappen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="33066-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="33066-174">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="33066-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="33066-175">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="33066-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="33066-176">**Meddela specifika personer om en avsändare blockeras på grund av att skicka skräppost som skickas:**</span><span class="sxs-lookup"><span data-stu-id="33066-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="33066-177">[Standardvarningsprincipen](../../compliance/alert-policies.md) **Användaren har begränsat från att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) när användare blockeras på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="33066-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="33066-178">Vi rekommenderar att du använder aviseringsprincipen i stället för den här inställningen i principen för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="33066-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="33066-179">Instruktioner finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="33066-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="33066-180">Den här inställningen fungerar bara i standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-180">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="33066-181">Det fungerar inte i anpassade utgående skräppostpolicyer som du skapar.</span><span class="sxs-lookup"><span data-stu-id="33066-181">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="33066-182">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="33066-182">To enable this setting:</span></span>

     <span data-ttu-id="33066-183">a.</span><span class="sxs-lookup"><span data-stu-id="33066-183">a.</span></span> <span data-ttu-id="33066-184">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="33066-184">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="33066-185">b.</span><span class="sxs-lookup"><span data-stu-id="33066-185">b.</span></span> <span data-ttu-id="33066-186">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="33066-186">Click **Add people**.</span></span> <span data-ttu-id="33066-187">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="33066-187">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="33066-188">c.</span><span class="sxs-lookup"><span data-stu-id="33066-188">c.</span></span> <span data-ttu-id="33066-189">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="33066-189">Enter the sender's email address.</span></span> <span data-ttu-id="33066-190">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="33066-190">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="33066-191">d.</span><span class="sxs-lookup"><span data-stu-id="33066-191">d.</span></span> <span data-ttu-id="33066-192">Klicka på</span><span class="sxs-lookup"><span data-stu-id="33066-192">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="33066-194">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="33066-194">to add the recipients.</span></span>

        <span data-ttu-id="33066-195">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="33066-195">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="33066-196">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** på utfällbara.</span><span class="sxs-lookup"><span data-stu-id="33066-196">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="33066-197">Om du vill ta bort en mottagare klickar du på ![ Knappen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="33066-197">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="33066-198">e.</span><span class="sxs-lookup"><span data-stu-id="33066-198">e.</span></span> <span data-ttu-id="33066-199">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="33066-199">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="33066-200">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="33066-200">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="33066-201">(Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="33066-201">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="33066-202">Dessa inställningar gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="33066-202">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="33066-203">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="33066-203">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="33066-204">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="33066-204">A valid value is 0 to 10000.</span></span> <span data-ttu-id="33066-205">Standardvärdet är 0, vilket innebär att tjänsten som standard används.</span><span class="sxs-lookup"><span data-stu-id="33066-205">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="33066-206">Mer information finns i [Skicka gränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="33066-206">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="33066-207">**Extern timgräns**: Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="33066-207">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="33066-208">**Intern timgräns**: Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="33066-208">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="33066-209">**Daglig gräns**: Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="33066-209">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="33066-210">**Åtgärd när en användare överskrider gränserna ovan**: Konfigurera åtgärden så att den vidtas när någon av **mottagargränserna** överskrids.</span><span class="sxs-lookup"><span data-stu-id="33066-210">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="33066-211">För alla åtgärder får mottagarna som anges i **användaren begränsade från att skicka e-postaviseringspolicy** (och i den nu redundanta Meddela specifika personer om en **avsändare blockeras på grund av att skicka utgående skräppost** i principen för utgående skräppost får e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="33066-211">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="33066-212">**Begränsa användaren från att skicka e-post till följande dag:** Detta är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="33066-212">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="33066-213">E-postmeddelanden skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="33066-213">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="33066-214">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="33066-214">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="33066-215">Aktivitetsaviseringen **Användaren har begränsat från att skicka e-post** meddelar administratörer (via e-post och på sidan Visa **aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="33066-215">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="33066-216">Alla mottagare som anges i **meddela specifika personer om en avsändare blockeras på grund av att skicka utgående skräppost** i policyn meddelas också.</span><span class="sxs-lookup"><span data-stu-id="33066-216">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="33066-217">Användaren kommer inte att kunna skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="33066-217">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="33066-218">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="33066-218">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="33066-219">**Begränsa användaren från att skicka e-post:** E-postmeddelanden skickas, användaren läggs till i portalen \*\*[Begränsade användare] <https://sip.protection.office.com/restrictedusers> \*\* i Security & Compliance Center och användaren kan inte skicka e-post förrän de har tagits bort från portalen **Begränsade användare** av en administratör. När en administratör har tagit bort användaren från listan begränsas användaren inte igen för den dagen.</span><span class="sxs-lookup"><span data-stu-id="33066-219">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="33066-220">Instruktioner finns i [Ta bort en användare från portalen Begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="33066-220">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="33066-221">**Ingen åtgärd, endast avisering:** E-postmeddelanden skickas.</span><span class="sxs-lookup"><span data-stu-id="33066-221">**No action, alert only**: Email notifications are sent.</span></span>
6. <span data-ttu-id="33066-222">(Valfritt) Expandera avsnittet **Automatisk vidarebefordran** om du vill konfigurera kontroller över hur automatisk vidarebefordran av användare styrs.</span><span class="sxs-lookup"><span data-stu-id="33066-222">(Optional) Expand **Automatic Forwarding** section to configure controls over how automatic forwarding by users is controlled.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33066-223">Dessa inställningar gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="33066-223">These settings are only applicable to cloud-based mailboxes.</span></span>
   
   - <span data-ttu-id="33066-224">**Automatisk vidarebefordran**</span><span class="sxs-lookup"><span data-stu-id="33066-224">**Automatic Forwarding**</span></span>
  
      <span data-ttu-id="33066-225">Välj ett av alternativen för att styra hur automatisk vidarebefordring hanteras.</span><span class="sxs-lookup"><span data-stu-id="33066-225">Select one of the options to control how automatic forwarding is handled.</span></span>
    
      - <span data-ttu-id="33066-226">**Automatisk:** Standardinställning som gör att systemet kan styra automatisk vidarebefordran med automatisk vidarebefordran inaktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="33066-226">**Automatic**: Default setting that allows the system to control automatic forwarding with automatic forwarding disabled by default.</span></span>
      - <span data-ttu-id="33066-227">**På**: Extern vidarebefordran aktiveras inom principen utan begränsning.</span><span class="sxs-lookup"><span data-stu-id="33066-227">**On**: External forwarding is enabled within the policy without restriction.</span></span>
      - <span data-ttu-id="33066-228">**Av**: Extern vidarebefordran är inaktiverad och kommer att blockeras</span><span class="sxs-lookup"><span data-stu-id="33066-228">**Off**: External forwarding is disabled and will be blocked</span></span>

7. <span data-ttu-id="33066-229">(Obligatoriskt) Expandera avsnittet **Tillämpat på** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="33066-229">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="33066-230">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="33066-230">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="33066-231">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="33066-231">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="33066-232">Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="33066-232">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="33066-233">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="33066-233">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="33066-234">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="33066-234">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="33066-235">**Avsändarendomänen är**: Anger avsändare i en eller flera av de konfigurerade accepterade domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33066-235">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="33066-236">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="33066-236">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="33066-237">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="33066-237">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="33066-238">**Avsändaren är**: Anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33066-238">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="33066-239">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="33066-239">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="33066-240">Klicka igen i rutan **Lägg till en tagg** för att markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="33066-240">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="33066-241">**Avsändaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33066-241">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="33066-242">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="33066-242">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="33066-243">Klicka igen i rutan **Lägg till en tagg** för att markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="33066-243">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="33066-244">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="33066-244">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="33066-245">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="33066-245">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="33066-246">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="33066-246">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="33066-247">Använda Security & Compliance Center för att visa principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="33066-247">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="33066-248">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-249">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera om du vill expandera en ![ ](../../media/scc-expand-icon.png) utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="33066-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="33066-250">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="33066-250">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="33066-251">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="33066-251">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="33066-252">Principinställningarna visas i den utökade principinformation som visas eller klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="33066-252">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="33066-253">Använda Security & Compliance Center för att ändra principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="33066-253">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="33066-254">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-255">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera om du vill expandera en ![ ](../../media/scc-expand-icon.png) utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="33066-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="33066-256">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="33066-256">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="33066-257">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="33066-257">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="33066-258">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="33066-258">Click **Edit policy**.</span></span>

<span data-ttu-id="33066-259">För anpassade principer för skräppost från utgående är de tillgängliga inställningarna i det utfällbara resultatet som visas identiska med de som beskrivs i avsnittet [Använd säkerhets- & Compliance Center för att skapa utgående skräppostprinciper.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="33066-259">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="33066-260">För standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip**är avsnittet **Tillämpad på** inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="33066-260">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="33066-261">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="33066-261">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="33066-262">Aktivera eller inaktivera principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="33066-262">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="33066-263">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-264">På sidan **Inställningar för skräppost** klickar du på Expandera ikonen för att expandera en anpassad princip som du har skapat ![ ](../../media/scc-expand-icon.png) (värdet i kolumnen **Typ** är principen **Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="33066-264">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="33066-265">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="33066-265">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="33066-266">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="33066-266">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="33066-268">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="33066-268">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="33066-270">Du kan inte inaktivera standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="33066-270">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="33066-271">Ange prioritet för anpassade principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="33066-271">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="33066-272">Som standard prioriteras principer för utgående skräppost som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="33066-272">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="33066-273">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="33066-273">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="33066-274">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="33066-274">No two policies can have the same priority.</span></span>

<span data-ttu-id="33066-275">Principer för anpassad skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="33066-275">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="33066-276">Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="33066-276">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="33066-277">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="33066-277">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="33066-278">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-278">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-279">På sidan **Inställningar för skräppost** hittar du de principer där värdet i kolumnen **Typ** är **anpassad utgående skräppostpolicy**.</span><span class="sxs-lookup"><span data-stu-id="33066-279">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="33066-280">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="33066-280">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="33066-281">Den anpassade utgående skräppostprincipen med högst prioritet har värde ![ nedåtpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **ikon 0**.</span><span class="sxs-lookup"><span data-stu-id="33066-281">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="33066-282">Den anpassade utgående skräppostprincipen med den lägsta prioriteten har ![ värdeupppilen ](../../media/ITPro-EAC-UpArrowIcon.png) **ikon n** (till exempel ![ up arrow-ikonen ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="33066-282">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="33066-283">Om du har tre eller flera anpassade utgående skräppostprinciper har principerna mellan högsta och lägsta prioritet värden ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ikon nedåtpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **ikon n** (till exempel ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ nedåtpilens nedåtpil ikon ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="33066-283">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="33066-284">Klicka på</span><span class="sxs-lookup"><span data-stu-id="33066-284">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="33066-286">eller</span><span class="sxs-lookup"><span data-stu-id="33066-286">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="33066-288">om du vill flytta den anpassade principen för utgående skräppost uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="33066-288">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="33066-289">Använd Security & Compliance Center för att ta bort principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="33066-289">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="33066-290">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="33066-290">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="33066-291">På sidan **Inställningar för skräppost** klickar du på Ikonen Expandera för att expandera den anpassade principen som du vill ta bort ![ ](../../media/scc-expand-icon.png) (kolumnen **Typ** är principen **Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="33066-291">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="33066-292">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="33066-292">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="33066-293">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="33066-293">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="33066-294">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="33066-294">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="33066-295">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppost för utgående information</span><span class="sxs-lookup"><span data-stu-id="33066-295">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="33066-296">Använda PowerShell för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="33066-296">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="33066-297">Att skapa en utgående skräppostprincip i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="33066-297">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="33066-298">Skapa principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="33066-298">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="33066-299">Skapa den utgående skräppostfilterregeln som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="33066-299">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="33066-300">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="33066-300">**Notes**:</span></span>

- <span data-ttu-id="33066-301">Du kan skapa en ny regel för skräppostfilter och tilldela den en befintlig, oassocierad utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="33066-301">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="33066-302">En regel för skräppostfilter kan inte associeras med mer än en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="33066-302">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="33066-303">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="33066-303">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="33066-304">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="33066-304">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="33066-305">Ange prioritet för principen när du skapar (_Prioritet_ _\<Number\>_ ) på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="33066-305">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="33066-306">En ny princip för skräppostfilter som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en skräppostfilterregel.</span><span class="sxs-lookup"><span data-stu-id="33066-306">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="33066-307">Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-307">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="33066-308">Om du vill skapa en princip för skräppostfilter för att skapa en utgående skräppostfilt</span><span class="sxs-lookup"><span data-stu-id="33066-308">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="33066-309">I det här exemplet skapas en ny utgående skräppostfilterprincip med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="33066-309">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="33066-310">Mottagarhastighetsgränserna är begränsade till mindre värden som standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="33066-310">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="33066-311">Mer information finns i [Skicka gränser för Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="33066-311">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="33066-312">När en av gränserna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="33066-312">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="33066-313">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="33066-313">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="33066-314">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-314">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="33066-315">Om du vill skapa en regel för skräppostfilter för att skapa ett utgående skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-315">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="33066-316">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="33066-316">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="33066-317">Den utgående skräppostfilterprincipen Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="33066-317">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="33066-318">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="33066-318">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="33066-319">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="33066-319">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="33066-320">Använda PowerShell för att visa principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="33066-320">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="33066-321">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="33066-321">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="33066-322">Om du vill returnera detaljerad information om en specifik utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-322">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="33066-323">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterprincipen Chefer.</span><span class="sxs-lookup"><span data-stu-id="33066-323">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="33066-324">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="33066-324">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="33066-325">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-325">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="33066-326">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33066-326">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="33066-327">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="33066-327">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="33066-328">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="33066-328">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="33066-329">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-329">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="33066-330">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="33066-330">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="33066-331">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="33066-331">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="33066-332">Använda PowerShell för att ändra principer för skräppost från inkommande skräppost</span><span class="sxs-lookup"><span data-stu-id="33066-332">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="33066-333">Samma inställningar är tillgängliga när du ändrar en policy för skadlig kodfilter i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett utgående skräppostfilterprincipavsnitt](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="33066-333">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="33066-334">Du kan inte byta namn på en utgående skräppostfilterprincip (cmdleten **Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="33066-334">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="33066-335">När du byter namn på en utgående skräppostprincip i Security & Compliance Center byter du bara namn på _regeln för_skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="33066-335">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="33066-336">Om du vill ändra en utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-336">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="33066-337">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="33066-337">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="33066-338">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-338">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="33066-339">Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern Aktiverad som gör att du kan skapa en _inaktiverad_ regel.</span><span class="sxs-lookup"><span data-stu-id="33066-339">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="33066-340">Information om hur du aktiverar eller inaktiverar befintliga regler för skräppostfilter finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="33066-340">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="33066-341">Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående skräppostfilterregel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33066-341">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="33066-342">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett utgående skräppostfilterregelavsnitt](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="33066-342">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="33066-343">Om du vill ändra en regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-343">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="33066-344">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="33066-344">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="33066-345">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-345">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="33066-346">Om du aktiverar eller inaktiverar en regel för utgående skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen för utgående skräppost (regeln för utgående skräppostfilter och den tilldelade utgående skräppostfilterprincipen).</span><span class="sxs-lookup"><span data-stu-id="33066-346">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="33066-347">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="33066-347">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="33066-348">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-348">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="33066-349">I det här exemplet inaktiveras den utgående skräppostfilterregeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="33066-349">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33066-350">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="33066-350">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33066-351">Detaljerad syntax- och parameterinformation finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [Inaktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="33066-351">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="33066-352">Använd PowerShell för att ange prioritet för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-352">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="33066-353">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="33066-353">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="33066-354">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="33066-354">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="33066-355">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="33066-355">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="33066-356">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="33066-356">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="33066-357">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="33066-357">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="33066-358">Om du vill ange prioritet för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33066-358">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="33066-359">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="33066-359">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="33066-360">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="33066-360">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 
> - <span data-ttu-id="33066-361">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **New-HostedOutboundSpamFilterRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="33066-361">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="33066-362">Principen för det utgående standardfiltfilteret har ingen motsvarande skräppostfilterregel och har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="33066-362">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="33066-363">Använda PowerShell för att ta bort principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="33066-363">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="33066-364">När du använder PowerShell för att ta bort en utgående skräppostfilterprincip tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="33066-364">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="33066-365">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-365">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="33066-366">I det här exemplet tas den utgående skräppostfilterprincipen marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="33066-366">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="33066-367">Detaljerad syntax- och parameterinformation finns i [Ta bort värdbaseradeOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="33066-367">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="33066-368">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="33066-368">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="33066-369">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande utgående skräppostfilterprincip bort.</span><span class="sxs-lookup"><span data-stu-id="33066-369">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="33066-370">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="33066-370">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="33066-371">I det här exemplet tas den utgående skräppostfilterregeln marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="33066-371">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="33066-372">Detaljerad syntax- och parameterinformation finns i [Ta bort värdbaseradeOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="33066-372">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="33066-373">Mer information</span><span class="sxs-lookup"><span data-stu-id="33066-373">For more information</span></span>

[<span data-ttu-id="33066-374">Ta bort blockerade användare från portalen med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="33066-374">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="33066-375">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="33066-375">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="33066-376">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="33066-376">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="33066-377">Rapporten Automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="33066-377">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
