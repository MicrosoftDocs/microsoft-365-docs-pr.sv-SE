---
title: Konfigurationsanalys för säkerhetsprinciper
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda konfigurationsanalysatorn för att hitta och åtgärda säkerhetsprinciper som finns under de förinställda säkerhetsprinciperna Standardskydd och Strikt skydd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f98ab9b251894a5821d308d95fd786b496e396e4
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878670"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="2187b-103">Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="2187b-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2187b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2187b-104">**Applies to**</span></span>
- [<span data-ttu-id="2187b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2187b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2187b-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2187b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2187b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2187b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2187b-108">Konfigurationsanalys i Microsoft 365 Defender-portalen ger dig en central plats för att hitta och åtgärda säkerhetsprinciper där inställningarna finns under inställningarna Standardskydd och Strikt skydd i [förinställda säkerhetsprinciper.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2187b-108">Configuration analyzer in the Microsoft 365 Defender portal provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="2187b-109">Följande typer av principer analyseras av konfigurationsanalysatorn:</span><span class="sxs-lookup"><span data-stu-id="2187b-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="2187b-110">**Exchange Online Protection (EOP):** Det här omfattar Microsoft 365 organisationer med Exchange Online e-postlådor och fristående EOP-organisationer utan Exchange Online postlådor:</span><span class="sxs-lookup"><span data-stu-id="2187b-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="2187b-111">[Principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2187b-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="2187b-112">[Principer för skydd mot skadlig programvara.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2187b-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="2187b-113">[Principer för skydd mot nätfiske i EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="2187b-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="2187b-114">**Microsoft Defender Office 365 principer:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för Office 365 tilläggsprenumerationer:</span><span class="sxs-lookup"><span data-stu-id="2187b-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="2187b-115">Principer mot nätfiske i Microsoft Defender för Office 365, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="2187b-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="2187b-116">Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="2187b-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="2187b-117">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="2187b-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="2187b-118">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="2187b-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="2187b-119">[Valv principer för länkar](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2187b-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="2187b-120">[Valv principer för bifogade filer](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2187b-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="2187b-121">**Standard-** och Strikt-principinställningsvärdena som används som baslinjer beskrivs i Rekommenderade inställningar för EOP och [Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md) </span><span class="sxs-lookup"><span data-stu-id="2187b-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2187b-122">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2187b-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2187b-123">Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="2187b-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="2187b-124">Använd för att gå **direkt till sidan Configuration analyzer** <https://security.microsoft.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="2187b-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="2187b-125">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2187b-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2187b-126">Du måste ha tilldelats behörigheter i Microsoft 365 Defender-portalen innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="2187b-126">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2187b-127">Om du vill använda konfigurationsanalysatorn och uppdatera säkerhetsprinciper måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="2187b-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2187b-128">För skrivskyddade åtkomst till konfigurationsanalys behöver du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="2187b-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2187b-129">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="2187b-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="2187b-130">Om du lägger till användare i Azure Active Directory-rollen får användarna de behörigheter  som krävs i Microsoft 365 Defender-portalen samt behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2187b-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2187b-131">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2187b-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="2187b-132">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="2187b-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2187b-133">Använda konfigurationsanalysen i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="2187b-133">Use the configuration analyzer in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2187b-134">I Den Microsoft 365 Defender-portalen går du till avsnittet & för **&** e-postsamarbete & principer för hotprinciper i \>  \>  \>  \> **mallade principer.**</span><span class="sxs-lookup"><span data-stu-id="2187b-134">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="2187b-135">Sidan **Konfigurationsanalys** har två huvudflikar:</span><span class="sxs-lookup"><span data-stu-id="2187b-135">The **Configuration analyzer** page has two main tabs:</span></span>

- <span data-ttu-id="2187b-136">**Inställningar och rekommendationer**: Du **väljer Standard** **eller Strikt** och jämför inställningarna med dina befintliga säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="2187b-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="2187b-137">I resultatet kan du justera värdena i inställningarna så att de hamnar på samma nivå som Standard eller Strikt.</span><span class="sxs-lookup"><span data-stu-id="2187b-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="2187b-138">**Konfigurationsanalys och historik:** I den här vyn kan du spåra principändringar över tid.</span><span class="sxs-lookup"><span data-stu-id="2187b-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="2187b-139">Fliken Inställningar och rekommendationer i konfigurationsanalys</span><span class="sxs-lookup"><span data-stu-id="2187b-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="2187b-140">Som standard öppnas fliken med jämförelsen av profilen för standardskydd.</span><span class="sxs-lookup"><span data-stu-id="2187b-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="2187b-141">Du kan växla till jämförelsen av profilen med strikt skydd genom att välja **Visa strikt rekommendationer.**</span><span class="sxs-lookup"><span data-stu-id="2187b-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="2187b-142">Om du vill växla tillbaka väljer du **Visa standardrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="2187b-142">To switch back, select **View Standard recommendations**.</span></span>

![Inställningar och rekommendationer i konfigurationsanalys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="2187b-144">Som standard innehåller **namnkolumnen Principgrupp/inställning** en komprimerad vy av de olika typerna av säkerhetsprinciper och antalet inställningar som behöver förbättras (om sådana finns).</span><span class="sxs-lookup"><span data-stu-id="2187b-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="2187b-145">Här är typerna av principer:</span><span class="sxs-lookup"><span data-stu-id="2187b-145">The types of policies are:</span></span>

- <span data-ttu-id="2187b-146">**Skräppostskydd**</span><span class="sxs-lookup"><span data-stu-id="2187b-146">**Anti-spam**</span></span>
- <span data-ttu-id="2187b-147">**Skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="2187b-147">**Anti-phishing**</span></span>
- <span data-ttu-id="2187b-148">**Skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="2187b-148">**Anti-malware**</span></span>
- <span data-ttu-id="2187b-149">**Valv bifogade filer** (om din prenumeration inkluderar Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="2187b-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="2187b-150">**Valv (om** din prenumeration inkluderar Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="2187b-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="2187b-151">I standardvyn döljs allt.</span><span class="sxs-lookup"><span data-stu-id="2187b-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="2187b-152">Bredvid varje princip finns en sammanfattning av jämförelseresultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard- eller striktskyddsprofilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="2187b-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="2187b-153">Följande information visas för den skyddsprofil som du jämför med:</span><span class="sxs-lookup"><span data-stu-id="2187b-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="2187b-154">**Grön**: Alla inställningar i alla befintliga principer är minst lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="2187b-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="2187b-155">**Gult** antal: Ett litet antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="2187b-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="2187b-156">**Röd**: Ett stort antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="2187b-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="2187b-157">Det kan vara några inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="2187b-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="2187b-158">För bra jämförelser ser du texten: Alla inställningar **följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="2187b-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="2187b-159">I annat fall visas antalet rekommenderade inställningar som ska ändras.</span><span class="sxs-lookup"><span data-stu-id="2187b-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="2187b-160">Om du **expanderar grupp-/inställningsnamn** för princip visas alla principer och de associerade inställningarna i varje specifik princip som kräver uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="2187b-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="2187b-161">Du kan också expandera en viss typ av princip (till exempel Skräppostskydd) om du bara vill visa de inställningarna i de policytyper som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="2187b-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="2187b-162">Om jämförelsen inte har några rekommendationer för förbättring (grön) visar expanderande princip ingenting.</span><span class="sxs-lookup"><span data-stu-id="2187b-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="2187b-163">Om det finns något antal rekommendationer för förbättring (gult eller rött) visas de inställningar som kräver uppmärksamhet och motsvarande information visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="2187b-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="2187b-164">**Principgrupp/inställningsnamn:** Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="2187b-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="2187b-165">På föregående skärmbild är det till exempel inställningarna i standardprincipen för skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="2187b-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="2187b-166">**Princip:** Namnet på den princip som påverkas som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="2187b-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="2187b-167">**Tillämpas på:** Antalet användare som de aktuella principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="2187b-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="2187b-168">**Aktuell konfiguration:** Det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="2187b-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="2187b-169">Det här värdet är tomt för standardprincipen av den typen som gäller för alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="2187b-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="2187b-170">**Senast ändrad:** Datumet då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="2187b-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="2187b-171">**Rekommendationer:** Värdet på inställningen i profilen standard eller Strikt skydd.</span><span class="sxs-lookup"><span data-stu-id="2187b-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="2187b-172">Om du vill ändra värdet för inställningen i principen så att den matchar det rekommenderade värdet i skyddsprofilen klickar du på **Adopt**.</span><span class="sxs-lookup"><span data-stu-id="2187b-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="2187b-173">Om ändringen lyckas visas meddelandet: Används **Rekommendationer används**.</span><span class="sxs-lookup"><span data-stu-id="2187b-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="2187b-174">Klicka **på** Uppdatera om du vill se det minskade antalet rekommendationer och borttagningen av den specifika inställnings-/principraden från resultatet.</span><span class="sxs-lookup"><span data-stu-id="2187b-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="2187b-175">Konfigurationsanalys och historikfliken i konfigurationsanalys</span><span class="sxs-lookup"><span data-stu-id="2187b-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="2187b-176">På den här fliken kan du spåra de ändringar som du har gjort av dina anpassade säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="2187b-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="2187b-177">Som standard visas följande information:</span><span class="sxs-lookup"><span data-stu-id="2187b-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="2187b-178">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="2187b-178">**Last modified**</span></span>
- <span data-ttu-id="2187b-179">**Ändrad av**</span><span class="sxs-lookup"><span data-stu-id="2187b-179">**Modified by**</span></span>
- <span data-ttu-id="2187b-180">**Inställningsnamn**</span><span class="sxs-lookup"><span data-stu-id="2187b-180">**Setting Name**</span></span>
- <span data-ttu-id="2187b-181">**Princip**</span><span class="sxs-lookup"><span data-stu-id="2187b-181">**Policy**</span></span>
- <span data-ttu-id="2187b-182">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2187b-182">**Type**</span></span>
- <span data-ttu-id="2187b-183">**Konfigurationsändring**</span><span class="sxs-lookup"><span data-stu-id="2187b-183">**Configuration change**</span></span>
- <span data-ttu-id="2187b-184">**Konfigurations drift**: värdet **Öka** eller **Minska**.</span><span class="sxs-lookup"><span data-stu-id="2187b-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="2187b-185">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="2187b-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2187b-186">I  den utfällna listan Filter som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="2187b-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="2187b-187">**Starttid** **och Sluttid** (datum)</span><span class="sxs-lookup"><span data-stu-id="2187b-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="2187b-188">**Standardskydd** eller **Strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="2187b-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="2187b-189">Om du vill exportera resultaten till en .csv klickar du på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="2187b-189">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurationsanalys och historikvy i Konfigurationsanalys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
