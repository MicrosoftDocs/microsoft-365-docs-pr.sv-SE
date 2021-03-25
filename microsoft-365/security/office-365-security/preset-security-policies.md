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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de tillämpar standard- och striktprincipinställningar i alla skyddsfunktioner i Exchange Online Protection (EOP) och Microsoft Defender för Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7579b2d2a47135ab9628d2ec8990f53c3917514b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207162"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="cdb30-103">Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="cdb30-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cdb30-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cdb30-104">**Applies to**</span></span>
- [<span data-ttu-id="cdb30-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cdb30-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cdb30-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cdb30-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cdb30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdb30-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cdb30-108">Förinställda säkerhetsprinciper tillhandahåller en central plats där användarna kan använda alla rekommenderade principer för skräppost, skadlig programvara och nätfiske på en gång.</span><span class="sxs-lookup"><span data-stu-id="cdb30-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="cdb30-109">Principinställningarna kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="cdb30-109">The policy settings are not configurable.</span></span> <span data-ttu-id="cdb30-110">De ställs i stället in av oss och baseras på våra observationer i datacenter för en balans mellan att hålla skadligt innehåll borta från användare utan att störa deras arbete.</span><span class="sxs-lookup"><span data-stu-id="cdb30-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="cdb30-111">Resten av det här avsnittet beskriver förinställda säkerhetsprinciper och hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="cdb30-111">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="cdb30-112">Vilka förinställda säkerhetsprinciper görs av</span><span class="sxs-lookup"><span data-stu-id="cdb30-112">What preset security policies are made of</span></span>

<span data-ttu-id="cdb30-113">Förinställda säkerhetsprinciper består av följande element:</span><span class="sxs-lookup"><span data-stu-id="cdb30-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="cdb30-114">Profiler</span><span class="sxs-lookup"><span data-stu-id="cdb30-114">Profiles</span></span>
- <span data-ttu-id="cdb30-115">Principer</span><span class="sxs-lookup"><span data-stu-id="cdb30-115">Policies</span></span>
- <span data-ttu-id="cdb30-116">Principinställningar</span><span class="sxs-lookup"><span data-stu-id="cdb30-116">Policy settings</span></span>

<span data-ttu-id="cdb30-117">Prioritetsordningen är dessutom viktig om flera förinställda säkerhetsprinciper och andra principer gäller för samma person.</span><span class="sxs-lookup"><span data-stu-id="cdb30-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="cdb30-118">Profiler i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-118">Profiles in preset security policies</span></span>

<span data-ttu-id="cdb30-119">En profil avgör skyddsnivån.</span><span class="sxs-lookup"><span data-stu-id="cdb30-119">A profile determines the level of protection.</span></span> <span data-ttu-id="cdb30-120">Följande profiler är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="cdb30-120">The following profiles are available:</span></span>

- <span data-ttu-id="cdb30-121">**Standardskydd:** En profil för baslinjeskydd som är lämplig för de flesta användare.</span><span class="sxs-lookup"><span data-stu-id="cdb30-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="cdb30-122">**Strikt skydd:** En mer aggressiva skyddsprofil för valda användare (högvärdesmålen eller prioriterade användare).</span><span class="sxs-lookup"><span data-stu-id="cdb30-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="cdb30-123">Du använder regler med villkor och undantag som avgör vilka profiler som profilerna ska tillämpas på eller inte.</span><span class="sxs-lookup"><span data-stu-id="cdb30-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="cdb30-124">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="cdb30-124">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="cdb30-125">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="cdb30-125">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="cdb30-126">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="cdb30-126">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="cdb30-127">Tillgängliga villkor och undantag är:</span><span class="sxs-lookup"><span data-stu-id="cdb30-127">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="cdb30-128">**Mottagarna är: Postlådor,** e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cdb30-128">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="cdb30-129">**Mottagarna är medlemmar i**: Grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cdb30-129">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="cdb30-130">**Mottagardomänerna är:** Godkända domäner som är konfigurerade i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cdb30-130">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="cdb30-131">Principer i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-131">Policies in preset security policies</span></span>

<span data-ttu-id="cdb30-132">Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdb30-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cdb30-133">Dessa principer skapas när _du_ tilldelar **standardskydds- eller** **strikt skyddsförinställda** säkerhetsprinciper till användarna.</span><span class="sxs-lookup"><span data-stu-id="cdb30-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="cdb30-134">Du kan inte ändra dessa principer.</span><span class="sxs-lookup"><span data-stu-id="cdb30-134">You can't modify these policies.</span></span>

- <span data-ttu-id="cdb30-135">**Principer för Exchange Online Protection (EOP):** Det här omfattar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="cdb30-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="cdb30-136">[Principer för skydd mot skräppost](configure-your-spam-filter-policies.md) med **standardförvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="cdb30-137">[Skydd mot skadlig programvara med](configure-anti-malware-policies.md) standard **förvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="cdb30-138">[EOP-principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings) med standard **förvald** säkerhetsprincip **och strikt förinställd** säkerhetsprincip (förfalskningsinställningar).</span><span class="sxs-lookup"><span data-stu-id="cdb30-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="cdb30-139">**Principer för Microsoft Defender för Office 365:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för tilläggsprenumerationer för Office 365:</span><span class="sxs-lookup"><span data-stu-id="cdb30-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="cdb30-140">Skydd mot nätfiske i Microsoft Defender för Office 365 med namnet **Standardförvald** säkerhetsprincip och **Strikt förinställd** säkerhetsprincip, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="cdb30-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="cdb30-141">Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="cdb30-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="cdb30-142">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="cdb30-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="cdb30-143">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="cdb30-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="cdb30-144">[Principer för säkra länkar](set-up-safe-links-policies.md) **med standard förvald säkerhetsprincip** **och strikt förinställd säkerhetsprincip.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="cdb30-145">[Principer för säkra bifogade](set-up-safe-attachments-policies.md) filer **med standard förvald säkerhetsprincip** **och strikt förinställd säkerhetsprincip.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="cdb30-146">Observera att du kan använda EOP-skydd för olika användare än Microsoft Defender för Office 365-skydd.</span><span class="sxs-lookup"><span data-stu-id="cdb30-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="cdb30-147">Principinställningar i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="cdb30-148">Du kan inte ändra principinställningarna i skyddsprofilerna.</span><span class="sxs-lookup"><span data-stu-id="cdb30-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="cdb30-149">**Standard-** och Strikt-principinställningsvärdena beskrivs i [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="cdb30-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="cdb30-150">Prioritetsordningen för förinställda säkerhetsprinciper och andra principer</span><span class="sxs-lookup"><span data-stu-id="cdb30-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="cdb30-151">När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:</span><span class="sxs-lookup"><span data-stu-id="cdb30-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="cdb30-152">**Strikt skydd förvald** säkerhetsprincip</span><span class="sxs-lookup"><span data-stu-id="cdb30-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="cdb30-153">**Förvald** säkerhetsprincip för standardskydd</span><span class="sxs-lookup"><span data-stu-id="cdb30-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="cdb30-154">Anpassade säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-154">Custom security policies</span></span>
4. <span data-ttu-id="cdb30-155">Standardsäkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-155">Default security policies</span></span>

<span data-ttu-id="cdb30-156">Inställningarna i principen för  strikt skydd åsidosätter med andra ord inställningarna i **standardskyddsprincipen,** som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="cdb30-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="cdb30-157">Tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="cdb30-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cdb30-158">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cdb30-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cdb30-159">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cdb30-159">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cdb30-160">Använd för att gå direkt **till sidan Förinställda** <https://protection.office.com/presetSecurityPolicies> säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="cdb30-160">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="cdb30-161">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cdb30-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cdb30-162">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="cdb30-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cdb30-163">Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cdb30-164">För skrivskyddade åtkomst till förinställda säkerhetsprinciper måste du vara medlem i **rollgruppen Global Reader.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="cdb30-165">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="cdb30-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cdb30-166">**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll  i administrationscentret för Microsoft 365 får användarna de behörigheter och behörigheter som krävs för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cdb30-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cdb30-167">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cdb30-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="cdb30-168">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="cdb30-168">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="cdb30-169">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **Förvalda** \> **säkerhetsprinciper** \> **för hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-169">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="cdb30-170">Under **Standardskydd eller** **Strikt skydd klickar** du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="cdb30-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="cdb30-171">Guiden **Använd standardskydd** **eller Använd strikt skydd** startas.</span><span class="sxs-lookup"><span data-stu-id="cdb30-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="cdb30-172">Om **EOP-skydden gäller för** steg identifierar du de interna mottagare som [EOP-skydd gäller](#policies-in-preset-security-policies) för:</span><span class="sxs-lookup"><span data-stu-id="cdb30-172">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="cdb30-173">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-173">Click **Add a condition**.</span></span> <span data-ttu-id="cdb30-174">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="cdb30-174">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="cdb30-175">**Mottagarna är**</span><span class="sxs-lookup"><span data-stu-id="cdb30-175">**The recipients are**</span></span>
      - <span data-ttu-id="cdb30-176">**Mottagarna är medlemmar i**</span><span class="sxs-lookup"><span data-stu-id="cdb30-176">**The recipients are members of**</span></span>
      - <span data-ttu-id="cdb30-177">**Mottagardomänerna är**</span><span class="sxs-lookup"><span data-stu-id="cdb30-177">**The recipient domains are**</span></span>

      <span data-ttu-id="cdb30-178">Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret.</span><span class="sxs-lookup"><span data-stu-id="cdb30-178">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="cdb30-179">Flera värden med samma villkor använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="cdb30-179">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="cdb30-180">Det villkor som du har markerat visas i ett skuggat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="cdb30-180">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="cdb30-181">I det avsnittet klickar du i **rutan Någon av dessa.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-181">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="cdb30-182">Om du väntar en stund visas en lista så att du kan välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="cdb30-182">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="cdb30-183">Du kan också börja skriva ett värde för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="cdb30-183">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="cdb30-184">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="cdb30-184">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="cdb30-185">Om du vill ta bort ett enskilt värde klickar du **på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.</span><span class="sxs-lookup"><span data-stu-id="cdb30-185">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="cdb30-186">Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="cdb30-186">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="cdb30-187">Om du vill lägga till ytterligare ett villkor **klickar du på** Lägg till ett villkor och väljer något av de återstående villkoren.</span><span class="sxs-lookup"><span data-stu-id="cdb30-187">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="cdb30-188">Olika villkor använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="cdb30-188">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="cdb30-189">Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som behövs eller tills villkoren tar slut.</span><span class="sxs-lookup"><span data-stu-id="cdb30-189">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="cdb30-190">Om du vill lägga till ett undantag klickar du **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-190">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="cdb30-191">I listrutan som visas väljer du ett villkor under **Utom när**.</span><span class="sxs-lookup"><span data-stu-id="cdb30-191">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="cdb30-192">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="cdb30-192">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="cdb30-193">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-193">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cdb30-194">Om din organisation har Microsoft Defender för Office 365 tas du till **de atp-skydd** som gäller för steg för att identifiera de interna mottagare som Microsoft Defender för [Office 365-skydd](#policies-in-preset-security-policies) gäller för.</span><span class="sxs-lookup"><span data-stu-id="cdb30-194">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="cdb30-195">Inställningarna och beteendet är exakt som **EOP-skydden gäller för** steg.</span><span class="sxs-lookup"><span data-stu-id="cdb30-195">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="cdb30-196">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cdb30-197">I steget **Bekräfta** kontrollerar du dina val och klickar sedan på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="cdb30-197">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="cdb30-198">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra tilldelningar av förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="cdb30-198">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="cdb30-199">Stegen för att ändra tilldelningen av  **säkerhetsprincipen Standard** eller Strikt skydd är desamma som när du först tilldelade de förinställda [säkerhetsprinciperna till användare.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="cdb30-199">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="cdb30-200">Om du vill **inaktivera säkerhetsprinciperna** **Standardskydd** eller Strikt skydd, samtidigt som de befintliga villkoren och undantagen bibehålls, drar du reglaget till **Inaktiverad.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-200">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="cdb30-201">Om du vill aktivera principerna drar du reglaget till **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="cdb30-201">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cdb30-202">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="cdb30-202">How do you know these procedures worked?</span></span>

<span data-ttu-id="cdb30-203">För att verifiera att du har  tilldelat en användare **säkerhetsprincipen Standardskydd** eller Strikt skydd använder du en skyddsinställning där standardvärdet skiljer sig från **inställningen för Standardskydd,** vilket skiljer sig från inställningen Strikt **skydd.**</span><span class="sxs-lookup"><span data-stu-id="cdb30-203">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="cdb30-204">För e-post som identifieras som skräppost (med god säkerhet) verifierar du till exempel att meddelandet levereras till mappen Skräppost för användare med **standardskydd** och sätts i karantän för strict **protection** users.</span><span class="sxs-lookup"><span data-stu-id="cdb30-204">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="cdb30-205">För massutskick kontrollerar du att BCL-värdet 6 eller senare levererar meddelandet till mappen Skräppost för användare med **standardskydd** och  BCL-värdet 4 eller högre karantäner meddelandet för strikt skyddsanvändare. [](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="cdb30-205">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>