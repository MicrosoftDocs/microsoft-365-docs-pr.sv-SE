---
title: Konfigurera principer för ATP-skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du skapar, ändrar och tar bort de avancerade anti-phishing-principer som är tillgängliga i organisationer med Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726763"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-103">Konfigurera principer för ATP-skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="81f1c-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="81f1c-104">ATP:s principer för phishing-phishing är en del av [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="81f1c-105">ATP:s principer för nätfiske kan skydda din organisation från skadliga identitetsbaserade nätfiskeattacker och andra typer av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="81f1c-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="81f1c-106">Mer information om skillnaderna mellan anti-phishing-policyer i EOP (Exchange Online Protection) och ATP:s principer för phishing finns i [Anti-phishing Protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="81f1c-107">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för ATP-phishing.</span><span class="sxs-lookup"><span data-stu-id="81f1c-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="81f1c-108">För större granularitet kan du också skapa anpassade ATP-principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="81f1c-109">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="81f1c-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="81f1c-110">Du kan konfigurera ATP-principer för nätfiske i Security & Compliance Center eller Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81f1c-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="81f1c-111">Information om hur du konfigurerar de mer begränsade i anti-phishing-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga Microsoft 365-organisationer utan Office 365 ATP) finns [i Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="81f1c-112">ATP:s principer för phishing-bekämpning i Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="81f1c-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="81f1c-113">De grundläggande inslagen i en ATP-policy mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="81f1c-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="81f1c-114">**Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="81f1c-115">**Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="81f1c-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="81f1c-116">Skillnaden mellan dessa två element är inte uppenbar när du hanterar ATP-principer för nätfiske i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="81f1c-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="81f1c-117">När du skapar en ATP-anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="81f1c-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="81f1c-118">När du ändrar en ATP-anti-phishing-princip i Security & Compliance Center ändras reglerna för namn, prioritet, aktiverad eller inaktiverad och mottagarfilter anti-phish-regeln.</span><span class="sxs-lookup"><span data-stu-id="81f1c-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="81f1c-119">Alla andra inställningar ändrar den associerade anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="81f1c-120">När du tar bort en ATP-anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="81f1c-121">I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="81f1c-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="81f1c-122">Du hanterar anti-phish-principer med hjälp av cmdleterna \*\* \* -AntiPhishPolicy\*\* och hanterar anti-phish-regler med hjälp av cmdlets \*\* \* -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="81f1c-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="81f1c-123">I PowerShell skapar du principen mot phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="81f1c-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="81f1c-124">I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="81f1c-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="81f1c-125">När du tar bort en anti-phish-princip från PowerShell tas inte motsvarande anti-phish-regel bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="81f1c-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="81f1c-126">Standardprincip för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="81f1c-127">Varje ATP-organisation har en inbyggd ATP-anti-phishing-princip med namnet Office365 AntiPhish Default som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="81f1c-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="81f1c-128">Anti-phish-principen som heter Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="81f1c-129">Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="81f1c-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="81f1c-130">Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="81f1c-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="81f1c-131">Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har värdet `True` ) och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="81f1c-132">Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade ATP-principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="81f1c-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81f1c-133">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="81f1c-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81f1c-134">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="81f1c-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="81f1c-135">Om du vill gå direkt till **ATP:s sida mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="81f1c-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="81f1c-136">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="81f1c-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="81f1c-137">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="81f1c-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="81f1c-138">Om du vill lägga till, ändra och ta bort ATP-principer för nätfiske måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="81f1c-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="81f1c-139">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="81f1c-140">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="81f1c-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="81f1c-141">För skrivskyddad åtkomst till ATP:s principer för nätfiske måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="81f1c-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="81f1c-142">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="81f1c-143">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="81f1c-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="81f1c-144">Våra rekommenderade inställningar för ATP-principer för nätfiske finns i [Principinställningar för Office ATP-phishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="81f1c-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="81f1c-145">Tillåt upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="81f1c-146">Information om var anti-nätfiskeprinciper tillämpas i filtreringspipelinen finns i [Ordning och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-147">Använd Security & Compliance Center för att skapa ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="81f1c-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="81f1c-148">Om du skapar en anpassad ATP-anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="81f1c-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="81f1c-149">När du skapar en ATP-princip mot nätfiske kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="81f1c-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="81f1c-150">När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="81f1c-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="81f1c-151">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-152">Klicka på **Skapa**på sidan **Anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="81f1c-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="81f1c-153">Guiden **Skapa en ny anti-phishing-princip** öppnas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="81f1c-154">Konfigurera följande inställningar på sidan Namn på **principen:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="81f1c-155">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="81f1c-156">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="81f1c-157">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="81f1c-158">På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="81f1c-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="81f1c-159">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="81f1c-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="81f1c-160">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="81f1c-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="81f1c-161">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="81f1c-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="81f1c-162">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-162">Click **Add a condition**.</span></span> <span data-ttu-id="81f1c-163">I listrutan som visas väljer du ett villkor under **Tillämpad om:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="81f1c-164">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="81f1c-165">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="81f1c-166">**Mottagardomänen är**: Anger mottagare i en eller flera av de konfigurerade accepterade domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="81f1c-167">När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**</span><span class="sxs-lookup"><span data-stu-id="81f1c-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="81f1c-168">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="81f1c-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="81f1c-169">Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="81f1c-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="81f1c-170">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="81f1c-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="81f1c-171">Om du vill ta bort enskilda poster klickar du på **Ikonen Ta bort** ta bort i ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="81f1c-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="81f1c-172">Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="81f1c-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="81f1c-173">Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="81f1c-174">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="81f1c-175">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="81f1c-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="81f1c-176">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="81f1c-177">Granska **inställningarna** på sidan Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="81f1c-178">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="81f1c-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="81f1c-179">När du är klar klickar du på **Skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="81f1c-180">Klicka på **OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="81f1c-181">När du har skapat ATP:s anti-nätfiskeprincip med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-182">Använda Security & Compliance Center för att ändra ATP:s principer för phishing-phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="81f1c-183">Använd följande procedurer för att ändra ATP:s principer för nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="81f1c-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="81f1c-184">Om du inte redan är där öppnar du Security & **Threat management** Compliance Center och går till \> **Policy** \> **ATP-principen**för hothantering.</span><span class="sxs-lookup"><span data-stu-id="81f1c-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-185">Välj den anpassade ATP-principen mot nätfiske som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="81f1c-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="81f1c-186">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="81f1c-187">**Den Redigera \<name\> din princip** utfällbara visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="81f1c-188">Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="81f1c-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="81f1c-189">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="81f1c-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="81f1c-190">När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Ikonen Avbryt** eller **Stäng** avsluta för att återgå till sidan Redigera ![ din ](../../media/scc-remove-icon.png) \*\*princip \<name\> \*\* (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="81f1c-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="81f1c-191">**Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="81f1c-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="81f1c-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="81f1c-192">**Name**</span></span>
   - <span data-ttu-id="81f1c-193">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="81f1c-193">**Description**</span></span>
   - <span data-ttu-id="81f1c-194">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="81f1c-194">**Applied to**</span></span>
   - <span data-ttu-id="81f1c-195">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="81f1c-195">**Review your settings**</span></span>

   <span data-ttu-id="81f1c-196">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="81f1c-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="81f1c-197">**Personifiering:** Klicka på **Redigera** om du vill ändra skyddade avsändare och skyddade domäner i principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="81f1c-198">Dessa inställningar är ett villkor för principen som identifierar falska avsändare att söka efter (individuellt eller efter domän) i Från-adressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="81f1c-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="81f1c-199">Mer information finns [i Inställningar för personifiering i ATP:s principer för phishing.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="81f1c-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="81f1c-200">**Lägg till användare för att skydda:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-201">Om du vill aktivera den drar du växlingsknappen till **På**och klickar sedan på knappen **Lägg till användare** som visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="81f1c-202">Konfigurera följande värden i utfällbara tilläggsvärden för **Lägg till** användare:</span><span class="sxs-lookup"><span data-stu-id="81f1c-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="81f1c-203">**E-postadress:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-203">**Email address**:</span></span>

        - <span data-ttu-id="81f1c-204">Klicka i rutan och bläddra igenom listan över användare att välja.</span><span class="sxs-lookup"><span data-stu-id="81f1c-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="81f1c-205">Klicka i rutan och börja skriva för att filtrera listan och välj en användare.</span><span class="sxs-lookup"><span data-stu-id="81f1c-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="81f1c-206">Om du vill ta bort en post klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) användaren.</span><span class="sxs-lookup"><span data-stu-id="81f1c-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="81f1c-207">**Namn**: Det här värdet fylls i baserat på den e-postadress du har valt, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="81f1c-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="81f1c-208">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="81f1c-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="81f1c-209">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="81f1c-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="81f1c-210">**Lägg till domäner som ska skyddas:** Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="81f1c-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="81f1c-211">**Inkludera automatiskt de domäner jag äger:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-212">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="81f1c-213">**Inkludera anpassade domäner:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-214">Om du vill aktivera den drar du växlingsknappen till **På**och i rutan **Lägg till domäner** anger du domännamnet (till exempel contoso.com), trycker på RETUR och upprepar vid behov.</span><span class="sxs-lookup"><span data-stu-id="81f1c-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="81f1c-215">**Åtgärder**: Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="81f1c-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="81f1c-216">**Om e-post skickas av en personifierad användare:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare för att skydda:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="81f1c-217">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="81f1c-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="81f1c-218">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="81f1c-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="81f1c-219">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="81f1c-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="81f1c-220">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="81f1c-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="81f1c-221">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="81f1c-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="81f1c-222">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="81f1c-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="81f1c-223">**Om e-post skickas av en personifierad domän:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domäner som du har angett i **Lägg till domäner för att skydda:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="81f1c-224">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="81f1c-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="81f1c-225">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="81f1c-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="81f1c-226">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="81f1c-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="81f1c-227">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="81f1c-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="81f1c-228">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="81f1c-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="81f1c-229">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="81f1c-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="81f1c-230">Klicka **på aktivera säkerhetstips för personifiering** och konfigurera någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="81f1c-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="81f1c-231">**Visa tips för personifierade användare:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-232">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="81f1c-233">**Visa tips för personifierade domäner**: Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-234">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="81f1c-235">**Visa tips för ovanliga tecken:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="81f1c-236">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="81f1c-237">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81f1c-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="81f1c-238">**Brevlåda intelligens:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="81f1c-239">**Aktivera postlådeinformation?**: Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="81f1c-240">Om du vill stänga av den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="81f1c-241">**Aktivera informationsskydd för postlådainformationsbaserad personifiering?**: Den här inställningen är endast tillgänglig om **Aktivera postlådeinformation?** är **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="81f1c-242">I **Om e-post skickas av en personifierad användare**kan du ange någon av följande åtgärder för att ta på meddelanden som inte fungerar som postlådeinformation (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="81f1c-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="81f1c-243">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="81f1c-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="81f1c-244">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="81f1c-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="81f1c-245">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="81f1c-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="81f1c-246">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="81f1c-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="81f1c-247">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="81f1c-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="81f1c-248">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="81f1c-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="81f1c-249">**Lägg till betrodda avsändare och domäner**: Ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="81f1c-250">**Betrodda avsändare:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="81f1c-251">Klicka i rutan och bläddra igenom listan över användare att välja.</span><span class="sxs-lookup"><span data-stu-id="81f1c-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="81f1c-252">Klicka i rutan och börja skriva för att filtrera listan och välj en användare.</span><span class="sxs-lookup"><span data-stu-id="81f1c-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="81f1c-253">Om du vill ta bort en post klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) användaren.</span><span class="sxs-lookup"><span data-stu-id="81f1c-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="81f1c-254">**Betrodda domäner**: Ange domännamnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.</span><span class="sxs-lookup"><span data-stu-id="81f1c-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="81f1c-255">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="81f1c-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="81f1c-256">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="81f1c-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="81f1c-257">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="81f1c-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="81f1c-258">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="81f1c-258">**Protected users**</span></span>
       - <span data-ttu-id="81f1c-259">**Skyddade domäner** \> **Inkludera domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="81f1c-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="81f1c-260">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="81f1c-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="81f1c-261">**Information om brevlåda**</span><span class="sxs-lookup"><span data-stu-id="81f1c-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="81f1c-262">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="81f1c-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="81f1c-263">**Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="81f1c-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="81f1c-264">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="81f1c-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="81f1c-265">Observera att samma inställningar också är tillgängliga i anti-phishing-principer i EOP.</span><span class="sxs-lookup"><span data-stu-id="81f1c-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="81f1c-266">**Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på.</span><span class="sxs-lookup"><span data-stu-id="81f1c-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="81f1c-267">Om du vill stänga av den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="81f1c-268">Mer information finns [i Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="81f1c-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="81f1c-269">Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kontakter i stället.</span><span class="sxs-lookup"><span data-stu-id="81f1c-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="81f1c-270">Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="81f1c-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="81f1c-271">**Aktivera funktionen Oautentiserad avsändare**: Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="81f1c-272">Om du vill stänga av den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="81f1c-273">**Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="81f1c-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="81f1c-274">**Om e-post skickas av någon som inte får förfalska din domän:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="81f1c-275">**Flytta meddelande till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="81f1c-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="81f1c-276">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="81f1c-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="81f1c-277">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="81f1c-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="81f1c-278">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="81f1c-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="81f1c-279">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="81f1c-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="81f1c-280">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="81f1c-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="81f1c-281">**Aktivera funktionen Oautentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="81f1c-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="81f1c-282">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="81f1c-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="81f1c-283">**Avancerade inställningar**: Klicka på **Redigera** för att konfigurera de avancerade tröskelvärdena för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="81f1c-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="81f1c-284">Mer information finns [i Avancerade tröskelvärden för nätfiske i ATP:s principer för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="81f1c-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="81f1c-285">**Avancerade tröskelvärden för nätfiske**: Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="81f1c-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="81f1c-286">**1 - Standard** (Detta är standardvärdet.)</span><span class="sxs-lookup"><span data-stu-id="81f1c-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="81f1c-287">**2 - Aggressiv**</span><span class="sxs-lookup"><span data-stu-id="81f1c-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="81f1c-288">**3 - Mer aggressiv**</span><span class="sxs-lookup"><span data-stu-id="81f1c-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="81f1c-289">**4 - Mest aggressiva**</span><span class="sxs-lookup"><span data-stu-id="81f1c-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="81f1c-290">**Granska dina inställningar**: Klicka på **Redigera** för att gå tillbaka till sidan **Avancerade tröskelvärden för nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="81f1c-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="81f1c-291">När du är klar klickar du på **Spara** på någon av sidor.</span><span class="sxs-lookup"><span data-stu-id="81f1c-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="81f1c-292">Tillbaka på **sidan \<Name\> Redigera din princip,** granska dina inställningar och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="81f1c-293">Använd Security & Compliance Center för att ändra standardprincipen för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="81f1c-294">Standardprincipen för ATP-phishing heter Office365 AntiPhish Default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="81f1c-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="81f1c-295">Så här ändrar du standardpolicyn för ATP-phishing:</span><span class="sxs-lookup"><span data-stu-id="81f1c-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="81f1c-296">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-297">Klicka på **Standardprincip**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="81f1c-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="81f1c-298">Sidan **Redigera din princip office365 AntiPhish Standard** visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="81f1c-299">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="81f1c-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="81f1c-300">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="81f1c-300">**Impersonation**</span></span>
   - <span data-ttu-id="81f1c-301">**Spolat**</span><span class="sxs-lookup"><span data-stu-id="81f1c-301">**Spoof**</span></span>
   - <span data-ttu-id="81f1c-302">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="81f1c-302">**Advanced settings**</span></span>

   <span data-ttu-id="81f1c-303">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="81f1c-304">Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="81f1c-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="81f1c-305">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="81f1c-306">Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="81f1c-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="81f1c-307">På sidan **Redigera din princip office365 AntiPhish Standard** granskar du dina inställningar och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-308">Aktivera eller inaktivera anpassade ATP-principer för phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="81f1c-309">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-310">Lägg märke till värdet i kolumnen **Status:**</span><span class="sxs-lookup"><span data-stu-id="81f1c-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="81f1c-311">Dra växlingsknappen till **Av** för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="81f1c-312">Dra växlingsknappen till **På** för att aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="81f1c-313">Du kan inte inaktivera standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="81f1c-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-314">Ange prioritet för anpassade ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="81f1c-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="81f1c-315">Som standard ges ATP-principer för phishing en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="81f1c-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="81f1c-316">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="81f1c-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="81f1c-317">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="81f1c-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="81f1c-318">Anpassade ATP-principer för nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="81f1c-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="81f1c-319">Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="81f1c-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="81f1c-320">**I**Security & Compliance Center kan du bara ändra prioriteten för ATP-principen mot nätfiske när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="81f1c-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="81f1c-321">I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="81f1c-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="81f1c-322">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i principens egenskaper (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center).</span><span class="sxs-lookup"><span data-stu-id="81f1c-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="81f1c-323">Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="81f1c-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="81f1c-324">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-325">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="81f1c-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="81f1c-326">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="81f1c-327">**Den Redigera \<name\> din princip** utfällbara visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="81f1c-328">Den anpassade ATP-principen mot nätfiske med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="81f1c-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="81f1c-329">Den anpassade ATP-principen mot nätfiske med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="81f1c-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="81f1c-330">Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="81f1c-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="81f1c-331">Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="81f1c-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="81f1c-332">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81f1c-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-333">Använda Security & Compliance Center för att visa ATP-principer för phishing-phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="81f1c-334">I Security & Compliance Center och gå **Threat management** till \> **Policy** \> **Atp-anti-phishing-principen**för hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="81f1c-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-335">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="81f1c-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="81f1c-336">Välj en anpassad ATP-anti-phishing-princip som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="81f1c-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="81f1c-337">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="81f1c-338">Klicka på **Standardprincip** om du vill visa standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="81f1c-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="81f1c-339">Den **Redigera \<name\> din princip** utfällbara visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="81f1c-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-340">Använd Security & Compliance Center för att ta bort ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="81f1c-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="81f1c-341">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81f1c-342">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="81f1c-343">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="81f1c-344">Klicka på **Ta bort princip**i utfällningen redigera din \*\*princip \<name\> \*\* och klicka sedan på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="81f1c-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="81f1c-345">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="81f1c-346">Använda Exchange Online PowerShell för att konfigurera ATP-principer för phishing</span><span class="sxs-lookup"><span data-stu-id="81f1c-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="81f1c-347">Använda PowerShell för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="81f1c-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="81f1c-348">Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="81f1c-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="81f1c-349">Skapa anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="81f1c-350">Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="81f1c-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="81f1c-351">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="81f1c-351">**Notes**:</span></span>

- <span data-ttu-id="81f1c-352">Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="81f1c-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="81f1c-353">En anti-phish regel kan inte associeras med mer än en anti-phish politik.</span><span class="sxs-lookup"><span data-stu-id="81f1c-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="81f1c-354">Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="81f1c-355">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="81f1c-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="81f1c-356">Ange prioritet för principen när du skapar (_Prioritet_ _\<Number\>_ ) på cmdleten **Ny antiphishRule).**</span><span class="sxs-lookup"><span data-stu-id="81f1c-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="81f1c-357">En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="81f1c-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="81f1c-358">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="81f1c-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="81f1c-359">Om du vill skapa en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="81f1c-360">I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="81f1c-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="81f1c-361">Principen är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="81f1c-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="81f1c-362">Beskrivningen är: Forskningsavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="81f1c-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="81f1c-363">Aktiverar organisationsdomänskydd för alla accepterade domäner och riktade domänskydd för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="81f1c-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="81f1c-364">Anger Mai Fujito (mfujito@fabrikam.com) som användare för att skydda mot personifiering.</span><span class="sxs-lookup"><span data-stu-id="81f1c-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="81f1c-365">Aktiverar postlådeinformation.</span><span class="sxs-lookup"><span data-stu-id="81f1c-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="81f1c-366">Aktiverar intelligensskydd för postlådor och anger karantänåtgärden.</span><span class="sxs-lookup"><span data-stu-id="81f1c-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="81f1c-367">Möjliggör säkerhetstips.</span><span class="sxs-lookup"><span data-stu-id="81f1c-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="81f1c-368">Detaljerad syntax- och parameterinformation finns i [Ny AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="81f1c-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="81f1c-369">Steg 2: Använd PowerShell för att skapa en anti-phish-regel</span><span class="sxs-lookup"><span data-stu-id="81f1c-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="81f1c-370">Om du vill skapa en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="81f1c-371">I det här exemplet skapas en anti-phish-regel med namnet Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="81f1c-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="81f1c-372">Regeln är associerad med anti-phish-principen som heter Forskningskarantän.</span><span class="sxs-lookup"><span data-stu-id="81f1c-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="81f1c-373">Regeln gäller för medlemmar i gruppen som heter Forskningsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="81f1c-374">Eftersom vi inte använder parametern _Prioritet_ används standardprioriteten.</span><span class="sxs-lookup"><span data-stu-id="81f1c-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="81f1c-375">Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="81f1c-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="81f1c-376">Använda PowerShell för att visa anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="81f1c-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="81f1c-377">Om du vill visa befintliga anti-phish-principer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="81f1c-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="81f1c-378">I det här exemplet returneras en sammanfattningslista över alla anti-phish-principer tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="81f1c-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="81f1c-379">I det här exemplet returneras alla egenskapsvärden för anti-phish-principen Chefer.</span><span class="sxs-lookup"><span data-stu-id="81f1c-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="81f1c-380">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="81f1c-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="81f1c-381">Använda PowerShell för att visa anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="81f1c-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="81f1c-382">Om du vill visa befintliga anti-phish-regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="81f1c-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="81f1c-383">I det här exemplet returneras en sammanfattningslista över alla anti-phish-regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="81f1c-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="81f1c-384">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="81f1c-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="81f1c-385">I det här exemplet returneras alla egenskapsvärden för anti-phish-regeln Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="81f1c-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="81f1c-386">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="81f1c-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="81f1c-387">Använda PowerShell för att ändra anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="81f1c-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="81f1c-388">Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="81f1c-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="81f1c-389">_Den MakeDefault-växel_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81f1c-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="81f1c-390">Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="81f1c-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="81f1c-391">När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.</span><span class="sxs-lookup"><span data-stu-id="81f1c-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="81f1c-392">Om du vill ändra en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="81f1c-393">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="81f1c-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="81f1c-394">Använda PowerShell för att ändra anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="81f1c-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="81f1c-395">Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="81f1c-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="81f1c-396">Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="81f1c-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="81f1c-397">Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81f1c-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="81f1c-398">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="81f1c-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="81f1c-399">Om du vill ändra en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="81f1c-400">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="81f1c-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="81f1c-401">Använda PowerShell för att aktivera eller inaktivera anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="81f1c-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="81f1c-402">Om du aktiverar eller inaktiverar en anti-phish-regel i PowerShell aktiveras eller inaktiveras hela anti-phishing-principen (anti-phish-regeln och den tilldelade anti-phish-principen).</span><span class="sxs-lookup"><span data-stu-id="81f1c-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="81f1c-403">Du kan inte aktivera eller inaktivera standardpolicyn mot nätfiske (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="81f1c-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="81f1c-404">Om du vill aktivera eller inaktivera en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="81f1c-405">I det här exemplet inaktiveras anti-phish-regeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="81f1c-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="81f1c-406">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="81f1c-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="81f1c-407">Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="81f1c-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="81f1c-408">Använd PowerShell för att ange prioritet för anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="81f1c-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="81f1c-409">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="81f1c-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="81f1c-410">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="81f1c-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="81f1c-411">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="81f1c-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="81f1c-412">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="81f1c-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="81f1c-413">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="81f1c-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="81f1c-414">Om du vill ange prioritet för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="81f1c-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="81f1c-415">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="81f1c-415">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="81f1c-416">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="81f1c-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="81f1c-417">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="81f1c-417">**Notes**:</span></span>

- <span data-ttu-id="81f1c-418">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **Ny-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="81f1c-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="81f1c-419">Standardanti-phish-principen har inte en motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="81f1c-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="81f1c-420">Använda PowerShell för att ta bort anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="81f1c-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="81f1c-421">När du använder PowerShell för att ta bort en anti-phish-princip tas inte motsvarande anti-phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="81f1c-422">Om du vill ta bort en anti-phish-princip i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="81f1c-423">I det här exemplet tas anti-phish-principen med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="81f1c-424">Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="81f1c-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="81f1c-425">Använda PowerShell för att ta bort anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="81f1c-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="81f1c-426">När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="81f1c-427">Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="81f1c-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="81f1c-428">I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="81f1c-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="81f1c-429">Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="81f1c-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="81f1c-430">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="81f1c-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="81f1c-431">Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:</span><span class="sxs-lookup"><span data-stu-id="81f1c-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="81f1c-432">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="81f1c-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="81f1c-433">Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="81f1c-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="81f1c-434">Så här visar du mer information:</span><span class="sxs-lookup"><span data-stu-id="81f1c-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="81f1c-435">Välj principen i listan och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="81f1c-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="81f1c-436">Klicka på **Standardprincip** och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="81f1c-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="81f1c-437">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="81f1c-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
