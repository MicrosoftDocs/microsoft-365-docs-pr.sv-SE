---
title: Ange inställningar för appskydd för Android- eller iOS-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Lär dig skapa, redigera eller ta bort en princip för hantering av app och skydda arbete filer på Android eller iOS-enheter.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983669"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Ange inställningar för appskydd för Android- eller iOS-enheter

## <a name="create-an-app-management-policy"></a>Skapa en princip för programhantering

1. Logga in på [Microsoft 365 Business](https://portal.office.com) som global administratör. 
    
2. I Administrationscenter väljer du **Lägg till princip** från kortet **Enheter**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Under **Typ av princip** väljer du **Programhantering för Android** eller **Programhantering för iOS** beroende på vilken uppsättning principer du vill skapa. 
    
5. Expandera **Skydda filer om enheter försvinner eller blir stulna** och **Hantera hur användare får åtkomst till Office-filer på mobila enheter** \> konfigurera inställningar efter eget önskemål. **Styr hur användare får åtkomst till Office-filer på mobila enheter** är **Av** som standard, men vi rekommenderar att du aktiverar det med **På** och godkänner standardvärdena. Se [Tillgängliga inställningar](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) för mer information. 
    
    Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. **Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla användare** (standard) väljer du **Ändra** och anger vilka säkerhetsgrupper som får dessa inställningar \> **Välj**.
    
7. Välj **Klar** för att spara principen och tilldela den till enheter. 
    
## <a name="edit-an-app-management-policy"></a>Redigera en princip för programhantering

1. Välj **Redigera principen**på kortet **principer** .
    
2. I fönstret **Redigera princip** väljer du den princip som du vill ändra 
    
3. Välj **Redigera** bredvid varje inställning för att ändra värdena i principen. Principen uppdateras automatiskt när du ändrar ett värde 
    
4. Stäng fönstret **Redigera princip** när du är klar. 
    
## <a name="delete-an-app-management-policy"></a>Ta bort en princip för programhantering

1. Välj **Ta bort principen**på kortet **principer** .
    
2. I fönstret **Ta bort princip** markerar du de principer du vill ta bort \> **Välj** och sedan **Bekräfta** för att ta bort principen eller principerna du valt. 
    
## <a name="available-settings"></a>Tillgängliga inställningar

Följande tabeller ger detaljerad information om vilka inställningar som finns för att skydda filer på enheter, och inställningarna som styr hur användare får åtkomst till Office-filer från sina mobila enheter.
  
 Mer information finns i artikeln om [hur skyddsfunktioner i Microsoft 365 Business mappas till Intune-inställningarna](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Inställningar som skyddar arbetsfiler

Följande inställningar är tillgängliga för att skydda arbetsfiler om en användares enhet försvinner eller blir stulen:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Ta bort arbetsﬁler från en inaktiv enheten efter så många dagar  <br/> |Om en enhet inte används under så många dagar som du anger här raderas alla arbetsfiler från enheten automatiskt.  <br/> |
|Tvinga användare att spara alla filer i OneDrive för företag  <br/> |Om den här inställningen är **På**, kommer filer bara att kunna sparas till OneDrive för företag.  <br/> |
|Kryptera arbetsfiler  <br/> |Behåll den här inställningen **På** så att arbetsfiler skyddas av kryptering. Om enheten försvinner eller blir stulen kommer ingen att kunna läsa företagets data.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Inställningar som styr hur användare kommer åt Office-filer på mobila enheter

Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om inställningen är **På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-programmen på sin mobila enhet.  <br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen bestämmer hur lång tid användare kan vara inaktiva innan de uppmanas att logga in igen.  <br/> |
|Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter  <br/> |Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket gör enheten mer utsatt för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  <br/> |
|Tillåt användare att kopiera innehåll från Office-program till personliga program  <br/> |Vi tillåter detta som standard, men om den här inställningen är **aktiverad**kommer användaren kan kopiera information i en arbetsfil till en personlig fil. Om inställningen är **Inaktiverad**, kan användaren inte kopiera informationen från ett konto för arbete till en personlig app eller kontoinformation.<br/> |
   

  

