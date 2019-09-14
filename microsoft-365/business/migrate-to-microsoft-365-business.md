---
title: Migrera till Microsoft 365 Business från Office 365 Business Premium
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig hur du flyttar ditt företag till Microsoft 365 Business.
ms.openlocfilehash: a3f77bd18b9b900151c50f923b705e4ff0150519
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982450"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="a8058-103">Migrera till Microsoft 365 Business från Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="a8058-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="a8058-104">Om du redan har en Office 365 för Business-prenumeration, till exempel Office 365 Business Premium, kan du enkelt lägga till licenser till Microsoft 365 Business och tilldela dem till vissa eller alla användare.</span><span class="sxs-lookup"><span data-stu-id="a8058-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8058-105">Du kan inte använda knappen [växla planer](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) för att uppgradera till Microsoft 365 Business ännu.</span><span class="sxs-lookup"><span data-stu-id="a8058-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="a8058-106">Lägg till Microsoft 365 Business-licenser</span><span class="sxs-lookup"><span data-stu-id="a8058-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="a8058-107">Du har två sätt att få Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a8058-107">You have two ways to get Microsoft 365 Business.</span></span> <span data-ttu-id="a8058-108">En partner kan köpa Microsoft 365 Business åt dig från [Microsoft Partner Center](get-microsoft-365-business.md).</span><span class="sxs-lookup"><span data-stu-id="a8058-108">A partner can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md).</span></span> <span data-ttu-id="a8058-109">Din partner kan också hjälpa dig att övergå till Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a8058-109">Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="a8058-110">Om du hanterar din egen prenumeration kan du [Kontakta sales](https://www.microsoft.com/microsoft-365/business) för att köpa Microsoft 365 Business-licenser.</span><span class="sxs-lookup"><span data-stu-id="a8058-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="a8058-111">Se [lägga till, ändra eller ta bort en prenumeration Advisor-partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) för att ta reda på hur du kan börja arbeta med en partner.</span><span class="sxs-lookup"><span data-stu-id="a8058-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="a8058-112">Om du får en länk för att köpa dina licenser, kommer du att gå igenom en guide som den nedan.</span><span class="sxs-lookup"><span data-stu-id="a8058-112">If you are given a link to purchase your licences, you will walk through a wizard like the one below.</span></span> <span data-ttu-id="a8058-113">Välj **Ja, Lägg till det i mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="a8058-113">Choose **Yes, add it to my account**.</span></span> <span data-ttu-id="a8058-114">Du kan också välja antalet licenser och betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="a8058-114">You can also pick the number of licences and the method of payment.</span></span>
  
![På länken Microsoft 365 Business Direct-köp väljer du att lägga till ditt nuvarande konto eller registrerar dig för ett nytt konto.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="a8058-116">Tilldela Microsoft 365-licenser</span><span class="sxs-lookup"><span data-stu-id="a8058-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="a8058-117">När du har köpt nya licenser, och detta är första gången du gjorde, visas den setup banner för Microsoft 365 företag på toppen av administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="a8058-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a8058-118">Banner för inställningar är en möjlighet att lägga till nya användare, en ny domän och migrera e-post för nya användare.</span><span class="sxs-lookup"><span data-stu-id="a8058-118">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="a8058-119">Om du inte planerar att göra något, bör du fortfarande gå igenom guiden och välja standardalternativ för att få det att försvinna från admin hemsida.</span><span class="sxs-lookup"><span data-stu-id="a8058-119">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Välj Starta installationen på den Microsoft 365 företag är redo att ställa in banner.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="a8058-121">Välj **Gör inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a8058-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="a8058-122">På sidan **Anpassa din inloggning och e-post** kan du lägga till en domän genom att välja **Anslut en domän som du redan äger** om du vill använda den här möjligheten för att lägga till en annan domän i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="a8058-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="a8058-123">Om du redan har konfigurerat en domän, kommer det andra fältet att indikera det och kommer att **säga Fortsätt att använda** \< _ditt domännamn_ \> **för e-post och inloggning**.  </span><span class="sxs-lookup"><span data-stu-id="a8058-123">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="a8058-124">Om du inte har konfigurerat en domän med din prenumeration, kommer det att **säga fortsätta att använda** \< _ditt företag Name.onmicrosoft.com_ \> **för e-post och logga in**.  </span><span class="sxs-lookup"><span data-stu-id="a8058-124">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="a8058-125">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a8058-125">Choose **Next**.</span></span>
    
    ![På sidan Anpassa din inloggning och e-post väljer du att antingen lägga till en domän eller använder den som du har använt.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="a8058-127">På sidan **Lägg till nya användare** kan du lägga till nya användare om du har nya medarbetare som du vill tilldela Microsoft 365 Business-licenser till.</span><span class="sxs-lookup"><span data-stu-id="a8058-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="a8058-128">Om du inte har nya medarbetare att lägga till och vill tilldela licenser till befintliga användare väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a8058-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="a8058-129">På sidan \* \* migrera e-postmeddelanden \* \* kan du välja att migrera e-post för alla nya användare som du lade till i steg 3.</span><span class="sxs-lookup"><span data-stu-id="a8058-129">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="a8058-130">Du kan hoppa över det här steget också.</span><span class="sxs-lookup"><span data-stu-id="a8058-130">You can skip this step also.</span></span> <span data-ttu-id="a8058-131">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a8058-131">Choose **Next**.</span></span>
    
5. <span data-ttu-id="a8058-132">På den sista sidan väljer **du gå till administratörscenter**och fortsätter installationen där.</span><span class="sxs-lookup"><span data-stu-id="a8058-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="a8058-133">Gå till **användare** \> **aktiva användare**i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="a8058-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="a8058-134">Välj den användare som du vill tilldela **Microsoft 365 Business** -licensen till och välj sedan **Redigera** bredvid **produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="a8058-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![I användarkortet väljer du Redigera bredvid produktlicenser.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="a8058-136">I **produktlicenser** Slide **Microsoft 365 Business** till **på** \> **Spara**, och **Stäng**sedan.</span><span class="sxs-lookup"><span data-stu-id="a8058-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="a8058-137">När du har köpt den första licensen för Microsoft 365-företag kan du nu också lägga till mer i **fakturering** \> **inköpstjänster**.</span><span class="sxs-lookup"><span data-stu-id="a8058-137">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**.</span></span> <span data-ttu-id="a8058-138">På sidan **Köp tjänster** kan du klicka på ellipserna på **Microsoft 365 visitkortet** och välja **ändra Licenskvantitet** för att köpa mer.</span><span class="sxs-lookup"><span data-stu-id="a8058-138">On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="a8058-139">Skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="a8058-139">Protect user devices and files</span></span>

<span data-ttu-id="a8058-140">När du har tilldelat licenser till Microsoft 365 Business kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="a8058-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="a8058-141">I administratörscenter, i det vänstra navigeringsfältet, gå till \*\*\*\* \> **principer**för enheter.</span><span class="sxs-lookup"><span data-stu-id="a8058-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="a8058-142">På sidan **enhetsprinciper** väljer **du Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a8058-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="a8058-143">I den **Lägg till princip** fönstret ge principen ett namn och välj sedan en **Principtyp** från listrutan.</span><span class="sxs-lookup"><span data-stu-id="a8058-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="a8058-144">Du kan ställa in användningsprinciper för att skydda filer på Android-och iPhone-enheter, samt Windows 10, och du kan ställa in principer för enhetskonfiguration för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="a8058-144">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="a8058-145">Se följande länkar för mer information:</span><span class="sxs-lookup"><span data-stu-id="a8058-145">See the following links for details:</span></span>
    
  - [<span data-ttu-id="a8058-146">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="a8058-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="a8058-147">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="a8058-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="a8058-148">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="a8058-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![I den Lägg till princip rutan, ange ett namn för den och välj principtypen från den nedrullningsbara menyn.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="a8058-150">När du har konfigurerat policyer kan du och dina anställda ställa in enheter:</span><span class="sxs-lookup"><span data-stu-id="a8058-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="a8058-151">Om Windows inte redan finns på Windows Pro Creator Update måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="a8058-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="a8058-152">Se [Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="a8058-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="a8058-153">Se [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="a8058-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="a8058-154">Om du vill installera Office-klientappar automatiskt, se [Förbered för Office-klientdistribution av Microsoft 365 Business](prepare-for-office-client-deployment.md) och [Installera eller avinstallera Office på Windows 10-enheter automatiskt](auto-install-or-uninstall-office.md).</span><span class="sxs-lookup"><span data-stu-id="a8058-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


