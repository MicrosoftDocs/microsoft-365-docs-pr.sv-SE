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
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207024"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="29287-103">Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="29287-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="29287-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="29287-104">**Applies to**</span></span>
- [<span data-ttu-id="29287-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="29287-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="29287-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="29287-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="29287-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29287-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="29287-108">Konfigurationsanalys i Säkerhets- och efterlevnadscenter för & tillhandahåller en central plats för att hitta och åtgärda säkerhetsprinciper där inställningarna finns under profilinställningarna Standardskydd och Strikt skydd i [förinställda säkerhetsprinciper.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29287-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="29287-109">Följande typer av principer analyseras av konfigurationsanalysatorn:</span><span class="sxs-lookup"><span data-stu-id="29287-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="29287-110">**Principer för Exchange Online Protection (EOP):** Det här omfattar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="29287-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="29287-111">[Principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29287-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="29287-112">[Principer för skydd mot skadlig programvara.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29287-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="29287-113">[Principer för skydd mot nätfiske i EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="29287-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="29287-114">**Principer för Microsoft Defender för Office 365:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för tilläggsprenumerationer för Office 365:</span><span class="sxs-lookup"><span data-stu-id="29287-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="29287-115">Principer mot nätfiske i Microsoft Defender för Office 365, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="29287-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="29287-116">Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="29287-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="29287-117">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="29287-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="29287-118">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="29287-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="29287-119">[Principer för säkra länkar.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29287-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>

  - <span data-ttu-id="29287-120">[Principer för säkra bifogade filer.](set-up-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29287-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="29287-121">**Standard-** och **Strikt-principinställningsvärdena** som används som baslinjer beskrivs i Rekommenderade inställningar för EOP och Microsoft Defender för Office [365-säkerhet.](recommended-settings-for-eop-and-office365.md)</span><span class="sxs-lookup"><span data-stu-id="29287-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="29287-122">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="29287-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="29287-123">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="29287-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="29287-124">Använd för att gå **direkt till sidan Configuration analyzer** <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="29287-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="29287-125">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="29287-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="29287-126">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="29287-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="29287-127">Om du vill använda konfigurationsanalysatorn och uppdatera säkerhetsprinciper måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="29287-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="29287-128">För skrivskyddade åtkomst till konfigurationsanalys behöver du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="29287-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="29287-129">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="29287-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="29287-130">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29287-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="29287-131">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="29287-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="29287-132">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="29287-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="29287-133">Använda konfigurationsanalysen i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="29287-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="29287-134">I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Analysverktyg** för \> **hantering av** \> **hotprinciper.**</span><span class="sxs-lookup"><span data-stu-id="29287-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget för konfigurationsanalys på sidan \> Hothanteringspolicy](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="29287-136">Konfigurationsanalysen har två huvudflikar:</span><span class="sxs-lookup"><span data-stu-id="29287-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="29287-137">**Inställningar och rekommendationer:** Du väljer Standard eller Strikt och jämför inställningarna med dina befintliga säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="29287-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="29287-138">I resultatet kan du justera värdena i inställningarna så att de hamnar på samma nivå som Standard eller Strikt.</span><span class="sxs-lookup"><span data-stu-id="29287-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="29287-139">**Konfigurationsanalys och historik:** I den här vyn kan du spåra principändringar över tid.</span><span class="sxs-lookup"><span data-stu-id="29287-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="29287-140">Fliken Inställningar och rekommendationer i konfigurationsanalys</span><span class="sxs-lookup"><span data-stu-id="29287-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="29287-141">Som standard öppnas fliken med jämförelsen av profilen för standardskydd.</span><span class="sxs-lookup"><span data-stu-id="29287-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="29287-142">Du kan växla till jämförelsen av profilen för strikt skydd genom att klicka på **Visa strikt rekommendationer.**</span><span class="sxs-lookup"><span data-stu-id="29287-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="29287-143">Om du vill växla tillbaka väljer du **Visa standardrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="29287-143">To switch back, select **View Standard recommendations**.</span></span>

![Vyn Inställningar och rekommendationer i Konfigurationsanalys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="29287-145">Som standard innehåller **namnkolumnen Principgrupp/inställning** en komprimerad vy av de olika typerna av säkerhetsprinciper och antalet inställningar som behöver förbättras (om sådana finns).</span><span class="sxs-lookup"><span data-stu-id="29287-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="29287-146">Här är typerna av principer:</span><span class="sxs-lookup"><span data-stu-id="29287-146">The types of policies are:</span></span>

- <span data-ttu-id="29287-147">**Skräppostskydd**</span><span class="sxs-lookup"><span data-stu-id="29287-147">**Anti-spam**</span></span>
- <span data-ttu-id="29287-148">**Skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="29287-148">**Anti-phishing**</span></span>
- <span data-ttu-id="29287-149">**Skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="29287-149">**Anti-malware**</span></span>
- <span data-ttu-id="29287-150">**ATP – säkra bifogade** filer (om prenumerationen omfattar Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="29287-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="29287-151">**ATP – säkra** länkar (om microsoft Defender för Office 365 ingår i prenumerationen)</span><span class="sxs-lookup"><span data-stu-id="29287-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="29287-152">I standardvyn döljs allt.</span><span class="sxs-lookup"><span data-stu-id="29287-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="29287-153">Bredvid varje princip finns en sammanfattning av jämförelseresultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard- eller striktskyddsprofilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="29287-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="29287-154">Följande information visas för den skyddsprofil som du jämför med:</span><span class="sxs-lookup"><span data-stu-id="29287-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="29287-155">**Grön**: Alla inställningar i alla befintliga principer är minst lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="29287-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="29287-156">**Gult** antal: Ett litet antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="29287-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="29287-157">**Röd**: Ett stort antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="29287-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="29287-158">Det kan vara några inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="29287-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="29287-159">För bra jämförelser ser du texten: Alla inställningar **följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="29287-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="29287-160">I annat fall visas antalet rekommenderade inställningar som ska ändras.</span><span class="sxs-lookup"><span data-stu-id="29287-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="29287-161">Om du **expanderar grupp-/inställningsnamn** för princip visas alla principer och de associerade inställningarna i varje specifik princip som kräver uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="29287-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="29287-162">Du kan också expandera en viss typ av princip (till exempel Skräppostskydd) om du bara vill visa de inställningarna i de policytyper som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="29287-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="29287-163">Om jämförelsen inte har några rekommendationer för förbättring (grön) visar expanderande princip ingenting.</span><span class="sxs-lookup"><span data-stu-id="29287-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="29287-164">Om det finns något antal rekommendationer för förbättring (gult eller rött) visas de inställningar som kräver uppmärksamhet och motsvarande information visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="29287-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="29287-165">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="29287-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="29287-166">I den föregående skärmbilden är till exempel tröskelvärdet för **massutskick** av e-post i en princip mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="29287-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="29287-167">**Princip:** Namnet på den princip som påverkas som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="29287-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="29287-168">**Tillämpas på:** Antalet användare som de aktuella principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="29287-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="29287-169">**Aktuell konfiguration:** Det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="29287-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="29287-170">**Senast ändrad:** Datumet då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="29287-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="29287-171">**Rekommendationer:** Värdet på inställningen i profilen standard eller strikt skydd.</span><span class="sxs-lookup"><span data-stu-id="29287-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="29287-172">Om du vill ändra värdet för inställningen i principen så att den matchar det rekommenderade värdet i skyddsprofilen klickar du på **Adopt**.</span><span class="sxs-lookup"><span data-stu-id="29287-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="29287-173">Om ändringen lyckas visas meddelandet: Rekommendationer **har godkänts**.</span><span class="sxs-lookup"><span data-stu-id="29287-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="29287-174">Klicka **på** Uppdatera om du vill se det minskade antalet rekommendationer och borttagningen av den specifika inställnings-/principraden från resultatet.</span><span class="sxs-lookup"><span data-stu-id="29287-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="29287-175">Konfigurationsanalys och historikfliken i konfigurationsanalys</span><span class="sxs-lookup"><span data-stu-id="29287-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="29287-176">På den här fliken kan du spåra de ändringar som du har gjort av dina anpassade säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="29287-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="29287-177">Som standard visas följande information:</span><span class="sxs-lookup"><span data-stu-id="29287-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="29287-178">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="29287-178">**Last modified**</span></span>
- <span data-ttu-id="29287-179">**Ändrad av**</span><span class="sxs-lookup"><span data-stu-id="29287-179">**Modified by**</span></span>
- <span data-ttu-id="29287-180">**Inställningsnamn**</span><span class="sxs-lookup"><span data-stu-id="29287-180">**Setting Name**</span></span>
- <span data-ttu-id="29287-181">**Princip**</span><span class="sxs-lookup"><span data-stu-id="29287-181">**Policy**</span></span>
- <span data-ttu-id="29287-182">**Typ**</span><span class="sxs-lookup"><span data-stu-id="29287-182">**Type**</span></span>

<span data-ttu-id="29287-183">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="29287-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="29287-184">I  den utfällna listan Filter som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="29287-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="29287-185">**Starttid** **och Sluttid** (datum)</span><span class="sxs-lookup"><span data-stu-id="29287-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="29287-186">**Standardskydd** eller **Strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="29287-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="29287-187">Om du vill exportera resultaten till en CSV-fil klickar du på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="29287-187">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurationsanalys och historikvy i Konfigurationsanalys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)