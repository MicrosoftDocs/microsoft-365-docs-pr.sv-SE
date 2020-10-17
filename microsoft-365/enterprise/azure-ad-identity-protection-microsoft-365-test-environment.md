---
title: Azure AD Identity Protection för test miljön av Microsoft 365 för företag
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
description: Konfigurera Azure AD Identity Protection och analysera aktuella konton i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487714"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="35b60-103">Azure AD Identity Protection för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35b60-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="35b60-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="35b60-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="35b60-105">Du kan använda identitets skydd i Azure Active Directory (Azure AD) för att upptäcka potentiella säkerhets problem som påverkar organisationens identitet, konfigurera automatiserade svar och undersöka incidenter.</span><span class="sxs-lookup"><span data-stu-id="35b60-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="35b60-106">I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analyser av test miljö kontona.</span><span class="sxs-lookup"><span data-stu-id="35b60-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="35b60-107">Konfiguration av Azure AD Identity-skydd i test miljön av Microsoft 365 för företag inbegriper två faser:</span><span class="sxs-lookup"><span data-stu-id="35b60-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="35b60-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35b60-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="35b60-109">Fas 2: använda Azure AD Identity-skydd</span><span class="sxs-lookup"><span data-stu-id="35b60-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="35b60-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="35b60-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="35b60-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35b60-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="35b60-113">Om du bara vill testa Azure AD Identity Protection på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="35b60-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="35b60-114">Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="35b60-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35b60-115">Testning av Azure AD Identity Protection kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="35b60-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="35b60-116">Det finns ett alternativ som gör att du kan testa Azure AD Identity-skyddet och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="35b60-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="35b60-117">Fas 2: använda Azure AD Identity-skydd</span><span class="sxs-lookup"><span data-stu-id="35b60-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="35b60-118">Öppna en privat instans av webbläsaren och logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med det globala administratörs kontot i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="35b60-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="35b60-119">I Azure-portalen skriver du **identitets skydd** i sökrutan och väljer sedan **Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="35b60-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="35b60-120">I blad med **identitets skydd-översikt** väljer du varje rapport för att se vad den rapporterar.</span><span class="sxs-lookup"><span data-stu-id="35b60-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="35b60-121">Under **meddela**väljer **du användare vid risk identifiering**.</span><span class="sxs-lookup"><span data-stu-id="35b60-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="35b60-122">Välj **medium**i fönstret **användare vid risk identifiering** .</span><span class="sxs-lookup"><span data-stu-id="35b60-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="35b60-123">För **e-postmeddelanden skickas till följande användare**: Välj **inkluderat** och kontrol lera att ditt globala administratörs konto finns med i listan med valda medlemmar.</span><span class="sxs-lookup"><span data-stu-id="35b60-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="35b60-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="35b60-124">Select **Save**.</span></span>

<span data-ttu-id="35b60-125">Under **skydda**väljer du olika principer för att se hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="35b60-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="35b60-126">Om du skapar och aktiverar en princip kontrollerar du att den inte blockerar åtkomst för alla användare, eller att du kanske inte kan logga in.</span><span class="sxs-lookup"><span data-stu-id="35b60-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="35b60-127">För att förhindra detta kan du utesluta specifika användar konton, till exempel globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="35b60-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="35b60-128">Mer information om testning och experimentering finns i [simulera risk händelser](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="35b60-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="35b60-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="35b60-129">Next step</span></span>

<span data-ttu-id="35b60-130">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="35b60-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="35b60-131">Se även</span><span class="sxs-lookup"><span data-stu-id="35b60-131">See also</span></span>

[<span data-ttu-id="35b60-132">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="35b60-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="35b60-133">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35b60-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35b60-134">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35b60-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="35b60-135">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="35b60-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
