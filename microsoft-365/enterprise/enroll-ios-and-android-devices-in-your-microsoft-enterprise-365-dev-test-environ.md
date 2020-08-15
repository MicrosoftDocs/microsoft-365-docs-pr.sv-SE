---
title: Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att registrera enheter i test miljön för Microsoft 365 och fjärrhantera dem.
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686016"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="94e56-103">Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94e56-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="94e56-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="94e56-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="94e56-105">Genom att följa anvisningarna i den här artikeln kan du registrera dig för och testa grundläggande funktioner för mobila enheter för iOS och Android-enheter i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="94e56-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="94e56-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="94e56-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="94e56-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94e56-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="94e56-109">Om du bara vill registrera iOS-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="94e56-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="94e56-110">Om du vill registrera iOS-och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="94e56-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="94e56-111">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="94e56-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="94e56-112">Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="94e56-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="94e56-113">Fas 2: registrera dina iOS-och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="94e56-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="94e56-114">Börja med att använda anvisningarna i [Installera och logga in på appen företags Portal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune-företagsportalsappen för din test miljö.</span><span class="sxs-lookup"><span data-stu-id="94e56-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="94e56-115">Följ sedan anvisningarna i [Konfigurera åtkomst till dina företags resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.</span><span class="sxs-lookup"><span data-stu-id="94e56-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="94e56-116">Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.</span><span class="sxs-lookup"><span data-stu-id="94e56-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="94e56-117">Fas 3: hantera dina iOS-och Android-enheter från andra datorer</span><span class="sxs-lookup"><span data-stu-id="94e56-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="94e56-118">Microsoft Intune innehåller funktioner för återställning av både fjärrlåsning och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="94e56-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="94e56-119">Om någon förlorar sin enhet kan du låsa den från en annan enhet.</span><span class="sxs-lookup"><span data-stu-id="94e56-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="94e56-120">Om någon glömmer sitt lösen ord kan du återställa det från en annan dator.</span><span class="sxs-lookup"><span data-stu-id="94e56-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="94e56-121">Så här låser du en iOS-eller Android-enhet från fjärrdator:</span><span class="sxs-lookup"><span data-stu-id="94e56-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="94e56-122">Logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="94e56-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="94e56-123">På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="94e56-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="94e56-124">Klicka på **enheter > alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="94e56-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="94e56-125">Klicka på en iOS-eller Android-enhet i listan med enheter och klicka sedan på **Remote lock** -åtgärden.</span><span class="sxs-lookup"><span data-stu-id="94e56-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="94e56-126">Så här återställer du lösen ordet från fjärrdator:</span><span class="sxs-lookup"><span data-stu-id="94e56-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="94e56-127">Om det behövs loggar du in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="94e56-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="94e56-128">På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="94e56-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="94e56-129">Klicka på **enheter > alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="94e56-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="94e56-130">I listan med enheter som du hanterar klickar du på en iOS-eller Android-enhet och väljer **... Mer**.</span><span class="sxs-lookup"><span data-stu-id="94e56-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="94e56-131">Välj sedan fjärråtgärd för att **ta bort en lösen ords** enhet.</span><span class="sxs-lookup"><span data-stu-id="94e56-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="94e56-132">Mer information finns i [tillgängliga enheter](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="94e56-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="94e56-133">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="94e56-133">Next step</span></span>

<span data-ttu-id="94e56-134">Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="94e56-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="94e56-135">Se även</span><span class="sxs-lookup"><span data-stu-id="94e56-135">See Also</span></span>

[<span data-ttu-id="94e56-136">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94e56-136">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="94e56-137">Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94e56-137">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="94e56-138">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94e56-138">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

