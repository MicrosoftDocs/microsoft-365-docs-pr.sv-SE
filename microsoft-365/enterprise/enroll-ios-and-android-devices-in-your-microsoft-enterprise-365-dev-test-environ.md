---
title: Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise
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
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Använd den här testlabbet-guiden för att registrera enheter i microsoft 365-testmiljön och fjärrhantera dem.
ms.openlocfilehash: ae6ff9e704fc239638b5951a95ae23c45e85b7be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807000"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="83905-103">Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83905-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="83905-104">*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="83905-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="83905-105">Genom att följa instruktionerna i den här artikeln kan du registrera och testa grundläggande funktioner för hantering av mobila enheter för iOS- och Android-enheter i microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="83905-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="83905-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.</span><span class="sxs-lookup"><span data-stu-id="83905-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="83905-108">Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83905-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="83905-109">Om du bara vill registrera iOS- och Android-enheter på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="83905-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="83905-110">Om du vill registrera iOS- och [Android-enheter](pass-through-auth-m365-ent-test-environment.md)i ett simulerat företag följer du instruktionerna i Direktautentisering .</span><span class="sxs-lookup"><span data-stu-id="83905-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="83905-111">Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="83905-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="83905-112">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="83905-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="83905-113">Fas 2: Registrera dina iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="83905-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="83905-114">Använd först instruktionerna i [Installera och logga in på företagsportalappen](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune Company Portal-appen för din testmiljö.</span><span class="sxs-lookup"><span data-stu-id="83905-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="83905-115">Använd sedan instruktionerna i [Konfigurera åtkomst till företagets resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.</span><span class="sxs-lookup"><span data-stu-id="83905-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="83905-116">Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.</span><span class="sxs-lookup"><span data-stu-id="83905-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="83905-117">Fas 3: Fjärrhantera dina iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="83905-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="83905-118">Microsoft Intune tillhandahåller både fjärrlås och återställning av lösenkod.</span><span class="sxs-lookup"><span data-stu-id="83905-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="83905-119">Om någon förlorar sin enhet kan du fjärrlåsa enheten.</span><span class="sxs-lookup"><span data-stu-id="83905-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="83905-120">Om någon glömmer sin lösenkod kan du återställa den på distans.</span><span class="sxs-lookup"><span data-stu-id="83905-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="83905-121">Så här låser du en iOS- eller Android-enhet på distans:</span><span class="sxs-lookup"><span data-stu-id="83905-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="83905-122">Logga in på Azure-portalen med [https://portal.azure.com](https://portal.azure.com) autentiseringsuppgifterna för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="83905-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="83905-123">Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="83905-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="83905-124">Klicka på **Enheter > Alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="83905-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="83905-125">Klicka på en iOS- eller Android-enhet i listan över enheter och klicka sedan på åtgärden **Fjärrlås.**</span><span class="sxs-lookup"><span data-stu-id="83905-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="83905-126">Så här återställer du lösenkoden på distans:</span><span class="sxs-lookup"><span data-stu-id="83905-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="83905-127">Om det behövs loggar du [https://portal.azure.com](https://portal.azure.com) in på Azure-portalen med autentiseringsuppgifterna för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="83905-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="83905-128">Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="83905-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="83905-129">Klicka på **Enheter > Alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="83905-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="83905-130">Från listan över enheter du hanterar, klicka på en iOS eller Android-enhet, och välj **... Mer**.</span><span class="sxs-lookup"><span data-stu-id="83905-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="83905-131">Välj sedan fjärråtgärden **Ta bort lösenkodsenhet.**</span><span class="sxs-lookup"><span data-stu-id="83905-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="83905-132">Ytterligare experiment finns i [Tillgängliga enhetsåtgärder](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="83905-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="83905-133">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="83905-133">Next step</span></span>

<span data-ttu-id="83905-134">Utforska ytterligare funktioner och funktioner för hantering av [mobila](m365-enterprise-test-lab-guides.md#mobile-device-management) enheter i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="83905-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="83905-135">Se även</span><span class="sxs-lookup"><span data-stu-id="83905-135">See Also</span></span>

[<span data-ttu-id="83905-136">Testlaboratorikguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83905-136">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="83905-137">Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="83905-137">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="83905-138">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83905-138">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

