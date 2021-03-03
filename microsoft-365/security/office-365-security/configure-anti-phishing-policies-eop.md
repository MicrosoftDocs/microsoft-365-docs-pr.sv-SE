---
title: Konfigurera principer för skydd mot nätfiske i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att skapa, ändra och ta bort de skydd mot nätfiske som är tillgängliga i Organisationer med eller utan Exchange Online-postlådor i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 612c7153f89a404cac736a9a46e8ca5f69e46f65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406226"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="33691-103">Konfigurera principer för skydd mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="33691-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33691-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="33691-104">**Applies to**</span></span>
- [<span data-ttu-id="33691-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33691-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="33691-106">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor finns det en standardprincip mot nätfiske som innehåller ett begränsat antal skydd mot förfalskning som är aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="33691-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="33691-107">Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="33691-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="33691-108">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="33691-109">För att få bättre detaljnivå kan du också skapa anpassade principer för nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33691-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="33691-110">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="33691-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="33691-111">Organisationer med Exchange Online-postlådor kan konfigurera principer för skydd mot nätfiske i Säkerhets- & Efterlevnadscenter eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33691-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="33691-112">Fristående EOP-organisationer kan endast använda Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="33691-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="33691-113">Information om hur du skapar och ändrar de mer avancerade principerna för nätfiske i Microsoft Defender för Office 365 som är tillgängliga i Defender för Office 365 finns i Konfigurera principer för nätfiske i Microsoft Defender för [Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="33691-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="33691-114">De grundläggande elementen i en princip mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="33691-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="33691-115">**Nätfiskeprincipen:** Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras samt de åtgärder som används.</span><span class="sxs-lookup"><span data-stu-id="33691-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="33691-116">**Den phish-regeln:** Anger prioritet och mottagarfilter (som principen gäller för) för en nätt phish-princip.</span><span class="sxs-lookup"><span data-stu-id="33691-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="33691-117">Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer mot nätfiske i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="33691-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="33691-118">När du skapar en policy mot nätfiske skapar du egentligen en nätfiskeprincip och den tillhörande nätfiskeprincipen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="33691-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="33691-119">När du ändrar en princip mot nätfiske ändrar inställningarna för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter ändrar nätfiskeregeln.</span><span class="sxs-lookup"><span data-stu-id="33691-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="33691-120">Alla andra inställningar ändrar den tillhörande anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="33691-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="33691-121">När du tar bort en nätfiskeprincip tas nätfiskeregeln och den tillhörande nätfiskeprincipen bort.</span><span class="sxs-lookup"><span data-stu-id="33691-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="33691-122">I Exchange Online PowerShell hanterar du principen och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="33691-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="33691-123">Mer information finns i avsnittet Använda [Exchange Online PowerShell för att konfigurera principer mot](#use-exchange-online-powershell-to-configure-anti-phishing-policies) nätfiske senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="33691-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="33691-124">Alla organisationer har en inbyggd policy för skydd mot nätfiske med namnet Office365 AntiPhish Default som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="33691-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="33691-125">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon skyddande phish-regel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="33691-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="33691-126">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="33691-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="33691-127">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="33691-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="33691-128">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="33691-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="33691-129">För att öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade principer för nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="33691-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33691-130">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="33691-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33691-131">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="33691-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="33691-132">Om du vill gå direkt **till sidan mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="33691-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="33691-133">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="33691-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="33691-134">Du kan inte hantera principer för nätfiske i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33691-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="33691-135">Du måste ha tilldelats behörigheter i **Exchange Online innan** du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="33691-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="33691-136">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="33691-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="33691-137">För skrivskyddade åtkomst till principer för nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33691-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="33691-138">Mer information finns i [Behörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="33691-138">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="33691-139">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="33691-139">**Notes**:</span></span>

  - <span data-ttu-id="33691-140">Om du lägger till användare till motsvarande Azure Active Directory-roll i  administrationscentret för Microsoft 365 får användarna de behörigheter och behörigheter som krävs för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33691-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="33691-141">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="33691-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="33691-142">Rollgruppen **Skrivskyddade organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till <sup>\*</sup> funktionen.</span><span class="sxs-lookup"><span data-stu-id="33691-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="33691-143"><sup>\*</sup> I Säkerhets- & efterlevnadscenter kan användare med skrivskyddsåtkomst visa inställningarna för anpassade principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="33691-144">Skrivskyddade användare kan inte se inställningarna i standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="33691-145">Om du vill skapa och ändra principer för nätfiske i fristående EOP måste du göra något som _kräver avisering_ för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="33691-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="33691-146">I till exempel administrationscentret för Exchange (EAC)  kan du gå till fliken  Behörigheter, välja en befintlig rollgrupp, klicka på redigera-ikonen och ta bort en roll (som du lägger till sist ![ ](../../media/ITPro-EAC-EditIcon.png) tillbaka).</span><span class="sxs-lookup"><span data-stu-id="33691-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="33691-147">Om klientorganisationen aldrig har blivit bortskriden visas en dialogruta med namnet Uppdatera organisationsinställningar **med** en förloppsstapel som ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="33691-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="33691-148">Mer information om härdning finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (som inte är tillgänglig i fristående EOP PowerShell eller i Säkerhets- och & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="33691-148">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="33691-149">Våra rekommenderade inställningar för principer för skydd mot nätfiske finns i [EOP:s standardinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="33691-150">Det kan ta upp till 30 minuter innan den uppdaterade principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="33691-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="33691-151">Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordningen och [prioriteten för e-postskyddet.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="33691-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="33691-152">Använd Säkerhets- & Center för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="33691-153">När du skapar en anpassad policy för nätfiske i Säkerhets- & Efterlevnadscenter skapas samtidigt den skyddande phish-regeln och den tillhörande nätfiskeprincipen med samma namn.</span><span class="sxs-lookup"><span data-stu-id="33691-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="33691-154">När du skapar en princip mot nätfiske kan du bara ange namn, beskrivning och mottagarfilter som identifierar vem principen gäller.</span><span class="sxs-lookup"><span data-stu-id="33691-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="33691-155">När du har skapat principen kan du ändra den om du vill ändra eller granska standardinställningarna för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="33691-156">Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-157">Klicka på **Skapa på** sidan Mot **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="33691-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="33691-158">Guiden **Skapa en ny princip mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="33691-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="33691-159">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="33691-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="33691-160">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="33691-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="33691-161">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="33691-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="33691-162">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="33691-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="33691-163">På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="33691-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="33691-164">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="33691-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="33691-165">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="33691-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="33691-166">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="33691-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="33691-167">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="33691-167">Click **Add a condition**.</span></span> <span data-ttu-id="33691-168">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="33691-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="33691-169">**Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33691-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="33691-170">**Mottagaren är medlem i:** Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33691-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="33691-171">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="33691-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="33691-172">När du har valt villkoret visas en motsvarande listruta med **rutan Valfri av dessa.**</span><span class="sxs-lookup"><span data-stu-id="33691-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="33691-173">Klicka i rutan och bläddra igenom listan med värden för att välja.</span><span class="sxs-lookup"><span data-stu-id="33691-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="33691-174">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="33691-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="33691-175">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="33691-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="33691-176">Om du vill ta bort enskilda poster klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.</span><span class="sxs-lookup"><span data-stu-id="33691-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="33691-177">Om du vill ta bort hela villkoret klickar **du på ikonen** Ta bort i ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="33691-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="33691-178">Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om.**</span><span class="sxs-lookup"><span data-stu-id="33691-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="33691-179">Om du vill lägga till undantag **klickar du på Lägg till ett** villkor och väljer ett undantag under Utom **om.**</span><span class="sxs-lookup"><span data-stu-id="33691-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="33691-180">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="33691-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="33691-181">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="33691-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="33691-182">Granska **inställningarna på sidan** Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="33691-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="33691-183">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="33691-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="33691-184">Klicka på Skapa den här principen när **du är klar.**</span><span class="sxs-lookup"><span data-stu-id="33691-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="33691-185">Klicka **på OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="33691-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="33691-186">När du har skapat principen mot nätfiske med de här allmänna principinställningarna följer du anvisningarna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="33691-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="33691-187">Använda Säkerhets- & Center för att ändra principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="33691-188">Använd följande procedurer för att ändra principer för skydd mot nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="33691-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="33691-189">Om du inte redan är där öppnar du Säkerhets- & Efterlevnadscenter och går **till** Policy för skydd mot \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="33691-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-190">Välj den anpassade principen för nätfiske som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="33691-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="33691-191">Om det redan är markerat avmarkerar du det och markerar det igen.</span><span class="sxs-lookup"><span data-stu-id="33691-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="33691-192">Den **utfällna knappen Redigera \<name\>** din princip visas.</span><span class="sxs-lookup"><span data-stu-id="33691-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="33691-193">Om **du** klickar på Redigera i ett avsnitt får du åtkomst till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="33691-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="33691-194">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="33691-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="33691-195">När du klickar på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men  du kan hoppa  inom  sidorna i valfri ordning och du kan klicka på Spara på valfri sida (eller  ![ ](../../media/scc-remove-icon.png) **\<name\>** ikonen Avbryt eller Stäng om du vill gå tillbaka till sidan Redigera principen (du behöver inte gå till den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="33691-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="33691-196">**Principinställning:** Klicka **på** Redigera om du vill ändra samma inställningar som var [tillgängliga när du](#use-the-security--compliance-center-to-create-anti-phishing-policies) skapade principen i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="33691-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="33691-197">**Name**</span><span class="sxs-lookup"><span data-stu-id="33691-197">**Name**</span></span>
   - <span data-ttu-id="33691-198">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="33691-198">**Description**</span></span>
   - <span data-ttu-id="33691-199">**Används på**</span><span class="sxs-lookup"><span data-stu-id="33691-199">**Applied to**</span></span>
   - <span data-ttu-id="33691-200">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="33691-200">**Review your settings**</span></span>

   <span data-ttu-id="33691-201">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="33691-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="33691-202">**Spoof:**  Klicka på Redigera om du vill aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthiskt identifiering av avsändare i Outlook och konfigurera åtgärden för meddelanden från spärrade förfalskningsavsändare.</span><span class="sxs-lookup"><span data-stu-id="33691-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="33691-203">Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="33691-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="33691-204">Observera att samma inställningar även är tillgängliga i principer för skydd mot nätfiske i Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="33691-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="33691-205">**Filterinställningar för förfalskning:** Standardvärdet är **På** och vi rekommenderar att du låter det vara på.</span><span class="sxs-lookup"><span data-stu-id="33691-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="33691-206">Om du vill inaktivera den drar du reglaget till **Av.**</span><span class="sxs-lookup"><span data-stu-id="33691-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="33691-207">Mer information finns i [Konfigurera förfalskningsinformation i EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="33691-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="33691-208">Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="33691-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="33691-209">Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="33691-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="33691-210">**Aktivera funktionen Oauthenticerad avsändare:** Standardvärdet är **På.**</span><span class="sxs-lookup"><span data-stu-id="33691-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="33691-211">Om du vill inaktivera den drar du reglaget till **Av.**</span><span class="sxs-lookup"><span data-stu-id="33691-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="33691-212">**Åtgärder:** Ange vilken åtgärd som ska vidtas för meddelanden som inte klarar förfalskningsinformation:</span><span class="sxs-lookup"><span data-stu-id="33691-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="33691-213">**Om e-post skickas av någon som inte har tillåtelse att kapa din domän:**</span><span class="sxs-lookup"><span data-stu-id="33691-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="33691-214">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="33691-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="33691-215">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="33691-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="33691-216">**Granska dina inställningar:** i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="33691-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="33691-217">Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="33691-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="33691-218">Du kan aktivera eller inaktivera följande **inställningar** **direkt** på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="33691-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="33691-219">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="33691-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="33691-220">**Aktivera funktionen Oauthenticerad avsändare**</span><span class="sxs-lookup"><span data-stu-id="33691-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="33691-221">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="33691-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="33691-222">Tillbaka på sidan **Redigera \<Name\> principen** granskar du inställningarna och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="33691-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="33691-223">Använd Säkerhets- & Center för efterlevnad för att ändra standardprincipen för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="33691-224">Standardprincipen för skydd mot nätfiske heter Office365 AntiPhish Default och visas inte i listan med principer.</span><span class="sxs-lookup"><span data-stu-id="33691-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="33691-225">Gör så här om du vill ändra standardprincipen för skydd mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="33691-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="33691-226">Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-227">Klicka på **Standardprincip** på sidan **Skydd mot nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="33691-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="33691-228">Sidan **Redigera standardprincip för Office365-skydd visas.**</span><span class="sxs-lookup"><span data-stu-id="33691-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="33691-229">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="33691-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="33691-230">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="33691-230">**Impersonation**</span></span>
   - <span data-ttu-id="33691-231">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="33691-231">**Spoof**</span></span>
   - <span data-ttu-id="33691-232">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="33691-232">**Advanced settings**</span></span>

   <span data-ttu-id="33691-233">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="33691-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="33691-234">Du kan  se avsnittet och värdena för principinställningen, men det finns ingen redigeringslänk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)). </span><span class="sxs-lookup"><span data-stu-id="33691-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="33691-235">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="33691-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="33691-236">Du kan inte ändra prioriteten för standardprincipen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="33691-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="33691-237">Granska inställningarna **på sidan Redigera standardinställningen för policyn för Office365,** och klicka sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="33691-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="33691-238">Aktivera eller inaktivera anpassade principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="33691-239">Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-240">Observera värdet i **kolumnen** Status:</span><span class="sxs-lookup"><span data-stu-id="33691-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="33691-241">Dra växlingsknappen till **Av** för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="33691-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="33691-242">Aktivera principen genom att **dra reglaget** till På.</span><span class="sxs-lookup"><span data-stu-id="33691-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="33691-243">Du kan inte inaktivera standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="33691-244">Ange prioritet för anpassade principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="33691-245">Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de har skapats (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="33691-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="33691-246">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="33691-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="33691-247">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="33691-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="33691-248">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="33691-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="33691-249">Anpassade principer för skydd mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="33691-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="33691-250">Standardprincipen för skydd mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="33691-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="33691-251">**Obs!** I Säkerhets- & Efterlevnadscenter kan du bara ändra prioriteten för principen mot nätfiske efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="33691-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="33691-252">I PowerShell kan du åsidosätta standardprioritet när du skapar nätt phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="33691-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="33691-253">Om du vill ändra prioriteten för  en princip klickar du på Öka prioritet eller  Minska prioriteten för principens egenskaper (du kan inte direkt ändra prioritetsnumret i Säkerhets- & Efterlevnadscenter). </span><span class="sxs-lookup"><span data-stu-id="33691-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="33691-254">Att ändra prioritet för en princip är bara meningsfullt om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="33691-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="33691-255">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="33691-256">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="33691-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="33691-257">Om det redan är markerat avmarkerar du det och markerar det igen.</span><span class="sxs-lookup"><span data-stu-id="33691-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="33691-258">Den **utfällna knappen Redigera \<name\>** din princip visas.</span><span class="sxs-lookup"><span data-stu-id="33691-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="33691-259">Den anpassade principen för nätfiske med **prioritetsvärdet** **0** har endast **knappen Minska** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="33691-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="33691-260">Den anpassade principen för nätfiske med lägsta **prioritetsvärde** (till exempel **3)** har endast knappen Öka **prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="33691-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="33691-261">Om du har tre eller fler anpassade principer för skydd mot nätfiske finns det både knapparna Öka prioritet och Minska prioritet mellan de högsta och lägsta prioritetsvärdena.  </span><span class="sxs-lookup"><span data-stu-id="33691-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="33691-262">Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="33691-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="33691-263">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="33691-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="33691-264">Använd Säkerhets- & Center för att visa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="33691-265">Gå till policyn för skydd mot  nätfiske i säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-266">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="33691-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="33691-267">Välj en anpassad princip för nätfiske som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="33691-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="33691-268">Om det redan är markerat avmarkerar du det och markerar det igen.</span><span class="sxs-lookup"><span data-stu-id="33691-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="33691-269">Klicka **på Standardprincip** om du vill visa standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="33691-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="33691-270">Den **utfällga \<name\>** menyn Redigera princip visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="33691-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="33691-271">Använda Säkerhets- & Center för att ta bort principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="33691-272">Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33691-273">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="33691-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="33691-274">Om det redan är markerat avmarkerar du det och markerar det igen.</span><span class="sxs-lookup"><span data-stu-id="33691-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="33691-275">I den **utfällingsrutan \<name\>** Redigera principen som visas klickar du på Ta bort princip och sedan **på Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="33691-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="33691-276">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="33691-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="33691-277">Använda Exchange Online PowerShell för att konfigurera principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="33691-278">Som tidigare beskrivits består en nätfiskeprincip av en nätfiskeprincip och en nätfiskeregel.</span><span class="sxs-lookup"><span data-stu-id="33691-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="33691-279">I Exchange Online PowerShell visar sig skillnaden mellan nättringsprinciper och nätt phish-regler.</span><span class="sxs-lookup"><span data-stu-id="33691-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="33691-280">Du hanterar phish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar nätfingregler med hjälp av **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="33691-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="33691-281">I PowerShell skapar du först en nätt phish-princip och sedan skapar du den skyddande phish-regel som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="33691-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="33691-282">I PowerShell kan du ändra inställningarna separat i nätt phish-principen och anti-phish-regeln.</span><span class="sxs-lookup"><span data-stu-id="33691-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="33691-283">När du tar bort en nätt phish-princip från PowerShell tas inte motsvarande phish-regel bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="33691-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="33691-284">Följande PowerShell-procedurer är inte tillgängliga i fristående EOP-organisationer som använder Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33691-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="33691-285">Använda PowerShell för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="33691-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="33691-286">Att skapa en princip mot nätfiske i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="33691-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="33691-287">Skapa en anti-phish-policy.</span><span class="sxs-lookup"><span data-stu-id="33691-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="33691-288">Skapa den phish-regel som anger den anti-phish-policy som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="33691-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="33691-289">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="33691-289">**Notes**:</span></span>

- <span data-ttu-id="33691-290">Du kan skapa en ny, phish-regel och tilldela den en befintlig, oassocierad nätt phish-princip.</span><span class="sxs-lookup"><span data-stu-id="33691-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="33691-291">En nätt phish-regel kan inte associeras med mer än en anti-phish-policy.</span><span class="sxs-lookup"><span data-stu-id="33691-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="33691-292">Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i Säkerhets- & och efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="33691-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="33691-293">Skapa den nya principen som inaktiverad _(aktiverad_ för `$false` cmdleten **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="33691-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="33691-294">Ange prioriteten för principen när den skapas _(Priority)_ _\<Number\>_ på **cmdleten New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="33691-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="33691-295">En ny, phish-princip som du skapar i PowerShell visas inte i Säkerhets- & och efterlevnadscenter förrän du tilldelar principen till en nätt phish-regel.</span><span class="sxs-lookup"><span data-stu-id="33691-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="33691-296">Steg 1: Använda PowerShell för att skapa en anti-phish-princip</span><span class="sxs-lookup"><span data-stu-id="33691-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="33691-297">Om du vill skapa en anti-phish-princip använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="33691-298">I det här exemplet skapas en nätt phish-princip som heter Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="33691-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="33691-299">Beskrivningen är: Forskningavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="33691-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="33691-300">Ändrar standardåtgärden för förfalskning till karantän.</span><span class="sxs-lookup"><span data-stu-id="33691-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="33691-301">Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33691-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="33691-302">Steg 2: Använda PowerShell för att skapa en antifishregel</span><span class="sxs-lookup"><span data-stu-id="33691-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="33691-303">Om du vill skapa en anti-phish-regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="33691-304">I det här exemplet skapas en antifishregel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="33691-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="33691-305">Regeln är kopplad till den phish-policy som heter Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="33691-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="33691-306">Regeln gäller för medlemmar i gruppen Research Department.</span><span class="sxs-lookup"><span data-stu-id="33691-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="33691-307">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="33691-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="33691-308">Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="33691-308">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="33691-309">Använda PowerShell för att visa nätthetsprinciper</span><span class="sxs-lookup"><span data-stu-id="33691-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="33691-310">Om du vill se befintliga principer för nättring använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="33691-311">Det här exemplet returnerar en sammanfattning av alla principer för nätt phish tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="33691-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="33691-312">I det här exemplet returneras alla egendomsvärden för den nätt phish-policy som heter Chefer.</span><span class="sxs-lookup"><span data-stu-id="33691-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="33691-313">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33691-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="33691-314">Använda PowerShell för att visa nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="33691-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="33691-315">Om du vill se befintliga skyddande regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="33691-316">Det här exemplet returnerar en sammanfattning av alla skyddande regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="33691-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="33691-317">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="33691-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="33691-318">I det här exemplet returneras alla egenskapsvärden för den phish-regeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="33691-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="33691-319">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="33691-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="33691-320">Använda PowerShell för att ändra nätthetsprinciper</span><span class="sxs-lookup"><span data-stu-id="33691-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="33691-321">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar en princip enligt beskrivningen i steg 1: Använda PowerShell för att skapa en nätt [phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="33691-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="33691-322">Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (gäller för alla, alltid Lägsta prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätt phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33691-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="33691-323">Du kan inte byta namn på en nätt **phish-princip (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="33691-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="33691-324">När du byter namn på en policy mot nätfiske i Säkerhets- & Efterlevnadscenter byter du bara namn på _nätfiskeregeln._</span><span class="sxs-lookup"><span data-stu-id="33691-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="33691-325">Om du vill ändra en anti-phish-princip använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="33691-326">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33691-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="33691-327">Använda PowerShell för att ändra nätthetsregler</span><span class="sxs-lookup"><span data-stu-id="33691-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="33691-328">Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är den aktiverade _parametern_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="33691-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="33691-329">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddande regler.</span><span class="sxs-lookup"><span data-stu-id="33691-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="33691-330">Annars är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i steg [2:](#step-2-use-powershell-to-create-an-anti-phish-rule) Använd PowerShell för att skapa ett avsnitt som inte är phish längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="33691-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="33691-331">Använd följande syntax för att ändra en antifishregel:</span><span class="sxs-lookup"><span data-stu-id="33691-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="33691-332">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="33691-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="33691-333">Använda PowerShell för att aktivera eller inaktivera skydd mot phish-regler</span><span class="sxs-lookup"><span data-stu-id="33691-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="33691-334">Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen).</span><span class="sxs-lookup"><span data-stu-id="33691-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="33691-335">Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="33691-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="33691-336">Om du vill aktivera eller inaktivera en nätt phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="33691-337">I det här exemplet inaktiveras den phish-regeln marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="33691-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33691-338">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="33691-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33691-339">Detaljerad information om syntax och parametrar finns [i Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="33691-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="33691-340">Använd PowerShell för att ange prioriteten för nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="33691-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="33691-341">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="33691-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="33691-342">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="33691-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="33691-343">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="33691-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="33691-344">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="33691-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="33691-345">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="33691-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="33691-346">Använd följande syntax för att ange prioriteten för en anti-phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="33691-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="33691-347">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="33691-347">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="33691-348">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="33691-348">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="33691-349">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="33691-349">**Notes**:</span></span>

- <span data-ttu-id="33691-350">Om du vill ange prioriteten för en  ny regel när du skapar den använder du prioritetsparametern i cmdleten **New-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="33691-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="33691-351">Standardprincipen för nätt phish har inte en motsvarande antifishregel och har alltid det omoderbara prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="33691-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="33691-352">Använda PowerShell för att ta bort nätt phish-principer</span><span class="sxs-lookup"><span data-stu-id="33691-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="33691-353">När du använder PowerShell för att ta bort en nätt phish-princip tas inte motsvarande phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="33691-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="33691-354">Om du vill ta bort en anti-phish-princip i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="33691-355">I det här exemplet tas den antifishpolicy som heter Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="33691-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="33691-356">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33691-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="33691-357">Använda PowerShell för att ta bort nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="33691-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="33691-358">När du använder PowerShell för att ta bort en nätt phish-regel tas inte motsvarande phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="33691-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="33691-359">Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="33691-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="33691-360">I det här exemplet tas den phish-regeln som heter Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="33691-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33691-361">Detaljerad information om syntax och parametrar finns [i Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="33691-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="33691-362">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="33691-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="33691-363">Kontrollera att du har konfigurerat principer för skydd mot nätfiske i Microsoft Defender för Office 365 genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="33691-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="33691-364">Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="33691-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="33691-365">Kontrollera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="33691-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="33691-366">Om du vill visa mer information gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="33691-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="33691-367">Välj principen i listan och visa informationen i den utfällade listrutan.</span><span class="sxs-lookup"><span data-stu-id="33691-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="33691-368">Klicka **på Standardprincip** och visa informationen i den utfällna menyn.</span><span class="sxs-lookup"><span data-stu-id="33691-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="33691-369">I Exchange Online PowerShell ersätter du med namnet på principen \<Name\> eller regeln, kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="33691-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
