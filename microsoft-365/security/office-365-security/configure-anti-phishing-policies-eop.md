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
ms.openlocfilehash: 5c2e036c075072056e7783ca4dc5aeb1289d827a
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213394"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="ca2c3-103">Konfigurera principer för nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="ca2c3-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="ca2c3-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor finns det en standardpolicy mot nätfiske som innehåller ett begränsat antal anti-spoofing-funktioner som är aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="ca2c3-105">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="ca2c3-106">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ca2c3-107">För större granularitet kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ca2c3-108">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ca2c3-109">Organisationer med Exchange Online-postlådor kan konfigurera principer mot nätfiske i Security & Compliance Center eller Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="ca2c3-110">Fristående EOP-organisationer kan bara använda Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="ca2c3-111">Information om hur du skapar och ändrar de mer avancerade ATP-principerna för nätfiske som är tillgängliga i Office 365 Advanced Threat Protection (Office 365 ATP) finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="ca2c3-112">Principer mot nätfiske i Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca2c3-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="ca2c3-113">De grundläggande inslagen i en anti-phishing-policy är:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ca2c3-114">**Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="ca2c3-115">**Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ca2c3-116">Skillnaden mellan dessa två element är inte uppenbar när du hanterar anti-phishing-principer i Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ca2c3-117">När du skapar en anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="ca2c3-118">När du ändrar en anti-phishing-princip i Security & Compliance Center ändras regeln mot alla inställningar som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ca2c3-119">Alla andra inställningar ändrar den associerade anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="ca2c3-120">När du tar bort en anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ca2c3-121">I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ca2c3-122">Du hanterar anti-phish-principer med hjälp av cmdlets \*\* \* -AntiPhishPolicy\*\* och hanterar anti-phish-regler med hjälp av cmdlets \*\* \* -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="ca2c3-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ca2c3-123">I PowerShell skapar du principen anti-phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="ca2c3-124">I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="ca2c3-125">Standardprincip för ATP-phishing</span><span class="sxs-lookup"><span data-stu-id="ca2c3-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="ca2c3-126">Varje organisation har en inbyggd anti-phishing-princip med namnet Office365 AntiPhish Standard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ca2c3-127">Principen Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="ca2c3-128">Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ca2c3-129">Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="ca2c3-130">Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har `True` värdet) och du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ca2c3-131">Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca2c3-132">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ca2c3-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca2c3-133">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ca2c3-134">Om du vill gå direkt till sidan **Mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ca2c3-135">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="ca2c3-136">Du kan inte hantera anti-phishing-principer i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="ca2c3-137">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ca2c3-138">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ca2c3-139">För skrivskyddad åtkomst till anti-phishing-principer måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="ca2c3-140">Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="ca2c3-141">För att kunna skapa och ändra anti-spam-policyer i fristående EOP måste du göra något som kräver _hydrering_ för din klient.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-141">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="ca2c3-142">I EAC kan du till exempel gå till fliken **Behörigheter,** välja en befintlig rollgrupp, klicka på **Redigera** ![ redigera ikon och ta bort en roll ](../../media/ITPro-EAC-EditIcon.png) (som du slutligen lägger till).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-142">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="ca2c3-143">Om din klient aldrig har hydrerats får du en dialogruta med namnet **Uppdatera organisationsinställningar** med ett förloppsindikator som ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-143">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="ca2c3-144">Mer information om hydrering finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) (som inte är tillgänglig i fristående EOP PowerShell eller i Security & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-144">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="ca2c3-145">Våra rekommenderade inställningar för anti-phishing-principer finns i [EOP:s standardinställningar för anti-nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-145">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="ca2c3-146">Tillåt upp till 30 minuter för den uppdaterade principen som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-146">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="ca2c3-147">Information om var principer mot nätfiske tillämpas i filtreringspipelinen finns i [Ordning och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-147">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="ca2c3-148">Använda Security & Compliance Center för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-148">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="ca2c3-149">Om du skapar en anpassad anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-149">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ca2c3-150">När du skapar en anti-phishing-princip kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-150">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ca2c3-151">När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-151">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ca2c3-152">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-153">Klicka på **Skapa**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-153">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ca2c3-154">Guiden **Skapa en ny anti-phishing-princip** öppnas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-154">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ca2c3-155">Konfigurera följande inställningar på sidan Namn på **principen:**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-155">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ca2c3-156">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ca2c3-157">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-157">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ca2c3-158">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-158">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ca2c3-159">På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-159">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ca2c3-160">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-160">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ca2c3-161">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<mottagare1\>_ eller _\<mottagare2\>_).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-161">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ca2c3-162">Olika villkor och undantag använder OCH-logik (till exempel _\<mottagare1\>_ och _\<medlem i grupp 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-162">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ca2c3-163">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-163">Click **Add a condition**.</span></span> <span data-ttu-id="ca2c3-164">I listrutan som visas väljer du ett villkor under **Tillämpad om:**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-164">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ca2c3-165">**Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-165">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ca2c3-166">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-166">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ca2c3-167">**Mottagardomänen är**: Anger mottagare i en eller flera av de konfigurerade accepterade domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-167">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="ca2c3-168">När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-168">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ca2c3-169">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-169">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ca2c3-170">Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-170">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ca2c3-171">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-171">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ca2c3-172">Om du vill ta bort enskilda poster klickar du på **Ikonen Ta bort** ta bort i ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-172">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ca2c3-173">Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-173">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ca2c3-174">Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-174">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ca2c3-175">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-175">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ca2c3-176">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-176">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ca2c3-177">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-177">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ca2c3-178">Granska **inställningarna** på sidan Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-178">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ca2c3-179">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-179">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ca2c3-180">När du är klar klickar du på **Skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-180">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ca2c3-181">Klicka på **OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-181">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ca2c3-182">När du har skapat principen mot nätfiske med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-182">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="ca2c3-183">Använda Security & Compliance Center för att ändra anti-phishing-principer</span><span class="sxs-lookup"><span data-stu-id="ca2c3-183">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="ca2c3-184">Använd följande procedurer för att ändra anti-phishing-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-184">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ca2c3-185">Om du inte redan är där öppnar du Security & Compliance **Threat management** Center och går till \> **Policy** \> **Anti-phishing för**hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-185">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-186">Välj den anpassade anti-phishing-principen som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-186">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ca2c3-187">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-187">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca2c3-188">Den \*\*utfällbara sidan Redigera ditt \< principnamn \> \*\* visas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-188">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ca2c3-189">Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-189">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ca2c3-190">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-190">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ca2c3-191">När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Ikonen Avbryt** eller **Stäng** avsluta för att återgå till sidan Redigera ![ ditt ](../../media/scc-remove-icon.png) \*\* \< principnamn \> \*\* (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-191">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ca2c3-192">**Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-192">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="ca2c3-193">**Name**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-193">**Name**</span></span>
   - <span data-ttu-id="ca2c3-194">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-194">**Description**</span></span>
   - <span data-ttu-id="ca2c3-195">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-195">**Applied to**</span></span>
   - <span data-ttu-id="ca2c3-196">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-196">**Review your settings**</span></span>

   <span data-ttu-id="ca2c3-197">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-197">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ca2c3-198">**Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-198">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ca2c3-199">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-199">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ca2c3-200">Observera att samma inställningar också är tillgängliga i ATP:s principer för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-200">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="ca2c3-201">**Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-201">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ca2c3-202">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-202">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ca2c3-203">Mer information finns [i Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-203">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ca2c3-204">Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-204">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ca2c3-205">Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-205">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ca2c3-206">**Aktivera funktionen Oautentiserade avsändare:** Standardvärdet är **På**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-206">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ca2c3-207">Om du vill inaktivera den drar du växlingsknappen till **Av**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-207">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ca2c3-208">**Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-208">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ca2c3-209">**Om e-post skickas av någon som inte får förfalska din domän:**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-209">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ca2c3-210">**Flytta meddelande till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-210">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ca2c3-211">**Karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-211">**Quarantine the message**</span></span>

   - <span data-ttu-id="ca2c3-212">**Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-212">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ca2c3-213">Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-213">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ca2c3-214">Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-214">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ca2c3-215">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-215">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ca2c3-216">**Aktivera funktionen Oautentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-216">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ca2c3-217">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-217">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ca2c3-218">Tillbaka på sidan **Redigera \< \> principnamn,** granska inställningarna och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-218">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="ca2c3-219">Använd Security & Compliance Center för att ändra standardprincipen mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-219">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="ca2c3-220">Standardprincipen mot nätfiske heter Office365 AntiPhish Default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-220">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ca2c3-221">Så här ändrar du standardpolicyn mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-221">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ca2c3-222">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-223">Klicka på **Standardprincip**på sidan **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-223">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ca2c3-224">Sidan **Redigera din princip office365 AntiPhish Standard** visas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-224">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ca2c3-225">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-225">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="ca2c3-226">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-226">**Impersonation**</span></span>
   - <span data-ttu-id="ca2c3-227">**Spolat**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-227">**Spoof**</span></span>
   - <span data-ttu-id="ca2c3-228">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-228">**Advanced settings**</span></span>

   <span data-ttu-id="ca2c3-229">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-229">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ca2c3-230">Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-230">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ca2c3-231">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-231">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ca2c3-232">Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-232">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ca2c3-233">På sidan **Redigera din princip office365 AntiPhish Standard** granskar du inställningarna och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-233">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="ca2c3-234">Aktivera eller inaktivera anpassade principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-234">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="ca2c3-235">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-235">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-236">Lägg märke till värdet i kolumnen **Status:**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-236">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ca2c3-237">Dra växlingsknappen till **Av** för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-237">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ca2c3-238">Dra växlingsknappen till **På** för att aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-238">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ca2c3-239">Du kan inte inaktivera standardpolicyn mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-239">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="ca2c3-240">Ange prioritet för anpassade principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-240">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="ca2c3-241">Som standard ges anti-phishing-principer en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-241">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ca2c3-242">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-242">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ca2c3-243">Två principer kan inte ha samma prioritet.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-243">No two policies can have the same priority.</span></span>

<span data-ttu-id="ca2c3-244">Anpassade principer mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ca2c3-245">Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade **prioritetsvärdet Lägsta**och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ca2c3-246">**I**Security & Compliance Center kan du bara ändra prioriteten för anti-phishing-principen när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ca2c3-247">I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ca2c3-248">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ca2c3-249">Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ca2c3-250">I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-251">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="ca2c3-252">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca2c3-253">Den \*\*utfällbara sidan Redigera ditt \< principnamn \> \*\* visas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ca2c3-254">Den anpassade anti-phishing-principen med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ca2c3-255">Den anpassade anti-phishing-principen med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ca2c3-256">Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ca2c3-257">Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ca2c3-258">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="ca2c3-259">Använda Security & Compliance Center för att visa principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="ca2c3-260">I Security & Compliance Center och gå till **Policy** \> **Policy** \> **anti-phishing**för hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-261">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="ca2c3-262">Välj en anpassad anti-phishing-princip som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ca2c3-263">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ca2c3-264">Klicka på **Standardprincip** om du vill visa standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ca2c3-265">Den \*\*utfällbara sidan Redigera ditt \< principnamn \> \*\* visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="ca2c3-266">Använd Security & Compliance Center för att ta bort principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="ca2c3-267">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ca2c3-268">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="ca2c3-269">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca2c3-270">Klicka på **Ta bort princip i**den utfällbara principen Redigera ditt \*\* \< \> principnamn\*\* som visas och klicka sedan på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ca2c3-271">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="ca2c3-272">Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="ca2c3-273">Följande procedurer är inte tillgängliga i fristående EOP-organisationer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-273">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ca2c3-274">Använda PowerShell för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ca2c3-274">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ca2c3-275">Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-275">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ca2c3-276">Skapa anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-276">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="ca2c3-277">Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-277">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ca2c3-278">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-278">**Notes**:</span></span>

- <span data-ttu-id="ca2c3-279">Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-279">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ca2c3-280">En anti-phish regel kan inte associeras med mer än en anti-phish politik.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-280">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ca2c3-281">Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-281">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ca2c3-282">Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-282">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="ca2c3-283">Ange prioritet för principen när du skapar _ \< \> (Prioritetsnummer)_ på cmdleten **Ny anti-AntiPhishRule).** _Priority_</span><span class="sxs-lookup"><span data-stu-id="ca2c3-283">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ca2c3-284">En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-284">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ca2c3-285">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="ca2c3-285">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ca2c3-286">Om du vill skapa en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-286">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="ca2c3-287">I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-287">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ca2c3-288">Principen är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-288">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ca2c3-289">Beskrivningen är: Forskningsavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-289">The description is: Research department policy.</span></span>
- <span data-ttu-id="ca2c3-290">Ändrar standardåtgärden för förfalskning till karantän.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-290">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="ca2c3-291">Detaljerad syntax- och parameterinformation finns i [Ny-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-291">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ca2c3-292">Steg 2: Använd PowerShell för att skapa en anti-phish-regel</span><span class="sxs-lookup"><span data-stu-id="ca2c3-292">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ca2c3-293">Om du vill skapa en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-293">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ca2c3-294">I det här exemplet skapas en anti-phish-regel med namnet Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-294">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ca2c3-295">Regeln är associerad med anti-phish-principen som heter Forskningskarantän.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-295">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ca2c3-296">Regeln gäller för medlemmar i gruppen som heter Forskningsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-296">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ca2c3-297">Eftersom vi inte använder parametern _Prioritet_ används standardprioriteten.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-297">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ca2c3-298">Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-298">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ca2c3-299">Använda PowerShell för att visa anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="ca2c3-299">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ca2c3-300">Om du vill visa befintliga anti-phish-principer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-300">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca2c3-301">I det här exemplet returneras en sammanfattningslista över alla anti-phish-principer tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-301">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ca2c3-302">I det här exemplet returneras alla egenskapsvärden för anti-phish-principen Chefer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-302">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ca2c3-303">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-303">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ca2c3-304">Använda PowerShell för att visa anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="ca2c3-304">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ca2c3-305">Om du vill visa befintliga anti-phish-regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-305">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca2c3-306">I det här exemplet returneras en sammanfattningslista över alla anti-phish-regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-306">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ca2c3-307">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-307">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ca2c3-308">I det här exemplet returneras alla egenskapsvärden för anti-phish-regeln Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-308">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ca2c3-309">Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-309">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ca2c3-310">Använda PowerShell för att ändra anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="ca2c3-310">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ca2c3-311">Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-311">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="ca2c3-312">_MakeDefault-växeln_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-312">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ca2c3-313">Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="ca2c3-313">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ca2c3-314">När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-314">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ca2c3-315">Om du vill ändra en anti-phish-princip använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-315">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ca2c3-316">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-316">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ca2c3-317">Använda PowerShell för att ändra anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="ca2c3-317">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ca2c3-318">Den enda inställningen som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-318">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ca2c3-319">Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-319">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ca2c3-320">Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-320">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ca2c3-321">Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-321">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ca2c3-322">Om du vill ändra en anti-phish-regel använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-322">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ca2c3-323">Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-323">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ca2c3-324">Använda PowerShell för att aktivera eller inaktivera anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="ca2c3-324">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ca2c3-325">Om du aktiverar eller inaktiverar en anti-phish-regel i PowerShell aktiveras eller inaktiveras hela anti-phishing-principen (anti-phish-regeln och den tilldelade anti-phish-principen).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-325">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ca2c3-326">Du kan inte aktivera eller inaktivera standardpolicyn mot nätfiske (den tillämpas alltid på alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-326">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ca2c3-327">Om du vill aktivera eller inaktivera en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-327">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ca2c3-328">I det här exemplet inaktiveras anti-phish-regeln med namnet Marknadsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-328">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca2c3-329">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-329">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca2c3-330">Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-330">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ca2c3-331">Använd PowerShell för att ange prioritet för anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="ca2c3-331">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ca2c3-332">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-332">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ca2c3-333">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-333">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ca2c3-334">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-334">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ca2c3-335">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-335">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ca2c3-336">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-336">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ca2c3-337">Om du vill ange prioritet för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-337">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ca2c3-338">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-338">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ca2c3-339">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="ca2c3-339">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ca2c3-340">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-340">**Notes**:</span></span>

- <span data-ttu-id="ca2c3-341">Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **Ny-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-341">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ca2c3-342">Standardanti-phish-principen har ingen motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-342">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ca2c3-343">Använda PowerShell för att ta bort anti-phish-principer</span><span class="sxs-lookup"><span data-stu-id="ca2c3-343">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ca2c3-344">När du använder PowerShell för att ta bort en anti-phish-princip tas inte motsvarande anti-phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-344">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ca2c3-345">Om du vill ta bort en anti-phish-princip i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-345">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ca2c3-346">I det här exemplet tas anti-phish-principen med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-346">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ca2c3-347">Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-347">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ca2c3-348">Använd PowerShell för att ta bort anti-phish-regler</span><span class="sxs-lookup"><span data-stu-id="ca2c3-348">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ca2c3-349">När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-349">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ca2c3-350">Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-350">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ca2c3-351">I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-351">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca2c3-352">Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="ca2c3-352">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ca2c3-353">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="ca2c3-353">How do you know these procedures worked?</span></span>

<span data-ttu-id="ca2c3-354">Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-354">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="ca2c3-355">Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="ca2c3-355">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="ca2c3-356">Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="ca2c3-356">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ca2c3-357">Så här visar du mer information:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-357">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ca2c3-358">Välj principen i listan och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-358">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ca2c3-359">Klicka på **Standardprincip** och visa informationen i utfällbara.</span><span class="sxs-lookup"><span data-stu-id="ca2c3-359">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ca2c3-360">I Exchange Online PowerShell ersätter du \< Namn med namnet på principen eller regeln och kör följande kommando och verifiera \> inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ca2c3-360">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
