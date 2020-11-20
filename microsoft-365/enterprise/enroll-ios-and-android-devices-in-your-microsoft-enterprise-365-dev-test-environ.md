---
title: Registrera iOS/iPad och Android-enheter i test miljön för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Använd den här test laboratorie guiden för att registrera enheter i test miljön för Microsoft 365 och fjärrhantera dem.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367089"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="cc6f2-103">Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="cc6f2-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="cc6f2-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cc6f2-105">I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för hantering av mobila enheter för iOS/iPad och Android-enheter i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="cc6f2-106">Att registrera iOS/iPad och Android-enheter i test miljön omfattar tre faser:</span><span class="sxs-lookup"><span data-stu-id="cc6f2-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="cc6f2-107">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="cc6f2-108">Fas 2: registrera dina iOS/iPad-och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="cc6f2-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="cc6f2-109">Fas 3: hantera dina iOS/iPad-och Android-enheter från andra datorer</span><span class="sxs-lookup"><span data-stu-id="cc6f2-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="cc6f2-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="cc6f2-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="cc6f2-113">Om du vill registrera iOS/iPad-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cc6f2-114">Om du vill registrera iOS/iPad och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc6f2-115">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cc6f2-116">Det finns här som ett alternativ så att du kan testa automatiserade licensierings-och grupp medlemskap och du kan experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="cc6f2-117">Fas 2: registrera dina iOS-och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="cc6f2-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="cc6f2-118">Om du funderar på att hantera dina enheter med hjälp av en lösning för en mobil enhet kan du använda Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="cc6f2-119">När du arbetar med en MDM-leverantör, inklusive Intune, är enheterna "registrerade".</span><span class="sxs-lookup"><span data-stu-id="cc6f2-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="cc6f2-120">När de har registrerats får de de funktioner och inställningar som du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="cc6f2-121">I Intune finns det ett par sätt att registrera iOS/iPad-och Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="cc6f2-122">Du kan välja vilket alternativ som passar bäst för din organisation.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="cc6f2-123">Mer information och vägledning finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="cc6f2-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="cc6f2-124">Distributions guide: registrera enheter för iOS och iPad i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cc6f2-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="cc6f2-125">Distributions guide: registrera Android-enheter i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cc6f2-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="cc6f2-126">Om du är redo att använda Intune för enhets hantering och vill ha lite vägledning kan följande information vara till hjälp:</span><span class="sxs-lookup"><span data-stu-id="cc6f2-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="cc6f2-127">Översikt över enhets hantering</span><span class="sxs-lookup"><span data-stu-id="cc6f2-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="cc6f2-128">Själv studie kurs: genom gång av Intune i Microsoft slut punkts hanteraren</span><span class="sxs-lookup"><span data-stu-id="cc6f2-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="cc6f2-129">Distributions guide: Konfigurera eller gå till Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cc6f2-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="cc6f2-130">Fas 3: hantera dina iOS-och Android-enheter från andra datorer</span><span class="sxs-lookup"><span data-stu-id="cc6f2-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="cc6f2-131">Microsoft Intune tillhandahåller funktionen för återställning av fjär lås och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="cc6f2-132">Om någon förlorar sin enhet kan du fjärrans luta enheten.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="cc6f2-133">Om någon glömmer sitt lösen ord kan du återställa det.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="cc6f2-134">Om du vill låsa upp en iOS/iPad-eller Android-enhet går du till [fjär lås enheter med Intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="cc6f2-135">Information om hur du återställer lösen ordet från en dator finns i [återställa eller ta bort en enhets kod i Intune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="cc6f2-136">Mer information om hur du kör fjärr anslutningar finns i [tillgängliga enheter](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="cc6f2-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="cc6f2-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="cc6f2-137">Next step</span></span>

<span data-ttu-id="cc6f2-138">Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="cc6f2-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc6f2-139">Se även</span><span class="sxs-lookup"><span data-stu-id="cc6f2-139">See Also</span></span>

[<span data-ttu-id="cc6f2-140">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="cc6f2-141">Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="cc6f2-142">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="cc6f2-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
