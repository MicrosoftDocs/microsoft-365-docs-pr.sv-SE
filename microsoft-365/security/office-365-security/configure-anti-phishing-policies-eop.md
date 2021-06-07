---
title: Konfigurera principer för skydd mot nätfiske i EOP
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
description: Administratörer kan lära sig att skapa, ändra och ta bort de principer mot nätfiske som är tillgängliga i Exchange Online Protection-organisationer (EOP) med eller utan Exchange Online postlådor.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c329edc517476cfb184bfa4b70c2f2c9542b6e33
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789069"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="99c51-103">Konfigurera principer för skydd mot nätfiske i EOP</span><span class="sxs-lookup"><span data-stu-id="99c51-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="99c51-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="99c51-104">**Applies to**</span></span>
- [<span data-ttu-id="99c51-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="99c51-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="99c51-106">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor finns det en standardprincip för skydd mot nätfiske som innehåller ett begränsat antal skydd mot förfalskningsfunktioner som är aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="99c51-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="99c51-107">Mer information finns i [Principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="99c51-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="99c51-108">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="99c51-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="99c51-109">För mer detaljerad information kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99c51-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="99c51-110">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="99c51-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="99c51-111">Organisationer med Exchange Online-postlådor kan konfigurera principer för skydd mot nätfiske Microsoft 365 säkerhetscenter eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c51-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="99c51-112">Fristående EOP-organisationer kan endast använda säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="99c51-112">Standalone EOP organizations can only use the security center.</span></span>

<span data-ttu-id="99c51-113">Information om hur du skapar och ändrar mer avancerade principer för nätfiske som finns i Microsoft Defender för Office 365 finns i Konfigurera principer för nätfiske i [Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="99c51-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="99c51-114">De grundläggande elementen i en princip mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="99c51-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="99c51-115">**Anti-phish policy:** Anger nätfiskeskydden som aktiverar eller inaktiverar samt de alternativ som används.</span><span class="sxs-lookup"><span data-stu-id="99c51-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="99c51-116">**Antifrasregeln**: Anger prioritet och mottagarfilter (som principen gäller för) för en nättfnig policy.</span><span class="sxs-lookup"><span data-stu-id="99c51-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="99c51-117">Skillnaden mellan dessa två element är inte uppenbart när du hanterar principer mot nätfiske i säkerhetscentret:</span><span class="sxs-lookup"><span data-stu-id="99c51-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="99c51-118">När du skapar en policy mot nätfiske skapar du i själva verket en nätfiskeregel och den tillhörande nätfiskeprincipen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="99c51-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="99c51-119">När du ändrar en princip mot nätfiske ändras nätfiskeregeln i inställningarna för namn, prioritet, aktiverad eller inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="99c51-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="99c51-120">Alla andra inställningar ändrar den associerade nätfn-principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="99c51-121">När du tar bort en nätfiskeprincip tas nätfiskeregeln och den tillhörande nätfiskeprincipen bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="99c51-122">I Exchange Online PowerShell hanterar du principen och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="99c51-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="99c51-123">Mer information finns i avsnittet Använda [Exchange Online PowerShell för att konfigurera principer mot nätfiske längre](#use-exchange-online-powershell-to-configure-anti-phishing-policies) fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99c51-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="99c51-124">Alla organisationer har en inbyggd policy för skydd mot nätfiske med namnet Office365-skyddfval som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="99c51-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="99c51-125">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon antifrasregel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="99c51-126">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="99c51-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="99c51-127">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="99c51-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="99c51-128">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="99c51-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="99c51-129">För att öka effektiviteten i skydd mot nätfiske kan du skapa anpassade principer mot nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="99c51-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99c51-130">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="99c51-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99c51-131">Öppna Microsoft 365 Säkerhetscenter på <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="99c51-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="99c51-132">Om du vill gå direkt **till sidan Mot nätfiske** använder du <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="99c51-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="99c51-133">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="99c51-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="99c51-134">Du kan inte hantera principer för nätfiske i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c51-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="99c51-135">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="99c51-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="99c51-136">Om du vill lägga till, ändra och ta bort principer  för skydd mot nätfiske måste du vara medlem i rollgrupperna Organisationshantering **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="99c51-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="99c51-137">För skrivskyddade åtkomst till principer mot nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="99c51-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="99c51-138">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="99c51-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="99c51-139">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="99c51-139">**Notes**:</span></span>

  - <span data-ttu-id="99c51-140">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99c51-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="99c51-141">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="99c51-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="99c51-142">Rollgruppen **Organisationshantering,** skrivskyddade [i Exchange Online,](/Exchange/permissions-exo/permissions-exo#role-groups) ger även skrivskyddsåtkomst till <sup>\*</sup> funktionen.</span><span class="sxs-lookup"><span data-stu-id="99c51-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="99c51-143">Vi rekommenderar inställningar för principer mot nätfiske i standardinställningarna för nätfiskeprincip i [EOP.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="99c51-143">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="99c51-144">Det kan ta upp till 30 minuter för den uppdaterade principen att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="99c51-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="99c51-145">Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordning och [prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="99c51-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="99c51-146">Använda säkerhetscentret för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-146">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="99c51-147">Om du skapar en anpassad policy för nätfiske i säkerhetscentret skapas samtidigt den antifiska regeln och den tillhörande nätfiskeprincipen med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="99c51-147">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="99c51-148">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-148">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-149">På sidan **Mot nätfiske** klickar du på ![ Skapa ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="99c51-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="99c51-150">Principguiden öppnas.</span><span class="sxs-lookup"><span data-stu-id="99c51-150">The policy wizard opens.</span></span> <span data-ttu-id="99c51-151">Konfigurera **följande inställningar på** sidan Principnamn:</span><span class="sxs-lookup"><span data-stu-id="99c51-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="99c51-152">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="99c51-153">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="99c51-154">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="99c51-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="99c51-155">På sidan **Användare, grupper och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="99c51-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="99c51-156">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99c51-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="99c51-157">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99c51-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="99c51-158">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99c51-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="99c51-159">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="99c51-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="99c51-160">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="99c51-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="99c51-161">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="99c51-161">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="99c51-163">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="99c51-163">next to the value.</span></span>

   <span data-ttu-id="99c51-164">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="99c51-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="99c51-165">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="99c51-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="99c51-166">Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor.</span><span class="sxs-lookup"><span data-stu-id="99c51-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="99c51-167">Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.</span><span class="sxs-lookup"><span data-stu-id="99c51-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="99c51-168">**Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="99c51-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="99c51-169">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="99c51-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="99c51-170">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="99c51-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99c51-171">På sidan **för &** skydd som visas använder  du kryssrutan Aktivera förfalskningsinformation för att aktivera eller inaktivera förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="99c51-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="99c51-172">Standardvärdet är på (markerat) och vi rekommenderar att du låter det vara på.</span><span class="sxs-lookup"><span data-stu-id="99c51-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="99c51-173">Du konfigurerar åtgärden för blockerade förfalskningsmeddelanden på nästa sida.</span><span class="sxs-lookup"><span data-stu-id="99c51-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="99c51-174">Om du vill inaktivera förfalskningsinformation avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="99c51-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="99c51-175">Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="99c51-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="99c51-176">Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="99c51-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="99c51-177">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="99c51-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="99c51-178">På sidan **Åtgärder** som visas kan du konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="99c51-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="99c51-179">**Om meddelandet identifieras som förfalskning: Den** här inställningen är bara tillgänglig om du har markerat Aktivera **förfalskningsinformation** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="99c51-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="99c51-180">Välj någon av följande åtgärder i listrutan för meddelanden från blockerade förfalskningsavsändare:</span><span class="sxs-lookup"><span data-stu-id="99c51-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="99c51-181">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="99c51-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="99c51-182">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="99c51-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="99c51-183">**Säkerhetstips & indikatorer:** Den här inställningen är bara tillgänglig om du **har markerat Aktivera förfalskningsinformation** på föregående sida:</span><span class="sxs-lookup"><span data-stu-id="99c51-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="99c51-184">Visa (?) för oautenterade avsändare för förfalskning: Lägger till ett frågetecken på **avsändarens** foto i rutan Från i Outlook om  meddelandet inte klarar SPF- eller DKIM-kontroller och meddelandet inte klarar DMARC eller sammansatt [autentisering.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="99c51-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="99c51-185">**Visa** via-taggen: Lägger till en via-tagg (chris@contoso.com via fabrikam.com) till från-adressen om den skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.**</span><span class="sxs-lookup"><span data-stu-id="99c51-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="99c51-186">För närvarande är **tagginställningen Visa via** inte tillgänglig i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="99c51-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="99c51-187">Om du inte har tagginställningen **Visa "via"** styrs  frågetecknet och via-taggen av Show **(?) för oauthenticerade** avsändare för förfalskning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="99c51-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="99c51-188">Markera kryssrutan om du vill aktivera en inställning.</span><span class="sxs-lookup"><span data-stu-id="99c51-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="99c51-189">Om du vill inaktivera den avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="99c51-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="99c51-190">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="99c51-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="99c51-191">Granska inställningarna på sidan **Granska** som visas.</span><span class="sxs-lookup"><span data-stu-id="99c51-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="99c51-192">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="99c51-192">You can select **Edit** in each section to modify the settings within the section.</span></span>

   <span data-ttu-id="99c51-193">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="99c51-193">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="99c51-194">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="99c51-194">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="99c51-195">Använd säkerhetscentret för att visa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-195">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="99c51-196">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-196">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-197">På **sidan Mot nätfiske** visas följande egenskaper i listan över principer mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="99c51-197">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="99c51-198">**Namn**</span><span class="sxs-lookup"><span data-stu-id="99c51-198">**Name**</span></span>
   - <span data-ttu-id="99c51-199">**Status**</span><span class="sxs-lookup"><span data-stu-id="99c51-199">**Status**</span></span>
   - <span data-ttu-id="99c51-200">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="99c51-200">**Priority**</span></span>
   - <span data-ttu-id="99c51-201">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="99c51-201">**Last modified**</span></span>

3. <span data-ttu-id="99c51-202">När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="99c51-202">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="99c51-203">Använda säkerhetscentret för att ändra principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-203">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="99c51-204">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-204">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-205">På sidan **Mot nätfiske** väljer du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="99c51-205">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="99c51-206">I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="99c51-206">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="99c51-207">Mer information om inställningarna finns i avsnittet Använda [säkerhetscentret för](#use-the-security-center-to-create-anti-phishing-policies) att skapa principer mot nätfiske längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99c51-207">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="99c51-208">Standardprincipen för skydd mot nätfiske är avsnittet **Användare,** grupper och domäner inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-208">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="99c51-209">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-209">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="99c51-210">Aktivera eller inaktivera anpassade principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-210">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="99c51-211">Du kan inte inaktivera standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="99c51-211">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="99c51-212">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-212">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-213">På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="99c51-213">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="99c51-214">Högst upp i den utfällda menyn principinformation ser du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="99c51-214">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="99c51-215">**Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .</span><span class="sxs-lookup"><span data-stu-id="99c51-215">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="99c51-216">**Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="99c51-216">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="99c51-217">I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="99c51-217">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="99c51-218">Klicka **Stäng** i den utfällda menyn principinformation.</span><span class="sxs-lookup"><span data-stu-id="99c51-218">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="99c51-219">Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="99c51-219">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="99c51-220">Ange prioritet för anpassade principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-220">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="99c51-221">Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="99c51-221">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="99c51-222">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="99c51-222">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="99c51-223">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="99c51-223">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="99c51-224">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Säkerhetscenter).</span><span class="sxs-lookup"><span data-stu-id="99c51-224">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="99c51-225">Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="99c51-225">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="99c51-226">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="99c51-226">**Notes**:</span></span>

- <span data-ttu-id="99c51-227">I säkerhetscentret kan du bara ändra prioriteten för nätfiskeprincipen när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="99c51-227">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="99c51-228">I PowerShell kan du åsidosätta standardprioritet när du skapar antifrasregeln (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="99c51-228">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="99c51-229">Principer för skydd mot nätfiske bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="99c51-229">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="99c51-230">Standardprincipen för skydd mot nätfiske har **prioritetsvärdet Lägsta** och du kan inte ändra den.</span><span class="sxs-lookup"><span data-stu-id="99c51-230">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="99c51-231">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-231">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-232">På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="99c51-232">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="99c51-233">Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:</span><span class="sxs-lookup"><span data-stu-id="99c51-233">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="99c51-234">Principen mot nätfiske med **prioritetsvärdet 0** har endast alternativet **Minska prioritet** tillgängligt. </span><span class="sxs-lookup"><span data-stu-id="99c51-234">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="99c51-235">Principen mot nätfiske med lägst **prioritetsvärde** (till exempel **3**) har endast alternativet **Öka** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="99c51-235">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="99c51-236">Om du har tre eller fler principer för skydd mot nätfiske  finns det både alternativ för öka prioritet och minska prioritet mellan de högsta och lägsta  prioritetsvärdena.</span><span class="sxs-lookup"><span data-stu-id="99c51-236">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="99c51-237">Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.</span><span class="sxs-lookup"><span data-stu-id="99c51-237">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="99c51-238">Klicka **Stäng** i den utfällda menyn principinformation när du är klar.</span><span class="sxs-lookup"><span data-stu-id="99c51-238">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="99c51-239">Använda säkerhetscentret för att ta bort anpassade principer för nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-239">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="99c51-240">När du använder säkerhetscentret för att ta bort en anpassad policy mot nätfiske tas både nätfiskeregeln och motsvarande nätfiskeprincip bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-240">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="99c51-241">Du kan inte ta bort standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="99c51-241">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="99c51-242">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-242">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="99c51-243">Välj en anpassad princip i listan genom att klicka på namnet på principen.</span><span class="sxs-lookup"><span data-stu-id="99c51-243">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="99c51-244">Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="99c51-244">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="99c51-245">I bekräftelsedialogrutan som visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="99c51-245">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="99c51-246">Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-246">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="99c51-247">Som tidigare beskrivits består en nätfiskeprincip av en nätfiskeprincip och en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="99c51-247">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="99c51-248">I Exchange Online PowerShell visar sig skillnaden mellan anti-phish-policyer och anti-phish-regler.</span><span class="sxs-lookup"><span data-stu-id="99c51-248">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="99c51-249">Du hanterar antifish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-phish-regler med hjälp av cmdletarna **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="99c51-249">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="99c51-250">I PowerShell skapar du först den nätfiska principen och sedan skapar du den skyddande phish-regeln som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="99c51-250">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="99c51-251">I PowerShell ändrar du inställningarna separat i antifish-principen och antifish-regeln.</span><span class="sxs-lookup"><span data-stu-id="99c51-251">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="99c51-252">När du tar bort en anti-phish-policy från PowerShell tas inte motsvarande anti phish-regel bort automatiskt, och vice versa.</span><span class="sxs-lookup"><span data-stu-id="99c51-252">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="99c51-253">Följande PowerShell-procedurer är inte tillgängliga i fristående EOP-organisationer som använder Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c51-253">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="99c51-254">Använda PowerShell för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="99c51-254">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="99c51-255">Det krävs två steg för att skapa en princip mot nätfiske i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="99c51-255">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="99c51-256">Skapa den anfish-policy som du sedan skapar.</span><span class="sxs-lookup"><span data-stu-id="99c51-256">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="99c51-257">Skapa den anti phish-regel som anger den antifishpolicy som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="99c51-257">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="99c51-258">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="99c51-258">**Notes**:</span></span>

- <span data-ttu-id="99c51-259">Du kan skapa en ny anti-phish-regel och tilldela en befintlig, oassocierad antifishprincip till den.</span><span class="sxs-lookup"><span data-stu-id="99c51-259">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="99c51-260">An anti-phish rule can't be associated with more than one anti-phish policy.</span><span class="sxs-lookup"><span data-stu-id="99c51-260">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="99c51-261">Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i säkerhetscentret förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="99c51-261">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>

  - <span data-ttu-id="99c51-262">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="99c51-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="99c51-263">Ange prioritet för principen vid skapandet (_Prioritet_ _\<Number\>_ ) på **cmdleten New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="99c51-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="99c51-264">En ny anti-phish-policy som du skapar i PowerShell visas inte i säkerhetscentret förrän du tilldelar principen till en antifishregel.</span><span class="sxs-lookup"><span data-stu-id="99c51-264">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="99c51-265">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="99c51-265">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="99c51-266">Använd följande syntax för att skapa en antifishpolicy:</span><span class="sxs-lookup"><span data-stu-id="99c51-266">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="99c51-267">I det här exemplet skapas en antifishprincip som heter Forskningsin karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="99c51-267">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="99c51-268">Beskrivningen är: Forskningavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="99c51-268">The description is: Research department policy.</span></span>
- <span data-ttu-id="99c51-269">Ändrar standardåtgärden för förfalskning till karantän.</span><span class="sxs-lookup"><span data-stu-id="99c51-269">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="99c51-270">Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="99c51-270">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="99c51-271">Steg 2: Använd PowerShell för att skapa en antifishregel</span><span class="sxs-lookup"><span data-stu-id="99c51-271">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="99c51-272">Använd följande syntax för att skapa en antifishregel:</span><span class="sxs-lookup"><span data-stu-id="99c51-272">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="99c51-273">I det här exemplet skapas en antifishregel som heter Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="99c51-273">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="99c51-274">Regeln är kopplad till den nättfiska principen som heter Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="99c51-274">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="99c51-275">Regeln gäller för medlemmar i gruppen Research Department.</span><span class="sxs-lookup"><span data-stu-id="99c51-275">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="99c51-276">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="99c51-276">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="99c51-277">Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="99c51-277">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="99c51-278">Använda PowerShell för att se nätträcksprinciper</span><span class="sxs-lookup"><span data-stu-id="99c51-278">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="99c51-279">Om du vill se befintliga skyddsprinciper använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="99c51-279">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="99c51-280">Det här exemplet returnerar en sammanfattning av alla antifishpolicys tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="99c51-280">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="99c51-281">Det här exemplet returnerar alla egenskapsvärden för den nättfiska policyn cheferna.</span><span class="sxs-lookup"><span data-stu-id="99c51-281">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="99c51-282">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="99c51-282">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="99c51-283">Använda PowerShell för att se nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="99c51-283">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="99c51-284">Använd följande syntax för att visa befintliga skydd mot phish-regler:</span><span class="sxs-lookup"><span data-stu-id="99c51-284">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="99c51-285">Det här exemplet returnerar en sammanfattning av alla nättringsregler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="99c51-285">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="99c51-286">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="99c51-286">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="99c51-287">I det här exemplet returneras alla egenskapsvärden för den nättfiska regeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="99c51-287">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="99c51-288">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="99c51-288">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="99c51-289">Använda PowerShell för att ändra skydd mot nättfingor</span><span class="sxs-lookup"><span data-stu-id="99c51-289">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="99c51-290">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar en princip som beskrivs i Steg 1: Använda PowerShell för att skapa en [anti-phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99c51-290">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="99c51-291">Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (används för alla, alltid lägst prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätfnig princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c51-291">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="99c51-292">Du kan inte byta namn på en nätt **phish-policy (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="99c51-292">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="99c51-293">När du byter namn på en policy mot nätfiske i säkerhetscentret byter du bara namn på _nätfiskeregeln._</span><span class="sxs-lookup"><span data-stu-id="99c51-293">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="99c51-294">Använd följande syntax för att ändra en nätt phish-policy:</span><span class="sxs-lookup"><span data-stu-id="99c51-294">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="99c51-295">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="99c51-295">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="99c51-296">Använda PowerShell för att ändra skydd mot phish-regler</span><span class="sxs-lookup"><span data-stu-id="99c51-296">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="99c51-297">Den enda inställningen som inte är tillgänglig när du ändrar en antifishregel i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="99c51-297">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="99c51-298">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddsregler.</span><span class="sxs-lookup"><span data-stu-id="99c51-298">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="99c51-299">Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-an-anti-phish-rule) Använd PowerShell för att skapa en nätfetregel längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99c51-299">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="99c51-300">Använd följande syntax för att ändra en antifishregel:</span><span class="sxs-lookup"><span data-stu-id="99c51-300">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="99c51-301">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="99c51-301">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="99c51-302">Använda PowerShell för att aktivera eller inaktivera nätthetsregler</span><span class="sxs-lookup"><span data-stu-id="99c51-302">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="99c51-303">Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen).</span><span class="sxs-lookup"><span data-stu-id="99c51-303">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="99c51-304">Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="99c51-304">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="99c51-305">Om du vill aktivera eller inaktivera en nätträcksregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="99c51-305">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="99c51-306">I det här exemplet inaktiveras den phish-regeln Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="99c51-306">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="99c51-307">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="99c51-307">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="99c51-308">Detaljerad information om syntax och parametrar finns [i Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="99c51-308">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="99c51-309">Använd PowerShell för att ange prioriteten för nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="99c51-309">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="99c51-310">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="99c51-310">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="99c51-311">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="99c51-311">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="99c51-312">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="99c51-312">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="99c51-313">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="99c51-313">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="99c51-314">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="99c51-314">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="99c51-315">Om du vill ange prioriteten för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="99c51-315">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="99c51-316">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="99c51-316">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="99c51-317">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="99c51-317">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="99c51-318">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="99c51-318">**Notes**:</span></span>

- <span data-ttu-id="99c51-319">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="99c51-319">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="99c51-320">Den förvalda antifish-principen har inte en motsvarande antifiska regel och har alltid det oföränderliga prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="99c51-320">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="99c51-321">Använda PowerShell för att ta bort nättfällprinciper</span><span class="sxs-lookup"><span data-stu-id="99c51-321">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="99c51-322">När du använder PowerShell för att ta bort en anti-phish-policy tas motsvarande anti phish-regel inte bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-322">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="99c51-323">Om du vill ta bort en anti-phish-policy i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="99c51-323">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="99c51-324">I det här exemplet tas den nättfiska policyn Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-324">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="99c51-325">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="99c51-325">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="99c51-326">Använda PowerShell för att ta bort nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="99c51-326">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="99c51-327">När du använder PowerShell för att ta bort en anti-phish-regel tas motsvarande anti-phish-policy inte bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-327">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="99c51-328">Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="99c51-328">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="99c51-329">I det här exemplet tas den antifiska regeln Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="99c51-329">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="99c51-330">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="99c51-330">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="99c51-331">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="99c51-331">How do you know these procedures worked?</span></span>

<span data-ttu-id="99c51-332">Verifiera att du har konfigurerat principer för skydd mot nätfiske i EOP genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="99c51-332">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="99c51-333">I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**</span><span class="sxs-lookup"><span data-stu-id="99c51-333">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="99c51-334">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="99c51-334">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="99c51-335">Om du vill visa mer information väljer du principen i listan genom att klicka på namnet och visa informationen i den utfäll vy som visas.</span><span class="sxs-lookup"><span data-stu-id="99c51-335">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="99c51-336">I Exchange Online PowerShell ersätter du med namnet på principen \<Name\> eller regeln, kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="99c51-336">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
