---
title: Förvalda säkerhetsprinciper
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
description: Administratörer kan lära sig att använda standard-och strikta princip inställningar i skydds funktionerna i Exchange Online Protection (EOP) och Office 365 Avancerat skydd (ATP)
ms.openlocfilehash: a624d48944965c217fb8547e4f09da0ec388e615
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830543"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="dc6e6-103">Förvalda säkerhets principer i EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="dc6e6-103">Preset security policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc6e6-104">Förvalda säkerhets principer är en central plats för att tillämpa alla rekommenderade spam-, malware-och phishing-principer för användare samtidigt.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="dc6e6-105">Princip inställningarna kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-105">The policy settings are not configurable.</span></span> <span data-ttu-id="dc6e6-106">I stället ställs de in av oss och baseras på våra observationer och erfarenheter i data centret för en avvägning mellan att hålla skadligt innehåll från användare utan att störa deras arbete.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="dc6e6-107">Resten av det här avsnittet beskriver förvalda säkerhets principer och hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="dc6e6-108">Vilka säkerhets principer som är gjorda för</span><span class="sxs-lookup"><span data-stu-id="dc6e6-108">What preset security policies are made of</span></span>

<span data-ttu-id="dc6e6-109">Förvalda säkerhets principer består av följande element:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="dc6e6-110">Principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-110">Profiles</span></span>
- <span data-ttu-id="dc6e6-111">Principerna</span><span class="sxs-lookup"><span data-stu-id="dc6e6-111">Policies</span></span>
- <span data-ttu-id="dc6e6-112">Princip inställningar</span><span class="sxs-lookup"><span data-stu-id="dc6e6-112">Policy settings</span></span>

<span data-ttu-id="dc6e6-113">Prioritetsordning är dessutom viktigt om flera förvalda säkerhets principer och andra principer gäller för samma person.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="dc6e6-114">Profiler i förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-114">Profiles in preset security policies</span></span>

<span data-ttu-id="dc6e6-115">En profil bestämmer skydds nivån.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-115">A profile determines the level of protection.</span></span> <span data-ttu-id="dc6e6-116">Följande profiler är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-116">The following profiles are available:</span></span>

- <span data-ttu-id="dc6e6-117">**Standard skydd** : en grundläggande skydds profil som passar de flesta användare.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-117">**Standard protection** : A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="dc6e6-118">**Strikt skydd** : en mer aggressiv skydds profil för utvalda användare (högsta värde mål eller prioriterade användare).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-118">**Strict protection** : A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="dc6e6-119">Du använder regler med villkor och undantag som avgör vem profilen är eller inte är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="dc6e6-120">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="dc6e6-121">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="dc6e6-122">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

<span data-ttu-id="dc6e6-123">De tillgängliga villkoren och undantagen är:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="dc6e6-124">**Mottagarna är** : post lådor, e-postanvändare eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-124">**The recipients are** : Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="dc6e6-125">**Mottagarna är medlemmar i** : grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-125">**The recipients are members of** : Groups in your organization.</span></span>
- <span data-ttu-id="dc6e6-126">**Mottagar domäner är** : godkända domäner som är konfigurerade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-126">**The recipient domains are** : Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="dc6e6-127">Principer i förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-127">Policies in preset security policies</span></span>

<span data-ttu-id="dc6e6-128">Förvalda säkerhets principer Använd motsvarande principer från de olika skydds funktionerna i EOP och Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="dc6e6-129">Dessa principer skapas _efter_ att du har tilldelat **standard** säkerhets principer för förvalda skydd eller **strikta skydd** för användare.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="dc6e6-130">Du kan inte ändra dessa principer.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-130">You can't modify these policies.</span></span>

- <span data-ttu-id="dc6e6-131">**Principer för Exchange Online Protection (EOP)** : det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-131">**Exchange Online Protection (EOP) policies** : This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="dc6e6-132">[Principer för skräp post](configure-your-spam-filter-policies.md) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets policy** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>
  - <span data-ttu-id="dc6e6-133">[Principer mot skadlig program vara](configure-anti-malware-policies.md) med namnet **Standard säkerhets princip** och **strikt förinställd säkerhets policy** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>
  - <span data-ttu-id="dc6e6-134">[EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets princip** (Spoof-inställningar).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="dc6e6-135">**Office 365 principer för avancerat skydd (ATP)** : Detta inkluderar organisationer med Microsoft 365 E5 eller Office 365 ATP-tilläggs abonnemang:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-135">**Office 365 Advanced Threat Protection (ATP) policies** : This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="dc6e6-136">ATP anti-nätfiske-principer som heter **Standard säkerhets princip för Förinställdhet** och **strikt förinställd säkerhets princip** , som omfattar:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy** , which include:</span></span>

    - <span data-ttu-id="dc6e6-137">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="dc6e6-138">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="dc6e6-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="dc6e6-139">Avancerade nät fiske trösklar</span><span class="sxs-lookup"><span data-stu-id="dc6e6-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="dc6e6-140">[Principer för säkra länkar](set-up-atp-safe-links-policies.md) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets policy** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-140">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>

  - <span data-ttu-id="dc6e6-141">[Principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) med **standard** säkerhets princip och **strikt förinställd säkerhets policy** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-141">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>

<span data-ttu-id="dc6e6-142">Observera att du kan använda EOP skydd för olika användare än ATP-skydd.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="dc6e6-143">Princip inställningar i förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="dc6e6-144">Du kan inte ändra princip inställningarna i skydds profilerna.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="dc6e6-145">Värdena för **standard** -och **strict** -princip beskrivs i [rekommenderade inställningar för EOP och Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="dc6e6-146">Prioritetsordning för förvalda säkerhets principer och andra principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="dc6e6-147">När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="dc6e6-148">**Strikt skydd** för förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="dc6e6-149">**Standard** säkerhets princip för förinställd skydd</span><span class="sxs-lookup"><span data-stu-id="dc6e6-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="dc6e6-150">Anpassade säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-150">Custom security policies</span></span>
4. <span data-ttu-id="dc6e6-151">Standard säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-151">Default security policies</span></span>

<span data-ttu-id="dc6e6-152">Med andra ord åsidosätter inställningarna för principen för **strikt skydd** standardinställningarna för **skydds** princip, som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standard principen.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="dc6e6-153">Tilldela användare förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc6e6-154">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="dc6e6-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc6e6-155">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="dc6e6-156">För att gå direkt till sidan för **förvalda säkerhets principer** , Använd <https://protection.office.com/presetSecurityPolicies> .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="dc6e6-157">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="dc6e6-158">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="dc6e6-159">Om du vill konfigurera förvalda säkerhets principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="dc6e6-160">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="dc6e6-161">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="dc6e6-162">Om du vill ha skrivskyddad åtkomst till förvalda säkerhets principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="dc6e6-163">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="dc6e6-164">**Global läsare** i [säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-164">**Global Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="dc6e6-165">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-165">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="dc6e6-166">Använd säkerhets & Compliance Center för att tilldela förvalda säkerhets principer till användare</span><span class="sxs-lookup"><span data-stu-id="dc6e6-166">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="dc6e6-167">Gå till säkerhets principer för principer för **hot Management** policy i säkerhets & efterlevnad \> **Policy** \> **Preset security policies** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies** .</span></span>

2. <span data-ttu-id="dc6e6-168">Under **standard skydd** eller **strikt skydd** klickar du på **Redigera** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-168">Under **Standard protection** or **Strict protection** , click **Edit** .</span></span>

3. <span data-ttu-id="dc6e6-169">Guiden **Använd standard skydd** eller **Använd strikt skydd** startas.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-169">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="dc6e6-170">På **EOP skydd gäller för** steg hur du identifierar de interna mottagarna som [EOP skydd](#policies-in-preset-security-policies) gäller för:</span><span class="sxs-lookup"><span data-stu-id="dc6e6-170">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="dc6e6-171">Klicka på **Lägg till ett villkor** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-171">Click **Add a condition** .</span></span> <span data-ttu-id="dc6e6-172">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :</span><span class="sxs-lookup"><span data-stu-id="dc6e6-172">In the dropdown that appears, select a condition under **Applied if** :</span></span>

      - <span data-ttu-id="dc6e6-173">**Mottagarna**</span><span class="sxs-lookup"><span data-stu-id="dc6e6-173">**The recipients are**</span></span>
      - <span data-ttu-id="dc6e6-174">**Mottagarna är medlemmar i**</span><span class="sxs-lookup"><span data-stu-id="dc6e6-174">**The recipients are members of**</span></span>
      - <span data-ttu-id="dc6e6-175">**Mottagar domänerna**</span><span class="sxs-lookup"><span data-stu-id="dc6e6-175">**The recipient domains are**</span></span>

      <span data-ttu-id="dc6e6-176">Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-176">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="dc6e6-177">Flera värden med samma villkor används eller logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-177">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span>

   2. <span data-ttu-id="dc6e6-178">Det villkor som du valde visas i ett skuggat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-178">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="dc6e6-179">Klicka i **någon av** rutorna i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-179">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="dc6e6-180">Om du väntar ett tag visas en lista så att du kan välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-180">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="dc6e6-181">Eller så kan du börja skriva ett värde för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-181">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="dc6e6-182">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="dc6e6-183">Om du vill ta bort ett enskilt värde klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-183">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="dc6e6-184">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-184">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="dc6e6-185">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer bland de återstående villkoren.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-185">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="dc6e6-186">Olika villkor används och logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-186">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

      <span data-ttu-id="dc6e6-187">Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som behövs eller tills du får slut på villkoren.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-187">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="dc6e6-188">Om du vill lägga till ett undantag klickar du på **Lägg till ett villkor** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-188">To add an exception, click **Add a condition** .</span></span> <span data-ttu-id="dc6e6-189">I den nedrullningsbara List rutan som visas väljer du ett villkor under **utom när** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-189">In the dropdown that appears, select a condition under **Except when** .</span></span> <span data-ttu-id="dc6e6-190">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-190">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="dc6e6-191">När du är klar klickar du på **Nästa** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-191">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="dc6e6-192">Om din organisation har Office 365 ATP kan du **använda säkerhets inställningarna för ATP** för att identifiera de interna mottagare som [Office 365 ATP-skydden](#policies-in-preset-security-policies) gäller för.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-192">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="dc6e6-193">Inställningarna och beteendet är exakt likadant som **EOP skydd gäller för** steg.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-193">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="dc6e6-194">När du är klar klickar du på **Nästa** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-194">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="dc6e6-195">I **bekräftelse** steget verifierar du dina val och klickar sedan på **Bekräfta** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-195">On the **Confirm** step, verify your selections, and then click **Confirm** .</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="dc6e6-196">Använd säkerhets & Compliance Center för att ändra tilldelningarna för förvalda säkerhets principer</span><span class="sxs-lookup"><span data-stu-id="dc6e6-196">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="dc6e6-197">Åtgärderna för att ändra tilldelningen av standard säkerhets principer för **skydd** eller **strikta skydd** är desamma som när du ursprungligen [tilldelade de förvalda säkerhets principerna till användarna](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span><span class="sxs-lookup"><span data-stu-id="dc6e6-197">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="dc6e6-198">Om du vill inaktivera **standard skydds** -eller **strikta** säkerhets principer och samtidigt behålla de befintliga villkoren och undantagen drar du reglaget till **inaktive rad** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-198">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** .</span></span> <span data-ttu-id="dc6e6-199">Aktivera principer genom att dra reglaget till **aktiverat** .</span><span class="sxs-lookup"><span data-stu-id="dc6e6-199">To enable the policies, slide the toggle to **Enabled** .</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="dc6e6-200">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="dc6e6-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="dc6e6-201">Om du vill kontrol lera att du har tilldelat **standard** säkerhets principen för skydd eller **strikt skydd** till en användare använder du en skydds inställning där standardvärdet skiljer sig från standardinställningen för **standard skydd** , som är den **strikta** inställningen för begränsning.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-201">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="dc6e6-202">Till exempel, för e-postmeddelanden som identifieras som skräp post (inte med hög exakthet) kontrollerar du att meddelandet levereras till mappen skräp post för **standard skydds** användare och karantän för **strikta skydds** användare.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-202">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="dc6e6-203">Om du har ett [Mass utskick av e-post](bulk-complaint-level-values.md)kan du kontrol lera att BCL värde 6 eller högre skickar meddelandet till mappen skräp post för **standard skydds** användare, och BCL värde 4 eller högre gör att meddelandet för **strikta skydds** användare.</span><span class="sxs-lookup"><span data-stu-id="dc6e6-203">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
