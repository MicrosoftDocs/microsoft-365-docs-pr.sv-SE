---
title: Verifiera appskyddsinställningar på Android- eller iOS-enheter
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
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 47ce137f785c595992886c756ad85b80957272fe
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594984"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="3b9ba-103">Verifiera appskyddsinställningar på Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="3b9ba-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="3b9ba-104">Följ instruktionerna i följande avsnitt för att verifiera appskyddsinställningar på Android- eller iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="3b9ba-105">Android</span><span class="sxs-lookup"><span data-stu-id="3b9ba-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="3b9ba-106">Kontrollera att appskyddsinställningarna fungerar på användarenheter</span><span class="sxs-lookup"><span data-stu-id="3b9ba-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="3b9ba-107">När du har [angett appkonfigurationer för Android-enheter](app-protection-settings-for-android-and-ios.md) för att skydda apparna kan du utföra stegen nedan för att verifiera att de inställningar du valde fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="3b9ba-108">Kontrollera först att principen gäller för den app där du ska validera den.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="3b9ba-109">I Microsoft 365 Business-[administrationscentret](https://portal.office.com) går du till **Principer** \> **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-109">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="3b9ba-110">Välj **Programprincip för Android** för de inställningar som du skapade vid installationen eller en annan princip som du skapade och kontrollera att den till exempel tillämpas för Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="3b9ba-112">Verifiera Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="3b9ba-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="3b9ba-113">Välj **Redigera** bredvid **Åtkomstkontroll för Office-dokument** i fönstret **Redigera princip**, expandera **Hantera hur användare kommer åt Office-filer på mobila enheter** och se till att **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program** är angiven till **På**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Kontrollera att kräv en PIN-kod eller ett fingeravtryck för att komma åt Office-appar är inställt på På.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="3b9ba-115">Öppna Outlook på användarens Android-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3b9ba-116">Du uppmanas också att ange en PIN-kod eller använda ett fingeravtryck.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="3b9ba-118">Verifiera Återställ PIN-kod efter antal misslyckade försök</span><span class="sxs-lookup"><span data-stu-id="3b9ba-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="3b9ba-119">I fönstret **Redigera princip** väljer du **Redigera** bredvid **Åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att Återställ **PIN-kod efter att antalet misslyckade försök** har angetts till något antal.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="3b9ba-120">Detta är som standard 5.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="3b9ba-121">Öppna Outlook på användarens Android-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3b9ba-122">Ange en felaktig PIN-kod så många gånger som anges i principen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="3b9ba-123">Du ser en uppmaning om att **anger PIN-försöksgräns som nåtts** för att återställa PIN-koden.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="3b9ba-125">Tryck på **Återställ PIN-kod**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-125">Press **Reset PIN**.</span></span> <span data-ttu-id="3b9ba-126">Du uppmanas att logga in med användarens Microsoft 365 Business-autentiseringsuppgifter och sedan behöva ange en ny PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-126">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="3b9ba-127">Verifiera Tvinga användare att spara alla filer i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="3b9ba-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="3b9ba-128">Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **På**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="3b9ba-130">Öppna Outlook på användarens Android-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-131">Öppna ett e-postmeddelande som innehåller en bifogad fil och tryck på nedåtpilikonen bredvid den bifogade filens information.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="3b9ba-133">Det går **inte att spara på enheten** längst ned på skärmen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="3b9ba-135">Det går inte att spara till OneDrive för företag från Android för närvarande. Du kan bara se att funktionen för att spara lokalt är blockerad.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="3b9ba-136">Verifiera Kräv att användare loggar in igen efter att Office-appar har varit inaktiva under en angiven tid</span><span class="sxs-lookup"><span data-stu-id="3b9ba-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="3b9ba-137">I fönstret **Redigera princip** väljer du **Redigera** bredvid **Åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att **Kräv att användarna loggar in igen när Office-appar har varit inaktiva i** vissa minuter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="3b9ba-138">Detta är 30 minuter som standard.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="3b9ba-139">Öppna Outlook på användarens Android-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-p105">Du bör nu se Inkorgen i Outlook. Låt Android-enheten stå oanvänd i minst 30 minuter (eller annan tidsrymd som är längre än vad du angav i principen). Enhetens bildskärm kommer sannolikt att tonas ned.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="3b9ba-143">Få åtkomst till Outlook på Android-enheten igen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="3b9ba-144">Du uppmanas att ange din PIN-kod innan du kan komma åt Outlook igen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="3b9ba-145">Verifiera Skydda arbetsfiler med kryptering</span><span class="sxs-lookup"><span data-stu-id="3b9ba-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="3b9ba-146">Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Skydda arbetsfiler med kryptering** är angiven till **På** och att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **Av**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="3b9ba-147">Öppna Outlook på användarens Android-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-148">Öppna ett e-postmeddelande som innehåller några bifogade filer för bildfiler.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="3b9ba-149">Tryck på nedåtpilikonen bredvid den bifogade filen om du vill spara den.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="3b9ba-p106">Det kan hända att du uppmanas att tillåta Outlook att komma åt foton, media och filer på din enhet. Tryck på **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="3b9ba-153">Längst ned på skärmen väljer du **Spara på enhet** och öppna sedan appen **Galleri**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="3b9ba-p107">Du bör nu se ett sparat, krypterat foto (eller flera, om du sparade flera bifogade bildfiler) i listan. Det kan hända att fotot visas i listan Bilder som en grå ruta med ett vitt utropstecken i en vit cirkel i mitten av den gråa rutan.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="3b9ba-157">Ios</span><span class="sxs-lookup"><span data-stu-id="3b9ba-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="3b9ba-158">Kontrollera att inställningarna för appskydd fungerar på användarnas enheter</span><span class="sxs-lookup"><span data-stu-id="3b9ba-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="3b9ba-159">När du har [angett appkonfigurationer för iOS-enheter](app-protection-settings-for-android-and-ios.md) för att skydda appar kan du utföra stegen nedan för att verifiera att de inställningar du valde fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="3b9ba-160">Kontrollera först att principen gäller för den app där du ska validera den.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="3b9ba-161">I Microsoft 365 Business-[administrationscentret](https://portal.office.com) går du till **Principer** \> **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-161">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="3b9ba-162">Välj **Programprincip för iOS** för de inställningar som du skapade vid installationen eller en annan princip som du skapade och kontrollera att den till exempel tillämpas för Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="3b9ba-164">Verifiera Kräv PIN-kod för åtkomst till Office-program</span><span class="sxs-lookup"><span data-stu-id="3b9ba-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="3b9ba-165">Välj **Redigera** bredvid **Åtkomstkontroll för Office-dokument** i fönstret **Redigera princip**, expandera **Hantera hur användare kommer åt Office-filer på mobila enheter** och se till att **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program** är angiven till **På**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Kontrollera att kräv en PIN-kod eller ett fingeravtryck för att komma åt Office-appar är inställt på På.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="3b9ba-167">Öppna Outlook på användarens iOS-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3b9ba-168">Du uppmanas också att ange en PIN-kod eller använda ett fingeravtryck.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="3b9ba-170">Verifiera Återställ PIN-kod efter antal misslyckade försök</span><span class="sxs-lookup"><span data-stu-id="3b9ba-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="3b9ba-171">I fönstret **Redigera princip** väljer du **Redigera** bredvid **Åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att Återställ **PIN-kod efter att antalet misslyckade försök** har angetts till något antal.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="3b9ba-172">Detta är som standard 5.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="3b9ba-173">Öppna Outlook på användarens iOS-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3b9ba-174">Ange en felaktig PIN-kod så många gånger som anges i principen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="3b9ba-175">Du ser en uppmaning om att **anger PIN-försöksgräns som nåtts** för att återställa PIN-koden.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="3b9ba-177">Tryck på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-177">Press **OK**.</span></span> <span data-ttu-id="3b9ba-178">Du uppmanas att logga in med användarens Microsoft 365 Business-autentiseringsuppgifter och sedan behöva ange en ny PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-178">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="3b9ba-179">Verifiera Tvinga användare att spara alla filer i OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="3b9ba-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="3b9ba-180">Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **På**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="3b9ba-182">Öppna Outlook på användarens iOS-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-183">Öppna ett e-postmeddelande som innehåller en bifogad fil, öppna den bifogade filen och välj **Spara** längst ned på skärmen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="3b9ba-185">Du bör se endast ett alternativ för OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="3b9ba-186">Om inte trycker du på **Lägg till konto** och väljer **OneDrive för företag** på skärmen Lägg till **lagringskonto.**</span><span class="sxs-lookup"><span data-stu-id="3b9ba-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="3b9ba-187">Ange användarens Microsoft 365 Business för att logga in när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-187">Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="3b9ba-188">Tryck på **Spara** och välj **OneDrive för företag**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="3b9ba-189">Verifiera Kräv att användare loggar in igen efter att Office-appar har varit inaktiva under en angiven tid</span><span class="sxs-lookup"><span data-stu-id="3b9ba-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="3b9ba-190">I fönstret **Redigera princip** väljer du **Redigera** bredvid **Åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att **Kräv att användarna loggar in igen när Office-appar har varit inaktiva i** vissa minuter.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="3b9ba-191">Detta är 30 minuter som standard.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="3b9ba-192">Öppna Outlook på användarens iOS-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-p113">Du bör nu se Inkorgen i Outlook. Låt iOS-enheten stå oanvänd i minst 30 minuter (eller annan tidsrymd som är längre än vad du angav i principen). Enhetens bildskärm kommer sannolikt att tonas ned.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="3b9ba-196">Få åtkomst till Outlook på iOS-enheten igen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="3b9ba-197">Du uppmanas att ange din PIN-kod innan du kan komma åt Outlook igen.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="3b9ba-198">Verifiera Skydda arbetsfiler med kryptering</span><span class="sxs-lookup"><span data-stu-id="3b9ba-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="3b9ba-199">Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Skydda arbetsfiler med kryptering** är angiven till **På** och att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **Av**.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="3b9ba-200">Öppna Outlook på användarens iOS-enhet och logga in med användarens Microsoft 365 Business-autentiseringsuppgifter. Ange en PIN-kod om du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="3b9ba-201">Öppna ett e-postmeddelande som innehåller några bifogade filer för bildfiler.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="3b9ba-202">Tryck på den bifogade filen och tryck sedan på alternativet **Spara** under den.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="3b9ba-p114">Öppna appen **Foton** från startskärmen. Du bör nu se ett sparat foto (eller flera, om du sparade flera bifogade bildfiler) som är krypterat.</span><span class="sxs-lookup"><span data-stu-id="3b9ba-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

