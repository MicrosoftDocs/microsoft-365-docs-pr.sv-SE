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
description: Administratörer kan läsa om hur standard- och strikt-principinställningarna används i alla skyddsfunktioner i Exchange Online Protection (EOP) och Microsoft Defender för Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e41edb6c2d77a69ee3d4fa28ff86e0e77410caa5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108301"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="70943-103">Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="70943-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="70943-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="70943-104">**Applies to**</span></span>
- [<span data-ttu-id="70943-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="70943-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="70943-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="70943-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="70943-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70943-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="70943-108">Förinställda säkerhetsprinciper tillhandahåller en central plats där användarna kan använda alla rekommenderade principer för skräppost, skadlig programvara och nätfiske på en gång.</span><span class="sxs-lookup"><span data-stu-id="70943-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="70943-109">Principinställningarna kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="70943-109">The policy settings are not configurable.</span></span> <span data-ttu-id="70943-110">De ställs i stället in av oss och baseras på våra observationer i datacenter för en balans mellan att hålla skadligt innehåll borta från användare och undvika onödiga störningar.</span><span class="sxs-lookup"><span data-stu-id="70943-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="70943-111">I resten av den här artikeln beskrivs förinställda säkerhetsprinciper och hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="70943-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="70943-112">Vilka förinställda säkerhetsprinciper görs av</span><span class="sxs-lookup"><span data-stu-id="70943-112">What preset security policies are made of</span></span>

<span data-ttu-id="70943-113">Förinställda säkerhetsprinciper består av följande element:</span><span class="sxs-lookup"><span data-stu-id="70943-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="70943-114">Profiler</span><span class="sxs-lookup"><span data-stu-id="70943-114">Profiles</span></span>
- <span data-ttu-id="70943-115">Principer</span><span class="sxs-lookup"><span data-stu-id="70943-115">Policies</span></span>
- <span data-ttu-id="70943-116">Principinställningar</span><span class="sxs-lookup"><span data-stu-id="70943-116">Policy settings</span></span>

<span data-ttu-id="70943-117">Prioritetsordningen är dessutom viktig om flera förinställda säkerhetsprinciper och andra principer gäller för samma person.</span><span class="sxs-lookup"><span data-stu-id="70943-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="70943-118">Profiler i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-118">Profiles in preset security policies</span></span>

<span data-ttu-id="70943-119">En profil avgör skyddsnivån.</span><span class="sxs-lookup"><span data-stu-id="70943-119">A profile determines the level of protection.</span></span> <span data-ttu-id="70943-120">Följande profiler är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="70943-120">The following profiles are available:</span></span>

- <span data-ttu-id="70943-121">**Standardskydd:** En profil för baslinjeskydd som är lämplig för de flesta användare.</span><span class="sxs-lookup"><span data-stu-id="70943-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="70943-122">**Strikt skydd:** En mer aggressiva skyddsprofil för valda användare (högvärdesmålen eller prioriterade användare).</span><span class="sxs-lookup"><span data-stu-id="70943-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="70943-123">Du använder regler med villkor och undantag som avgör vilka profiler som profilerna ska tillämpas på eller inte.</span><span class="sxs-lookup"><span data-stu-id="70943-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="70943-124">Tillgängliga villkor och undantag är:</span><span class="sxs-lookup"><span data-stu-id="70943-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="70943-125">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="70943-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="70943-126">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="70943-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="70943-127">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="70943-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="70943-128">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="70943-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="70943-129">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="70943-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="70943-130">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="70943-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="70943-131">Principer i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-131">Policies in preset security policies</span></span>

<span data-ttu-id="70943-132">Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="70943-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="70943-133">Dessa principer skapas när _du_ tilldelar **standardskydds- eller** **strikt skyddsförinställda** säkerhetsprinciper till användarna.</span><span class="sxs-lookup"><span data-stu-id="70943-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="70943-134">Du kan inte ändra dessa principer.</span><span class="sxs-lookup"><span data-stu-id="70943-134">You can't modify these policies.</span></span>

- <span data-ttu-id="70943-135">**Exchange Online Protection (EOP):** Det här omfattar Microsoft 365 organisationer med Exchange Online e-postlådor och fristående EOP-organisationer utan Exchange Online postlådor:</span><span class="sxs-lookup"><span data-stu-id="70943-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="70943-136">[Principer för skydd mot skräppost](configure-your-spam-filter-policies.md) med **standardförvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="70943-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="70943-137">[Skydd mot skadlig programvara med](configure-anti-malware-policies.md) standard **förvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="70943-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="70943-138">[EOP-principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings) med standard **förvald** säkerhetsprincip **och strikt förinställd** säkerhetsprincip (förfalskningsinställningar).</span><span class="sxs-lookup"><span data-stu-id="70943-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="70943-139">**Microsoft Defender Office 365 principer:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för Office 365 tilläggsprenumerationer:</span><span class="sxs-lookup"><span data-stu-id="70943-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="70943-140">Principer för skydd mot nätfiske i Microsoft Defender Office 365 som **heter Standardförvald** säkerhetsprincip **och Strikt förinställd** säkerhetsprincip, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="70943-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="70943-141">Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="70943-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="70943-142">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="70943-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="70943-143">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="70943-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="70943-144">[Valv som heter](set-up-safe-links-policies.md) **Standardförvald säkerhetsprincip** **och Strikt förinställd säkerhetsprincip.**</span><span class="sxs-lookup"><span data-stu-id="70943-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="70943-145">[Valv principer för bifogade filer](set-up-safe-attachments-policies.md) med standard **förvald** **säkerhetsprincip och strikt förinställd säkerhetsprincip.**</span><span class="sxs-lookup"><span data-stu-id="70943-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="70943-146">Observera att du kan använda EOP-skydd för olika användare än Microsoft Defender för Office 365 skydd.</span><span class="sxs-lookup"><span data-stu-id="70943-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="70943-147">Principinställningar i förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="70943-148">Du kan inte ändra principinställningarna i skyddsprofilerna.</span><span class="sxs-lookup"><span data-stu-id="70943-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="70943-149">Standard- och **Strikt-principinställningsvärdena** beskrivs [i Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="70943-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="70943-150">Prioritetsordningen för förinställda säkerhetsprinciper och andra principer</span><span class="sxs-lookup"><span data-stu-id="70943-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="70943-151">När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:</span><span class="sxs-lookup"><span data-stu-id="70943-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="70943-152">**Strikt skydd förvald** säkerhetsprincip</span><span class="sxs-lookup"><span data-stu-id="70943-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="70943-153">**Förvald** säkerhetsprincip för standardskydd</span><span class="sxs-lookup"><span data-stu-id="70943-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="70943-154">Anpassade säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-154">Custom security policies</span></span>
4. <span data-ttu-id="70943-155">Standardsäkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-155">Default security policies</span></span>

<span data-ttu-id="70943-156">Inställningarna i principen för  strikt skydd åsidosätter med andra ord inställningarna i **standardskyddsprincipen,** som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="70943-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="70943-157">Tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="70943-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="70943-158">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="70943-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="70943-159">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="70943-159">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="70943-160">Använd för att gå direkt **till sidan Förinställda** <https://security.microsoft.com/presetSecurityPolicies> säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="70943-160">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="70943-161">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="70943-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="70943-162">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="70943-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="70943-163">Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="70943-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="70943-164">För skrivskyddade åtkomst till förinställda säkerhetsprinciper måste du vara medlem i **rollgruppen Global Reader.**</span><span class="sxs-lookup"><span data-stu-id="70943-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="70943-165">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="70943-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="70943-166">**Obs!** Om du lägger till användare Azure Active Directory motsvarande roll i Administrationscenter för Microsoft 365  får användarna nödvändiga behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70943-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="70943-167">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="70943-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="70943-168">Använd Microsoft 365 Defender-portalen för att tilldela förinställda säkerhetsprinciper till användare</span><span class="sxs-lookup"><span data-stu-id="70943-168">Use the Microsoft 365 Defender portal to assign preset security policies to users</span></span>

1. <span data-ttu-id="70943-169">I Microsoft 365 Defender-portalen går du till avsnittet **Förinställda** säkerhetsprinciper & e-& principer för säkerhetsprinciper för regler och \>  \>  \>  \> **hot.**</span><span class="sxs-lookup"><span data-stu-id="70943-169">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="70943-170">Under **Standardskydd eller** **Strikt skydd klickar** du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="70943-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="70943-171">Guiden **Använd standardskydd** **eller Använd strikt skydd** startas.</span><span class="sxs-lookup"><span data-stu-id="70943-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="70943-172">På sidan **EOP-skydd gäller för** identifierar du de interna mottagare som [EOP-skydd gäller](#policies-in-preset-security-policies) för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="70943-172">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="70943-173">**Användare**</span><span class="sxs-lookup"><span data-stu-id="70943-173">**Users**</span></span>
   - <span data-ttu-id="70943-174">**Grupper**</span><span class="sxs-lookup"><span data-stu-id="70943-174">**Groups**</span></span>
   - <span data-ttu-id="70943-175">**Domäner**</span><span class="sxs-lookup"><span data-stu-id="70943-175">**Domains**</span></span>

   <span data-ttu-id="70943-176">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="70943-176">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="70943-177">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="70943-177">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="70943-178">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="70943-178">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="70943-180">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="70943-180">next to the value.</span></span>

   <span data-ttu-id="70943-181">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="70943-181">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="70943-182">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="70943-182">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="70943-183">**Uteslut dessa användare, grupper** och domäner: Om du vill lägga till undantag för de interna mottagare som principen gäller för (mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="70943-183">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="70943-184">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="70943-184">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="70943-185">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="70943-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="70943-186">I Microsoft Defender för Office 365-organisationer tas du till sidan med Defender för **Office 365-skydd** för att identifiera de interna mottagare som [Microsoft Defender för Office 365-skydd](#policies-in-preset-security-policies) gäller för (mottagarvillkor).</span><span class="sxs-lookup"><span data-stu-id="70943-186">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="70943-187">Inställningarna och beteendet är exakt som **EOP-skydden gäller för** sidan.</span><span class="sxs-lookup"><span data-stu-id="70943-187">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="70943-188">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="70943-188">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="70943-189">På sidan **Granska och bekräfta ändringarna** verifierar du dina val och klickar sedan på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="70943-189">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="70943-190">Använd Microsoft 365 Defender-portalen för att ändra tilldelningar av förinställda säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="70943-190">Use the Microsoft 365 Defender portal to modify the assignments of preset security policies</span></span>

<span data-ttu-id="70943-191">Stegen för att ändra tilldelningen av  **säkerhetsprincipen Standard** eller Strikt skydd är desamma som när du först tilldelade de förinställda [säkerhetsprinciperna till användare.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="70943-191">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="70943-192">Om du vill  **inaktivera säkerhetsprinciperna Standardskydd** eller Strikt skydd samtidigt som de befintliga villkoren och undantagen bibehålls drar du reglaget **till Inaktiverad** ![ ](../../media/scc-toggle-off.png) av.</span><span class="sxs-lookup"><span data-stu-id="70943-192">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="70943-193">Du aktiverar principerna genom att dra reglaget till **Aktiverad** ![ växlingsknapp På ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="70943-193">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="70943-194">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="70943-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="70943-195">För att verifiera att du har  tilldelat en användare **säkerhetsprincipen Standardskydd** eller Strikt skydd använder du en skyddsinställning där standardvärdet skiljer sig från **inställningen för Standardskydd,** vilket skiljer sig från inställningen Strikt **skydd.**</span><span class="sxs-lookup"><span data-stu-id="70943-195">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="70943-196">För e-post som identifieras som skräppost (med god säkerhet) verifierar du till exempel att meddelandet levereras till mappen Skräppost för användare med **standardskydd** och sätts i karantän för strict **protection** users.</span><span class="sxs-lookup"><span data-stu-id="70943-196">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="70943-197">För massutskick kontrollerar du att BCL-värdet 6 eller senare levererar meddelandet till mappen Skräppost för användare med **standardskydd** och  BCL-värdet 4 eller högre karantäner meddelandet för strikt skyddsanvändare. [](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="70943-197">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
