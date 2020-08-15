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
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694996"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d8056-103">Azure AD Identity Protection för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d8056-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d8056-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="d8056-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d8056-105">Med identitets skydd i Azure Active Directory (Azure AD) kan du upptäcka potentiella säkerhets problem som påverkar organisationens identitet, konfigurera automatiserade svar och undersöka incidenter.</span><span class="sxs-lookup"><span data-stu-id="d8056-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="d8056-106">I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analyser av test miljö kontona.</span><span class="sxs-lookup"><span data-stu-id="d8056-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="d8056-107">Det finns två faser för konfiguration av Azure AD Identity-skydd i test miljön för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="d8056-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="d8056-108">Skapa test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="d8056-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="d8056-109">Använd Azure AD Identity Protection.</span><span class="sxs-lookup"><span data-stu-id="d8056-109">Use Azure AD Identity Protection.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d8056-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="d8056-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d8056-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d8056-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d8056-113">Om du bara vill testa Azure AD Identity-skyddet på ett billigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d8056-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d8056-114">Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d8056-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8056-115">Testning av Azure AD Identity Protection kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d8056-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d8056-116">Det finns ett alternativ som gör att du kan testa Azure AD Identity-skyddet och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="d8056-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="d8056-117">Fas 2: använda Azure AD Identity-skydd</span><span class="sxs-lookup"><span data-stu-id="d8056-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="d8056-118">Öppna en privat instans av webbläsaren och logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med det globala administratörs kontot i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="d8056-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="d8056-119">I Azure-portalen skriver du **identitets skydd** i sökrutan och klickar sedan på **Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="d8056-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="d8056-120">I bladet **identitets skydd-översikt** klickar du på var och en av rapporterna för att se vad de rapporterar.</span><span class="sxs-lookup"><span data-stu-id="d8056-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="d8056-121">Under **meddela**klickar **du på användare med risk varningar**.</span><span class="sxs-lookup"><span data-stu-id="d8056-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="d8056-122">Välj **medium**i fönstret **användare vid risk identifiering** .</span><span class="sxs-lookup"><span data-stu-id="d8056-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="d8056-123">För **e-postmeddelanden skickas till följande användare**: Klicka på **inkluderat** och kontrol lera att ditt globala administratörs konto finns med i listan med valda medlemmar.</span><span class="sxs-lookup"><span data-stu-id="d8056-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="d8056-124">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8056-124">Click **Save**.</span></span>

<span data-ttu-id="d8056-125">Klicka igenom de olika principerna under **skydda** för att se hur du konfigurerar dem.</span><span class="sxs-lookup"><span data-stu-id="d8056-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="d8056-126">Om du skapar och aktiverar en princip bör du kontrol lera att den inte blockerar åtkomsten för ett alltför långt giltighets område, eller så kanske du inte kan logga in, även som den globala administratören.</span><span class="sxs-lookup"><span data-stu-id="d8056-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="d8056-127">Mer information om testning och experimentering finns i [simulera risk händelser](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="d8056-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="d8056-128">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d8056-128">Next step</span></span>

<span data-ttu-id="d8056-129">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="d8056-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8056-130">Se även</span><span class="sxs-lookup"><span data-stu-id="d8056-130">See also</span></span>

[<span data-ttu-id="d8056-131">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="d8056-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d8056-132">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d8056-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d8056-133">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d8056-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d8056-134">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="d8056-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
