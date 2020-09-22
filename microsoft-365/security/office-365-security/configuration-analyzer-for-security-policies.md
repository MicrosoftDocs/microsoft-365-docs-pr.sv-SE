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
ms.openlocfilehash: d2d37d937f42587ad99e4145d3a9f9fbc6a5a0f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203437"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="64da2-103">Konfigurations analys för skydds principer i EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="64da2-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="64da2-104">De funktioner som beskrivs i det här avsnittet är i för hands version, är inte tillgängliga i alla organisationer och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="64da2-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="64da2-105">Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="64da2-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="64da2-106">Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda säkerhets principer där inställningarna är under standard skydds-och strikta skydds profil inställningar i [förvalda säkerhets principer](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="64da2-107">Följande typer av principer analyseras av konfigurations analys:</span><span class="sxs-lookup"><span data-stu-id="64da2-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="64da2-108">**Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="64da2-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="64da2-109">[Principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="64da2-110">[Principer mot skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="64da2-111">[EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="64da2-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="64da2-112">**Office 365 principer för avancerat skydd (ATP)**: Detta inkluderar organisationer med Microsoft 365 E5 eller Office 365 ATP-tilläggs abonnemang:</span><span class="sxs-lookup"><span data-stu-id="64da2-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="64da2-113">ATP anti-phishing-principer, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="64da2-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="64da2-114">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.</span><span class="sxs-lookup"><span data-stu-id="64da2-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="64da2-115">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="64da2-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="64da2-116">Avancerade nät fiske trösklar</span><span class="sxs-lookup"><span data-stu-id="64da2-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="64da2-117">[Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="64da2-117">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="64da2-118">[Principer för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="64da2-118">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="64da2-119">De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="64da2-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="64da2-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="64da2-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="64da2-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="64da2-122">Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="64da2-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="64da2-123">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="64da2-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="64da2-124">Du måste tilldelas behörigheter innan du kan utföra åtgärderna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="64da2-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="64da2-125">För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="64da2-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="64da2-126">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="64da2-127">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="64da2-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="64da2-128">Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="64da2-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="64da2-129">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="64da2-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="64da2-130">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="64da2-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="64da2-131">Använda Configuration Analyzer i Center för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="64da2-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="64da2-132">Gå till **Threat management** \> **Policy** \> **konfigurations analys**för Threat Management policy i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="64da2-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="64da2-134">Konfigurations analysen har två primära flikar:</span><span class="sxs-lookup"><span data-stu-id="64da2-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="64da2-135">**Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="64da2-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="64da2-136">I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.</span><span class="sxs-lookup"><span data-stu-id="64da2-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="64da2-137">**Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra princip förändringar med tiden.</span><span class="sxs-lookup"><span data-stu-id="64da2-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="64da2-138">Fliken inställning och rekommendationer i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="64da2-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="64da2-139">Som standard öppnas fliken i jämförelsen med standard skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="64da2-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="64da2-140">Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="64da2-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="64da2-141">Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="64da2-141">To switch back, select **View Standard recommendations**.</span></span>

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="64da2-143">Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och det antal inställningar som behöver förbättras.</span><span class="sxs-lookup"><span data-stu-id="64da2-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="64da2-144">Följande typer av principer är:</span><span class="sxs-lookup"><span data-stu-id="64da2-144">The types of policies are:</span></span>

- <span data-ttu-id="64da2-145">**Skydd mot skräp post**</span><span class="sxs-lookup"><span data-stu-id="64da2-145">**Anti-spam**</span></span>
- <span data-ttu-id="64da2-146">**Anti-nätfiske**</span><span class="sxs-lookup"><span data-stu-id="64da2-146">**Anti-phishing**</span></span>
- <span data-ttu-id="64da2-147">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="64da2-147">**Anti-malware**</span></span>
- <span data-ttu-id="64da2-148">**Säkra filer för ATP** (om ditt abonnemang inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="64da2-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="64da2-149">**Säkerhet för ATP** (om ditt abonnemang inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="64da2-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="64da2-150">I standardvyn är allting dolda.</span><span class="sxs-lookup"><span data-stu-id="64da2-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="64da2-151">Bredvid varje princip finns en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="64da2-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="64da2-152">Följande information om den skydds profil som du jämför med ska visas:</span><span class="sxs-lookup"><span data-stu-id="64da2-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="64da2-153">**Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="64da2-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="64da2-154">**Gul**: ett litet antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="64da2-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="64da2-155">**Rött**: ett stort antal inställningar i befintliga principer är inte så säkert som skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="64da2-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="64da2-156">Det här kan vara några få inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="64da2-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="64da2-157">För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="64da2-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="64da2-158">I annat fall ser du antalet rekommenderade inställningar att ändra.</span><span class="sxs-lookup"><span data-stu-id="64da2-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="64da2-159">Om du expanderar **princip grupp/inställnings namn**visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="64da2-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="64da2-160">Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="64da2-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="64da2-161">Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting.</span><span class="sxs-lookup"><span data-stu-id="64da2-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="64da2-162">Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="64da2-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="64da2-163">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="64da2-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="64da2-164">I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="64da2-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="64da2-165">**Princip**: namnet på den berörda policyn som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="64da2-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="64da2-166">**Tillämpas på**: antalet användare som de berörda principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="64da2-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="64da2-167">**Aktuell konfiguration**: det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="64da2-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="64da2-168">**Senast ändrad**: det datum då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="64da2-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="64da2-169">**Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="64da2-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="64da2-170">Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.**</span><span class="sxs-lookup"><span data-stu-id="64da2-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="64da2-171">Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**.</span><span class="sxs-lookup"><span data-stu-id="64da2-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="64da2-172">Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.</span><span class="sxs-lookup"><span data-stu-id="64da2-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="64da2-173">Konfiguration av avvikelser och historik i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="64da2-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="64da2-174">Med den här fliken kan du spåra de ändringar du har gjort i dina anpassade säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="64da2-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="64da2-175">Följande information visas som standard:</span><span class="sxs-lookup"><span data-stu-id="64da2-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="64da2-176">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="64da2-176">**Last modified**</span></span>
- <span data-ttu-id="64da2-177">**Ändrat av**</span><span class="sxs-lookup"><span data-stu-id="64da2-177">**Modified by**</span></span>
- <span data-ttu-id="64da2-178">**Inställnings namn**</span><span class="sxs-lookup"><span data-stu-id="64da2-178">**Setting Name**</span></span>
- <span data-ttu-id="64da2-179">**Autentiseringsprincip**</span><span class="sxs-lookup"><span data-stu-id="64da2-179">**Policy**</span></span>
- <span data-ttu-id="64da2-180">**Typ**</span><span class="sxs-lookup"><span data-stu-id="64da2-180">**Type**</span></span>

<span data-ttu-id="64da2-181">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="64da2-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="64da2-182">I de utfällbara **filter** som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="64da2-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="64da2-183">**Start tid** och **slut tid** (datum)</span><span class="sxs-lookup"><span data-stu-id="64da2-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="64da2-184">**Standard skydd** eller **strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="64da2-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="64da2-185">Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="64da2-185">To export the results to a .csv file, click **Export**.</span></span>

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
