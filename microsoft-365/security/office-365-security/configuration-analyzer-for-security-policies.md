---
title: Konfigurationsanalysator för säkerhetsprinciper
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du använder konfigurationsanalysatorn för att hitta och åtgärda säkerhetsprinciper som innehåller inställningar som ligger under standardskydd och strikt skydd förinställda säkerhetsprinciper.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533995"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="cbb19-103">Konfigurationsanalysator för skyddsprinciper i EOP och Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="cbb19-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="cbb19-104">Funktionerna som beskrivs i det här avsnittet är i förhandsversion, är inte tillgängliga i alla organisationer och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="cbb19-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="cbb19-105">Konfigurationsanalysator i Security & Compliance Center är en central plats för att hitta och åtgärda någon av dina säkerhetsprinciper som innehåller inställningar som ligger under profilinställningarna för standardskydd och strikt skydd i [förinställda säkerhetsprinciper](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="cbb19-106">Följande typer av principer analyseras av konfigurationsanalysatorn:</span><span class="sxs-lookup"><span data-stu-id="cbb19-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="cbb19-107">**EOP-principer (Exchange Online Protection):** Detta inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:</span><span class="sxs-lookup"><span data-stu-id="cbb19-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="cbb19-108">[Anti-spam politik](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="cbb19-109">[Anti-malware politik](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="cbb19-110">[EOP:s policyer för phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="cbb19-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="cbb19-111">**Office 365 Advanced Threat Protection (ATP)-principer**: Detta inkluderar organisationer med Microsoft 365 E5- eller Office 365 ATP-tilläggsprenumerationer:</span><span class="sxs-lookup"><span data-stu-id="cbb19-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="cbb19-112">ATP:s policyer för phishing, som omfattar:</span><span class="sxs-lookup"><span data-stu-id="cbb19-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="cbb19-113">Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP:s policyer för nätfiske.</span><span class="sxs-lookup"><span data-stu-id="cbb19-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="cbb19-114">Inställningar för personifiering</span><span class="sxs-lookup"><span data-stu-id="cbb19-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="cbb19-115">Avancerade tröskelvärden för nätfiske</span><span class="sxs-lookup"><span data-stu-id="cbb19-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="cbb19-116">[Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="cbb19-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="cbb19-117">[Principer för säkra bilagor](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="cbb19-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="cbb19-118">Principinställningsvärdena **Standard** och **Strikt** som används som baslinjer beskrivs i [Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cbb19-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cbb19-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cbb19-120">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cbb19-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cbb19-121">Om du vill gå direkt till sidan **Konfigurationsanalysator** använder du <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="cbb19-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="cbb19-122">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cbb19-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cbb19-123">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="cbb19-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="cbb19-124">Om du vill använda konfigurationsanalysatorn **och** göra uppdateringar av säkerhetsprinciper måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="cbb19-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="cbb19-125">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="cbb19-126">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="cbb19-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="cbb19-127">För skrivskyddad åtkomst till konfigurationsanalysatorn måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="cbb19-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="cbb19-128">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cbb19-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="cbb19-129">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="cbb19-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="cbb19-130">Använda konfigurationsanalysatorn i Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cbb19-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="cbb19-131">Gå till analysator för **&-efterlevnadsprincip** i Security & Compliance Center \> **Policy** \> **Configuration analyzer**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widgeten Konfigurationsanalys på sidan Policy för hothantering \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="cbb19-133">Konfigurationsanalysatorn har två huvudflikar:</span><span class="sxs-lookup"><span data-stu-id="cbb19-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="cbb19-134">**Inställningar och rekommendationer**: Du väljer Standard eller Strikt och jämför dessa inställningar med dina befintliga säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="cbb19-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="cbb19-135">I resultatet kan du justera värdena för dina inställningar för att få dem upp till samma nivå som Standard eller Strikt.</span><span class="sxs-lookup"><span data-stu-id="cbb19-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="cbb19-136">**Konfigurationsdriftanalys och historik**: Med den här vyn kan du spåra de ändringar som du har gjort i dina principer baserat på resultatet av konfigurationsanalysatorn över tid.</span><span class="sxs-lookup"><span data-stu-id="cbb19-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="cbb19-137">Fliken Inställning och rekommendationer i konfigurationsanalysatorn</span><span class="sxs-lookup"><span data-stu-id="cbb19-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="cbb19-138">Som standard öppnas fliken i jämförelsen med standardskyddsprofilen.</span><span class="sxs-lookup"><span data-stu-id="cbb19-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="cbb19-139">Du kan växla till jämförelsen av profilen Strikt skydd genom att klicka på **Visa strikta rekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="cbb19-140">Om du vill växla tillbaka väljer du **Visa standardrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-140">To switch back, select **View Standard recommendations**.</span></span>

![Inställnings- och rekommendationer visas i konfigurationsanalysatorn](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="cbb19-142">Som standard innehåller kolumnen **Principgrupp/inställningsnamn** en komprimerad vy över de olika typerna av säkerhetspoliser och antalet inställningar i de principer som behöver förbättras (om sådana finns).</span><span class="sxs-lookup"><span data-stu-id="cbb19-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="cbb19-143">De olika typerna av principer är:</span><span class="sxs-lookup"><span data-stu-id="cbb19-143">The types of policies are:</span></span>

- <span data-ttu-id="cbb19-144">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="cbb19-144">**Anti-spam**</span></span>
- <span data-ttu-id="cbb19-145">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="cbb19-145">**Anti-phishing**</span></span>
- <span data-ttu-id="cbb19-146">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="cbb19-146">**Anti-malware**</span></span>
- <span data-ttu-id="cbb19-147">**ATP Säkra bilagor** (om din prenumeration inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="cbb19-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="cbb19-148">**ATP Safe Links** (om din prenumeration inkluderar ATP)</span><span class="sxs-lookup"><span data-stu-id="cbb19-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="cbb19-149">I standardvyn är allt komprimerat.</span><span class="sxs-lookup"><span data-stu-id="cbb19-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="cbb19-150">Bredvid varje princip visas en sammanfattning av jämförelseresultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för profilerna Standard eller Strikt skydd (som du inte kan ändra).</span><span class="sxs-lookup"><span data-stu-id="cbb19-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="cbb19-151">Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="cbb19-151">You'll see the following information:</span></span>

- <span data-ttu-id="cbb19-152">**Grön**: Alla inställningar i alla befintliga principer är minst lika säkra som den skyddsprofil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="cbb19-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="cbb19-153">**Amber**: Ett litet antal inställningar i de befintliga principerna är inte lika säkra som den skyddsprofil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="cbb19-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="cbb19-154">**Röd**: Ett stort antal inställningar i de befintliga principerna är inte lika säkra som den skyddsprofil som du jämför med.</span><span class="sxs-lookup"><span data-stu-id="cbb19-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="cbb19-155">Detta kan vara några inställningar i många principer eller många inställningar i en princip.</span><span class="sxs-lookup"><span data-stu-id="cbb19-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="cbb19-156">För positiva jämförelser ser du texten: **Alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationerna**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="cbb19-157">Annars visas antalet rekommenderade inställningar som ska ändras.</span><span class="sxs-lookup"><span data-stu-id="cbb19-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="cbb19-158">Om du expanderar **principgrupp/inställningsnamn**visas alla principer och associerade inställningar i varje specifik princip som kräver uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="cbb19-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="cbb19-159">Du kan också expandera en viss typ av policy (till exempel **Anti-spam)** för att bara se de inställningarna i de typer av principer som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="cbb19-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="cbb19-160">Om jämförelsen inte har några rekommendationer för förbättring (grön), expanderande politiken visar ingenting.</span><span class="sxs-lookup"><span data-stu-id="cbb19-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="cbb19-161">Om det finns ett antal rekommendationer för förbättringar (gult eller rött), de inställningar som kräver uppmärksamhet avslöjas, och motsvarande information avslöjas i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="cbb19-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="cbb19-162">Namnet på den inställning som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="cbb19-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="cbb19-163">I föregående skärmbild är det till exempel **tröskelvärdet för massutskick av e-post** i en policy mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="cbb19-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="cbb19-164">**Princip**: Namnet på den berörda principen som innehåller inställningen.</span><span class="sxs-lookup"><span data-stu-id="cbb19-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="cbb19-165">**Används på**: Antalet användare som de berörda principerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="cbb19-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="cbb19-166">**Aktuell konfiguration**: Det aktuella värdet för inställningen.</span><span class="sxs-lookup"><span data-stu-id="cbb19-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="cbb19-167">**Senast ändrad**: Det datum då principen senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="cbb19-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="cbb19-168">**Rekommendationer**: Värdet av inställningen i profilen Standard eller Strikt skydd.</span><span class="sxs-lookup"><span data-stu-id="cbb19-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="cbb19-169">Om du vill ändra värdet för inställningen i principen så att den matchar det rekommenderade värdet i skyddsprofilen klickar du på **Anta**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="cbb19-170">Om ändringen lyckas visas meddelandet: Rekommendationer har **antagits**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="cbb19-171">Klicka på **Uppdatera** om du vill se det minskade antalet rekommendationer och borttagningen av den specifika inställningen/principraden från resultaten.</span><span class="sxs-lookup"><span data-stu-id="cbb19-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="cbb19-172">Fliken Analys och historik på fliken Konfigurationsdrift i konfigurationsanalysatorn</span><span class="sxs-lookup"><span data-stu-id="cbb19-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="cbb19-173">På den här fliken kan du spåra de ändringar som du har gjort i dina anpassade säkerhetsprinciper baserat på informationen i säkerhetsanalysatorn.</span><span class="sxs-lookup"><span data-stu-id="cbb19-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="cbb19-174">Som standard visas följande information:</span><span class="sxs-lookup"><span data-stu-id="cbb19-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="cbb19-175">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="cbb19-175">**Last modified**</span></span>
- <span data-ttu-id="cbb19-176">**Ändrad av**</span><span class="sxs-lookup"><span data-stu-id="cbb19-176">**Modified by**</span></span>
- <span data-ttu-id="cbb19-177">**Ange namn**</span><span class="sxs-lookup"><span data-stu-id="cbb19-177">**Setting Name**</span></span>
- <span data-ttu-id="cbb19-178">**Politik**</span><span class="sxs-lookup"><span data-stu-id="cbb19-178">**Policy**</span></span>
- <span data-ttu-id="cbb19-179">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cbb19-179">**Type**</span></span>

<span data-ttu-id="cbb19-180">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cbb19-181">I det utfällbara **filter** som visas kan du välja bland följande filter:</span><span class="sxs-lookup"><span data-stu-id="cbb19-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="cbb19-182">**Starttid** och **sluttid** (datum)</span><span class="sxs-lookup"><span data-stu-id="cbb19-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="cbb19-183">**Standardskydd** eller **Strikt skydd**</span><span class="sxs-lookup"><span data-stu-id="cbb19-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="cbb19-184">Om du vill exportera resultaten till en CSV-fil klickar du på **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="cbb19-184">To export the results to a .csv file, click **Export**.</span></span>

![Konfigurationsanalys och historikvy i konfigurationsanalysatorn](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
