---
title: Ökad Microsoft 365-säkerhet för test miljön av Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att aktivera ytterligare Microsoft 365-säkerhets inställningar din Microsoft 365 för företags test miljö.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847006"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fc771-103">Ökad Microsoft 365-säkerhet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fc771-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fc771-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="fc771-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fc771-105">Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i test miljön av Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="fc771-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="fc771-107">Klicka [här](../downloads/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="fc771-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fc771-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fc771-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fc771-109">Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="fc771-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fc771-110">Om du vill konfigurera utökad Microsoft 365-säkerhet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fc771-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc771-111">Testning av utökad Microsoft 365-säkerhet kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="fc771-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="fc771-112">Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="fc771-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="fc771-113">Fas 2: Konfigurera utökad Microsoft 365-säkerhet</span><span class="sxs-lookup"><span data-stu-id="fc771-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="fc771-114">I den här fasen aktiverar du ökad Microsoft 365-säkerhet för din test miljö för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc771-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="fc771-115">Mer information och inställningar finns i [Konfigurera din klient organisation för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="fc771-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="fc771-116">Konfigurera SharePoint Online för att blockera appar som inte stöder modern</span><span class="sxs-lookup"><span data-stu-id="fc771-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="fc771-117">Appar som inte stöder modern lösenordsautentisering kan inte ha [identitets-och enhets åtkomst inställningar](../security/office-365-security/microsoft-365-policies-configurations.md) kopplade till dem, vilket är ett viktigt element för att skydda ditt Microsoft 365-abonnemang och dess digitala till gångar.</span><span class="sxs-lookup"><span data-stu-id="fc771-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="fc771-118">Gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in på ditt microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="fc771-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="fc771-119">Om du använder test miljön för det lättviktiga Microsoft 365 loggar du in från din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="fc771-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="fc771-120">Om du använder den simulerade företags test miljön för Microsoft 365 kan du använda [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella KLIENT1 och sedan logga in från KLIENT1.</span><span class="sxs-lookup"><span data-stu-id="fc771-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="fc771-121">På fliken ny **administrations Center för Microsoft 365** går du till **administrations** Center i det vänstra navigerings fönstret och klickar på **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="fc771-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="fc771-122">Klicka på **principer > åtkomst kontroll** på fliken nytt **administrations Center för SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="fc771-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="fc771-123">Klicka på **appar som inte stöder modern auktorisering** , Välj **blockera åtkomst** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc771-123">Click **Apps that don't support modern authentication** , select **Block access** , and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="fc771-124">Aktivera Defender för Office 365 för SharePoint, OneDrive för företag och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc771-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="fc771-125">Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från oavsiktlig delning av skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="fc771-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="fc771-126">Gå till [säkerhets & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="fc771-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="fc771-127">I det vänstra navigerings fönstret under **Threat Management** klickar du på **princip** och sedan på **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="fc771-127">In the left navigation pane, under **Threat management** , click **Policy** , and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="fc771-128">Under **skydda filer i SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="fc771-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="fc771-129">Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="fc771-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="fc771-130">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc771-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="fc771-131">Aktivera skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="fc771-131">Enable anti-malware</span></span>

<span data-ttu-id="fc771-132">Skadlig program vara består av virus och spionprogram.</span><span class="sxs-lookup"><span data-stu-id="fc771-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="fc771-133">Virus angriper andra program och data och de fördelas på hela datorn och letar efter program att infektera.</span><span class="sxs-lookup"><span data-stu-id="fc771-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="fc771-134">Spionprogram refererar till skadlig program vara som samlar in dina person uppgifter, till exempel inloggnings information och person uppgifter, och skickar tillbaka den till författaren med skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="fc771-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="fc771-135">Microsoft 365 har inbyggda funktioner för skräp post och spam som hjälper dig att skydda inkommande och utgående meddelanden från skadlig program vara och hjälpa till att skydda dig från skräp post.</span><span class="sxs-lookup"><span data-stu-id="fc771-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="fc771-136">Mer information finns i [anti-spam & skydd mot skadlig program vara](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fc771-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="fc771-137">Så här kontrollerar du att behandling mot skadlig program vara utförs på filer med vanliga typer av bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="fc771-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="fc771-138">Klicka på knappen bakåt i webbläsaren för att gå tillbaka till **princip** sidan.</span><span class="sxs-lookup"><span data-stu-id="fc771-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="fc771-139">Klicka på **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="fc771-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="fc771-140">Dubbelklicka på den princip som heter **default**.</span><span class="sxs-lookup"><span data-stu-id="fc771-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="fc771-141">Klicka på **Inställningar** i **princip fönstret mot skadlig program vara** .</span><span class="sxs-lookup"><span data-stu-id="fc771-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="fc771-142">Välj **på** under **vanliga typer av bifogade filer** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc771-142">Under **Common Attachment Types filter** , select **On** , and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="fc771-143">Fas 3: granska säkerhets instrument panelen</span><span class="sxs-lookup"><span data-stu-id="fc771-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="fc771-144">Threat Management i Microsoft 365 hjälper dig att kontrol lera och hantera mobila enheters åtkomst till organisationens data, skydda din organisation från data förlust och hjälpa till att skydda inkommande och utgående meddelanden från skadlig program vara och skräp post.</span><span class="sxs-lookup"><span data-stu-id="fc771-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="fc771-145">Du använder också Threat Management för att skydda din domäns rykte och för att avgöra om avsändaren är skadligt falsk från din domän.</span><span class="sxs-lookup"><span data-stu-id="fc771-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="fc771-146">Så här visar du säkerhets instrument panelen:</span><span class="sxs-lookup"><span data-stu-id="fc771-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="fc771-147">Om det behövs går du till sidan [säkerhets & efterlevnad](https://protection.office.com) och loggar in med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="fc771-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="fc771-148">Klicka på **instrument panel** under **Threat Management** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="fc771-148">In the left navigation pane, under **Threat management** , click **Dashboard**.</span></span>

<span data-ttu-id="fc771-149">Ta en titt på alla kort på instrument panelen för att bekanta dig med informationen.</span><span class="sxs-lookup"><span data-stu-id="fc771-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="fc771-150">Mer information finns i [säkerhets instrument panelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="fc771-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="fc771-151">Fas 4: Undersök Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="fc771-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="fc771-152">Microsofts säkra poäng visar din Posture som ett nummer som visar din aktuella nivå i förhållande till de funktioner som är tillgängliga i ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="fc771-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="fc771-153">Du får också en lista över förbättrings åtgärder som du kan vidta för att förbättra din poäng.</span><span class="sxs-lookup"><span data-stu-id="fc771-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="fc771-154">Skapa en ny flik i webbläsaren och gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/)och klicka sedan på **säker Poäng**.</span><span class="sxs-lookup"><span data-stu-id="fc771-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="fc771-155">På fliken **Översikt**  ser du din nuvarande säkra poäng och hur den jämförs med det globala medelvärdet och abonnemanget med ett liknande antal licenser.</span><span class="sxs-lookup"><span data-stu-id="fc771-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="fc771-156">På fliken **förbättrings åtgärder** läser du igenom listan med åtgärder du kan vidta för att öka poängen.</span><span class="sxs-lookup"><span data-stu-id="fc771-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="fc771-157">Mer information finns i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="fc771-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc771-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fc771-158">Next steps</span></span>

<span data-ttu-id="fc771-159">Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="fc771-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc771-160">Se även</span><span class="sxs-lookup"><span data-stu-id="fc771-160">See also</span></span>

[<span data-ttu-id="fc771-161">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fc771-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fc771-162">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fc771-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fc771-163">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="fc771-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
