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
ms.openlocfilehash: e17ac2658c7276ba4a77de371847343866815c42
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065306"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="d24fd-103">Uppgradera till Microsoft 365 Business från Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d24fd-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="d24fd-104">Om du har en [Office 365 för företagsprenumeration,](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)till exempel Office 365 Business Premium, kan du enkelt uppgradera till Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d24fd-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="d24fd-105">Uppgradera till Microsoft 365 Business om du vill lägga till:</span><span class="sxs-lookup"><span data-stu-id="d24fd-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="d24fd-106">Windows 10 Pro (till datorer som kör Windows 8 eller senare)</span><span class="sxs-lookup"><span data-stu-id="d24fd-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="d24fd-107">Enkla kontroller som hanterar affärsdata på enheter</span><span class="sxs-lookup"><span data-stu-id="d24fd-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="d24fd-108">Avancerade säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="d24fd-108">Advanced security capabilities.</span></span>
<span data-ttu-id="d24fd-109">Läs mer om Microsoft 365 Business på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="d24fd-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="d24fd-110">Vad är skillnaden mellan Office 365 Business Premium och Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="d24fd-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="d24fd-111">Vi har lagt till en jämförelse sida vid sida av dessa två planer till [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="d24fd-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="d24fd-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d24fd-112">Before you get started</span></span>

- <span data-ttu-id="d24fd-113">**När ska jag välja att uppgradera?**</span><span class="sxs-lookup"><span data-stu-id="d24fd-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="d24fd-114">Uppgradering är rätt val när du vill uppgradera **alla användare** som tilldelats en enda plan.</span><span class="sxs-lookup"><span data-stu-id="d24fd-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="d24fd-115">När du väljer uppgradering byter alla abonnemangsanvändare till ett annat abonnemang samtidigt.</span><span class="sxs-lookup"><span data-stu-id="d24fd-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="d24fd-116">Om du inte vill uppgradera alla som tilldelats ett enda abonnemang köper du licenser för den nya planen (i det här fallet Microsoft 365 Business) och [tilldelar dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) till varje användare som du vill uppgradera.</span><span class="sxs-lookup"><span data-stu-id="d24fd-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="d24fd-117">**Vissa tillägg kan förhindra uppgraderingen** Om du försöker starta en uppgradering och du har ett tillägg som hindrar dig från att fortsätta kan du först ta bort tillägget och sedan lägga till den igen senare om du fortfarande behöver den.</span><span class="sxs-lookup"><span data-stu-id="d24fd-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span> 
- <span data-ttu-id="d24fd-118">**Om du förbetalda din plan** Det finns inte en enkel uppgraderingsväg för förbetalda planer.</span><span class="sxs-lookup"><span data-stu-id="d24fd-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="d24fd-119">Du vet om du har en förbetald plan eftersom du har konfigurerat din plan med hjälp av ett produkt-ID som du kan ha köpt i en butik.</span><span class="sxs-lookup"><span data-stu-id="d24fd-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="d24fd-120">Kontakta en partner, gå till Microsoft Store eller vänta tills din förbetalda plan går ut för att växla till ett nytt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d24fd-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="d24fd-121">Uppgradera till Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="d24fd-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="d24fd-122">Köp dina licenser genom att följa dessa steg i det [nya administrationscentret:](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="d24fd-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="d24fd-123">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administrationscentret på .</span><span class="sxs-lookup"><span data-stu-id="d24fd-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="d24fd-124">Gå till navigeringsfönstret och välj \> **Faktureringsprodukter & Tjänster**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d24fd-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="d24fd-125">Hitta din Office 365-prenumeration och välj den för att visa informationen.</span><span class="sxs-lookup"><span data-stu-id="d24fd-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![En skärmbild visar hur du hittar och väljer din prenumeration i administrationscentret.](../media/FindYourSubscription.png)

3. <span data-ttu-id="d24fd-127">På nästa sida väljer du **Uppgradera**.</span><span class="sxs-lookup"><span data-stu-id="d24fd-127">On the next page, select **Upgrade**.</span></span> 

      ![En skärmbild visar var du kan välja Uppgradera i administrationscentret.](../media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="d24fd-129">Om du ser ett meddelande som säger att **uppgradera din prenumeration stöds inte med gruppbaserad licensiering i Azure Active Directory**kan du ignorera detta på ett säkert sätt om du inte har en mycket stor organisation.</span><span class="sxs-lookup"><span data-stu-id="d24fd-129">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="d24fd-130">Organisationer som har valt det här alternativet är medvetna om att de använder gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="d24fd-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="d24fd-131">Därefter kan du visa en lista över Office-planer som du kan uppgradera till.</span><span class="sxs-lookup"><span data-stu-id="d24fd-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="d24fd-132">I det här fallet hittar du Microsoft 365 Business-planen.</span><span class="sxs-lookup"><span data-stu-id="d24fd-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="d24fd-133">Du kan rulla nedåt om du vill se alla Office-appar och -tjänster som ingår i den här planen.</span><span class="sxs-lookup"><span data-stu-id="d24fd-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="d24fd-134">Under **Microsoft 365 Business**väljer du **Uppgradera** om du vill lägga till Microsoft 365 Business i din kundvagn.</span><span class="sxs-lookup"><span data-stu-id="d24fd-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="d24fd-135">I varukorgen:</span><span class="sxs-lookup"><span data-stu-id="d24fd-135">In the cart:</span></span>
    1. <span data-ttu-id="d24fd-136">Vi kommer automatiskt att inkludera licenser för alla dina nuvarande användare.</span><span class="sxs-lookup"><span data-stu-id="d24fd-136">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="d24fd-137">Om du behöver fler eller färre licenser måste du [köpa och tilldela dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="d24fd-137">If you need more or fewer licenses, you need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="d24fd-138">Du kan justera hur du vill betala: månadsvis eller årligen.</span><span class="sxs-lookup"><span data-stu-id="d24fd-138">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="d24fd-139">Välj rullgardinsmenyn för att göra ditt val.</span><span class="sxs-lookup"><span data-stu-id="d24fd-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="d24fd-140">Välj **Gå till kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetoden för det här kontot.</span><span class="sxs-lookup"><span data-stu-id="d24fd-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="d24fd-141">Du kan också lägga till en promo kod här om du har en.</span><span class="sxs-lookup"><span data-stu-id="d24fd-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="d24fd-142">Välj Gör en **beställning** för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="d24fd-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="d24fd-143">Det tar Microsoft några minuter att ställa in dina nya serviceplaner.</span><span class="sxs-lookup"><span data-stu-id="d24fd-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="d24fd-144">Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**.</span><span class="sxs-lookup"><span data-stu-id="d24fd-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="d24fd-145">När planen är klar kan du behöva slutföra några ytterligare installationssteg i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="d24fd-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="d24fd-146">Välj **Start i** navigeringsfönstret om du vill slutföra ytterligare installationssteg.</span><span class="sxs-lookup"><span data-stu-id="d24fd-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="d24fd-147">Du får en proportionell återbetalning för de Office 365-licenser som du inte längre behöver.</span><span class="sxs-lookup"><span data-stu-id="d24fd-147">You'll receive a prorated refund for the Office 365 licenses that you no longer need.</span></span> <span data-ttu-id="d24fd-148">Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har konfigurerat den nya planen.</span><span class="sxs-lookup"><span data-stu-id="d24fd-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="d24fd-149">Skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="d24fd-149">Protect user devices and files</span></span>

<span data-ttu-id="d24fd-150">Nu när Microsoft 365 Business-licenser har tilldelats, slutföra steg för att börja skydda enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="d24fd-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="d24fd-151">Du använder några nya alternativ som ingår i navigeringsfönstret i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="d24fd-151">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="d24fd-152">Gå till \> **Enhetsprinciper**i navigeringsfönstret \*\*\*\* i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d24fd-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="d24fd-153">Välj **Lägg till**på sidan **Enhetsprinciper.**</span><span class="sxs-lookup"><span data-stu-id="d24fd-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="d24fd-154">I **fönstret Lägg** till princip ger principen ett namn (till exempel Skydda arbetsfiler) och välj sedan en **principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="d24fd-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d24fd-155">Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="d24fd-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="d24fd-156">Mer information finns i följande länkar:</span><span class="sxs-lookup"><span data-stu-id="d24fd-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="d24fd-157">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="d24fd-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="d24fd-158">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d24fd-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="d24fd-159">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="d24fd-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="d24fd-160">När du har konfigurerat principer kan du och dina medarbetare konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="d24fd-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="d24fd-161">Om dina Windows-enheter inte redan använder Uppdateringen av Windows Pro Creator måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="d24fd-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="d24fd-162">Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="d24fd-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="d24fd-163">Se [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="d24fd-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
