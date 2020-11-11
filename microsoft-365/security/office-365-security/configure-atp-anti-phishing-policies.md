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
ms.openlocfilehash: 7665d0dc475909d04da209aa6c1cd6b12378f8a9
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993394"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-103">Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff3f0-104">Anti-nätfiske-principer i [Microsoft Defender för Office 365](office-365-atp.md) skyddar din organisation från illasinnade nätfiske-attacker och andra typer av nät fiske attacker.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="ff3f0-105">Mer information om skillnaderna mellan anti-nätfiske-principer i Exchange Online Protection (EOP) och anti-nätfiske-principer i Microsoft Defender för Office 365 finns i [skydd mot nätfiske](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="ff3f0-106">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ff3f0-107">Om du vill ha större precision kan du även skapa anpassade AntiPhishing-principer som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ff3f0-108">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ff3f0-109">Du kan konfigurera anti-nätfiske-principer i säkerhets & efterlevnads Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="ff3f0-110">Information om hur du konfigurerar de begränsade begränsningarna för nätfiske-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga organisationer utan Microsoft Defender för Office 365) finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="ff3f0-111">De grundläggande delarna i en Antivirus policy är:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ff3f0-112">**Policyn för Phish** : anger skydds alternativen för nätfiske för att aktivera eller inaktivera och åtgärderna för att tillämpa alternativ.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ff3f0-113">**Regeln för Phish** : anger de prioritets-och mottagar filter (som principen gäller för) för en policy mot anti-Phish.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ff3f0-114">Skillnaden mellan dessa två element är inte uppenbar när du hanterar skydd mot nätfiske i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ff3f0-115">När du skapar en princip skapar du verkligen en Phish regel och tillhör ande policy för anti-Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ff3f0-116">När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra Phish regel.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ff3f0-117">Alla andra inställningar ändra den associerade policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ff3f0-118">När du tar bort en princip tas Phish-regeln och den associerade anti-Phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ff3f0-119">I Exchange Online PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ff3f0-120">Mer information finns i [använda Exchange Online PowerShell för att konfigurera skydd mot nätfiske-principer i avsnittet Microsoft Defender för Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="ff3f0-121">Alla Microsoft Defender för Office 365-organisationer har en inbyggd policy för anti-nätfiske som heter Office365 AntiPhish standard och har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ff3f0-122">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-Phish-regel (mottagar filter) som är kopplade till principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ff3f0-123">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ff3f0-124">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ff3f0-125">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ff3f0-126">För att öka effektiviteten för skydd mot nätfiske i Microsoft Defender för Office 365 kan du skapa anpassade skydds principer med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ff3f0-127">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ff3f0-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ff3f0-128">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ff3f0-129">Använd om du vill gå direkt till sidan **ATP-nätfiske** <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ff3f0-130">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ff3f0-131">Du måste tilldelas behörigheter innan du kan utföra åtgärderna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="ff3f0-132">För att lägga till, ändra och ta bort skydd mot nätfiske måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ff3f0-133">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ff3f0-134">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ff3f0-135">För skrivskyddad åtkomst till principer mot nätfiske måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ff3f0-136">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ff3f0-137">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="ff3f0-138">För våra rekommenderade inställningar för skydd mot nätfiske i Microsoft Defender för Office 365, se [AntiPhishing-principer i inställningar för Defender för Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="ff3f0-139">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="ff3f0-140">Information om var anti-nätfiske-principer tillämpas i filtrerings pipeline finns i [order och prioritetsordning för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-141">Använda säkerhets & Compliance Center för att skapa skydd mot nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ff3f0-142">Om du skapar en anpassad skydds princip i säkerhets & Compliance Center skapar regeln mot Phish och tillhör ande policy mot Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ff3f0-143">När du skapar en AntiPhishing-princip kan du bara ange princip namnet, beskrivningen och det mottagar filter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ff3f0-144">När du har skapat den här principen kan du ändra principen för att ändra eller granska standardinställningarna för nät fiske inställningar.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ff3f0-145">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-146">Klicka på **skapa** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ff3f0-147">Guiden **skapa en ny policy för skydd mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ff3f0-148">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ff3f0-149">**Namn** : Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ff3f0-150">**Beskrivning** : Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ff3f0-151">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ff3f0-152">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ff3f0-153">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ff3f0-154">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="ff3f0-155">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="ff3f0-156">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-156">Click **Add a condition**.</span></span> <span data-ttu-id="ff3f0-157">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="ff3f0-158">**Mottagaren är** : anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ff3f0-159">**Mottagaren är medlem i** : anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ff3f0-160">**Mottagar domänen är** : anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="ff3f0-161">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ff3f0-162">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ff3f0-163">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ff3f0-164">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ff3f0-165">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ff3f0-166">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ff3f0-167">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ff3f0-168">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ff3f0-169">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ff3f0-170">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ff3f0-171">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ff3f0-172">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ff3f0-173">När du är klar klickar du på **skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ff3f0-174">Klicka på **OK** i bekräftelse dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ff3f0-175">När du har skapat AntiPhishing-principen med dessa allmänna inställningar följer du anvisningarna i nästa avsnitt för att konfigurera skydds inställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-176">Använda säkerhets & Compliance Center för att ändra anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ff3f0-177">Använd följande procedurer för att ändra anti-nätfiske-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ff3f0-178">Om du inte redan har gjort det öppnar du säkerhets & efterlevnad och går till **hot Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-179">Välj den anpassade Antivirus princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ff3f0-180">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ff3f0-181">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ff3f0-182">Om du klickar på **Redigera** i ett avsnitt får du till gång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ff3f0-183">Följande anvisningar visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ff3f0-184">När du har klickat på **Redigera** i ett avsnitt visas de tillgängliga inställningarna i ett guide format, men du kan hoppa mellan sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Avbryt** eller **Stäng** Stäng-ikonen om du vill ![ ](../../media/scc-remove-icon.png) gå tillbaka till sidan **Redigera din policy \<name\>** ).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ff3f0-185">**Princip inställning** : Klicka på **Redigera** om du vill ändra samma inställningar som fanns tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="ff3f0-186">**Name**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-186">**Name**</span></span>
   - <span data-ttu-id="ff3f0-187">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-187">**Description**</span></span>
   - <span data-ttu-id="ff3f0-188">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-188">**Applied to**</span></span>
   - <span data-ttu-id="ff3f0-189">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-189">**Review your settings**</span></span>

   <span data-ttu-id="ff3f0-190">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ff3f0-191">**Personifiering** : Klicka på **Redigera** för att ändra de skyddade avsändarna och de skyddade domänerna i principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="ff3f0-192">Dessa inställningar är ett villkor för den princip som identifierar falska avsändare att leta efter (individuellt eller efter domän) i från-adressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="ff3f0-193">Mer information finns i [Inställningar för personifiering i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ff3f0-194">**Lägg till användare att skydda** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-195">Aktivera **den genom att dra den till den** och sedan klicka på knappen **Lägg till användare** som visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="ff3f0-196">I **Lägg till** utfällda användare som visas konfigurerar du följande värden:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="ff3f0-197">**E-post adress** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-197">**Email address** :</span></span>

       - <span data-ttu-id="ff3f0-198">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-198">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ff3f0-199">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-199">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ff3f0-200">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ff3f0-201">**Namn** : det här värdet fylls i baserat på e-postadressen du valde, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="ff3f0-202">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="ff3f0-203">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="ff3f0-204">I varje skydds princip kan du ange högst 60 skyddade användare (avsändarens e-postadress).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-204">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="ff3f0-205">Du kan inte ange samma skyddade användare i flera principer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-205">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="ff3f0-206">Användarautentisering fungerar inte om avsändaren och mottagaren tidigare kommunicerat via e-post.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-206">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="ff3f0-207">Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifierings försök.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-207">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="ff3f0-208">**Lägg till domäner att skydda** : Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-208">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="ff3f0-209">**Inkludera automatiskt de domäner jag äger** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-209">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-210">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-210">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ff3f0-211">**Inkludera anpassade domäner** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-211">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-212">Om du vill aktivera funktionen drar du växlings knappen till **på på** och anger sedan domän namnet (till exempel contoso.com) i rutan **Lägg till domäner** , trycker på RETUR och upprepar efter behov.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-212">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ff3f0-213">Du kan ha högst 50 domäner i alla nät fiske principer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-213">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="ff3f0-214">**Åtgärder** : Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-214">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="ff3f0-215">**Om e-post skickas av en personifierad användare** : Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare att skydda** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-215">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="ff3f0-216">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-216">**Don't apply any action**</span></span>
       - <span data-ttu-id="ff3f0-217">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-217">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ff3f0-218">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-218">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ff3f0-219">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-219">**Quarantine the message**</span></span>
       - <span data-ttu-id="ff3f0-220">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-220">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ff3f0-221">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-221">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ff3f0-222">**Om e-post skickas av en domänkontrollant** : Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domänerna som du har angett i **Lägg till domäner för att skydda** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-222">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

       - <span data-ttu-id="ff3f0-223">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="ff3f0-224">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ff3f0-225">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-225">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ff3f0-226">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="ff3f0-227">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ff3f0-228">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-228">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ff3f0-229">Klicka på **Aktivera säkerhets tips för personifiering** och konfigurera något av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-229">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="ff3f0-230">**Visa tips för personifierade användare** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-230">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-231">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ff3f0-232">**Visa tips för personifierade domäner** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-232">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-233">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-233">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ff3f0-234">**Visa tips för ovanliga tecken** : standardvärdet är **inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-234">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="ff3f0-235">Aktivera den genom att dra den till **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-235">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="ff3f0-236">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-236">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ff3f0-237">**Post låda** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-237">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="ff3f0-238">**Aktivera post lådans intelligens?** : standardvärdet är **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-238">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="ff3f0-239">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-239">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="ff3f0-240">**Aktivera post låde baserat personifieringstoken?** : den här inställningen är endast tillgänglig om **Aktivera post låda-intelligens?** är **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-240">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="ff3f0-241">I **om e-post skickas av en personifierad användare** kan du ange någon av följande åtgärder som ska vidtas för meddelanden som inte har post lådans intelligens (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="ff3f0-241">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="ff3f0-242">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-242">**Don't apply any action**</span></span>
       - <span data-ttu-id="ff3f0-243">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-243">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ff3f0-244">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-244">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ff3f0-245">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-245">**Quarantine the message**</span></span>
       - <span data-ttu-id="ff3f0-246">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-246">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ff3f0-247">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-247">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ff3f0-248">**Lägga till betrodda avsändare och domäner** : ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-248">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="ff3f0-249">**Betrodda avsändare** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-249">**Trusted senders** :</span></span>

       - <span data-ttu-id="ff3f0-250">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-250">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ff3f0-251">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-251">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ff3f0-252">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-252">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ff3f0-253">**Betrodda domäner** : ange domän namnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-253">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="ff3f0-254">**Granska dina inställningar** : i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-254">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ff3f0-255">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-255">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ff3f0-256">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-256">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ff3f0-257">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-257">**Protected users**</span></span>
       - <span data-ttu-id="ff3f0-258">**Skyddade domäner** \> **Lägga till domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-258">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="ff3f0-259">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="ff3f0-259">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="ff3f0-260">**Post lådans intelligens**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-260">**Mailbox intelligence**</span></span>

   <span data-ttu-id="ff3f0-261">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-261">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ff3f0-262">**Falska** användare: Klicka på **Redigera** för att aktivera eller inaktivera förfalsknings intelligens, aktivera och inaktivera overifierad avsändare i Outlook och konfigurera åtgärden så att den gäller för meddelanden från blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-262">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ff3f0-263">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-263">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ff3f0-264">Observera att dessa inställningar också är tillgängliga i principer för nätfiske i EOP.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-264">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="ff3f0-265">**Inställningar för förfalsknings filter** : standardvärdet är **på** och vi rekommenderar att du lämnar det.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-265">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="ff3f0-266">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-266">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ff3f0-267">Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-267">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ff3f0-268">Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-268">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ff3f0-269">Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-269">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ff3f0-270">**Aktivera overifierad avsändare** : standardvärdet är **på**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-270">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="ff3f0-271">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-271">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ff3f0-272">**Åtgärder** : ange vilken åtgärd som ska vidtas för meddelanden som saknar förfalsknings information:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-272">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ff3f0-273">**Om e-post skickas av någon som inte har tillåtelse att imitera din domän** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-273">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="ff3f0-274">**Flytta meddelandet till mottagarnas skräp post mappar**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-274">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ff3f0-275">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-275">**Quarantine the message**</span></span>

   - <span data-ttu-id="ff3f0-276">**Granska dina inställningar** : i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-276">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ff3f0-277">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-277">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ff3f0-278">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-278">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="ff3f0-279">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-279">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ff3f0-280">**Aktivera ej autentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-280">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ff3f0-281">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-281">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="ff3f0-282">**Avancerade inställningar** : Klicka på **Redigera** för att konfigurera de avancerade gräns värdena för nät fiske tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-282">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="ff3f0-283">Mer information finns i [avancerade nät fiske trösklar i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-283">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="ff3f0-284">**Avancerade nät fiske gränser** : Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-284">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="ff3f0-285">**1 – standard** (det här är standardvärdet).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-285">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="ff3f0-286">**2 – aggressivt**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-286">**2 - Aggressive**</span></span>
   - <span data-ttu-id="ff3f0-287">**3 – mer aggressivt**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-287">**3 - More aggressive**</span></span>
   - <span data-ttu-id="ff3f0-288">**4-mest aggressivt**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-288">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="ff3f0-289">**Granska dina inställningar** : Klicka på **Redigera** för att gå tillbaka till sidan för **avancerade nät fiske gränser** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-289">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="ff3f0-290">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-290">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="ff3f0-291">Gå tillbaka till sidan **Redigera din \<Name\> policy** och granska inställningarna och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-291">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-292">Använda säkerhets & Compliance Center för att ändra standard policy för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-292">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ff3f0-293">Standard policyn för anti-phishing i Microsoft Defender för Office 365 heter Office365 AntiPhish default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-293">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ff3f0-294">Gör så här om du vill ändra standard principen för anti-nätfiske:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-294">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ff3f0-295">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-295">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-296">Klicka på **standard princip** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-296">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ff3f0-297">**Standard sidan Redigera policyn för Office365 AntiPhish** visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-297">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ff3f0-298">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="ff3f0-298">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="ff3f0-299">**Falsk identitet**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-299">**Impersonation**</span></span>
   - <span data-ttu-id="ff3f0-300">**Falskt**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-300">**Spoof**</span></span>
   - <span data-ttu-id="ff3f0-301">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="ff3f0-301">**Advanced settings**</span></span>

   <span data-ttu-id="ff3f0-302">Följande inställningar är inte tillgängliga när du ändrar standard princip:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-302">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ff3f0-303">Du kan se avsnitt och värden för **princip inställningar** , men det finns inga **redigerings** länkar, så du kan inte ändra inställningarna (princip namn, beskrivning och vem principen gäller för (gäller alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-303">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ff3f0-304">Du kan inte ta bort standard principen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-304">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ff3f0-305">Du kan inte ändra prioriteten för standard principen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-305">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ff3f0-306">På **standard sidan Redigera en Office365 AntiPhish** du på Inställningar och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-306">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-307">Aktivera eller inaktivera anpassade skydds principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-307">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ff3f0-308">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-309">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-309">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ff3f0-310">Inaktivera principen genom att dra till **av** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-310">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ff3f0-311">Aktivera principen genom att dra den till **aktiverat** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-311">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ff3f0-312">Du kan inte inaktivera standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-312">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-313">Ange prioritet för anpassade anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-313">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ff3f0-314">Som standard får anti-nätfiske-principer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-314">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ff3f0-315">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-315">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ff3f0-316">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-316">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ff3f0-317">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-317">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ff3f0-318">Anpassade principer för anti-nätfiske visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-318">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ff3f0-319">Standard policyn för anti-phishing med namnet Office365 AntiPhish standard har värdet **lägst** och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="ff3f0-320">**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för skydd mot nätfiske när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-320">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ff3f0-321">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln mot Phish (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ff3f0-322">Om du vill ändra prioriteten för en princip klickar du på **öka prioriteten** eller **minska prioriteten** i egenskaperna för principen (du kan inte direkt ändra **prioritets** numret i säkerhets & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ff3f0-323">Det är bara att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ff3f0-324">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-325">Välj den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="ff3f0-326">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ff3f0-327">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ff3f0-328">Den anpassade AntiPhishing-principen med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-328">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ff3f0-329">Den anpassade AntiPhishing-principen med lägst **prioritet** (till exempel **3** ) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-329">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ff3f0-330">Om du har tre eller fler anpassade nät fiske principer har de värden mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ff3f0-331">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ff3f0-332">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-333">Använd säkerhets & Compliance Center för att Visa anti-nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-333">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ff3f0-334">I säkerhets & Compliance Center och gå till **hot Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-335">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="ff3f0-336">Välj en anpassad Antivirus policy som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-336">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ff3f0-337">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ff3f0-338">Klicka på **standard princip** för att Visa standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ff3f0-339">**Redigera den utfällbara \<name\> principen** visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-340">Använda säkerhets & Compliance Center för att ta bort skydd mot nätfiske-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-340">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="ff3f0-341">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ff3f0-342">Välj den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="ff3f0-343">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ff3f0-344">I redigera den utfällbara **princip \<name\>** som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ff3f0-345">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ff3f0-346">Använda Exchange Online PowerShell för att konfigurera AntiPhishing-principer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ff3f0-346">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ff3f0-347">Som du redan har beskrivt består en policy mot skräp post och en Phish policy.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-347">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ff3f0-348">I Exchange Online PowerShell är skillnaden mellan policyer för Phish och Phish regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-348">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ff3f0-349">Du hanterar policyn för Phish genom att använda cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-Phish-regler med hjälp av cmdlet **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-349">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ff3f0-350">I PowerShell skapar du policyn för Phish först och sedan skapar du regeln mot Phish som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-350">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ff3f0-351">I PowerShell ändrar du inställningarna i policyn för Phish och anti-Phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-351">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ff3f0-352">När du tar bort en policy för Phish från PowerShell tas motsvarande antiphish-regel inte bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-352">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ff3f0-353">Använda PowerShell för att skapa skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ff3f0-353">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ff3f0-354">Att skapa en skydds policy i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-354">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ff3f0-355">Skapa policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-355">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ff3f0-356">Skapa en regel för Phish som anger den policy för anti-Phish som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-356">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ff3f0-357">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-357">**Notes** :</span></span>

- <span data-ttu-id="ff3f0-358">Du kan skapa en ny Phish regel och koppla en befintlig, icke associerad policy mot anti-Phish-princip till den.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-358">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ff3f0-359">En antiphish-regel kan inte kopplas till fler än en anti-Phish princip.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-359">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ff3f0-360">Du kan konfigurera följande inställningar i nya principer mot Phish i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-360">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ff3f0-361">Skapa den nya principen som inaktive rad ( _aktive rad_ `$false` på **New-AntiPhishRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-361">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ff3f0-362">Ange prioriteten för principen när den skapas ( _prioritet_ _\<Number\>_ ) på den **nya AntiPhishRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-362">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ff3f0-363">En ny policy för Phish som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-363">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ff3f0-364">Steg 1: använda PowerShell för att skapa en policy för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-364">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ff3f0-365">Använd följande syntax för att skapa en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-365">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ff3f0-366">I det här exemplet skapas policy för Phish forsknings karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-366">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ff3f0-367">Principen är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-367">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ff3f0-368">Beskrivningen är: policy för forsknings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-368">The description is: Research department policy.</span></span>
- <span data-ttu-id="ff3f0-369">Gör att organisationer-domäner skyddas för alla godkända domäner och riktade domäner för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-369">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="ff3f0-370">Anger Mai Fujito (mfujito@fabrikam.com) som användaren skyddar dig mot.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-370">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="ff3f0-371">Aktiverar post lådans intelligens.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-371">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="ff3f0-372">Aktiverar post lådans informations skydd och anger karantän åtgärden.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-372">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="ff3f0-373">Möjliggör säkerhets tips.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-373">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="ff3f0-374">Detaljerad information om syntax och parametrar finns i [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-374">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ff3f0-375">Steg 2: använda PowerShell för att skapa en regel för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-375">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ff3f0-376">Använd följande syntax för att skapa en Phish-regel:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-376">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ff3f0-377">I det här exemplet skapas en Phish regel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-377">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ff3f0-378">Regeln associeras med policyn för Phish med namnet forsknings karantän.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-378">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ff3f0-379">Regeln gäller för medlemmar i gruppen Research avdelning.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-379">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ff3f0-380">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-380">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ff3f0-381">Detaljerad information om syntax och parametrar finns i [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-381">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ff3f0-382">Använda PowerShell för att visa principer mot Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-382">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ff3f0-383">Använd följande syntax för att visa befintliga principer för Phish:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-383">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ff3f0-384">I det här exemplet returneras en sammanfattande lista över alla Phish-principer tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-384">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ff3f0-385">I det här exemplet returneras alla egenskapsvärde för Phish policy med namnet chefer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-385">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ff3f0-386">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-386">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ff3f0-387">Använda PowerShell för att visa regler för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-387">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ff3f0-388">Använd följande syntax för att visa befintliga regler för Phish:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-388">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ff3f0-389">I det här exemplet returneras en sammanfattande lista över alla Phish regler tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-389">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ff3f0-390">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-390">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ff3f0-391">I det här exemplet returneras alla egenskaps värden för Phish regeln contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-391">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ff3f0-392">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-392">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ff3f0-393">Använda PowerShell för att ändra policyn för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-393">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ff3f0-394">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en policy för Phish i PowerShell som när du skapar policyn enligt beskrivningen i [steg 1: använda PowerShell för att skapa ett princip policy för Phish](#step-1-use-powershell-to-create-an-anti-phish-policy) .</span><span class="sxs-lookup"><span data-stu-id="ff3f0-394">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="ff3f0-395">_MakeDefault_ -växeln som aktiverar den angivna principen till standard principen (tillämpas på alla, alltid **lägst** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en policy mot Phish i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-395">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ff3f0-396">Du kan inte byta namn på en policy mot Phish ( **set-AntiPhishPolicy** -cmdleten har ingen _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-396">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ff3f0-397">När du byter namn på en skydds princip i säkerhets & Compliance Center byter du bara namn på _regeln_ mot Phish.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-397">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ff3f0-398">Använd följande syntax för att ändra en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-398">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ff3f0-399">Detaljerad information om syntax och parametrar finns i [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-399">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ff3f0-400">Använda PowerShell för att ändra regler för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-400">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ff3f0-401">Den enda inställning som inte är tillgänglig när du ändrar en anti-Phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-401">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ff3f0-402">Information om hur du aktiverar eller inaktiverar befintliga regler för Phish finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-402">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ff3f0-403">Annars är inga ytterligare inställningar tillgängliga när du ändrar en Phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-403">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ff3f0-404">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en antiphish regel](#step-2-use-powershell-to-create-an-anti-phish-rule) -avsnitt tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-404">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ff3f0-405">Om du vill ändra en Phish regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-405">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ff3f0-406">Detaljerad information om syntax och parametrar finns i [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-406">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ff3f0-407">Använda PowerShell för att aktivera eller inaktivera Phish regler</span><span class="sxs-lookup"><span data-stu-id="ff3f0-407">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ff3f0-408">Aktivering eller inaktive ring av en Phish regel i PowerShell aktiverar eller inaktiverar hela AntiPhishing-principen (anti-Phish-regeln och den tilldelade anti-Phish-principen).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-408">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ff3f0-409">Du kan inte aktivera eller inaktivera standard policyn för skydd mot nätfiske (det gäller alltid alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-409">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ff3f0-410">Så här aktiverar eller inaktiverar du en Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-410">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ff3f0-411">I det här exemplet inaktive ras den Phish marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-411">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ff3f0-412">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-412">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ff3f0-413">Detaljerad information om syntax och parametrar finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) och [disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-413">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ff3f0-414">Använd PowerShell för att ange prioriteten för antiphish-regler</span><span class="sxs-lookup"><span data-stu-id="ff3f0-414">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ff3f0-415">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-415">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ff3f0-416">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-416">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ff3f0-417">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-417">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ff3f0-418">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-418">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ff3f0-419">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-419">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ff3f0-420">Använd följande syntax för att ange prioriteten för en anti-Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-420">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ff3f0-421">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-421">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ff3f0-422">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="ff3f0-422">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ff3f0-423">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="ff3f0-423">**Notes** :</span></span>

- <span data-ttu-id="ff3f0-424">Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-AntiPhishRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-424">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ff3f0-425">Standard policyn för Phish har ingen motsvarande anti-Phish-regel och har alltid det icke ändrings bara prioritet svärdet **lägst**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-425">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ff3f0-426">Använda PowerShell för att ta bort principer för Phish</span><span class="sxs-lookup"><span data-stu-id="ff3f0-426">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ff3f0-427">När du använder PowerShell för att ta bort en policy för Phish, tas inte motsvarande antiphish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-427">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ff3f0-428">Använd följande syntax för att ta bort en policy för Phish i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-428">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ff3f0-429">I det här exemplet tas policyn för Phish bort från marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-429">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ff3f0-430">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-430">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ff3f0-431">Använda PowerShell för att ta bort Phish regler</span><span class="sxs-lookup"><span data-stu-id="ff3f0-431">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ff3f0-432">När du använder PowerShell för att ta bort en antiphish-regel tas motsvarande policy mot Phish inte bort.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-432">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ff3f0-433">Om du vill ta bort en Phish regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-433">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ff3f0-434">Det här exemplet tar bort regeln marknadsförings avdelning för Phish.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-434">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ff3f0-435">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ff3f0-435">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ff3f0-436">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="ff3f0-436">How do you know these procedures worked?</span></span>

<span data-ttu-id="ff3f0-437">Gör något av följande för att kontrol lera att du har konfigurerat skydd mot nätfiske i Microsoft Defender för Office 365:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-437">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ff3f0-438">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-438">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="ff3f0-439">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-439">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ff3f0-440">Gör något av följande om du vill visa mer information:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-440">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ff3f0-441">Välj en princip i listan och visa detaljerna i den utfällbara informationen.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-441">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ff3f0-442">Klicka på **standard policy** och se informationen i utfällbar form.</span><span class="sxs-lookup"><span data-stu-id="ff3f0-442">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ff3f0-443">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ff3f0-443">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
