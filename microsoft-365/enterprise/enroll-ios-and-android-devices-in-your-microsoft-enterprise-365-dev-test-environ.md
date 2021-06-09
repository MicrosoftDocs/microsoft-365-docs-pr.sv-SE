---
title: Registrera iOS-/iPadOS- och Android-enheter i din Microsoft 365 för företagstestmiljö
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
description: Använd den här testlabbguiden för att registrera enheter i Microsoft 365 testmiljö och hantera dem på distans.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367089"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="99b90-103">Registrera iOS- och Android-enheter i din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="99b90-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="99b90-104">*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="99b90-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="99b90-105">I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för hantering av mobila enheter för iOS-/iPadOS- och Android-enheter i testmiljön för Microsoft 365 företag.</span><span class="sxs-lookup"><span data-stu-id="99b90-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="99b90-106">Registrering av iOS-/iPadOS- och Android-enheter i testmiljön omfattar tre faser:</span><span class="sxs-lookup"><span data-stu-id="99b90-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="99b90-107">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="99b90-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="99b90-108">Fas 2: Registrera dina iOS-/iPadOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="99b90-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="99b90-109">Fas 3: Hantera dina iOS-/iPadOS- och Android-enheter via fjärrstyrning</span><span class="sxs-lookup"><span data-stu-id="99b90-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="99b90-111">En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="99b90-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="99b90-112">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="99b90-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="99b90-113">Om du vill registrera iOS-/iPadOS- och Android-enheter på ett lätt sätt med minimikraven följer du anvisningarna i [Lätt baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="99b90-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="99b90-114">Om du vill registrera iOS/iPadOS och Android-enheter i ett simulerat företag följer du anvisningarna i [Direktautentisering.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="99b90-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="99b90-115">Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="99b90-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="99b90-116">Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap, och du kan experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="99b90-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="99b90-117">Fas 2: Registrera dina iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="99b90-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="99b90-118">Om du överväger en MDM-lösning (Mobile Device Management) för att hantera dina enheter kan du använda Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="99b90-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="99b90-119">När du arbetar med en MDM-leverantör, inklusive Intune, registreras enheter.</span><span class="sxs-lookup"><span data-stu-id="99b90-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="99b90-120">När de har registrerats får de de funktioner och inställningar som du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="99b90-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="99b90-121">I Intune finns det några olika sätt att registrera dina iOS-/iPadOS- och Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="99b90-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="99b90-122">Du kan välja det registreringsalternativ som passar din organisation bäst.</span><span class="sxs-lookup"><span data-stu-id="99b90-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="99b90-123">Mer information och vägledning finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="99b90-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="99b90-124">Distributionsguide: Registrera iOS- och iPadOS-enheter i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="99b90-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="99b90-125">Distributionsguide: Registrera Android-enheter i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="99b90-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="99b90-126">Om du är redo att använda Intune för enhetshantering och vill ha lite vägledning kan följande information vara till hjälp:</span><span class="sxs-lookup"><span data-stu-id="99b90-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="99b90-127">Översikt över enhetshantering</span><span class="sxs-lookup"><span data-stu-id="99b90-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="99b90-128">Självstudiekurs: Genomgång av Intune i Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="99b90-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="99b90-129">Distributionsguide: Installera eller flytta till Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="99b90-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="99b90-130">Fas 3: Hantera iOS- och Android-enheter via fjärrstyrning</span><span class="sxs-lookup"><span data-stu-id="99b90-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="99b90-131">Microsoft Intune även fjärrlås och återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="99b90-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="99b90-132">Om någon förlorar sin enhet kan du fjärrlåsa enheten.</span><span class="sxs-lookup"><span data-stu-id="99b90-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="99b90-133">Om någon glömmer sitt lösenord kan du fjärråterställninga det.</span><span class="sxs-lookup"><span data-stu-id="99b90-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="99b90-134">Information om hur du fjärrlåser en iOS/iPadOS- eller Android-enhet finns i [Fjärrlåsa enheter med Intune.](/mem/intune/remote-actions/device-remote-lock)</span><span class="sxs-lookup"><span data-stu-id="99b90-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="99b90-135">Om du vill fjärråterställning av lösenordet kan du [gå till Återställa eller ta bort en enhetskod i Intune.](/mem/intune/remote-actions/device-passcode-reset)</span><span class="sxs-lookup"><span data-stu-id="99b90-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="99b90-136">Information om ytterligare uppgifter som du kan köra på distans finns [i tillgängliga enhetsåtgärder.](/mem/intune/remote-actions/device-management#available-device-actions)</span><span class="sxs-lookup"><span data-stu-id="99b90-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="99b90-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="99b90-137">Next step</span></span>

<span data-ttu-id="99b90-138">Utforska ytterligare [funktioner för hantering av](m365-enterprise-test-lab-guides.md#mobile-device-management) mobila enheter och funktioner i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="99b90-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="99b90-139">Se även</span><span class="sxs-lookup"><span data-stu-id="99b90-139">See Also</span></span>

[<span data-ttu-id="99b90-140">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="99b90-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="99b90-141">Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="99b90-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="99b90-142">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="99b90-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
