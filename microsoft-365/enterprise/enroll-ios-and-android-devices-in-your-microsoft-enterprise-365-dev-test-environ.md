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
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487702"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="993e3-103">Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="993e3-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="993e3-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="993e3-105">I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för mobila enheter för iOS och Android-enheter i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="993e3-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="993e3-106">Att registrera iOS-och Android-enheter i test miljön omfattar tre faser:</span><span class="sxs-lookup"><span data-stu-id="993e3-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="993e3-107">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="993e3-108">Fas 2: registrera dina iOS-och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="993e3-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="993e3-109">Fas 3: hantera dina iOS-och Android-enheter från andra datorer</span><span class="sxs-lookup"><span data-stu-id="993e3-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="993e3-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="993e3-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="993e3-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="993e3-113">Om du vill registrera iOS-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="993e3-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="993e3-114">Om du vill registrera iOS-och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="993e3-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="993e3-115">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="993e3-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="993e3-116">Det finns här som ett alternativ så att du kan testa automatiserade licensierings-och grupp medlemskap och du kan experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="993e3-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="993e3-117">Fas 2: registrera dina iOS-och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="993e3-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="993e3-118">Börja med att använda anvisningarna i [Installera och logga in på appen företags Portal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune-företagsportalsappen för din test miljö.</span><span class="sxs-lookup"><span data-stu-id="993e3-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="993e3-119">Följ sedan anvisningarna i [Konfigurera åtkomst till dina företags resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.</span><span class="sxs-lookup"><span data-stu-id="993e3-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="993e3-120">Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.</span><span class="sxs-lookup"><span data-stu-id="993e3-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="993e3-121">Fas 3: hantera dina iOS-och Android-enheter från andra datorer</span><span class="sxs-lookup"><span data-stu-id="993e3-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="993e3-122">Microsoft Intune innehåller funktioner för återställning av både fjärrlåsning och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="993e3-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="993e3-123">Om någon förlorar sin enhet kan du fjärrans luta enheten.</span><span class="sxs-lookup"><span data-stu-id="993e3-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="993e3-124">Om någon glömmer sitt lösen ord kan du återställa det.</span><span class="sxs-lookup"><span data-stu-id="993e3-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="993e3-125">Så här låser du upp en iOS-eller Android-enhet:</span><span class="sxs-lookup"><span data-stu-id="993e3-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="993e3-126">Logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="993e3-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="993e3-127">I Azure-portalen anger du **Intune** i sökrutan och väljer **Intune**.</span><span class="sxs-lookup"><span data-stu-id="993e3-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="993e3-128">Klicka på **enheter > alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="993e3-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="993e3-129">I listan över enheter väljer du en iOS-eller Android-enhet och väljer sedan **fjärrlåsning** .</span><span class="sxs-lookup"><span data-stu-id="993e3-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="993e3-130">Så här återställer du lösen ordet från en annan dator:</span><span class="sxs-lookup"><span data-stu-id="993e3-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="993e3-131">Om det behövs loggar du in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="993e3-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="993e3-132">I Azure-portalen anger du **Intune** i sökrutan och väljer **Intune**.</span><span class="sxs-lookup"><span data-stu-id="993e3-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="993e3-133">Välj **enheter**till  >  **alla enheter**.</span><span class="sxs-lookup"><span data-stu-id="993e3-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="993e3-134">I listan över enheter som du hanterar väljer du en iOS-eller Android-enhet väljer du **... Mer**och välj sedan fjärråtgärd för att **ta bort en lösen ords** enhet.</span><span class="sxs-lookup"><span data-stu-id="993e3-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="993e3-135">Mer information finns i [tillgängliga enheter](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="993e3-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="993e3-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="993e3-136">Next step</span></span>

<span data-ttu-id="993e3-137">Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="993e3-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="993e3-138">Se även</span><span class="sxs-lookup"><span data-stu-id="993e3-138">See Also</span></span>

[<span data-ttu-id="993e3-139">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="993e3-140">Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="993e3-141">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="993e3-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
