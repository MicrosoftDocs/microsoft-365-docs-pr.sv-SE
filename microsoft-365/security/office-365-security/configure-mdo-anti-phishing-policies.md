---
title: Konfigurera principer mot nätfiske i Microsoft Defender för Office 365
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
description: Administratörer kan lära sig att skapa, ändra och ta bort avancerade principer mot nätfiske som är tillgängliga i organisationer med Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbf90f52127e96e08f1c176a23d5f5ab1d6d86c4
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054545"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e62e8-103">Konfigurera principer mot nätfiske i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="e62e8-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e62e8-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e62e8-104">**Applies to**</span></span>
- [<span data-ttu-id="e62e8-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e62e8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e62e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e62e8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e62e8-107">Skydd mot nätfiske [i Microsoft Defender för Office 365](defender-for-office-365.md) kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra typer av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="e62e8-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="e62e8-108">Mer information om skillnaderna mellan principer för skydd mot nätfiske i Exchange Online Protection (EOP) och principer för skydd mot nätfiske i Microsoft Defender för Office 365 finns i Skydd mot [nätfiske.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e62e8-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="e62e8-109">Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e62e8-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="e62e8-110">För mer detaljerad information kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="e62e8-111">Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="e62e8-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="e62e8-112">Du kan konfigurera principer mot nätfiske i Defender för Office 365 i Microsoft 365 Defender portalen eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e62e8-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="e62e8-113">Information om hur du konfigurerar de mer begränsade i principer för skydd mot nätfiske som är tillgängliga i Exchange Online Protection (det vill säga organisationer som saknar Defender för Office 365) finns i Konfigurera principer för skydd mot nätfiske [i EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e62e8-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="e62e8-114">De grundläggande elementen i en princip mot nätfiske är:</span><span class="sxs-lookup"><span data-stu-id="e62e8-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="e62e8-115">**Anti-phish policy:** Anger nätfiskeskydden som aktiverar eller inaktiverar samt de alternativ som används.</span><span class="sxs-lookup"><span data-stu-id="e62e8-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="e62e8-116">**Antifrasregeln**: Anger prioritet och mottagarfilter (som principen gäller för) för en nättfnig policy.</span><span class="sxs-lookup"><span data-stu-id="e62e8-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="e62e8-117">Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer mot nätfiske i Microsoft 365 Defender portalen:</span><span class="sxs-lookup"><span data-stu-id="e62e8-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="e62e8-118">När du skapar en princip skapar du faktiskt en antifishregel och den tillhörande antifishprincipen samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="e62e8-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e62e8-119">När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter den antifish-regeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="e62e8-120">Alla andra inställningar ändrar den associerade nätfn-principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="e62e8-121">När du tar bort en princip tas den nättfiska regeln och den tillhörande antifiska policyn bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="e62e8-122">I Exchange Online PowerShell hanterar du principen och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="e62e8-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e62e8-123">Mer information finns i avsnittet Använda [Exchange Online PowerShell för att konfigurera principer mot nätfiske längre](#use-exchange-online-powershell-to-configure-anti-phishing-policies) fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="e62e8-124">Alla Defender för Office 365-organisationer har en inbyggd policy mot nätfiske med namnet Office365-skyddstrecksstandard som har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="e62e8-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="e62e8-125">Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon antifrasregel (mottagarfilter) kopplad till principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="e62e8-126">Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist).</span><span class="sxs-lookup"><span data-stu-id="e62e8-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="e62e8-127">Alla anpassade policyer som du skapar har alltid högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="e62e8-128">Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.</span><span class="sxs-lookup"><span data-stu-id="e62e8-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="e62e8-129">Om du vill öka effektiviteten i skydd mot nätfiske i Defender för Office 365 kan du skapa anpassade principer för skydd mot nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="e62e8-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e62e8-130">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="e62e8-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e62e8-131">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="e62e8-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="e62e8-132">Om du vill gå direkt **till sidan Mot nätfiske** använder du <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="e62e8-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="e62e8-133">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e62e8-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e62e8-134">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="e62e8-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e62e8-135">Om du vill lägga till, ändra och ta bort principer  för skydd mot nätfiske måste du vara medlem i rollgrupperna Organisationshantering **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e62e8-136">För skrivskyddade åtkomst till principer mot nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e62e8-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="e62e8-137">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e62e8-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e62e8-138">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="e62e8-138">**Notes**:</span></span>

  - <span data-ttu-id="e62e8-139">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e62e8-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e62e8-140">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e62e8-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e62e8-141">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e62e8-142">Vi rekommenderar inställningar för principer mot nätfiske i Defender för Office 365 finns i Princip mot nätfiske i [Defender för Office 365 inställningar.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e62e8-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="e62e8-143">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e62e8-144">Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordning och [prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="e62e8-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="e62e8-145">Använd Microsoft 365 Defender för att skapa principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="e62e8-146">Om du skapar en egen policy mot nätfiske i Microsoft 365 Defender-portalen skapas samtidigt den antifiska regeln och den tillhörande nätfiskeprincipen med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="e62e8-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e62e8-147">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-148">På sidan **Mot nätfiske** klickar du på ![ Skapa ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="e62e8-149">Principguiden öppnas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-149">The policy wizard opens.</span></span> <span data-ttu-id="e62e8-150">Konfigurera **följande inställningar på** sidan Principnamn:</span><span class="sxs-lookup"><span data-stu-id="e62e8-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="e62e8-151">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="e62e8-152">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e62e8-153">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e62e8-154">På sidan **Användare, grupper och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="e62e8-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="e62e8-155">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e62e8-156">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="e62e8-157">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="e62e8-158">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="e62e8-159">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="e62e8-160">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="e62e8-160">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e62e8-162">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-162">next to the value.</span></span>

   <span data-ttu-id="e62e8-163">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="e62e8-164">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="e62e8-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="e62e8-165">Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor.</span><span class="sxs-lookup"><span data-stu-id="e62e8-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e62e8-166">Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.</span><span class="sxs-lookup"><span data-stu-id="e62e8-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="e62e8-167">**Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="e62e8-168">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="e62e8-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e62e8-169">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e62e8-170">Konfigurera följande **inställningar & skyddssidan** som visas på tröskelvärdet för nätfiske:</span><span class="sxs-lookup"><span data-stu-id="e62e8-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e62e8-171">**Tröskelvärde för nätfiske:** Använd skjutreglaget för att välja något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e62e8-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="e62e8-172">**1 – Standard** (det här är standardvärdet.)</span><span class="sxs-lookup"><span data-stu-id="e62e8-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="e62e8-173">**2 – Aggressivt**</span><span class="sxs-lookup"><span data-stu-id="e62e8-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="e62e8-174">**3 – Mer aggressiva**</span><span class="sxs-lookup"><span data-stu-id="e62e8-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="e62e8-175">**4 – Mest aggressiva**</span><span class="sxs-lookup"><span data-stu-id="e62e8-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="e62e8-176">Mer information finns i Avancerade [tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e62e8-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="e62e8-177">**Personifiering:** De här inställningarna är ett villkor för principen som identifierar specifika avsändare som ska leta efter (individuellt eller per domän) i från-adressen till inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e62e8-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="e62e8-178">Mer information finns i Inställningar [för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e62e8-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="e62e8-179">I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser).</span><span class="sxs-lookup"><span data-stu-id="e62e8-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="e62e8-180">Du kan inte ange samma skyddade användare i flera principer.</span><span class="sxs-lookup"><span data-stu-id="e62e8-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="e62e8-181">Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post.</span><span class="sxs-lookup"><span data-stu-id="e62e8-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="e62e8-182">Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.</span><span class="sxs-lookup"><span data-stu-id="e62e8-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="e62e8-183">**Aktivera att användare skyddar:** Standardvärdet är inaktiverat (inte markerat).</span><span class="sxs-lookup"><span data-stu-id="e62e8-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="e62e8-184">Om du vill aktivera den markerar du kryssrutan och klickar sedan på länken **Hantera (nn)** avsändare som visas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="e62e8-185">I den **utfällandefällningen Hantera avsändare** för personifieringsskydd som visas gör du så här:</span><span class="sxs-lookup"><span data-stu-id="e62e8-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="e62e8-186">**Interna avsändare: Klicka** på Lägg ![ till intern ikon Välj ](../../media/m365-cc-sc-add-internal-icon.png) **intern**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="e62e8-187">I den **utfällfältet Lägg** till interna avsändare som visas klickar du i rutan och väljer en intern användare i listan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="e62e8-188">Du kan filtrera listan genom att skriva in användaren och sedan välja användaren i resultatet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="e62e8-189">Du kan använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn och så vidare), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="e62e8-190">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e62e8-191">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="e62e8-191">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e62e8-193">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-193">next to the value.</span></span>

         <span data-ttu-id="e62e8-194">När du är klar klickar du på Lägg **till**</span><span class="sxs-lookup"><span data-stu-id="e62e8-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="e62e8-195">**Externa avsändare: Klicka** på Lägg ![ till extern ikon Välj ](../../media/m365-cc-sc-create-icon.png) **extern**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="e62e8-196">I den **utfällna** menyn Lägg till externa  avsändare som visas anger du  ett visningsnamn i rutan Lägg till ett namn och en e-postadress i rutan Lägg till en **e-postadress.** Klicka sedan på Lägg till .</span><span class="sxs-lookup"><span data-stu-id="e62e8-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="e62e8-197">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e62e8-198">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="e62e8-198">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e62e8-200">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-200">next to the value.</span></span>

         <span data-ttu-id="e62e8-201">När du är klar klickar du på Lägg **till**</span><span class="sxs-lookup"><span data-stu-id="e62e8-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="e62e8-202">Tillbaka på den **utfällande listrutan** Hantera avsändare för personifiering kan du ta bort poster genom att välja en eller flera poster i listan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="e62e8-203">Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="e62e8-204">När du har markerat minst en post visas ikonen Ta bort markerade användare Ta bort markerade användare, som du kan använda för att ![ ta bort de markerade ](../../media/m365-cc-sc-remove-selected-users-icon.png)  posterna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="e62e8-205">Klicka på **Klar** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="e62e8-206">**Aktivera domäner att skydda:** Standardvärdet är av (inte markerat).</span><span class="sxs-lookup"><span data-stu-id="e62e8-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="e62e8-207">Om du vill aktivera den markerar du kryssrutan och konfigurerar sedan en eller båda av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e62e8-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="e62e8-208">**Inkludera de domäner som jag** äger : Om du vill aktivera den här inställningen markerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="e62e8-209">Om du vill visa de domäner som du äger klickar du **på Visa mina domäner**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="e62e8-210">**Ta med egna** domäner: Aktivera den här inställningen genom att markera kryssrutan och sedan klicka på länken **Hantera (nn)** egna domäner som visas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="e62e8-211">I den **utfällande menyn Hantera egna domäner** för personifieringsskydd klickar du på ikonen Lägg till domäner Lägg till ![ ](../../media/m365-cc-sc-create-icon.png) **domäner.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="e62e8-212">I den **utfällliga** menyn Lägg  till egna domäner som visas klickar du i rutan Domän, anger ett värde och trycker på Retur eller väljer det värde som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="e62e8-213">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e62e8-214">Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="e62e8-215">När du är klar klickar du på Lägg **till domäner**</span><span class="sxs-lookup"><span data-stu-id="e62e8-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="e62e8-216">Du kan ha högst 50 domäner i alla principer mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e62e8-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="e62e8-217">På den **utfällande sidan** Hantera egna domäner för personifiering kan du ta bort poster genom att välja en eller flera poster i listan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="e62e8-218">Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="e62e8-219">När du har valt minst en post visas ikonen Ta bort domäner Ta bort, som du kan använda för ![ att ta bort de markerade ](../../media/m365-cc-sc-delete-icon.png)  posterna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="e62e8-220">**Lägga till betrodda** avsändare och domäner: : Ange undantag för personifieringsskydd för principen genom att klicka på Hantera **(nn)** betrodda avsändare och domäner.</span><span class="sxs-lookup"><span data-stu-id="e62e8-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="e62e8-221">I den **utfällande menyn Hantera egna domäner** för personifieringsskydd konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e62e8-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="e62e8-222">**Avsändare:** Kontrollera att fliken **Avsändare** är markerad och klicka på ![ ikonen Lägg till ](../../media/m365-cc-sc-create-icon.png) avsändare.</span><span class="sxs-lookup"><span data-stu-id="e62e8-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="e62e8-223">I den **utfällfältet Lägg till** betrodda avsändare som visas anger du en e-postadress i rutan och klickar sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="e62e8-224">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e62e8-225">Om du vill ta bort en befintlig post klickar ![ du på Ikonen Ta bort för ](../../media/m365-cc-sc-close-icon.png) posten.</span><span class="sxs-lookup"><span data-stu-id="e62e8-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="e62e8-226">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="e62e8-227">**Domäner:** Välj fliken **Domän och** klicka på ikonen Lägg ![ till ](../../media/m365-cc-sc-create-icon.png) domäner.</span><span class="sxs-lookup"><span data-stu-id="e62e8-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="e62e8-228">I den **utfällingsrutan** Lägg  till betrodda domäner som visas klickar du i rutan Domän, anger ett värde och trycker på Retur eller väljer det värde som visas under rutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="e62e8-229">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="e62e8-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e62e8-230">Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="e62e8-231">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="e62e8-232">På den **utfällbar** fliken Hantera egna domäner för personifiering  kan du ta bort poster från flikarna Avsändare och Domän genom att välja en eller flera poster i listan. </span><span class="sxs-lookup"><span data-stu-id="e62e8-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="e62e8-233">Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="e62e8-234">När du har markerat minst en post visas **ikonen Ta** bort, som du kan använda för att ta bort de markerade posterna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="e62e8-235">Klicka på **Klar** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="e62e8-236">**Aktivera** postlådeintelligens: Standardvärdet är på (markerat) och vi rekommenderar att du låter det vara på.</span><span class="sxs-lookup"><span data-stu-id="e62e8-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="e62e8-237">Om du vill inaktivera den avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="e62e8-238">**Aktivera intelligence-baserat personifieringsskydd: Den** här inställningen är bara tillgänglig om **Aktivera postlådeintelligens** är på (markerad).</span><span class="sxs-lookup"><span data-stu-id="e62e8-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="e62e8-239">Med den här inställningen kan postlådeinformation vidta åtgärder på meddelanden som identifieras som personifieringsförsök.</span><span class="sxs-lookup"><span data-stu-id="e62e8-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="e62e8-240">Du anger vilken åtgärd som ska vidtas i **inställningen Om postlådeinformation identifierar en imiterad** användare på nästa sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="e62e8-241">Vi rekommenderar att du aktiverar den här inställningen genom att markera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="e62e8-242">Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="e62e8-243">**Förfalskning**: I det här avsnittet använder du kryssrutan Aktivera **förfalskningsinformation** för att aktivera eller inaktivera förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="e62e8-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="e62e8-244">Standardvärdet är på (markerat) och vi rekommenderar att du låter det vara på.</span><span class="sxs-lookup"><span data-stu-id="e62e8-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="e62e8-245">Du anger vilken åtgärd som ska vidtas på meddelanden från blockerade förfalskningsavsändare i inställningen Om meddelande identifieras som **förfalskning** på nästa sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="e62e8-246">Om du vill inaktivera förfalskningsinformation avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="e62e8-247">Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället.</span><span class="sxs-lookup"><span data-stu-id="e62e8-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e62e8-248">Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="e62e8-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="e62e8-249">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e62e8-250">På sidan **Åtgärder** som visas kan du konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e62e8-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e62e8-251">**Meddelandeåtgärder:** Konfigurera följande åtgärder i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="e62e8-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="e62e8-252">**Om meddelandet identifieras som en imiterad** användare: Den här inställningen är bara tillgänglig om du har valt Aktivera användare att **skydda** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="e62e8-253">Välj någon av följande åtgärder i listrutan för meddelanden där avsändaren är en av de skyddade användare som du angav på föregående sida:</span><span class="sxs-lookup"><span data-stu-id="e62e8-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="e62e8-254">**Använd inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="e62e8-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="e62e8-255">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="e62e8-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="e62e8-256">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="e62e8-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="e62e8-257">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="e62e8-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="e62e8-258">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="e62e8-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="e62e8-259">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="e62e8-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="e62e8-260">**Om meddelandet identifieras som en** imiterad domän: Den här inställningen är bara tillgänglig om du har markerat Aktivera domäner att **skydda** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="e62e8-261">Välj någon av följande åtgärder i listrutan för meddelanden där avsändarens e-postadress finns i någon av de skyddade domäner som du angav på föregående sida:</span><span class="sxs-lookup"><span data-stu-id="e62e8-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="e62e8-262">**Använd inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="e62e8-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="e62e8-263">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="e62e8-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="e62e8-264">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="e62e8-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="e62e8-265">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="e62e8-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="e62e8-266">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="e62e8-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="e62e8-267">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="e62e8-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="e62e8-268">**Om postlådeintelligen identifierar** en imiterad användare : Den här inställningen är bara tillgänglig om du har markerat Aktivera intelligens för **personifieringsskydd** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="e62e8-269">Välj någon av följande åtgärder i listrutan för meddelanden som identifierats som personifieringsförsök av postlådeinformation:</span><span class="sxs-lookup"><span data-stu-id="e62e8-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="e62e8-270">**Använd inte någon åtgärd**</span><span class="sxs-lookup"><span data-stu-id="e62e8-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="e62e8-271">**Omdirigera meddelandet till andra e-postadresser**</span><span class="sxs-lookup"><span data-stu-id="e62e8-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="e62e8-272">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="e62e8-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="e62e8-273">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="e62e8-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="e62e8-274">**Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**</span><span class="sxs-lookup"><span data-stu-id="e62e8-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="e62e8-275">**Ta bort meddelandet innan det levereras**</span><span class="sxs-lookup"><span data-stu-id="e62e8-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="e62e8-276">**Om meddelandet identifieras som förfalskning: Den** här inställningen är bara tillgänglig om du har markerat Aktivera **förfalskningsinformation** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="e62e8-277">Välj någon av följande åtgärder i listrutan för meddelanden från blockerade förfalskningsavsändare:</span><span class="sxs-lookup"><span data-stu-id="e62e8-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="e62e8-278">**Flytta meddelandet till mottagarnas skräppostmappar**</span><span class="sxs-lookup"><span data-stu-id="e62e8-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="e62e8-279">**Sätt meddelandet i karantän**</span><span class="sxs-lookup"><span data-stu-id="e62e8-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="e62e8-280">**Säkerhetstips för &**: Konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e62e8-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="e62e8-281">Visa första säkerhetstips **:** Den här säkerhetstips ersätter behovet av att skapa e-postflödesregler (kallas även transportregler) som lägger till rubriken **X-MS-Exchange-EnableFirstContactSafetyTip** med värdet **Enable** to messages.</span><span class="sxs-lookup"><span data-stu-id="e62e8-281">**Show first contact safety tip**: This safety tip replaces the need to create mail flow rules (also known as transport rules) that add the header named **X-MS-Exchange-EnableFirstContactSafetyTip** with the value **Enable** to messages.</span></span>
     - <span data-ttu-id="e62e8-282">**Visa funktionen för användarpersonifiering säkerhetstips:** Den här inställningen är bara tillgänglig om du har markerat Aktivera användare **att skydda** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="e62e8-283">**Visa domänpersonifiering säkerhetstips:** Den här inställningen är bara tillgänglig om du har markerat Aktivera **domäner att skydda** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="e62e8-284">**Visa ovanliga tecken för användarpersonifiering säkerhetstips** Den här inställningen är bara tillgänglig om du **har markerat Aktivera användare för att** skydda eller Aktivera domäner att **skydda** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="e62e8-285">**Visa (?) för oauthenticerade** avsändare för förfalskning: Den här inställningen är bara tillgänglig om du har markerat Aktivera **förfalskningsinformation** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="e62e8-286">Lägger till ett frågetecken på avsändarens foto i rutan Från i Outlook om meddelandet inte  klarar SPF eller DKIM kontrollerar och meddelandet inte klarar DMARC eller sammansatt [autentisering.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="e62e8-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="e62e8-287">**Visa via-taggen:** Den här inställningen är bara tillgänglig om du **har markerat Aktivera förfalskningsinformation** på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="e62e8-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="e62e8-288">Lägger till en via-tagg (chris@contoso.com via fabrikam.com) till från-adressen om den skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="e62e8-289">Standardvärdet är på (markerat).</span><span class="sxs-lookup"><span data-stu-id="e62e8-289">The default value is on (selected).</span></span> <span data-ttu-id="e62e8-290">Om du vill inaktivera den avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="e62e8-291">Om du inte har tagginställningen **Visa "via"**  styrs frågetecknet och via-taggen av Show **(?) för oauthenticerade** avsändare för förfalskning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="e62e8-292">Markera kryssrutan om du vill aktivera en inställning.</span><span class="sxs-lookup"><span data-stu-id="e62e8-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="e62e8-293">Om du vill inaktivera den avmarkerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="e62e8-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="e62e8-294">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="e62e8-295">Granska inställningarna på sidan **Granska** som visas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="e62e8-296">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e62e8-297">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="e62e8-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="e62e8-298">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="e62e8-299">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="e62e8-300">Använd Microsoft 365 Defender för att se principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="e62e8-301">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-302">På **sidan Mot nätfiske** visas följande egenskaper i listan över principer mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="e62e8-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="e62e8-303">**Namn**</span><span class="sxs-lookup"><span data-stu-id="e62e8-303">**Name**</span></span>
   - <span data-ttu-id="e62e8-304">**Status**</span><span class="sxs-lookup"><span data-stu-id="e62e8-304">**Status**</span></span>
   - <span data-ttu-id="e62e8-305">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="e62e8-305">**Priority**</span></span>
   - <span data-ttu-id="e62e8-306">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="e62e8-306">**Last modified**</span></span>

3. <span data-ttu-id="e62e8-307">När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="e62e8-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="e62e8-308">Använda Microsoft 365 Defender för att ändra principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="e62e8-309">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-310">På sidan **Mot nätfiske** väljer du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e62e8-311">I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e62e8-312">Mer information om inställningarna finns i avsnittet Använda Microsoft 365 Defender för att skapa principer [mot nätfiske](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="e62e8-313">Standardprincipen för skydd mot nätfiske är avsnittet **Användare,** grupper och domäner inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="e62e8-314">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="e62e8-315">Aktivera eller inaktivera anpassade principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="e62e8-316">Du kan inte inaktivera standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e62e8-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="e62e8-317">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-318">På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e62e8-319">Högst upp i den utfällda menyn principinformation ser du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e62e8-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="e62e8-320">**Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .</span><span class="sxs-lookup"><span data-stu-id="e62e8-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="e62e8-321">**Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="e62e8-322">I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="e62e8-323">Klicka **Stäng** i den utfällda menyn principinformation.</span><span class="sxs-lookup"><span data-stu-id="e62e8-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="e62e8-324">Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="e62e8-325">Ange prioritet för anpassade principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="e62e8-326">Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="e62e8-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e62e8-327">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="e62e8-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e62e8-328">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="e62e8-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e62e8-329">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Defender-portalen).</span><span class="sxs-lookup"><span data-stu-id="e62e8-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="e62e8-330">Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="e62e8-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="e62e8-331">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="e62e8-331">**Notes**:</span></span>

- <span data-ttu-id="e62e8-332">I Microsoft 365 Defender-portalen kan du bara ändra prioriteten för nätfiskeprincipen när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="e62e8-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="e62e8-333">I PowerShell kan du åsidosätta standardprioritet när du skapar antifrasregeln (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="e62e8-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="e62e8-334">Principer för skydd mot nätfiske bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="e62e8-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e62e8-335">Standardprincipen för skydd mot nätfiske har **prioritetsvärdet Lägsta** och du kan inte ändra den.</span><span class="sxs-lookup"><span data-stu-id="e62e8-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="e62e8-336">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-337">På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e62e8-338">Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:</span><span class="sxs-lookup"><span data-stu-id="e62e8-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="e62e8-339">Principen med **prioritetsvärdet** **0** har bara alternativet **Minska** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="e62e8-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="e62e8-340">Principen med det lägsta **prioritetsvärdet** (till exempel **3)** har endast alternativet **Öka** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="e62e8-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="e62e8-341">Om du har tre eller fler principer har principerna mellan de högsta och lägsta prioritetsvärdena både alternativen Öka **prioritet** **och Minska** prioritet tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="e62e8-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="e62e8-342">Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="e62e8-343">Klicka **Stäng** i den utfällda menyn principinformation när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="e62e8-344">Använda Microsoft 365 Defender för att ta bort anpassade principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="e62e8-345">När du använder Microsoft 365 Defender-portalen för att ta bort en anpassad policy mot nätfiske tas både antifishregeln och motsvarande anti-phish-policy bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="e62e8-346">Du kan inte ta bort standardprincipen för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e62e8-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="e62e8-347">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e62e8-348">På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet på principen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="e62e8-349">Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="e62e8-350">I bekräftelsedialogrutan som visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e62e8-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="e62e8-351">Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="e62e8-352">Som tidigare beskrivits består en policy mot skräppost av en anti-phish-policy och en anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="e62e8-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="e62e8-353">I Exchange Online PowerShell visar sig skillnaden mellan anti-phish-policyer och anti-phish-regler.</span><span class="sxs-lookup"><span data-stu-id="e62e8-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="e62e8-354">Du hanterar antifish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-phish-regler med hjälp av cmdletarna **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="e62e8-355">I PowerShell skapar du först den nätfiska principen och sedan skapar du den skyddande phish-regeln som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="e62e8-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e62e8-356">I PowerShell ändrar du inställningarna separat i antifish-principen och antifish-regeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="e62e8-357">När du tar bort en anti-phish-policy från PowerShell tas inte motsvarande anti phish-regel bort automatiskt, och vice versa.</span><span class="sxs-lookup"><span data-stu-id="e62e8-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="e62e8-358">Använda PowerShell för att skapa principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="e62e8-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="e62e8-359">Det krävs två steg för att skapa en princip mot nätfiske i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e62e8-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e62e8-360">Skapa den anfish-policy som du sedan skapar.</span><span class="sxs-lookup"><span data-stu-id="e62e8-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="e62e8-361">Skapa den anti phish-regel som anger den antifishpolicy som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="e62e8-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="e62e8-362">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="e62e8-362">**Notes**:</span></span>

- <span data-ttu-id="e62e8-363">Du kan skapa en ny anti-phish-regel och tilldela en befintlig, oassocierad antifishprincip till den.</span><span class="sxs-lookup"><span data-stu-id="e62e8-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="e62e8-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span><span class="sxs-lookup"><span data-stu-id="e62e8-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="e62e8-365">Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="e62e8-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="e62e8-366">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="e62e8-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="e62e8-367">Ange prioritet för principen vid skapandet (_Prioritet_ _\<Number\>_ ) på **cmdleten New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="e62e8-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="e62e8-368">En ny anti phish-policy som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en antifishregel.</span><span class="sxs-lookup"><span data-stu-id="e62e8-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="e62e8-369">Steg 1: Använd PowerShell för att skapa en anti-phish-policy</span><span class="sxs-lookup"><span data-stu-id="e62e8-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="e62e8-370">Använd följande syntax för att skapa en antifishpolicy:</span><span class="sxs-lookup"><span data-stu-id="e62e8-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="e62e8-371">I det här exemplet skapas en antifishprincip som heter Forskningsin karantän med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e62e8-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="e62e8-372">Principen är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="e62e8-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="e62e8-373">Beskrivningen är: Forskningavdelningens policy.</span><span class="sxs-lookup"><span data-stu-id="e62e8-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="e62e8-374">Ger skydd av organisationsdomäner för alla godkända domäner och skydd för riktade domäner fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e62e8-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="e62e8-375">Anger MaiOrto (mfujito@fabrikam.com) som användaren som ska skydda från personifiering.</span><span class="sxs-lookup"><span data-stu-id="e62e8-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="e62e8-376">Aktiverar postlådeintelligens.</span><span class="sxs-lookup"><span data-stu-id="e62e8-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="e62e8-377">Aktiverar postlådeintelligensskydd och anger karantänåtgärden.</span><span class="sxs-lookup"><span data-stu-id="e62e8-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="e62e8-378">Aktiverar säkerhetstips.</span><span class="sxs-lookup"><span data-stu-id="e62e8-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="e62e8-379">Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e62e8-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="e62e8-380">Steg 2: Använd PowerShell för att skapa en antifishregel</span><span class="sxs-lookup"><span data-stu-id="e62e8-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="e62e8-381">Använd följande syntax för att skapa en antifishregel:</span><span class="sxs-lookup"><span data-stu-id="e62e8-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="e62e8-382">I det här exemplet skapas en antifishregel som heter Forskningsavdelningen med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="e62e8-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="e62e8-383">Regeln är kopplad till den nättfiska principen som heter Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="e62e8-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="e62e8-384">Regeln gäller för medlemmar i gruppen Research Department.</span><span class="sxs-lookup"><span data-stu-id="e62e8-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="e62e8-385">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="e62e8-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="e62e8-386">Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="e62e8-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="e62e8-387">Använda PowerShell för att se nätträcksprinciper</span><span class="sxs-lookup"><span data-stu-id="e62e8-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="e62e8-388">Om du vill se befintliga skyddsprinciper använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e62e8-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e62e8-389">Det här exemplet returnerar en sammanfattning av alla antifishpolicys tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="e62e8-390">Det här exemplet returnerar alla egenskapsvärden för den nättfiska policyn cheferna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="e62e8-391">Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e62e8-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="e62e8-392">Använda PowerShell för att se nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="e62e8-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="e62e8-393">Använd följande syntax för att visa befintliga skydd mot phish-regler:</span><span class="sxs-lookup"><span data-stu-id="e62e8-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e62e8-394">Det här exemplet returnerar en sammanfattning av alla nättringsregler tillsammans med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="e62e8-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="e62e8-395">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="e62e8-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="e62e8-396">I det här exemplet returneras alla egenskapsvärden för den nättfiska regeln Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e62e8-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="e62e8-397">Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="e62e8-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="e62e8-398">Använda PowerShell för att ändra skydd mot nättfingor</span><span class="sxs-lookup"><span data-stu-id="e62e8-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="e62e8-399">Förutom följande objekt är samma inställningar tillgängliga när du ändrar en [anti-phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) i PowerShell som när du skapar principen enligt beskrivningen i Steg 1: Använda PowerShell för att skapa ett avsnitt för en anti-phish-policy tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="e62e8-400">Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (används för alla, alltid lägst prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätfnig princip i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e62e8-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="e62e8-401">Du kan inte byta namn på en nätt **phish-policy (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="e62e8-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e62e8-402">När du byter namn på en policy mot nätfiske i Microsoft 365 Defender-portalen byter du bara namn på _nätfiskeregeln._</span><span class="sxs-lookup"><span data-stu-id="e62e8-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="e62e8-403">Använd följande syntax för att ändra en nätt phish-policy:</span><span class="sxs-lookup"><span data-stu-id="e62e8-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e62e8-404">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e62e8-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="e62e8-405">Använda PowerShell för att ändra skydd mot phish-regler</span><span class="sxs-lookup"><span data-stu-id="e62e8-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="e62e8-406">Den enda inställningen som inte är tillgänglig när du ändrar en antifishregel i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="e62e8-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e62e8-407">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddsregler.</span><span class="sxs-lookup"><span data-stu-id="e62e8-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="e62e8-408">Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en antifn-regel i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e62e8-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="e62e8-409">Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg 2: Använd PowerShell för att skapa en [nättfingrregel](#step-2-use-powershell-to-create-an-anti-phish-rule) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e62e8-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="e62e8-410">Använd följande syntax för att ändra en antifishregel:</span><span class="sxs-lookup"><span data-stu-id="e62e8-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e62e8-411">Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="e62e8-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="e62e8-412">Använda PowerShell för att aktivera eller inaktivera nätthetsregler</span><span class="sxs-lookup"><span data-stu-id="e62e8-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="e62e8-413">Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen).</span><span class="sxs-lookup"><span data-stu-id="e62e8-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="e62e8-414">Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).</span><span class="sxs-lookup"><span data-stu-id="e62e8-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="e62e8-415">Om du vill aktivera eller inaktivera en nätträcksregel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e62e8-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="e62e8-416">I det här exemplet inaktiveras den phish-regeln Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="e62e8-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e62e8-417">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="e62e8-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e62e8-418">Detaljerad information om syntax och parametrar finns [i Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="e62e8-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="e62e8-419">Använd PowerShell för att ange prioriteten för nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="e62e8-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="e62e8-420">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="e62e8-420">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e62e8-421">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="e62e8-421">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e62e8-422">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="e62e8-422">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e62e8-423">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="e62e8-423">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e62e8-424">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="e62e8-424">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e62e8-425">Om du vill ange prioriteten för en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e62e8-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e62e8-426">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="e62e8-426">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e62e8-427">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="e62e8-427">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e62e8-428">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="e62e8-428">**Notes**:</span></span>

- <span data-ttu-id="e62e8-429">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-AntiPhishRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="e62e8-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="e62e8-430">Den förvalda antifish-principen har inte en motsvarande antifiska regel och har alltid det oföränderliga prioritetsvärdet **Lägsta.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="e62e8-431">Använda PowerShell för att ta bort nättfällprinciper</span><span class="sxs-lookup"><span data-stu-id="e62e8-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="e62e8-432">När du använder PowerShell för att ta bort en anti-phish-policy tas motsvarande anti phish-regel inte bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="e62e8-433">Om du vill ta bort en anti-phish-policy i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e62e8-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e62e8-434">I det här exemplet tas den nättfiska policyn Marketing Department bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e62e8-435">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="e62e8-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="e62e8-436">Använda PowerShell för att ta bort nätträcksregler</span><span class="sxs-lookup"><span data-stu-id="e62e8-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="e62e8-437">När du använder PowerShell för att ta bort en anti-phish-regel tas motsvarande anti-phish-policy inte bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="e62e8-438">Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e62e8-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="e62e8-439">I det här exemplet tas den antifiska regeln Marknadsföringsavdelningen bort.</span><span class="sxs-lookup"><span data-stu-id="e62e8-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e62e8-440">Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="e62e8-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e62e8-441">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="e62e8-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="e62e8-442">Verifiera att du har konfigurerat principer för skydd mot nätfiske i Defender för Office 365 genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="e62e8-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="e62e8-443">I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="e62e8-444">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="e62e8-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e62e8-445">Om du vill visa mer information väljer du principen i listan genom att klicka på namnet och visa informationen i den utfäll vy som visas.</span><span class="sxs-lookup"><span data-stu-id="e62e8-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="e62e8-446">I Exchange Online Ersätt med namnet på principen eller regeln i PowerShell och kör \<Name\> följande kommando och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="e62e8-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
