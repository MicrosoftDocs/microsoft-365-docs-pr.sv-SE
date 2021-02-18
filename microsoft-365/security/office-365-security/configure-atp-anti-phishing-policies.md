---
title: Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365
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
description: Administratörer kan lära sig att skapa, ändra och ta bort avancerade principer för nätfiske som är tillgängliga i organisationer med Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89b931b37119d7c8c689d0f3c044fcd550db67ab
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287503"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-103">Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="490b6-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="490b6-104">**Applies to**</span></span>
- [<span data-ttu-id="490b6-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="490b6-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="490b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="490b6-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="490b6-107">Skydd mot nätfiskeprinciper i Microsoft Defender för [Office 365](office-365-atp.md) kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra typer av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="490b6-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="490b6-108">Mer information om skillnaderna mellan principer för skydd mot nätfiske i Exchange Online Protection (EOP) och principer för skydd mot nätfiske i Microsoft Defender för Office 365 finns i Skydd mot [nätfiske.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="490b6-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="490b6-109">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="490b6-110">För att få bättre detaljnivå kan du också skapa anpassade principer för nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="490b6-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="490b6-111">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="490b6-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="490b6-112">Du kan konfigurera principer för skydd mot nätfiske i Säkerhets- & Compliance Center eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="490b6-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="490b6-113">Information om hur du konfigurerar mer begränsade principer mot nätfiske som är tillgängliga i organisationer med Exchange Online Protection (det vill säga organisationer som inte har Microsoft Defender för Office 365) finns i Konfigurera principer för nätfiske i [EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="490b6-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="490b6-114">De grundläggande elementen i en princip mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="490b6-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="490b6-115">**Anfingprincipen:** Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras samt de åtgärder som används.</span><span class="sxs-lookup"><span data-stu-id="490b6-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="490b6-116">**Den phish-regeln:** Anger prioritet och mottagarfilter (som principen gäller för) för en nätt phish-princip.</span><span class="sxs-lookup"><span data-stu-id="490b6-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="490b6-117">Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer mot nätfiske i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="490b6-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="490b6-118">När du skapar en princip skapar du i själva verket en antifishregel och den tillhörande nätt phish-principen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="490b6-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="490b6-119">När du ändrar en princip ändrar inställningar som rör namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter ändrar antifishregeln.</span><span class="sxs-lookup"><span data-stu-id="490b6-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="490b6-120">Alla andra inställningar ändrar den tillhörande anti-phish-principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="490b6-121">När du tar bort en princip tas den phish-regeln och den tillhörande skyddt phish-principen bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="490b6-122">I Exchange Online PowerShell hanterar du principen och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="490b6-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="490b6-123">Mer information finns i avsnittet Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske i avsnittet Microsoft Defender för [Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="490b6-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="490b6-124">Alla Microsoft Defender för Office 365-organisationer har en inbyggd policy mot nätfiske med namnet Office365 AntiPhish Default som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="490b6-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="490b6-125">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon skyddande phish-regel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="490b6-126">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="490b6-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="490b6-127">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="490b6-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="490b6-128">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="490b6-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="490b6-129">För att öka effektiviteten i skydd mot nätfiske i Microsoft Defender för Office 365 kan du skapa anpassade principer för nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="490b6-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="490b6-130">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="490b6-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="490b6-131">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="490b6-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="490b6-132">Om du vill gå direkt till **ATP-sidan mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="490b6-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="490b6-133">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="490b6-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="490b6-134">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="490b6-134">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="490b6-135">Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="490b6-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="490b6-136">För skrivskyddade åtkomst till principer för nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="490b6-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="490b6-137">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="490b6-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="490b6-138">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="490b6-138">**Notes**:</span></span>

  - <span data-ttu-id="490b6-139">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="490b6-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="490b6-140">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="490b6-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="490b6-141">Rollgruppen **Skrivskyddade organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till <sup>\*</sup> funktionen.</span><span class="sxs-lookup"><span data-stu-id="490b6-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="490b6-142"><sup>\*</sup> I Säkerhets- & efterlevnadscenter kan användare med skrivskyddsåtkomst visa inställningarna för anpassade principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="490b6-143">Skrivskyddade användare kan inte se inställningarna i standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="490b6-144">Vi rekommenderar inställningar för principer mot nätfiske i Microsoft Defender för Office 365 i Principen mot nätfiske i Defender för [Office 365-inställningar.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="490b6-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="490b6-145">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="490b6-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="490b6-146">Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordningen och [prioriteten för e-postskydd.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="490b6-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-147">Använd Säkerhets- & efterlevnadscenter för att skapa principer mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="490b6-148">När du skapar en anpassad policy för nätfiske i Säkerhets- & Efterlevnadscenter skapas samtidigt den skyddande phish-regeln och den tillhörande nätfiskeprincipen med samma namn.</span><span class="sxs-lookup"><span data-stu-id="490b6-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="490b6-149">När du skapar en princip mot nätfiske kan du bara ange namn, beskrivning och mottagarfilter som identifierar vem principen gäller.</span><span class="sxs-lookup"><span data-stu-id="490b6-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="490b6-150">När du har skapat principen kan du ändra den om du vill ändra eller granska standardinställningarna för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="490b6-151">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-152">Klicka på **Skapa på** sidan Mot **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="490b6-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="490b6-153">Guiden **Skapa en ny princip mot nätfiske** öppnas.</span><span class="sxs-lookup"><span data-stu-id="490b6-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="490b6-154">På sidan **Namnge principen** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="490b6-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="490b6-155">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="490b6-156">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="490b6-157">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="490b6-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="490b6-158">På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="490b6-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="490b6-159">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="490b6-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="490b6-160">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="490b6-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="490b6-161">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="490b6-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="490b6-162">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="490b6-162">Click **Add a condition**.</span></span> <span data-ttu-id="490b6-163">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="490b6-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="490b6-164">**Mottagaren är:** Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="490b6-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="490b6-165">**Mottagaren är medlem i:** Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="490b6-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="490b6-166">**Mottagardomänen är:** Anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="490b6-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="490b6-167">När du har valt villkoret visas en motsvarande listruta med **rutan Valfri av dessa.**</span><span class="sxs-lookup"><span data-stu-id="490b6-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="490b6-168">Klicka i rutan och bläddra igenom listan med värden för att välja.</span><span class="sxs-lookup"><span data-stu-id="490b6-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="490b6-169">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="490b6-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="490b6-170">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="490b6-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="490b6-171">Om du vill ta bort enskilda poster klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.</span><span class="sxs-lookup"><span data-stu-id="490b6-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="490b6-172">Om du vill ta bort hela villkoret klickar **du på ikonen** Ta bort i ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="490b6-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="490b6-173">Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om.**</span><span class="sxs-lookup"><span data-stu-id="490b6-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="490b6-174">Om du vill lägga till undantag **klickar du på Lägg till** ett villkor och väljer ett undantag under Utom **om.**</span><span class="sxs-lookup"><span data-stu-id="490b6-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="490b6-175">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="490b6-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="490b6-176">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="490b6-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="490b6-177">Granska **inställningarna på sidan** Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="490b6-178">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="490b6-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="490b6-179">Klicka på Skapa den här principen när **du är klar.**</span><span class="sxs-lookup"><span data-stu-id="490b6-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="490b6-180">Klicka **på OK** i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="490b6-181">När du har skapat principen för nätfiske med de här allmänna inställningarna följer du anvisningarna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-182">Använd Säkerhets- & Efterlevnadscenter för att ändra principer för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="490b6-183">Använd följande procedurer för att ändra principer för skydd mot nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.</span><span class="sxs-lookup"><span data-stu-id="490b6-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="490b6-184">Om du inte redan är där öppnar du Säkerhets- &  Efterlevnadscenter och går till ATP för hanteringspolicy för hot mot \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="490b6-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-185">Välj den anpassade principen för nätfiske som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="490b6-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="490b6-186">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="490b6-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="490b6-187">Den **utfällna knappen Redigera \<name\>** din princip visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="490b6-188">Om **du** klickar på Redigera i ett avsnitt får du åtkomst till inställningarna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="490b6-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="490b6-189">Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).</span><span class="sxs-lookup"><span data-stu-id="490b6-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="490b6-190">När du klickar på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men  du kan hoppa  inom  sidorna i valfri ordning och du kan klicka på Spara på valfri sida (eller  ![ ](../../media/scc-remove-icon.png) **\<name\>** ikonen Avbryt eller Stäng om du vill gå tillbaka till sidan Redigera principen (du behöver inte gå till den sista sidan i guiden för att spara eller lämna).</span><span class="sxs-lookup"><span data-stu-id="490b6-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="490b6-191">**Principinställning:** Klicka **på** Redigera om du vill ändra samma inställningar som var [tillgängliga när du](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) skapade principen i föregående avsnitt:</span><span class="sxs-lookup"><span data-stu-id="490b6-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="490b6-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="490b6-192">**Name**</span></span>
   - <span data-ttu-id="490b6-193">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="490b6-193">**Description**</span></span>
   - <span data-ttu-id="490b6-194">**Tillämpas på**</span><span class="sxs-lookup"><span data-stu-id="490b6-194">**Applied to**</span></span>
   - <span data-ttu-id="490b6-195">**Granska dina inställningar**</span><span class="sxs-lookup"><span data-stu-id="490b6-195">**Review your settings**</span></span>

   <span data-ttu-id="490b6-196">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="490b6-197">**Personifiering:** Klicka på **Redigera** om du vill ändra de skyddade avsändarna och de skyddade domänerna i principen.</span><span class="sxs-lookup"><span data-stu-id="490b6-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="490b6-198">De här inställningarna är ett villkor för principen som identifierar förfalskningsavsändare som ska leta efter (individuellt eller per domän) i avsändaradressen för inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="490b6-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="490b6-199">Mer information finns i inställningarna [för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="490b6-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="490b6-200">**Lägg till användare som ska** skydda: Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-201">Om du vill aktivera den drar du reglaget **till På** och klickar sedan på knappen **Lägg till** användare som visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="490b6-202">Konfigurera **följande värden i** den utfällblad för Lägg till användare som visas:</span><span class="sxs-lookup"><span data-stu-id="490b6-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="490b6-203">**E-postadress:**</span><span class="sxs-lookup"><span data-stu-id="490b6-203">**Email address**:</span></span>

       - <span data-ttu-id="490b6-204">Klicka i rutan och bläddra igenom listan med användare som du vill välja.</span><span class="sxs-lookup"><span data-stu-id="490b6-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="490b6-205">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="490b6-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="490b6-206">Om du vill ta bort en post klickar **du på** ikonen Ta bort ![ för ](../../media/scc-remove-icon.png) användaren.</span><span class="sxs-lookup"><span data-stu-id="490b6-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="490b6-207">**Namn:** Det här värdet fylls i baserat på e-postadressen du valde, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="490b6-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="490b6-208">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="490b6-209">Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.</span><span class="sxs-lookup"><span data-stu-id="490b6-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="490b6-210">I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser).</span><span class="sxs-lookup"><span data-stu-id="490b6-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="490b6-211">Du kan inte ange samma skyddade användare i flera principer.</span><span class="sxs-lookup"><span data-stu-id="490b6-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="490b6-212">Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post.</span><span class="sxs-lookup"><span data-stu-id="490b6-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="490b6-213">Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.</span><span class="sxs-lookup"><span data-stu-id="490b6-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="490b6-214">**Lägg till domäner att skydda:** Konfigurera en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="490b6-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="490b6-215">**Inkludera automatiskt domänerna som jag äger:** Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-216">Aktivera den genom att dra växlingsknappen till **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="490b6-217">**Ta med egna domäner:** Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-218">Aktivera den genom att dra reglaget till  På och ange domännamnet i rutan Lägg till domäner (till exempel contoso.com), tryck på RETUR och upprepa efter behov.</span><span class="sxs-lookup"><span data-stu-id="490b6-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="490b6-219">Du kan ha högst 50 domäner i alla principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="490b6-220">**Åtgärder:** Klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="490b6-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="490b6-221">**Om e-post** skickas av en imiterad användare: Konfigurera en av följande åtgärder för meddelanden där förfalskningsavsändaren är en av de skyddade användare som du har angett i Lägg till användare **för att skydda:**</span><span class="sxs-lookup"><span data-stu-id="490b6-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="490b6-222">**Använd ingen åtgärd**</span><span class="sxs-lookup"><span data-stu-id="490b6-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="490b6-223">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="490b6-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="490b6-224">**Flytta meddelandet till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="490b6-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="490b6-225">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="490b6-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="490b6-226">**Leverera meddelandet och lägga till andra adresser i raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="490b6-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="490b6-227">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="490b6-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="490b6-228">**Om e-post** skickas med en imiterad domän: Konfigurera någon av följande åtgärder för meddelanden där förfalskningsavsändaren finns på en av de skyddade domäner som du har angett i Lägg till **domäner att skydda:**</span><span class="sxs-lookup"><span data-stu-id="490b6-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="490b6-229">**Använd ingen åtgärd**</span><span class="sxs-lookup"><span data-stu-id="490b6-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="490b6-230">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="490b6-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="490b6-231">**Flytta meddelandet till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="490b6-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="490b6-232">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="490b6-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="490b6-233">**Leverera meddelandet och lägga till andra adresser i raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="490b6-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="490b6-234">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="490b6-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="490b6-235">Klicka **på aktivera säkerhetstips för personifiering** och konfigurera någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="490b6-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="490b6-236">**Visa tips för imiterade användare:** Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-237">Aktivera den genom att dra växlingsknappen till **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="490b6-238">**Visa tips för imiterade domäner:** Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-239">Aktivera den genom att dra växlingsknappen till **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="490b6-240">**Visa tips för ovanliga tecken:** Standardvärdet är **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="490b6-241">Aktivera den genom att dra växlingsknappen till **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="490b6-242">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="490b6-243">**Postlådeinformation:**</span><span class="sxs-lookup"><span data-stu-id="490b6-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="490b6-244">**Aktivera postlådeinformation?**: Standardvärdet är **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="490b6-245">Om du vill inaktivera den drar du reglaget till **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="490b6-246">**Aktivera personifieringsskydd baserat på postlådeinformation?**: Den här inställningen är endast tillgänglig om **Aktivera postlådeinformation?** är **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="490b6-247">I **Om** e-post skickas av en imiterad användare kan du ange någon av följande åtgärder för meddelanden som inte fungerar som postlådeinformation (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):</span><span class="sxs-lookup"><span data-stu-id="490b6-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="490b6-248">**Använd ingen åtgärd**</span><span class="sxs-lookup"><span data-stu-id="490b6-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="490b6-249">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="490b6-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="490b6-250">**Flytta meddelandet till mappen Skräppost**</span><span class="sxs-lookup"><span data-stu-id="490b6-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="490b6-251">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="490b6-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="490b6-252">**Leverera meddelandet och lägga till andra adresser i raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="490b6-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="490b6-253">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="490b6-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="490b6-254">**Lägg till betrodda avsändare och domäner:** Ange undantag för principen:</span><span class="sxs-lookup"><span data-stu-id="490b6-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="490b6-255">**Betrodda avsändare:**</span><span class="sxs-lookup"><span data-stu-id="490b6-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="490b6-256">Klicka i rutan och bläddra igenom listan med användare som du vill välja.</span><span class="sxs-lookup"><span data-stu-id="490b6-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="490b6-257">Klicka i rutan och börja skriva för att filtrera listan och välja en användare.</span><span class="sxs-lookup"><span data-stu-id="490b6-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="490b6-258">Om du vill ta bort en post klickar **du på** ikonen Ta bort ![ för ](../../media/scc-remove-icon.png) användaren.</span><span class="sxs-lookup"><span data-stu-id="490b6-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="490b6-259">**Betrodda** domäner: Ange domännamnet (till exempel contoso.com), tryck på RETUR och upprepa om det behövs.</span><span class="sxs-lookup"><span data-stu-id="490b6-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="490b6-260">**Granska dina inställningar:** i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="490b6-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="490b6-261">Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="490b6-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="490b6-262">Du kan aktivera eller inaktivera följande **inställningar** **direkt** på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="490b6-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="490b6-263">**Skyddade användare**</span><span class="sxs-lookup"><span data-stu-id="490b6-263">**Protected users**</span></span>
       - <span data-ttu-id="490b6-264">**Skyddade domäner** \> **Inkludera domäner som jag äger**</span><span class="sxs-lookup"><span data-stu-id="490b6-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="490b6-265">**Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)</span><span class="sxs-lookup"><span data-stu-id="490b6-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="490b6-266">**Postlådeinformation**</span><span class="sxs-lookup"><span data-stu-id="490b6-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="490b6-267">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="490b6-268">**Spoof:**  Klicka på Redigera för att aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthiskt identifiering av avsändare i Outlook och konfigurera åtgärden för meddelanden från blockerade förfalskningsavsändare.</span><span class="sxs-lookup"><span data-stu-id="490b6-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="490b6-269">Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="490b6-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="490b6-270">Observera att samma inställningar även är tillgängliga i principer för skydd mot nätfiske i EOP.</span><span class="sxs-lookup"><span data-stu-id="490b6-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="490b6-271">**Filterinställningar för förfalskning:** Standardvärdet är **På** och vi rekommenderar att du låter det vara på.</span><span class="sxs-lookup"><span data-stu-id="490b6-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="490b6-272">Om du vill inaktivera den drar du reglaget till **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="490b6-273">Mer information finns i [Konfigurera förfalskningsinformation i EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="490b6-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="490b6-274">Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="490b6-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="490b6-275">Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="490b6-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="490b6-276">**Aktivera funktionen Oauthenticerad avsändare:** Standardvärdet är **På.**</span><span class="sxs-lookup"><span data-stu-id="490b6-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="490b6-277">Om du vill inaktivera den drar du reglaget till **Av.**</span><span class="sxs-lookup"><span data-stu-id="490b6-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="490b6-278">**Åtgärder:** Ange vilken åtgärd som ska vidtas för meddelanden som inte klarar förfalskningsinformation:</span><span class="sxs-lookup"><span data-stu-id="490b6-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="490b6-279">**Om e-post skickas av någon som inte har tillåtelse att kapa din domän:**</span><span class="sxs-lookup"><span data-stu-id="490b6-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="490b6-280">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="490b6-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="490b6-281">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="490b6-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="490b6-282">**Granska dina inställningar:** i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="490b6-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="490b6-283">Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.</span><span class="sxs-lookup"><span data-stu-id="490b6-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="490b6-284">Du kan aktivera eller inaktivera följande **inställningar** **direkt** på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="490b6-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="490b6-285">**Aktivera skydd mot förfalskning**</span><span class="sxs-lookup"><span data-stu-id="490b6-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="490b6-286">**Aktivera funktionen Oauthenticerad avsändare**</span><span class="sxs-lookup"><span data-stu-id="490b6-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="490b6-287">Klicka på Spara på valfri sida **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="490b6-288">**Avancerade inställningar:** Klicka på **Redigera om du** vill konfigurera avancerade tröskelvärden för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="490b6-289">Mer information finns i Avancerade [tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="490b6-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="490b6-290">**Avancerade tröskelvärden för** nätfiske: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="490b6-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="490b6-291">**1 – Standard** (det här är standardvärdet.)</span><span class="sxs-lookup"><span data-stu-id="490b6-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="490b6-292">**2 – Aggressiv**</span><span class="sxs-lookup"><span data-stu-id="490b6-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="490b6-293">**3 – Mer aggressiva**</span><span class="sxs-lookup"><span data-stu-id="490b6-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="490b6-294">**4 – Mest aggressiva**</span><span class="sxs-lookup"><span data-stu-id="490b6-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="490b6-295">**Granska dina inställningar:** Klicka på **Redigera om** du vill gå tillbaka till **sidan Avancerade tröskelvärden för nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="490b6-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="490b6-296">Klicka på Spara på någon av sidorna **när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="490b6-297">Tillbaka på sidan **Redigera \<Name\> principen** granskar du inställningarna och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="490b6-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-298">Använd Säkerhets- & för att ändra standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="490b6-299">Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 kallas Office365 AntiPhish Default och visas inte i listan med principer.</span><span class="sxs-lookup"><span data-stu-id="490b6-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="490b6-300">Gör så här om du vill ändra standardprincipen för skydd mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="490b6-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="490b6-301">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-302">Klicka på **Standardprincip** på sidan **Skydd mot nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="490b6-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="490b6-303">Sidan **Redigera standardprincip för Office365-skydd visas.**</span><span class="sxs-lookup"><span data-stu-id="490b6-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="490b6-304">Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="490b6-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="490b6-305">**Personifiering**</span><span class="sxs-lookup"><span data-stu-id="490b6-305">**Impersonation**</span></span>
   - <span data-ttu-id="490b6-306">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="490b6-306">**Spoof**</span></span>
   - <span data-ttu-id="490b6-307">**Avancerade inställningar**</span><span class="sxs-lookup"><span data-stu-id="490b6-307">**Advanced settings**</span></span>

   <span data-ttu-id="490b6-308">Följande inställningar är inte tillgängliga när du ändrar standardprincipen:</span><span class="sxs-lookup"><span data-stu-id="490b6-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="490b6-309">Du kan  se avsnittet och värdena för principinställningen, men det finns ingen redigeringslänk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)). </span><span class="sxs-lookup"><span data-stu-id="490b6-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="490b6-310">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="490b6-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="490b6-311">Du kan inte ändra prioriteten för standardprincipen (den används alltid sist).</span><span class="sxs-lookup"><span data-stu-id="490b6-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="490b6-312">Granska inställningarna på sidan Redigera standardinställningen för principen i **Office365** och klicka sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="490b6-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-313">Aktivera eller inaktivera anpassade principer för nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="490b6-314">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-315">Observera värdet i **kolumnen** Status:</span><span class="sxs-lookup"><span data-stu-id="490b6-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="490b6-316">Inaktivera principen genom att dra **reglaget** till Av.</span><span class="sxs-lookup"><span data-stu-id="490b6-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="490b6-317">Aktivera principen genom att **dra reglaget** till På.</span><span class="sxs-lookup"><span data-stu-id="490b6-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="490b6-318">Du kan inte inaktivera standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-319">Ange prioritet för anpassade principer för nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="490b6-320">Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de har skapats (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="490b6-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="490b6-321">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="490b6-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="490b6-322">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="490b6-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="490b6-323">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="490b6-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="490b6-324">Anpassade principer för skydd mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="490b6-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="490b6-325">Standardprincipen för skydd mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** och du kan inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="490b6-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="490b6-326">**Obs!** I Säkerhets- & Efterlevnadscenter kan du bara ändra prioriteten för principen mot nätfiske efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="490b6-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="490b6-327">I PowerShell kan du åsidosätta standardprioritet när du skapar nätt phish-regeln (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="490b6-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="490b6-328">Om du vill ändra prioriteten för  en princip klickar du på Öka prioritet eller  Minska prioriteten för principens egenskaper (du kan inte direkt ändra prioritetsnumret i Säkerhets- & Efterlevnadscenter). </span><span class="sxs-lookup"><span data-stu-id="490b6-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="490b6-329">Att ändra prioritet för en princip är bara meningsfullt om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="490b6-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="490b6-330">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-331">Markera den princip som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="490b6-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="490b6-332">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="490b6-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="490b6-333">Den **utfällna knappen Redigera \<name\>** din princip visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="490b6-334">Den anpassade principen för nätfiske med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="490b6-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="490b6-335">Den anpassade principen för nätfiske med lägsta **prioritetsvärde** (till exempel **3)** har endast knappen Öka **prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="490b6-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="490b6-336">Om du har tre eller fler anpassade principer för skydd mot nätfiske finns det både knapparna Öka prioritet och Minska prioritet mellan de högsta och lägsta prioritetsvärdena.  </span><span class="sxs-lookup"><span data-stu-id="490b6-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="490b6-337">Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="490b6-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="490b6-338">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="490b6-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-339">Använd Säkerhets- & för att visa principer för skydd mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="490b6-340">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-341">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="490b6-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="490b6-342">Välj en anpassad princip för nätfiske som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="490b6-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="490b6-343">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="490b6-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="490b6-344">Klicka **på Standardprincip** om du vill visa standardprincipen för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="490b6-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="490b6-345">Den **utfällga \<name\>** menyn Redigera princip visas, där du kan visa inställningar och värden.</span><span class="sxs-lookup"><span data-stu-id="490b6-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-346">Använda Säkerhets- & för att ta bort nätfiskeprinciper i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="490b6-347">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="490b6-348">Markera den princip som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="490b6-349">Om den redan är markerad avmarkerar du den och markerar den igen.</span><span class="sxs-lookup"><span data-stu-id="490b6-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="490b6-350">I den **utfällingsrutan \<name\>** Redigera principen som visas klickar du på Ta bort princip och sedan **på Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="490b6-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="490b6-351">Du kan inte ta bort standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="490b6-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="490b6-352">Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="490b6-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="490b6-353">Som vi beskrivit tidigare består en policy för skräppost av en nätt phish-princip och en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="490b6-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="490b6-354">I Exchange Online PowerShell visar sig skillnaden mellan nättringsprinciper och nätt phish-regler.</span><span class="sxs-lookup"><span data-stu-id="490b6-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="490b6-355">Du hanterar phish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar nätfingregler med hjälp av **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="490b6-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="490b6-356">I PowerShell skapar du först en nätt phish-princip och sedan skapar du den skyddande phish-regel som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="490b6-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="490b6-357">I PowerShell kan du ändra inställningarna separat i nätt phish-principen och anti-phish-regeln.</span><span class="sxs-lookup"><span data-stu-id="490b6-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="490b6-358">När du tar bort en nätt phish-princip från PowerShell tas inte motsvarande phish-regel bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="490b6-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="490b6-359">Använda PowerShell för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="490b6-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="490b6-360">Att skapa en princip mot nätfiske i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="490b6-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="490b6-361">Skapa en anti-phish-policy.</span><span class="sxs-lookup"><span data-stu-id="490b6-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="490b6-362">Skapa den phish-regel som anger den anti-phish-policy som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="490b6-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="490b6-363">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="490b6-363">**Notes**:</span></span>

- <span data-ttu-id="490b6-364">Du kan skapa en ny, phish-regel och tilldela den en befintlig, oassocierad nätt phish-princip.</span><span class="sxs-lookup"><span data-stu-id="490b6-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="490b6-365">En nätt phish-regel kan inte associeras med mer än en anti-phish-policy.</span><span class="sxs-lookup"><span data-stu-id="490b6-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="490b6-366">Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i Säkerhets- & och efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="490b6-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="490b6-367">Skapa den nya principen som inaktiverad _(aktiverad_ för `$false` cmdleten **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="490b6-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="490b6-368">Ange prioriteten för principen när den skapas _(Priority)_ _\<Number\>_ på **cmdleten New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="490b6-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="490b6-369">En ny, phish-princip som du skapar i PowerShell visas inte i Säkerhets- & och efterlevnadscenter förrän du tilldelar principen till en nätt phish-regel.</span><span class="sxs-lookup"><span data-stu-id="490b6-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="490b6-370">Steg 1: Använda PowerShell för att skapa en anti-phish-princip</span><span class="sxs-lookup"><span data-stu-id="490b6-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="490b6-371">Om du vill skapa en anti-phish-princip använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="490b6-372">I det här exemplet skapas en antifishprincip som heter Research Quarantine med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="490b6-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="490b6-373">Principen är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="490b6-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="490b6-374">Beskrivningen är: Forskningavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="490b6-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="490b6-375">Aktiverar skydd av organisationsdomäner för alla godkända domäner och riktat domänskydd för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="490b6-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="490b6-376">Anger Mai Torto (mfujito@fabrikam.com) som användaren som ska skydda mot personifiering.</span><span class="sxs-lookup"><span data-stu-id="490b6-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="490b6-377">Aktiverar postlådeinformation.</span><span class="sxs-lookup"><span data-stu-id="490b6-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="490b6-378">Aktiverar postlådeinformationsskydd och anger åtgärden för karantän.</span><span class="sxs-lookup"><span data-stu-id="490b6-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="490b6-379">Aktiverar säkerhetstips.</span><span class="sxs-lookup"><span data-stu-id="490b6-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="490b6-380">Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="490b6-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="490b6-381">Steg 2: Använda PowerShell för att skapa en antifishregel</span><span class="sxs-lookup"><span data-stu-id="490b6-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="490b6-382">Om du vill skapa en antifishregel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="490b6-383">I det här exemplet skapas en antifishregel som heter Research Department med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="490b6-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="490b6-384">Regeln är kopplad till den phish-policy som heter Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="490b6-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="490b6-385">Regeln gäller för medlemmar i gruppen Research Department.</span><span class="sxs-lookup"><span data-stu-id="490b6-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="490b6-386">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="490b6-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="490b6-387">Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="490b6-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="490b6-388">Använda PowerShell för att visa nätthetsprinciper</span><span class="sxs-lookup"><span data-stu-id="490b6-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="490b6-389">Använd följande syntax för att visa befintliga principer för nätt phish:</span><span class="sxs-lookup"><span data-stu-id="490b6-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="490b6-390">Det här exemplet returnerar en sammanfattning av alla principer för nätt phish tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="490b6-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="490b6-391">I det här exemplet returneras alla egendomsvärden för den nätt phish-policy som heter Chefer.</span><span class="sxs-lookup"><span data-stu-id="490b6-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="490b6-392">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="490b6-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="490b6-393">Använda PowerShell för att visa nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="490b6-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="490b6-394">Om du vill se befintliga skyddande regler använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="490b6-395">Det här exemplet returnerar en sammanfattning av alla skyddande regler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="490b6-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="490b6-396">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="490b6-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="490b6-397">I det här exemplet returneras alla egenskapsvärden för den phish-regeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="490b6-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="490b6-398">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="490b6-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="490b6-399">Använda PowerShell för att ändra nätthetsprinciper</span><span class="sxs-lookup"><span data-stu-id="490b6-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="490b6-400">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en [anti-phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) i PowerShell som när du skapar principen enligt beskrivningen i steg 1: Använda PowerShell för att skapa ett avsnitt som inte är en phish-policy längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="490b6-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="490b6-401">Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (gäller för alla, alltid Lägsta prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätt phish-princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="490b6-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="490b6-402">Du kan inte byta namn på en nätt **phish-princip (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="490b6-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="490b6-403">När du byter namn på en policy mot nätfiske i Säkerhets- & Efterlevnadscenter byter du bara namn på _nätfiskeregeln._</span><span class="sxs-lookup"><span data-stu-id="490b6-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="490b6-404">Om du vill ändra en anti-phish-princip använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="490b6-405">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="490b6-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="490b6-406">Använda PowerShell för att ändra nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="490b6-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="490b6-407">Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är den aktiverade _parametern_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="490b6-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="490b6-408">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddande regler.</span><span class="sxs-lookup"><span data-stu-id="490b6-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="490b6-409">Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en nätt phish-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="490b6-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="490b6-410">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg [2:](#step-2-use-powershell-to-create-an-anti-phish-rule) Använd PowerShell för att skapa ett avsnitt som inte är phish längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="490b6-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="490b6-411">Om du vill ändra en anti-phish-regel använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="490b6-412">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="490b6-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="490b6-413">Använda PowerShell för att aktivera eller inaktivera phish-regler</span><span class="sxs-lookup"><span data-stu-id="490b6-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="490b6-414">Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen).</span><span class="sxs-lookup"><span data-stu-id="490b6-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="490b6-415">Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="490b6-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="490b6-416">Om du vill aktivera eller inaktivera en nätt phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="490b6-417">I det här exemplet inaktiveras den phish-regeln marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="490b6-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="490b6-418">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="490b6-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="490b6-419">Detaljerad information om syntax och parametrar finns i [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="490b6-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="490b6-420">Använd PowerShell för att ange prioriteten för nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="490b6-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="490b6-421">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="490b6-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="490b6-422">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="490b6-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="490b6-423">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="490b6-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="490b6-424">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="490b6-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="490b6-425">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="490b6-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="490b6-426">Använd följande syntax för att ange prioriteten för en nätt phish-regel i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="490b6-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="490b6-427">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="490b6-427">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="490b6-428">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="490b6-428">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="490b6-429">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="490b6-429">**Notes**:</span></span>

- <span data-ttu-id="490b6-430">Om du vill ange prioriteten för en  ny regel när du skapar den använder du prioritetsparametern i cmdleten **New-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="490b6-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="490b6-431">Standardprincipen för nätt phish har inte en motsvarande antifishregel och har alltid det omoderbara prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="490b6-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="490b6-432">Använda PowerShell för att ta bort nätt phish-principer</span><span class="sxs-lookup"><span data-stu-id="490b6-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="490b6-433">När du använder PowerShell för att ta bort en nätt phish-princip tas inte motsvarande phish-regel bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="490b6-434">Om du vill ta bort en anti-phish-princip i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="490b6-435">I det här exemplet tas den antifishpolicy som heter Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="490b6-436">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="490b6-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="490b6-437">Använda PowerShell för att ta bort nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="490b6-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="490b6-438">När du använder PowerShell för att ta bort en nätt phish-regel tas inte motsvarande phish-princip bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="490b6-439">Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="490b6-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="490b6-440">I det här exemplet tas den phish-regeln som heter Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="490b6-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="490b6-441">Detaljerad information om syntax och parametrar finns [i Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="490b6-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="490b6-442">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="490b6-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="490b6-443">Kontrollera att du har konfigurerat principer för skydd mot nätfiske i Microsoft Defender för Office 365 genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="490b6-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="490b6-444">Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="490b6-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="490b6-445">Kontrollera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="490b6-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="490b6-446">Om du vill visa mer information gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="490b6-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="490b6-447">Välj principen i listan och visa informationen i den utfällade listrutan.</span><span class="sxs-lookup"><span data-stu-id="490b6-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="490b6-448">Klicka **på Standardprincip** och visa informationen i den utfällna menyn.</span><span class="sxs-lookup"><span data-stu-id="490b6-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="490b6-449">I Exchange Online PowerShell ersätter du med namnet på principen eller regeln \<Name\> och kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="490b6-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
