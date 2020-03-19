---
title: Azure AD Identity Protection för din Testmiljö för Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurera Azure AD Identity Protection och analysera de aktuella kontona i din Microsoft 365 Enterprise-testmiljö.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810371"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9d8c7-103">Azure AD Identity Protection för din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8c7-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9d8c7-104">*Den här testlabbguiden kan endast användas för Testmiljöer för Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9d8c7-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9d8c7-105">Med Azure Active Directory (Azure AD) Identity Protection kan du identifiera potentiella säkerhetsproblem som påverkar organisationens identiteter, konfigurera automatiska svar och undersöka incidenter.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="9d8c7-106">I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analysen av dina testmiljökonton.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="9d8c7-107">Det finns två faser för att konfigurera Azure AD Identity Protection i din Testmiljö för Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="9d8c7-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="9d8c7-108">Skapa testmiljön för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="9d8c7-109">Använd Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-109">Use Azure AD Identity Protection.</span></span>

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9d8c7-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9d8c7-112">Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8c7-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9d8c7-113">Om du bara vill testa Azure AD Identity Protection på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9d8c7-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9d8c7-114">Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9d8c7-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d8c7-115">Testning av Azure AD Identity Protection kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="9d8c7-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9d8c7-116">Den finns här som ett alternativ så att du kan testa Azure AD Identity Protection och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="9d8c7-117">Fas 2: Använd Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9d8c7-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="9d8c7-118">Öppna en privat instans av din webbläsare och [https://portal.azure.com](https://portal.azure.com) logga in på Azure-portalen med det globala administratörskontot för din Testmiljö för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="9d8c7-119">Skriv **identitetsskydd** i sökrutan i Azure-portalen och klicka sedan på **Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="9d8c7-120">I bladet **Identitetsskydd - Översikt** klickar du på var och en av rapporterna för att se vad de rapporterar.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="9d8c7-121">Klicka på **Användare i riskzonen som upptäckts aviseringar under** **Meddelande**.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="9d8c7-122">Välj **Medel**i fönstret **Användare med riskidentifierade aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="9d8c7-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="9d8c7-123">För **e-postmeddelanden skickas till följande användare**, klicka på **Ingår** och kontrollera att ditt globala administratörskonto finns i listan över valda medlemmar.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="9d8c7-124">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-124">Click **Save**.</span></span>

<span data-ttu-id="9d8c7-125">Klicka igenom de olika principerna under **Skydda** för att se hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="9d8c7-126">Om du skapar och aktiverar en princip kontrollerar du att den inte blockerar åtkomsten för ett alltför brett utrymme för villkor, eller så kanske du inte kan logga in, inte ens som global administratör.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="9d8c7-127">För ytterligare testning och experiment, se [Simulera riskhändelser](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="9d8c7-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="9d8c7-128">Se steget [Skydda mot autentiseringskomprometterande åtgärder i identitetsfasen](identity-secure-user-sign-ins.md#identity-ident-prot) för information och länkar för att distribuera Azure AD Identity Protection i produktionen.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="9d8c7-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9d8c7-129">Next step</span></span>

<span data-ttu-id="9d8c7-130">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="9d8c7-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d8c7-131">Se även</span><span class="sxs-lookup"><span data-stu-id="9d8c7-131">See also</span></span>

[<span data-ttu-id="9d8c7-132">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="9d8c7-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9d8c7-133">Labbguider för Microsoft 365 Enterprise Test</span><span class="sxs-lookup"><span data-stu-id="9d8c7-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9d8c7-134">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8c7-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9d8c7-135">Dokumentation för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8c7-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
