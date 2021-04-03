---
title: Ange inställningar för appskydd för Android- eller iOS-enheter
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Lär dig hur du skapar, redigerar eller tar bort en princip för apphantering och skyddar arbetsfiler på Android- eller iOS-enheter.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580303"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Ange inställningar för appskydd för Android- eller iOS-enheter

Den här artikeln gäller Microsoft 365 Business Premium.

## <a name="create-an-app-management-policy"></a>Skapa en princip för programhantering

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Välj Enheter principer Lägg till **i** \> **navigeringsfältet** \> **till vänster.**
  
3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Under **Principtyp** väljer du **Programhantering för Android** eller **Programhantering för iOS,** beroende på vilken uppsättning principer du vill skapa. 
    
5. Expandera **Skydda arbetsfiler om enheter försvinner eller blir stulna och** Hantera hur användare får åtkomst till **Office-filer på mobila enheter.** Konfigurera inställningarna som du vill. **Hantera hur användare kommer åt Office-filer** på mobila enheter är Av som standard, men vi rekommenderar att du aktiverar det **med** På och godkänner standardvärdena.  Mer information finns i [Tillgängliga inställningar](#available-settings). 
    
    Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. **Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla** användare som standard väljer du **Ändra**, väljer de säkerhetsgrupper som får de här inställningarna \> **Välj**.
    
7. Välj **Klar** för att spara principen och tilldela den till enheter. 
    
## <a name="edit-an-app-management-policy"></a>Redigera en princip för programhantering

1. På kortet **Principer** väljer du **Redigera princip**.
    
2. I fönstret **Redigera princip** väljer du den princip som du vill ändra 
    
3. Välj **Redigera** bredvid varje inställning för att ändra värdena i principen. När du ändrar ett värde sparas det automatiskt i principen.
    
4. När du är klar stänger du **fönstret Redigera** princip. 
    
## <a name="delete-an-app-management-policy"></a>Ta bort en princip för programhantering

1. Välj en **princip** och sedan Ta bort på sidan **Principer.**
    
2. I fönstret **Ta bort princip** väljer du Bekräfta **för** att ta bort principen eller principerna du valt. 
    
## <a name="available-settings"></a>Tillgängliga inställningar

Följande tabeller innehåller detaljerad information om vilka inställningar som är tillgängliga för att skydda arbetsfiler på enheter och de inställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter.
  
 Mer information finns i Hur [mappar skyddsfunktioner i Microsoft 365 Business Premium till Intune-inställningar.](map-protection-features-to-intune-settings.md) 
  
### <a name="settings-that-protect-work-files"></a>Inställningar som skyddar arbetsfiler

Följande inställningar är tillgängliga för att skydda arbetsfiler om en användares enhet försvinner eller blir stulen:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Ta bort arbetsﬁler från en inaktiv enheten efter så många dagar  <br/> |Om en enhet inte används under det antal dagar som du anger här tas alla arbetsfiler som lagras på enheten bort automatiskt.  <br/> |
|Tvinga användare att spara alla filer i OneDrive för företag  <br/> |Om den här inställningen **är På** är OneDrive för företag den enda tillgängliga platsen att spara filer på.  <br/> |
|Kryptera arbetsfiler  <br/> |Behåll den här inställningen **På** så att arbetsfiler skyddas av kryptering. Även om enheten försvinner eller blir stulen kan ingen läsa företagets data.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Inställningar som styr hur användare kommer åt Office-filer på mobila enheter

Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om den här inställningen **är På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-apparna på sina mobila enheter.<br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen bestämmer hur länge en användare kan vara inaktiv innan de uppmanas att logga in igen.  <br/> |
|Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter  <br/> |Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  <br/> |
|Tillåt inte användare att kopiera innehåll från Office-program till personliga program  <br/> |Vi tillåter inte detta som standard, men om inställningen är **På** kan användaren kopiera information i en arbetsfil till en privat fil. Om inställningen är **Av**, kan användaren inte kopiera information från en arbetskonto till ett privat program eller konto.  <br/> |
