---
title: Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här testlabbguiden för att lägga till Intune-efterlevnadsprinciper för enheter i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367101"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7398a-103">Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7398a-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7398a-104">*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="7398a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7398a-105">I den här artikeln beskrivs hur du lägger till en intune enhetsefterlevnadsprincip för Windows 10 enheter och Microsoft 365-appar för företag i din Microsoft 365 för företagstestmiljö.</span><span class="sxs-lookup"><span data-stu-id="7398a-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7398a-106">När du lägger till en Intune-enhetsefterlevnadsprincip ingår två faser:</span><span class="sxs-lookup"><span data-stu-id="7398a-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="7398a-107">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7398a-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="7398a-108">Fas 2: Skapa en policy för enhetsefterlevnad för Windows 10 enheter</span><span class="sxs-lookup"><span data-stu-id="7398a-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7398a-110">En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="7398a-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7398a-111">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7398a-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7398a-112">Om du bara vill konfigurera MAM-principer på ett lätt sätt med minimikraven följer du anvisningarna i Enkel [baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="7398a-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7398a-113">Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [Direktautentisering.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="7398a-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7398a-114">Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="7398a-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7398a-115">Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="7398a-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="7398a-116">Fas 2: Skapa en policy för enhetsefterlevnad för Windows 10 enheter</span><span class="sxs-lookup"><span data-stu-id="7398a-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="7398a-117">I den här fasen skapar du en policy för enhetsefterlevnad för Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="7398a-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="7398a-118">Den här fasen använder Microsoft Intune och [Microsoft Endpoint Manager för att](https://go.microsoft.com/fwlink/?linkid=2109431) lägga till en grupp och skapa en efterlevnadsprincip.</span><span class="sxs-lookup"><span data-stu-id="7398a-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="7398a-119">Gå till [Microsoft 365 och logga](https://admin.microsoft.com)in på din prenumeration Microsoft 365 testlabb med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="7398a-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="7398a-120">Välj **Endpoint Manager** administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="7398a-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="7398a-121">Administrationscentret [Endpoint Manager öppnas.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="7398a-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="7398a-122">Om du ser ett meddelande **som liknar Du har inte** aktiverat enhetshantering än väljer du Intune som MDM-instans.</span><span class="sxs-lookup"><span data-stu-id="7398a-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="7398a-123">Specifika steg finns i Ange [utfärdare för hantering av mobila enheter.](/mem/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="7398a-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="7398a-124">Fokus Endpoint Manager på enhetshantering och apphantering.</span><span class="sxs-lookup"><span data-stu-id="7398a-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="7398a-125">En genomgång av det här administrationscentret finns i [Självstudiekurs: Genomgång av Intune i Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="7398a-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="7398a-126">I **Grupper lägger** du till en **Microsoft 365** **säkerhetsgrupp** eller säkerhetsgrupp med namnet Managed Windows 10 **device users**, med en **tilldelad** medlemskapstyp.</span><span class="sxs-lookup"><span data-stu-id="7398a-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="7398a-127">I nästa steg ska du tilldela den här gruppen din efterlevnadsprincip.</span><span class="sxs-lookup"><span data-stu-id="7398a-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="7398a-128">För specifika steg, och för information om hur du **Microsoft 365** **säkerhetsgrupper,** se Lägga [till grupper för att ordna användare och enheter.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="7398a-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="7398a-129">Skapa **en** princip för Windows 10 i Enheter.</span><span class="sxs-lookup"><span data-stu-id="7398a-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="7398a-130">Tilldela den här principen till gruppen **hanterade Windows 10 enhet som du** har skapat.</span><span class="sxs-lookup"><span data-stu-id="7398a-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="7398a-131">I principen kan du blockera enkla lösenord, kräva en brandvägg, kräva att Microsoft Defender-tjänsten mot skadlig programvara körs och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="7398a-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="7398a-132">En efterlevnadsprincip omfattar vanligtvis basinställningarna eller en miniminivå som varje enhet ska ha.</span><span class="sxs-lookup"><span data-stu-id="7398a-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="7398a-133">Mer information om tillgängliga efterlevnadsinställningar som du kan konfigurera finns i Använda efterlevnadsprinciper för att ange regler för [enheter som du hanterar.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="7398a-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="7398a-134">När du är klar har du en princip för enhetsefterlevnad för att testa medlemmar i **gruppen Hanterade Windows 10 och enhetsanvändare.**</span><span class="sxs-lookup"><span data-stu-id="7398a-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="7398a-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7398a-135">Next step</span></span>

<span data-ttu-id="7398a-136">Utforska ytterligare [funktioner för hantering av](m365-enterprise-test-lab-guides.md#mobile-device-management) mobila enheter och funktioner i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="7398a-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7398a-137">Se även</span><span class="sxs-lookup"><span data-stu-id="7398a-137">See also</span></span>

<span data-ttu-id="7398a-138">[Microsoft 365 för testlabbguider för företag.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="7398a-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="7398a-139">Registrera iOS- och Android-enheter i din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="7398a-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="7398a-140">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7398a-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7398a-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="7398a-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
