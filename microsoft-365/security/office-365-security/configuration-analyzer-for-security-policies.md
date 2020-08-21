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
description: Administratörer kan lära sig hur de använder konfigurations analys för att hitta och åtgärda säkerhets principer som innehåller inställningar som finns under standard säkerhets principer för förvalda skydd och begränsande skydd.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825779"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="ab58a-103">Konfigurations analys för skydds principer i EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ab58a-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="ab58a-104">De funktioner som beskrivs i det här avsnittet är i för hands version, är inte tillgängliga i alla organisationer och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="ab58a-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="ab58a-105">Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda någon av dina säkerhets principer som innehåller inställningar som är lägre än standard skydds-och strikta skydds inställningar för [säkerhets principer](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="ab58a-106">Följande typer av principer analyseras av konfigurations analys:</span><span class="sxs-lookup"><span data-stu-id="ab58a-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="ab58a-107">**Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="ab58a-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="ab58a-108">[Principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="ab58a-109">[Principer mot skadlig program vara](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="ab58a-110">[EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ab58a-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="ab58a-111">**Office 365 principer för avancerat skydd (ATP)**: Detta inkluderar organisationer med Microsoft 365 E5 eller Office 365 ATP-tilläggs abonnemang:</span><span class="sxs-lookup"><span data-stu-id="ab58a-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="ab58a-112">ATP anti-phishing-principer, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="ab58a-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="ab58a-113">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.</span><span class="sxs-lookup"><span data-stu-id="ab58a-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="ab58a-114">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="ab58a-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="ab58a-115">Avancerade nät fiske trösklar</span><span class="sxs-lookup"><span data-stu-id="ab58a-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="ab58a-116">[Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="ab58a-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="ab58a-117">[Principer för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="ab58a-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="ab58a-118">De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ab58a-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ab58a-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ab58a-120">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ab58a-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ab58a-121">Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="ab58a-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="ab58a-122">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab58a-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ab58a-123">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="ab58a-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="ab58a-124">För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="ab58a-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ab58a-125">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ab58a-126">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ab58a-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ab58a-127">Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="ab58a-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ab58a-128">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ab58a-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ab58a-129">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ab58a-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="ab58a-130">Använda Configuration Analyzer i Center för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="ab58a-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="ab58a-131">Gå till **Threat management** \> **Policy** \> **konfigurations analys**för Threat Management policy i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="ab58a-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="ab58a-133">Konfigurations analysen har två primära flikar:</span><span class="sxs-lookup"><span data-stu-id="ab58a-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="ab58a-134">**Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="ab58a-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="ab58a-135">I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.</span><span class="sxs-lookup"><span data-stu-id="ab58a-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="ab58a-136">**Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra de ändringar som du har gjort av dina principer baserat på resultaten av Configuration Analyzer över tiden.</span><span class="sxs-lookup"><span data-stu-id="ab58a-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="ab58a-137">Fliken inställning och rekommendationer i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="ab58a-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="ab58a-138">Som standard öppnas fliken i jämförelsen med standard skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="ab58a-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="ab58a-139">Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="ab58a-140">Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-140">To switch back, select **View Standard recommendations**.</span></span>

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="ab58a-142">Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och antalet inställningar i de principer som behöver förbättras.</span><span class="sxs-lookup"><span data-stu-id="ab58a-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="ab58a-143">Följande typer av principer är:</span><span class="sxs-lookup"><span data-stu-id="ab58a-143">The types of policies are:</span></span>

- <span data-ttu-id="ab58a-144">**Skydd mot skräp post**</span><span class="sxs-lookup"><span data-stu-id="ab58a-144">**Anti-spam**</span></span>
- <span data-ttu-id="ab58a-145">**Anti-nätfiske**</span><span class="sxs-lookup"><span data-stu-id="ab58a-145">**Anti-phishing**</span></span>
- <span data-ttu-id="ab58a-146">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="ab58a-146">**Anti-malware**</span></span>
- <span data-ttu-id="ab58a-147">**Säkra filer för ATP** (om ditt abonnemang inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="ab58a-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="ab58a-148">**Säkerhet för ATP** (om ditt abonnemang inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="ab58a-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="ab58a-149">I standardvyn är allting dolda.</span><span class="sxs-lookup"><span data-stu-id="ab58a-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="ab58a-150">Bredvid varje princip visas en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="ab58a-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="ab58a-151">Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="ab58a-151">You'll see the following information:</span></span>

- <span data-ttu-id="ab58a-152">**Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som den skydds profil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="ab58a-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="ab58a-153">**Gul**: ett litet antal inställningar i de befintliga principerna är inte lika säkert som den skydds profil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="ab58a-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="ab58a-154">**Rött**: ett stort antal inställningar i de befintliga principerna är inte lika säkert som den skydds profil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="ab58a-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="ab58a-155">Det här kan vara några få inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="ab58a-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="ab58a-156">För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="ab58a-157">I annat fall ser du antalet rekommenderade inställningar att ändra.</span><span class="sxs-lookup"><span data-stu-id="ab58a-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="ab58a-158">Om du expanderar **princip grupp/inställnings namn**visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ab58a-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="ab58a-159">Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="ab58a-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="ab58a-160">Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting.</span><span class="sxs-lookup"><span data-stu-id="ab58a-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="ab58a-161">Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="ab58a-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="ab58a-162">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="ab58a-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="ab58a-163">I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="ab58a-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="ab58a-164">**Princip**: namnet på den berörda policyn som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="ab58a-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="ab58a-165">**Tillämpas på**: antalet användare som de berörda principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ab58a-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="ab58a-166">**Aktuell konfiguration**: det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="ab58a-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="ab58a-167">**Senast ändrad**: det datum då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="ab58a-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="ab58a-168">**Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen.</span><span class="sxs-lookup"><span data-stu-id="ab58a-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="ab58a-169">Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.**</span><span class="sxs-lookup"><span data-stu-id="ab58a-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="ab58a-170">Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="ab58a-171">Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.</span><span class="sxs-lookup"><span data-stu-id="ab58a-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="ab58a-172">Konfiguration av avvikelser och historik i konfigurations analys</span><span class="sxs-lookup"><span data-stu-id="ab58a-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="ab58a-173">Med den här fliken kan du spåra de ändringar som du har gjort i dina anpassade säkerhets principer baserat på informationen i säkerhets analys.</span><span class="sxs-lookup"><span data-stu-id="ab58a-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="ab58a-174">Följande information visas som standard:</span><span class="sxs-lookup"><span data-stu-id="ab58a-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="ab58a-175">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="ab58a-175">**Last modified**</span></span>
- <span data-ttu-id="ab58a-176">**Ändrat av**</span><span class="sxs-lookup"><span data-stu-id="ab58a-176">**Modified by**</span></span>
- <span data-ttu-id="ab58a-177">**Inställnings namn**</span><span class="sxs-lookup"><span data-stu-id="ab58a-177">**Setting Name**</span></span>
- <span data-ttu-id="ab58a-178">**Autentiseringsprincip**</span><span class="sxs-lookup"><span data-stu-id="ab58a-178">**Policy**</span></span>
- <span data-ttu-id="ab58a-179">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ab58a-179">**Type**</span></span>

<span data-ttu-id="ab58a-180">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="ab58a-181">I de utfällbara **filter** som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="ab58a-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="ab58a-182">**Start tid** och **slut tid** (datum)</span><span class="sxs-lookup"><span data-stu-id="ab58a-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="ab58a-183">**Standard skydd** eller **strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="ab58a-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="ab58a-184">Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="ab58a-184">To export the results to a .csv file, click **Export**.</span></span>

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
