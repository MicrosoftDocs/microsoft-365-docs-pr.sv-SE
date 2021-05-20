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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att visa, skapa, ändra och ta bort principer för utgående skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ead8aa75c0218dd2c4cad96e50e37ed3ddc12815
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583214"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="12f3a-103">Konfigurera utgående skräppostfiltrering i EOP</span><span class="sxs-lookup"><span data-stu-id="12f3a-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="12f3a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="12f3a-104">**Applies to**</span></span>
- [<span data-ttu-id="12f3a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="12f3a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="12f3a-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="12f3a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="12f3a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12f3a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="12f3a-108">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras automatiskt utgående e-postmeddelanden som skickas via EOP för aktivitet som skräppost och ovanlig sändning.</span><span class="sxs-lookup"><span data-stu-id="12f3a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="12f3a-109">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="12f3a-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="12f3a-110">Misstänkta utgående meddelanden märks som skräppost (oavsett konfidensnivå för skräppost eller SCL) och dirigeras genom högriskleveranspoolen för att skydda tjänstens rykte (det vill säga hålla [Microsoft 365-käll-e-postservrarna](high-risk-delivery-pool-for-outbound-messages.md) borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="12f3a-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="12f3a-111">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviseringsprinciper.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="12f3a-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="12f3a-112">EOP använder principer för utgående skräppost som en del av organisationens totala skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="12f3a-113">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="12f3a-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="12f3a-114">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="12f3a-115">För större detaljnivå kan du också skapa anpassade principer för utgående skräppost som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="12f3a-116">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="12f3a-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="12f3a-117">Du kan konfigurera principer för utgående skräppost i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="12f3a-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="12f3a-118">De grundläggande elementen i en princip för utgående skräppost i EOP är:</span><span class="sxs-lookup"><span data-stu-id="12f3a-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="12f3a-119">**Principen för utgående skräppostfilter:** Anger åtgärderna för utgående skräppostfiltrering av bedömningsutskick och aviseringsalternativen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="12f3a-120">**Regeln för utgående skräppostfilter:** Anger prioritet och mottagarfilter (som principen gäller för) för en princip för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="12f3a-121">Skillnaden mellan dessa två element är inte uppenbara när du hanterar utgående skräppost-faktorer i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="12f3a-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="12f3a-122">När du skapar en princip skapar du faktiskt en utgående skräppostfilterregel och samtidigt den associerade policyn för utgående skräppostfilter med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="12f3a-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="12f3a-123">När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverade eller inaktiverade samt mottagarfilter regeln för skräppostfilter för utgående trafik.</span><span class="sxs-lookup"><span data-stu-id="12f3a-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="12f3a-124">Alla andra inställningar ändrar den associerade policyn för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="12f3a-125">När du tar bort en princip tas regeln för utgående skräppostfilter och tillhörande princip för utgående skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="12f3a-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="12f3a-126">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="12f3a-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="12f3a-127">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) för att konfigurera principer för utgående skräppost längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="12f3a-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="12f3a-128">Alla organisationer har en inbyggd policy för utgående skräppost med namnet Standard, som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="12f3a-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="12f3a-129">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon utgående skräppostfilterregel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="12f3a-130">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="12f3a-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="12f3a-131">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="12f3a-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="12f3a-132">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="12f3a-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="12f3a-133">För att göra utgående skräppostfiltrering mer effektiv kan du skapa anpassade principer för utgående skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12f3a-134">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="12f3a-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="12f3a-135">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="12f3a-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="12f3a-136">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="12f3a-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="12f3a-137">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="12f3a-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="12f3a-138">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="12f3a-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="12f3a-139">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="12f3a-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="12f3a-140">Om du vill lägga till, ändra och ta bort utgående skräppostprinciper måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="12f3a-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="12f3a-141">För skrivskyddad åtkomst till principer för utgående skräppost måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="12f3a-142">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="12f3a-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > - <span data-ttu-id="12f3a-143">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12f3a-143">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="12f3a-144">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="12f3a-144">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > 
  > - <span data-ttu-id="12f3a-145">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-145">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="12f3a-146">Våra rekommenderade inställningar för principer för utgående skräppost finns i Principinställningar för [utgående skräppostfilter i EOP.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="12f3a-146">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="12f3a-147">Standardprinciperna för avisering med namnet Begränsning av e-postutskick har [](../../compliance/alert-policies.md) **överskridits,** mönster för misstänkta e-postutskick och Användaren har begränsats från att skicka e-post, som redan har skickat e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer) om ovanliga utgående e-postaktiviteter och blockerade användare på grund av utgående skräppost. </span><span class="sxs-lookup"><span data-stu-id="12f3a-147">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="12f3a-148">Mer information finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="12f3a-148">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="12f3a-149">Vi rekommenderar att du använder dessa aviseringsprinciper i stället för alternativen för meddelanden i principer för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-149">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="12f3a-150">Använd säkerhets- & för att skapa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-150">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="12f3a-151">När du skapar en anpassad utgående skräppostprincip i Säkerhets- och efterlevnadscenter för & skapas samtidigt skräppostfilterregeln och den tillhörande skräppostfilterprincipen med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="12f3a-151">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="12f3a-152">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-153">På sidan **Anti-spam settings** klickar du på **Create an outbound policy**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-153">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="12f3a-154">I **policyn för utgående skräppostfilter** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="12f3a-154">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="12f3a-155">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="12f3a-156">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-156">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="12f3a-157">(Valfritt) Expandera avsnittet **Meddelanden för** att konfigurera ytterligare användare som ska ta emot kopior och aviseringar om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="12f3a-157">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="12f3a-158">**Skicka en kopia av misstänkta utgående** e-postmeddelanden till vissa personer : Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.</span><span class="sxs-lookup"><span data-stu-id="12f3a-158">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="12f3a-159">Den här inställningen fungerar bara i standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-159">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="12f3a-160">Det fungerar inte i anpassade principer för utgående skräppost som du skapar.</span><span class="sxs-lookup"><span data-stu-id="12f3a-160">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="12f3a-161">Så här aktiverar du den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="12f3a-161">To enable this setting:</span></span>

     1. <span data-ttu-id="12f3a-162">Markera kryssrutan för att aktivera inställningen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-162">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="12f3a-163">Klicka **på Lägg till personer.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-163">Click **Add people**.</span></span> <span data-ttu-id="12f3a-164">I den **utfällna plats där Lägg till eller** ta bort mottagare visas:</span><span class="sxs-lookup"><span data-stu-id="12f3a-164">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="12f3a-165">Ange avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="12f3a-165">Enter the sender's email address.</span></span> <span data-ttu-id="12f3a-166">Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.</span><span class="sxs-lookup"><span data-stu-id="12f3a-166">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="12f3a-167">Klicka på</span><span class="sxs-lookup"><span data-stu-id="12f3a-167">Click</span></span> ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="12f3a-169">för att lägga till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="12f3a-169">to add the recipients.</span></span>

        <span data-ttu-id="12f3a-170">Upprepa de här stegen så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="12f3a-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="12f3a-171">De mottagare du lagt till visas i **avsnittet Mottagarlista** i den utfällade listrutan.</span><span class="sxs-lookup"><span data-stu-id="12f3a-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="12f3a-172">Om du vill ta bort en mottagare klickar du ![ på Knappen Ta ](../../media/scc-remove-icon.png) bort.</span><span class="sxs-lookup"><span data-stu-id="12f3a-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="12f3a-173">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="12f3a-173">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="12f3a-174">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="12f3a-174">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="12f3a-175">**Meddela specifika personer om en avsändare är blockerad på grund av utgående skräppost:**</span><span class="sxs-lookup"><span data-stu-id="12f3a-175">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="12f3a-176">Den här inställningen håller på att tas bort från policyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-176">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="12f3a-177">[Standardaviseringsprincipen](../../compliance/alert-policies.md)  med namnet Användare som inte kan skicka e-post skickar redan e-postmeddelanden till medlemmar i **gruppen TenantAdmins** (globala administratörer) när användare **blockeras** på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="12f3a-178">**Vi rekommenderar starkt att du använder aviseringsprincipen i stället** för den här inställningen i policyn för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-178">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="12f3a-179">Anvisningar finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="12f3a-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="12f3a-180">(Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="12f3a-180">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="12f3a-181">De här inställningarna gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="12f3a-181">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="12f3a-182">**Maximalt antal mottagare per användare**</span><span class="sxs-lookup"><span data-stu-id="12f3a-182">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="12f3a-183">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="12f3a-183">A valid value is 0 to 10000.</span></span> <span data-ttu-id="12f3a-184">Standardvärdet är 0, vilket betyder att tjänstens standardinställningar används.</span><span class="sxs-lookup"><span data-stu-id="12f3a-184">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="12f3a-185">Mer information finns i Skicka [begränsningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="12f3a-185">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="12f3a-186">**Gräns för extern timme:** Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="12f3a-186">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="12f3a-187">**Gräns för intern timme:** Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="12f3a-187">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="12f3a-188">**Daglig gräns:** Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="12f3a-188">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="12f3a-189">**Åtgärd när en användare överskrider gränserna ovan:** Konfigurera åtgärden som ska vidtas när någon av **mottagarbegränsningarna** överskrids.</span><span class="sxs-lookup"><span data-stu-id="12f3a-189">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="12f3a-190">För alla åtgärder anger mottagarna  i användarens princip för begränsad e-postavisering (och i den nu redundanta Informerar du vissa personer om en avsändare blockeras på grund av inställningen för utgående skräppost i principen för utgående skräppost får du e-postmeddelanden. </span><span class="sxs-lookup"><span data-stu-id="12f3a-190">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="12f3a-191">**Hindra användaren från att skicka e-post till följande** dag: Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="12f3a-191">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="12f3a-192">E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="12f3a-192">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="12f3a-193">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="12f3a-193">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="12f3a-194">Aktivitetsaviseringen med **namnet Användare begränsad från att skicka e-postmeddelanden** till administratörer (via e-post och på sidan **Visa** aviseringar).</span><span class="sxs-lookup"><span data-stu-id="12f3a-194">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="12f3a-195">Alla mottagare som anges i inställningen Meddela specifika personer om en avsändare blockeras på grund av att skicka **utgående** skräppost i principen meddelas också.</span><span class="sxs-lookup"><span data-stu-id="12f3a-195">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="12f3a-196">Användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="12f3a-196">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="12f3a-197">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="12f3a-197">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="12f3a-198">Hindra användaren från att skicka e-post: E-postaviseringar skickas, användaren läggs till på **portalen [Begränsade <https://sip.protection.office.com/restrictedusers> användare]** i säkerhets- och  efterlevnadscentret för & och användaren kan inte skicka e-post förrän han eller hon har tagits bort från portalen Begränsade användare av en administratör.  När en administratör tar bort användaren från listan begränsas inte användaren på nytt under den dagen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-198">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="12f3a-199">Instruktioner finns i Ta [bort en användare från portalen begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="12f3a-199">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="12f3a-200">**Ingen åtgärd, endast avisering:** E-postaviseringar skickas.</span><span class="sxs-lookup"><span data-stu-id="12f3a-200">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="12f3a-201">(Valfritt) Expandera **avsnittet Automatisk vidarebefordran** om du vill styra automatisk vidarebefordran av e-post av användare till externa avsändare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-201">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="12f3a-202">Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="12f3a-202">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="12f3a-203">Före september 2020 är de här inställningarna tillgängliga men inte tvingade.</span><span class="sxs-lookup"><span data-stu-id="12f3a-203">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="12f3a-204">De här inställningarna gäller endast för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="12f3a-204">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="12f3a-205">När automatisk vidarebefordran är inaktiverat får mottagaren en rapport om utebliven leverans (kallas även NDR-rapport eller icke-leveranskända meddelanden) om externa avsändare skickar e-post till en postlåda som har vidarebefordran på plats.</span><span class="sxs-lookup"><span data-stu-id="12f3a-205">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="12f3a-206">Om meddelandet skickas av en  intern avsändare och vidarebefordransmetoden är vidarebefordran av postlåda [(kallas](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) även SMTP-vidarebefordran) får den interna avsändaren NDR-meddelandet. </span><span class="sxs-lookup"><span data-stu-id="12f3a-206">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="12f3a-207">Den interna avsändaren får ingen NDR om vidarebefordran inträffade på grund av en inkorgsregel.</span><span class="sxs-lookup"><span data-stu-id="12f3a-207">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="12f3a-208">De tillgängliga värdena är:</span><span class="sxs-lookup"><span data-stu-id="12f3a-208">The available values are:</span></span>

   - <span data-ttu-id="12f3a-209">**Automatiskt – Systemkontrollerat:** Tillåter utgående skräppostfiltrering att styra automatisk extern vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="12f3a-209">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="12f3a-210">Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="12f3a-210">This is the default value.</span></span>
   - <span data-ttu-id="12f3a-211">**På:** Automatisk vidarebefordran av extern e-post är inte inaktiverat av principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-211">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="12f3a-212">**Av:** All automatisk vidarebefordran av extern e-post är inaktiverad enligt principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-212">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="12f3a-213">(Obligatoriskt) Expandera avsnittet **Används för** för att identifiera de interna avsändare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="12f3a-213">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="12f3a-214">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="12f3a-214">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="12f3a-215">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="12f3a-215">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="12f3a-216">Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="12f3a-216">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="12f3a-217">Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="12f3a-217">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="12f3a-218">Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="12f3a-218">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="12f3a-219">**Avsändardomänen** är: Anger avsändare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-219">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="12f3a-220">Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän.</span><span class="sxs-lookup"><span data-stu-id="12f3a-220">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="12f3a-221">Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="12f3a-221">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="12f3a-222">**Avsändaren är:** Anger en eller flera användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-222">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="12f3a-223">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="12f3a-223">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="12f3a-224">Klicka igen i **rutan Lägg till en** tagg om du vill välja fler avsändare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-224">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="12f3a-225">**Avsändaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-225">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="12f3a-226">Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="12f3a-226">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="12f3a-227">Klicka igen i **rutan Lägg till en** tagg om du vill välja fler avsändare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-227">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="12f3a-228">**Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag.</span><span class="sxs-lookup"><span data-stu-id="12f3a-228">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="12f3a-229">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="12f3a-229">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="12f3a-230">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="12f3a-230">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="12f3a-231">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att visa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-231">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="12f3a-232">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-233">På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera en policy för utgående skräppost:</span><span class="sxs-lookup"><span data-stu-id="12f3a-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="12f3a-234">Standardprincipen med namnet **Utgående skräppostfilterprincip.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="12f3a-235">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="12f3a-236">Principinställningarna visas i den utökade principinformationen som visas, eller så kan du klicka på **Redigera princip.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-236">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="12f3a-237">Använda säkerhets- & för att ändra principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-237">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="12f3a-238">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-239">På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera en policy för utgående skräppost:</span><span class="sxs-lookup"><span data-stu-id="12f3a-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="12f3a-240">Standardprincipen med namnet **Utgående skräppostfilterprincip.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="12f3a-241">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="12f3a-242">Klicka på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-242">Click **Edit policy**.</span></span>

<span data-ttu-id="12f3a-243">För anpassade principer för utgående skräppost är de tillgängliga inställningarna i den utfällsamma som beskrivs i avsnittet Use the Security & Compliance Center för att skapa [utgående](#use-the-security--compliance-center-to-create-outbound-spam-policies) skräppostprinciper.</span><span class="sxs-lookup"><span data-stu-id="12f3a-243">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="12f3a-244">I standardprincipen för utgående skräppost med  namnet Utgående skräppostfilter är avsnittet Används på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-244">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="12f3a-245">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="12f3a-245">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="12f3a-246">Aktivera eller inaktivera principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-246">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="12f3a-247">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-247">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-248">På sidan **Anti-spam settings klickar** du på Expand-ikonen för att expandera en anpassad princip som du skapat (värdet i kolumnen Typ är ![ Custom ](../../media/scc-expand-icon.png) **outbound spam policy**). </span><span class="sxs-lookup"><span data-stu-id="12f3a-248">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="12f3a-249">Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.</span><span class="sxs-lookup"><span data-stu-id="12f3a-249">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="12f3a-250">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="12f3a-250">Move the toggle to the left to disable the policy:</span></span> ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   <span data-ttu-id="12f3a-252">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="12f3a-252">Move the toggle to the right to enable the policy:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)

<span data-ttu-id="12f3a-254">Du kan inte inaktivera standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-254">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="12f3a-255">Ange prioritet för anpassade principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-255">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="12f3a-256">Som standard prioriteras principer för utgående skräppost utifrån den ordning de skapades (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="12f3a-256">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="12f3a-257">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="12f3a-257">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="12f3a-258">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="12f3a-258">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="12f3a-259">Anpassade principer för utgående skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="12f3a-259">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="12f3a-260">Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har prioritetsvärdet **Lägsta** och du kan inte ändra den.</span><span class="sxs-lookup"><span data-stu-id="12f3a-260">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="12f3a-261">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="12f3a-261">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="12f3a-262">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-263">På sidan **Anti-spam settings** hittar du principerna där värdet i kolumnen **Typ** är **Custom outbound spam policy**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-263">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="12f3a-264">Kontrollera värdena i kolumnen **Prioritet**:</span><span class="sxs-lookup"><span data-stu-id="12f3a-264">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="12f3a-265">Den anpassade policyn för utgående skräppost med högsta prioritet har värdet ![ nedåtpilikonen ](../../media/ITPro-EAC-DownArrowIcon.png) **0.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-265">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="12f3a-266">Den anpassade policyn för utgående skräppost med lägst prioritet har värdet ![ Uppåtpil ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel ![ Uppåtpil-ikonen ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**</span><span class="sxs-lookup"><span data-stu-id="12f3a-266">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="12f3a-267">Om du har tre eller fler anpassade principer för utgående skräppost har principerna mellan högsta och lägsta prioritet värdena Uppåtpil-ikonen Nedåtpil-ikon n (till exempel uppåtpilikonen Nedåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ikon ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**</span><span class="sxs-lookup"><span data-stu-id="12f3a-267">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="12f3a-268">Klicka på</span><span class="sxs-lookup"><span data-stu-id="12f3a-268">Click</span></span> ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="12f3a-270">eller</span><span class="sxs-lookup"><span data-stu-id="12f3a-270">or</span></span> ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="12f3a-272">för att flytta den anpassade policyn för utgående skräppost uppåt eller nedåt i prioritetslistan.</span><span class="sxs-lookup"><span data-stu-id="12f3a-272">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="12f3a-273">Använda Säkerhets- och & för att ta bort principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-273">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="12f3a-274">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-274">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="12f3a-275">På sidan **Anti-spam settings klickar** du på Expand icon för att expandera den anpassade princip som du vill ta bort (kolumnen Type är ![ Custom ](../../media/scc-expand-icon.png) **outbound spam policy**). </span><span class="sxs-lookup"><span data-stu-id="12f3a-275">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="12f3a-276">I den utökade principinformationen som visas klickar du på **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="12f3a-276">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="12f3a-277">Klicka på **Ja** i varningsrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="12f3a-277">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="12f3a-278">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="12f3a-278">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="12f3a-279">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-279">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="12f3a-280">Som tidigare beskrivits består en princip för utgående skräppost av en utgående skräppostfilterprincip och en regel för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-280">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="12f3a-281">I Exchange Online PowerShell eller fristående EOP PowerShell syns skillnaden mellan principer för utgående skräppostfilter och utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-281">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="12f3a-282">Du hanterar principer för utgående skräppostfilter med hjälp av cmdletarna **\* -HostedOutboundSpamFilterPolicy** och du hanterar filterregler för utgående skräppost med hjälp av cmdletarna **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-282">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="12f3a-283">I PowerShell skapar du först principen för utgående skräppostfilter och sedan skapar du den utgående skräppostfilterregeln som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="12f3a-283">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="12f3a-284">I PowerShell ändrar du inställningarna i filterprincipen för utgående skräppost och separat på filterregeln för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="12f3a-284">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="12f3a-285">När du tar bort en princip för utgående skräppostfilter från PowerShell tas inte motsvarande utgående skräppostfilterregel bort automatiskt, och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="12f3a-285">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="12f3a-286">Använda PowerShell för att skapa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="12f3a-287">Det krävs två steg för att skapa en princip för utgående skräppost i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12f3a-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="12f3a-288">Skapa policyn för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-288">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="12f3a-289">Skapa den utgående skräppostfilterregel som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="12f3a-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

> [!NOTE]
> - <span data-ttu-id="12f3a-290">Du kan skapa en ny regel för utgående skräppostfilter och tilldela en befintlig, oassocierad utgående skräppostfilterprincip till den.</span><span class="sxs-lookup"><span data-stu-id="12f3a-290">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="12f3a-291">En utgående skräppostfilterregel kan inte associeras med mer än en princip för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-291">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
> 
> - <span data-ttu-id="12f3a-292">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="12f3a-292">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="12f3a-293">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="12f3a-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
>   - <span data-ttu-id="12f3a-294">Ange prioritet för principen vid skapande (_Prioritet_ ) på _\<Number\>_ cmdleten **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="12f3a-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="12f3a-295">En ny utgående policy för skräppostfilter som du skapar i PowerShell visas inte i säkerhets- och efterlevnadscentret för & förrän du tilldelar principen till en regel för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-295">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="12f3a-296">Steg 1: Använda PowerShell för att skapa en princip för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-296">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="12f3a-297">Använd följande syntax för att skapa en princip för utgående skräppostfilter:</span><span class="sxs-lookup"><span data-stu-id="12f3a-297">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="12f3a-298">I det här exemplet skapas en ny policy för utgående skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="12f3a-298">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="12f3a-299">Mottagarens ratebegränsningar är begränsade till mindre värden som är standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="12f3a-299">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="12f3a-300">Mer information finns i Skicka [begränsningar över Microsoft 365 alternativ.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="12f3a-300">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="12f3a-301">När en av begränsningarna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="12f3a-301">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="12f3a-302">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="12f3a-302">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="12f3a-303">Steg 2: Använda PowerShell för att skapa en regel för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-303">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="12f3a-304">Använd följande syntax för att skapa en utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="12f3a-304">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="12f3a-305">I det här exemplet skapas en ny utgående skräppostfilterregel med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="12f3a-305">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="12f3a-306">Principen för utgående skräppostfilter med namnet Contoso Executives är kopplad till regeln.</span><span class="sxs-lookup"><span data-stu-id="12f3a-306">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="12f3a-307">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="12f3a-307">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="12f3a-308">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="12f3a-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="12f3a-309">Använda PowerShell för att visa principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-309">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="12f3a-310">Om du vill returnera en sammanfattning av alla principer för utgående skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="12f3a-310">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="12f3a-311">Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterprincip:</span><span class="sxs-lookup"><span data-stu-id="12f3a-311">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="12f3a-312">Det här exemplet returnerar alla egenskapsvärden för policyn för utgående skräppostfilter med namnet Chefer.</span><span class="sxs-lookup"><span data-stu-id="12f3a-312">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="12f3a-313">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="12f3a-313">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="12f3a-314">Använda PowerShell för att visa regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-314">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="12f3a-315">Om du vill visa befintliga regler för skräppostfilter för utgående trafik använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="12f3a-315">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="12f3a-316">Kör följande kommando för att returnera en sammanfattningslista över alla utgående skräppostfilterregler:</span><span class="sxs-lookup"><span data-stu-id="12f3a-316">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="12f3a-317">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="12f3a-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="12f3a-318">Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="12f3a-318">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="12f3a-319">Det här exemplet returnerar alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="12f3a-319">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="12f3a-320">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterRule.](/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="12f3a-320">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="12f3a-321">Använda PowerShell för att ändra principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-321">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="12f3a-322">Samma inställningar är tillgängliga när du ändrar en princip för skadlig programvara i PowerShell som när du skapar principen enligt beskrivningen i Steg [1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) Använda PowerShell för att skapa en princip för utgående skräppostfilter tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="12f3a-322">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="12f3a-323">Du kan inte byta namn på en utgående policy för skräppostfilter **(cmdleten Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="12f3a-323">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="12f3a-324">När du byter namn på en utgående skräppostprincip i Säkerhets- och & säkerhets- och efterlevnadscenter byter du bara namn på filterregeln för _utgående skräppost._</span><span class="sxs-lookup"><span data-stu-id="12f3a-324">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="12f3a-325">Använd följande syntax för att ändra en princip för utgående skräppostfilter:</span><span class="sxs-lookup"><span data-stu-id="12f3a-325">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="12f3a-326">Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="12f3a-326">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="12f3a-327">Använda PowerShell för att ändra regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-327">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="12f3a-328">Den enda inställningen som inte är tillgänglig när du ändrar en regel för utgående skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="12f3a-328">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="12f3a-329">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="12f3a-329">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="12f3a-330">Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en regel för utgående skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12f3a-330">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="12f3a-331">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg [2: Använd PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) för att skapa en utgående skräppostfilterregel tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="12f3a-331">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="12f3a-332">Använd följande syntax för att ändra en utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="12f3a-332">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="12f3a-333">Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterRule.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="12f3a-333">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="12f3a-334">Använda PowerShell för att aktivera eller inaktivera regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-334">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="12f3a-335">Om du aktiverar eller inaktiverar en utgående skräppostfilterregel i PowerShell aktiveras eller inaktiveras principen för hela den utgående skräpposten (regeln för utgående skräppostfilter och policyn för utgående skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="12f3a-335">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="12f3a-336">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="12f3a-336">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="12f3a-337">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="12f3a-337">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="12f3a-338">I det här exemplet inaktiveras regeln för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12f3a-338">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12f3a-339">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="12f3a-339">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12f3a-340">Detaljerad information om syntax och parametrar finns i [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [Disable-HostedOutboundSpamFilterRule.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="12f3a-340">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="12f3a-341">Använda PowerShell för att ange prioriteten för utgående skräppostfilterregler</span><span class="sxs-lookup"><span data-stu-id="12f3a-341">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="12f3a-342">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="12f3a-342">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="12f3a-343">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="12f3a-343">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="12f3a-344">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="12f3a-344">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="12f3a-345">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="12f3a-345">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="12f3a-346">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="12f3a-346">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="12f3a-347">Om du vill ange prioriteten för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="12f3a-347">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="12f3a-348">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="12f3a-348">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="12f3a-349">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="12f3a-349">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="12f3a-350">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i stället för cmdleten **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="12f3a-351">Standardprincipen för utgående skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid det omoderbara prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="12f3a-351">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="12f3a-352">Använda PowerShell för att ta bort principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-352">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="12f3a-353">När du använder PowerShell för att ta bort en princip för utgående skräppostfilter tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="12f3a-353">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="12f3a-354">Om du vill ta bort en princip för utgående skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="12f3a-354">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="12f3a-355">Det här exemplet tar bort policyn för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12f3a-355">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="12f3a-356">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="12f3a-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="12f3a-357">Använda PowerShell för att ta bort regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="12f3a-357">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="12f3a-358">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande princip för skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="12f3a-358">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="12f3a-359">Om du vill ta bort en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="12f3a-359">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="12f3a-360">Det här exemplet tar bort regeln för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="12f3a-360">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="12f3a-361">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterRule.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="12f3a-361">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="12f3a-362">Mer information</span><span class="sxs-lookup"><span data-stu-id="12f3a-362">For more information</span></span>

[<span data-ttu-id="12f3a-363">Ta bort blockerade användare från portalen med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="12f3a-363">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="12f3a-364">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="12f3a-364">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="12f3a-365">Vanliga frågor och svar om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="12f3a-365">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="12f3a-366">Rapporten Automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="12f3a-366">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)