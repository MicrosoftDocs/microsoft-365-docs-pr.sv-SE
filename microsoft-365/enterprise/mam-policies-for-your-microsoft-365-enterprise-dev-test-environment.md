---
title: Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här test laboratorie guiden för att lägga till principer för efterlevnadsprinciper i din Microsoft 365 för företags test miljö.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487418"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d3183-103">Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d3183-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d3183-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="d3183-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d3183-105">I den här artikeln beskrivs hur du lägger till en policy för principer för en Intune-enhet för Windows 10-enheter och Microsoft 365-appar för företag till din test miljö för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="d3183-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d3183-106">Du lägger till en policy för en Intune-enhet i två faser:</span><span class="sxs-lookup"><span data-stu-id="d3183-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="d3183-107">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d3183-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d3183-108">Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d3183-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d3183-110">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d3183-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d3183-111">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d3183-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d3183-112">Om du vill konfigurera MAM-principer på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d3183-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d3183-113">Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d3183-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3183-114">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d3183-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d3183-115">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="d3183-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="d3183-116">Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d3183-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="d3183-117">I den här fasen skapar du en princip för enhetskompatibilitet för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="d3183-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="d3183-118">Gå till [administrations centret för microsoft 365](https://admin.microsoft.com) och logga in på ditt Microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="d3183-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="d3183-119">Öppna Azure-portalen på på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="d3183-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="d3183-120">I sökrutan för Azure-portalen anger du **Intune**och sedan **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d3183-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="d3183-121">Om du ser ett meddelande om **att du inte har aktiverat enhets hantering ännu** i fönstret **Microsoft Intune** väljer du det.</span><span class="sxs-lookup"><span data-stu-id="d3183-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="d3183-122">I fönstret **hantering av mobila enheter** väljer du **Intune MDM**och väljer sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="d3183-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="d3183-123">Uppdatera din webbläsare.</span><span class="sxs-lookup"><span data-stu-id="d3183-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="d3183-124">I det vänstra navigerings fönstret väljer du **grupper**.</span><span class="sxs-lookup"><span data-stu-id="d3183-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="d3183-125">I fönstret **grupper – alla grupper** väljer du **+ ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="d3183-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="d3183-126">I fönstret **grupp** väljer du **Microsoft 365** eller **säkerhet** för **grupptyp?**, anger **hanterade Windows 10-användare** i **namn**, Välj **tilldelat** i **medlemskaps typ**och välj sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3183-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="d3183-127">Välj **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="d3183-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="d3183-128">I listan **snabb uppgifter** i fönstret **Microsoft Intune** väljer du **skapa en policy för efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="d3183-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="d3183-129">I fönstret **policy profiler för efterlevnad** väljer du **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="d3183-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="d3183-130">Ange **Windows 10**i **namn**i fönstret **Skapa princip** .</span><span class="sxs-lookup"><span data-stu-id="d3183-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="d3183-131">I **Platform**väljer du **Windows 10 och senare**, väljer **OK** i fönstret **policyn för Windows 10-efterlevnad** och väljer sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="d3183-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="d3183-132">Välj **profiler för efterlevnadsprinciper**och välj sedan **Windows 10** -princip namnet.</span><span class="sxs-lookup"><span data-stu-id="d3183-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="d3183-133">I fönstret **Windows 10** väljer du **uppgifter**och väljer sedan **Välj grupper som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="d3183-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="d3183-134">I fönstret **Välj grupper som ska inkluderas** väljer du gruppen **hanterade Windows 10-enheter** och väljer sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="d3183-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="d3183-135">Välj **Spara**, Välj **Microsoft Intune-översikt**och välj sedan **klient program** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="d3183-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="d3183-136">Välj **appar**i fönstret **klient program** och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d3183-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="d3183-137">Välj **program typ**i fönstret **Lägg till app** och välj sedan **Windows 10** under **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="d3183-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="d3183-138">I fönstret **Lägg till app** väljer du **information för programpaket**.</span><span class="sxs-lookup"><span data-stu-id="d3183-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="d3183-139">I fönstret **Programsvits information** anger du **Microsoft 365-appar för företag** i både **Suite-namn** och **programbeskrivning**och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3183-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3183-140">I fönstret **Lägg till app** väljer du **Konfigurera programsvit**och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3183-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3183-141">I fönstret **Lägg till app** väljer du **Inställningar för programpaket**.</span><span class="sxs-lookup"><span data-stu-id="d3183-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="d3183-142">För **Uppdatera kanal**, Välj **halvårs företag**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3183-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="d3183-143">I fönstret **Lägg till app** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d3183-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="d3183-144">Du har nu en policy för enhetskompatibilitet för att testa de valda programmen i policyn för **Windows 10** -enheter och för medlemmar i gruppen **användare av hanterade Windows 10-enheter** .</span><span class="sxs-lookup"><span data-stu-id="d3183-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="d3183-145">Observera att om du väljer **Microsoft 365** skapas ytterligare resurser med grupp typen.</span><span class="sxs-lookup"><span data-stu-id="d3183-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="d3183-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d3183-146">Next step</span></span>

<span data-ttu-id="d3183-147">Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="d3183-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3183-148">Se även</span><span class="sxs-lookup"><span data-stu-id="d3183-148">See also</span></span>

<span data-ttu-id="d3183-149">[Microsoft 365 för företags test labb guider](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="d3183-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="d3183-150">Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d3183-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="d3183-151">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="d3183-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d3183-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d3183-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
