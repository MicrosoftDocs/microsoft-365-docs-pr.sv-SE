---
title: Konfigurera utgående skräppostfiltrering
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
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa, skapa, ändra och ta bort utgående skräp post principer i Exchange Online Protection (EOP).
ms.openlocfilehash: ebeebe3486ad4dad926ad72509154904700e320a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949354"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="31fe3-103">Konfigurera utgående skräp post filtrering i EOP</span><span class="sxs-lookup"><span data-stu-id="31fe3-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="31fe3-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kontrol leras automatiskt utgående e-postmeddelanden som skickas via EOP för skräp post och ovanliga meddelanden.</span><span class="sxs-lookup"><span data-stu-id="31fe3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="31fe3-105">Utgående skräp post från en användare i din organisation indikerar vanligt vis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="31fe3-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="31fe3-106">Misstänkta utgående meddelanden markeras som skräp post (oavsett säkerhets nivån för skräp post eller SCL) och dirigeras via poolen med [hög risk](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill säga Microsoft 365 Source e-postservrar med IP-adressblock).</span><span class="sxs-lookup"><span data-stu-id="31fe3-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="31fe3-107">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviserings principer](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="31fe3-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="31fe3-108">EOP använder utgående spam-principer som en del av organisationens allmänna försvar mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="31fe3-109">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="31fe3-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="31fe3-110">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard princip för utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="31fe3-111">För högre precision kan du också skapa anpassade principer för utgående skräp post som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="31fe3-112">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="31fe3-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="31fe3-113">Du kan konfigurera regler för utgående skräp post i säkerhets & efterföljandekrav eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="31fe3-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="31fe3-114">De grundläggande delarna i en regel för utgående e-post i EOP är:</span><span class="sxs-lookup"><span data-stu-id="31fe3-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="31fe3-115">**Filter policy för utgående e-post**: anger åtgärderna för utgående spam-filtrering verdicts och meddelande alternativen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="31fe3-116">**Filter regeln för utgående e-post**: anger de prioritets-och mottagar filter (som principen gäller för) för en utgående filter policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="31fe3-117">Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående spam-principer i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="31fe3-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="31fe3-118">När du skapar en princip skapar du verkligen en utgående filter regel för skräp post och den associerade principen för skräp post filter samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="31fe3-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="31fe3-119">När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra regeln för utgående skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="31fe3-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="31fe3-120">Alla andra inställningar ändrar den associerade filtret för skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="31fe3-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="31fe3-121">När du tar bort en princip tas regeln för utgående skräp post bort och den associerade filtrerings principen för utgående e-post raderas.</span><span class="sxs-lookup"><span data-stu-id="31fe3-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="31fe3-122">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="31fe3-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="31fe3-123">Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera avsnittet för principer för skräp post](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="31fe3-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="31fe3-124">Varje organisation har inbyggd princip för skräp post som heter standard och har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="31fe3-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="31fe3-125">Principen tillämpas på alla användare i organisationen, även om det inte finns någon utgående filter regel (mottagar filter) som är kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="31fe3-126">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="31fe3-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="31fe3-127">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="31fe3-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="31fe3-128">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="31fe3-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="31fe3-129">Om du vill öka effektiviteten för utgående skräp post filtrering kan du skapa anpassade principer för utgående e-post med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="31fe3-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="31fe3-130">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="31fe3-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="31fe3-131">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="31fe3-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="31fe3-132">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="31fe3-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="31fe3-133">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="31fe3-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="31fe3-134">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="31fe3-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="31fe3-135">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="31fe3-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="31fe3-136">För att lägga till, ändra och ta bort principer för utgående skräp post måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="31fe3-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="31fe3-137">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="31fe3-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="31fe3-138">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="31fe3-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="31fe3-139">För skrivskyddad åtkomst till principer för utgående skräp post måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="31fe3-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="31fe3-140">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="31fe3-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="31fe3-141">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="31fe3-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="31fe3-142">De rekommenderade inställningarna för utgående skräp post finns i [EOP utgående filter princip inställningar för skräp post](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="31fe3-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="31fe3-143">Standard [aviserings principerna](../../compliance/alert-policies.md) med **begränsning för e-postutskick har överskridits**, **misstänkt e-post som skickar mönster**och **användare hindras från att skicka e-post** till medlemmar i gruppen **TenantAdmins** (**globala administratörer**) om ovanliga utgående e-postaktiviteter och blockerade användare på grund av utgående skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="31fe3-144">Mer information finns i [Verifiera aviserings inställningarna för användare med begränsad åtkomst](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="31fe3-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="31fe3-145">Vi rekommenderar att du använder dessa aviserings principer i stället för meddelande alternativen i principer för utgående skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="31fe3-146">Använda säkerhets & Compliance Center för att skapa principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="31fe3-147">Om du skapar en anpassad princip för utgående e-post i säkerhets & Compliance Center skapas skräp post filter regeln och den associerade skräp post filter principen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="31fe3-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="31fe3-148">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-149">På sidan **Inställningar för skräp post** klickar du på **skapa en utgående princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="31fe3-150">I **principen utgående skräp post filter** lägger du till följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="31fe3-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="31fe3-151">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="31fe3-152">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="31fe3-153">Skriver Expandera avsnittet **meddelanden** för att konfigurera ytterligare användare som ska få kopior och meddelanden om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="31fe3-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="31fe3-154">**Skicka en kopia av misstänkta utgående e-postmeddelanden till vissa personer**: den här inställningen lägger till angivna användare som hemlig kopia för de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="31fe3-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="31fe3-155">Den här inställningen fungerar bara i standard principen för utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="31fe3-156">Den fungerar inte i anpassade principer för utgående e-post som du skapar.</span><span class="sxs-lookup"><span data-stu-id="31fe3-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="31fe3-157">Så här aktiverar du inställningen:</span><span class="sxs-lookup"><span data-stu-id="31fe3-157">To enable this setting:</span></span>

     1. <span data-ttu-id="31fe3-158">Markera kryss rutan om du vill aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="31fe3-159">Klicka på **Lägg till personer**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-159">Click **Add people**.</span></span> <span data-ttu-id="31fe3-160">I **Lägg till eller ta bort** utfällda mottagare visas:</span><span class="sxs-lookup"><span data-stu-id="31fe3-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="31fe3-161">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="31fe3-161">Enter the sender's email address.</span></span> <span data-ttu-id="31fe3-162">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="31fe3-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="31fe3-163">Klicka på</span><span class="sxs-lookup"><span data-stu-id="31fe3-163">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="31fe3-165">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="31fe3-165">to add the recipients.</span></span>

        <span data-ttu-id="31fe3-166">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="31fe3-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="31fe3-167">Mottagarna som du lägger till visas i avsnittet **mottagar lista** på utfällda objekt.</span><span class="sxs-lookup"><span data-stu-id="31fe3-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="31fe3-168">Om du vill ta bort en mottagare klickar du på ![ knappen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="31fe3-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="31fe3-169">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="31fe3-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="31fe3-170">Om du vill inaktivera den här inställningen avmarkerar du kryss rutan.</span><span class="sxs-lookup"><span data-stu-id="31fe3-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="31fe3-171">**Meddela specifika personer om en avsändare blockeras på grund av inkommande skräp post**:</span><span class="sxs-lookup"><span data-stu-id="31fe3-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="31fe3-172">Den här inställningen används för att utgå från principer för utgående skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="31fe3-173">Standard [aviserings principen](../../compliance/alert-policies.md) med **användare som är begränsad från att skicka e-post skickar inte** e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**globala administratörer**) när användare blockeras på grund av begränsningarna i området för **mottagar gränser** .</span><span class="sxs-lookup"><span data-stu-id="31fe3-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="31fe3-174">**Vi rekommenderar starkt att du använder notifieringsregeln i stället för den här inställningen i principen för utgående skräp post för att meddela administratörer och andra användare**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="31fe3-175">Anvisningar finns i [Verifiera aviserings inställningarna för användare med begränsad](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)åtkomst.</span><span class="sxs-lookup"><span data-stu-id="31fe3-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="31fe3-176">Skriver Expandera avsnittet **mottagar gränser** för att konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="31fe3-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="31fe3-177">De här inställningarna gäller endast för molnbaserade post lådor.</span><span class="sxs-lookup"><span data-stu-id="31fe3-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="31fe3-178">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="31fe3-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="31fe3-179">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="31fe3-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="31fe3-180">Standardvärdet är 0, vilket innebär att tjänstens standardinställningar används.</span><span class="sxs-lookup"><span data-stu-id="31fe3-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="31fe3-181">Mer information finns i avsnittet om att [Skicka gränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="31fe3-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="31fe3-182">**Extern Tim gräns**: maximalt antal externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="31fe3-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="31fe3-183">**Intern gräns för varje timme**: det högsta antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="31fe3-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="31fe3-184">**Daglig gräns**: det högsta antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="31fe3-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="31fe3-185">**Åtgärd när en användare överskrider ovanstående gränser**: Konfigurera den åtgärd som ska vidtas när någon av de **mottagande gränserna** överskrids.</span><span class="sxs-lookup"><span data-stu-id="31fe3-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="31fe3-186">För alla åtgärder är mottagarna angivna i **användarens begränsade från att skicka e-** postaviserings princip (och i det **här meddelandet om att en avsändare har blockerats på grund av att den utgående skräp posten** avinstalleras.</span><span class="sxs-lookup"><span data-stu-id="31fe3-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="31fe3-187">**Hindra användaren från att skicka e-post till följande dag**: Detta är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="31fe3-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="31fe3-188">E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="31fe3-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="31fe3-189">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="31fe3-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="31fe3-190">Aktivitets aviseringen som heter **användare begränsad från att skicka e-post till** administratörer (via e-post och på sidan **Visa aviseringar** ).</span><span class="sxs-lookup"><span data-stu-id="31fe3-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="31fe3-191">Alla mottagare som anges i **meddela vissa personer om en avsändare blockeras på grund av utskick av utgående skräp post** i principen informeras också.</span><span class="sxs-lookup"><span data-stu-id="31fe3-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="31fe3-192">Användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="31fe3-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="31fe3-193">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="31fe3-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="31fe3-194">**Hindra användaren från att skicka e-post**: e-postaviseringar skickas, användaren läggs till i gruppen **[ <https://sip.protection.office.com/restrictedusers> begränsade användare]** i säkerhets & Compliance Center och användaren kan inte skicka e-post förrän de tas bort från portalen för **begränsade användare** av en administratör. När en administratör tar bort användaren från listan kommer användaren inte att begränsas till den dagen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="31fe3-195">Anvisningar finns i [ta bort en användare från portalen med begränsade användare när du skickar skräp post](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="31fe3-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="31fe3-196">**Ingen åtgärd, endast meddelande**: e-postaviseringar skickas.</span><span class="sxs-lookup"><span data-stu-id="31fe3-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="31fe3-197">Skriver Expandera avsnittet **Automatic Forwarding** för att styra automatisk vidarebefordran av e-post till externa avsändare.</span><span class="sxs-lookup"><span data-stu-id="31fe3-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="31fe3-198">Mer information om automatisk vidarebefordran finns i [Konfigurera e-postvidarekoppling](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="31fe3-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="31fe3-199">Före den september 2020 är de här inställningarna tillgängliga men inte tvingande.</span><span class="sxs-lookup"><span data-stu-id="31fe3-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="31fe3-200">De här inställningarna gäller endast för molnbaserade post lådor.</span><span class="sxs-lookup"><span data-stu-id="31fe3-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="31fe3-201">Automatisk vidarebefordran till interna mottagare påverkas inte av den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="31fe3-202">De tillgängliga värdena är:</span><span class="sxs-lookup"><span data-stu-id="31fe3-202">The available values are:</span></span>

   - <span data-ttu-id="31fe3-203">**Automatisk Systemstyrd**: tillåter utgående skräp post filtrering för automatisk överföring av externa e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="31fe3-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="31fe3-204">Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="31fe3-204">This is the default value.</span></span>

   - <span data-ttu-id="31fe3-205">**Den**: automatisk överföring av externa e-post är inte inaktive rad av principen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="31fe3-206">**Av**den här principen är inaktive rad för automatisk vidarebefordring av externa e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="31fe3-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="31fe3-207">Kunna Expandera avsnittet **används** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="31fe3-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="31fe3-208">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="31fe3-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="31fe3-209">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="31fe3-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="31fe3-210">Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="31fe3-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="31fe3-211">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="31fe3-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="31fe3-212">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="31fe3-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="31fe3-213">**Avsändarens domän är**: anger avsändare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="31fe3-214">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="31fe3-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="31fe3-215">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="31fe3-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="31fe3-216">**Avsändare är**: anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="31fe3-217">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="31fe3-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="31fe3-218">Klicka på rutan **Lägg till en tagg** för att välja fler avsändare.</span><span class="sxs-lookup"><span data-stu-id="31fe3-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="31fe3-219">**Avsändaren är medlem i**: anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="31fe3-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="31fe3-220">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="31fe3-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="31fe3-221">Klicka på rutan **Lägg till en tagg** för att välja fler avsändare.</span><span class="sxs-lookup"><span data-stu-id="31fe3-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="31fe3-222">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="31fe3-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="31fe3-223">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="31fe3-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="31fe3-224">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="31fe3-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="31fe3-225">Använd säkerhets & Compliance Center för att visa principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="31fe3-226">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-227">På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en princip för utgående skräp post:</span><span class="sxs-lookup"><span data-stu-id="31fe3-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="31fe3-228">Standard principen med namnet **utgående skräp post filter princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="31fe3-229">En anpassad princip som du skapade där värdet i kolumnen **Type** är anpassat för **utgående skräp post**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="31fe3-230">Princip inställningarna visas i den utökade princip informationen som visas, eller så kan du klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="31fe3-231">Använda inställningarna för säkerhets & efterlevnad för att ändra principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="31fe3-232">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-233">På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en princip för utgående skräp post:</span><span class="sxs-lookup"><span data-stu-id="31fe3-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="31fe3-234">Standard principen med namnet **utgående skräp post filter princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="31fe3-235">En anpassad princip som du skapade där värdet i kolumnen **Type** är anpassat för **utgående skräp post**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="31fe3-236">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-236">Click **Edit policy**.</span></span>

<span data-ttu-id="31fe3-237">För anpassade principer för utgående e-post är de tillgängliga inställningarna i utfällning som visas identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa regler för utgående skräp post](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="31fe3-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="31fe3-238">För den utgående standardinställningen för skräp post **filtrerings**principen är alternativet **tillämpa på** inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="31fe3-239">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="31fe3-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="31fe3-240">Aktivera och inaktivera principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="31fe3-241">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-242">På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en anpassad princip som du har skapat (värdet i kolumnen **Type** är **anpassad princip för utgående skräp post**).</span><span class="sxs-lookup"><span data-stu-id="31fe3-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="31fe3-243">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="31fe3-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="31fe3-244">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="31fe3-244">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="31fe3-246">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="31fe3-246">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="31fe3-248">Det går inte att inaktivera standard principen för utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="31fe3-249">Ange prioritet för anpassade principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="31fe3-250">Som standard ges principer för utgående skräp post en prioritet som baseras på den ordning de skapades (nyare policys är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="31fe3-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="31fe3-251">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="31fe3-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="31fe3-252">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="31fe3-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="31fe3-253">Anpassade principer för utgående skräp post visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="31fe3-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="31fe3-254">Standardvärdet för utgående skräp post **filtrerings princip** har värdet **lägst**och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="31fe3-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="31fe3-255">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="31fe3-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="31fe3-256">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-257">Leta reda på de principer där värdet i kolumnen **typ** är **anpassat för utgående skräp post**på sidan **Inställningar för skräp post** .</span><span class="sxs-lookup"><span data-stu-id="31fe3-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="31fe3-258">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="31fe3-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="31fe3-259">Den anpassade principen för utgående skräp post med den högsta prioriteten har ikonen för värde ![ nedpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="31fe3-260">Den anpassade principen för utgående skräp post med lägst prioritet har ![ ikonen för värde uppåt ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel uppåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="31fe3-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="31fe3-261">Om du har tre eller fler anpassade principer för utgående e-post har principerna mellan den högsta och lägsta prioriteten ikonen för att hålla ned en nedåtpil (till exempel ikonen nedåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="31fe3-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="31fe3-262">Klicka på</span><span class="sxs-lookup"><span data-stu-id="31fe3-262">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="31fe3-264">eller</span><span class="sxs-lookup"><span data-stu-id="31fe3-264">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="31fe3-266">för att flytta den anpassade principen för utgående skräp post uppåt eller nedåt i prioritets listan.</span><span class="sxs-lookup"><span data-stu-id="31fe3-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="31fe3-267">Använda tjänsten säkerhets & efterlevnad för att ta bort principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="31fe3-268">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="31fe3-269">På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera den anpassade princip som du vill ta bort (kolumnen **Type** är **anpassad princip för utgående skräp post**).</span><span class="sxs-lookup"><span data-stu-id="31fe3-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="31fe3-270">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="31fe3-271">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="31fe3-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="31fe3-272">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="31fe3-273">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="31fe3-274">Som du redan har beskrivit innehåller en utgående skräp post princip och en regel för utgående skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="31fe3-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="31fe3-275">I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan utgående filter principer för skräp post och filter regler för utgående e-post synlig.</span><span class="sxs-lookup"><span data-stu-id="31fe3-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="31fe3-276">Du hanterar principer för utgående skräp post filter genom att använda cmdletarna \*\* \* -HostedOutboundSpamFilterPolicy\*\* och du hanterar utgående filter regler för skräp post genom att använda cmdlet \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="31fe3-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="31fe3-277">I PowerShell skapar du principen för utgående skräp post filter först och sedan skapar du regeln för utgående skräp post filter som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="31fe3-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="31fe3-278">I PowerShell ändrar du inställningarna för filtrering av skräp post filter och regeln för utgående skräp post filter separat.</span><span class="sxs-lookup"><span data-stu-id="31fe3-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="31fe3-279">När du tar bort en regel för utgående skräp post från PowerShell tas den motsvarande filtret för skräp post filter inte bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="31fe3-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="31fe3-280">Använda PowerShell för att skapa regler för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="31fe3-281">Det är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="31fe3-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="31fe3-282">Skapa filtret för utgående skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="31fe3-283">Skapa filter regeln för utgående e-post som anger vilken regel för utgående skräp post som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="31fe3-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="31fe3-284">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="31fe3-284">**Notes**:</span></span>

- <span data-ttu-id="31fe3-285">Du kan skapa en ny regel för utgående skräp post filter och koppla en befintlig, otilldelad filter princip för utgående e-post till den.</span><span class="sxs-lookup"><span data-stu-id="31fe3-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="31fe3-286">En regel för utgående skräp post kan inte kopplas till fler än en utgående filter policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="31fe3-287">Du kan konfigurera följande inställningar på nya utgående filter principer för skräp post i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän efter att du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="31fe3-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="31fe3-288">Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-HostedOutboundSpamFilterRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="31fe3-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="31fe3-289">Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya HostedOutboundSpamFilterRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="31fe3-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="31fe3-290">En ny regel för utgående skräp post som du skapar i PowerShell visas inte i säkerhets & Compliance Center förrän du tilldelar principen till en skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="31fe3-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="31fe3-291">Steg 1: använda PowerShell för att skapa en utgående filter policy för skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="31fe3-292">Använd den här syntaxen om du vill skapa en regel för utgående skräp post filter:</span><span class="sxs-lookup"><span data-stu-id="31fe3-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="31fe3-293">I det här exemplet skapas en ny regel för utgående skräp post som heter Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="31fe3-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="31fe3-294">Värdet för mottagarens hastighet är begränsat till lägre värden.</span><span class="sxs-lookup"><span data-stu-id="31fe3-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="31fe3-295">Mer information finns i [Skicka begränsningar mellan Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="31fe3-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="31fe3-296">När en av gränserna nås förhindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="31fe3-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="31fe3-297">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31fe3-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="31fe3-298">Steg 2: använda PowerShell för att skapa en regel för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="31fe3-299">Om du vill skapa en regel för utgående skräp post använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="31fe3-300">I det här exemplet skapas en ny regel för utgående skräp post som heter Contoso Executives med dessa inställningar:</span><span class="sxs-lookup"><span data-stu-id="31fe3-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="31fe3-301">Filtret för utgående skräp post som heter Contoso-chefer är associerat med regeln.</span><span class="sxs-lookup"><span data-stu-id="31fe3-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="31fe3-302">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="31fe3-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="31fe3-303">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="31fe3-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="31fe3-304">Använda PowerShell för att visa filter principer för utgående e-post</span><span class="sxs-lookup"><span data-stu-id="31fe3-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="31fe3-305">Kör det här kommandot för att returnera en sammanfattande lista över alla filter principer för utgående e-post:</span><span class="sxs-lookup"><span data-stu-id="31fe3-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="31fe3-306">Använd den här syntaxen om du vill returnera detaljerad information om en viss regel för utgående skräp post filter:</span><span class="sxs-lookup"><span data-stu-id="31fe3-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="31fe3-307">I det här exemplet returneras alla egenskaps värden för principen utgående skräp post filter med namnet chefer.</span><span class="sxs-lookup"><span data-stu-id="31fe3-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="31fe3-308">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31fe3-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="31fe3-309">Använda PowerShell för att visa regler för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="31fe3-310">Om du vill visa befintliga regler för skräp post filter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="31fe3-311">Om du vill returnera en sammanfattnings lista över alla regler för utgående skräp post filter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="31fe3-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="31fe3-312">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="31fe3-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="31fe3-313">Om du vill returnera detaljerad information om en viss regel för utgående skräp post filter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="31fe3-314">I det här exemplet returneras alla egenskaps värden för regel regeln för utgående e-post som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="31fe3-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="31fe3-315">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="31fe3-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="31fe3-316">Använda PowerShell för att ändra principer för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="31fe3-317">Samma inställningar är tillgängliga när du ändrar en filter princip för skadlig kod i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: använda PowerShell för att skapa en regel för utgående skräp post filter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="31fe3-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="31fe3-318">Du kan inte byta namn på en filter princip för utgående e-post (cmdleten **set-HostedOutboundSpamFilterPolicy** , saknar _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="31fe3-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="31fe3-319">När du byter namn på en utgående skräp post policy i säkerhets & Compliance Center byter du bara namn på _regeln_för utgående skräp post filter.</span><span class="sxs-lookup"><span data-stu-id="31fe3-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="31fe3-320">Om du vill ändra en regel för utgående skräp post använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="31fe3-321">Detaljerad information om syntax och parametrar finns i [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31fe3-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="31fe3-322">Använda PowerShell för att ändra regler för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="31fe3-323">Den enda inställning som inte är tillgänglig när du ändrar en utgående regel för skräp post filter i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="31fe3-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="31fe3-324">Information om hur du aktiverar eller inaktiverar befintliga regler för skräp post filter finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="31fe3-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="31fe3-325">Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående filter regel för skräp post i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31fe3-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="31fe3-326">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en utgående filter regel för skräp post](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="31fe3-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="31fe3-327">Om du vill ändra en regel för utgående skräp post använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="31fe3-328">Detaljerad information om syntax och parametrar finns i [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="31fe3-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="31fe3-329">Använda PowerShell för att aktivera eller inaktivera regler för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="31fe3-330">När du aktiverar eller inaktiverar en regel för utgående skräp post i PowerShell aktive ras eller inaktive ras hela principen för utgående skräp post (regeln för utgående skräp post filter och den kopplade filter principen för utgående e-post).</span><span class="sxs-lookup"><span data-stu-id="31fe3-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="31fe3-331">Du kan inte aktivera eller inaktivera standard principen för utgående skräp post (det gäller alltid alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="31fe3-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="31fe3-332">Använd den här syntaxen om du vill aktivera eller inaktivera en regel för utgående skräp post filter i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31fe3-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="31fe3-333">I det här exemplet inaktive ras filter regeln för utgående skräp post.</span><span class="sxs-lookup"><span data-stu-id="31fe3-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="31fe3-334">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="31fe3-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="31fe3-335">Detaljerad information om syntax och parametrar finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="31fe3-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="31fe3-336">Använda PowerShell för att ställa in prioriteten för utgående skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="31fe3-337">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="31fe3-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="31fe3-338">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="31fe3-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="31fe3-339">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="31fe3-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="31fe3-340">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="31fe3-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="31fe3-341">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="31fe3-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="31fe3-342">Om du vill ange prioritet för en regel för utgående skräp post i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="31fe3-343">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="31fe3-343">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="31fe3-344">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="31fe3-344">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="31fe3-345">Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-HostedOutboundSpamFilterRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="31fe3-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="31fe3-346">Standard policyn för skräp post filter har ingen motsvarande filter regel för skräp post, och den har alltid det värde som är **lägst**.</span><span class="sxs-lookup"><span data-stu-id="31fe3-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="31fe3-347">Använda PowerShell för att ta bort principer för skräp post filter</span><span class="sxs-lookup"><span data-stu-id="31fe3-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="31fe3-348">När du använder PowerShell för att ta bort en regel för utgående skräp post tas den motsvarande regeln för skräp post filter inte bort.</span><span class="sxs-lookup"><span data-stu-id="31fe3-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="31fe3-349">Använd den här syntaxen om du vill ta bort en regel för utgående skräp post i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31fe3-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="31fe3-350">Det här exemplet tar bort filtret för utgående skräp post som heter marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="31fe3-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="31fe3-351">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31fe3-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="31fe3-352">Använda PowerShell för att ta bort regler för utgående skräp post</span><span class="sxs-lookup"><span data-stu-id="31fe3-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="31fe3-353">När du använder PowerShell för att ta bort en regel för utgående skräp post tas inte motsvarande filter policy för utgående e-post bort.</span><span class="sxs-lookup"><span data-stu-id="31fe3-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="31fe3-354">Om du vill ta bort en regel för utgående skräp post i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="31fe3-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="31fe3-355">I det här exemplet tas regeln för utgående skräp post bort med namnet marknadsförings avdelning.</span><span class="sxs-lookup"><span data-stu-id="31fe3-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="31fe3-356">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="31fe3-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="31fe3-357">Mer information</span><span class="sxs-lookup"><span data-stu-id="31fe3-357">For more information</span></span>

[<span data-ttu-id="31fe3-358">Ta bort blockerade användare från portalen med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="31fe3-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="31fe3-359">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="31fe3-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="31fe3-360">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="31fe3-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="31fe3-361">Rapporten Automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="31fe3-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
