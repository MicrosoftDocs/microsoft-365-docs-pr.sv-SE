---
title: Konfigurera AntiPhishing-principer i EOP
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
description: Administratörer kan lära sig hur de skapar, ändrar och tar bort de anti-phishing-principer som är tillgängliga i EOP-organisationer (Exchange Online Protection) med eller utan Exchange Online-postlådor.
ms.openlocfilehash: 3b83bcd3c60dbd779d727a79f6689fdf0004d340
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255763"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="21e4d-103">Konfigurera AntiPhishing-principer i EOP</span><span class="sxs-lookup"><span data-stu-id="21e4d-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="21e4d-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det en standard policy för skydd mot förfalskning som är aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="21e4d-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="21e4d-105">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="21e4d-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="21e4d-106">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="21e4d-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="21e4d-107">Om du vill ha större precision kan du även skapa anpassade AntiPhishing-principer som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="21e4d-108">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="21e4d-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="21e4d-109">Organisationer med Exchange Online-postlådor kan konfigurera AntiPhishing-principer i säkerhets & efterlevnads Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e4d-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="21e4d-110">Fristående EOP organisationer kan bara använda säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="21e4d-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="21e4d-111">Information om hur du skapar och ändrar de mer avancerade principer för ATP-nätfiske som är tillgängliga i Office 365 Avancerat skydd (Office 365 ATP) finns i avsnittet [Konfigurera Antinätfiske-principer för ATP](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="21e4d-112">De grundläggande delarna i en Antivirus policy är:</span><span class="sxs-lookup"><span data-stu-id="21e4d-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="21e4d-113">**Policyn för Phish**: anger skydds alternativen för nätfiske för att aktivera eller inaktivera och åtgärderna för att tillämpa alternativ.</span><span class="sxs-lookup"><span data-stu-id="21e4d-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="21e4d-114">**Regeln för Phish**: anger de prioritets-och mottagar filter (som principen gäller för) för en policy mot anti-Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="21e4d-115">Skillnaden mellan dessa två element är inte uppenbar när du hanterar skydd mot nätfiske i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="21e4d-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="21e4d-116">När du skapar en AntiPhishing-princip skapar du verkligen en Phish regel och tillhör ande policy för anti-Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="21e4d-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="21e4d-117">När du ändrar en skydds princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra regeln för Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="21e4d-118">Alla andra inställningar ändra den associerade policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="21e4d-119">När du tar bort en AntiPhishing-princip tas regeln mot Phish och tillhör ande policy mot Phish bort.</span><span class="sxs-lookup"><span data-stu-id="21e4d-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="21e4d-120">I Exchange Online PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="21e4d-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="21e4d-121">Mer information finns i avsnittet [använda Exchange Online PowerShell för att konfigurera principer för nätfiske (policys](#use-exchange-online-powershell-to-configure-anti-phishing-policies) ) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21e4d-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="21e4d-122">Varje organisation har en inbyggd policy för anti-nätfiske som heter Office365 AntiPhish standard och har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="21e4d-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="21e4d-123">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-Phish-regel (mottagar filter) som är kopplade till principen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="21e4d-124">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="21e4d-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="21e4d-125">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="21e4d-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="21e4d-126">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="21e4d-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="21e4d-127">För att öka effektiviteten för skydd mot nätfiske kan du skapa anpassade skydds principer med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="21e4d-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21e4d-128">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="21e4d-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="21e4d-129">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="21e4d-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="21e4d-130">För att gå direkt till **nätfiske-** sidan, Använd <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="21e4d-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="21e4d-131">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="21e4d-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="21e4d-132">Du kan inte hantera anti-nätfiske-principer i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e4d-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="21e4d-133">Du måste tilldelas behörigheter innan du kan utföra åtgärderna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="21e4d-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="21e4d-134">För att lägga till, ändra och ta bort skydd mot nätfiske måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="21e4d-134">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="21e4d-135">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="21e4d-136">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="21e4d-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="21e4d-137">För skrivskyddad åtkomst till principer mot nätfiske måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="21e4d-137">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="21e4d-138">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="21e4d-139">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="21e4d-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="21e4d-140">Om du vill skapa och ändra skydds principer för fristående EOP måste du göra något som kräver _Hydration_ för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="21e4d-140">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="21e4d-141">I Exchange Admin Center (UK) kan du till exempel gå till fliken **behörigheter** , välja en befintlig roll grupp, klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och ta bort en roll (som du kommer att lägga till igen).</span><span class="sxs-lookup"><span data-stu-id="21e4d-141">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="21e4d-142">Om klient organisationen aldrig har fått en sådan status får du en dialog som heter **Update organisations inställningar** med en förlopps indikator som ska utföras.</span><span class="sxs-lookup"><span data-stu-id="21e4d-142">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="21e4d-143">Mer information om Hydration finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (som inte är tillgänglig i den fristående EOP PowerShell eller i säkerhets & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="21e4d-143">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="21e4d-144">De rekommenderade inställningarna för skydd mot nätfiske finns i [EOP standardinställningar för skydd mot nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="21e4d-144">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="21e4d-145">Tillåt upp till 30 minuter innan den uppdaterade policyn tillämpas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-145">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="21e4d-146">Information om var anti-nätfiske-principer tillämpas i filtrerings pipeline finns i [order och prioritetsordning för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="21e4d-147">Skapa principer för nätfiske med hjälp av säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="21e4d-147">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="21e4d-148">Om du skapar en anpassad skydds princip i säkerhets & Compliance Center skapar regeln mot Phish och tillhör ande policy mot Phish med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="21e4d-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="21e4d-149">När du skapar en AntiPhishing-princip kan du bara ange princip namnet, beskrivningen och det mottagar filter som identifierar vem principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="21e4d-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="21e4d-150">När du har skapat den här principen kan du ändra principen för att ändra eller granska standardinställningarna för nät fiske inställningar.</span><span class="sxs-lookup"><span data-stu-id="21e4d-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="21e4d-151">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-152">Klicka på **skapa**på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="21e4d-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="21e4d-153">Guiden **skapa en ny policy för skydd mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="21e4d-154">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="21e4d-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="21e4d-155">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="21e4d-156">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="21e4d-157">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="21e4d-158">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="21e4d-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="21e4d-159">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="21e4d-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="21e4d-160">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="21e4d-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="21e4d-161">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="21e4d-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="21e4d-162">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-162">Click **Add a condition**.</span></span> <span data-ttu-id="21e4d-163">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om**:</span><span class="sxs-lookup"><span data-stu-id="21e4d-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="21e4d-164">**Mottagaren är**: anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="21e4d-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="21e4d-165">**Mottagaren är medlem i**: anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="21e4d-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="21e4d-166">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="21e4d-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="21e4d-167">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="21e4d-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="21e4d-168">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="21e4d-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="21e4d-169">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="21e4d-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="21e4d-170">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="21e4d-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="21e4d-171">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="21e4d-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="21e4d-172">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="21e4d-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="21e4d-173">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="21e4d-174">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="21e4d-175">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="21e4d-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="21e4d-176">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="21e4d-177">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="21e4d-178">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="21e4d-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="21e4d-179">När du är klar klickar du på **skapa den här principen**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="21e4d-180">Klicka på **OK** i bekräftelse dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="21e4d-181">När du har skapat AntiPhishing-principen med dessa allmänna princip inställningar följer du anvisningarna i nästa avsnitt för att konfigurera skydds inställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-181">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="21e4d-182">Använda säkerhets & Compliance Center för att ändra principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="21e4d-182">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="21e4d-183">Använd följande procedurer för att ändra anti-nätfiske-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="21e4d-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="21e4d-184">Om du inte redan har gjort det öppnar du säkerhets & efterlevnad och går till skydd mot **hot Management** \> **policy** \> **mot nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-185">Välj den anpassade Antivirus princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="21e4d-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="21e4d-186">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="21e4d-187">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="21e4d-188">Om du klickar på **Redigera** i ett avsnitt får du till gång till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="21e4d-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="21e4d-189">Följande anvisningar visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="21e4d-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="21e4d-190">När du har klickat på **Redigera** i ett avsnitt visas de tillgängliga inställningarna i ett guide format, men du kan hoppa mellan sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Avbryt** eller **Stäng** Stäng-ikonen om du vill ![ ](../../media/scc-remove-icon.png) gå tillbaka till sidan \*\*Redigera din policy \<name\> \*\* ).</span><span class="sxs-lookup"><span data-stu-id="21e4d-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="21e4d-191">**Princip inställning**: Klicka på **Redigera** om du vill ändra samma inställningar som fanns tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies) i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="21e4d-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="21e4d-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="21e4d-192">**Name**</span></span>
   - <span data-ttu-id="21e4d-193">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="21e4d-193">**Description**</span></span>
   - <span data-ttu-id="21e4d-194">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="21e4d-194">**Applied to**</span></span>
   - <span data-ttu-id="21e4d-195">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="21e4d-195">**Review your settings**</span></span>

   <span data-ttu-id="21e4d-196">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="21e4d-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="21e4d-197">**Falska**användare: Klicka på **Redigera** för att aktivera eller inaktivera förfalsknings intelligens, aktivera och inaktivera overifierad avsändare i Outlook och konfigurera åtgärden så att den gäller för meddelanden från blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="21e4d-197">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="21e4d-198">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="21e4d-198">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="21e4d-199">Observera att dessa inställningar också är tillgängliga i tilläggsprogram för ATP.</span><span class="sxs-lookup"><span data-stu-id="21e4d-199">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="21e4d-200">**Inställningar för förfalsknings filter**: standardvärdet är **på**och vi rekommenderar att du lämnar det.</span><span class="sxs-lookup"><span data-stu-id="21e4d-200">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="21e4d-201">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="21e4d-201">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="21e4d-202">Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-202">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="21e4d-203">Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="21e4d-203">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="21e4d-204">Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="21e4d-204">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="21e4d-205">**Aktivera overifierad avsändare**: standardvärdet är **på**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-205">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="21e4d-206">Inaktivera växlings knappen för att **stänga av den.**</span><span class="sxs-lookup"><span data-stu-id="21e4d-206">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="21e4d-207">**Åtgärder**: ange vilken åtgärd som ska vidtas för meddelanden som saknar förfalsknings information:</span><span class="sxs-lookup"><span data-stu-id="21e4d-207">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="21e4d-208">**Om e-post skickas av någon som inte har tillåtelse att imitera din domän**:</span><span class="sxs-lookup"><span data-stu-id="21e4d-208">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="21e4d-209">**Flytta meddelandet till mottagarnas skräp post mappar**</span><span class="sxs-lookup"><span data-stu-id="21e4d-209">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="21e4d-210">**Sätt i karantän meddelandet**</span><span class="sxs-lookup"><span data-stu-id="21e4d-210">**Quarantine the message**</span></span>

   - <span data-ttu-id="21e4d-211">**Granska dina inställningar**: i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="21e4d-211">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="21e4d-212">Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.</span><span class="sxs-lookup"><span data-stu-id="21e4d-212">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="21e4d-213">Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:</span><span class="sxs-lookup"><span data-stu-id="21e4d-213">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="21e4d-214">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="21e4d-214">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="21e4d-215">**Aktivera ej autentiserad avsändare**</span><span class="sxs-lookup"><span data-stu-id="21e4d-215">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="21e4d-216">När du är klar klickar du på **Spara** på valfri sida.</span><span class="sxs-lookup"><span data-stu-id="21e4d-216">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="21e4d-217">Gå tillbaka till sidan **Redigera din \<Name\> policy** och granska inställningarna och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-217">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="21e4d-218">Använda säkerhets & Compliance Center för att ändra standard policyn för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="21e4d-218">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="21e4d-219">Standard policyn för anti-phishing heter Office365 AntiPhish default och visas inte i listan över principer.</span><span class="sxs-lookup"><span data-stu-id="21e4d-219">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="21e4d-220">Gör så här om du vill ändra standard principen för anti-nätfiske:</span><span class="sxs-lookup"><span data-stu-id="21e4d-220">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="21e4d-221">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-222">Klicka på **standard princip**på sidan **mot nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="21e4d-222">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="21e4d-223">**Standard sidan Redigera policyn för Office365 AntiPhish** visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-223">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="21e4d-224">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="21e4d-224">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="21e4d-225">**Falsk identitet**</span><span class="sxs-lookup"><span data-stu-id="21e4d-225">**Impersonation**</span></span>
   - <span data-ttu-id="21e4d-226">**Falskt**</span><span class="sxs-lookup"><span data-stu-id="21e4d-226">**Spoof**</span></span>
   - <span data-ttu-id="21e4d-227">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="21e4d-227">**Advanced settings**</span></span>

   <span data-ttu-id="21e4d-228">Följande inställningar är inte tillgängliga när du ändrar standard princip:</span><span class="sxs-lookup"><span data-stu-id="21e4d-228">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="21e4d-229">Du kan se avsnitt och värden för **princip inställningar** , men det finns inga **redigerings** länkar, så du kan inte ändra inställningarna (princip namn, beskrivning och vem principen gäller för (gäller alla mottagare)).</span><span class="sxs-lookup"><span data-stu-id="21e4d-229">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="21e4d-230">Du kan inte ta bort standard principen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-230">You can't delete the default policy.</span></span>
   - <span data-ttu-id="21e4d-231">Du kan inte ändra prioriteten för standard principen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="21e4d-231">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="21e4d-232">På **standard sidan Redigera en Office365 AntiPhish** du på Inställningar och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-232">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="21e4d-233">Aktivera eller inaktivera anpassade nät fiske principer</span><span class="sxs-lookup"><span data-stu-id="21e4d-233">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="21e4d-234">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-235">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="21e4d-235">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="21e4d-236">Inaktivera principen genom att dra till **av** .</span><span class="sxs-lookup"><span data-stu-id="21e4d-236">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="21e4d-237">Aktivera principen genom att dra den till **aktiverat** .</span><span class="sxs-lookup"><span data-stu-id="21e4d-237">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="21e4d-238">Du kan inte inaktivera standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="21e4d-238">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="21e4d-239">Ange prioritet för anpassade anti-phishing-principer</span><span class="sxs-lookup"><span data-stu-id="21e4d-239">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="21e4d-240">Som standard får anti-nätfiske-principer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="21e4d-240">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="21e4d-241">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="21e4d-241">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="21e4d-242">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="21e4d-242">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="21e4d-243">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="21e4d-243">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="21e4d-244">Anpassade principer för anti-nätfiske visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="21e4d-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="21e4d-245">Standard policyn för anti-phishing med namnet Office365 AntiPhish standard har värdet **lägst**och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="21e4d-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="21e4d-246">**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för skydd mot nätfiske när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="21e4d-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="21e4d-247">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln mot Phish (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="21e4d-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="21e4d-248">Om du vill ändra prioriteten för en princip klickar du på **öka prioriteten** eller **minska prioriteten** i egenskaperna för principen (du kan inte direkt ändra **prioritets** numret i säkerhets & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="21e4d-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="21e4d-249">Det är bara att ändra prioriteten för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="21e4d-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="21e4d-250">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-251">Välj den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="21e4d-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="21e4d-252">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="21e4d-253">**Redigera den utfällbara \<name\> principen** visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="21e4d-254">Den anpassade AntiPhishing-principen med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21e4d-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="21e4d-255">Den anpassade AntiPhishing-principen med lägst **prioritet** (till exempel **3**) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21e4d-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="21e4d-256">Om du har tre eller fler anpassade nät fiske principer har de värden mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21e4d-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="21e4d-257">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="21e4d-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="21e4d-258">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="21e4d-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="21e4d-259">Använd säkerhets & Compliance Center för att visa principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="21e4d-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="21e4d-260">I säkerhets & Compliance Center och gå till skydd mot **hot Management** \> **policy** \> **mot nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-261">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="21e4d-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="21e4d-262">Välj en anpassad Antivirus policy som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="21e4d-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="21e4d-263">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="21e4d-264">Klicka på **standard princip** för att Visa standard policyn för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="21e4d-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="21e4d-265">**Redigera den utfällbara \<name\> principen** visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="21e4d-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="21e4d-266">Använda säkerhets & Compliance Center för att ta bort skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="21e4d-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="21e4d-267">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="21e4d-268">Välj den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="21e4d-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="21e4d-269">Om det redan är markerat avmarkerar du det och väljer det igen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="21e4d-270">I redigera den utfällbara \*\*princip \<name\> \*\* som visas klickar du på **ta bort princip**och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="21e4d-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="21e4d-271">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="21e4d-272">Använda Exchange Online PowerShell för att konfigurera skydd mot nätfiske-principer</span><span class="sxs-lookup"><span data-stu-id="21e4d-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="21e4d-273">Som tidigare beskrivits består en policy för skydd mot Phish och en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="21e4d-273">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="21e4d-274">I Exchange Online PowerShell är skillnaden mellan policyer för Phish och Phish regler uppenbar.</span><span class="sxs-lookup"><span data-stu-id="21e4d-274">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="21e4d-275">Du hanterar policyn för Phish genom att använda cmdletarna \*\* \* -AntiPhishPolicy\*\* och du hanterar anti-Phish-regler med hjälp av cmdlet \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="21e4d-275">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="21e4d-276">I PowerShell skapar du policyn för Phish först och sedan skapar du regeln mot Phish som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="21e4d-276">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="21e4d-277">I PowerShell ändrar du inställningarna i policyn för Phish och anti-Phish-regeln separat.</span><span class="sxs-lookup"><span data-stu-id="21e4d-277">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="21e4d-278">När du tar bort en policy för Phish från PowerShell tas motsvarande antiphish-regel inte bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="21e4d-278">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="21e4d-279">Följande PowerShell-procedurer är inte tillgängliga i fristående EOP-organisationer med Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e4d-279">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="21e4d-280">Använda PowerShell för att skapa skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="21e4d-280">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="21e4d-281">Att skapa en skydds policy i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="21e4d-281">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="21e4d-282">Skapa policyn för Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-282">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="21e4d-283">Skapa en regel för Phish som anger den policy för anti-Phish som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="21e4d-283">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="21e4d-284">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="21e4d-284">**Notes**:</span></span>

- <span data-ttu-id="21e4d-285">Du kan skapa en ny Phish regel och koppla en befintlig, icke associerad policy mot anti-Phish-princip till den.</span><span class="sxs-lookup"><span data-stu-id="21e4d-285">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="21e4d-286">En antiphish-regel kan inte kopplas till fler än en anti-Phish princip.</span><span class="sxs-lookup"><span data-stu-id="21e4d-286">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="21e4d-287">Du kan konfigurera följande inställningar i nya principer mot Phish i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="21e4d-287">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="21e4d-288">Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-AntiPhishRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="21e4d-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="21e4d-289">Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya AntiPhishRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="21e4d-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="21e4d-290">En ny policy för Phish som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en antiphish-regel.</span><span class="sxs-lookup"><span data-stu-id="21e4d-290">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="21e4d-291">Steg 1: använda PowerShell för att skapa en policy för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-291">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="21e4d-292">Använd följande syntax för att skapa en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="21e4d-292">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="21e4d-293">I det här exemplet skapas en policy med Phish forsknings karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="21e4d-293">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="21e4d-294">Beskrivningen är: policy för forsknings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-294">The description is: Research department policy.</span></span>
- <span data-ttu-id="21e4d-295">Ändrar standard åtgärden för förfalskning till karantän.</span><span class="sxs-lookup"><span data-stu-id="21e4d-295">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="21e4d-296">Detaljerad information om syntax och parametrar finns i [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="21e4d-296">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="21e4d-297">Steg 2: använda PowerShell för att skapa en regel för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-297">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="21e4d-298">Använd följande syntax för att skapa en Phish-regel:</span><span class="sxs-lookup"><span data-stu-id="21e4d-298">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="21e4d-299">I det här exemplet skapas en Phish regel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="21e4d-299">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="21e4d-300">Regeln associeras med policyn för Phish med namnet forsknings karantän.</span><span class="sxs-lookup"><span data-stu-id="21e4d-300">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="21e4d-301">Regeln gäller för medlemmar i gruppen Research avdelning.</span><span class="sxs-lookup"><span data-stu-id="21e4d-301">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="21e4d-302">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="21e4d-302">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="21e4d-303">Detaljerad information om syntax och parametrar finns i [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="21e4d-303">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="21e4d-304">Använda PowerShell för att visa principer mot Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-304">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="21e4d-305">Använd följande syntax för att visa befintliga principer för Phish:</span><span class="sxs-lookup"><span data-stu-id="21e4d-305">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="21e4d-306">I det här exemplet returneras en sammanfattande lista över alla Phish-principer tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="21e4d-306">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="21e4d-307">I det här exemplet returneras alla egenskapsvärde för Phish policy med namnet chefer.</span><span class="sxs-lookup"><span data-stu-id="21e4d-307">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="21e4d-308">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="21e4d-308">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="21e4d-309">Använda PowerShell för att visa regler för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-309">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="21e4d-310">Använd följande syntax för att visa befintliga regler för Phish:</span><span class="sxs-lookup"><span data-stu-id="21e4d-310">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="21e4d-311">I det här exemplet returneras en sammanfattande lista över alla Phish regler tillsammans med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="21e4d-311">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="21e4d-312">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="21e4d-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="21e4d-313">I det här exemplet returneras alla egenskaps värden för Phish regeln contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="21e4d-313">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="21e4d-314">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="21e4d-314">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="21e4d-315">Använda PowerShell för att ändra policyn för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-315">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="21e4d-316">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en policy mot Phish i PowerShell som när du skapar en princip enligt beskrivningen i [steg 1: använda PowerShell för att skapa en policy för att Phish en](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare version av den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21e4d-316">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="21e4d-317">_MakeDefault_ -växeln som aktiverar den angivna principen till standard principen (tillämpas på alla, alltid **lägst** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en policy mot Phish i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e4d-317">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="21e4d-318">Du kan inte byta namn på en policy mot Phish ( **set-AntiPhishPolicy** -cmdleten har ingen _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="21e4d-318">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="21e4d-319">När du byter namn på en skydds princip i säkerhets & Compliance Center byter du bara namn på _regeln_mot Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-319">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="21e4d-320">Använd följande syntax för att ändra en policy för Phish:</span><span class="sxs-lookup"><span data-stu-id="21e4d-320">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="21e4d-321">Detaljerad information om syntax och parametrar finns i [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="21e4d-321">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="21e4d-322">Använda PowerShell för att ändra regler för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-322">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="21e4d-323">Den enda inställning som inte är tillgänglig när du ändrar en anti-Phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="21e4d-323">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="21e4d-324">Information om hur du aktiverar eller inaktiverar befintliga regler för Phish finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="21e4d-324">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="21e4d-325">I annat fall är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en antiphish regel](#step-2-use-powershell-to-create-an-anti-phish-rule) -avsnitt tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21e4d-325">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="21e4d-326">Om du vill ändra en Phish regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="21e4d-326">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="21e4d-327">Detaljerad information om syntax och parametrar finns i [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="21e4d-327">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="21e4d-328">Använda PowerShell för att aktivera eller inaktivera Phish regler</span><span class="sxs-lookup"><span data-stu-id="21e4d-328">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="21e4d-329">Aktivering eller inaktive ring av en Phish regel i PowerShell aktiverar eller inaktiverar hela AntiPhishing-principen (anti-Phish-regeln och den tilldelade anti-Phish-principen).</span><span class="sxs-lookup"><span data-stu-id="21e4d-329">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="21e4d-330">Du kan inte aktivera eller inaktivera standard policyn för skydd mot nätfiske (det gäller alltid alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="21e4d-330">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="21e4d-331">Så här aktiverar eller inaktiverar du en Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21e4d-331">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="21e4d-332">I det här exemplet inaktive ras den Phish marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-332">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="21e4d-333">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="21e4d-333">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="21e4d-334">Detaljerad information om syntax och parametrar finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) och [disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="21e4d-334">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="21e4d-335">Använd PowerShell för att ange prioriteten för antiphish-regler</span><span class="sxs-lookup"><span data-stu-id="21e4d-335">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="21e4d-336">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="21e4d-336">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="21e4d-337">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="21e4d-337">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="21e4d-338">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="21e4d-338">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="21e4d-339">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="21e4d-339">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="21e4d-340">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="21e4d-340">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="21e4d-341">Använd följande syntax för att ange prioriteten för en anti-Phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21e4d-341">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="21e4d-342">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="21e4d-342">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="21e4d-343">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="21e4d-343">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="21e4d-344">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="21e4d-344">**Notes**:</span></span>

- <span data-ttu-id="21e4d-345">Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-AntiPhishRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="21e4d-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="21e4d-346">Standard policyn för Phish har ingen motsvarande anti-Phish-regel och har alltid det icke ändrings bara prioritet svärdet **lägst**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-346">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="21e4d-347">Använda PowerShell för att ta bort principer för Phish</span><span class="sxs-lookup"><span data-stu-id="21e4d-347">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="21e4d-348">När du använder PowerShell för att ta bort en policy för Phish, tas inte motsvarande antiphish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="21e4d-348">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="21e4d-349">Använd följande syntax för att ta bort en policy för Phish i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21e4d-349">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="21e4d-350">I det här exemplet tas policyn för Phish bort från marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-350">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="21e4d-351">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="21e4d-351">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="21e4d-352">Använda PowerShell för att ta bort Phish regler</span><span class="sxs-lookup"><span data-stu-id="21e4d-352">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="21e4d-353">När du använder PowerShell för att ta bort en antiphish-regel tas motsvarande policy mot Phish inte bort.</span><span class="sxs-lookup"><span data-stu-id="21e4d-353">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="21e4d-354">Om du vill ta bort en Phish regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="21e4d-354">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="21e4d-355">Det här exemplet tar bort regeln marknadsförings avdelning för Phish.</span><span class="sxs-lookup"><span data-stu-id="21e4d-355">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="21e4d-356">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="21e4d-356">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="21e4d-357">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="21e4d-357">How do you know these procedures worked?</span></span>

<span data-ttu-id="21e4d-358">Gör något av följande om du vill verifiera att du har konfigurerat ATP-skydds principer:</span><span class="sxs-lookup"><span data-stu-id="21e4d-358">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="21e4d-359">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="21e4d-359">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="21e4d-360">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="21e4d-360">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="21e4d-361">Gör något av följande om du vill visa mer information:</span><span class="sxs-lookup"><span data-stu-id="21e4d-361">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="21e4d-362">Välj en princip i listan och visa detaljerna i den utfällbara informationen.</span><span class="sxs-lookup"><span data-stu-id="21e4d-362">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="21e4d-363">Klicka på **standard policy** och se informationen i utfällbar form.</span><span class="sxs-lookup"><span data-stu-id="21e4d-363">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="21e4d-364">I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln, kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="21e4d-364">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
