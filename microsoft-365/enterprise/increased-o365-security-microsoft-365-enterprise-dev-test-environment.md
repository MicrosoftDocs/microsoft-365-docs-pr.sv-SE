---
title: Ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här testlabbet-guiden om du vill aktivera ytterligare microsoft 365-säkerhetsinställningar i Microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 166388de138f5268eb29b8a427bad61ec6ab7cda
ms.sourcegitcommit: 2c4dfce178695a99bbdf1468f072cc1f94f6915b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2020
ms.locfileid: "43058887"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d1342-103">Ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="d1342-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d1342-104">*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="d1342-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d1342-105">Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="d1342-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d1342-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="d1342-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d1342-108">Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1342-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d1342-109">Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d1342-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d1342-110">Om du vill konfigurera ökad Microsoft 365-säkerhet i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d1342-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1342-111">Testning av ökad Microsoft 365-säkerhet kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d1342-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d1342-112">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="d1342-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="d1342-113">Fas 2: Konfigurera ökad Microsoft 365-säkerhet</span><span class="sxs-lookup"><span data-stu-id="d1342-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="d1342-114">I den här fasen aktiverar du ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="d1342-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="d1342-115">Mer information och inställningar finns i [Konfigurera din Office 365-klient för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="d1342-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="d1342-116">Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering</span><span class="sxs-lookup"><span data-stu-id="d1342-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="d1342-117">Appar som inte stöder modern autentisering kan inte ha [konfigurationer för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) som tillämpas på dem, vilket är en viktig del för att skydda din Microsoft 365-prenumeration och dess digitala tillgångar.</span><span class="sxs-lookup"><span data-stu-id="d1342-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="d1342-118">Gå till Microsoft 365[https://portal.microsoft.com](https://portal.microsoft.com)admincenter ( ) och logga in på din Microsoft 365 testlabbprenumeration med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="d1342-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="d1342-119">Om du använder den lätta testmiljön för Microsoft 365 loggar du in från den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="d1342-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="d1342-120">Om du använder testmiljön för simulerade företag microsoft 365 använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella klientdatorn och loggar sedan in från CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="d1342-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="d1342-121">Klicka på **SharePoint**under **Administrationscenter** i det vänstra navigeringsfönstret på fliken **Microsoft 365 i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="d1342-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="d1342-122">Klicka på **Principer > Åtkomstkontroll**på fliken Nytt **administrationscenter i SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="d1342-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="d1342-123">Klicka på **Appar som inte stöder modern autentisering,** välj Blockera **åtkomst**och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d1342-123">Click **Apps that don’t support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="d1342-124">Aktivera avancerat skydd mot hot för SharePoint, OneDrive för företag och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1342-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="d1342-125">Office 365 Advanced Threat Protection (ATP) för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="d1342-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="d1342-126">Gå till [Office 365 Security & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="d1342-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="d1342-127">Klicka på **Princip**under **Hothantering**i det vänstra navigeringsfönstret och klicka sedan på **BETRODDa bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="d1342-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="d1342-128">Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d1342-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="d1342-129">välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d1342-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="d1342-130">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d1342-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="d1342-131">Aktivera anti-malware</span><span class="sxs-lookup"><span data-stu-id="d1342-131">Enable anti-malware</span></span>

<span data-ttu-id="d1342-132">Skadlig kod består av virus och spionprogram.</span><span class="sxs-lookup"><span data-stu-id="d1342-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="d1342-133">Virus infekterar andra program och data, och de sprids i hela datorn letar efter program att infektera.</span><span class="sxs-lookup"><span data-stu-id="d1342-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="d1342-134">Spionprogram refererar till skadlig kod som samlar in din personliga information, till exempel inloggningsinformation och personuppgifter, och skickar tillbaka den till den skadliga koden.</span><span class="sxs-lookup"><span data-stu-id="d1342-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="d1342-135">Microsoft 365 har inbyggda funktioner för filtrering av skadlig kod och skräppost som skyddar inkommande och utgående meddelanden från skadlig programvara och skyddar dig från skräppost.</span><span class="sxs-lookup"><span data-stu-id="d1342-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="d1342-136">Mer information finns i [Skydd mot skräppost & skydd mot skadlig kod i Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="d1342-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="d1342-137">Så här säkerställer du att bearbetning av skadlig kod utförs på filer med vanliga filtyper för bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="d1342-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="d1342-138">Klicka på bakåtknappen i webbläsaren för att komma tillbaka till **sidan Policy.**</span><span class="sxs-lookup"><span data-stu-id="d1342-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="d1342-139">Klicka på **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="d1342-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="d1342-140">Dubbelklicka på principen **Standard**.</span><span class="sxs-lookup"><span data-stu-id="d1342-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="d1342-141">Klicka på **Inställningar**i **policyfönstret mot skadlig kod** .</span><span class="sxs-lookup"><span data-stu-id="d1342-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="d1342-142">Under **filtret Vanliga typer av bifogade filer**väljer du **På**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d1342-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="d1342-143">Fas 3: Undersök säkerhetsinstrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="d1342-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="d1342-144">Office 365-hothantering kan hjälpa dig att kontrollera och hantera åtkomst till mobila enheter till organisationens data, skydda din organisation från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost.</span><span class="sxs-lookup"><span data-stu-id="d1342-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="d1342-145">Du använder också hothantering för att skydda domänens rykte och för att avgöra om avsändare förfalskar konton från domänen eller inte.</span><span class="sxs-lookup"><span data-stu-id="d1342-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="d1342-146">Så här ser du säkerhetsinstrumentpanelen:</span><span class="sxs-lookup"><span data-stu-id="d1342-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="d1342-147">Om det behövs går du till [Office 365 Security & Compliance Center](https://protection.office.com) och loggar in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="d1342-147">If needed, go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="d1342-148">Klicka på **Instrumentpanel**under **Hothantering**i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d1342-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="d1342-149">Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="d1342-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="d1342-150">Mer information finns i [Säkerhetspanelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="d1342-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="d1342-151">Fas 4: Undersök Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="d1342-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="d1342-152">Microsoft Secure Score visar din säkerhetsposition som ett nummer, vilket anger din nuvarande nivå i förhållande till de funktioner som är tillgängliga i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d1342-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="d1342-153">Det ger dig också en lista över förbättringsåtgärder du kan vidta för att förbättra din poäng.</span><span class="sxs-lookup"><span data-stu-id="d1342-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="d1342-154">Skapa en ny flik i webbläsaren och gå till [Säkerhetscentret för Microsoft 365](https://security.microsoft.com/)och klicka sedan på **Säker poäng**.</span><span class="sxs-lookup"><span data-stu-id="d1342-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="d1342-155">På fliken **Översikt** noterar du ditt nuvarande säkra resultat och hur det kan jämföras med det globala genomsnittet och prenumerationerna med ett liknande antal licenser.</span><span class="sxs-lookup"><span data-stu-id="d1342-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="d1342-156">På fliken **Förbättringsåtgärder** läser du igenom listan över åtgärder som du kan vidta för att öka din poäng.</span><span class="sxs-lookup"><span data-stu-id="d1342-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="d1342-157">Mer information finns i [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="d1342-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1342-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d1342-158">Next steps</span></span>

<span data-ttu-id="d1342-159">Se steget [Konfigurera ökad säkerhet för Microsoft 365](infoprotect-configure-increased-security-office-365.md) i **informationsskyddsfasen** för information och länkar för att konfigurera dessa inställningar i produktionen.</span><span class="sxs-lookup"><span data-stu-id="d1342-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="d1342-160">Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="d1342-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1342-161">Se även</span><span class="sxs-lookup"><span data-stu-id="d1342-161">See also</span></span>

[<span data-ttu-id="d1342-162">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1342-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d1342-163">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1342-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d1342-164">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="d1342-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
