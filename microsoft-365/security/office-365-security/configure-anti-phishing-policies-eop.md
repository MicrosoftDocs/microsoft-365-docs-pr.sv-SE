---
title: Konfigurera principer för nätfiske i EOP
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
description: Administratörer kan lära sig hur du skapar, ändrar och tar bort de anti-nätfiskeprinciper som är tillgängliga i EOP-organisationer (Exchange Online Protection) med eller utan Exchange Online-postlådor.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726784"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="281dc-103">Konfigurera principer för nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="281dc-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="281dc-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor finns det en standardpolicy mot nätfiske som innehåller ett begränsat antal anti-spoofing-funktioner som är aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="281dc-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="281dc-105">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="281dc-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="281dc-106">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="281dc-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="281dc-107">För större granularitet kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="281dc-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="281dc-108">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="281dc-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="281dc-109">Organisationer med Exchange Online-postlådor kan konfigurera principer mot nätfiske i Security & Compliance Center eller Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="281dc-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="281dc-110">Fristående EOP-organisationer kan bara använda Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="281dc-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="281dc-111">Information om hur du skapar och ändrar de mer avancerade ATP-principerna för nätfiske som är tillgängliga i Office 365 Advanced Threat Protection (Office 365 ATP) finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="281dc-112">Principer mot nätfiske i Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="281dc-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="281dc-113">De grundläggande inslagen i en anti-phishing-policy är:</span><span class="sxs-lookup"><span data-stu-id="281dc-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="281dc-114">**Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="281dc-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="281dc-115">**Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="281dc-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="281dc-116">Skillnaden mellan dessa två element är inte uppenbar när du hanterar anti-phishing-principer i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="281dc-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="281dc-117">När du skapar en anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="281dc-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="281dc-118">När du ändrar en anti-phishing-princip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter anti-phish-regeln.</span><span class="sxs-lookup"><span data-stu-id="281dc-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="281dc-119">Alla andra inställningar ändrar den associerade anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="281dc-120">När du tar bort en anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="281dc-121">I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="281dc-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="281dc-122">Du hanterar anti-phish-principer med hjälp av cmdleterna \*\* \* -AntiPhishPolicy\*\* och hanterar anti-phish-regler med hjälp av cmdlets \*\* \* -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="281dc-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="281dc-123">I PowerShell skapar du principen mot phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="281dc-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="281dc-124">I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="281dc-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="281dc-125">Standardprincip för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="281dc-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="281dc-126">Varje organisation har en inbyggd anti-phishing-princip med namnet Office365 AntiPhish Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="281dc-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="281dc-127">Principen Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="281dc-128">Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="281dc-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="281dc-129">Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="281dc-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="281dc-130">Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har värdet `True` ) och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="281dc-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="281dc-131">Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="281dc-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="281dc-132">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="281dc-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="281dc-133">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="281dc-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="281dc-134">Om du vill gå direkt till sidan **Mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="281dc-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="281dc-135">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="281dc-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="281dc-136">Du kan inte hantera anti-phishing-principer i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="281dc-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="281dc-137">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="281dc-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="281dc-138">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="281dc-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="281dc-139">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="281dc-140">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="281dc-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="281dc-141">För skrivskyddad åtkomst till anti-phishing-policyer måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="281dc-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="281dc-142">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="281dc-143">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="281dc-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="281dc-144">För att kunna skapa och ändra anti-spam politik i fristående EOP, måste du göra något som kräver _hydrering_ för din hyresgäst.</span><span class="sxs-lookup"><span data-stu-id="281dc-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="281dc-145">I Administrationscentret för Exchange (EAC) kan du till exempel gå till fliken **Behörigheter,** välja en befintlig rollgrupp, klicka på **Redigera** ![ redigera ikon och ta bort en roll ](../../media/ITPro-EAC-EditIcon.png) (som du slutligen lägger till).</span><span class="sxs-lookup"><span data-stu-id="281dc-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="281dc-146">Om din klient aldrig har hydrerats får du en dialogruta med namnet **Uppdatera organisationsinställningar** med ett förloppsindikator som ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="281dc-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="281dc-147">Mer information om hydrering finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (som inte är tillgänglig i fristående EOP PowerShell eller i Security & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="281dc-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="281dc-148">Våra rekommenderade inställningar för anti-phishing-principer finns i [EOP:s standardinställningar för anti-nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="281dc-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="281dc-149">Tillåt upp till 30 minuter för den uppdaterade principen som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="281dc-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="281dc-150">Information om var anti-nätfiskeprinciper tillämpas i filtreringspipelinen finns i [Ordning och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="281dc-151">Använda Security & Compliance Center för att skapa policyer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="281dc-152">Om du skapar en anpassad anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="281dc-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="281dc-153">När du skapar en anti-phishing-princip kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="281dc-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="281dc-154">När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="281dc-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="281dc-155">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-156">Klicka på **Skapa**på sidan **Anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="281dc-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="281dc-157">Guiden **Skapa en ny anti-phishing-princip** öppnas.</span><span class="sxs-lookup"><span data-stu-id="281dc-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="281dc-158">Konfigurera följande inställningar på sidan Namn på **principen:**</span><span class="sxs-lookup"><span data-stu-id="281dc-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="281dc-159">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="281dc-160">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="281dc-161">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="281dc-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="281dc-162">På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="281dc-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="281dc-163">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="281dc-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="281dc-164">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="281dc-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="281dc-165">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="281dc-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="281dc-166">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="281dc-166">Click **Add a condition**.</span></span> <span data-ttu-id="281dc-167">I listrutan som visas väljer du ett villkor under **Tillämpad om:**</span><span class="sxs-lookup"><span data-stu-id="281dc-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="281dc-168">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="281dc-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="281dc-169">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="281dc-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="281dc-170">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="281dc-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="281dc-171">När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**</span><span class="sxs-lookup"><span data-stu-id="281dc-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="281dc-172">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="281dc-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="281dc-173">Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="281dc-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="281dc-174">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="281dc-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="281dc-175">Om du vill ta bort enskilda poster klickar du på **Ikonen Ta bort** ta bort i ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="281dc-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="281dc-176">Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="281dc-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="281dc-177">Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.</span><span class="sxs-lookup"><span data-stu-id="281dc-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="281dc-178">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**.</span><span class="sxs-lookup"><span data-stu-id="281dc-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="281dc-179">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="281dc-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="281dc-180">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="281dc-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="281dc-181">Granska **inställningarna** på sidan Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="281dc-182">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="281dc-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="281dc-183">När du är klar klickar du på **Skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="281dc-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="281dc-184">Klicka på **OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="281dc-185">När du har skapat principen mot nätfiske med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="281dc-186">Använda Security & Compliance Center för att ändra anti-phishing-principer</span><span class="sxs-lookup"><span data-stu-id="281dc-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="281dc-187">Använd följande procedurer för att ändra anti-phishing-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="281dc-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="281dc-188">Om du inte redan är där öppnar du Security & Compliance **Threat management** Center och går till \> **Policy** \> **Anti-phishing för**hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="281dc-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-189">Välj den anpassade anti-phishing-principen som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="281dc-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="281dc-190">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="281dc-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="281dc-191">**Den Redigera \<name\> din princip** utfällbara visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="281dc-192">Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="281dc-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="281dc-193">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="281dc-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="281dc-194">När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Ikonen Avbryt** eller **Stäng** avsluta för att återgå till sidan Redigera ![ din ](../../media/scc-remove-icon.png) \*\*princip \<name\> \*\* (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="281dc-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="281dc-195">**Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="281dc-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="281dc-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="281dc-196">**Name**</span></span>
   - <span data-ttu-id="281dc-197">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="281dc-197">**Description**</span></span>
   - <span data-ttu-id="281dc-198">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="281dc-198">**Applied to**</span></span>
   - <span data-ttu-id="281dc-199">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="281dc-199">**Review your settings**</span></span>

   <span data-ttu-id="281dc-200">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="281dc-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="281dc-201">**Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="281dc-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="281dc-202">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="281dc-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="281dc-203">Observera att samma inställningar också är tillgängliga i ATP:s principer för phishing.Note that these same settings are also available in ATP anti-phishing policies.</span><span class="sxs-lookup"><span data-stu-id="281dc-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="281dc-204">**Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på.</span><span class="sxs-lookup"><span data-stu-id="281dc-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="281dc-205">Om du vill stänga av den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="281dc-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="281dc-206">Mer information finns [i Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="281dc-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="281dc-207">Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kontakter i stället.</span><span class="sxs-lookup"><span data-stu-id="281dc-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="281dc-208">Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="281dc-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="281dc-209">**Aktivera funktionen Oautentiserad avsändare**: Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="281dc-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="281dc-210">Om du vill stänga av den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="281dc-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="281dc-211">**Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="281dc-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="281dc-212">**Om e-post skickas av någon som inte får förfalska din domän:**</span><span class="sxs-lookup"><span data-stu-id="281dc-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="281dc-213">**Flytta meddelande till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="281dc-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="281dc-214">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="281dc-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="281dc-215">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="281dc-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="281dc-216">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="281dc-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="281dc-217">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="281dc-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="281dc-218">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="281dc-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="281dc-219">**Aktivera funktionen Oautentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="281dc-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="281dc-220">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="281dc-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="281dc-221">Tillbaka på **sidan \<Name\> Redigera din princip,** granska dina inställningar och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="281dc-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="281dc-222">Använd Security & Compliance Center för att ändra standardpolicyn mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="281dc-223">Standardprincipen mot nätfiske heter Office365 AntiPhish Default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="281dc-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="281dc-224">Så här ändrar du standardpolicyn mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="281dc-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="281dc-225">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-226">Klicka på **Standardprincip**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="281dc-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="281dc-227">Sidan **Redigera din princip office365 AntiPhish Standard** visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="281dc-228">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="281dc-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="281dc-229">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="281dc-229">**Impersonation**</span></span>
   - <span data-ttu-id="281dc-230">**Spolat**</span><span class="sxs-lookup"><span data-stu-id="281dc-230">**Spoof**</span></span>
   - <span data-ttu-id="281dc-231">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="281dc-231">**Advanced settings**</span></span>

   <span data-ttu-id="281dc-232">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="281dc-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="281dc-233">Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="281dc-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="281dc-234">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="281dc-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="281dc-235">Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="281dc-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="281dc-236">På sidan **Redigera din princip office365 AntiPhish Standard** granskar du dina inställningar och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="281dc-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="281dc-237">Aktivera eller inaktivera anpassade principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="281dc-238">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-239">Lägg märke till värdet i kolumnen **Status:**</span><span class="sxs-lookup"><span data-stu-id="281dc-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="281dc-240">Dra växlingsknappen till **Av** för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="281dc-241">Dra växlingsknappen till **På** för att aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="281dc-242">Du kan inte inaktivera standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="281dc-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="281dc-243">Ange prioritet för anpassade principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="281dc-244">Som standard ges anti-phishing-principer en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="281dc-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="281dc-245">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="281dc-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="281dc-246">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="281dc-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="281dc-247">Anpassade principer mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="281dc-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="281dc-248">Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="281dc-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="281dc-249">**I**Security & Compliance Center kan du bara ändra prioriteten för anti-phishing-principen när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="281dc-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="281dc-250">I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="281dc-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="281dc-251">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i principens egenskaper (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center).</span><span class="sxs-lookup"><span data-stu-id="281dc-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="281dc-252">Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="281dc-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="281dc-253">Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-254">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="281dc-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="281dc-255">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="281dc-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="281dc-256">**Den Redigera \<name\> din princip** utfällbara visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="281dc-257">Den anpassade anti-phishing-principen med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="281dc-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="281dc-258">Den anpassade anti-phishing-principen med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="281dc-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="281dc-259">Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="281dc-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="281dc-260">Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="281dc-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="281dc-261">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="281dc-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="281dc-262">Använda Security & Compliance Center för att visa principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="281dc-263">I Security & Compliance Center och gå till **Policy** \> **Policy** \> **anti-phishing**för hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="281dc-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-264">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="281dc-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="281dc-265">Välj en anpassad anti-phishing-princip som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="281dc-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="281dc-266">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="281dc-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="281dc-267">Klicka på **Standardprincip** om du vill visa standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="281dc-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="281dc-268">Den **Redigera \<name\> din princip** utfällbara visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="281dc-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="281dc-269">Använda Security & Compliance Center för att ta bort principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="281dc-270">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="281dc-271">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="281dc-272">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="281dc-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="281dc-273">Klicka på **Ta bort princip**i utfällningen redigera din \*\*princip \<name\> \*\* och klicka sedan på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="281dc-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="281dc-274">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="281dc-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="281dc-275">Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="281dc-276">Följande procedurer är inte tillgängliga i fristående EOP-organisationer.</span><span class="sxs-lookup"><span data-stu-id="281dc-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="281dc-277">Använda PowerShell för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="281dc-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="281dc-278">Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="281dc-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="281dc-279">Skapa anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="281dc-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="281dc-280">Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="281dc-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="281dc-281">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="281dc-281">**Notes**:</span></span>

- <span data-ttu-id="281dc-282">Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="281dc-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="281dc-283">En anti-phish regel kan inte associeras med mer än en anti-phish politik.</span><span class="sxs-lookup"><span data-stu-id="281dc-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="281dc-284">Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="281dc-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="281dc-285">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="281dc-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="281dc-286">Ange prioritet för principen när du skapar (_Prioritet_ _\<Number\>_ ) på cmdleten **Ny antiphishRule).**</span><span class="sxs-lookup"><span data-stu-id="281dc-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="281dc-287">En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="281dc-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="281dc-288">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="281dc-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="281dc-289">Om du vill skapa en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="281dc-290">I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="281dc-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="281dc-291">Principen är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="281dc-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="281dc-292">Beskrivningen är: Forskningsavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="281dc-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="281dc-293">Ändrar standardåtgärden för förfalskning till karantän.</span><span class="sxs-lookup"><span data-stu-id="281dc-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="281dc-294">Detaljerad syntax- och parameterinformation finns i [Ny AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="281dc-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="281dc-295">Steg 2: Använd PowerShell för att skapa en anti-phish-regel</span><span class="sxs-lookup"><span data-stu-id="281dc-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="281dc-296">Om du vill skapa en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="281dc-297">I det här exemplet skapas en anti-phish-regel med namnet Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="281dc-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="281dc-298">Regeln är associerad med anti-phish-principen som heter Forskningskarantän.</span><span class="sxs-lookup"><span data-stu-id="281dc-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="281dc-299">Regeln gäller för medlemmar i gruppen som heter Forskningsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="281dc-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="281dc-300">Eftersom vi inte använder parametern _Prioritet_ används standardprioriteten.</span><span class="sxs-lookup"><span data-stu-id="281dc-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="281dc-301">Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="281dc-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="281dc-302">Använda PowerShell för att visa anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="281dc-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="281dc-303">Om du vill visa befintliga anti-phish-principer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="281dc-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="281dc-304">I det här exemplet returneras en sammanfattningslista över alla anti-phish-principer tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="281dc-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="281dc-305">I det här exemplet returneras alla egenskapsvärden för anti-phish-principen Chefer.</span><span class="sxs-lookup"><span data-stu-id="281dc-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="281dc-306">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="281dc-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="281dc-307">Använda PowerShell för att visa anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="281dc-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="281dc-308">Om du vill visa befintliga anti-phish-regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="281dc-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="281dc-309">I det här exemplet returneras en sammanfattningslista över alla anti-phish-regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="281dc-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="281dc-310">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="281dc-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="281dc-311">I det här exemplet returneras alla egenskapsvärden för anti-phish-regeln Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="281dc-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="281dc-312">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="281dc-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="281dc-313">Använda PowerShell för att ändra anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="281dc-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="281dc-314">Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="281dc-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="281dc-315">_Den MakeDefault-växel_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="281dc-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="281dc-316">Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="281dc-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="281dc-317">När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.</span><span class="sxs-lookup"><span data-stu-id="281dc-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="281dc-318">Om du vill ändra en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="281dc-319">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="281dc-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="281dc-320">Använda PowerShell för att ändra anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="281dc-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="281dc-321">Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="281dc-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="281dc-322">Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="281dc-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="281dc-323">Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="281dc-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="281dc-324">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="281dc-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="281dc-325">Om du vill ändra en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="281dc-326">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="281dc-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="281dc-327">Använda PowerShell för att aktivera eller inaktivera anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="281dc-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="281dc-328">Om du aktiverar eller inaktiverar en anti-phish-regel i PowerShell aktiveras eller inaktiveras hela anti-phishing-principen (anti-phish-regeln och den tilldelade anti-phish-principen).</span><span class="sxs-lookup"><span data-stu-id="281dc-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="281dc-329">Du kan inte aktivera eller inaktivera standardpolicyn mot nätfiske (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="281dc-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="281dc-330">Om du vill aktivera eller inaktivera en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="281dc-331">I det här exemplet inaktiveras anti-phish-regeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="281dc-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="281dc-332">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="281dc-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="281dc-333">Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="281dc-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="281dc-334">Använd PowerShell för att ange prioritet för anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="281dc-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="281dc-335">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="281dc-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="281dc-336">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="281dc-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="281dc-337">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="281dc-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="281dc-338">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="281dc-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="281dc-339">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="281dc-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="281dc-340">Om du vill ange prioritet för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="281dc-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="281dc-341">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="281dc-341">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="281dc-342">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="281dc-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="281dc-343">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="281dc-343">**Notes**:</span></span>

- <span data-ttu-id="281dc-344">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **Ny-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="281dc-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="281dc-345">Standardanti-phish-principen har inte en motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="281dc-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="281dc-346">Använda PowerShell för att ta bort anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="281dc-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="281dc-347">När du använder PowerShell för att ta bort en anti-phish-princip tas inte motsvarande anti-phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="281dc-348">Om du vill ta bort en anti-phish-princip i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="281dc-349">I det här exemplet tas anti-phish-principen med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="281dc-350">Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="281dc-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="281dc-351">Använda PowerShell för att ta bort anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="281dc-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="281dc-352">När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="281dc-353">Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="281dc-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="281dc-354">I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="281dc-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="281dc-355">Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="281dc-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="281dc-356">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="281dc-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="281dc-357">Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:</span><span class="sxs-lookup"><span data-stu-id="281dc-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="281dc-358">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="281dc-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="281dc-359">Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="281dc-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="281dc-360">Så här visar du mer information:</span><span class="sxs-lookup"><span data-stu-id="281dc-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="281dc-361">Välj principen i listan och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="281dc-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="281dc-362">Klicka på **Standardprincip** och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="281dc-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="281dc-363">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="281dc-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
