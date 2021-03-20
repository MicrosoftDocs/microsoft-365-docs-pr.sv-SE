---
title: Azure AD-identitetsskydd för din testmiljö för Microsoft 365 för företag
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
description: Konfigurera Azure AD Identity Protection och analysera de aktuella kontona i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905350"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0137d-103">Azure AD-identitetsskydd för din testmiljö för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="0137d-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0137d-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="0137d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="0137d-105">Du kan använda Azure Active Directory-identitetsskydd (Azure AD) för att upptäcka potentiella säkerhetsproblem som påverkar organisationens identiteter, konfigurera automatiska svar och undersöka incidenter.</span><span class="sxs-lookup"><span data-stu-id="0137d-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="0137d-106">I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analysen av testmiljökontona.</span><span class="sxs-lookup"><span data-stu-id="0137d-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="0137d-107">Att konfigurera Azure AD-identitetsskydd i testmiljön Microsoft 365 för företag omfattar två faser:</span><span class="sxs-lookup"><span data-stu-id="0137d-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="0137d-108">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="0137d-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="0137d-109">Fas 2: Använda Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="0137d-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0137d-111">En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.</span><span class="sxs-lookup"><span data-stu-id="0137d-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0137d-112">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="0137d-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0137d-113">Om du bara vill testa Azure AD Identity Protection på ett lätt sätt med minimikraven följer du anvisningarna i [Lightweight Base-konfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="0137d-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0137d-114">Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0137d-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0137d-115">Om du testar Azure AD Identity Protection krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="0137d-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0137d-116">Den finns här som ett alternativ så att du kan testa Azure AD Identity Protection och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="0137d-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="0137d-117">Fas 2: Använda Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="0137d-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="0137d-118">Öppna en privat instans av webbläsaren och logga in på Azure-portalen med det globala administratörskontot för [https://portal.azure.com](https://portal.azure.com) testmiljön Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="0137d-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="0137d-119">I Azure-portalen skriver du **identitetsskydd** i sökrutan och väljer sedan **Azure AD Identity Protection.**</span><span class="sxs-lookup"><span data-stu-id="0137d-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="0137d-120">I **bladet Identitetsskydd –** Översikt markerar du varje rapport för att se vad det är för rapportering.</span><span class="sxs-lookup"><span data-stu-id="0137d-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="0137d-121">Under **Meddela** väljer du **Användare med risk upptäckte aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="0137d-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="0137d-122">I fönstret **Användare med risk upptäckte aviseringar** väljer du **Medel**.</span><span class="sxs-lookup"><span data-stu-id="0137d-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="0137d-123">För **E-postmeddelanden skickas till följande användare** väljer du Ingår **och** kontrollerar att ditt globala administratörskonto finns med i listan med valda medlemmar.</span><span class="sxs-lookup"><span data-stu-id="0137d-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="0137d-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0137d-124">Select **Save**.</span></span>

<span data-ttu-id="0137d-125">Under **Skydda** väljer du olika metoder för att se hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="0137d-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="0137d-126">Om du skapar och aktiverar en princip ska du kontrollera att den inte blockerar åtkomsten för alla användare, eller att du kanske inte kan logga in.</span><span class="sxs-lookup"><span data-stu-id="0137d-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="0137d-127">Du kan förhindra detta genom att utesluta specifika användarkonton, till exempel globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="0137d-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="0137d-128">Mer information om hur du provar och experimenterar [finns i Flytta upp riskhändelser.](/azure/active-directory/active-directory-identityprotection-playbook)</span><span class="sxs-lookup"><span data-stu-id="0137d-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="0137d-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0137d-129">Next step</span></span>

<span data-ttu-id="0137d-130">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="0137d-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0137d-131">Se även</span><span class="sxs-lookup"><span data-stu-id="0137d-131">See also</span></span>

[<span data-ttu-id="0137d-132">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="0137d-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="0137d-133">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="0137d-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0137d-134">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="0137d-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0137d-135">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="0137d-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)