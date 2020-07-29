---
title: Förvalda säkerhetsprinciper
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
description: Administratörer kan lära sig hur du använder standard- och strikta principinställningar för skyddsfunktionerna i Exchange Online Protection (EOP) och Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: dd730639aa15709bafd600d4cc2706befb143cd4
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430405"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="9cabd-103">Förinställda säkerhetsprinciper i EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="9cabd-103">Preset security policies in EOP and Office 365 ATP</span></span>

<span data-ttu-id="9cabd-104">Förinställda säkerhetsprinciper ger en centraliserad plats för att tillämpa alla rekommenderade principer för skräppost, skadlig kod och nätfiske på användare samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9cabd-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="9cabd-105">Principinställningarna kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="9cabd-105">The policy settings are not configurable.</span></span> <span data-ttu-id="9cabd-106">Istället är de som av oss och bygger på våra observationer och erfarenheter i datacenter för en balans mellan att hålla skadligt innehåll borta från användare utan att störa deras arbete.</span><span class="sxs-lookup"><span data-stu-id="9cabd-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="9cabd-107">I resten av det här avsnittet beskrivs förinställda säkerhetsprinciper och hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="9cabd-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="9cabd-108">Vilka förinställda säkerhetsprinciper som görs av</span><span class="sxs-lookup"><span data-stu-id="9cabd-108">What preset security policies are made of</span></span>

<span data-ttu-id="9cabd-109">Förinställda säkerhetsprinciper består av följande element:</span><span class="sxs-lookup"><span data-stu-id="9cabd-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="9cabd-110">Profiler</span><span class="sxs-lookup"><span data-stu-id="9cabd-110">Profiles</span></span>
- <span data-ttu-id="9cabd-111">Politik</span><span class="sxs-lookup"><span data-stu-id="9cabd-111">Policies</span></span>
- <span data-ttu-id="9cabd-112">Principinställningar</span><span class="sxs-lookup"><span data-stu-id="9cabd-112">Policy settings</span></span>

<span data-ttu-id="9cabd-113">Dessutom är prioritetsordningen viktig om flera förinställda säkerhetsprinciper och andra principer gäller för samma person.</span><span class="sxs-lookup"><span data-stu-id="9cabd-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="9cabd-114">Profiler i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-114">Profiles in preset security policies</span></span>

<span data-ttu-id="9cabd-115">En profil bestämmer skyddsnivån.</span><span class="sxs-lookup"><span data-stu-id="9cabd-115">A profile determines the level of protection.</span></span> <span data-ttu-id="9cabd-116">Följande profiler är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="9cabd-116">The following profiles are available:</span></span>

- <span data-ttu-id="9cabd-117">**Standardskydd**: En baslinjeskyddsprofil som är lämplig för de flesta användare.</span><span class="sxs-lookup"><span data-stu-id="9cabd-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="9cabd-118">**Strikt skydd**: En mer aggressiv skyddsprofil för utvalda användare (högt värdemål eller prioriterade användare).</span><span class="sxs-lookup"><span data-stu-id="9cabd-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="9cabd-119">Du använder regler med villkor och undantag som avgör vilka profilerna är eller inte tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="9cabd-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="9cabd-120">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="9cabd-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9cabd-121">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9cabd-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9cabd-122">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9cabd-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="9cabd-123">De tillgängliga villkoren och undantagen är:</span><span class="sxs-lookup"><span data-stu-id="9cabd-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="9cabd-124">**Mottagarna är**: Postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9cabd-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="9cabd-125">**Mottagarna är medlemmar**i : Grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9cabd-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="9cabd-126">**Mottagarnatrdomäner är**: Godkända domäner som är konfigurerade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9cabd-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="9cabd-127">Principer i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-127">Policies in preset security policies</span></span>

<span data-ttu-id="9cabd-128">Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="9cabd-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="9cabd-129">Dessa principer skapas _när_ du har tilldelat **standardskydd** eller förinställda säkerhetsprinciper **för strikt skydd** till användare.</span><span class="sxs-lookup"><span data-stu-id="9cabd-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="9cabd-130">Du kan inte ändra dessa principer.</span><span class="sxs-lookup"><span data-stu-id="9cabd-130">You can't modify these policies.</span></span>

- <span data-ttu-id="9cabd-131">**EOP-principer (Exchange Online Protection):** Detta inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="9cabd-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="9cabd-132">[Anti-spam-principer](configure-your-spam-filter-policies.md) med namnet **Standard förinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="9cabd-133">[Principer mot skadlig kod](configure-anti-malware-policies.md) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="9cabd-134">[EOP:s principer för phishing-phishing](set-up-anti-phishing-policies.md#spoof-settings) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip** (falska inställningar).</span><span class="sxs-lookup"><span data-stu-id="9cabd-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="9cabd-135">**Office 365 Advanced Threat Protection (ATP)-principer**: Detta inkluderar organisationer med Microsoft 365 E5- eller Office 365 ATP-tilläggsprenumerationer:</span><span class="sxs-lookup"><span data-stu-id="9cabd-135">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="9cabd-136">ATP-principer för nätfiske med namnet **Standard förinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="9cabd-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="9cabd-137">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP:s policyer för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9cabd-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="9cabd-138">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="9cabd-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="9cabd-139">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="9cabd-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="9cabd-140">[Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-140">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="9cabd-141">[Principer för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-141">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="9cabd-142">Observera att du kan använda EOP-skydd för andra användare än ATP-skydd.</span><span class="sxs-lookup"><span data-stu-id="9cabd-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="9cabd-143">Principinställningar i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="9cabd-144">Du kan inte ändra principinställningarna i skyddsprofilerna.</span><span class="sxs-lookup"><span data-stu-id="9cabd-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="9cabd-145">Principinställningsvärdena **Standard** och **Strikt** beskrivs i [Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="9cabd-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="9cabd-146">Prioritetsordning för förinställda säkerhetsprinciper och andra principer</span><span class="sxs-lookup"><span data-stu-id="9cabd-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="9cabd-147">När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:</span><span class="sxs-lookup"><span data-stu-id="9cabd-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="9cabd-148">**Strikt säkerhetsprincip** för skydd</span><span class="sxs-lookup"><span data-stu-id="9cabd-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="9cabd-149">Förinställd säkerhetsprincip för **standardskydd**</span><span class="sxs-lookup"><span data-stu-id="9cabd-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="9cabd-150">Anpassade säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-150">Custom security policies</span></span>
4. <span data-ttu-id="9cabd-151">Standardsäkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-151">Default security policies</span></span>

<span data-ttu-id="9cabd-152">Med andra ord åsidosätter inställningarna i principen **Strikt skydd** inställningarna för **standardskyddsprincipen,** som åsidosätter inställningarna från en anpassad princip, som åsidosätter inställningarna från standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="9cabd-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="9cabd-153">Tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="9cabd-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9cabd-154">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="9cabd-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9cabd-155">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9cabd-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9cabd-156">Om du vill gå direkt till sidan **Förinställda säkerhetsprinciper** använder du <https://protection.office.com/presetSecurityPolicies> .</span><span class="sxs-lookup"><span data-stu-id="9cabd-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="9cabd-157">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9cabd-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9cabd-158">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="9cabd-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="9cabd-159">Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="9cabd-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9cabd-160">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9cabd-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9cabd-161">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="9cabd-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="9cabd-162">För skrivskyddad åtkomst till förinställda säkerhetsprinciper måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="9cabd-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9cabd-163">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9cabd-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9cabd-164">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="9cabd-164">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="9cabd-165">Använda Säkerhets- & Compliance Center för att tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="9cabd-165">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="9cabd-166">Gå till **Threat management** \> **Policy** \> **säkerhetsprinciper för principförinställda säkerhetsprinciper i säkerhetsprinciper**för & säkerhetsprinciper för & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="9cabd-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="9cabd-167">Klicka på **Redigera**under **Standardskydd** eller **Strikt skydd**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-167">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="9cabd-168">Guiden **Använd standardskydd** eller **Använd strikt skydd** startar.</span><span class="sxs-lookup"><span data-stu-id="9cabd-168">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="9cabd-169">När det gäller **EOP-skydd för** steg, identifiera de interna mottagare som [EOP-skydd](#policies-in-preset-security-policies) gäller för</span><span class="sxs-lookup"><span data-stu-id="9cabd-169">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="9cabd-170">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-170">Click **Add a condition**.</span></span> <span data-ttu-id="9cabd-171">I listrutan som visas väljer du ett villkor under **Tillämpad om:**</span><span class="sxs-lookup"><span data-stu-id="9cabd-171">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="9cabd-172">**Mottagarna är**</span><span class="sxs-lookup"><span data-stu-id="9cabd-172">**The recipients are**</span></span>
      - <span data-ttu-id="9cabd-173">**Mottagarna är medlemmar i**</span><span class="sxs-lookup"><span data-stu-id="9cabd-173">**The recipients are members of**</span></span>
      - <span data-ttu-id="9cabd-174">**De mottagande domänerna är**</span><span class="sxs-lookup"><span data-stu-id="9cabd-174">**The recipient domains are**</span></span>

      <span data-ttu-id="9cabd-175">Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret.</span><span class="sxs-lookup"><span data-stu-id="9cabd-175">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="9cabd-176">Flera värden med samma villkor använder ELLER-logik (till exempel _\<recipient1\>_ _\<recipient2\>_ eller ).</span><span class="sxs-lookup"><span data-stu-id="9cabd-176">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="9cabd-177">Villkoret som du valde visas i ett skuggat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="9cabd-177">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="9cabd-178">Klicka i rutan **Någon av dessa** i det avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9cabd-178">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="9cabd-179">Om du väntar ett ögonblick visas en lista så att du kan välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="9cabd-179">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="9cabd-180">Du kan också börja skriva ett värde för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="9cabd-180">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="9cabd-181">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="9cabd-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="9cabd-182">Om du vill ta bort ett enskilt värde klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="9cabd-182">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="9cabd-183">Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="9cabd-183">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="9cabd-184">Om du vill lägga till ett annat villkor klickar du på **Lägg till ett villkor** och väljer från de återstående villkoren.</span><span class="sxs-lookup"><span data-stu-id="9cabd-184">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="9cabd-185">Olika villkor använder OCH logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="9cabd-185">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="9cabd-186">Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som det behövs eller tills villkoren har tagit.</span><span class="sxs-lookup"><span data-stu-id="9cabd-186">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="9cabd-187">Om du vill lägga till ett undantag klickar du på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-187">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="9cabd-188">I listrutan som visas väljer du ett villkor under **Förutom när**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-188">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="9cabd-189">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="9cabd-189">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9cabd-190">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9cabd-191">Om din organisation har Office 365 ATP tas du till **ATP-skydden för** att gå för att identifiera de interna mottagare som [Office 365 ATP-skydd](#policies-in-preset-security-policies) gäller för.</span><span class="sxs-lookup"><span data-stu-id="9cabd-191">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="9cabd-192">Inställningarna och beteendet är precis som **eop-skydden gäller för** steg.</span><span class="sxs-lookup"><span data-stu-id="9cabd-192">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="9cabd-193">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9cabd-194">Kontrollera dina val i steget **Bekräfta** och klicka sedan på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-194">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="9cabd-195">Använd Säkerhets- & Compliance Center för att ändra tilldelningarna av förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="9cabd-195">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="9cabd-196">Stegen för att ändra tilldelningen av **säkerhetsprincipen Standardskydd** eller **Strikt skydd** är desamma som när du först [tilldelade användarna de förinställda säkerhetsprinciperna](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span><span class="sxs-lookup"><span data-stu-id="9cabd-196">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="9cabd-197">Om du vill inaktivera säkerhetsprinciperna **för standardskydd** eller **strikt skydd** samtidigt som de befintliga villkoren och undantagen bevaras, drar du växlingsknappen till **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-197">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="9cabd-198">Om du vill aktivera principerna drar du växlingsknappen till **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="9cabd-198">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9cabd-199">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="9cabd-199">How do you know these procedures worked?</span></span>

<span data-ttu-id="9cabd-200">Om du vill kontrollera att du har tilldelat en användare **standardskydds-** eller strikt skyddssäkerhetsprincip använder du en skyddsinställning där standardvärdet skiljer sig från **standardskyddsinställningen,** vilket är annorlunda än inställningen **Strikt skydd.** **Strict protection**</span><span class="sxs-lookup"><span data-stu-id="9cabd-200">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="9cabd-201">Till exempel, för e-post som upptäcks som skräppost (inte hög förtroende spam) kontrollera att meddelandet levereras till skräppostmappen för **standardskydd** användare, och karantän för **strikt skydd** användare.</span><span class="sxs-lookup"><span data-stu-id="9cabd-201">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="9cabd-202">Eller, för [massmeddelande](bulk-complaint-level-values.md), kontrollera att BCL-värdet 6 eller högre levererar meddelandet till mappen Skräppost för **standardskyddsanvändare** och BCL-värdet 4 eller högre i karantän meddelandet för **användare av strikt skydd.**</span><span class="sxs-lookup"><span data-stu-id="9cabd-202">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
