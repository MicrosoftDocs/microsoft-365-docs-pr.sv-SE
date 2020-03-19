---
title: Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 Enterprise
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
description: Använd den här testlabbguiden för att aktivera ytterligare Microsoft 365-säkerhetsinställningar för din Testmiljö för Microsoft 365 Enterprise.
ms.openlocfilehash: 465e9df40e8dfe9883a81d352eabff17151df8f3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807002"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="288f6-103">Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="288f6-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="288f6-104">*Den här testlabbguiden kan endast användas för Testmiljöer för Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="288f6-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="288f6-105">Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i din Testmiljö för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="288f6-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="288f6-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.</span><span class="sxs-lookup"><span data-stu-id="288f6-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="288f6-108">Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="288f6-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="288f6-109">Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight-baskonfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="288f6-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="288f6-110">Om du vill konfigurera ökad Microsoft 365-säkerhet i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="288f6-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="288f6-111">Testning av ökad Microsoft 365-säkerhet kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="288f6-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="288f6-112">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="288f6-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="288f6-113">Fas 2: Konfigurera ökad Microsoft 365-säkerhet</span><span class="sxs-lookup"><span data-stu-id="288f6-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="288f6-114">I den här fasen aktiverar du ökad Microsoft 365-säkerhet för din Microsoft 365 Enterprise-testmiljö.</span><span class="sxs-lookup"><span data-stu-id="288f6-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="288f6-115">Mer information och inställningar finns i [Konfigurera din Office 365-klient för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="288f6-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="288f6-116">Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering</span><span class="sxs-lookup"><span data-stu-id="288f6-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="288f6-117">Appar som inte stöder modern autentisering kan inte ha [identitets- och enhetsåtkomstkonfigurationer](microsoft-365-policies-configurations.md) som tillämpas på dem, vilket är en viktig del av att skydda din Microsoft 365-prenumeration och dess digitala tillgångar.</span><span class="sxs-lookup"><span data-stu-id="288f6-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="288f6-118">Gå till administrationscentret för[https://portal.microsoft.com](https://portal.microsoft.com)Microsoft 365 ( ) och logga in på din Microsoft 365-testlabbprenumeration med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="288f6-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="288f6-119">Om du använder den lätta testmiljön i Microsoft 365 loggar du in från den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="288f6-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="288f6-120">Om du använder den simulerade testmiljön för företaget Microsoft 365 använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella KLIENTEN FÖR KLIENT1 och loggar sedan in från CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="288f6-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="288f6-121">Klicka på **SharePoint**under **Administrationscenter** i det vänstra navigeringsfönstret på fliken nytt **administrationscenter i Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="288f6-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="288f6-122">Klicka på **Access-kontroll**på fliken Nytt **administrationscenter i SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="288f6-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="288f6-123">Klicka på **Appar som inte stöder modern autentisering,** välj Blockera **åtkomst**och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="288f6-123">Click **Apps that don’t support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="288f6-124">Aktivera avancerat hotskydd för SharePoint- och OneDrive för företag och Microsoft-team</span><span class="sxs-lookup"><span data-stu-id="288f6-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="288f6-125">Office 365 Advanced Threat Protection (ATP) för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="288f6-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="288f6-126">Gå till [Office 365 Security & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="288f6-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="288f6-127">Klicka på **Princip**under **Hothantering**i det vänstra navigeringsfönstret och klicka sedan på **AP-säkra bilagor**.</span><span class="sxs-lookup"><span data-stu-id="288f6-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="288f6-128">Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="288f6-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="288f6-129">välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="288f6-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="288f6-130">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="288f6-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="288f6-131">Aktivera skadlig kod</span><span class="sxs-lookup"><span data-stu-id="288f6-131">Enable anti-malware</span></span>

<span data-ttu-id="288f6-132">Skadlig kod består av virus och spionprogram.</span><span class="sxs-lookup"><span data-stu-id="288f6-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="288f6-133">Virus infekterar andra program och data, och de sprids över hela datorn letar efter program att infektera.</span><span class="sxs-lookup"><span data-stu-id="288f6-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="288f6-134">Spionprogram refererar till skadlig kod som samlar in din personliga information, till exempel inloggningsinformation och personuppgifter, och skickar tillbaka den till den skadliga koden.</span><span class="sxs-lookup"><span data-stu-id="288f6-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="288f6-135">Microsoft 365 har inbyggda funktioner för skadlig programvara och skräppostfiltrering som hjälper till att skydda inkommande och utgående meddelanden från skadlig programvara och skyddar dig från skräppost.</span><span class="sxs-lookup"><span data-stu-id="288f6-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="288f6-136">Mer information finns i [Skydd mot skräppost & skydd mot skadlig kod i Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="288f6-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="288f6-137">Så här kontrollerar du att bearbetning mot skadlig kod utförs på filer med vanliga filtyper för bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="288f6-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="288f6-138">Klicka på bakåtknappen i webbläsaren för att komma tillbaka till **sidan Policy.**</span><span class="sxs-lookup"><span data-stu-id="288f6-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="288f6-139">Klicka på **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="288f6-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="288f6-140">Dubbelklicka på principen **Standard**.</span><span class="sxs-lookup"><span data-stu-id="288f6-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="288f6-141">Klicka på **Inställningar**i **principfönstret Mot skadlig kod** .</span><span class="sxs-lookup"><span data-stu-id="288f6-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="288f6-142">Under **Filtret Vanliga bifogade filer**väljer du **På**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="288f6-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="288f6-143">Fas 3: Undersök säkerhetsinstrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="288f6-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="288f6-144">Hothantering i Office 365 kan hjälpa dig att kontrollera och hantera åtkomst till mobila enheter till organisationens data, skydda din organisation från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost.</span><span class="sxs-lookup"><span data-stu-id="288f6-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="288f6-145">Du använder också hothantering för att skydda domänens rykte och för att avgöra om avsändare är skadligt förfalska konton från din domän.</span><span class="sxs-lookup"><span data-stu-id="288f6-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="288f6-146">Så här visar du säkerhetsinstrumentpanelen:</span><span class="sxs-lookup"><span data-stu-id="288f6-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="288f6-147">Om det behövs går du till [Office 365 Security & Compliance Center](https://protection.office.com) och loggar in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="288f6-147">If needed, go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="288f6-148">Klicka på **Instrumentpanel**under **Hothantering**i det vänstra navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="288f6-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="288f6-149">Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="288f6-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="288f6-150">Mer information finns i [Säkerhetsinstrumentpanelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="288f6-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="288f6-151">Fas 4: Undersök Microsoftsecure-poäng</span><span class="sxs-lookup"><span data-stu-id="288f6-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="288f6-152">Microsoft Secure Score visar din säkerhetsposition som ett tal, vilket anger din aktuella nivå i förhållande till de funktioner som är tillgängliga i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="288f6-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="288f6-153">Det ger dig också en lista över förbättringsåtgärder du kan vidta för att förbättra din poäng.</span><span class="sxs-lookup"><span data-stu-id="288f6-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="288f6-154">Skapa en ny flik i webbläsaren och gå till [Säkerhetscentret för Microsoft 365](https://security.microsoft.com/)och klicka sedan på **Säker poäng**.</span><span class="sxs-lookup"><span data-stu-id="288f6-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="288f6-155">På fliken **Översikt** bör du notera din aktuella säkra poäng och hur det kan jämföras med det globala genomsnittet och prenumerationer med ett liknande antal licenser.</span><span class="sxs-lookup"><span data-stu-id="288f6-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="288f6-156">På fliken **Förbättringsåtgärder** läser du igenom listan över åtgärder som du kan vidta för att öka poängen.</span><span class="sxs-lookup"><span data-stu-id="288f6-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="288f6-157">Mer information finns i [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="288f6-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="288f6-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="288f6-158">Next steps</span></span>

<span data-ttu-id="288f6-159">Se [steget Konfigurera ökad säkerhet för Microsoft 365](infoprotect-configure-increased-security-office-365.md) i **informationsskyddsfasen** för information och länkar för att konfigurera dessa inställningar i produktionen.</span><span class="sxs-lookup"><span data-stu-id="288f6-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="288f6-160">Utforska ytterligare [funktioner för informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="288f6-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="288f6-161">Se även</span><span class="sxs-lookup"><span data-stu-id="288f6-161">See also</span></span>

[<span data-ttu-id="288f6-162">Labbguider för Microsoft 365 Enterprise Test</span><span class="sxs-lookup"><span data-stu-id="288f6-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="288f6-163">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="288f6-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="288f6-164">Dokumentation för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="288f6-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
