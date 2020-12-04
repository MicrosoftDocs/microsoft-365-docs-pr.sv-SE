---
title: Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du skapar, ändrar och tar bort de avancerade AntiPhishing-principer som är tillgängliga i organisationer med Microsoft Defender för Office 365.
ms.openlocfilehash: ae8c87a0bfb7f975328d8283f0b62aa12c1d5e2b
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572411"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-103">Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0085c-104">Anti-nätfiske-principer i [Microsoft Defender för Office 365](office-365-atp.md) skyddar din organisation från illasinnade nätfiske-attacker och andra typer av nät fiske attacker.</span><span class="sxs-lookup"><span data-stu-id="0085c-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0085c-105">Mer information om skillnaderna mellan anti-nätfiske-principer i Exchange Online Protection (EOP) och anti-nätfiske-principer i Microsoft Defender för Office 365 finns i [skydd mot nätfiske](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0085c-106">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0085c-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0085c-107">Om du vill ha större precision kan du även skapa anpassade AntiPhishing-principer som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0085c-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0085c-108">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0085c-109">Du kan konfigurera anti-nätfiske-principer i säkerhets & efterlevnads Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0085c-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0085c-110">Information om hur du konfigurerar de begränsade begränsningarna för nätfiske-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga organisationer utan Microsoft Defender för Office 365) finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="0085c-111">De grundläggande delarna i en Antivirus policy är:</span><span class="sxs-lookup"><span data-stu-id="0085c-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0085c-112">**Policyn för Phish**: anger skydds alternativen för nätfiske för att aktivera eller inaktivera och åtgärderna för att tillämpa alternativ.</span><span class="sxs-lookup"><span data-stu-id="0085c-112">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="0085c-113">**Regeln för Phish**: anger de prioritets-och mottagar filter (som principen gäller för) för en policy mot anti-Phish.</span><span class="sxs-lookup"><span data-stu-id="0085c-113">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0085c-114">Skillnaden mellan dessa två element är inte uppenbar när du hanterar skydd mot nätfiske i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="0085c-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0085c-115">När du skapar en princip skapar du verkligen en Phish regel och tillhör ande policy för anti-Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="0085c-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0085c-116">När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra Phish regel.</span><span class="sxs-lookup"><span data-stu-id="0085c-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0085c-117">Alla andra inställningar ändra den associerade policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="0085c-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="0085c-118">När du tar bort en princip tas Phish-regeln och den associerade anti-Phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="0085c-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0085c-119">I Exchange Online PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="0085c-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0085c-120">Mer information finns i [använda Exchange Online PowerShell för att konfigurera skydd mot nätfiske-principer i avsnittet Microsoft Defender för Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0085c-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="0085c-121">Alla Microsoft Defender för Office 365-organisationer har en inbyggd policy för anti-nätfiske som heter Office365 AntiPhish standard och har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0085c-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0085c-122">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-Phish-regel (mottagar filter) som är kopplade till principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="0085c-123">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="0085c-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0085c-124">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="0085c-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="0085c-125">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="0085c-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0085c-126">För att öka effektiviteten för skydd mot nätfiske i Microsoft Defender för Office 365 kan du skapa anpassade skydds principer med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="0085c-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0085c-127">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="0085c-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0085c-128">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0085c-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0085c-129">Använd om du vill gå direkt till sidan **ATP-nätfiske** <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="0085c-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0085c-130">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0085c-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0085c-131">Du måste tilldelas behörigheter i säkerhets & Compliance Center innan du kan göra det i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="0085c-131">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0085c-132">För att lägga till, ändra och ta bort skydd mot nätfiske måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="0085c-132">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0085c-133">Om du vill ha skrivskyddad åtkomst till principer mot nätfiske måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="0085c-133">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="0085c-134">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="0085c-135">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0085c-135">**Notes**:</span></span>

  - <span data-ttu-id="0085c-136">Om du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0085c-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0085c-137">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="0085c-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="0085c-138">Roll gruppen **organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="0085c-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="0085c-139"><sup>\*</sup> I säkerhets & Compliance Center är skrivskyddad åtkomst tillåta användare att Visa inställningar för anpassade skydds principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-139"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="0085c-140">Skrivskyddade användare kan inte se inställningarna i standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0085c-140">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="0085c-141">För våra rekommenderade inställningar för skydd mot nätfiske i Microsoft Defender för Office 365, se [AntiPhishing-principer i inställningar för Defender för Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0085c-141">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="0085c-142">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="0085c-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0085c-143">Information om var anti-nätfiske-principer tillämpas i filtrerings pipeline finns i [order och prioritetsordning för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-144">Använda säkerhets & Compliance Center för att skapa skydd mot nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-144">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0085c-145">Om du skapar en anpassad skydds princip i säkerhets & Compliance Center skapar regeln mot Phish och tillhör ande policy mot Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="0085c-145">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0085c-146">När du skapar en AntiPhishing-princip kan du bara ange princip namnet, beskrivningen och det mottagar filter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="0085c-146">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0085c-147">När du har skapat den här principen kan du ändra principen för att ändra eller granska standardinställningarna för nät fiske inställningar.</span><span class="sxs-lookup"><span data-stu-id="0085c-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0085c-148">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-149">Klicka på **skapa** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="0085c-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0085c-150">Guiden **skapa en ny policy för skydd mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="0085c-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0085c-151">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0085c-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0085c-152">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0085c-153">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0085c-154">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0085c-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0085c-155">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="0085c-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0085c-156">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="0085c-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0085c-157">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0085c-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0085c-158">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0085c-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0085c-159">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="0085c-159">Click **Add a condition**.</span></span> <span data-ttu-id="0085c-160">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om**:</span><span class="sxs-lookup"><span data-stu-id="0085c-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0085c-161">**Mottagaren är**: anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0085c-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0085c-162">**Mottagaren är medlem i**: anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0085c-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0085c-163">**Mottagar domänen är**: anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0085c-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="0085c-164">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="0085c-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0085c-165">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="0085c-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0085c-166">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="0085c-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0085c-167">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="0085c-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0085c-168">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="0085c-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0085c-169">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="0085c-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0085c-170">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.</span><span class="sxs-lookup"><span data-stu-id="0085c-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0085c-171">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**.</span><span class="sxs-lookup"><span data-stu-id="0085c-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0085c-172">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="0085c-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0085c-173">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0085c-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0085c-174">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0085c-175">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="0085c-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0085c-176">När du är klar klickar du på **skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="0085c-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0085c-177">Klicka på **OK** i bekräftelse dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0085c-178">När du har skapat AntiPhishing-principen med dessa allmänna inställningar följer du anvisningarna i nästa avsnitt för att konfigurera skydds inställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-178">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-179">Använda säkerhets & Compliance Center för att ändra anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-179">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0085c-180">Använd följande procedurer för att ändra anti-nätfiske-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="0085c-180">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0085c-181">Om du inte redan har gjort det öppnar du säkerhets & efterlevnad och går till **hot Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-182">Välj den anpassade Antivirus princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="0085c-182">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0085c-183">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="0085c-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0085c-184">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0085c-185">Om du klickar på **Redigera** i ett avsnitt får du till gång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0085c-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0085c-186">Följande anvisningar visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="0085c-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0085c-187">När du har klickat på **Redigera** i ett avsnitt visas de tillgängliga inställningarna i ett guide format, men du kan hoppa mellan sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Avbryt** eller **Stäng** Stäng-ikonen om du vill ![ ](../../media/scc-remove-icon.png) gå tillbaka till sidan **Redigera din policy \<name\>** ).</span><span class="sxs-lookup"><span data-stu-id="0085c-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0085c-188">**Princip inställning**: Klicka på **Redigera** om du vill ändra samma inställningar som fanns tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="0085c-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="0085c-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="0085c-189">**Name**</span></span>
   - <span data-ttu-id="0085c-190">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0085c-190">**Description**</span></span>
   - <span data-ttu-id="0085c-191">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="0085c-191">**Applied to**</span></span>
   - <span data-ttu-id="0085c-192">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="0085c-192">**Review your settings**</span></span>

   <span data-ttu-id="0085c-193">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0085c-194">**Personifiering**: Klicka på **Redigera** för att ändra de skyddade avsändarna och de skyddade domänerna i principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0085c-195">Dessa inställningar är ett villkor för den princip som identifierar falska avsändare att leta efter (individuellt eller efter domän) i från-adressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="0085c-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0085c-196">Mer information finns i [Inställningar för personifiering i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0085c-196">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0085c-197">**Lägg till användare att skydda**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-198">Aktivera **den genom att dra den till den** och sedan klicka på knappen **Lägg till användare** som visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0085c-199">I **Lägg till** utfällda användare som visas konfigurerar du följande värden:</span><span class="sxs-lookup"><span data-stu-id="0085c-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0085c-200">**E-post adress**:</span><span class="sxs-lookup"><span data-stu-id="0085c-200">**Email address**:</span></span>

       - <span data-ttu-id="0085c-201">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="0085c-201">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0085c-202">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="0085c-202">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0085c-203">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="0085c-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0085c-204">**Namn**: det här värdet fylls i baserat på e-postadressen du valde, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="0085c-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0085c-205">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-205">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="0085c-206">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="0085c-206">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="0085c-207">I varje skydds princip kan du ange högst 60 skyddade användare (avsändarens e-postadress).</span><span class="sxs-lookup"><span data-stu-id="0085c-207">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="0085c-208">Du kan inte ange samma skyddade användare i flera principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-208">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="0085c-209">Användarautentisering fungerar inte om avsändaren och mottagaren tidigare kommunicerat via e-post.</span><span class="sxs-lookup"><span data-stu-id="0085c-209">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="0085c-210">Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifierings försök.</span><span class="sxs-lookup"><span data-stu-id="0085c-210">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="0085c-211">**Lägg till domäner att skydda**: Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0085c-211">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0085c-212">**Inkludera automatiskt de domäner jag äger**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-212">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-213">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-213">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0085c-214">**Inkludera anpassade domäner**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-214">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-215">Om du vill aktivera funktionen drar du växlings knappen till **på på** och anger sedan domän namnet (till exempel contoso.com) i rutan **Lägg till domäner** , trycker på RETUR och upprepar efter behov.</span><span class="sxs-lookup"><span data-stu-id="0085c-215">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0085c-216">Du kan ha högst 50 domäner i alla nät fiske principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="0085c-217">**Åtgärder**: Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="0085c-217">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="0085c-218">**Om e-post skickas av en personifierad användare**: Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare att skydda**:</span><span class="sxs-lookup"><span data-stu-id="0085c-218">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="0085c-219">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="0085c-219">**Don't apply any action**</span></span>
       - <span data-ttu-id="0085c-220">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0085c-220">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0085c-221">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="0085c-221">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0085c-222">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0085c-222">**Quarantine the message**</span></span>
       - <span data-ttu-id="0085c-223">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0085c-223">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0085c-224">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0085c-224">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0085c-225">**Om e-post skickas av en domänkontrollant**: Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domänerna som du har angett i **Lägg till domäner för att skydda**:</span><span class="sxs-lookup"><span data-stu-id="0085c-225">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="0085c-226">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="0085c-226">**Don't apply any action**</span></span>
       - <span data-ttu-id="0085c-227">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0085c-227">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0085c-228">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="0085c-228">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0085c-229">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0085c-229">**Quarantine the message**</span></span>
       - <span data-ttu-id="0085c-230">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0085c-230">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0085c-231">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0085c-231">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0085c-232">Klicka på **Aktivera säkerhets tips för personifiering** och konfigurera något av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0085c-232">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0085c-233">**Visa tips för personifierade användare**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-233">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-234">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0085c-235">**Visa tips för personifierade domäner**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-235">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-236">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-236">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0085c-237">**Visa tips för ovanliga tecken**: standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="0085c-237">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="0085c-238">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-238">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0085c-239">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0085c-239">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0085c-240">**Post låda**:</span><span class="sxs-lookup"><span data-stu-id="0085c-240">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="0085c-241">**Aktivera post lådans intelligens?**: standardvärdet är **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-241">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="0085c-242">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="0085c-242">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0085c-243">**Aktivera post låde baserat personifieringstoken?**: den här inställningen är endast tillgänglig om **Aktivera post låda-intelligens?** är **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-243">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0085c-244">I **om e-post skickas av en personifierad användare** kan du ange någon av följande åtgärder som ska vidtas för meddelanden som inte har post lådans intelligens (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="0085c-244">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0085c-245">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="0085c-245">**Don't apply any action**</span></span>
       - <span data-ttu-id="0085c-246">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0085c-246">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0085c-247">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="0085c-247">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0085c-248">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0085c-248">**Quarantine the message**</span></span>
       - <span data-ttu-id="0085c-249">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0085c-249">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0085c-250">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0085c-250">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0085c-251">**Lägga till betrodda avsändare och domäner**: ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="0085c-251">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0085c-252">**Betrodda avsändare**:</span><span class="sxs-lookup"><span data-stu-id="0085c-252">**Trusted senders**:</span></span>

       - <span data-ttu-id="0085c-253">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="0085c-253">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0085c-254">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="0085c-254">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0085c-255">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="0085c-255">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0085c-256">**Betrodda domäner**: ange domän namnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.</span><span class="sxs-lookup"><span data-stu-id="0085c-256">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0085c-257">**Granska dina inställningar**: i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="0085c-257">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0085c-258">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-258">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0085c-259">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="0085c-259">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0085c-260">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="0085c-260">**Protected users**</span></span>
       - <span data-ttu-id="0085c-261">**Skyddade domäner** \> **Lägga till domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="0085c-261">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0085c-262">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="0085c-262">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0085c-263">**Post lådans intelligens**</span><span class="sxs-lookup"><span data-stu-id="0085c-263">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0085c-264">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-264">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0085c-265">**Falska** användare: Klicka på **Redigera** för att aktivera eller inaktivera förfalsknings intelligens, aktivera och inaktivera overifierad avsändare i Outlook och konfigurera åtgärden så att den gäller för meddelanden från blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="0085c-265">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0085c-266">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0085c-266">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0085c-267">Observera att dessa inställningar också är tillgängliga i principer för nätfiske i EOP.</span><span class="sxs-lookup"><span data-stu-id="0085c-267">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0085c-268">**Inställningar för förfalsknings filter**: standardvärdet är **på** och vi rekommenderar att du lämnar det.</span><span class="sxs-lookup"><span data-stu-id="0085c-268">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0085c-269">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="0085c-269">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0085c-270">Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-270">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0085c-271">Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="0085c-271">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0085c-272">Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="0085c-272">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0085c-273">**Aktivera overifierad avsändare**: standardvärdet är **på**.</span><span class="sxs-lookup"><span data-stu-id="0085c-273">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0085c-274">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="0085c-274">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0085c-275">**Åtgärder**: ange vilken åtgärd som ska vidtas för meddelanden som saknar förfalsknings information:</span><span class="sxs-lookup"><span data-stu-id="0085c-275">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0085c-276">**Om e-post skickas av någon som inte har tillåtelse att imitera din domän**:</span><span class="sxs-lookup"><span data-stu-id="0085c-276">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0085c-277">**Flytta meddelandet till mottagarnas skräp post mappar**</span><span class="sxs-lookup"><span data-stu-id="0085c-277">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0085c-278">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0085c-278">**Quarantine the message**</span></span>

   - <span data-ttu-id="0085c-279">**Granska dina inställningar**: i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="0085c-279">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0085c-280">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-280">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0085c-281">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="0085c-281">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="0085c-282">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="0085c-282">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0085c-283">**Aktivera ej autentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="0085c-283">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0085c-284">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-284">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0085c-285">**Avancerade inställningar**: Klicka på **Redigera** för att konfigurera de avancerade gräns värdena för nät fiske tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0085c-285">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0085c-286">Mer information finns i [avancerade nät fiske trösklar i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0085c-286">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0085c-287">**Avancerade nät fiske gränser**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="0085c-287">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="0085c-288">**1 – standard** (det här är standardvärdet).</span><span class="sxs-lookup"><span data-stu-id="0085c-288">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0085c-289">**2 – aggressivt**</span><span class="sxs-lookup"><span data-stu-id="0085c-289">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0085c-290">**3 – mer aggressivt**</span><span class="sxs-lookup"><span data-stu-id="0085c-290">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0085c-291">**4-mest aggressivt**</span><span class="sxs-lookup"><span data-stu-id="0085c-291">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0085c-292">**Granska dina inställningar**: Klicka på **Redigera** för att gå tillbaka till sidan för **avancerade nät fiske gränser** .</span><span class="sxs-lookup"><span data-stu-id="0085c-292">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0085c-293">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0085c-293">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0085c-294">Gå tillbaka till sidan **Redigera din \<Name\> policy** och granska inställningarna och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0085c-294">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-295">Använda säkerhets & Compliance Center för att ändra standard policy för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-295">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0085c-296">Standard policyn för anti-phishing i Microsoft Defender för Office 365 heter Office365 AntiPhish default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-296">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0085c-297">Gör så här om du vill ändra standard principen för anti-nätfiske:</span><span class="sxs-lookup"><span data-stu-id="0085c-297">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0085c-298">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-298">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-299">Klicka på **standard princip** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="0085c-299">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0085c-300">**Standard sidan Redigera policyn för Office365 AntiPhish** visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-300">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0085c-301">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="0085c-301">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="0085c-302">**Falsk identitet**</span><span class="sxs-lookup"><span data-stu-id="0085c-302">**Impersonation**</span></span>
   - <span data-ttu-id="0085c-303">**Falskt**</span><span class="sxs-lookup"><span data-stu-id="0085c-303">**Spoof**</span></span>
   - <span data-ttu-id="0085c-304">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="0085c-304">**Advanced settings**</span></span>

   <span data-ttu-id="0085c-305">Följande inställningar är inte tillgängliga när du ändrar standard princip:</span><span class="sxs-lookup"><span data-stu-id="0085c-305">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0085c-306">Du kan se avsnitt och värden för **princip inställningar** , men det finns inga **redigerings** länkar, så du kan inte ändra inställningarna (princip namn, beskrivning och vem principen gäller för (gäller alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="0085c-306">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0085c-307">Du kan inte ta bort standard principen.</span><span class="sxs-lookup"><span data-stu-id="0085c-307">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0085c-308">Du kan inte ändra prioriteten för standard principen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="0085c-308">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0085c-309">På **standard sidan Redigera en Office365 AntiPhish** du på Inställningar och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0085c-309">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-310">Aktivera eller inaktivera anpassade skydds principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-310">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0085c-311">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-311">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-312">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="0085c-312">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0085c-313">Inaktivera principen genom att dra till **av** .</span><span class="sxs-lookup"><span data-stu-id="0085c-313">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0085c-314">Aktivera principen genom att dra den till **aktiverat** .</span><span class="sxs-lookup"><span data-stu-id="0085c-314">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0085c-315">Du kan inte inaktivera standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0085c-315">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-316">Ange prioritet för anpassade anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-316">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0085c-317">Som standard får anti-nätfiske-principer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="0085c-317">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0085c-318">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="0085c-318">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0085c-319">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="0085c-319">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0085c-320">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-320">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0085c-321">Anpassade principer för anti-nätfiske visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="0085c-321">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0085c-322">Standard policyn för anti-phishing med namnet Office365 AntiPhish standard har värdet **lägst** och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="0085c-322">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0085c-323">**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för skydd mot nätfiske när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="0085c-323">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0085c-324">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln mot Phish (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="0085c-324">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0085c-325">Om du vill ändra prioriteten för en princip klickar du på **öka prioriteten** eller **minska prioriteten** i egenskaperna för principen (du kan inte direkt ändra **prioritets** numret i säkerhets & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="0085c-325">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0085c-326">Det är bara att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="0085c-326">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0085c-327">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-328">Välj den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="0085c-328">Select the policy that you want to modify.</span></span> <span data-ttu-id="0085c-329">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="0085c-329">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0085c-330">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-330">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0085c-331">Den anpassade AntiPhishing-principen med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0085c-331">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0085c-332">Den anpassade AntiPhishing-principen med lägst **prioritet** (till exempel **3**) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0085c-332">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0085c-333">Om du har tre eller fler anpassade nät fiske principer har de värden mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0085c-333">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0085c-334">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="0085c-334">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0085c-335">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0085c-335">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-336">Använd säkerhets & Compliance Center för att Visa anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-336">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0085c-337">I säkerhets & Compliance Center och gå till **hot Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-337">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-338">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="0085c-338">Do one of the following steps:</span></span>

   - <span data-ttu-id="0085c-339">Välj en anpassad Antivirus policy som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="0085c-339">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0085c-340">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="0085c-340">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0085c-341">Klicka på **standard princip** för att Visa standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0085c-341">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0085c-342">**Redigera den utfällbara \<name\> principen** visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="0085c-342">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-343">Använda säkerhets & Compliance Center för att ta bort skydd mot nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-343">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0085c-344">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-344">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0085c-345">Välj den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0085c-345">Select the policy that you want to remove.</span></span> <span data-ttu-id="0085c-346">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="0085c-346">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0085c-347">I redigera den utfällbara **princip \<name\>** som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="0085c-347">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0085c-348">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="0085c-348">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0085c-349">Använda Exchange Online PowerShell för att konfigurera AntiPhishing-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="0085c-349">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0085c-350">Som du redan har beskrivt består en policy mot skräp post och en Phish policy.</span><span class="sxs-lookup"><span data-stu-id="0085c-350">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="0085c-351">I Exchange Online PowerShell är skillnaden mellan policyer för Phish och Phish regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="0085c-351">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0085c-352">Du hanterar policyn för Phish genom att använda cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-Phish-regler med hjälp av cmdlet **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="0085c-352">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0085c-353">I PowerShell skapar du policyn för Phish först och sedan skapar du regeln mot Phish som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="0085c-353">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0085c-354">I PowerShell ändrar du inställningarna i policyn för Phish och anti-Phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="0085c-354">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="0085c-355">När du tar bort en policy för Phish från PowerShell tas motsvarande antiphish-regel inte bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="0085c-355">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0085c-356">Använda PowerShell för att skapa skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0085c-356">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0085c-357">Att skapa en skydds policy i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="0085c-357">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0085c-358">Skapa policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="0085c-358">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="0085c-359">Skapa en regel för Phish som anger den policy för anti-Phish som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="0085c-359">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0085c-360">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0085c-360">**Notes**:</span></span>

- <span data-ttu-id="0085c-361">Du kan skapa en ny Phish regel och koppla en befintlig, icke associerad policy mot anti-Phish-princip till den.</span><span class="sxs-lookup"><span data-stu-id="0085c-361">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0085c-362">En antiphish-regel kan inte kopplas till fler än en anti-Phish princip.</span><span class="sxs-lookup"><span data-stu-id="0085c-362">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0085c-363">Du kan konfigurera följande inställningar i nya principer mot Phish i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="0085c-363">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0085c-364">Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-AntiPhishRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="0085c-364">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="0085c-365">Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya AntiPhishRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="0085c-365">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0085c-366">En ny policy för Phish som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="0085c-366">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0085c-367">Steg 1: använda PowerShell för att skapa en policy för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-367">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0085c-368">Använd följande syntax för att skapa en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="0085c-368">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0085c-369">I det här exemplet skapas policy för Phish forsknings karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0085c-369">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0085c-370">Principen är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0085c-370">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0085c-371">Beskrivningen är: policy för forsknings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="0085c-371">The description is: Research department policy.</span></span>
- <span data-ttu-id="0085c-372">Gör att organisationer-domäner skyddas för alla godkända domäner och riktade domäner för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0085c-372">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0085c-373">Anger Mai Fujito (mfujito@fabrikam.com) som användaren skyddar dig mot.</span><span class="sxs-lookup"><span data-stu-id="0085c-373">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0085c-374">Aktiverar post lådans intelligens.</span><span class="sxs-lookup"><span data-stu-id="0085c-374">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0085c-375">Aktiverar post lådans informations skydd och anger karantän åtgärden.</span><span class="sxs-lookup"><span data-stu-id="0085c-375">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0085c-376">Möjliggör säkerhets tips.</span><span class="sxs-lookup"><span data-stu-id="0085c-376">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0085c-377">Detaljerad information om syntax och parametrar finns i [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0085c-377">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0085c-378">Steg 2: använda PowerShell för att skapa en regel för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-378">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0085c-379">Använd följande syntax för att skapa en Phish-regel:</span><span class="sxs-lookup"><span data-stu-id="0085c-379">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0085c-380">I det här exemplet skapas en Phish regel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="0085c-380">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0085c-381">Regeln associeras med policyn för Phish med namnet forsknings karantän.</span><span class="sxs-lookup"><span data-stu-id="0085c-381">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0085c-382">Regeln gäller för medlemmar i gruppen Research avdelning.</span><span class="sxs-lookup"><span data-stu-id="0085c-382">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0085c-383">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="0085c-383">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0085c-384">Detaljerad information om syntax och parametrar finns i [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0085c-384">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0085c-385">Använda PowerShell för att visa principer mot Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-385">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0085c-386">Använd följande syntax för att visa befintliga principer för Phish:</span><span class="sxs-lookup"><span data-stu-id="0085c-386">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0085c-387">I det här exemplet returneras en sammanfattande lista över alla Phish-principer tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="0085c-387">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0085c-388">I det här exemplet returneras alla egenskapsvärde för Phish policy med namnet chefer.</span><span class="sxs-lookup"><span data-stu-id="0085c-388">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0085c-389">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0085c-389">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0085c-390">Använda PowerShell för att visa regler för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-390">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0085c-391">Använd följande syntax för att visa befintliga regler för Phish:</span><span class="sxs-lookup"><span data-stu-id="0085c-391">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0085c-392">I det här exemplet returneras en sammanfattande lista över alla Phish regler tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="0085c-392">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0085c-393">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="0085c-393">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0085c-394">I det här exemplet returneras alla egenskaps värden för Phish regeln contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="0085c-394">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0085c-395">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0085c-395">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0085c-396">Använda PowerShell för att ändra policyn för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-396">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0085c-397">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en policy för Phish i PowerShell som när du skapar policyn enligt beskrivningen i [steg 1: använda PowerShell för att skapa ett princip policy för Phish](#step-1-use-powershell-to-create-an-anti-phish-policy) .</span><span class="sxs-lookup"><span data-stu-id="0085c-397">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="0085c-398">_MakeDefault_ -växeln som aktiverar den angivna principen till standard principen (tillämpas på alla, alltid **lägst** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en policy mot Phish i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0085c-398">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0085c-399">Du kan inte byta namn på en policy mot Phish ( **set-AntiPhishPolicy** -cmdleten har ingen _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="0085c-399">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0085c-400">När du byter namn på en skydds princip i säkerhets & Compliance Center byter du bara namn på _regeln_ mot Phish.</span><span class="sxs-lookup"><span data-stu-id="0085c-400">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0085c-401">Använd följande syntax för att ändra en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="0085c-401">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0085c-402">Detaljerad information om syntax och parametrar finns i [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0085c-402">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0085c-403">Använda PowerShell för att ändra regler för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-403">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0085c-404">Den enda inställning som inte är tillgänglig när du ändrar en anti-Phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="0085c-404">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0085c-405">Information om hur du aktiverar eller inaktiverar befintliga regler för Phish finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0085c-405">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0085c-406">Annars är inga ytterligare inställningar tillgängliga när du ändrar en Phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0085c-406">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0085c-407">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en antiphish regel](#step-2-use-powershell-to-create-an-anti-phish-rule) -avsnitt tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0085c-407">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0085c-408">Om du vill ändra en Phish regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0085c-408">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0085c-409">Detaljerad information om syntax och parametrar finns i [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0085c-409">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0085c-410">Använda PowerShell för att aktivera eller inaktivera Phish regler</span><span class="sxs-lookup"><span data-stu-id="0085c-410">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0085c-411">Aktivering eller inaktive ring av en Phish regel i PowerShell aktiverar eller inaktiverar hela AntiPhishing-principen (anti-Phish-regeln och den tilldelade anti-Phish-principen).</span><span class="sxs-lookup"><span data-stu-id="0085c-411">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0085c-412">Du kan inte aktivera eller inaktivera standard policyn för skydd mot nätfiske (det gäller alltid alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="0085c-412">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0085c-413">Så här aktiverar eller inaktiverar du en Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0085c-413">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0085c-414">I det här exemplet inaktive ras den Phish marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="0085c-414">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0085c-415">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="0085c-415">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0085c-416">Detaljerad information om syntax och parametrar finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) och [disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0085c-416">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0085c-417">Använd PowerShell för att ange prioriteten för antiphish-regler</span><span class="sxs-lookup"><span data-stu-id="0085c-417">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0085c-418">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="0085c-418">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0085c-419">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="0085c-419">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0085c-420">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="0085c-420">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0085c-421">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="0085c-421">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0085c-422">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="0085c-422">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0085c-423">Använd följande syntax för att ange prioriteten för en anti-Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0085c-423">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0085c-424">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="0085c-424">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0085c-425">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="0085c-425">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0085c-426">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0085c-426">**Notes**:</span></span>

- <span data-ttu-id="0085c-427">Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-AntiPhishRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="0085c-427">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0085c-428">Standard policyn för Phish har ingen motsvarande anti-Phish-regel och har alltid det icke ändrings bara prioritet svärdet **lägst**.</span><span class="sxs-lookup"><span data-stu-id="0085c-428">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0085c-429">Använda PowerShell för att ta bort principer för Phish</span><span class="sxs-lookup"><span data-stu-id="0085c-429">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0085c-430">När du använder PowerShell för att ta bort en policy för Phish, tas inte motsvarande antiphish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="0085c-430">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0085c-431">Använd följande syntax för att ta bort en policy för Phish i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0085c-431">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0085c-432">I det här exemplet tas policyn för Phish bort från marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="0085c-432">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0085c-433">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0085c-433">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0085c-434">Använda PowerShell för att ta bort Phish regler</span><span class="sxs-lookup"><span data-stu-id="0085c-434">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0085c-435">När du använder PowerShell för att ta bort en antiphish-regel tas motsvarande policy mot Phish inte bort.</span><span class="sxs-lookup"><span data-stu-id="0085c-435">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0085c-436">Om du vill ta bort en Phish regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0085c-436">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0085c-437">Det här exemplet tar bort regeln marknadsförings avdelning för Phish.</span><span class="sxs-lookup"><span data-stu-id="0085c-437">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0085c-438">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0085c-438">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0085c-439">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="0085c-439">How do you know these procedures worked?</span></span>

<span data-ttu-id="0085c-440">Gör något av följande för att kontrol lera att du har konfigurerat skydd mot nätfiske i Microsoft Defender för Office 365:</span><span class="sxs-lookup"><span data-stu-id="0085c-440">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="0085c-441">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="0085c-441">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0085c-442">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="0085c-442">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0085c-443">Gör något av följande om du vill visa mer information:</span><span class="sxs-lookup"><span data-stu-id="0085c-443">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0085c-444">Välj en princip i listan och visa detaljerna i den utfällbara informationen.</span><span class="sxs-lookup"><span data-stu-id="0085c-444">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0085c-445">Klicka på **standard policy** och se informationen i utfällbar form.</span><span class="sxs-lookup"><span data-stu-id="0085c-445">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0085c-446">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="0085c-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
