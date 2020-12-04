---
title: Konfigurations analys för säkerhets principer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder konfigurations analys för att hitta och åtgärda säkerhets principer som är under standard säkerhets principer för förvalda skydd och begränsande skydd.
ms.openlocfilehash: 7d02a6f83ceb06eb56039b449890fd90712c76e5
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572543"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="aca25-103">Konfigurations analys för skydds principer i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="aca25-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="aca25-104">De funktioner som beskrivs i det här avsnittet är i för hands version, är inte tillgängliga i alla organisationer och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="aca25-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="aca25-105">Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="aca25-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="aca25-106">Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda säkerhets principer där inställningarna är under standard skydds-och strikta skydds profil inställningar i [förvalda säkerhets principer](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="aca25-107">Följande typer av principer analyseras av konfigurations analys:</span><span class="sxs-lookup"><span data-stu-id="aca25-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="aca25-108">**Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="aca25-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="aca25-109">[Principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="aca25-110">[Principer mot skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="aca25-111">[EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="aca25-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="aca25-112">**Microsoft Defender för Office 365-principer**: Detta inkluderar organisationer med Microsoft 365 E5-eller Defender för Office 365-tilläggs prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="aca25-112">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="aca25-113">Skydd mot nätfiske i Microsoft Defender för Office 365, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="aca25-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="aca25-114">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.</span><span class="sxs-lookup"><span data-stu-id="aca25-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="aca25-115">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="aca25-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="aca25-116">Avancerade nät fiske trösklar</span><span class="sxs-lookup"><span data-stu-id="aca25-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="aca25-117">[Principer för säkra länkar](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="aca25-118">[Principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="aca25-119">De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aca25-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="aca25-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aca25-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="aca25-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="aca25-122">Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="aca25-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="aca25-123">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="aca25-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="aca25-124">Du måste tilldelas behörigheter i säkerhets & Compliance Center innan du kan göra det i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="aca25-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="aca25-125">För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="aca25-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="aca25-126">Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .</span><span class="sxs-lookup"><span data-stu-id="aca25-126">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="aca25-127">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="aca25-128">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="aca25-128">**Notes**:</span></span>

  - <span data-ttu-id="aca25-129">Om du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aca25-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="aca25-130">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="aca25-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="aca25-131">Roll gruppen **organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="aca25-131">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="aca25-132">Använda Configuration Analyzer i Center för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="aca25-132">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="aca25-133">Gå till **Threat management** \> **Policy** \> **konfigurations analys** för Threat Management policy i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="aca25-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="aca25-135">Konfigurations analysen har två primära flikar:</span><span class="sxs-lookup"><span data-stu-id="aca25-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="aca25-136">**Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="aca25-136">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="aca25-137">I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.</span><span class="sxs-lookup"><span data-stu-id="aca25-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="aca25-138">**Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra princip förändringar med tiden.</span><span class="sxs-lookup"><span data-stu-id="aca25-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="aca25-139">Fliken inställning och rekommendationer i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="aca25-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="aca25-140">Som standard öppnas fliken i jämförelsen med standard skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="aca25-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="aca25-141">Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="aca25-141">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="aca25-142">Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="aca25-142">To switch back, select **View Standard recommendations**.</span></span>

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="aca25-144">Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och det antal inställningar som behöver förbättras.</span><span class="sxs-lookup"><span data-stu-id="aca25-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="aca25-145">Följande typer av principer är:</span><span class="sxs-lookup"><span data-stu-id="aca25-145">The types of policies are:</span></span>

- <span data-ttu-id="aca25-146">**Skydd mot skräp post**</span><span class="sxs-lookup"><span data-stu-id="aca25-146">**Anti-spam**</span></span>
- <span data-ttu-id="aca25-147">**Anti-nätfiske**</span><span class="sxs-lookup"><span data-stu-id="aca25-147">**Anti-phishing**</span></span>
- <span data-ttu-id="aca25-148">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="aca25-148">**Anti-malware**</span></span>
- <span data-ttu-id="aca25-149">**ATP-säkra bifogade filer** (om ditt abonnemang innehåller Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="aca25-149">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="aca25-150">**Säkerhet för ATP** (om ditt abonnemang inkluderar Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="aca25-150">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="aca25-151">I standardvyn är allting dolda.</span><span class="sxs-lookup"><span data-stu-id="aca25-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="aca25-152">Bredvid varje princip finns en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="aca25-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="aca25-153">Följande information om den skydds profil som du jämför med ska visas:</span><span class="sxs-lookup"><span data-stu-id="aca25-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="aca25-154">**Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="aca25-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="aca25-155">**Gul**: ett litet antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="aca25-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="aca25-156">**Rött**: ett stort antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="aca25-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="aca25-157">Det här kan vara några få inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="aca25-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="aca25-158">För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="aca25-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="aca25-159">I annat fall ser du antalet rekommenderade inställningar att ändra.</span><span class="sxs-lookup"><span data-stu-id="aca25-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="aca25-160">Om du expanderar **princip grupp/inställnings namn** visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="aca25-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="aca25-161">Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="aca25-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="aca25-162">Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting.</span><span class="sxs-lookup"><span data-stu-id="aca25-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="aca25-163">Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="aca25-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="aca25-164">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="aca25-164">The name of the setting that requires your attention.</span></span> <span data-ttu-id="aca25-165">I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="aca25-165">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="aca25-166">**Princip**: namnet på den berörda policyn som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="aca25-166">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="aca25-167">**Tillämpas på**: antalet användare som de berörda principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="aca25-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="aca25-168">**Aktuell konfiguration**: det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="aca25-168">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="aca25-169">**Senast ändrad**: det datum då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="aca25-169">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="aca25-170">**Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="aca25-170">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="aca25-171">Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.**</span><span class="sxs-lookup"><span data-stu-id="aca25-171">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="aca25-172">Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**.</span><span class="sxs-lookup"><span data-stu-id="aca25-172">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="aca25-173">Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.</span><span class="sxs-lookup"><span data-stu-id="aca25-173">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="aca25-174">Konfiguration av avvikelser och historik i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="aca25-174">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="aca25-175">Med den här fliken kan du spåra de ändringar du har gjort i dina anpassade säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="aca25-175">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="aca25-176">Följande information visas som standard:</span><span class="sxs-lookup"><span data-stu-id="aca25-176">By default, the following information is displayed:</span></span>

- <span data-ttu-id="aca25-177">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="aca25-177">**Last modified**</span></span>
- <span data-ttu-id="aca25-178">**Ändrat av**</span><span class="sxs-lookup"><span data-stu-id="aca25-178">**Modified by**</span></span>
- <span data-ttu-id="aca25-179">**Inställnings namn**</span><span class="sxs-lookup"><span data-stu-id="aca25-179">**Setting Name**</span></span>
- <span data-ttu-id="aca25-180">**Autentiseringsprincip**</span><span class="sxs-lookup"><span data-stu-id="aca25-180">**Policy**</span></span>
- <span data-ttu-id="aca25-181">**Typ**</span><span class="sxs-lookup"><span data-stu-id="aca25-181">**Type**</span></span>

<span data-ttu-id="aca25-182">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="aca25-182">To filter the results, click **Filter**.</span></span> <span data-ttu-id="aca25-183">I de utfällbara **filter** som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="aca25-183">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="aca25-184">**Start tid** och **slut tid** (datum)</span><span class="sxs-lookup"><span data-stu-id="aca25-184">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="aca25-185">**Standard skydd** eller **strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="aca25-185">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="aca25-186">Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="aca25-186">To export the results to a .csv file, click **Export**.</span></span>

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
