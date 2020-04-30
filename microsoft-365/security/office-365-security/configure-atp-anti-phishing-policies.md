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
description: Administratörer kan lära sig hur du skapar, ändrar och tar bort de avancerade anti-nätfiskeprinciper som är tillgängliga i organisationer med Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: e1a7d3b9d401d8bb5bec08d7b5d58546bbd382aa
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949265"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-103">Konfigurera principer för ATP-skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="0c0eb-104">ATP:s principer för phishing är en del av [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="0c0eb-105">ATP:s principer för nätfiske kan skydda din organisation från skadliga nätfiskeattacker och andra typer av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0c0eb-106">Mer information om skillnaderna mellan anti-phishing-policyer i EOP (Exchange Online Protection) och ATP:s principer för phishing finns i [Anti-phishing protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0c0eb-107">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för ATP-phishing.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="0c0eb-108">För större granularitet kan du också skapa anpassade ATP-principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0c0eb-109">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0c0eb-110">Du kan konfigurera ATP-principer för nätfiske i Security & Compliance Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0c0eb-111">Information om hur du konfigurerar de mer begränsade i anti-phishing-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga Office 365-organisationer utan ATP) finns [i Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Office 365 organizations without ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="0c0eb-112">ATP:s principer för phishing-bekämpning i Security & Compliance Center vs Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c0eb-112">ATP anti-phishing policies in the Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="0c0eb-113">De grundläggande inslagen i en ATP-policy mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="0c0eb-114">**Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="0c0eb-115">**Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0c0eb-116">Skillnaden mellan dessa två element är inte uppenbar när du hanterar ATP-principer för phishing-bekämpning i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0c0eb-117">När du skapar en ATP-anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="0c0eb-118">När du ändrar en ATP-anti-phishing-princip i Security & Compliance Center ändras reglerna för namn, prioritet, aktiverad eller inaktiverad och mottagarfilter anti-phish-regeln.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0c0eb-119">Alla andra inställningar ändrar den associerade anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="0c0eb-120">När du tar bort en ATP-anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0c0eb-121">I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0c0eb-122">Du hanterar anti-phish-principer med hjälp av \*\* \*cmdlets -AntiPhishPolicy\*\* och hanterar anti-phish-regler med hjälp av \*\* \*cmdlets -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="0c0eb-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0c0eb-123">I PowerShell skapar du principen anti-phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="0c0eb-124">I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="0c0eb-125">När du tar bort en anti-phish-princip från PowerShell tas inte motsvarande anti-phish-regel bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="0c0eb-126">Standardprincip för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="0c0eb-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="0c0eb-127">Varje ATP-organisation har en inbyggd ATP-anti-phishing-princip med namnet Office365 AntiPhish Default som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0c0eb-128">Anti-phish-principen med namnet Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="0c0eb-129">Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0c0eb-130">Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="0c0eb-131">Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har värdet) `True`och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0c0eb-132">Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade ATP-principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c0eb-133">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="0c0eb-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0c0eb-134">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0c0eb-135">Om du vill gå direkt till **ATP:s sida mot nätfiske** använder du <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0c0eb-136">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0c0eb-137">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0c0eb-138">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0c0eb-139">För skrivskyddad åtkomst till anti-phishing-principer måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="0c0eb-140">Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0c0eb-141">Våra rekommenderade inställningar för ATP-principer för nätfiske finns i [Principinställningar för Office ATP-phishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-141">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="0c0eb-142">Tillåt upp till 30 minuter för en ny eller uppdaterad princip som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0c0eb-143">Information om var principer mot nätfiske tillämpas i filtreringspipelinen finns [i Ordning och prioritet för e-postskydd i Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-144">Använd Security & Compliance Center för att skapa ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-144">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="0c0eb-145">Om du skapar en anpassad ATP-anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-145">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0c0eb-146">När du skapar en ATP-princip mot nätfiske kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-146">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0c0eb-147">När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0c0eb-148">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-149">Klicka på **Skapa**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0c0eb-150">Guiden **Skapa en ny anti-phishing-princip** öppnas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0c0eb-151">Konfigurera följande inställningar på sidan Namn på **principen:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0c0eb-152">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0c0eb-153">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0c0eb-154">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0c0eb-155">På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0c0eb-156">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0c0eb-157">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<mottagare1\>_ eller _\<mottagare2\>_).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0c0eb-158">Olika villkor och undantag använder OCH-logik (till exempel _\<mottagare1\>_ och _\<medlem i grupp 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0c0eb-159">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-159">Click **Add a condition**.</span></span> <span data-ttu-id="0c0eb-160">I listrutan som visas väljer du ett villkor under **Tillämpad om:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0c0eb-161">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0c0eb-162">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0c0eb-163">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span>

   <span data-ttu-id="0c0eb-164">När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0c0eb-165">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0c0eb-166">Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0c0eb-167">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0c0eb-168">Om du vill ta bort](../../media/scc-remove-icon.png) enskilda poster klickar du på **Ikonen Ta bort** ![ta bort i värdet.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0c0eb-169">Om du vill ta **Remove** ![bort](../../media/scc-remove-icon.png) hela villkoret klickar du på Ikonen Ta bort ta bort på villkoret.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0c0eb-170">Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0c0eb-171">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0c0eb-172">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0c0eb-173">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0c0eb-174">Granska **inställningarna** på sidan Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0c0eb-175">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0c0eb-176">När du är klar klickar du på **Skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0c0eb-177">Klicka på **OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0c0eb-178">När du har skapat ATP:s anti-nätfiskeprincip med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-178">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-179">Använda Security & Compliance Center för att ändra ATP:s principer för phishing-phishing</span><span class="sxs-lookup"><span data-stu-id="0c0eb-179">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="0c0eb-180">Använd följande procedurer för att ändra ATP:s principer för nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-180">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0c0eb-181">Om du inte redan är där öppnar du Security & Compliance Center och går till **Policy** \> **ATP-principen** **mot** \> nätfiske mot hothantering .</span><span class="sxs-lookup"><span data-stu-id="0c0eb-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-182">Välj den anpassade ATP-principen mot nätfiske som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-182">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0c0eb-183">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0c0eb-184">Den \*\*utfällbara sidan Redigera ditt principnamn \<\> \*\* visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0c0eb-185">Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0c0eb-186">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0c0eb-187">När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa](../../media/scc-remove-icon.png) inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller Ikonen **Avbryt** eller **Stäng** ![avsluta för att återgå till sidan Redigera ditt \*\*principnamn \<\> \*\* (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0c0eb-188">**Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="0c0eb-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-189">**Name**</span></span>
   - <span data-ttu-id="0c0eb-190">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-190">**Description**</span></span>
   - <span data-ttu-id="0c0eb-191">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-191">**Applied to**</span></span>
   - <span data-ttu-id="0c0eb-192">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-192">**Review your settings**</span></span>

   <span data-ttu-id="0c0eb-193">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0c0eb-194">**Personifiering:** Klicka på **Redigera** om du vill ändra skyddade avsändare och skyddade domäner i principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0c0eb-195">Dessa inställningar är ett villkor för principen som identifierar förfalskade avsändare att söka efter (individuellt eller efter domän) i Från-adressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0c0eb-196">Mer information finns [i Inställningar för personifiering i ATP:s principer för phishing.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="0c0eb-196">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0c0eb-197">**Lägg till användare för att skydda:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-198">Om du vill aktivera den drar du växlingsknappen till **På**och klickar sedan på knappen **Lägg till användare** som visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0c0eb-199">Konfigurera följande värden i utfällningen **för Lägg till användare:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0c0eb-200">**E-postadress:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-200">**Email address**:</span></span>

        - <span data-ttu-id="0c0eb-201">Klicka i rutan och bläddra igenom listan över användare att välja.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-201">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="0c0eb-202">Klicka i rutan och börja skriva för att filtrera listan och välj en användare.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-202">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="0c0eb-203">Om du vill ta bort](../../media/scc-remove-icon.png) en post klickar du på **Ikonen Ta bort** ![ta bort på användaren.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0c0eb-204">**Namn**: Det här värdet fylls i baserat på den e-postadress du har valt, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0c0eb-205">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-205">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="0c0eb-206">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-206">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="0c0eb-207">**Lägg till domäner som ska skyddas:** Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-207">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0c0eb-208">**Inkludera automatiskt de domäner jag äger:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-208">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-209">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-209">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0c0eb-210">**Inkludera anpassade domäner:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-210">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-211">Om du vill aktivera den drar du växlingsknappen till **På**och i rutan **Lägg till domäner** anger du domännamnet (till exempel contoso.com), trycker på RETUR och upprepar vid behov.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-211">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0c0eb-212">**Åtgärder**: Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-212">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="0c0eb-213">**Om e-post skickas av en personifierad användare:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare för att skydda:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-213">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="0c0eb-214">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-214">**Don't apply any action**</span></span>
       - <span data-ttu-id="0c0eb-215">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-215">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0c0eb-216">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-216">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0c0eb-217">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-217">**Quarantine the message**</span></span>
       - <span data-ttu-id="0c0eb-218">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-218">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0c0eb-219">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-219">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0c0eb-220">**Om e-post skickas av en personifierad domän:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domäner som du har angett i **Lägg till domäner för att skydda:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-220">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="0c0eb-221">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-221">**Don't apply any action**</span></span>
     - <span data-ttu-id="0c0eb-222">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-222">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="0c0eb-223">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-223">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="0c0eb-224">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-224">**Quarantine the message**</span></span>
     - <span data-ttu-id="0c0eb-225">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-225">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="0c0eb-226">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-226">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0c0eb-227">Klicka **på aktivera säkerhetstips för personifiering** och konfigurera någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-227">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0c0eb-228">**Visa tips för personifierade användare:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-228">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-229">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-229">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0c0eb-230">**Visa tips för personifierade domäner**: Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-230">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-231">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0c0eb-232">**Visa tips för ovanliga tecken:** Standardvärdet är **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-232">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="0c0eb-233">Om du vill aktivera den drar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-233">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0c0eb-234">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-234">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0c0eb-235">**Brevlåda intelligens:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-235">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="0c0eb-236">**Aktivera postlådeinformation?**: Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-236">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="0c0eb-237">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-237">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0c0eb-238">**Aktivera informationsskydd för postlådainformationsbaserad personifiering?**: Den här inställningen är endast tillgänglig om **Aktivera postlådeinformation?** är **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-238">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0c0eb-239">I **Om e-post skickas av en personifierad användare**kan du ange en av följande åtgärder för att ta på meddelanden som inte kan skicka postlådeinformation (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="0c0eb-239">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0c0eb-240">**Använd inga åtgärder**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-240">**Don't apply any action**</span></span>
       - <span data-ttu-id="0c0eb-241">**Omdirigera meddelande till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-241">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0c0eb-242">**Flytta meddelande till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-242">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0c0eb-243">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-243">**Quarantine the message**</span></span>
       - <span data-ttu-id="0c0eb-244">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-244">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0c0eb-245">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-245">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0c0eb-246">**Lägg till betrodda avsändare och domäner**: Ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-246">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0c0eb-247">**Betrodda avsändare:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-247">**Trusted senders**:</span></span>

       - <span data-ttu-id="0c0eb-248">Klicka i rutan och bläddra igenom listan över användare att välja.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-248">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0c0eb-249">Klicka i rutan och börja skriva för att filtrera listan och välj en användare.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-249">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0c0eb-250">Om du vill ta bort](../../media/scc-remove-icon.png) en post klickar du på **Ikonen Ta bort** ![ta bort på användaren.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-250">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0c0eb-251">**Betrodda domäner**: Ange domännamnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-251">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0c0eb-252">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-252">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0c0eb-253">Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-253">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0c0eb-254">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-254">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0c0eb-255">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-255">**Protected users**</span></span>
       - <span data-ttu-id="0c0eb-256">**Skyddade domäner** \> **Inkludera domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-256">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0c0eb-257">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="0c0eb-257">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0c0eb-258">**Information om brevlåda**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-258">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0c0eb-259">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-259">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0c0eb-260">**Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-260">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0c0eb-261">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-261">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0c0eb-262">Observera att samma inställningar också är tillgängliga i anti-phishing-principer i EOP.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-262">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0c0eb-263">**Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-263">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0c0eb-264">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-264">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0c0eb-265">Mer information finns i [Konfigurera förfalskningsinformation i Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-265">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0c0eb-266">Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Office 365. du aktiverar utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-266">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0c0eb-267">Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-267">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0c0eb-268">**Aktivera funktionen Oautentiserade avsändare:** Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-268">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0c0eb-269">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-269">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0c0eb-270">**Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-270">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0c0eb-271">**Om e-post skickas av någon som inte får förfalska din domän:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-271">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0c0eb-272">**Flytta meddelande till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-272">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0c0eb-273">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-273">**Quarantine the message**</span></span>

   - <span data-ttu-id="0c0eb-274">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-274">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0c0eb-275">Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-275">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0c0eb-276">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-276">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0c0eb-277">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-277">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0c0eb-278">**Aktivera funktionen Oautentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-278">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0c0eb-279">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-279">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0c0eb-280">**Avancerade inställningar**: Klicka på **Redigera** för att konfigurera de avancerade tröskelvärdena för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-280">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0c0eb-281">Mer information finns [i Avancerade tröskelvärden för nätfiske i ATP:s principer för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-281">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0c0eb-282">**Avancerade tröskelvärden för nätfiske**: Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-282">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="0c0eb-283">**1 - Standard** (Detta är standardvärdet.)</span><span class="sxs-lookup"><span data-stu-id="0c0eb-283">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0c0eb-284">**2 - Aggressiv**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-284">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0c0eb-285">**3 - Mer aggressiv**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-285">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0c0eb-286">**4 - Mest aggressiva**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-286">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0c0eb-287">**Granska dina inställningar**: Klicka på **Redigera** för att gå tillbaka till sidan **Avancerade nätfiskegränser.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-287">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0c0eb-288">När du är klar klickar du på **Spara** på någon av sidor.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-288">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0c0eb-289">Tillbaka på sidan **Redigera\> principnamn, \<** granska inställningarna och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-289">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="0c0eb-290">Använd Security & Compliance Center för att ändra standardprincipen för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="0c0eb-290">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="0c0eb-291">Standardprincipen för ATP-phishing heter Office365 AntiPhish Default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-291">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0c0eb-292">Så här ändrar du standardprincipen för ATP-bekämpningsfiske:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-292">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0c0eb-293">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-293">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-294">Klicka på **Standardprincip**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-294">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0c0eb-295">Sidan **Redigera din princip office365 AntiPhish Standard** visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-295">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0c0eb-296">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="0c0eb-296">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="0c0eb-297">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-297">**Impersonation**</span></span>
   - <span data-ttu-id="0c0eb-298">**Spolat**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-298">**Spoof**</span></span>
   - <span data-ttu-id="0c0eb-299">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-299">**Advanced settings**</span></span>

   <span data-ttu-id="0c0eb-300">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-300">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0c0eb-301">Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-301">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0c0eb-302">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-302">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0c0eb-303">Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-303">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0c0eb-304">På sidan **Redigera din princip office365 AntiPhish Standard** granskar du inställningarna och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-304">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-305">Aktivera eller inaktivera anpassade ATP-principer för phishing</span><span class="sxs-lookup"><span data-stu-id="0c0eb-305">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0c0eb-306">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-306">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-307">Lägg märke till värdet i kolumnen **Status:**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-307">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0c0eb-308">Dra växlingsknappen till **Av** för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-308">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0c0eb-309">Dra växlingsknappen till **På** för att aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-309">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0c0eb-310">Du kan inte inaktivera standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-310">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-311">Ange prioritet för anpassade ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-311">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="0c0eb-312">Som standard ges ATP-principer för phishing en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-312">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0c0eb-313">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-313">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0c0eb-314">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-314">No two policies can have the same priority.</span></span>

<span data-ttu-id="0c0eb-315">Anpassade ATP-principer för nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0c0eb-316">Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0c0eb-317">**I**Security & Compliance Center kan du bara ändra prioriteten för ATP-principen mot nätfiske när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="0c0eb-318">I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0c0eb-319">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0c0eb-320">Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0c0eb-321">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-322">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="0c0eb-323">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0c0eb-324">Den \*\*utfällbara sidan Redigera ditt principnamn \<\> \*\* visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0c0eb-325">Den anpassade ATP-principen mot nätfiske med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0c0eb-326">Den anpassade ATP-principen mot nätfiske med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0c0eb-327">Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0c0eb-328">Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0c0eb-329">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-330">Använda Security & Compliance Center för att visa ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0c0eb-331">I Security & Compliance Center och gå till **Atp-anti-phishing-principen** **mot hothanteringspolicy** \> **Policy** \> .</span><span class="sxs-lookup"><span data-stu-id="0c0eb-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-332">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="0c0eb-333">Välj en anpassad ATP-anti-phishing-princip som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0c0eb-334">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0c0eb-335">Klicka på **Standardprincip** om du vill visa standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0c0eb-336">Den \*\*utfällbara sidan Redigera ditt principnamn \<\> \*\* visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-337">Använd Security & Compliance Center för att ta bort ATP-principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0c0eb-338">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0c0eb-339">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="0c0eb-340">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0c0eb-341">Klicka på **Ta bort princip i**den utfällbara principen Redigera ditt \*\*principnamn \<\> \*\* som visas och klicka sedan på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0c0eb-342">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="0c0eb-343">Använda Exchange Online PowerShell för att konfigurera ATP-principer för phishing</span><span class="sxs-lookup"><span data-stu-id="0c0eb-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0c0eb-344">Använda PowerShell för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="0c0eb-344">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0c0eb-345">Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-345">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0c0eb-346">Skapa anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-346">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="0c0eb-347">Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-347">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0c0eb-348">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-348">**Notes**:</span></span>

- <span data-ttu-id="0c0eb-349">Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-349">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0c0eb-350">En anti-phish regel kan inte associeras med mer än en anti-phish politik.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-350">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0c0eb-351">Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-351">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0c0eb-352">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-352">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="0c0eb-353">Ange prioritet för principen när du skapar _(Prioritetsnummer)_ _ \<\>_ på cmdleten **Ny anti-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-353">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0c0eb-354">En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-354">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0c0eb-355">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="0c0eb-355">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0c0eb-356">Om du vill skapa en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-356">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0c0eb-357">I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-357">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0c0eb-358">Principen är aktiverad (vi använder inte parametern _Aktiverad_ och `$true`standardvärdet är ).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-358">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0c0eb-359">Beskrivningen är: Forskningsavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-359">The description is: Research department policy.</span></span>
- <span data-ttu-id="0c0eb-360">Aktiverar organisationsdomänskydd för alla accepterade domäner och riktade domänskydd för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-360">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0c0eb-361">Anger Mai Fujito (mfujito@fabrikam.com) som användare för att skydda mot personifiering.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-361">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0c0eb-362">Aktiverar postlådeinformation.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-362">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0c0eb-363">Aktiverar intelligensskydd för postlådor och anger karantänåtgärden.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-363">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0c0eb-364">Möjliggör säkerhetstips.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-364">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0c0eb-365">Detaljerad syntax- och parameterinformation finns i [Ny-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-365">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0c0eb-366">Steg 2: Använd PowerShell för att skapa en anti-phish-regel</span><span class="sxs-lookup"><span data-stu-id="0c0eb-366">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0c0eb-367">Om du vill skapa en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-367">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0c0eb-368">I det här exemplet skapas en anti-phish-regel med namnet Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-368">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0c0eb-369">Regeln är associerad med anti-phish-principen som heter Forskningskarantän.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-369">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0c0eb-370">Regeln gäller för medlemmar i gruppen som heter Forskningsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-370">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0c0eb-371">Eftersom vi inte använder parametern _Prioritet_ används standardprioriteten.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-371">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0c0eb-372">Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-372">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0c0eb-373">Använda PowerShell för att visa anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="0c0eb-373">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0c0eb-374">Om du vill visa befintliga anti-phish-principer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-374">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0c0eb-375">I det här exemplet returneras en sammanfattningslista över alla anti-phish-principer tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-375">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0c0eb-376">I det här exemplet returneras alla egenskapsvärden för anti-phish-principen Chefer.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-376">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0c0eb-377">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-377">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0c0eb-378">Använda PowerShell för att visa anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="0c0eb-378">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0c0eb-379">Om du vill visa befintliga anti-phish-regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-379">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0c0eb-380">I det här exemplet returneras en sammanfattningslista över alla anti-phish-regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-380">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0c0eb-381">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-381">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0c0eb-382">I det här exemplet returneras alla egenskapsvärden för anti-phish-regeln Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-382">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0c0eb-383">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-383">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0c0eb-384">Använda PowerShell för att ändra anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="0c0eb-384">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0c0eb-385">Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-385">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="0c0eb-386">_MakeDefault-växeln_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-386">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0c0eb-387">Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="0c0eb-387">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0c0eb-388">När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-388">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0c0eb-389">Om du vill ändra en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-389">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0c0eb-390">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-390">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0c0eb-391">Använda PowerShell för att ändra anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="0c0eb-391">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0c0eb-392">Den enda inställningen som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-392">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0c0eb-393">Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-393">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0c0eb-394">Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-394">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0c0eb-395">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-395">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0c0eb-396">Om du vill ändra en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-396">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0c0eb-397">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-397">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0c0eb-398">Använda PowerShell för att aktivera eller inaktivera anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="0c0eb-398">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0c0eb-399">Om du aktiverar eller inaktiverar en anti-phish-regel i PowerShell aktiveras eller inaktiveras hela anti-phishing-principen (anti-phish-regeln och den tilldelade anti-phish-principen).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-399">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0c0eb-400">Du kan inte aktivera eller inaktivera standardpolicyn mot nätfiske (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-400">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0c0eb-401">Om du vill aktivera eller inaktivera en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-401">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0c0eb-402">I det här exemplet inaktiveras anti-phish-regeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-402">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0c0eb-403">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-403">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0c0eb-404">Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-404">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0c0eb-405">Använd PowerShell för att ange prioritet för anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="0c0eb-405">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0c0eb-406">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-406">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0c0eb-407">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-407">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0c0eb-408">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-408">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0c0eb-409">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-409">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0c0eb-410">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-410">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0c0eb-411">Om du vill ange prioritet för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-411">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0c0eb-412">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-412">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0c0eb-413">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="0c0eb-413">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0c0eb-414">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-414">**Notes**:</span></span>

- <span data-ttu-id="0c0eb-415">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **Ny-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-415">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0c0eb-416">Standardanti-phish-principen har ingen motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-416">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0c0eb-417">Använda PowerShell för att ta bort anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="0c0eb-417">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0c0eb-418">När du använder PowerShell för att ta bort en anti-phish-princip tas inte motsvarande anti-phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-418">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0c0eb-419">Om du vill ta bort en anti-phish-princip i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-419">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0c0eb-420">I det här exemplet tas anti-phish-principen med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-420">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0c0eb-421">Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-421">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0c0eb-422">Använd PowerShell för att ta bort anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="0c0eb-422">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0c0eb-423">När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-423">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0c0eb-424">Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-424">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0c0eb-425">I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-425">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0c0eb-426">Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0c0eb-426">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0c0eb-427">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="0c0eb-427">How do you know these procedures worked?</span></span>

<span data-ttu-id="0c0eb-428">Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-428">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="0c0eb-429">I Security & Compliance Center går du till **ATP-principen** **Policy** \> **mot hothantering.** \></span><span class="sxs-lookup"><span data-stu-id="0c0eb-429">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0c0eb-430">Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-430">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0c0eb-431">Så här visar du mer information:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-431">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0c0eb-432">Välj principen i listan och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-432">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0c0eb-433">Klicka på **Standardprincip** och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-433">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0c0eb-434">I Exchange Online PowerShell ersätter du \<Namn\> med namnet på principen eller regeln och kör följande kommando och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="0c0eb-434">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
