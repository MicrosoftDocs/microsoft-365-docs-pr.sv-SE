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
description: Skräppostfiltrering är alltid aktiverat om du använder tjänsten för att skicka utgående e-post, vilket skyddar organisationer som använder tjänsten och deras avsedda mottagare.
ms.openlocfilehash: 699de94a300ac8625e92d2c467edd461d72c7d2f
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608180"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="3dec1-103">Konfigurera skräppostfiltrering utanför mängden i Office 365</span><span class="sxs-lookup"><span data-stu-id="3dec1-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="3dec1-104">Om du är office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor kontrolleras utgående e-postmeddelanden som skickas via EOP automatiskt efter skräppost och ovanlig sändningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="3dec1-105">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="3dec1-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="3dec1-106">Misstänkta utgående meddelanden markeras som skräppost (oavsett skräppostförtroendenivå eller SCL) och dirigeras genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill än att hålla e-postservrar för Office 365 borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="3dec1-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="3dec1-107">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [varningsprinciper](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3dec1-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="3dec1-108">EOP använder utgående skräppostpolicyer som en del av organisationens övergripande försvar mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="3dec1-109">Mer information finns i [Skydd mot skräppost i Office 365](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3dec1-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="3dec1-110">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="3dec1-111">För större granularitet kan du också skapa anpassade principer för skräppost som är tillämpliga på specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3dec1-112">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="3dec1-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3dec1-113">Du kan konfigurera principer för skräppost från utgående företag i Office 365 Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Office 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="3dec1-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="3dec1-114">Principer för utgående skräppost i Office 365 Security & Compliance Center vs Exchange Online PowerShell eller Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="3dec1-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="3dec1-115">De grundläggande inslagen i en utgående spam-policy i EOP är:</span><span class="sxs-lookup"><span data-stu-id="3dec1-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="3dec1-116">**Principen för skräppostfilter:** Anger åtgärder för utgående skräppostfiltreringsutslag och meddelandealternativen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="3dec1-117">**Regeln för skräppostfilter:** Anger prioritets- och mottagarfilter (vem principen gäller för) för en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="3dec1-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="3dec1-118">Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för utgående skräppost i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="3dec1-118">The difference between these two elements isn't obvious when you manage outbound spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3dec1-119">När du skapar en utgående skräppostprincip i Security & Compliance Center skapar du faktiskt en utgående skräppostfilterregel och den tillhörande principen för skräppostfilter samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="3dec1-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="3dec1-120">När du ändrar en utgående skräppostprincip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter regeln för skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="3dec1-121">Alla andra inställningar ändrar den associerade principen för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="3dec1-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="3dec1-122">När du tar bort en utgående skräppostprincip från Security & Compliance Center tas regeln för skräppostfilter och den tillhörande principen för skräppost från skräppost bort.</span><span class="sxs-lookup"><span data-stu-id="3dec1-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="3dec1-123">I Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell är skillnaden mellan utgående skräppostfilterprinciper och utgående skräppostfilterregler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="3dec1-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="3dec1-124">Du hanterar principer för skräppostutgående skräppost med cmdlets \*\* \*-HostedContentFilterPolicy\*\* och du hanterar utgående skräppostfilterregler med hjälp av \*\* \*cmdlets -HostedContentFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="3dec1-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="3dec1-125">I PowerShell skapar du först principen för skräppostfilter och skapar först den utgående skräppostfilterregeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="3dec1-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="3dec1-126">I PowerShell ändrar du inställningarna i principen för skräppost och regeln för skräppostfilter separat.</span><span class="sxs-lookup"><span data-stu-id="3dec1-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="3dec1-127">När du tar bort en utgående skräppostfilterprincip från PowerShell tas inte motsvarande utgående skräppostfilterregel automatiskt bort och vice versa.</span><span class="sxs-lookup"><span data-stu-id="3dec1-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="3dec1-128">Standardpolicy för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="3dec1-128">Default outbound spam policy</span></span>

<span data-ttu-id="3dec1-129">Varje organisation har en inbyggd utgående skräppostprincip med namnet Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="3dec1-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="3dec1-130">Den utgående skräppostfilterprincipen Standard tillämpas på alla mottagare i organisationen, även om det inte finns någon regel för utgående skräppostfilter (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="3dec1-131">Principen med namnet Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="3dec1-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3dec1-132">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="3dec1-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="3dec1-133">Principen som heter Standard är standardprincipen (egenskapen **IsDefault** har värdet `True`), och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3dec1-134">Om du vill öka effektiviteten i skräppostfiltrering kan du skapa anpassade principer för skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="3dec1-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3dec1-135">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="3dec1-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3dec1-136">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3dec1-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3dec1-137">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="3dec1-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="3dec1-138">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3dec1-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3dec1-139">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3dec1-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3dec1-140">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="3dec1-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3dec1-141">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="3dec1-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="3dec1-142">För skrivskyddad åtkomst till principer för skräppost med utgående skräppost måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="3dec1-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="3dec1-143">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3dec1-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3dec1-144">Våra rekommenderade inställningar för utgående skräppostpolicyer finns i [EOP:s policyinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)för skräppostfilter .</span><span class="sxs-lookup"><span data-stu-id="3dec1-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="3dec1-145">[Standardvarningsprinciperna](../../compliance/alert-policies.md) **e-postöverföringsgränsen överskred**, **Misstänkta e-postsändningsmönster har upptäckts**och användaren har begränsat till att **skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) om ovanlig utgående e-postaktivitet och blockerade användare på grund av utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="3dec1-146">Mer information finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="3dec1-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="3dec1-147">Vi rekommenderar att du använder dessa aviseringsprinciper i stället för meddelandealternativen i principer för skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="3dec1-148">Använd Security & Compliance Center för att skapa principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="3dec1-149">Om du skapar en anpassad utgående skräppostprincip i Security & Compliance Center skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="3dec1-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3dec1-150">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-151">Klicka på **Skapa en utgående princip**på sidan Inställningar för **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="3dec1-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="3dec1-152">Konfigurera följande inställningar i **principen För skräppostutgående skräppost** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="3dec1-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3dec1-153">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3dec1-154">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="3dec1-155">(Valfritt) Expandera avsnittet **Meddelanden** om du vill konfigurera ytterligare användare som ska ta emot kopior och meddelanden om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="3dec1-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="3dec1-156">**Skicka en kopia av misstänkta utgående e-postmeddelanden till specifika personer:** Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="3dec1-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="3dec1-157">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-157">To enable this setting:</span></span>

     <span data-ttu-id="3dec1-158">a.</span><span class="sxs-lookup"><span data-stu-id="3dec1-158">a.</span></span> <span data-ttu-id="3dec1-159">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="3dec1-160">b.</span><span class="sxs-lookup"><span data-stu-id="3dec1-160">b.</span></span> <span data-ttu-id="3dec1-161">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-161">Click **Add people**.</span></span> <span data-ttu-id="3dec1-162">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="3dec1-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="3dec1-163">C.</span><span class="sxs-lookup"><span data-stu-id="3dec1-163">c.</span></span> <span data-ttu-id="3dec1-164">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="3dec1-164">Enter the sender's email address.</span></span> <span data-ttu-id="3dec1-165">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="3dec1-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="3dec1-166">D.</span><span class="sxs-lookup"><span data-stu-id="3dec1-166">d.</span></span> <span data-ttu-id="3dec1-167">Klicka på</span><span class="sxs-lookup"><span data-stu-id="3dec1-167">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="3dec1-169">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="3dec1-169">to add the recipients.</span></span>

        <span data-ttu-id="3dec1-170">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="3dec1-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="3dec1-171">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="3dec1-172">Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .</span><span class="sxs-lookup"><span data-stu-id="3dec1-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="3dec1-173">ᵉ.</span><span class="sxs-lookup"><span data-stu-id="3dec1-173">e.</span></span> <span data-ttu-id="3dec1-174">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="3dec1-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="3dec1-175">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="3dec1-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="3dec1-176">**Meddela specifika personer om en avsändare blockeras på grund av att skicka skräppost som skickas:**</span><span class="sxs-lookup"><span data-stu-id="3dec1-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="3dec1-177">[Standardvarningsprincipen](../../compliance/alert-policies.md) **Användaren har begränsats från att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) när användare blockeras på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="3dec1-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="3dec1-178">Vi rekommenderar att du använder aviseringsprincipen i stället för den här inställningen i principen för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="3dec1-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="3dec1-179">Instruktioner finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="3dec1-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="3dec1-180">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-180">To enable this setting:</span></span>

     <span data-ttu-id="3dec1-181">a.</span><span class="sxs-lookup"><span data-stu-id="3dec1-181">a.</span></span> <span data-ttu-id="3dec1-182">Markera kryssrutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="3dec1-183">b.</span><span class="sxs-lookup"><span data-stu-id="3dec1-183">b.</span></span> <span data-ttu-id="3dec1-184">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-184">Click **Add people**.</span></span> <span data-ttu-id="3dec1-185">I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**</span><span class="sxs-lookup"><span data-stu-id="3dec1-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="3dec1-186">C.</span><span class="sxs-lookup"><span data-stu-id="3dec1-186">c.</span></span> <span data-ttu-id="3dec1-187">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="3dec1-187">Enter the sender's email address.</span></span> <span data-ttu-id="3dec1-188">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="3dec1-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="3dec1-189">D.</span><span class="sxs-lookup"><span data-stu-id="3dec1-189">d.</span></span> <span data-ttu-id="3dec1-190">Klicka på</span><span class="sxs-lookup"><span data-stu-id="3dec1-190">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="3dec1-192">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="3dec1-192">to add the recipients.</span></span>

        <span data-ttu-id="3dec1-193">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="3dec1-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="3dec1-194">Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="3dec1-195">Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .</span><span class="sxs-lookup"><span data-stu-id="3dec1-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="3dec1-196">ᵉ.</span><span class="sxs-lookup"><span data-stu-id="3dec1-196">e.</span></span> <span data-ttu-id="3dec1-197">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="3dec1-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="3dec1-198">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="3dec1-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="3dec1-199">(Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="3dec1-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="3dec1-200">Dessa inställningar gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="3dec1-200">These settings are only applicable to cloud-based mailboxes.</span></span>
     
   - <span data-ttu-id="3dec1-201">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="3dec1-201">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="3dec1-202">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="3dec1-202">A valid value is 0 to 10000.</span></span> <span data-ttu-id="3dec1-203">Standardvärdet är 0, vilket innebär att tjänsten som standard används.</span><span class="sxs-lookup"><span data-stu-id="3dec1-203">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="3dec1-204">Mer information finns i [Skicka gränser för Office 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="3dec1-204">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="3dec1-205">**Extern timgräns**: Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="3dec1-205">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="3dec1-206">**Intern timgräns**: Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="3dec1-206">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="3dec1-207">**Daglig gräns**: Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="3dec1-207">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="3dec1-208">**Åtgärd när en användare överskrider gränserna ovan**: Konfigurera åtgärden så att den vidtas när någon av **mottagarnas gränser** överskrids.</span><span class="sxs-lookup"><span data-stu-id="3dec1-208">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="3dec1-209">För alla åtgärder får mottagarna som anges i **användaren begränsade från att skicka e-postaviseringsprincip** (och i den nu redundanta Meddela specifika personer om en **avsändare blockeras på grund av att skicka utgående skräppost** i principen för utgående skräppost får e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="3dec1-209">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="3dec1-210">**Begränsa användaren från att skicka e-post till följande dag:** Detta är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-210">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="3dec1-211">E-postmeddelanden skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="3dec1-211">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3dec1-212">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="3dec1-212">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="3dec1-213">Aktivitetsaviseringen **Användaren har begränsats från att skicka e-post** meddelar administratörer (via e-post och på sidan **Visa aviseringar).**</span><span class="sxs-lookup"><span data-stu-id="3dec1-213">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="3dec1-214">Alla mottagare som anges i **meddela specifika personer om en avsändare blockeras på grund av att skicka utgående skräppost** i policyn meddelas också.</span><span class="sxs-lookup"><span data-stu-id="3dec1-214">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="3dec1-215">Användaren kommer inte att kunna skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="3dec1-215">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3dec1-216">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="3dec1-216">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="3dec1-217">**Begränsa användaren från att skicka e-post:** E-postmeddelanden skickas, användaren läggs till i portalen \*\*[Begränsade användare]<https://sip.protection.office.com/restrictedusers> \*\* i Security & Compliance Center och användaren kan inte skicka e-post förrän de har tagits bort från portalen **Begränsade användare** av en administratör. När en administratör har tagit bort användaren från listan begränsas användaren inte igen för den dagen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-217">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="3dec1-218">Instruktioner finns i [Ta bort en användare från portalen Begränsade användare när](removing-user-from-restricted-users-portal-after-spam.md)du har skickat skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-218">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="3dec1-219">**Ingen åtgärd, endast avisering:** E-postmeddelanden skickas.</span><span class="sxs-lookup"><span data-stu-id="3dec1-219">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="3dec1-220">(Obligatoriskt) Expandera avsnittet **Tillämpat på** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="3dec1-220">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="3dec1-221">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="3dec1-221">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3dec1-222">Flera värden med samma villkor eller undantag använder ELLER-logik (till exempel _ \<sender1\> _ eller _ \<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="3dec1-222">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="3dec1-223">Olika villkor eller undantag använder AND-logik (till exempel _ \<sender1\> _ och _ \<medlem i grupp 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3dec1-223">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="3dec1-224">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="3dec1-224">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="3dec1-225">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="3dec1-225">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="3dec1-226">**Avsändarendomänen är**: Anger avsändare i en eller flera av de konfigurerade accepterade domänerna i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3dec1-226">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="3dec1-227">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="3dec1-227">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="3dec1-228">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3dec1-228">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="3dec1-229">**Avsändaren är**: Anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-229">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="3dec1-230">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="3dec1-230">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3dec1-231">Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="3dec1-231">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3dec1-232">**Avsändaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-232">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="3dec1-233">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="3dec1-233">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3dec1-234">Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.</span><span class="sxs-lookup"><span data-stu-id="3dec1-234">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3dec1-235">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="3dec1-235">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="3dec1-236">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="3dec1-236">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="3dec1-237">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="3dec1-237">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="3dec1-238">Använda Security & Compliance Center för att visa principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-238">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="3dec1-239">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-240">På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="3dec1-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3dec1-241">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3dec1-242">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3dec1-243">Principinställningarna visas i den utökade principinformation som visas eller så kan du klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-243">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="3dec1-244">Använda Security & Compliance Center för att ändra principer för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-244">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="3dec1-245">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-245">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-246">På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:</span><span class="sxs-lookup"><span data-stu-id="3dec1-246">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3dec1-247">Standardprincipen **Utgående skräppostfilterprincip**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-247">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3dec1-248">En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-248">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3dec1-249">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-249">Click **Edit policy**.</span></span>

<span data-ttu-id="3dec1-250">För anpassade principer för utgående skräppost är de tillgängliga inställningarna i det utfällbara resultatet som visas identiska med de som beskrivs i avsnittet [Använd säkerhets- & Compliance Center för att skapa utgående skräppostprinciper.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="3dec1-250">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="3dec1-251">För standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip**är avsnittet **Tillämpad** på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-251">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3dec1-252">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="3dec1-252">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="3dec1-253">Aktivera eller inaktivera principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-253">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="3dec1-254">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-255">På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Expandera ikonen för att expandera en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="3dec1-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3dec1-256">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="3dec1-256">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="3dec1-257">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-257">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="3dec1-259">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-259">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="3dec1-261">Du kan inte inaktivera standardpolicyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-261">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="3dec1-262">Ange prioritet för anpassade principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-262">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="3dec1-263">Som standard prioriteras principer för utgående skräppost som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="3dec1-263">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3dec1-264">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="3dec1-264">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3dec1-265">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-265">No two policies can have the same priority.</span></span>

<span data-ttu-id="3dec1-266">Principer för anpassad skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="3dec1-266">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3dec1-267">Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="3dec1-267">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="3dec1-268">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="3dec1-268">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="3dec1-269">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-270">På sidan **Inställningar för skräppost** hittar du de principer där värdet i kolumnen **Typ** är policy för **anpassad utgående skräppost**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-270">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="3dec1-271">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="3dec1-271">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="3dec1-272">Den anpassade utgående skräppostprincipen med ![högst prioritet](../../media/ITPro-EAC-DownArrowIcon.png) har värde nedåtpilen **ikon 0**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-272">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="3dec1-273">Den anpassade utgående skräppostpolicyn med ![den lägsta](../../media/ITPro-EAC-UpArrowIcon.png) prioriteten har ![värdeupppilen **ikon n** (till exempel up arrow-ikonen](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="3dec1-273">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="3dec1-274">Om du har tre eller flera anpassade utgående skräppostprinciper har ![principerna](../../media/ITPro-EAC-UpArrowIcon.png)![mellan högsta](../../media/ITPro-EAC-DownArrowIcon.png) och lägsta prioritet värden ikon](../../media/ITPro-EAC-DownArrowIcon.png) nedåtpilen **ikon n** (till exempel ![nedåtpilens nedåtpil ikon](../../media/ITPro-EAC-UpArrowIcon.png)![ **2**).</span><span class="sxs-lookup"><span data-stu-id="3dec1-274">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="3dec1-275">Klicka på</span><span class="sxs-lookup"><span data-stu-id="3dec1-275">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="3dec1-277">eller</span><span class="sxs-lookup"><span data-stu-id="3dec1-277">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="3dec1-279">om du vill flytta den anpassade principen för utgående skräppost uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="3dec1-279">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="3dec1-280">Använd Security & Compliance Center för att ta bort principer för skräppost från utgående</span><span class="sxs-lookup"><span data-stu-id="3dec1-280">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="3dec1-281">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-281">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3dec1-282">På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Ikonen Expandera för att expandera den anpassade principen som du vill ta bort (kolumnen **Typ** är **principen Anpassad utgående skräppost**).</span><span class="sxs-lookup"><span data-stu-id="3dec1-282">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3dec1-283">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-283">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="3dec1-284">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="3dec1-284">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3dec1-285">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-285">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="3dec1-286">Använda Exchange Online PowerShell eller Exchange Online Protection PowerShell för att konfigurera principer för skräppost för utgående information</span><span class="sxs-lookup"><span data-stu-id="3dec1-286">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="3dec1-287">Använda PowerShell för att skapa principer för skräppost än</span><span class="sxs-lookup"><span data-stu-id="3dec1-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="3dec1-288">Att skapa en utgående skräppostprincip i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="3dec1-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3dec1-289">Skapa principen för skräppostfiltrets utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="3dec1-289">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="3dec1-290">Skapa den utgående skräppostfilterregeln som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="3dec1-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="3dec1-291">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="3dec1-291">**Notes**:</span></span>

- <span data-ttu-id="3dec1-292">Du kan skapa en ny regel för skräppostfilter och tilldela den en befintlig, oassocierad utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="3dec1-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="3dec1-293">En regel för skräppostfilter kan inte associeras med mer än en utgående skräppostfilterprincip.</span><span class="sxs-lookup"><span data-stu-id="3dec1-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="3dec1-294">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3dec1-295">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="3dec1-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="3dec1-296">Ange prioritet för principen när du skapar ( _ \<Prioritetsnummer\>_) på cmdleten **New-HostedOutboundSpamFilterRule).** _Priority_</span><span class="sxs-lookup"><span data-stu-id="3dec1-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="3dec1-297">En ny princip för skräppostfilter som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en skräppostfilterregel.</span><span class="sxs-lookup"><span data-stu-id="3dec1-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="3dec1-298">Steg 1: Använd PowerShell för att skapa en utgående skräppostfilterprincip</span><span class="sxs-lookup"><span data-stu-id="3dec1-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="3dec1-299">Om du vill skapa en princip för skräppostfilter för att skapa ett utgående skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3dec1-300">I det här exemplet skapas en ny utgående skräppostfilterprincip med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="3dec1-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="3dec1-301">Mottagarhastighetsgränserna är begränsade till mindre värden som standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="3dec1-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="3dec1-302">Mer information finns i [Skicka gränser för Office 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="3dec1-302">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="3dec1-303">När en av gränserna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="3dec1-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="3dec1-304">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3dec1-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="3dec1-305">Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="3dec1-306">Om du vill skapa en regel för skräppostfilter kan du använda den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3dec1-307">I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="3dec1-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="3dec1-308">Den utgående skräppostfilterprincipen Contoso Executives är associerad med regeln.</span><span class="sxs-lookup"><span data-stu-id="3dec1-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="3dec1-309">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="3dec1-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="3dec1-310">Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3dec1-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="3dec1-311">Använda PowerShell för att visa principer för skräppostutgående skräppost</span><span class="sxs-lookup"><span data-stu-id="3dec1-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="3dec1-312">Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="3dec1-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="3dec1-313">Om du vill returnera detaljerad information om en specifik utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3dec1-314">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterprincipen Chefer.</span><span class="sxs-lookup"><span data-stu-id="3dec1-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="3dec1-315">Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3dec1-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="3dec1-316">Använda PowerShell för att visa regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="3dec1-317">Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="3dec1-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="3dec1-318">Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="3dec1-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="3dec1-319">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="3dec1-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="3dec1-320">Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3dec1-321">I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="3dec1-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="3dec1-322">Detaljerad syntax- och parameterinformation finns i [Hämta VärddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3dec1-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="3dec1-323">Använda PowerShell för att ändra principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="3dec1-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="3dec1-324">Samma inställningar är tillgängliga när du ändrar en policy för skadlig kodfilter i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett utgående skräppostfilterprincipavsnitt](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="3dec1-325">**Du**kan inte byta namn på en utgående skräppostfilterprincip (cmdleten **Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="3dec1-325">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3dec1-326">När du byter namn på en utgående skräppostprincip i Security & Compliance Center byter du bara namn på _regeln för_skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="3dec1-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="3dec1-327">Om du vill ändra en utgående skräppostfilterprincip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3dec1-328">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3dec1-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="3dec1-329">Använda PowerShell för att ändra regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="3dec1-330">Den enda inställning som inte är tillgänglig när du ändrar en utgående skräppostfilterregel i PowerShell är parametern Aktiverad som gör att du kan skapa en _inaktiverad_ regel.</span><span class="sxs-lookup"><span data-stu-id="3dec1-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3dec1-331">Information om hur du aktiverar eller inaktiverar befintliga regler för skräppostfilter finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3dec1-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="3dec1-332">Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående skräppostfilterregel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dec1-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="3dec1-333">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett utgående skräppostfilterregelavsnitt](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3dec1-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="3dec1-334">Om du vill ändra en regel för skräppostfilter använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3dec1-335">Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3dec1-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="3dec1-336">Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="3dec1-337">Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen om utgående skräppost (regeln för utgående skräppostfilter och den tilldelade principen för skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="3dec1-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="3dec1-338">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="3dec1-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="3dec1-339">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="3dec1-340">I det här exemplet inaktiveras den utgående skräppostfilterregeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="3dec1-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3dec1-341">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="3dec1-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3dec1-342">Detaljerad syntax- och parameterinformation finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) och [Inaktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3dec1-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="3dec1-343">Använda PowerShell för att ange prioritet för regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="3dec1-344">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="3dec1-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3dec1-345">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="3dec1-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3dec1-346">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="3dec1-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3dec1-347">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="3dec1-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3dec1-348">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="3dec1-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3dec1-349">Om du vill ange prioritet för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="3dec1-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3dec1-350">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="3dec1-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="3dec1-351">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="3dec1-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3dec1-352">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="3dec1-352">**Notes**:</span></span>

- <span data-ttu-id="3dec1-353">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **New-HostedOutboundSpamFilterRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="3dec1-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="3dec1-354">Principen för skräppostfilter för utgående har ingen motsvarande skräppostfilterregel och har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="3dec1-354">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="3dec1-355">Använda PowerShell för att ta bort principer för skräppost från skräppost</span><span class="sxs-lookup"><span data-stu-id="3dec1-355">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="3dec1-356">När du använder PowerShell för att ta bort en utgående skräppostfilterprincip tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="3dec1-356">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="3dec1-357">Om du vill ta bort en princip för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-357">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3dec1-358">I det här exemplet tas den utgående skräppostfilterprincipen marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="3dec1-358">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3dec1-359">Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3dec1-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="3dec1-360">Använda PowerShell för att ta bort regler för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="3dec1-360">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="3dec1-361">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande utgående skräppostfilterprincip bort.</span><span class="sxs-lookup"><span data-stu-id="3dec1-361">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="3dec1-362">Om du vill ta bort en regel för skräppostfilter i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="3dec1-362">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="3dec1-363">I det här exemplet tas den utgående skräppostfilterregeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="3dec1-363">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3dec1-364">Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3dec1-364">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3dec1-365">Mer information</span><span class="sxs-lookup"><span data-stu-id="3dec1-365">For more information</span></span>

[<span data-ttu-id="3dec1-366">Ta bort blockerade användare från portalen med åtkomstbegränsade användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="3dec1-366">Remove blocked users from the Restricted Users portal in Office 365</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="3dec1-367">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="3dec1-367">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="3dec1-368">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="3dec1-368">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
