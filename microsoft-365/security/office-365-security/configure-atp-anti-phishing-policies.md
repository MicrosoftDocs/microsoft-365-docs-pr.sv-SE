---
title: Konfigurera principer för ATP-skydd mot nätfiske
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
description: Administratörer kan läsa mer om hur du skapar, ändrar och tar bort de avancerade AntiPhishing-principer som är tillgängliga i organisationer med Office 365-tjänsten för avancerat skydd (Office 365 ATP).
ms.openlocfilehash: d6655089556f7268222dc47e2196f8aa1fc3da4e
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769226"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-103">Konfigurera principer för ATP-skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="7c758-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7c758-104">ATP anti-phishing-principer är en del av [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7c758-105">ATP anti-phishing-principer kan bidra till att skydda din organisation från illasinnade nätfiske-attacker och andra typer av nät fiske attacker.</span><span class="sxs-lookup"><span data-stu-id="7c758-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="7c758-106">Mer information om skillnaderna mellan anti-nätfiske-principer i Exchange Online Protection (EOP) och ATP-nätfiske-regler finns i [skydd mot nätfiske](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="7c758-107">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard policyn för ATP-nätfiske.</span><span class="sxs-lookup"><span data-stu-id="7c758-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="7c758-108">För högre precision kan du också skapa anpassade tilläggs principer för ATP som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7c758-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="7c758-109">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="7c758-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="7c758-110">Du kan konfigurera AntiPhishing-principer för ATP i säkerhets & Compliance Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c758-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="7c758-111">Information om hur du konfigurerar de begränsade begränsningarna för nätfiske-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga Microsoft 365-organisationer utan Office 365 ATP) finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="7c758-112">ATP anti-nätfiske-principer i säkerhets & Compliance Center kontra PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c758-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="7c758-113">De grundläggande delarna i en policy för ATP-anti-phishing är:</span><span class="sxs-lookup"><span data-stu-id="7c758-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="7c758-114">**Policyn för Phish** : anger skydds alternativen för nätfiske för att aktivera eller inaktivera och åtgärderna för att tillämpa alternativ.</span><span class="sxs-lookup"><span data-stu-id="7c758-114">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="7c758-115">**Regeln för Phish** : anger de prioritets-och mottagar filter (som principen gäller för) för en policy mot anti-Phish.</span><span class="sxs-lookup"><span data-stu-id="7c758-115">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="7c758-116">Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för ATP-nätfiske i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="7c758-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="7c758-117">När du skapar en princip skapar du verkligen en Phish regel och tillhör ande policy för anti-Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="7c758-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="7c758-118">När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra Phish regel.</span><span class="sxs-lookup"><span data-stu-id="7c758-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="7c758-119">Alla andra inställningar ändra den associerade policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="7c758-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="7c758-120">När du tar bort en princip tas Phish-regeln och den associerade anti-Phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="7c758-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="7c758-121">I Exchange Online PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="7c758-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="7c758-122">Mer information finns i [använda Exchange Online PowerShell för att konfigurera principer för Stöldskydd mot nätfiske](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7c758-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="7c758-123">Varje Office 365 ATP-organisation har en inbyggd ATP-Antivirus princip som heter Office365 AntiPhish standard och har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="7c758-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="7c758-124">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-Phish-regel (mottagar filter) som är kopplade till principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="7c758-125">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="7c758-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="7c758-126">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="7c758-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="7c758-127">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="7c758-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="7c758-128">För att öka effektiviteten för skydd mot nätfiske kan du skapa anpassade principer för ATP-nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="7c758-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7c758-129">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="7c758-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7c758-130">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7c758-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7c758-131">Använd om du vill gå direkt till sidan **ATP-nätfiske** <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="7c758-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="7c758-132">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7c758-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7c758-133">Du måste tilldelas behörigheter innan du kan utföra åtgärderna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="7c758-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="7c758-134">För att lägga till, ändra och ta bort ATP-Antivirus principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="7c758-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="7c758-135">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="7c758-136">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="7c758-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="7c758-137">Om du vill ha skrivskyddad åtkomst till ATP-Antivirus principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="7c758-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="7c758-138">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="7c758-139">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="7c758-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="7c758-140">För våra rekommenderade inställningar för principer för ATP-nätfiske läser du [princip inställningar för ATP-nätfiske](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="7c758-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="7c758-141">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7c758-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="7c758-142">Information om var anti-nätfiske-principer tillämpas i filtrerings pipeline finns i [order och prioritetsordning för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-143">Skapa ATP-Antivirus policyer med hjälp av säkerhets &</span><span class="sxs-lookup"><span data-stu-id="7c758-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="7c758-144">Om du skapar en egen Antivirus policy för ATP i säkerhets & Compliance Center skapar regeln mot Phish och tillhör ande policy mot Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="7c758-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="7c758-145">När du skapar en Antivirus policy med ATP kan du bara ange princip namnet, beskrivningen och det mottagar filter som identifierar vem policyn gäller för.</span><span class="sxs-lookup"><span data-stu-id="7c758-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="7c758-146">När du har skapat den här principen kan du ändra principen för att ändra eller granska standardinställningarna för nät fiske inställningar.</span><span class="sxs-lookup"><span data-stu-id="7c758-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="7c758-147">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-148">Klicka på **skapa** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-148">On the **Anti-phishing** page, click **Create** .</span></span>

3. <span data-ttu-id="7c758-149">Guiden **skapa en ny policy för skydd mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="7c758-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="7c758-150">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7c758-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="7c758-151">**Namn** : Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-151">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="7c758-152">**Beskrivning** : Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-152">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="7c758-153">När du är klar klickar du på **Nästa** .</span><span class="sxs-lookup"><span data-stu-id="7c758-153">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="7c758-154">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="7c758-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="7c758-155">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="7c758-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="7c758-156">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="7c758-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="7c758-157">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="7c758-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="7c758-158">Klicka på **Lägg till ett villkor** .</span><span class="sxs-lookup"><span data-stu-id="7c758-158">Click **Add a condition** .</span></span> <span data-ttu-id="7c758-159">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :</span><span class="sxs-lookup"><span data-stu-id="7c758-159">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="7c758-160">**Mottagaren är** : anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7c758-160">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="7c758-161">**Mottagaren är medlem i** : anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7c758-161">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="7c758-162">**Mottagar domänen är** : anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7c758-162">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="7c758-163">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="7c758-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="7c758-164">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="7c758-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="7c758-165">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="7c758-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="7c758-166">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="7c758-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="7c758-167">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="7c758-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="7c758-168">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7c758-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="7c758-169">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om** .</span><span class="sxs-lookup"><span data-stu-id="7c758-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if** .</span></span>

   <span data-ttu-id="7c758-170">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om** .</span><span class="sxs-lookup"><span data-stu-id="7c758-170">To add exceptions, click **Add a condition** and select an exception under **Except if** .</span></span> <span data-ttu-id="7c758-171">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="7c758-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="7c758-172">När du är klar klickar du på **Nästa** .</span><span class="sxs-lookup"><span data-stu-id="7c758-172">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="7c758-173">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="7c758-174">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="7c758-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="7c758-175">När du är klar klickar du på **skapa den här principen** .</span><span class="sxs-lookup"><span data-stu-id="7c758-175">When you're finished, click **Create this policy** .</span></span>

6. <span data-ttu-id="7c758-176">Klicka på **OK** i bekräftelse dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="7c758-177">När du har skapat säkerhets policyn för ATP med dessa allmänna princip inställningar, följer du anvisningarna i nästa avsnitt för att konfigurera skydds inställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-178">Använd säkerhets & Compliance Center för att ändra principer för ATP-Antivirus</span><span class="sxs-lookup"><span data-stu-id="7c758-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="7c758-179">Gör så här om du vill ändra ATP-Antivirus principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="7c758-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="7c758-180">Om du inte redan har gjort det öppnar du säkerhets & efterlevnad och går till **hot Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-181">Välj den anpassade Antivirus policy för ATP som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="7c758-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="7c758-182">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="7c758-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7c758-183">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="7c758-184">Om du klickar på **Redigera** i ett avsnitt får du till gång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7c758-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="7c758-185">Följande anvisningar visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="7c758-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="7c758-186">När du har klickat på **Redigera** i ett avsnitt visas de tillgängliga inställningarna i ett guide format, men du kan hoppa mellan sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Avbryt** eller **Stäng** Stäng-ikonen om du vill ![ ](../../media/scc-remove-icon.png) gå tillbaka till sidan **Redigera din policy \<name\>** ).</span><span class="sxs-lookup"><span data-stu-id="7c758-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="7c758-187">**Princip inställning** : Klicka på **Redigera** om du vill ändra samma inställningar som fanns tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="7c758-187">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="7c758-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="7c758-188">**Name**</span></span>
   - <span data-ttu-id="7c758-189">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="7c758-189">**Description**</span></span>
   - <span data-ttu-id="7c758-190">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="7c758-190">**Applied to**</span></span>
   - <span data-ttu-id="7c758-191">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="7c758-191">**Review your settings**</span></span>

   <span data-ttu-id="7c758-192">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="7c758-193">**Personifiering** : Klicka på **Redigera** för att ändra de skyddade avsändarna och de skyddade domänerna i principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-193">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="7c758-194">Dessa inställningar är ett villkor för den princip som identifierar falska avsändare att leta efter (individuellt eller efter domän) i från-adressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="7c758-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="7c758-195">Mer information finns i [Inställningar för personifiering i principer för Stöldskydd mot ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="7c758-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="7c758-196">**Lägg till användare att skydda** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-196">**Add users to protect** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-197">Aktivera **den genom att dra den till den** och sedan klicka på knappen **Lägg till användare** som visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-197">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="7c758-198">I **Lägg till** utfällda användare som visas konfigurerar du följande värden:</span><span class="sxs-lookup"><span data-stu-id="7c758-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="7c758-199">**E-post adress** :</span><span class="sxs-lookup"><span data-stu-id="7c758-199">**Email address** :</span></span>

        - <span data-ttu-id="7c758-200">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="7c758-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="7c758-201">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="7c758-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="7c758-202">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7c758-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="7c758-203">**Namn** : det här värdet fylls i baserat på e-postadressen du valde, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="7c758-203">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="7c758-204">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-204">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="7c758-205">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="7c758-205">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7c758-206">Du kan ange högst 60 användare i fältet säkerhets & efterlevnad eller i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c758-206">You can enter a maximum of 60 users in the Security & Compliance Center or in PowerShell.</span></span>
       
   - <span data-ttu-id="7c758-207">**Lägg till domäner att skydda** : Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7c758-207">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="7c758-208">**Inkludera automatiskt de domäner jag äger** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-208">**Automatically include the domains I own** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-209">Aktivera den genom att dra den till **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-209">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="7c758-210">**Inkludera anpassade domäner** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-210">**Include custom domains** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-211">Om du vill aktivera funktionen drar du växlings knappen till **på på** och anger sedan domän namnet (till exempel contoso.com) i rutan **Lägg till domäner** , trycker på RETUR och upprepar efter behov.</span><span class="sxs-lookup"><span data-stu-id="7c758-211">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7c758-212">Du kan ange högst 50 domäner i säkerhets & efterföljandekrav eller i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c758-212">You can enter a maximum of 50 domains in the Security & Compliance Center or in PowerShell.</span></span>

   - <span data-ttu-id="7c758-213">**Åtgärder** : Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="7c758-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="7c758-214">**Om e-post skickas av en personifierad användare** : Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare att skydda** :</span><span class="sxs-lookup"><span data-stu-id="7c758-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="7c758-215">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="7c758-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="7c758-216">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="7c758-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="7c758-217">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="7c758-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="7c758-218">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="7c758-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="7c758-219">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="7c758-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="7c758-220">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="7c758-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="7c758-221">**Om e-post skickas av en domänkontrollant** : Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domänerna som du har angett i **Lägg till domäner för att skydda** :</span><span class="sxs-lookup"><span data-stu-id="7c758-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

     - <span data-ttu-id="7c758-222">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="7c758-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="7c758-223">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="7c758-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="7c758-224">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="7c758-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="7c758-225">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="7c758-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="7c758-226">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="7c758-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="7c758-227">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="7c758-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="7c758-228">Klicka på **Aktivera säkerhets tips för personifiering** och konfigurera något av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7c758-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="7c758-229">**Visa tips för personifierade användare** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-229">**Show tip for impersonated users** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-230">Aktivera den genom att dra den till **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-230">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="7c758-231">**Visa tips för personifierade domäner** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-231">**Show tip for impersonated domains** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-232">Aktivera den genom att dra den till **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-232">To turn it on, slide the toggle to **On** .</span></span>
     - <span data-ttu-id="7c758-233">**Visa tips för ovanliga tecken** : standardvärdet är **inaktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-233">**Show tip for unusual characters** : The default value is **Off** .</span></span> <span data-ttu-id="7c758-234">Aktivera den genom att dra den till **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-234">To turn it on, slide the toggle to **On** .</span></span>

     <span data-ttu-id="7c758-235">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7c758-235">When you're finished, click **Save** .</span></span>

   - <span data-ttu-id="7c758-236">**Post låda** :</span><span class="sxs-lookup"><span data-stu-id="7c758-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="7c758-237">**Aktivera post lådans intelligens?** : standardvärdet är **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-237">**Enable mailbox intelligence?** : The default value is **On** .</span></span> <span data-ttu-id="7c758-238">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="7c758-238">To turn it off, slide the toggle to **Off** .</span></span>

     - <span data-ttu-id="7c758-239">**Aktivera post låde baserat personifieringstoken?** : den här inställningen är endast tillgänglig om **Aktivera post låda-intelligens?** är **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On** .</span></span>

       <span data-ttu-id="7c758-240">I **om e-post skickas av en personifierad användare** kan du ange någon av följande åtgärder som ska vidtas för meddelanden som inte har post lådans intelligens (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="7c758-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="7c758-241">**Tillämpa inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="7c758-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="7c758-242">**Omdirigera meddelanden till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="7c758-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="7c758-243">**Flytta meddelandet till mappen skräp post**</span><span class="sxs-lookup"><span data-stu-id="7c758-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="7c758-244">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="7c758-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="7c758-245">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="7c758-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="7c758-246">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="7c758-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="7c758-247">**Lägga till betrodda avsändare och domäner** : ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="7c758-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="7c758-248">**Betrodda avsändare** :</span><span class="sxs-lookup"><span data-stu-id="7c758-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="7c758-249">Klicka i rutan och bläddra igenom listan med användare som ska markeras.</span><span class="sxs-lookup"><span data-stu-id="7c758-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="7c758-250">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="7c758-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="7c758-251">Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7c758-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="7c758-252">**Betrodda domäner** : ange domän namnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.</span><span class="sxs-lookup"><span data-stu-id="7c758-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="7c758-253">**Granska dina inställningar** : i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="7c758-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="7c758-254">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="7c758-255">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="7c758-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="7c758-256">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="7c758-256">**Protected users**</span></span>
       - <span data-ttu-id="7c758-257">**Skyddade domäner** \> **Lägga till domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="7c758-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="7c758-258">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="7c758-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="7c758-259">**Post lådans intelligens**</span><span class="sxs-lookup"><span data-stu-id="7c758-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="7c758-260">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="7c758-261">**Falska** användare: Klicka på **Redigera** för att aktivera eller inaktivera förfalsknings intelligens, aktivera och inaktivera overifierad avsändare i Outlook och konfigurera åtgärden så att den gäller för meddelanden från blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="7c758-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="7c758-262">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="7c758-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="7c758-263">Observera att dessa inställningar också är tillgängliga i principer för nätfiske i EOP.</span><span class="sxs-lookup"><span data-stu-id="7c758-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="7c758-264">**Inställningar för förfalsknings filter** : standardvärdet är **på** och vi rekommenderar att du lämnar det.</span><span class="sxs-lookup"><span data-stu-id="7c758-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="7c758-265">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="7c758-265">To turn it off, slide the toggle to **Off** .</span></span> <span data-ttu-id="7c758-266">Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="7c758-267">Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="7c758-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="7c758-268">Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="7c758-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="7c758-269">**Aktivera overifierad avsändare** : standardvärdet är **på** .</span><span class="sxs-lookup"><span data-stu-id="7c758-269">**Enable Unauthenticated Sender feature** : The default value is **On** .</span></span> <span data-ttu-id="7c758-270">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="7c758-270">To turn it off, slide the toggle to **Off** .</span></span>

   - <span data-ttu-id="7c758-271">**Åtgärder** : ange vilken åtgärd som ska vidtas för meddelanden som saknar förfalsknings information:</span><span class="sxs-lookup"><span data-stu-id="7c758-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="7c758-272">**Om e-post skickas av någon som inte har tillåtelse att imitera din domän** :</span><span class="sxs-lookup"><span data-stu-id="7c758-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="7c758-273">**Flytta meddelandet till mottagarnas skräp post mappar**</span><span class="sxs-lookup"><span data-stu-id="7c758-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="7c758-274">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="7c758-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="7c758-275">**Granska dina inställningar** : i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="7c758-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="7c758-276">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="7c758-277">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="7c758-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="7c758-278">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="7c758-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="7c758-279">**Aktivera ej autentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="7c758-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="7c758-280">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="7c758-281">**Avancerade inställningar** : Klicka på **Redigera** för att konfigurera de avancerade gräns värdena för nät fiske tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7c758-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="7c758-282">Mer information finns i [avancerade nät fiske tröskelvärden i AntiPhishing-principer för ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="7c758-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="7c758-283">**Avancerade nät fiske gränser** : Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="7c758-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="7c758-284">**1 – standard** (det här är standardvärdet).</span><span class="sxs-lookup"><span data-stu-id="7c758-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="7c758-285">**2 – aggressivt**</span><span class="sxs-lookup"><span data-stu-id="7c758-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="7c758-286">**3 – mer aggressivt**</span><span class="sxs-lookup"><span data-stu-id="7c758-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="7c758-287">**4-mest aggressivt**</span><span class="sxs-lookup"><span data-stu-id="7c758-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="7c758-288">**Granska dina inställningar** : Klicka på **Redigera** för att gå tillbaka till sidan för **avancerade nät fiske gränser** .</span><span class="sxs-lookup"><span data-stu-id="7c758-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="7c758-289">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="7c758-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="7c758-290">Gå tillbaka till sidan **Redigera din \<Name\> policy** och granska inställningarna och klicka sedan på **Stäng** .</span><span class="sxs-lookup"><span data-stu-id="7c758-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close** .</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="7c758-291">Använda säkerhets & Compliance Center för att ändra standard policyn för ATP-skydd</span><span class="sxs-lookup"><span data-stu-id="7c758-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="7c758-292">Standard policyn för ATP-nätfiske heter Office365 AntiPhish default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="7c758-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="7c758-293">Gör så här om du vill ändra standard policyn för ATP-nätfiske:</span><span class="sxs-lookup"><span data-stu-id="7c758-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="7c758-294">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-295">Klicka på **standard princip** på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-295">On the **Anti-phishing** page, click **Default policy** .</span></span>

3. <span data-ttu-id="7c758-296">**Standard sidan Redigera policyn för Office365 AntiPhish** visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="7c758-297">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="7c758-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="7c758-298">**Falsk identitet**</span><span class="sxs-lookup"><span data-stu-id="7c758-298">**Impersonation**</span></span>
   - <span data-ttu-id="7c758-299">**Falskt**</span><span class="sxs-lookup"><span data-stu-id="7c758-299">**Spoof**</span></span>
   - <span data-ttu-id="7c758-300">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="7c758-300">**Advanced settings**</span></span>

   <span data-ttu-id="7c758-301">Följande inställningar är inte tillgängliga när du ändrar standard princip:</span><span class="sxs-lookup"><span data-stu-id="7c758-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="7c758-302">Du kan se avsnitt och värden för **princip inställningar** , men det finns inga **redigerings** länkar, så du kan inte ändra inställningarna (princip namn, beskrivning och vem principen gäller för (gäller alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="7c758-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="7c758-303">Du kan inte ta bort standard principen.</span><span class="sxs-lookup"><span data-stu-id="7c758-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="7c758-304">Du kan inte ändra prioriteten för standard principen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="7c758-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="7c758-305">På **standard sidan Redigera en Office365 AntiPhish** du på Inställningar och klickar sedan på **Stäng** .</span><span class="sxs-lookup"><span data-stu-id="7c758-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close** .</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-306">Aktivera eller inaktivera anpassade Antivirus principer för ATP</span><span class="sxs-lookup"><span data-stu-id="7c758-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7c758-307">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-308">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="7c758-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="7c758-309">Inaktivera principen genom att dra till **av** .</span><span class="sxs-lookup"><span data-stu-id="7c758-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="7c758-310">Aktivera principen genom att dra den till **aktiverat** .</span><span class="sxs-lookup"><span data-stu-id="7c758-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="7c758-311">Du kan inte inaktivera standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="7c758-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-312">Ange prioritet för anpassade Antivirus principer för ATP</span><span class="sxs-lookup"><span data-stu-id="7c758-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="7c758-313">Som standard ges ATP-Antivirus principer en prioritet som baseras på den ordning de skapades (nyare principer är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="7c758-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="7c758-314">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="7c758-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="7c758-315">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="7c758-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="7c758-316">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="7c758-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="7c758-317">Anpassade Antivirus principer för ATP visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="7c758-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="7c758-318">Standard policyn för anti-phishing med namnet Office365 AntiPhish standard har värdet **lägst** och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="7c758-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="7c758-319">**Obs!** i fältet säkerhets & efterlevnad kan du bara ändra prioriteten för ATP-principen för Stöldskydd när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="7c758-319">**Note** : In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="7c758-320">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln mot Phish (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="7c758-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="7c758-321">Om du vill ändra prioriteten för en princip klickar du på **öka prioriteten** eller **minska prioriteten** i egenskaperna för principen (du kan inte direkt ändra **prioritets** numret i säkerhets & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="7c758-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="7c758-322">Det är bara att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="7c758-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="7c758-323">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-324">Välj den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="7c758-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="7c758-325">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="7c758-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7c758-326">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="7c758-327">Den anpassade policyn för ATP-nätfiske med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="7c758-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="7c758-328">Den anpassade policyn för ATP-nätfiske med lägst **prioritet** (till exempel **3** ) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="7c758-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="7c758-329">Om du har tre eller fler anpassade nät fiske principer har de värden mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="7c758-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="7c758-330">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="7c758-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="7c758-331">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7c758-331">When you're finished, click **Close** .</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-332">Använd säkerhets & kompatibilitetstillstånd för att Visa ATP-Antivirus principer</span><span class="sxs-lookup"><span data-stu-id="7c758-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7c758-333">I säkerhets & Compliance Center och gå till **hot Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-334">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="7c758-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="7c758-335">Välj en egen Antivirus policy för ATP som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="7c758-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="7c758-336">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="7c758-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="7c758-337">Klicka på **standard princip** för att Visa standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="7c758-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="7c758-338">**Redigera den utfällbara \<name\> principen** visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="7c758-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-339">Använd säkerhets & Compliance Center för att ta bort ATP-AntiPhishing-principer</span><span class="sxs-lookup"><span data-stu-id="7c758-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="7c758-340">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span>

2. <span data-ttu-id="7c758-341">Välj den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7c758-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="7c758-342">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="7c758-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="7c758-343">I redigera den utfällbara **princip \<name\>** som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="7c758-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="7c758-344">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="7c758-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="7c758-345">Konfigurera tilläggsprogram för ATP med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c758-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="7c758-346">Som du redan har beskrivit innehåller ett ATP-policy mot skräp post Phish och en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="7c758-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="7c758-347">I Exchange Online PowerShell är skillnaden mellan policyer för Phish och Phish regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="7c758-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="7c758-348">Du hanterar policyn för Phish genom att använda cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-Phish-regler med hjälp av cmdlet **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="7c758-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="7c758-349">I PowerShell skapar du policyn för Phish först och sedan skapar du regeln mot Phish som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="7c758-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="7c758-350">I PowerShell ändrar du inställningarna i policyn för Phish och anti-Phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="7c758-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="7c758-351">När du tar bort en policy för Phish från PowerShell tas motsvarande antiphish-regel inte bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="7c758-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="7c758-352">Använda PowerShell för att skapa skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="7c758-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="7c758-353">Att skapa en skydds policy i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="7c758-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="7c758-354">Skapa policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="7c758-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="7c758-355">Skapa en regel för Phish som anger den policy för anti-Phish som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="7c758-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="7c758-356">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="7c758-356">**Notes** :</span></span>

- <span data-ttu-id="7c758-357">Du kan skapa en ny Phish regel och koppla en befintlig, icke associerad policy mot anti-Phish-princip till den.</span><span class="sxs-lookup"><span data-stu-id="7c758-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="7c758-358">En antiphish-regel kan inte kopplas till fler än en anti-Phish princip.</span><span class="sxs-lookup"><span data-stu-id="7c758-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="7c758-359">Du kan konfigurera följande inställningar i nya principer mot Phish i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="7c758-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="7c758-360">Skapa den nya principen som inaktive rad ( _aktive rad_ `$false` på **New-AntiPhishRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="7c758-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="7c758-361">Ange prioriteten för principen när den skapas ( _prioritet_ _\<Number\>_ ) på den **nya AntiPhishRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="7c758-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="7c758-362">En ny policy för Phish som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="7c758-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="7c758-363">Steg 1: använda PowerShell för att skapa en policy för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="7c758-364">Använd följande syntax för att skapa en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="7c758-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="7c758-365">I det här exemplet skapas policy för Phish forsknings karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7c758-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="7c758-366">Principen är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="7c758-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="7c758-367">Beskrivningen är: policy för forsknings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="7c758-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="7c758-368">Gör att organisationer-domäner skyddas för alla godkända domäner och riktade domäner för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7c758-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="7c758-369">Anger Mai Fujito (mfujito@fabrikam.com) som användaren skyddar dig mot.</span><span class="sxs-lookup"><span data-stu-id="7c758-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="7c758-370">Aktiverar post lådans intelligens.</span><span class="sxs-lookup"><span data-stu-id="7c758-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="7c758-371">Aktiverar post lådans informations skydd och anger karantän åtgärden.</span><span class="sxs-lookup"><span data-stu-id="7c758-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="7c758-372">Möjliggör säkerhets tips.</span><span class="sxs-lookup"><span data-stu-id="7c758-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="7c758-373">Detaljerad information om syntax och parametrar finns i [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="7c758-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="7c758-374">Steg 2: använda PowerShell för att skapa en regel för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="7c758-375">Använd följande syntax för att skapa en Phish-regel:</span><span class="sxs-lookup"><span data-stu-id="7c758-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="7c758-376">I det här exemplet skapas en Phish regel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="7c758-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="7c758-377">Regeln associeras med policyn för Phish med namnet forsknings karantän.</span><span class="sxs-lookup"><span data-stu-id="7c758-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="7c758-378">Regeln gäller för medlemmar i gruppen Research avdelning.</span><span class="sxs-lookup"><span data-stu-id="7c758-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="7c758-379">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="7c758-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="7c758-380">Detaljerad information om syntax och parametrar finns i [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="7c758-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="7c758-381">Använda PowerShell för att visa principer mot Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="7c758-382">Använd följande syntax för att visa befintliga principer för Phish:</span><span class="sxs-lookup"><span data-stu-id="7c758-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7c758-383">I det här exemplet returneras en sammanfattande lista över alla Phish-principer tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="7c758-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="7c758-384">I det här exemplet returneras alla egenskapsvärde för Phish policy med namnet chefer.</span><span class="sxs-lookup"><span data-stu-id="7c758-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="7c758-385">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="7c758-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="7c758-386">Använda PowerShell för att visa regler för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="7c758-387">Använd följande syntax för att visa befintliga regler för Phish:</span><span class="sxs-lookup"><span data-stu-id="7c758-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7c758-388">I det här exemplet returneras en sammanfattande lista över alla Phish regler tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="7c758-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="7c758-389">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="7c758-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="7c758-390">I det här exemplet returneras alla egenskaps värden för Phish regeln contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="7c758-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="7c758-391">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="7c758-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="7c758-392">Använda PowerShell för att ändra policyn för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="7c758-393">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en policy för Phish i PowerShell som när du skapar policyn enligt beskrivningen i [steg 1: använda PowerShell för att skapa ett princip policy för Phish](#step-1-use-powershell-to-create-an-anti-phish-policy) .</span><span class="sxs-lookup"><span data-stu-id="7c758-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="7c758-394">_MakeDefault_ -växeln som aktiverar den angivna principen till standard principen (tillämpas på alla, alltid **lägst** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en policy mot Phish i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c758-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="7c758-395">Du kan inte byta namn på en policy mot Phish ( **set-AntiPhishPolicy** -cmdleten har ingen _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="7c758-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="7c758-396">När du byter namn på en skydds princip i säkerhets & Compliance Center byter du bara namn på _regeln_ mot Phish.</span><span class="sxs-lookup"><span data-stu-id="7c758-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_ .</span></span>

<span data-ttu-id="7c758-397">Använd följande syntax för att ändra en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="7c758-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="7c758-398">Detaljerad information om syntax och parametrar finns i [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="7c758-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="7c758-399">Använda PowerShell för att ändra regler för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="7c758-400">Den enda inställning som inte är tillgänglig när du ändrar en anti-Phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="7c758-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="7c758-401">Information om hur du aktiverar eller inaktiverar befintliga regler för Phish finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="7c758-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="7c758-402">Annars är inga ytterligare inställningar tillgängliga när du ändrar en Phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c758-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="7c758-403">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en antiphish regel](#step-2-use-powershell-to-create-an-anti-phish-rule) -avsnitt tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7c758-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="7c758-404">Om du vill ändra en Phish regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7c758-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="7c758-405">Detaljerad information om syntax och parametrar finns i [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="7c758-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="7c758-406">Använda PowerShell för att aktivera eller inaktivera Phish regler</span><span class="sxs-lookup"><span data-stu-id="7c758-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="7c758-407">Aktivering eller inaktive ring av en Phish regel i PowerShell aktiverar eller inaktiverar hela AntiPhishing-principen (anti-Phish-regeln och den tilldelade anti-Phish-principen).</span><span class="sxs-lookup"><span data-stu-id="7c758-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="7c758-408">Du kan inte aktivera eller inaktivera standard policyn för skydd mot nätfiske (det gäller alltid alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="7c758-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="7c758-409">Så här aktiverar eller inaktiverar du en Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7c758-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="7c758-410">I det här exemplet inaktive ras den Phish marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="7c758-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7c758-411">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="7c758-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7c758-412">Detaljerad information om syntax och parametrar finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) och [disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="7c758-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="7c758-413">Använd PowerShell för att ange prioriteten för antiphish-regler</span><span class="sxs-lookup"><span data-stu-id="7c758-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="7c758-414">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="7c758-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="7c758-415">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="7c758-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="7c758-416">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="7c758-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="7c758-417">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="7c758-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="7c758-418">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="7c758-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="7c758-419">Använd följande syntax för att ange prioriteten för en anti-Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7c758-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="7c758-420">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="7c758-420">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="7c758-421">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="7c758-421">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="7c758-422">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="7c758-422">**Notes** :</span></span>

- <span data-ttu-id="7c758-423">Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-AntiPhishRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="7c758-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="7c758-424">Standard policyn för Phish har ingen motsvarande anti-Phish-regel och har alltid det icke ändrings bara prioritet svärdet **lägst** .</span><span class="sxs-lookup"><span data-stu-id="7c758-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest** .</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="7c758-425">Använda PowerShell för att ta bort principer för Phish</span><span class="sxs-lookup"><span data-stu-id="7c758-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="7c758-426">När du använder PowerShell för att ta bort en policy för Phish, tas inte motsvarande antiphish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="7c758-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="7c758-427">Använd följande syntax för att ta bort en policy för Phish i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7c758-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="7c758-428">I det här exemplet tas policyn för Phish bort från marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="7c758-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="7c758-429">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="7c758-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="7c758-430">Använda PowerShell för att ta bort Phish regler</span><span class="sxs-lookup"><span data-stu-id="7c758-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="7c758-431">När du använder PowerShell för att ta bort en antiphish-regel tas motsvarande policy mot Phish inte bort.</span><span class="sxs-lookup"><span data-stu-id="7c758-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="7c758-432">Om du vill ta bort en Phish regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7c758-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="7c758-433">Det här exemplet tar bort regeln marknadsförings avdelning för Phish.</span><span class="sxs-lookup"><span data-stu-id="7c758-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="7c758-434">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="7c758-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7c758-435">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="7c758-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="7c758-436">Gör något av följande om du vill verifiera att du har konfigurerat ATP-skydds principer:</span><span class="sxs-lookup"><span data-stu-id="7c758-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="7c758-437">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="7c758-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** .</span></span> <span data-ttu-id="7c758-438">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="7c758-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="7c758-439">Gör något av följande om du vill visa mer information:</span><span class="sxs-lookup"><span data-stu-id="7c758-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="7c758-440">Välj en princip i listan och visa detaljerna i den utfällbara informationen.</span><span class="sxs-lookup"><span data-stu-id="7c758-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="7c758-441">Klicka på **standard policy** och se informationen i utfällbar form.</span><span class="sxs-lookup"><span data-stu-id="7c758-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="7c758-442">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="7c758-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
