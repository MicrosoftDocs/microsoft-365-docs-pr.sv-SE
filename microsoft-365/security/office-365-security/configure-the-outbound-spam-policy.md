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
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822015"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="b02f4-103">Konfigurera utgående skräppostfiltrering i EOP</span><span class="sxs-lookup"><span data-stu-id="b02f4-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b02f4-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="b02f4-104">**Applies to**</span></span>
- [<span data-ttu-id="b02f4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b02f4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b02f4-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="b02f4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b02f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b02f4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b02f4-108">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras automatiskt utgående e-postmeddelanden som skickas via EOP för aktivitet som skräppost och ovanlig sändning.</span><span class="sxs-lookup"><span data-stu-id="b02f4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="b02f4-109">Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="b02f4-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="b02f4-110">Misstänkta utgående meddelanden märks som skräppost (oavsett konfidensnivå för skräppost eller SCL) och dirigeras genom högriskleveranspoolen för att skydda tjänstens rykte (det vill säga hålla [Microsoft 365-käll-e-postservrarna](high-risk-delivery-pool-for-outbound-messages.md) borta från IP-blockeringslistor).</span><span class="sxs-lookup"><span data-stu-id="b02f4-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="b02f4-111">Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviseringsprinciper.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b02f4-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="b02f4-112">EOP använder principer för utgående skräppost som en del av organisationens totala skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="b02f4-113">Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b02f4-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="b02f4-114">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="b02f4-115">För större detaljnivå kan du också skapa anpassade principer för utgående skräppost som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b02f4-116">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="b02f4-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b02f4-117">Du kan konfigurera principer för utgående skräppost i säkerhetscentret i Microsoft 365 eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="b02f4-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="b02f4-118">De grundläggande elementen i en princip för utgående skräppost i EOP är:</span><span class="sxs-lookup"><span data-stu-id="b02f4-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="b02f4-119">**Principen för utgående skräppostfilter:** Anger åtgärderna för utgående skräppostfiltrering av bedömningsutskick och aviseringsalternativen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="b02f4-120">**Regeln för utgående skräppostfilter:** Anger prioritet och mottagarfilter (som principen gäller för) för en princip för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="b02f4-121">Skillnaden mellan dessa två element är inte uppenbara när du hanterar utgående skräppost-faktorer på säkerhetscentret:</span><span class="sxs-lookup"><span data-stu-id="b02f4-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="b02f4-122">När du skapar en princip skapar du faktiskt en utgående skräppostfilterregel och samtidigt den associerade policyn för utgående skräppostfilter med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="b02f4-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b02f4-123">När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverade eller inaktiverade samt mottagarfilter regeln för skräppostfilter för utgående trafik.</span><span class="sxs-lookup"><span data-stu-id="b02f4-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="b02f4-124">Alla andra inställningar ändrar den associerade policyn för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="b02f4-125">När du tar bort en princip tas regeln för utgående skräppostfilter och tillhörande princip för utgående skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="b02f4-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="b02f4-126">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="b02f4-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b02f4-127">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) för att konfigurera principer för utgående skräppost längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b02f4-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="b02f4-128">Alla organisationer har en inbyggd policy för utgående skräppost med namnet Standard, som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="b02f4-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="b02f4-129">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon utgående skräppostfilterregel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="b02f4-130">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="b02f4-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b02f4-131">Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.</span><span class="sxs-lookup"><span data-stu-id="b02f4-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="b02f4-132">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="b02f4-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b02f4-133">För att göra utgående skräppostfiltrering mer effektiv kan du skapa anpassade principer för utgående skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="b02f4-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b02f4-134">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b02f4-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b02f4-135">Öppna Microsoft 365 Säkerhetscenter på <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="b02f4-135">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="b02f4-136">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://security.microsoft.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="b02f4-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="b02f4-137">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b02f4-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b02f4-138">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b02f4-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b02f4-139">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="b02f4-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b02f4-140">Om du vill lägga till, ändra och ta bort utgående skräppostprinciper måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="b02f4-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b02f4-141">För skrivskyddad åtkomst till principer för utgående skräppost måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b02f4-142">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="b02f4-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="b02f4-143">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="b02f4-143">**Notes**:</span></span>

  - <span data-ttu-id="b02f4-144">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b02f4-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b02f4-145">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b02f4-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="b02f4-146">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b02f4-147">Våra rekommenderade inställningar för principer för utgående skräppost finns i Principinställningar för [utgående skräppostfilter i EOP.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b02f4-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="b02f4-148">Standardprinciperna för avisering med namnet Begränsning av e-postutskick har [](../../compliance/alert-policies.md) **överskridits,** mönster för misstänkta e-postutskick och Användaren har begränsats från att skicka e-post, som redan har skickat e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer) om ovanliga utgående e-postaktiviteter och blockerade användare på grund av utgående skräppost. </span><span class="sxs-lookup"><span data-stu-id="b02f4-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="b02f4-149">Mer information finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="b02f4-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="b02f4-150">Vi rekommenderar att du använder dessa aviseringsprinciper i stället för alternativen för meddelanden i principer för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="b02f4-151">Använda säkerhetscentret för att skapa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="b02f4-152">När du skapar en anpassad utgående skräppostprincip i säkerhetscentret skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="b02f4-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b02f4-153">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-154">På sidan **Principer för skydd mot skräppost** klickar du på Skapa ikon Skapa ![ ](../../media/m365-cc-sc-create-icon.png) **princip** och väljer sedan **Utgående** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="b02f4-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="b02f4-155">Principguiden öppnas.</span><span class="sxs-lookup"><span data-stu-id="b02f4-155">The policy wizard opens.</span></span> <span data-ttu-id="b02f4-156">Konfigurera följande inställningar på **sidan Namnge principen**:</span><span class="sxs-lookup"><span data-stu-id="b02f4-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="b02f4-157">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="b02f4-158">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b02f4-159">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b02f4-160">På sidan **Användare, grupper och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="b02f4-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="b02f4-161">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b02f4-162">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="b02f4-163">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="b02f4-164">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="b02f4-165">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="b02f4-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="b02f4-166">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="b02f4-166">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="b02f4-168">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-168">next to the value.</span></span>

   <span data-ttu-id="b02f4-169">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="b02f4-170">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="b02f4-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="b02f4-171">Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor.</span><span class="sxs-lookup"><span data-stu-id="b02f4-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b02f4-172">Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.</span><span class="sxs-lookup"><span data-stu-id="b02f4-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="b02f4-173">**Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="b02f4-174">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="b02f4-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b02f4-175">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b02f4-176">Konfigurera **följande inställningar** på sidan Skyddsinställningar som öppnas:</span><span class="sxs-lookup"><span data-stu-id="b02f4-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="b02f4-177">**Meddelandegränser:** Inställningarna i det här avsnittet konfigurerar gränserna för utgående e-postmeddelanden **Exchange Online** postlådor:</span><span class="sxs-lookup"><span data-stu-id="b02f4-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="b02f4-178">**Ange en gräns för externa** meddelanden: Det maximala antalet externa mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="b02f4-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="b02f4-179">**Ange en gräns för interna** meddelanden: Det maximala antalet interna mottagare per timme.</span><span class="sxs-lookup"><span data-stu-id="b02f4-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="b02f4-180">**Ange en daglig meddelandegräns:** Det maximala totala antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="b02f4-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="b02f4-181">Ett giltigt värde är 0 till 10000.</span><span class="sxs-lookup"><span data-stu-id="b02f4-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="b02f4-182">Standardvärdet är 0, vilket betyder att tjänstens standardinställningar används.</span><span class="sxs-lookup"><span data-stu-id="b02f4-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="b02f4-183">Mer information finns i Skicka [begränsningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="b02f4-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="b02f4-184">Ange ett värde i rutan eller använd pilarna för att öka/minska i rutan.</span><span class="sxs-lookup"><span data-stu-id="b02f4-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="b02f4-185">**Begränsning som gjorts för användare som** når meddelandegränsen: Välj en åtgärd i  listrutan när någon av begränsningarna i avsnittet Skyddsinställningar överskrids.</span><span class="sxs-lookup"><span data-stu-id="b02f4-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="b02f4-186">För alla åtgärder får de  mottagare som angetts i användarens  inställning för begränsad e-postavisering (och i den nu redundanta aviseringen Meddela dessa användare och grupper om en avsändare blockeras på grund av att du skickat utgående skräppost senare på den här sidan) e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b02f4-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="b02f4-187">**Hindra användaren från att skicka e-post till följande** dag: Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="b02f4-188">E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="b02f4-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b02f4-189">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="b02f4-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="b02f4-190">Aktivitetsaviseringen med **namnet Användare begränsad från att skicka e-postmeddelanden** till administratörer (via e-post och på sidan **Visa** aviseringar).</span><span class="sxs-lookup"><span data-stu-id="b02f4-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="b02f4-191">Alla mottagare som anges i inställningen Meddela specifika personer om en avsändare blockeras på grund av att skicka **utgående** skräppost i principen meddelas också.</span><span class="sxs-lookup"><span data-stu-id="b02f4-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="b02f4-192">Användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid.</span><span class="sxs-lookup"><span data-stu-id="b02f4-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b02f4-193">Det finns inget sätt för administratören att åsidosätta det här blocket.</span><span class="sxs-lookup"><span data-stu-id="b02f4-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="b02f4-194">**Hindra** användaren från att skicka e-post: E-postaviseringar skickas, användaren läggs till i Begränsade användare i säkerhetscentret och användaren kan inte skicka e-post förrän han eller hon har tagits bort från Begränsade användare av en  <https://security.microsoft.com/restrictedusers> administratör.  När en administratör tar bort användaren från listan begränsas inte användaren på nytt under den dagen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="b02f4-195">Instruktioner finns i Ta [bort en användare från portalen begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="b02f4-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="b02f4-196">**Ingen åtgärd, endast avisering:** E-postaviseringar skickas.</span><span class="sxs-lookup"><span data-stu-id="b02f4-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="b02f4-197">**Regler för vidarebefordran:** Använd inställningarna i det här avsnittet för att styra automatisk vidarebefordran av **e Exchange Online postlådor** till externa avsändare.</span><span class="sxs-lookup"><span data-stu-id="b02f4-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="b02f4-198">Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="b02f4-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="b02f4-199">När automatisk vidarebefordran är inaktiverat får mottagaren en rapport om utebliven leverans (kallas även NDR-rapport eller icke-leveranskända meddelanden) om externa avsändare skickar e-post till en postlåda som har vidarebefordran på plats.</span><span class="sxs-lookup"><span data-stu-id="b02f4-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="b02f4-200">Om meddelandet skickas av en  intern avsändare och vidarebefordransmetoden är vidarebefordran av postlåda [(kallas](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) även SMTP-vidarebefordran) får den interna avsändaren NDR-meddelandet. </span><span class="sxs-lookup"><span data-stu-id="b02f4-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="b02f4-201">Den interna avsändaren får ingen NDR om vidarebefordran inträffade på grund av en inkorgsregel.</span><span class="sxs-lookup"><span data-stu-id="b02f4-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="b02f4-202">Välj någon av följande åtgärder i **listrutan Automatiska vidare** vidarebefordransregler:</span><span class="sxs-lookup"><span data-stu-id="b02f4-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="b02f4-203">**Automatiskt – Systemkontrollerat:** Tillåter utgående skräppostfiltrering att styra automatisk extern vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="b02f4-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="b02f4-204">Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-204">This is the default value.</span></span>
     - <span data-ttu-id="b02f4-205">**På:** Automatisk vidarebefordran av extern e-post är inte inaktiverat av principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="b02f4-206">**Av:** All automatisk vidarebefordran av extern e-post är inaktiverad enligt principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="b02f4-207">**Meddelanden:** Använd inställningarna i avsnittet för att konfigurera ytterligare mottagare som ska få kopior och aviseringar om misstänkta utgående e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="b02f4-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="b02f4-208">**Skicka en kopia av misstänkta utgående** e-postmeddelanden som överskrider dessa gränser för dessa användare och grupper: Den här inställningen lägger till de angivna mottagarna i fältet Hemlig kopia i misstänkta utgående meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b02f4-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="b02f4-209">Den här inställningen fungerar bara i standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="b02f4-210">Det fungerar inte i anpassade principer för utgående skräppost som du skapar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="b02f4-211">Markera kryssrutan om du vill aktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="b02f4-212">I rutan som visas klickar du i rutan, anger en giltig e-postadress och trycker sedan på Retur eller väljer det fullständiga värde som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="b02f4-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="b02f4-213">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="b02f4-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b02f4-214">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="b02f4-214">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="b02f4-216">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-216">next to the value.</span></span>

   - <span data-ttu-id="b02f4-217">**Meddela dessa användare och grupper om en avsändare är blockerad på grund av utgående skräppost**</span><span class="sxs-lookup"><span data-stu-id="b02f4-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="b02f4-218">Den här inställningen håller på att tas bort från policyn för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="b02f4-219">[Standardaviseringsprincipen](../../compliance/alert-policies.md)  med namnet Användare som inte kan skicka e-post skickar redan e-postmeddelanden till medlemmar i **gruppen TenantAdmins** (globala administratörer) när användare **blockeras** på grund av att de överskrider gränserna i avsnittet **Mottagargränser.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="b02f4-220">**Vi rekommenderar starkt att du använder aviseringsprincipen i stället** för den här inställningen i policyn för utgående skräppost för att meddela administratörer och andra användare.</span><span class="sxs-lookup"><span data-stu-id="b02f4-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="b02f4-221">Anvisningar finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="b02f4-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="b02f4-222">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b02f4-223">Granska inställningarna på sidan **Granska** som visas.</span><span class="sxs-lookup"><span data-stu-id="b02f4-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="b02f4-224">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="b02f4-225">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="b02f4-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="b02f4-226">Klicka på **Skapa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="b02f4-227">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="b02f4-228">Använda säkerhetscentret för att visa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="b02f4-229">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-230">På sidan **Princip för skräppostskydd** letar du efter något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="b02f4-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="b02f4-231">Värdet **för Type** är **Policyn för anpassad utgående skräppost**</span><span class="sxs-lookup"><span data-stu-id="b02f4-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="b02f4-232">**Namnvärdet** är **utgående policy mot skräppost (standard)**</span><span class="sxs-lookup"><span data-stu-id="b02f4-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="b02f4-233">Följande egenskaper visas i listan över principer för skräppostskydd:</span><span class="sxs-lookup"><span data-stu-id="b02f4-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="b02f4-234">**Namn**</span><span class="sxs-lookup"><span data-stu-id="b02f4-234">**Name**</span></span>
   - <span data-ttu-id="b02f4-235">**Status**</span><span class="sxs-lookup"><span data-stu-id="b02f4-235">**Status**</span></span>
   - <span data-ttu-id="b02f4-236">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="b02f4-236">**Priority**</span></span>
   - <span data-ttu-id="b02f4-237">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b02f4-237">**Type**</span></span>

3. <span data-ttu-id="b02f4-238">När du väljer en princip för utgående skräppost genom att klicka på namnet visas principinställningarna i en utfällmapp.</span><span class="sxs-lookup"><span data-stu-id="b02f4-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="b02f4-239">Använda säkerhetscentret för att ändra principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="b02f4-240">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-241">På sidan **Principer för skräppostskydd** väljer du en utgående policy för skräppost i listan genom att klicka på namnet:</span><span class="sxs-lookup"><span data-stu-id="b02f4-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="b02f4-242">En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="b02f4-243">Standardprincipen med namnet **Utgående policy mot skräppost (standard).**</span><span class="sxs-lookup"><span data-stu-id="b02f4-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="b02f4-244">I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="b02f4-245">Mer information om inställningarna finns i föregående Använda säkerhetscentret för att skapa principer för [utgående skräppost](#use-the-security-center-to-create-outbound-spam-policies) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b02f4-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="b02f4-246">I standardprincipen för utgående skräppost är **avsnittet** Tillämpas på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="b02f4-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="b02f4-247">Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="b02f4-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="b02f4-248">Aktivera eller inaktivera anpassade principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="b02f4-249">Du kan inte inaktivera standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="b02f4-250">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-251">På sidan **Principer för skydd mot** skräppost  väljer du en princip med värdet Typ av policy för anpassad **utgående skräppost** i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b02f4-252">Högst upp i den utfällda menyn principinformation ser du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="b02f4-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="b02f4-253">**Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .</span><span class="sxs-lookup"><span data-stu-id="b02f4-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="b02f4-254">**Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="b02f4-255">I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="b02f4-256">Klicka **Stäng** i den utfällda menyn principinformation.</span><span class="sxs-lookup"><span data-stu-id="b02f4-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="b02f4-257">Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="b02f4-258">Ange prioritet för anpassade principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="b02f4-259">Som standard prioriteras principer för utgående skräppost baserat på i vilken ordning de skapas (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="b02f4-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="b02f4-260">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="b02f4-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b02f4-261">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="b02f4-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b02f4-262">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Säkerhetscenter).</span><span class="sxs-lookup"><span data-stu-id="b02f4-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="b02f4-263">Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="b02f4-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="b02f4-264">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="b02f4-264">**Notes**:</span></span>

- <span data-ttu-id="b02f4-265">I säkerhetscentret kan du bara ändra prioriteten för policyn för utgående skräppost efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="b02f4-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="b02f4-266">I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="b02f4-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="b02f4-267">Principer för utgående skräppost bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="b02f4-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b02f4-268">Standardprincipen för utgående skräppost har prioritetsvärdet **Lägsta** och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="b02f4-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="b02f4-269">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-270">På sidan **Principer för skydd mot skräppost** väljer  du en princip med värdet Typ av anpassad **utgående skräppost-policy** i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b02f4-271">Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:</span><span class="sxs-lookup"><span data-stu-id="b02f4-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="b02f4-272">Policyn för utgående skräppost med **prioritetsvärdet** **0** har endast alternativet **Minska** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="b02f4-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="b02f4-273">Policyn för utgående skräppost med det **lägsta prioritetsvärdet** (till exempel **3)** har endast **alternativet Öka** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="b02f4-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="b02f4-274">Om du har tre eller fler principer för utgående skräppost har  principer mellan de högsta och lägsta prioritetsvärdena både alternativen Öka prioritet och **Minska** prioritet tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b02f4-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="b02f4-275">Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="b02f4-276">Klicka **Stäng** i den utfällda menyn principinformation när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b02f4-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="b02f4-277">Använda säkerhetscentret för att ta bort anpassade principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="b02f4-278">När du använder säkerhetscentret för att ta bort en anpassad policy för utgående skräppost tas både skräppostfilterregeln och motsvarande policy för skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="b02f4-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="b02f4-279">Du kan inte ta bort standardprincipen för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="b02f4-280">I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b02f4-281">På sidan **Principer för skydd mot** skräppost  väljer du en princip med värdet Typ av policy för anpassad **utgående skräppost** i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="b02f4-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="b02f4-282">Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="b02f4-283">I bekräftelsedialogrutan som visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b02f4-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="b02f4-284">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="b02f4-285">Som tidigare beskrivits består en princip för utgående skräppost av en utgående skräppostfilterprincip och en regel för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="b02f4-286">I Exchange Online PowerShell eller fristående EOP PowerShell syns skillnaden mellan principer för utgående skräppostfilter och utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="b02f4-287">Du hanterar principer för utgående skräppostfilter med hjälp av cmdletarna **\* -HostedOutboundSpamFilterPolicy** och du hanterar filterregler för utgående skräppost med hjälp av cmdletarna **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="b02f4-288">I PowerShell skapar du först principen för utgående skräppostfilter och sedan skapar du den utgående skräppostfilterregeln som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="b02f4-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b02f4-289">I PowerShell ändrar du inställningarna i filterprincipen för utgående skräppost och separat på filterregeln för utgående skräppost.</span><span class="sxs-lookup"><span data-stu-id="b02f4-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="b02f4-290">När du tar bort en princip för utgående skräppostfilter från PowerShell tas inte motsvarande utgående skräppostfilterregel bort automatiskt, och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="b02f4-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="b02f4-291">Använda PowerShell för att skapa principer för utgående skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="b02f4-292">Det krävs två steg för att skapa en princip för utgående skräppost i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b02f4-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b02f4-293">Skapa policyn för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="b02f4-294">Skapa den utgående skräppostfilterregel som anger den utgående skräppostfilterprincip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="b02f4-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="b02f4-295">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="b02f4-295">**Notes**:</span></span>

   - <span data-ttu-id="b02f4-296">Du kan skapa en ny regel för utgående skräppostfilter och tilldela en befintlig, oassocierad utgående skräppostfilterprincip till den.</span><span class="sxs-lookup"><span data-stu-id="b02f4-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="b02f4-297">En utgående skräppostfilterregel kan inte associeras med mer än en princip för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="b02f4-298">Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i säkerhetscentret förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="b02f4-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="b02f4-299">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="b02f4-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="b02f4-300">Ange prioritet för principen vid skapande (_Prioritet_ ) på _\<Number\>_ cmdleten **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="b02f4-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="b02f4-301">En ny princip för utgående skräppostfilter som du skapar i PowerShell visas inte i säkerhetscentret förrän du tilldelar principen till en regel för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="b02f4-302">Steg 1: Använda PowerShell för att skapa en princip för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="b02f4-303">Använd följande syntax för att skapa en princip för utgående skräppostfilter:</span><span class="sxs-lookup"><span data-stu-id="b02f4-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="b02f4-304">I det här exemplet skapas en ny policy för utgående skräppostfilter med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b02f4-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="b02f4-305">Mottagarens ratebegränsningar är begränsade till mindre värden som är standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="b02f4-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="b02f4-306">Mer information finns i Skicka [begränsningar över Microsoft 365 alternativ.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="b02f4-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="b02f4-307">När en av begränsningarna har nåtts hindras användaren från att skicka meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b02f4-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="b02f4-308">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="b02f4-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="b02f4-309">Steg 2: Använda PowerShell för att skapa en regel för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="b02f4-310">Använd följande syntax för att skapa en utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="b02f4-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b02f4-311">I det här exemplet skapas en ny utgående skräppostfilterregel med namnet Contoso Executives med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b02f4-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="b02f4-312">Principen för utgående skräppostfilter med namnet Contoso Executives är kopplad till regeln.</span><span class="sxs-lookup"><span data-stu-id="b02f4-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="b02f4-313">Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="b02f4-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="b02f4-314">Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b02f4-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="b02f4-315">Använda PowerShell för att visa principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="b02f4-316">Om du vill returnera en sammanfattning av alla principer för utgående skräppostfilter kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="b02f4-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="b02f4-317">Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterprincip:</span><span class="sxs-lookup"><span data-stu-id="b02f4-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b02f4-318">Det här exemplet returnerar alla egenskapsvärden för policyn för utgående skräppostfilter med namnet Chefer.</span><span class="sxs-lookup"><span data-stu-id="b02f4-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="b02f4-319">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="b02f4-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="b02f4-320">Använda PowerShell för att visa regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="b02f4-321">Om du vill visa befintliga regler för skräppostfilter för utgående trafik använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b02f4-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="b02f4-322">Kör följande kommando för att returnera en sammanfattningslista över alla utgående skräppostfilterregler:</span><span class="sxs-lookup"><span data-stu-id="b02f4-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="b02f4-323">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b02f4-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="b02f4-324">Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="b02f4-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b02f4-325">Det här exemplet returnerar alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b02f4-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b02f4-326">Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterRule.](/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="b02f4-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="b02f4-327">Använda PowerShell för att ändra principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="b02f4-328">Samma inställningar är tillgängliga när du ändrar en princip för skadlig programvara i PowerShell som när du skapar principen enligt beskrivningen i Steg [1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) Använda PowerShell för att skapa en princip för utgående skräppostfilter tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b02f4-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b02f4-329">Du kan inte byta namn på en utgående policy för skräppostfilter **(cmdleten Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="b02f4-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b02f4-330">När du byter namn på en utgående skräppostprincip i säkerhetscentret byter du bara namn på regeln för utgående _skräppostfilter._</span><span class="sxs-lookup"><span data-stu-id="b02f4-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="b02f4-331">Använd följande syntax för att ändra en princip för utgående skräppostfilter:</span><span class="sxs-lookup"><span data-stu-id="b02f4-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b02f4-332">Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="b02f4-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="b02f4-333">Använda PowerShell för att ändra regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="b02f4-334">Den enda inställningen som inte är tillgänglig när du ändrar en regel för utgående skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="b02f4-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b02f4-335">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för utgående skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b02f4-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="b02f4-336">Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en regel för utgående skräppostfilter i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b02f4-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="b02f4-337">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg [2: Använd PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) för att skapa en utgående skräppostfilterregel tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b02f4-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="b02f4-338">Använd följande syntax för att ändra en utgående skräppostfilterregel:</span><span class="sxs-lookup"><span data-stu-id="b02f4-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b02f4-339">Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterRule.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="b02f4-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="b02f4-340">Använda PowerShell för att aktivera eller inaktivera regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="b02f4-341">Om du aktiverar eller inaktiverar en utgående skräppostfilterregel i PowerShell aktiveras eller inaktiveras principen för hela den utgående skräpposten (regeln för utgående skräppostfilter och policyn för utgående skräppostfilter).</span><span class="sxs-lookup"><span data-stu-id="b02f4-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="b02f4-342">Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="b02f4-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="b02f4-343">Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b02f4-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="b02f4-344">I det här exemplet inaktiveras regeln för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b02f4-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b02f4-345">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="b02f4-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b02f4-346">Detaljerad information om syntax och parametrar finns i [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [Disable-HostedOutboundSpamFilterRule.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="b02f4-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="b02f4-347">Använda PowerShell för att ange prioriteten för utgående skräppostfilterregler</span><span class="sxs-lookup"><span data-stu-id="b02f4-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="b02f4-348">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="b02f4-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b02f4-349">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="b02f4-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b02f4-350">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="b02f4-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b02f4-351">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="b02f4-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b02f4-352">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="b02f4-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b02f4-353">Om du vill ange prioriteten för en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b02f4-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b02f4-354">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="b02f4-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b02f4-355">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="b02f4-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b02f4-356">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="b02f4-356">**Notes**:</span></span>

- <span data-ttu-id="b02f4-357">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i stället för cmdleten **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="b02f4-358">Standardprincipen för utgående skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid det omoderbara prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="b02f4-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="b02f4-359">Använda PowerShell för att ta bort principer för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="b02f4-360">När du använder PowerShell för att ta bort en princip för utgående skräppostfilter tas inte motsvarande utgående skräppostfilterregel bort.</span><span class="sxs-lookup"><span data-stu-id="b02f4-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="b02f4-361">Om du vill ta bort en princip för utgående skräppostfilter i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b02f4-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b02f4-362">Det här exemplet tar bort policyn för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b02f4-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b02f4-363">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="b02f4-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="b02f4-364">Använda PowerShell för att ta bort regler för utgående skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b02f4-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="b02f4-365">När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande princip för skräppostfilter bort.</span><span class="sxs-lookup"><span data-stu-id="b02f4-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="b02f4-366">Om du vill ta bort en utgående skräppostfilterregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b02f4-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="b02f4-367">Det här exemplet tar bort regeln för utgående skräppostfilter med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b02f4-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b02f4-368">Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterRule.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="b02f4-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b02f4-369">Mer information</span><span class="sxs-lookup"><span data-stu-id="b02f4-369">For more information</span></span>

[<span data-ttu-id="b02f4-370">Ta bort blockerade användare från portalen med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="b02f4-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="b02f4-371">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="b02f4-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="b02f4-372">Vanliga frågor och svar om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="b02f4-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="b02f4-373">Rapporten Automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="b02f4-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
