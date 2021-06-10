---
title: Ökad Microsoft 365 säkerheten för din Microsoft 365 för företagstestmiljö
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
description: Använd den här testlabbguiden för att Microsoft 365 ytterligare säkerhetsinställningar i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198357"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7e282-103">Ökad Microsoft 365 säkerheten för din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7e282-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7e282-104">*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="7e282-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7e282-105">Med hjälp av instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i Microsoft 365 för företagstestmiljö.</span><span class="sxs-lookup"><span data-stu-id="7e282-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7e282-107">Klicka [här](../downloads/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="7e282-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7e282-108">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7e282-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7e282-109">Om du bara vill konfigurera Microsoft 365 säkerhet på ett lätt sätt med minimikraven följer du anvisningarna i [Lightweight Base-konfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="7e282-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7e282-110">Om du vill konfigurera Microsoft 365 säkerhet i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7e282-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e282-111">Om du testar Microsoft 365 säkerheten krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="7e282-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7e282-112">Här finns ett alternativ så att du kan testa automatiska licenser och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="7e282-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="7e282-113">Fas 2: Konfigurera Microsoft 365 säkerhet</span><span class="sxs-lookup"><span data-stu-id="7e282-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="7e282-114">I den här fasen aktiverar du ökad Microsoft 365 säkerhet för din Microsoft 365 för företagstestmiljö.</span><span class="sxs-lookup"><span data-stu-id="7e282-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="7e282-115">Mer information och inställningar finns i Konfigurera [klientorganisationen för ökad säkerhet.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="7e282-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="7e282-116">Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering</span><span class="sxs-lookup"><span data-stu-id="7e282-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="7e282-117">Appar som inte stöder modern autentisering kan inte ha [identitets-](../security/office-365-security/microsoft-365-policies-configurations.md) och enhetsåtkomstkonfigurationer tillämpade på dem, vilket är en viktig del av att skydda din Microsoft 365-prenumeration och dess digitala tillgångar.</span><span class="sxs-lookup"><span data-stu-id="7e282-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="7e282-118">Gå till Microsoft 365 ( ) och logga in på din Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) testlabbprenumeration med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="7e282-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="7e282-119">Om du använder den lätta Microsoft 365 testmiljön loggar du in från den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="7e282-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="7e282-120">Om du använder den simulerade företagstestmiljön Microsoft 365 du använda [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella CLIENT1-datorn och logga sedan in från CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="7e282-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="7e282-121">Klicka på Microsoft 365 **under Administrationscenter** i det vänstra **navigeringsfönstret** på fliken för **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="7e282-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="7e282-122">På den nya **SharePoint fliken administrationscenter** klickar du på **Principer > Access-kontroll**.</span><span class="sxs-lookup"><span data-stu-id="7e282-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="7e282-123">Klicka **på Appar som inte stöder modern autentisering .** Välj Blockera **åtkomst** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7e282-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="7e282-124">Aktivera Defender för Office 365 för SharePoint, OneDrive för företag och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e282-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="7e282-125">Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar organisationen från att oavsiktligt dela skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="7e282-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="7e282-126">Gå till [Säkerhets- & Säkerhets- och](https://protection.office.com) efterlevnadscenter och logga in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="7e282-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="7e282-127">I det vänstra navigeringsfönstret, under **Hothantering,** klickar du **på Princip** och sedan på Valv **Bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7e282-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="7e282-128">Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="7e282-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="7e282-129">väljer **du Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="7e282-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="7e282-130">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7e282-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="7e282-131">Aktivera skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="7e282-131">Enable anti-malware</span></span>

<span data-ttu-id="7e282-132">Skadlig programvara består av virus och spionprogram.</span><span class="sxs-lookup"><span data-stu-id="7e282-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="7e282-133">Virus smittar andra program och data, och de sprids i din dator genom att söka efter program som de kan smitta.</span><span class="sxs-lookup"><span data-stu-id="7e282-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="7e282-134">Spionprogram används om skadlig programvara som samlar in personlig information, till exempel inloggningsuppgifter och personuppgifter, som sedan skickas tillbaka till den som skapar skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7e282-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="7e282-135">Microsoft 365 innehåller inbyggda funktioner för skadlig programvara och filtrering av skräppost som hjälper till att skydda inkommande och utgående meddelanden från skadlig programvara och skydda dig mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="7e282-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="7e282-136">Mer information finns i Skydd [mot skräppost & skydd mot skadlig programvara.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7e282-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="7e282-137">Så här säkerställer du att bearbetning med skadlig programvara utförs på filer med vanliga filtyper för bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7e282-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="7e282-138">Gå tillbaka till sidan Princip genom att klicka på **tillbakaknappen i** webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="7e282-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="7e282-139">Klicka **på Skydd mot skadlig programvara.**</span><span class="sxs-lookup"><span data-stu-id="7e282-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="7e282-140">Dubbelklicka på principen Standard **.**</span><span class="sxs-lookup"><span data-stu-id="7e282-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="7e282-141">I fönstret **princip mot skadlig programvara** klickar du på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="7e282-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="7e282-142">Under **Vanliga typer av bifogade filer** väljer du **På** och klickar sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="7e282-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="7e282-143">Fas 3: Undersöka säkerhetspanelen</span><span class="sxs-lookup"><span data-stu-id="7e282-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="7e282-144">Hothantering i Microsoft 365 kan hjälpa dig att styra och hantera mobil enhetsåtkomst till organisationens data, skydda organisationen från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost.</span><span class="sxs-lookup"><span data-stu-id="7e282-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="7e282-145">Du använder även hothantering för att skydda domänens rykte och för att avgöra om avsändare är skadliga förfalskningskonton från din domän.</span><span class="sxs-lookup"><span data-stu-id="7e282-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="7e282-146">Så här visar du säkerhetspanelen:</span><span class="sxs-lookup"><span data-stu-id="7e282-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="7e282-147">Om det behövs går du till [säkerhets- & säkerhets- och](https://protection.office.com) efterlevnadscentret och loggar in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="7e282-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="7e282-148">I det vänstra navigeringsfönstret, under **Hothantering, klickar** du på **Instrumentpanel**.</span><span class="sxs-lookup"><span data-stu-id="7e282-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="7e282-149">Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som finns.</span><span class="sxs-lookup"><span data-stu-id="7e282-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="7e282-150">Mer information finns i [Säkerhetsinstrumentpanel](../security/office-365-security/security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="7e282-150">For more information, see [Security Dashboard](../security/office-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="7e282-151">Fas 4: Undersöka Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="7e282-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="7e282-152">Microsoft Secure Score visar att din säkerhet ligger på ett nummer, vilket anger din aktuella nivå i förhållande till de funktioner som är tillgängliga i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="7e282-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="7e282-153">Du får också en lista över förbättringsåtgärder du kan vidta för att förbättra ditt resultat.</span><span class="sxs-lookup"><span data-stu-id="7e282-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="7e282-154">Skapa en ny flik i webbläsaren, gå till fliken [Microsoft 365 och](https://security.microsoft.com/)klicka sedan på **Säker poäng.**</span><span class="sxs-lookup"><span data-stu-id="7e282-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="7e282-155">På fliken **Översikt**  kan du notera ditt aktuella Secure Score och hur det står sig jämfört med det globala medelvärdet och prenumerationer med liknande antal licenser.</span><span class="sxs-lookup"><span data-stu-id="7e282-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="7e282-156">På fliken **Förbättringsåtgärder** läser du igenom listan med åtgärder du kan vidta för att höja poäng.</span><span class="sxs-lookup"><span data-stu-id="7e282-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="7e282-157">Mer information finns i [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="7e282-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e282-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7e282-158">Next steps</span></span>

<span data-ttu-id="7e282-159">Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="7e282-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e282-160">Se även</span><span class="sxs-lookup"><span data-stu-id="7e282-160">See also</span></span>

[<span data-ttu-id="7e282-161">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7e282-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7e282-162">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7e282-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7e282-163">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7e282-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)