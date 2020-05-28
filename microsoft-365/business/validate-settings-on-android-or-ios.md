---
title: Validera inställningar för appskydd på Android- eller iOS-enheter
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Lär dig hur du validerar inställningarna för skydd av Microsoft 365 Business Premium-appar på dina Android- eller iOS-enheter.
ms.openlocfilehash: d4b8ec3ff3a15c25133b20d437249611530977a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403379"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Validera inställningar för appskydd på Android- eller iOS-enheter

Följ instruktionerna i följande avsnitt för att validera inställningar för appskydd på Android- eller iOS-enheter.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Kontrollera att appskyddsinställningarna fungerar på användarenheter

När du har [angett appkonfigurationer för Android-enheter](app-protection-settings-for-android-and-ios.md) för att skydda apparna kan du utföra stegen nedan för att verifiera att de inställningar du valde fungerar som de ska. 
  
Kontrollera först att principen gäller för appen där du ska validera den.
  
1. Gå till [policyn](https://portal.office.com) **För redigering av principer** i Microsoft 365 Business \> **Edit policy**Premium.
    
2. Välj **Programprincip för Android** för de inställningar som du skapade vid installationen, eller en annan princip som du har skapat, och kontrollera att den tillämpas för Outlook, till exempel. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Verifiera Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program

Välj **Redigera** bredvid **Åtkomstkontroll för Office-dokument** i fönstret **Redigera princip**, expandera **Hantera hur användare kommer åt Office-filer på mobila enheter** och se till att **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program** är angiven till **På**.
  
![Kontrollera att Kräv en PIN-kod eller ett fingeravtryck för att komma åt Office-appar är inställt på På.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens Android-enhet.
    
2. Du uppmanas också att ange en PIN-kod eller använda ett fingeravtryck.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Verifiera Återställ PIN-kod efter antal misslyckade försök

I **fönstret Redigera princip** väljer du **Redigera bredvid** **åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att Återställ **PIN-kod efter att antalet misslyckade försök** har angetts till ett visst antal. Detta är 5 som standard. 
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens Android-enhet.
    
2. Ange en felaktig PIN-kod så många gånger som anges i principen. Du ser en uppmaning om att ange **PIN-försöksbegränsning som har nåtts** för att återställa PIN-koden. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Tryck på **Återställ PIN-kod**. Du uppmanas att logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter och sedan ange en ny PIN-kod.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Verifiera Tvinga användare att spara alla filer i OneDrive för företag

Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **På**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens Android-enhet och ange en PIN-kod om så önskas.
    
2. Öppna ett e-postmeddelande som innehåller en bifogad fil och tryck på nedåtpilikonen bredvid den bifogade filens information.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Det går inte **att spara** på enheten längst ned på skärmen. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Det går inte att spara till OneDrive för företag från Android för närvarande. Du kan bara se att funktionen för att spara lokalt är blockerad. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Verifiera Kräv att användare loggar in igen efter att Office-appar har varit inaktiva under en angiven tid

I **fönstret Redigera princip** väljer du **Redigera bredvid** **åtkomstkontroll för Office-dokument,** utöka **Hantera hur användare kommer åt Office-filer på mobila enheter**och se till att Kräva att användare loggar in igen efter att **Office-appar har varit inaktiva för** är inställd på ett visst antal minuter. Detta är 30 minuter som standard. 
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens Android-enhet och ange en PIN-kod om så önskas.
    
2. Du bör nu se Inkorgen i Outlook. Låt Android-enheten stå oanvänd i minst 30 minuter (eller annan tidsrymd som är längre än vad du angav i principen). Enhetens bildskärm kommer sannolikt att tonas ned.
    
3. Öppna Outlook på Android-enheten igen.
    
4. Du uppmanas att ange din PIN-kod innan du kan komma åt Outlook igen.
    
### <a name="validate-protect-work-files-with-encryption"></a>Verifiera Skydda arbetsfiler med kryptering

Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Skydda arbetsfiler med kryptering** är angiven till **På** och att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **Av**.
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens Android-enhet och ange en PIN-kod om så önskas.
    
2. Öppna ett e-postmeddelande som innehåller några bifogade bildfiler.
    
3. Tryck på nedåtpilikonen bredvid den bifogade filen om du vill spara den.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Det kan hända att du uppmanas att tillåta Outlook att komma åt foton, media och filer på din enhet. Tryck på **Tillåt**.
    
5. Längst ned på skärmen väljer du **Spara på enhet** och öppna sedan appen **Galleri**. 
    
6. Du bör nu se ett sparat, krypterat foto (eller flera, om du sparade flera bifogade bildfiler) i listan. Det kan hända att fotot visas i listan Bilder som en grå ruta med ett vitt utropstecken i en vit cirkel i mitten av den gråa rutan.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>Ios
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Kontrollera att inställningarna för appskydd fungerar på användarnas enheter

När du har [angett appkonfigurationer för iOS-enheter](app-protection-settings-for-android-and-ios.md) för att skydda appar kan du utföra stegen nedan för att verifiera att de inställningar du valde fungerar som de ska. 
  
Kontrollera först att principen gäller för appen där du ska validera den.
  
1. Gå till [policyn](https://portal.office.com) **För redigering av principer** i Microsoft 365 Business \> **Edit policy**Premium.
    
2. Välj **Programprincip för iOS** för de inställningar som du skapade vid installationen, eller en annan princip som du har skapat, och kontrollera att den tillämpas för Outlook till exempel. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Verifiera Kräv PIN-kod för åtkomst till Office-program

Välj **Redigera** bredvid **Åtkomstkontroll för Office-dokument** i fönstret **Redigera princip**, expandera **Hantera hur användare kommer åt Office-filer på mobila enheter** och se till att **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program** är angiven till **På**.
  
![Kontrollera att Kräv en PIN-kod eller ett fingeravtryck för att komma åt Office-appar är inställt på På.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens iOS-enhet.
    
2. Du uppmanas också att ange en PIN-kod eller använda ett fingeravtryck.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Verifiera Återställ PIN-kod efter antal misslyckade försök

I **fönstret Redigera princip** väljer du **Redigera bredvid** **åtkomstkontroll för Office-dokument,** expanderar **Hantera hur användare kommer åt Office-filer på mobila enheter**och kontrollerar att Återställ **PIN-kod efter att antalet misslyckade försök** har angetts till ett visst antal. Detta är 5 som standard. 
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens iOS-enhet.
    
2. Ange en felaktig PIN-kod så många gånger som anges i principen. Du ser en uppmaning om att ange **PIN-försöksbegränsning som har nåtts** för att återställa PIN-koden. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Tryck på **OK**. Du uppmanas att logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter och sedan ange en ny PIN-kod.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Verifiera Tvinga användare att spara alla filer i OneDrive för företag

Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **På**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens iOS-enhet och ange en PIN-kod om så önskas.
    
2. Öppna ett e-postmeddelande som innehåller en bifogad fil, öppna den bifogade filen och välj **Spara** längst ned på skärmen. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Du bör se endast ett alternativ för OneDrive för företag. Om inte trycker du på **Lägg till konto** och väljer **OneDrive för företag** på skärmen Lägg till **lagringskonto.** Ange slutanvändarens Microsoft 365 Business Premium för att logga in när du uppmanas att göra det. 
    
    Tryck på **Spara** och välj **OneDrive för företag**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Verifiera Kräv att användare loggar in igen efter att Office-appar har varit inaktiva under en angiven tid

I **fönstret Redigera princip** väljer du **Redigera bredvid** **åtkomstkontroll för Office-dokument,** utöka **Hantera hur användare kommer åt Office-filer på mobila enheter**och se till att Kräva att användare loggar in igen efter att **Office-appar har varit inaktiva för** är inställd på ett visst antal minuter. Detta är 30 minuter som standard. 
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens iOS-enhet och ange en PIN-kod om så önskas.
    
2. Du bör nu se Inkorgen i Outlook. Låt iOS-enheten stå oanvänd i minst 30 minuter (eller annan tidsrymd som är längre än vad du angav i principen). Enhetens bildskärm kommer sannolikt att tonas ned.
    
3. Öppna Outlook på iOS-enheten igen.
    
4. Du uppmanas att ange din PIN-kod innan du kan komma åt Outlook igen.
    
### <a name="validate-protect-work-files-with-encryption"></a>Verifiera Skydda arbetsfiler med kryptering

Välj **Redigera** bredvid **Skydd mot förlorade eller stulna enheter** i fönstret **Redigera princip**, expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna** och se till att **Skydda arbetsfiler med kryptering** är angiven till **På** och att **Tvinga användare att spara alla filer i OneDrive för företag** är angiven till **Av**.
  
1. Öppna Outlook och logga in med användarens Microsoft 365 Business Premium-autentiseringsuppgifter på användarens iOS-enhet och ange en PIN-kod om så önskas.
    
2. Öppna ett e-postmeddelande som innehåller några bifogade bildfiler.
    
3. Tryck på den bifogade filen och tryck sedan på alternativet **Spara** under den. 
    
4. Öppna appen **Foton** från startskärmen. Du bör nu se ett sparat foto (eller flera, om du sparade flera bifogade bildfiler) som är krypterat. 
    
---

