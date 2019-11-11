---
title: Uppgradera till Microsoft 365 Business från Office 365 Business Premium
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
ms.openlocfilehash: f3a25746cf123fa471c29084a62a6fcfc1542a02
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231420"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="ad0f2-103">Uppgradera till Microsoft 365 Business från Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ad0f2-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="ad0f2-104">Om du har en [office 365 för Business-prenumeration](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), till exempel Office 365 Business Premium, kan du enkelt uppgradera till Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="ad0f2-105">Uppgradera till Microsoft 365 Business om du vill lägga till:</span><span class="sxs-lookup"><span data-stu-id="ad0f2-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="ad0f2-106">Windows 10 Pro (till datorer som kör Windows 8 eller senare)</span><span class="sxs-lookup"><span data-stu-id="ad0f2-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="ad0f2-107">Enkla kontroller som hanterar affärsdata på enheter</span><span class="sxs-lookup"><span data-stu-id="ad0f2-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="ad0f2-108">Avancerade säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-108">Advanced security capabilities.</span></span>
<span data-ttu-id="ad0f2-109">Läs mer om Microsoft 365 Business på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="ad0f2-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="ad0f2-110">Vad är skillnaden mellan Office 365 Business Premium och Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="ad0f2-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="ad0f2-111">Vi har lagt till en sida-vid-sida-jämförelse av dessa två planer till [Microsoft 365 Business servicebeskrivning](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="ad0f2-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="ad0f2-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="ad0f2-112">Before you get started</span></span>

- <span data-ttu-id="ad0f2-113">**När ska jag välja Upgrade?**</span><span class="sxs-lookup"><span data-stu-id="ad0f2-113">**When should I choose upgrade?**</span></span> <span data-ttu-id="ad0f2-114">Uppgraderingen är rätt val när du vill uppgradera **alla användare** som tilldelats en enda plan.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="ad0f2-115">När du väljer uppgradera får alla plan användare byta till en annan plan samtidigt.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="ad0f2-116">Om du inte vill uppgradera alla som är tilldelade till en enda plan, köpa licenser för den nya planen (i det här fallet Microsoft 365 företag) och [tilldela dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) till varje användare som du vill uppgradera.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="ad0f2-117">**Vissa tillägg kan förhindra uppgradering** Om du försöker starta en uppgradering och har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till det igen senare-om du fortfarande behöver det.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-117">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="ad0f2-118">**Om du förbetalt din plan** Det finns inte en enkel uppgraderingsväg för förbetalda abonnemang.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="ad0f2-119">Du vet om du har en förutbetald plan eftersom du ställer in din plan med ett produkt-ID som du kan ha köpt i en butik.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="ad0f2-120">Kontakta en partner, gå till Microsoft Store eller vänta tills ditt förbetalda abonnemang går ut för att byta till ett nytt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-120">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="ad0f2-121">Uppgradera till Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ad0f2-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="ad0f2-122">Köp dina licenser genom att följa dessa steg i det [nya administratörscentret](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span><span class="sxs-lookup"><span data-stu-id="ad0f2-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="ad0f2-123">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="ad0f2-124">Gå till navigeringsfönstret och välj **fakturerings** \> **produkter & tjänster**.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="ad0f2-125">Hitta din Office 365-prenumeration och välj den för att visa detaljerna.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![En skärmbild visar hur du hittar och väljer din prenumeration i administratörscenter.](media/FindYourSubscription.png)

3. <span data-ttu-id="ad0f2-127">På nästa sida väljer du **Uppgradera**.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-127">On the next page, select **Upgrade**.</span></span> 

      ![En skärmbild visar var du ska välja uppgradering i administratörscenter.](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="ad0f2-129">Om du ser ett meddelande som säger "uppgradera din prenumeration stöds inte med gruppbaserad licensiering i Azure Active Directory", kan du bortse från detta om du inte har en mycket stor organisation.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-129">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="ad0f2-130">Organisationer som har valt det här alternativet kommer att vara medveten om att de använder gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="ad0f2-131">Därefter kan du Visa en lista över Office-planer som du kan uppgradera till.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="ad0f2-132">I det här fallet hittar du Microsoft 365 affärsplan.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="ad0f2-133">Du kan rulla nedåt om du vill se alla Office-appar och-tjänster som ingår i den här planen.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="ad0f2-134">Under **Microsoft 365 Business**väljer du **Uppgradera** för att lägga till Microsoft 365 Business i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="ad0f2-135">I vagnen:</span><span class="sxs-lookup"><span data-stu-id="ad0f2-135">In the cart:</span></span>
    1. <span data-ttu-id="ad0f2-136">Vi inkluderar automatiskt licenser för alla dina nuvarande användare till kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-136">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="ad0f2-137">Om du behöver mer eller mindre licenser måste du [köpa och tilldela dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="ad0f2-137">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="ad0f2-138">Du kan justera hur du vill betala-månad eller år.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-138">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="ad0f2-139">Välj den nedrullningsbara menyn för att göra ditt val.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="ad0f2-140">Välj **gå till kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetoden för det här kontot.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="ad0f2-141">Du kan också lägga till en kampanjkod här om du har en.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="ad0f2-142">Välj **Beställ** för att slutföra köpet.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="ad0f2-143">Det tar Microsoft några minuter att ställa in dina nya service planer.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="ad0f2-144">Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="ad0f2-145">När planen är klar kan du behöva utföra några ytterligare konfigurationssteg i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="ad0f2-146">I navigeringsfönstret väljer du **hem** för att slutföra eventuella ytterligare inställningssteg.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="ad0f2-147">Du får en proportionell återbetalning för Ofifce 365-licenser som du inte längre behöver.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-147">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="ad0f2-148">Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har ställt in den nya planen.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="ad0f2-149">Skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="ad0f2-149">Protect user devices and files</span></span>

<span data-ttu-id="ad0f2-150">Nu när Microsoft 365-företagslicenser har tilldelats, slutför du stegen för att börja skydda enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="ad0f2-151">Du kommer att använda några nya alternativ som ingår i Administrationscenter navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-151">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="ad0f2-152">I administratörscenter, i navigeringsfönstret, gå till **principer**för **enheter** \> .</span><span class="sxs-lookup"><span data-stu-id="ad0f2-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="ad0f2-153">På sidan **enhetsprinciper** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="ad0f2-154">I den **Lägg till princip** fönstret ge principen ett namn (till exempel skydda arbetsfiler), och välj sedan en **Principtyp** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="ad0f2-155">Du kan ställa in användningsprinciper för att skydda filer på Android-och iPhone-enheter, samt Windows 10, och du kan ställa in principer för enhetskonfiguration för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="ad0f2-156">Se följande länkar för mer information:</span><span class="sxs-lookup"><span data-stu-id="ad0f2-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="ad0f2-157">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="ad0f2-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="ad0f2-158">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="ad0f2-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="ad0f2-159">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="ad0f2-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="ad0f2-160">När du har konfigurerat policyer kan du och dina anställda ställa in enheter:</span><span class="sxs-lookup"><span data-stu-id="ad0f2-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="ad0f2-161">Om Windows-enheterna inte redan använder Windows Pro Creator-uppdateringen måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="ad0f2-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="ad0f2-162">Se [Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="ad0f2-163">Se [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="ad0f2-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



