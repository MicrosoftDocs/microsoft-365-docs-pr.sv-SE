---
title: Konfigurera skräppostfiltrering
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
description: Skräppostfiltrering är alltid aktiverat om du använder tjänsten för att skicka utgående e-post, vilket skyddar organisationer som använder tjänsten och deras avsedda mottagare.
ms.openlocfilehash: e788310ae8fd3c0da7f1a39fbba2dc0d6e369d30
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893959"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="d8e3d-103">Konfigurera skräppostfiltrering utanför mängden i Office 365</span><span class="sxs-lookup"><span data-stu-id="d8e3d-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="d8e3d-104">Om du är office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection -kund (EOP) utan Exchange Online-postlådor kontrolleras utgående e-postmeddelanden som skickas via EOP automatiskt efter skräppost och ovanliga skicka aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="d8e3d-105">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="d8e3d-106">Misstänkta utgående meddelanden markeras som skräppost (oavsett skräppostförtroendenivå eller SCL) och dirigeras genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill än att hålla e-postservrar för Office 365 borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="d8e3d-107">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [varningsprinciper](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="d8e3d-108">EOP använder utgående skräppostpolicyer som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="d8e3d-109">Mer information finns [i Skydd mot skräppost i Office 365](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="d8e3d-110">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="d8e3d-111">För större granularitet kan du också skapa anpassade principer för skräppost som är tillämpliga på specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d8e3d-112">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (körordningen) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d8e3d-113">Du kan konfigurera principer för skräppost från utgående företag i Office 365 Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Office 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="d8e3d-114">Principer för utgående skräppost i Office 365 Security & Compliance Center vs Exchange Online PowerShell eller Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8e3d-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="d8e3d-115">De grundläggande inslagen i en utgående spam-policy i EOP är:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="d8e3d-116">**Principen för skräppostfilter:** Anger åtgärder för utgående skräppostfiltreringsutslag och meddelandealternativen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="d8e3d-117">**Regeln för skräppostfilter:** Anger prioritets- och mottagarfilter (vem principen gäller för) för en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="d8e3d-118">Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående skräppostpoliser i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d8e3d-119">När du skapar en utgående skräppostprincip i Security & Compliance Center skapar du faktiskt en utgående skräppostfilterregel och den tillhörande principen för skräppostfilter samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="d8e3d-120">När du ändrar en utgående skräppostprincip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter regeln för skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="d8e3d-121">Alla andra inställningar ändrar den associerade principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="d8e3d-122">När du tar bort en utgående skräppostprincip från Security & Compliance Center tas regeln för skräppostfilter och den tillhörande principen för skräppost från skräppost bort.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="d8e3d-123">I Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell är skillnaden mellan utgående skräppostfilterprinciper och utgående skräppostfilterregler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="d8e3d-124">Du hanterar principer för skräppostutgående skräppost med cmdlets \*\* \*-HostedContentFilterPolicy\*\* och du hanterar utgående skräppostfilterregler med hjälp av \*\* \*cmdlets -HostedContentFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="d8e3d-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="d8e3d-125">I PowerShell skapar du först principen för skräppostfilter och skapar först den utgående skräppostfilterregeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="d8e3d-126">I PowerShell ändrar du inställningarna i principen för skräppost och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="d8e3d-127">När du tar bort en utgående skräppostfilterprincip från PowerShell tas inte motsvarande utgående skräppostfilterregel automatiskt bort och vice versa.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="d8e3d-128">Standardpolicy för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-128">Default outbound spam policy</span></span>

<span data-ttu-id="d8e3d-129">Varje organisation har en inbyggd utgående skräppostprincip med namnet Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="d8e3d-130">Den utgående skräppostfilterprincipen Standard tillämpas på alla mottagare i organisationen, även om det inte finns någon regel för utgående skräppostfilter (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="d8e3d-131">Principen Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d8e3d-132">Alla anpassade principer som du skapar har alltid högre prioritet än principen Standard.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="d8e3d-133">Principen Standard är standardprincipen (egenskapen **IsDefault** har värdet) `True`och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d8e3d-134">Om du vill öka effektiviteten i skräppostfiltrering kan du skapa anpassade principer för skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d8e3d-135">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d8e3d-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d8e3d-136">Du öppnar Security & Compliance Center <https://protection.office.com/>på .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d8e3d-137">Om du vill gå direkt till <https://protection.office.com/antispam>sidan Inställningar för **skräppost** använder du .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="d8e3d-138">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d8e3d-139">Information om hur du ansluter till fristående Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d8e3d-140">Du måste tilldelas behörigheter innan du kan utföra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d8e3d-141">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d8e3d-142">För skrivskyddad åtkomst till principer för skräppost med utgående skräppost måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d8e3d-143">Mer information om rollgrupper i Security & Compliance Center finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d8e3d-144">Våra rekommenderade inställningar för utgående skräppostpolicyer finns i [EOP:s policyinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)för skräppostfilter .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="d8e3d-145">[Standardvarningsprinciperna](../../compliance/alert-policies.md) **e-postöverföringsgränsen överskred**, **Misstänkta e-postsändningsmönster har upptäckts**och användaren har begränsat till att **skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) om ovanlig utgående e-postaktivitet och blockerade användare på grund av utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="d8e3d-146">Mer information finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="d8e3d-147">Vi rekommenderar att du använder dessa aviseringsprinciper i stället för meddelandealternativen i principer för skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="d8e3d-148">Använd Security & Compliance Center för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="d8e3d-149">Om du skapar en anpassad utgående skräppostprincip i Security & Compliance Center skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d8e3d-150">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-151">Klicka på **Skapa en utgående princip**på sidan Inställningar för **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="d8e3d-152">Konfigurera följande inställningar i **principen För skräppostutgående skräppost** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d8e3d-153">**Namn**: Ange ett unikt, beskrivande namn för principen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d8e3d-154">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="d8e3d-155">(Valfritt) Expandera avsnittet **Meddelanden** om du vill konfigurera ytterligare användare som ska ta emot kopior och meddelanden om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="d8e3d-156">**Skicka en kopia av misstänkta utgående e-postmeddelanden till specifika personer:** Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="d8e3d-157">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-157">To enable this setting:</span></span>

     <span data-ttu-id="d8e3d-158">A.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-158">a.</span></span> <span data-ttu-id="d8e3d-159">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d8e3d-160">B.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-160">b.</span></span> <span data-ttu-id="d8e3d-161">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-161">Click **Add people**.</span></span> <span data-ttu-id="d8e3d-162">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d8e3d-163">C.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-163">c.</span></span> <span data-ttu-id="d8e3d-164">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-164">Enter the sender's email address.</span></span> <span data-ttu-id="d8e3d-165">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d8e3d-166">D.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-166">d.</span></span> <span data-ttu-id="d8e3d-167">Klicka</span><span class="sxs-lookup"><span data-stu-id="d8e3d-167">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d8e3d-169">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-169">to add the recipients.</span></span>

        <span data-ttu-id="d8e3d-170">Upprepa dessa steg så många gånger som behövs.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d8e3d-171">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d8e3d-172">Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d8e3d-173">ᵉ.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-173">e.</span></span> <span data-ttu-id="d8e3d-174">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d8e3d-175">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="d8e3d-176">**Meddela specifika personer om en avsändare blockeras på grund av att skicka skräppost som skickas:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="d8e3d-177">[Standardvarningsprincipen](../../compliance/alert-policies.md) **Användaren har begränsats från att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) när användare blockeras på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="d8e3d-178">Vi rekommenderar att du använder aviseringsprincipen i stället för den här inställningen i principen för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="d8e3d-179">Instruktioner finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="d8e3d-180">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-180">To enable this setting:</span></span>

     <span data-ttu-id="d8e3d-181">A.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-181">a.</span></span> <span data-ttu-id="d8e3d-182">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d8e3d-183">B.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-183">b.</span></span> <span data-ttu-id="d8e3d-184">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-184">Click **Add people**.</span></span> <span data-ttu-id="d8e3d-185">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d8e3d-186">C.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-186">c.</span></span> <span data-ttu-id="d8e3d-187">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-187">Enter the sender's email address.</span></span> <span data-ttu-id="d8e3d-188">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d8e3d-189">D.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-189">d.</span></span> <span data-ttu-id="d8e3d-190">Klicka</span><span class="sxs-lookup"><span data-stu-id="d8e3d-190">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d8e3d-192">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-192">to add the recipients.</span></span>

        <span data-ttu-id="d8e3d-193">Upprepa dessa steg så många gånger som behövs.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d8e3d-194">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d8e3d-195">Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d8e3d-196">ᵉ.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-196">e.</span></span> <span data-ttu-id="d8e3d-197">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d8e3d-198">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="d8e3d-199">(Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden: ]</span><span class="sxs-lookup"><span data-stu-id="d8e3d-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="d8e3d-200">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="d8e3d-201">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="d8e3d-202">Standardvärdet är 0, vilket innebär att tjänsten som standard används.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="d8e3d-203">Mer information finns i [Skicka gränser för Office 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="d8e3d-204">**Extern timgräns**: Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="d8e3d-205">**Intern timgräns**: Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="d8e3d-206">**Daglig gräns**: Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="d8e3d-207">**Åtgärd när en användare överskrider gränserna ovan**: Konfigurera åtgärden så att den vidtas när någon av **mottagarnas gränser** överskrids.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="d8e3d-208">För alla åtgärder får mottagarna som anges i **användaren begränsade från att skicka e-postaviseringsprincip** (och i den nu redundanta Meddela specifika personer om en **avsändare blockeras på grund av att skicka utgående skräppost** i principen för utgående skräppost får e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="d8e3d-209">**Begränsa användaren från att skicka e-post till följande dag:** Detta är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="d8e3d-210">E-postmeddelanden skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d8e3d-211">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="d8e3d-212">Aktivitetsaviseringen **Användaren har begränsats från att skicka e-post** meddelar administratörer (via e-post och på sidan **Visa aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="d8e3d-213">Alla mottagare som anges i **meddela specifika personer om en avsändare blockeras på grund av att skicka utgående skräppost** i policyn meddelas också.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="d8e3d-214">Användaren kommer inte att kunna skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d8e3d-215">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="d8e3d-216">**Begränsa användaren från att skicka e-post:** E-postmeddelanden skickas, användaren läggs till i portalen \*\*[Begränsade användare]<https://sip.protection.office.com/restrictedusers> \*\* i Security & Compliance Center och användaren kan inte skicka e-post förrän de har tagits bort från portalen **Begränsade användare** av en administratör. När en administratör har tagit bort användaren från listan begränsas användaren inte igen för den dagen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="d8e3d-217">Instruktioner finns i [Ta bort en användare från portalen Begränsade användare när](removing-user-from-restricted-users-portal-after-spam.md)du har skickat skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="d8e3d-218">**Ingen åtgärd, endast avisering:** E-postmeddelanden skickas.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="d8e3d-219">(Obligatoriskt) Expandera avsnittet **Tillämpat på** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="d8e3d-220">Du kan bara använda ett villkor eller ett undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d8e3d-221">Flera värden med samma villkor eller undantag använder ELLER-logik (till exempel _ \<sender1\> _ eller _ \<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="d8e3d-222">Olika villkor eller undantag använder AND-logik (till exempel _ \<sender1\> _ och _ \<medlem i grupp 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="d8e3d-223">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att se alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="d8e3d-224">Du kan ![klicka](../../media/scc-remove-icon.png) på Knappen Ta bort om du vill ta bort villkor som du inte vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="d8e3d-225">**Avsändarendomänen är**: Anger avsändare i en eller flera av de konfigurerade accepterade domänerna i Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="d8e3d-226">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="d8e3d-227">Klicka igen i rutan **Lägg till en tagg** om du vill välja ytterligare domäner om mer än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="d8e3d-228">**Avsändaren är**: Anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="d8e3d-229">Klicka i **lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d8e3d-230">Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d8e3d-231">**Avsändaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="d8e3d-232">Klicka i **lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d8e3d-233">Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d8e3d-234">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger för att se alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="d8e3d-235">Inställningarna och beteendet är precis som villkoren.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="d8e3d-236">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="d8e3d-237">Använda Security & Compliance Center för att visa principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="d8e3d-238">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-239">På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d8e3d-240">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d8e3d-241">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d8e3d-242">Principinställningarna visas i den utökade principinformation som visas eller så kan du klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="d8e3d-243">Använda Security & Compliance Center för att ändra principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="d8e3d-244">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-245">På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d8e3d-246">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d8e3d-247">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d8e3d-248">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-248">Click **Edit policy**.</span></span>

<span data-ttu-id="d8e3d-249">För anpassade principer för utgående skräppost är de tillgängliga inställningarna i det utfällbara resultatet som visas identiska med de som beskrivs i avsnittet [Använd säkerhets- & Compliance Center för att skapa utgående skräppostprinciper.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="d8e3d-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="d8e3d-250">För standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip**är avsnittet **Tillämpad** på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="d8e3d-251">Information om hur du aktiverar eller inaktiverar en princip anger du principprioritetsordningen eller konfigurerar karantänmeddelanden för slutanvändaren finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="d8e3d-252">Aktivera eller inaktivera principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="d8e3d-253">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-254">På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Expandera ikonen för att expandera en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d8e3d-255">Lägg märke till värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="d8e3d-256">Flytta växlingsknappen åt vänster för att inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-256">Move the toggle to the left to disable the policy:</span></span> ![Växla av](../../media/scc-toggle-off.png)

   <span data-ttu-id="d8e3d-258">Flytta växlingsknappen åt höger för att aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-258">Move the toggle to the right to enable the policy:</span></span> ![Växla på](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="d8e3d-260">Du kan inte inaktivera standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="d8e3d-261">Ange prioritet för anpassade principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="d8e3d-262">Som standard prioriteras principer för utgående skräppost som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d8e3d-263">Ett högre prioritetsnummer anger en högre prioritet för principen (0 är högst) och principer bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d8e3d-264">Inga två principer kan ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="d8e3d-265">Principer för anpassad skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d8e3d-266">Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="d8e3d-267">Om du vill ändra prioriteten för en princip flyttar du principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i säkerhets- & compliance center).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d8e3d-268">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-269">På sidan **Inställningar för skräppost** hittar du de principer där värdet i kolumnen **Typ** är policy för **anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="d8e3d-270">Lägg märke till värdena i kolumnen **Prioritet:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="d8e3d-271">Den anpassade utgående skräppostprincipen med ![högst prioritet](../../media/ITPro-EAC-DownArrowIcon.png) har värde nedåtpilen **ikon 0**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="d8e3d-272">Den anpassade utgående skräppostpolicyn med ![den lägsta](../../media/ITPro-EAC-UpArrowIcon.png) prioriteten har ![värdeupppilen **ikon n** (till exempel up arrow-ikonen](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="d8e3d-273">Om du har tre eller flera anpassade utgående skräppostprinciper har ![principerna](../../media/ITPro-EAC-UpArrowIcon.png)![mellan högsta](../../media/ITPro-EAC-DownArrowIcon.png) och lägsta prioritet värden ikon](../../media/ITPro-EAC-DownArrowIcon.png) nedåtpilen **ikon n** (till exempel ![nedåtpilens nedåtpil ikon](../../media/ITPro-EAC-UpArrowIcon.png)![ **2**).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="d8e3d-274">Klicka</span><span class="sxs-lookup"><span data-stu-id="d8e3d-274">Click</span></span> ![Ikon för Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="d8e3d-276">eller</span><span class="sxs-lookup"><span data-stu-id="d8e3d-276">or</span></span> ![Ikon för Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="d8e3d-278">om du vill flytta den anpassade principen för utgående skräppost uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="d8e3d-279">Använd Security & Compliance Center för att ta bort principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="d8e3d-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="d8e3d-280">Gå till **Policy** \> **Policy** \> **anti-spam**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="d8e3d-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d8e3d-281">På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Ikonen Expandera för att expandera den anpassade principen som du vill ta bort (kolumnen **Typ** är **principen Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d8e3d-282">Klicka på **Ta bort princip**i den utökade principinformationen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="d8e3d-283">Klicka på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d8e3d-284">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="d8e3d-285">Använda Exchange Online PowerShell eller Exchange Online Protection PowerShell för att konfigurera principer för skräppost för utgående information</span><span class="sxs-lookup"><span data-stu-id="d8e3d-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="d8e3d-286">Använda PowerShell för att skapa principer för skräppost än</span><span class="sxs-lookup"><span data-stu-id="d8e3d-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="d8e3d-287">Att skapa en utgående skräppostprincip i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d8e3d-288">Skapa principen för skräppostfiltrets utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="d8e3d-289">Skapa den utgående skräppostfilterregeln som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="d8e3d-290">**Anmärkningar:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-290">**Notes**:</span></span>

- <span data-ttu-id="d8e3d-291">Du kan skapa en ny regel för skräppostfilter och tilldela den en befintlig, oassocierad utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="d8e3d-292">En regel för skräppostfilter kan inte associeras med mer än en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="d8e3d-293">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d8e3d-294">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="d8e3d-295">Ange prioritet för principen när du skapar ( _ \<Prioritetsnummer\>_) på cmdleten **New-HostedOutboundSpamFilterRule).** _Priority_</span><span class="sxs-lookup"><span data-stu-id="d8e3d-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="d8e3d-296">En ny princip för skräppostfilter som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en skräppostfilterregel.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="d8e3d-297">Steg 1: Använd PowerShell för att skapa en utgående skräppostfilterprincip</span><span class="sxs-lookup"><span data-stu-id="d8e3d-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="d8e3d-298">Om du vill skapa en princip för skräppostfilter för att skapa ett utgående skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d8e3d-299">I det här exemplet skapas en ny utgående skräppostfilterprincip med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="d8e3d-300">Mottagarhastighetsgränserna är begränsade till mindre värden som standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="d8e3d-301">Mer information finns i [Skicka gränser för Office 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="d8e3d-302">När en av gränserna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="d8e3d-303">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="d8e3d-304">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="d8e3d-305">Om du vill skapa en regel för skräppostfilter kan du använda den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d8e3d-306">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="d8e3d-307">Den utgående skräppostfilterprincipen Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="d8e3d-308">Regeln gäller för medlemmar i gruppen Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="d8e3d-309">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="d8e3d-310">Använda PowerShell för att visa principer för skräppostutgående skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="d8e3d-311">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="d8e3d-312">Om du vill returnera detaljerad information om en specifik utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d8e3d-313">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterprincipen Chefer.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="d8e3d-314">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="d8e3d-315">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="d8e3d-316">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="d8e3d-317">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="d8e3d-318">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="d8e3d-319">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d8e3d-320">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d8e3d-321">Detaljerad syntax- och parameterinformation finns i [Hämta VärddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="d8e3d-322">Använda PowerShell för att ändra principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="d8e3d-323">Samma inställningar är tillgängliga när du ändrar en policy för skadlig kodfilter i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett utgående skräppostfilterprincipavsnitt](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="d8e3d-324">**Du**kan inte byta namn på en utgående skräppostfilterprincip (cmdleten **Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="d8e3d-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d8e3d-325">När du byter namn på en utgående skräppostprincip i Security & Compliance Center byter du bara namn på _regeln för_skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="d8e3d-326">Om du vill ändra en utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d8e3d-327">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="d8e3d-328">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="d8e3d-329">Den enda inställning som inte är tillgänglig när du ändrar en utgående skräppostfilterregel i PowerShell är parametern Aktiverad som gör att du kan skapa en _inaktiverad_ regel.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d8e3d-330">Information om hur du aktiverar eller inaktiverar befintliga regler för skräppostfilter finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="d8e3d-331">Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående skräppostfilterregel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="d8e3d-332">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett utgående skräppostfilterregelavsnitt](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d8e3d-333">Om du vill ändra en regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d8e3d-334">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="d8e3d-335">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="d8e3d-336">Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen om utgående skräppost (regeln för utgående skräppostfilter och den tilldelade principen för skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="d8e3d-337">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="d8e3d-338">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="d8e3d-339">I det här exemplet inaktiveras den utgående skräppostfilterregeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d8e3d-340">Det här exemplet aktiverar samma regel.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d8e3d-341">Detaljerad syntax- och parameterinformation finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) och [Inaktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="d8e3d-342">Använda PowerShell för att ange prioritet för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="d8e3d-343">Det högsta prioritetsvärdet som du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d8e3d-344">Det lägsta värdet du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d8e3d-345">Om du till exempel har fem regler kan du använda prioritetsvärdena 0 till och med 4.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d8e3d-346">Om du ändrar prioriteten för en befintlig regel kan det ha en kaskadeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d8e3d-347">Om du till exempel har fem anpassade regler (prioritet 0 till 4) och du ändrar prioriteten för en regel till 2, ändras den befintliga regeln med prioritet 2 till prioritet 3 och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d8e3d-348">Om du vill ange prioritet för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d8e3d-349">I det här exemplet anges prioriteten för regeln Marknadsavdelningen till 2.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-349">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d8e3d-350">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-350">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d8e3d-351">**Anmärkningar:**</span><span class="sxs-lookup"><span data-stu-id="d8e3d-351">**Notes**:</span></span>

- <span data-ttu-id="d8e3d-352">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **New-HostedOutboundSpamFilterRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="d8e3d-353">Principen för skräppostfilter för utgående har ingen motsvarande skräppostfilterregel och har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="d8e3d-354">Använda PowerShell för att ta bort principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="d8e3d-355">När du använder PowerShell för att ta bort en utgående skräppostfilterprincip tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="d8e3d-356">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d8e3d-357">I det här exemplet tas den utgående skräppostfilterprincipen marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d8e3d-358">Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="d8e3d-359">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="d8e3d-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="d8e3d-360">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande utgående skräppostfilterprincip bort.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="d8e3d-361">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="d8e3d-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="d8e3d-362">I det här exemplet tas den utgående skräppostfilterregeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="d8e3d-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d8e3d-363">Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="d8e3d-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="d8e3d-364">Mer information</span><span class="sxs-lookup"><span data-stu-id="d8e3d-364">For more information</span></span>

[<span data-ttu-id="d8e3d-365">Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-365">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="d8e3d-366">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="d8e3d-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="d8e3d-367">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="d8e3d-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
