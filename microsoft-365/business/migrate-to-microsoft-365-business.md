---
title: Uppgradera till Microsoft 365 Business från Office 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Steg som uppgraderar ditt företag från Office 365 Business Premium till Microsoft 365 Business.
ms.openlocfilehash: 0732f76e5bd8540e5954bd7ea7b88061326901b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593688"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="b7bf5-103">Uppgradera till Microsoft 365 Business från Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b7bf5-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="b7bf5-104">Om du har en [Office 365 för företag-prenumeration,](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)till exempel Office 365 Business Premium, kan du enkelt uppgradera till Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="b7bf5-105">Uppgradera till Microsoft 365 Business om du vill lägga till:</span><span class="sxs-lookup"><span data-stu-id="b7bf5-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="b7bf5-106">Windows 10 Pro (till datorer som kör Windows 8 eller senare)</span><span class="sxs-lookup"><span data-stu-id="b7bf5-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="b7bf5-107">Enkla kontroller som hanterar affärsdata på enheter</span><span class="sxs-lookup"><span data-stu-id="b7bf5-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="b7bf5-108">Avancerade säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-108">Advanced security capabilities.</span></span>
<span data-ttu-id="b7bf5-109">Läs mer om Microsoft 365 Business på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="b7bf5-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="b7bf5-110">Vad är skillnaden mellan Office 365 Business Premium och Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="b7bf5-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="b7bf5-111">Vi har lagt till en sida-vid-sida jämförelse av dessa två planer till [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="b7bf5-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="b7bf5-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b7bf5-112">Before you get started</span></span>

- <span data-ttu-id="b7bf5-113">**När ska jag välja att uppgradera?**</span><span class="sxs-lookup"><span data-stu-id="b7bf5-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="b7bf5-114">Uppgradering är rätt val när du vill uppgradera **alla användare** som tilldelats en enda plan.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="b7bf5-115">När du väljer uppgradering, alla plan användare får byta till en annan plan samtidigt.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="b7bf5-116">Om du inte vill uppgradera alla som har tilldelats en enda plan köper du licenser för den nya planen (i det här fallet Microsoft 365 Business) och [tilldelar dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) till varje användare som du vill uppgradera.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="b7bf5-117">**Vissa tillägg kan förhindra uppgraderingen** Om du försöker starta en uppgradering och du har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till den senare om du fortfarande behöver det.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span> 
- <span data-ttu-id="b7bf5-118">**Om du förbetalt din plan** Det finns inte en enkel uppgraderingsväg för förbetalda planer.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="b7bf5-119">Du vet om du har en förbetald plan eftersom du ställer in din plan med ett produkt-ID som du kan ha köpt i en butik.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="b7bf5-120">Kontakta en partner, gå till Microsoft Store eller vänta tills din förbetalda plan går ut för att växla till en ny plan.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="b7bf5-121">Uppgradera till Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b7bf5-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="b7bf5-122">Köp dina licenser genom att följa dessa steg i det [nya administrationscentret:](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="b7bf5-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="b7bf5-123">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administratörscentret på .</span><span class="sxs-lookup"><span data-stu-id="b7bf5-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="b7bf5-124">Gå till navigeringsfönstret och välj \> **Faktureringsprodukter & Tjänster**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b7bf5-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="b7bf5-125">Leta reda på din Office 365-prenumeration och välj den för att visa informationen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![En skärmbild visar hur du hittar och väljer din prenumeration i administrationscentret.](media/FindYourSubscription.png)

3. <span data-ttu-id="b7bf5-127">På nästa sida väljer du **Uppgradera**.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-127">On the next page, select **Upgrade**.</span></span> 

      ![En skärmbild visar var du vill välja Uppgradera i administrationscentret.](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="b7bf5-129">Om du ser ett meddelande om att **uppgradera din prenumeration inte stöds med gruppbaserad licensiering i Azure Active Directory**kan du ignorera detta om du inte har en mycket stor organisation.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-129">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="b7bf5-130">Organisationer som har valt det här alternativet är medvetna om att de använder gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="b7bf5-131">Därefter kan du visa en lista över Office-planer som du kan uppgradera till.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="b7bf5-132">I det här fallet hittar du Microsoft 365 Business-planen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="b7bf5-133">Du kan rulla nedåt om du vill se alla Office-appar och tjänster som ingår i den här planen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="b7bf5-134">Under **Microsoft 365 Business**väljer du **Uppgradera** för att lägga till Microsoft 365 Business i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="b7bf5-135">I vagnen:</span><span class="sxs-lookup"><span data-stu-id="b7bf5-135">In the cart:</span></span>
    1. <span data-ttu-id="b7bf5-136">Vi kommer automatiskt att inkludera licenser för alla dina nuvarande användare.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-136">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="b7bf5-137">Om du behöver fler eller färre licenser måste du [köpa och tilldela dessa licenser individuellt.](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="b7bf5-137">If you need more or fewer licenses, you need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="b7bf5-138">Du kan justera hur du vill betala: månadsvis eller årligen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-138">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="b7bf5-139">Välj rullgardinsmenyn för att göra ditt val.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="b7bf5-140">Välj **Gå till Kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetodför det här kontot.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="b7bf5-141">Du kan också lägga till en kampanjkod här om du har en.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="b7bf5-142">Välj **Placera order** för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="b7bf5-143">Det tar Microsoft några minuter att ställa in dina nya serviceplaner.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="b7bf5-144">Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="b7bf5-145">När planen är klar kan du behöva slutföra några ytterligare inställningssteg i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="b7bf5-146">I navigeringsfönstret väljer du **Start för** att slutföra ytterligare inställningssteg.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="b7bf5-147">Du får en proportionell återbetalning för de Office 365-licenser som du inte längre behöver.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-147">You'll receive a prorated refund for the Office 365 licenses that you no longer need.</span></span> <span data-ttu-id="b7bf5-148">Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har ställt in den nya planen.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="b7bf5-149">Skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="b7bf5-149">Protect user devices and files</span></span>

<span data-ttu-id="b7bf5-150">Nu när Microsoft 365 Business-licenser har tilldelats, slutför du stegen för att börja skydda enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="b7bf5-151">Du använder några nya alternativ som ingår i navigeringsfönstret för administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-151">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="b7bf5-152">Gå till \> **Enhetsprinciper**i navigeringsfönstret \*\*\*\* i administrationscentret .</span><span class="sxs-lookup"><span data-stu-id="b7bf5-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="b7bf5-153">På sidan **Enhetsprinciper** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="b7bf5-154">I fönstret **Lägg till princip** ger principen ett namn (till exempel Skydda arbetsfiler) och välj sedan en **principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b7bf5-155">Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter, samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="b7bf5-156">Se följande länkar för detaljer:</span><span class="sxs-lookup"><span data-stu-id="b7bf5-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="b7bf5-157">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="b7bf5-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="b7bf5-158">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="b7bf5-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="b7bf5-159">Ange enhetsskyddsinställningar för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="b7bf5-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="b7bf5-160">När du har konfigurerat principer kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="b7bf5-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="b7bf5-161">Om windows-enheterna inte redan använder Windows Pro Creator-uppdateringen måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="b7bf5-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="b7bf5-162">Se [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="b7bf5-163">Se [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="b7bf5-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
