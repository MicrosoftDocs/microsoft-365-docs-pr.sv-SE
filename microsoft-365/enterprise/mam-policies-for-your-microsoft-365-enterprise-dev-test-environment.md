---
title: Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill lägga till Intune-principer för enhetsefterlevnad i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: b0b8bd2d76a3959bbcca749545d9a16e50491d20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812226"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="38953-103">Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="38953-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="38953-104">*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="38953-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="38953-105">Med instruktionerna i den här artikeln lägger du till en Intune-enhetsefterlevnadsprincip för Windows 10-enheter och Office 365 ProPlus i microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="38953-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Office 365 ProPlus to your Microsoft 365 Enterprise test environment.</span></span>

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="38953-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.</span><span class="sxs-lookup"><span data-stu-id="38953-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="38953-108">Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="38953-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="38953-109">Om du bara vill konfigurera MAM-principer på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="38953-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="38953-110">Om du vill konfigurera [MAM-principer](pass-through-auth-m365-ent-test-environment.md)i ett simulerat företag följer du instruktionerna i Direktautentisering .</span><span class="sxs-lookup"><span data-stu-id="38953-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="38953-111">Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="38953-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="38953-112">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="38953-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="38953-113">Fas 2: Skapa en princip för enhetsefterlevnad för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="38953-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="38953-114">I den här fasen skapar du en enhetsefterlevnadsprincip för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="38953-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="38953-115">Gå till Office 365-portalen på ([https://portal.office.com](https://portal.office.com)) och logga in på din Office 365 testlabbprenumeration med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="38953-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="38953-116">Öppna Azure-portalen på [https://portal.azure.com](https://portal.azure.com)en ny flik i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="38953-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="38953-117">Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="38953-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="38953-118">Om meddelandet **Du inte har aktiverat enhetshantering ännu i** Microsoft **Intune-fönstret** klickar du på den.</span><span class="sxs-lookup"><span data-stu-id="38953-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="38953-119">Klicka på **Intune MDM Authority**i **fönstret Hantering av mobila enheter** och klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="38953-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="38953-120">Uppdatera webbläsarfliken.</span><span class="sxs-lookup"><span data-stu-id="38953-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="38953-121">Klicka på **Grupper**i det vänstra navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="38953-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="38953-122">Klicka på **+ Ny grupp**i fönstret **Grupper-allagrupper** .</span><span class="sxs-lookup"><span data-stu-id="38953-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="38953-123">I **gruppfönstret** väljer du Typ av **Office 365** eller **Säkerhet** för **grupp?**, skriver **du Hanterade Windows 10-enhetsanvändare** i **Namn**, väljer Tilldelad i **medlemstyp** och klickar sedan på **Skapa**. **Membership type**</span><span class="sxs-lookup"><span data-stu-id="38953-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="38953-124">Klicka på **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="38953-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="38953-125">Klicka på **Skapa en efterlevnadsprincip**i **snabbdatalistan** i fönstret **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="38953-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="38953-126">Klicka på Skapa princip i fönstret **Profil för efterlevnadsprincip.** **Create Policy**</span><span class="sxs-lookup"><span data-stu-id="38953-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="38953-127">Skriv **Windows 10**i **Namn**i fönstret **Skapa princip** .</span><span class="sxs-lookup"><span data-stu-id="38953-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="38953-128">Välj Windows **10 och senare** **i** **fönstret Windows** **10 och** klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38953-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="38953-129">Klicka på **Efterlevnadsprincipprofiler**och sedan på principnamnet för **Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="38953-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="38953-130">Klicka på **Tilldelningar**i fönstret **Windows 10** och klicka sedan på **Välj grupper som du vill inkludera**.</span><span class="sxs-lookup"><span data-stu-id="38953-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="38953-131">Klicka på gruppen Hanterade Windows **10-enhetsanvändare** i fönstret **Välj grupper som ska inkluderas** och klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="38953-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="38953-132">Klicka på **Spara,** klicka på **Microsoft Intune-Översikt**och sedan på **Klientappar** i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="38953-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="38953-133">Klicka på **Appar**i fönstret **Klientappar** och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="38953-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="38953-134">I fönstret **Lägg till app** väljer du **Apptyp**och väljer sedan **Windows 10** under **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="38953-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="38953-135">Välj Information om **App Suite**i fönstret Lägg till **app** .</span><span class="sxs-lookup"><span data-stu-id="38953-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="38953-136">Skriv **Office 365 ProPlus** i både **Suite Namn** och Suite **Description**i informationsfönstret för **App Suite.**</span><span class="sxs-lookup"><span data-stu-id="38953-136">In the **App Suite Information** pane, type **Office 365 ProPlus** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="38953-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38953-137">Click OK.</span></span>

19. <span data-ttu-id="38953-138">I fönstret **Lägg till app** väljer du Konfigurera App **Suite**och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="38953-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="38953-139">Välj **Inställningar för App Suite**i fönstret Lägg till **app.**</span><span class="sxs-lookup"><span data-stu-id="38953-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="38953-140">För **Uppdatera kanal**väljer du **Halvårsvis**och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="38953-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="38953-141">Klicka på **Lägg till**i fönstret Lägg **till app** .</span><span class="sxs-lookup"><span data-stu-id="38953-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="38953-142">Du har nu en princip för enhetsefterlevnad för att testa de valda apparna i windows **10-enhetens** efterlevnadsprincip och för medlemmar i gruppen **Hanterade Windows 10-enhetsanvändare.**</span><span class="sxs-lookup"><span data-stu-id="38953-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="38953-143">Observera att om du väljer Office 365 som grupptyp skapas ytterligare resurser.</span><span class="sxs-lookup"><span data-stu-id="38953-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="38953-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="38953-144">Next step</span></span>

<span data-ttu-id="38953-145">Utforska ytterligare funktioner och funktioner för hantering av [mobila](m365-enterprise-test-lab-guides.md#mobile-device-management) enheter i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="38953-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="38953-146">Se även</span><span class="sxs-lookup"><span data-stu-id="38953-146">See also</span></span>

<span data-ttu-id="38953-147">[Microsoft 365 Företagstestlabbguider](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="38953-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="38953-148">Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="38953-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="38953-149">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="38953-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="38953-150">Företagsmobilitet + säkerhet (EMS)</span><span class="sxs-lookup"><span data-stu-id="38953-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
