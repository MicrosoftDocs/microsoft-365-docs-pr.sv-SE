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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686760"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07394-103">Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="07394-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07394-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="07394-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="07394-105">Med instruktionerna i den här artikeln kan du lägga till en policy för principer för en Intune-enhet för Windows 10-enheter och Microsoft 365-appar för företag till din test miljö för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="07394-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="07394-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="07394-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07394-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="07394-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07394-109">Om du bara vill konfigurera MAM-principer på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="07394-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="07394-110">Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="07394-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="07394-111">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="07394-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="07394-112">Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="07394-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="07394-113">Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="07394-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="07394-114">I den här fasen skapar du en princip för enhetskompatibilitet för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="07394-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="07394-115">Gå till [administrations centret för microsoft 365](https://admin.microsoft.com) och logga in på ditt Microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="07394-115">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="07394-116">Öppna Azure-portalen på på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="07394-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="07394-117">På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="07394-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="07394-118">Om du ser ett meddelande om **att du inte har aktiverat enhets hantering** i **Microsoft Intune** -fönstret klickar du på det.</span><span class="sxs-lookup"><span data-stu-id="07394-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="07394-119">Klicka på **INTUNE MDM-auktoritet**i fönstret **hantering av mobila enheter** och klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="07394-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="07394-120">Uppdatera din webbläsare.</span><span class="sxs-lookup"><span data-stu-id="07394-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="07394-121">Klicka på **grupper**i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="07394-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="07394-122">I fönstret **grupper – alla grupper** klickar du på **+ ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="07394-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="07394-123">I fönstret **grupp** väljer du **Microsoft 365** eller **säkerhet** för **grupptyp?**, Skriv **hanterade Windows 10-enheter-användare** i **namn**, Välj **tilldelat** i **medlemskaps typ**och klicka sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="07394-123">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="07394-124">Klicka på **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="07394-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="07394-125">Klicka på **skapa en policy för efterlevnad**i listan **snabb uppgifter** i fönstret **Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="07394-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="07394-126">Klicka på **Skapa princip**i fönstret **policy profiler för efterlevnad** .</span><span class="sxs-lookup"><span data-stu-id="07394-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="07394-127">I fönstret **Skapa princip** skriver du **Windows 10**i **namn**.</span><span class="sxs-lookup"><span data-stu-id="07394-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="07394-128">I **Platform**väljer du **Windows 10 och senare**klickar du på **OK** i fönstret **efterlevnad för Windows 10** och klickar sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="07394-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="07394-129">Klicka på **profiler för efterlevnadsprinciper**och klicka sedan på princip namnet för **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="07394-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="07394-130">I fönstret **Windows 10** klickar du på **uppgifter**och sedan på **Välj grupper som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="07394-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="07394-131">Klicka på gruppen **hanterade användare av Windows 10-enhet** i fönstret **Välj grupper som ska inkluderas** och klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="07394-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="07394-132">Klicka på **Spara**, klicka på **Microsoft Intune-översikt**och klicka sedan på **klient program** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="07394-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="07394-133">I fönstret **klient program** klickar du på **appar**och sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="07394-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="07394-134">Välj **program typ**i fönstret **Lägg till app** och välj sedan **Windows 10** under **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="07394-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>

17. <span data-ttu-id="07394-135">I fönstret **Lägg till app** väljer du **information för programpaket**.</span><span class="sxs-lookup"><span data-stu-id="07394-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="07394-136">I fönstret **information om programsviten** skriver du **Microsoft 365-appar för företag** i både **serie namn** och **programbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="07394-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="07394-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="07394-137">Click OK.</span></span>

19. <span data-ttu-id="07394-138">I fönstret **Lägg till app** väljer du **Konfigurera programsvit**och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="07394-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="07394-139">I fönstret **Lägg till app** väljer du **Inställningar för programpaket**.</span><span class="sxs-lookup"><span data-stu-id="07394-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="07394-140">För **Uppdatera kanal**väljer du **halvår för företag**och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="07394-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="07394-141">Klicka på **Lägg till**i fönstret **Lägg till app** .</span><span class="sxs-lookup"><span data-stu-id="07394-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="07394-142">Du har nu en policy för enhetskompatibilitet för att testa de valda programmen i policyn för **Windows 10** -enheter och för medlemmar i gruppen **användare av hanterade Windows 10-enheter** .</span><span class="sxs-lookup"><span data-stu-id="07394-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="07394-143">Observera att om du väljer Microsoft 365 som grupptyp skapas ytterligare resurser.</span><span class="sxs-lookup"><span data-stu-id="07394-143">Please note that selecting Microsoft 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="07394-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="07394-144">Next step</span></span>

<span data-ttu-id="07394-145">Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="07394-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="07394-146">Se även</span><span class="sxs-lookup"><span data-stu-id="07394-146">See also</span></span>

<span data-ttu-id="07394-147">[Microsoft 365 för företags test labb guider](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="07394-147">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="07394-148">Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="07394-148">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="07394-149">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="07394-149">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="07394-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="07394-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
