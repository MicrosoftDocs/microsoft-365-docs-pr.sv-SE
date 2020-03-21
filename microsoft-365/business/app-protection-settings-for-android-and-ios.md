---
title: Ange inställningar för appskydd för Android- eller iOS-enheter
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Lär dig hur du skapar, redigerar eller tar bort en apphanteringsprincip och skyddar arbetsfiler på Android- eller iOS-enheter.
ms.openlocfilehash: 0adb103ac3bef72e340c1f5daf54a6b8a184d85c
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894289"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="40455-103">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="40455-103">Set app protection settings for Android or iOS devices</span></span>

![Banner som https://aka.ms/aboutM365previewpekar på .](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="40455-105">Skapa en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="40455-105">Create an app management policy</span></span>

1. <span data-ttu-id="40455-106">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="40455-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="40455-107">Välj Enhetsprinciper **Policies** \> **Lägg till**i den vänstra **navigeringsskeppet** \> .</span><span class="sxs-lookup"><span data-stu-id="40455-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="40455-108">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="40455-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="40455-109">Under **Principtyp**väljer du **Programhantering för Android** eller **Programhantering för iOS**, beroende på vilken uppsättning principer du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="40455-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="40455-110">Expandera **Skydda arbetsfiler när enheter försvinner eller blir stulna** och Hantera hur användare kommer åt **Office-filer på mobila enheter**.</span><span class="sxs-lookup"><span data-stu-id="40455-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="40455-111">Konfigurera inställningarna som du vill.</span><span class="sxs-lookup"><span data-stu-id="40455-111">Configure the settings how you would like.</span></span> <span data-ttu-id="40455-112">**Hantera hur användare kommer åt Office-filer på mobila enheter** **som** standard, men vi rekommenderar att du aktiverar **den** och accepterar standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="40455-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="40455-113">Mer information finns i [Tillgängliga inställningar](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="40455-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="40455-114">Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="40455-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="40455-116">**Vem får de här inställningarna?**</span><span class="sxs-lookup"><span data-stu-id="40455-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="40455-117">Om du inte vill använda standardgruppen **Alla användare** väljer du **Ändra**, välj \> de säkerhetsgrupper som får dessa inställningar **Välj**.</span><span class="sxs-lookup"><span data-stu-id="40455-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="40455-118">Välj **Klar** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="40455-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="40455-119">Redigera en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="40455-119">Edit an app management policy</span></span>

1. <span data-ttu-id="40455-120">På **policykortet** väljer du **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="40455-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="40455-121">I fönstret **Redigera princip** väljer du den princip som du vill ändra</span><span class="sxs-lookup"><span data-stu-id="40455-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="40455-122">Välj **Redigera** bredvid varje inställning för att ändra värdena i principen.</span><span class="sxs-lookup"><span data-stu-id="40455-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="40455-123">När du ändrar ett värde sparas det automatiskt i principen.</span><span class="sxs-lookup"><span data-stu-id="40455-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="40455-124">När du är klar stänger du **fönstret Redigera princip.**</span><span class="sxs-lookup"><span data-stu-id="40455-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="40455-125">Ta bort en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="40455-125">Delete an app management policy</span></span>

1. <span data-ttu-id="40455-126">På sidan **Principer** väljer du en princip och tar sedan **bort**.</span><span class="sxs-lookup"><span data-stu-id="40455-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="40455-127">I **fönstret Ta bort princip** väljer du **Bekräfta** om du vill ta bort principen eller principerna som du har valt.</span><span class="sxs-lookup"><span data-stu-id="40455-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="40455-128">Tillgängliga inställningar</span><span class="sxs-lookup"><span data-stu-id="40455-128">Available settings</span></span>

<span data-ttu-id="40455-129">Följande tabeller innehåller detaljerad information om tillgängliga inställningar för att skydda arbetsfiler på enheter och de inställningar som styr hur användare kommer åt Office-filer från sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="40455-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="40455-130">Mer information finns i [Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="40455-130">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="40455-131">Inställningar som skyddar arbetsfiler</span><span class="sxs-lookup"><span data-stu-id="40455-131">Settings that protect work files</span></span>

<span data-ttu-id="40455-132">Följande inställningar är tillgängliga för att skydda arbetsfiler om en användares enhet försvinner eller blir stulen:</span><span class="sxs-lookup"><span data-stu-id="40455-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="40455-133">Inställning</span><span class="sxs-lookup"><span data-stu-id="40455-133">Setting</span></span>  <br/> |<span data-ttu-id="40455-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="40455-134">Description</span></span>  <br/> |
|<span data-ttu-id="40455-135">Ta bort arbetsﬁler från en inaktiv enheten efter så många dagar</span><span class="sxs-lookup"><span data-stu-id="40455-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="40455-136">Om en enhet inte används under det antal dagar som du anger här tas alla arbetsfiler som lagras på enheten bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="40455-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="40455-137">Tvinga användare att spara alla filer i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="40455-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="40455-138">Om den här inställningen är **På**är OneDrive för företag den enda tillgängliga sparplatsen för arbetsfiler.</span><span class="sxs-lookup"><span data-stu-id="40455-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="40455-139">Kryptera arbetsfiler</span><span class="sxs-lookup"><span data-stu-id="40455-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="40455-140">Behåll den här inställningen **På** så att arbetsfiler skyddas av kryptering.</span><span class="sxs-lookup"><span data-stu-id="40455-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="40455-141">Även om enheten försvinner eller blir stulen kan ingen läsa dina företagsdata.</span><span class="sxs-lookup"><span data-stu-id="40455-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="40455-142">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="40455-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="40455-143">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="40455-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="40455-144">Inställning</span><span class="sxs-lookup"><span data-stu-id="40455-144">Setting</span></span>  <br/> |<span data-ttu-id="40455-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="40455-145">Description</span></span>  <br/> |
|<span data-ttu-id="40455-146">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="40455-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="40455-147">Om den här inställningen är **På** användarna måste tillhandahålla en annan form av autentisering, utöver sitt användarnamn och lösenord, innan de kan använda Office-appar på sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="40455-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="40455-148">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="40455-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="40455-149">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="40455-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="40455-150">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="40455-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="40455-151">Den här inställningen avgör hur länge en användare kan vara inaktiv innan han eller hon uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="40455-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="40455-152">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="40455-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="40455-p105">Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  </span><span class="sxs-lookup"><span data-stu-id="40455-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="40455-156">Tillåt inte att användare kopierar innehåll från Office-appar till personliga appar</span><span class="sxs-lookup"><span data-stu-id="40455-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="40455-157">Vi tillåter inte detta som standard, men om inställningen är **På** kan användaren kopiera information i en arbetsfil till en privat fil.</span><span class="sxs-lookup"><span data-stu-id="40455-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="40455-158">Om inställningen är **Av**, kan användaren inte kopiera information från en arbetskonto till ett privat program eller konto.</span><span class="sxs-lookup"><span data-stu-id="40455-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
