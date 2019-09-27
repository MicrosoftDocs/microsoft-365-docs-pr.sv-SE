---
title: Ange inställningar för appskydd för Android- eller iOS-enheter
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Lär dig hur du skapar, redigerar eller tar bort en apphanteringsprincip och skyddar arbetsfiler på Android-eller iOS-enheter.
ms.openlocfilehash: 68a338ffb4f9b6cab16c677f80d27481ccec4bd8
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287704"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="3ec2e-103">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="3ec2e-103">Set app protection settings for Android or iOS devices</span></span>

![Banderoll som pekar https://aka.ms/aboutM365previewpå.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="3ec2e-105">Skapa en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="3ec2e-105">Create an app management policy</span></span>

1. <span data-ttu-id="3ec2e-106">Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="3ec2e-107">I det vänstra navigeringsfältet väljer du **enhets** \> **principer** \> **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="3ec2e-108">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="3ec2e-109">Under **Typ av princip** väljer du **Programhantering för Android** eller **Programhantering för iOS** beroende på vilken uppsättning principer du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="3ec2e-110">Expandera **Skydda filer om enheter försvinner eller blir stulna** och **Hantera hur användare får åtkomst till Office-filer på mobila enheter** \> konfigurera inställningar efter eget önskemål.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="3ec2e-111">**Styr hur användare får åtkomst till Office-filer på mobila enheter** är **Av** som standard, men vi rekommenderar att du aktiverar det med **På** och godkänner standardvärdena.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="3ec2e-112">Se [tillgängliga inställningar](#available-settings) för mer information.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="3ec2e-113">Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="3ec2e-p102">**Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla användare** (standard) väljer du **Ändra** och anger vilka säkerhetsgrupper som får dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="3ec2e-117">Välj **Klar** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="3ec2e-118">Redigera en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="3ec2e-118">Edit an app management policy</span></span>

1. <span data-ttu-id="3ec2e-119">På kortet **principer** väljer du **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="3ec2e-120">I fönstret **Redigera princip** väljer du den princip som du vill ändra</span><span class="sxs-lookup"><span data-stu-id="3ec2e-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="3ec2e-p103">Välj **Redigera** bredvid varje inställning för att ändra värdena i principen. Principen uppdateras automatiskt när du ändrar ett värde</span><span class="sxs-lookup"><span data-stu-id="3ec2e-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="3ec2e-123">Stäng fönstret **Redigera princip** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="3ec2e-124">Ta bort en princip för programhantering</span><span class="sxs-lookup"><span data-stu-id="3ec2e-124">Delete an app management policy</span></span>

1. <span data-ttu-id="3ec2e-125">På den **principer** sidan, Välj en princip och sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="3ec2e-126">På den **ta bort princip** fönstret Välj **Bekräfta** att ta bort den princip eller principer som du har valt.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="3ec2e-127">Tillgängliga inställningar</span><span class="sxs-lookup"><span data-stu-id="3ec2e-127">Available settings</span></span>

<span data-ttu-id="3ec2e-128">Följande tabeller ger detaljerad information om vilka inställningar som finns för att skydda filer på enheter, och inställningarna som styr hur användare får åtkomst till Office-filer från sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="3ec2e-129">Mer information finns i artikeln om [hur skyddsfunktioner i Microsoft 365 Business mappas till Intune-inställningarna](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3ec2e-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="3ec2e-130">Inställningar som skyddar arbetsfiler</span><span class="sxs-lookup"><span data-stu-id="3ec2e-130">Settings that protect work files</span></span>

<span data-ttu-id="3ec2e-131">Följande inställningar är tillgängliga för att skydda arbetsfiler om en användares enhet försvinner eller blir stulen:</span><span class="sxs-lookup"><span data-stu-id="3ec2e-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3ec2e-132">Inställning</span><span class="sxs-lookup"><span data-stu-id="3ec2e-132">Setting</span></span>  <br/> |<span data-ttu-id="3ec2e-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3ec2e-133">Description</span></span>  <br/> |
|<span data-ttu-id="3ec2e-134">Ta bort arbetsﬁler från en inaktiv enheten efter så många dagar</span><span class="sxs-lookup"><span data-stu-id="3ec2e-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="3ec2e-135">Om en enhet inte används under så många dagar som du anger här raderas alla arbetsfiler från enheten automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="3ec2e-136">Tvinga användare att spara alla filer i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="3ec2e-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="3ec2e-137">Om den här inställningen är **På**, kommer filer bara att kunna sparas till OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="3ec2e-138">Kryptera arbetsfiler</span><span class="sxs-lookup"><span data-stu-id="3ec2e-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="3ec2e-p104">Behåll den här inställningen **På** så att arbetsfiler skyddas av kryptering. Om enheten försvinner eller blir stulen kommer ingen att kunna läsa företagets data.  </span><span class="sxs-lookup"><span data-stu-id="3ec2e-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="3ec2e-141">Inställningar som styr hur användare kommer åt Office-filer på mobila enheter</span><span class="sxs-lookup"><span data-stu-id="3ec2e-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="3ec2e-142">Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:</span><span class="sxs-lookup"><span data-stu-id="3ec2e-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3ec2e-143">Inställning</span><span class="sxs-lookup"><span data-stu-id="3ec2e-143">Setting</span></span>  <br/> |<span data-ttu-id="3ec2e-144">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3ec2e-144">Description</span></span>  <br/> |
|<span data-ttu-id="3ec2e-145">Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="3ec2e-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="3ec2e-146">Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="3ec2e-147">Återställ PIN-kod när inloggningen misslyckas så här många gånger</span><span class="sxs-lookup"><span data-stu-id="3ec2e-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="3ec2e-148">Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="3ec2e-149">Kräv att användare loggar in igen efter att Office-appar har varit inaktiva</span><span class="sxs-lookup"><span data-stu-id="3ec2e-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="3ec2e-150">Den här inställningen bestämmer hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="3ec2e-151">Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter</span><span class="sxs-lookup"><span data-stu-id="3ec2e-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="3ec2e-p105">Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  </span><span class="sxs-lookup"><span data-stu-id="3ec2e-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="3ec2e-155">Tillåt användare att kopiera innehåll från Office-program till personliga program</span><span class="sxs-lookup"><span data-stu-id="3ec2e-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="3ec2e-156">Vi tillåter inte detta som standard, men om inställningen är **På** kan användaren kopiera information i en arbetsfil till en privat fil.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="3ec2e-157">Om inställningen är **Av**, kan användaren inte kopiera information från en arbetskonto till ett privat program eller konto.</span><span class="sxs-lookup"><span data-stu-id="3ec2e-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

