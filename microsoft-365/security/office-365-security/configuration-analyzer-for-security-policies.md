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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder konfigurations analys för att hitta och åtgärda säkerhets principer som är under standard säkerhets principer för förvalda skydd och begränsande skydd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029484"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="fe650-103">Konfigurations analys för skydds principer i EOP och Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fe650-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fe650-104">Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda säkerhets principer där inställningarna är under standard skydds-och strikta skydds profil inställningar i [förvalda säkerhets principer](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-104">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="fe650-105">Följande typer av principer analyseras av konfigurations analys:</span><span class="sxs-lookup"><span data-stu-id="fe650-105">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="fe650-106">**Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="fe650-106">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="fe650-107">[Principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-107">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="fe650-108">[Principer mot skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-108">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="fe650-109">[EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="fe650-109">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="fe650-110">**Microsoft Defender för Office 365-principer**: Detta inkluderar organisationer med Microsoft 365 E5-eller Defender för Office 365-tilläggs prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="fe650-110">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="fe650-111">Skydd mot nätfiske i Microsoft Defender för Office 365, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="fe650-111">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="fe650-112">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.</span><span class="sxs-lookup"><span data-stu-id="fe650-112">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="fe650-113">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="fe650-113">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="fe650-114">Avancerade nät fiske trösklar</span><span class="sxs-lookup"><span data-stu-id="fe650-114">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="fe650-115">[Principer för säkra länkar](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-115">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="fe650-116">[Principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-116">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="fe650-117">De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-117">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fe650-118">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="fe650-118">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fe650-119">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fe650-119">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fe650-120">Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="fe650-120">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="fe650-121">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe650-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="fe650-122">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="fe650-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fe650-123">För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="fe650-123">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="fe650-124">Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .</span><span class="sxs-lookup"><span data-stu-id="fe650-124">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fe650-125">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fe650-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="fe650-126">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe650-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fe650-127">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="fe650-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="fe650-128">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="fe650-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="fe650-129">Använda Configuration Analyzer i Center för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="fe650-129">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="fe650-130">Gå till  \>  \> **konfigurations analys** för Threat Management policy i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="fe650-130">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="fe650-132">Konfigurations analysen har två primära flikar:</span><span class="sxs-lookup"><span data-stu-id="fe650-132">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="fe650-133">**Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="fe650-133">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="fe650-134">I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.</span><span class="sxs-lookup"><span data-stu-id="fe650-134">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="fe650-135">**Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra princip förändringar med tiden.</span><span class="sxs-lookup"><span data-stu-id="fe650-135">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="fe650-136">Fliken inställning och rekommendationer i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="fe650-136">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="fe650-137">Som standard öppnas fliken i jämförelsen med standard skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="fe650-137">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="fe650-138">Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="fe650-138">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="fe650-139">Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="fe650-139">To switch back, select **View Standard recommendations**.</span></span>

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="fe650-141">Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och det antal inställningar som behöver förbättras.</span><span class="sxs-lookup"><span data-stu-id="fe650-141">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="fe650-142">Följande typer av principer är:</span><span class="sxs-lookup"><span data-stu-id="fe650-142">The types of policies are:</span></span>

- <span data-ttu-id="fe650-143">**Skydd mot skräp post**</span><span class="sxs-lookup"><span data-stu-id="fe650-143">**Anti-spam**</span></span>
- <span data-ttu-id="fe650-144">**Anti-nätfiske**</span><span class="sxs-lookup"><span data-stu-id="fe650-144">**Anti-phishing**</span></span>
- <span data-ttu-id="fe650-145">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="fe650-145">**Anti-malware**</span></span>
- <span data-ttu-id="fe650-146">**ATP-säkra bifogade filer** (om ditt abonnemang innehåller Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="fe650-146">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="fe650-147">**Säkerhet för ATP** (om ditt abonnemang inkluderar Microsoft Defender för Office 365)</span><span class="sxs-lookup"><span data-stu-id="fe650-147">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="fe650-148">I standardvyn är allting dolda.</span><span class="sxs-lookup"><span data-stu-id="fe650-148">In the default view, everything is collapsed.</span></span> <span data-ttu-id="fe650-149">Bredvid varje princip finns en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="fe650-149">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="fe650-150">Följande information om den skydds profil som du jämför med ska visas:</span><span class="sxs-lookup"><span data-stu-id="fe650-150">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="fe650-151">**Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="fe650-151">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="fe650-152">**Gul**: ett litet antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="fe650-152">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="fe650-153">**Rött**: ett stort antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="fe650-153">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="fe650-154">Det här kan vara några få inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="fe650-154">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="fe650-155">För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="fe650-155">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="fe650-156">I annat fall ser du antalet rekommenderade inställningar att ändra.</span><span class="sxs-lookup"><span data-stu-id="fe650-156">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="fe650-157">Om du expanderar **princip grupp/inställnings namn** visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fe650-157">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="fe650-158">Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="fe650-158">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="fe650-159">Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting.</span><span class="sxs-lookup"><span data-stu-id="fe650-159">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="fe650-160">Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="fe650-160">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="fe650-161">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="fe650-161">The name of the setting that requires your attention.</span></span> <span data-ttu-id="fe650-162">I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="fe650-162">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="fe650-163">**Princip**: namnet på den berörda policyn som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="fe650-163">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="fe650-164">**Tillämpas på**: antalet användare som de berörda principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="fe650-164">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="fe650-165">**Aktuell konfiguration**: det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="fe650-165">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="fe650-166">**Senast ändrad**: det datum då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="fe650-166">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="fe650-167">**Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="fe650-167">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="fe650-168">Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.**</span><span class="sxs-lookup"><span data-stu-id="fe650-168">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="fe650-169">Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**.</span><span class="sxs-lookup"><span data-stu-id="fe650-169">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="fe650-170">Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.</span><span class="sxs-lookup"><span data-stu-id="fe650-170">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="fe650-171">Konfiguration av avvikelser och historik i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="fe650-171">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="fe650-172">Med den här fliken kan du spåra de ändringar du har gjort i dina anpassade säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="fe650-172">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="fe650-173">Följande information visas som standard:</span><span class="sxs-lookup"><span data-stu-id="fe650-173">By default, the following information is displayed:</span></span>

- <span data-ttu-id="fe650-174">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="fe650-174">**Last modified**</span></span>
- <span data-ttu-id="fe650-175">**Ändrat av**</span><span class="sxs-lookup"><span data-stu-id="fe650-175">**Modified by**</span></span>
- <span data-ttu-id="fe650-176">**Inställnings namn**</span><span class="sxs-lookup"><span data-stu-id="fe650-176">**Setting Name**</span></span>
- <span data-ttu-id="fe650-177">**Autentiseringsprincip**</span><span class="sxs-lookup"><span data-stu-id="fe650-177">**Policy**</span></span>
- <span data-ttu-id="fe650-178">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fe650-178">**Type**</span></span>

<span data-ttu-id="fe650-179">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="fe650-179">To filter the results, click **Filter**.</span></span> <span data-ttu-id="fe650-180">I de utfällbara **filter** som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="fe650-180">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="fe650-181">**Start tid** och **slut tid** (datum)</span><span class="sxs-lookup"><span data-stu-id="fe650-181">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="fe650-182">**Standard skydd** eller **strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="fe650-182">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="fe650-183">Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="fe650-183">To export the results to a .csv file, click **Export**.</span></span>

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
