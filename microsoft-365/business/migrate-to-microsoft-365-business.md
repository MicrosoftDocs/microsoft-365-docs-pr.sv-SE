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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig hur du flyttar ditt företag till Microsoft 365 Business.
ms.openlocfilehash: ae9ca0fe97916fdae6104a6edbb04efba5d9299e
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575887"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migrera till Microsoft 365 Business från Office 365 Business Premium

Om du redan har en Office 365 för Business-prenumeration, till exempel Office 365 Business Premium, kan du enkelt lägga till licenser till Microsoft 365 Business och tilldela dem till vissa eller alla användare.
  
> [!NOTE]
> Du kan inte använda knappen [växla planer](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) för att uppgradera till Microsoft 365 Business ännu. 
  
## <a name="add-microsoft-365-business-licenses"></a>Lägg till Microsoft 365 Business-licenser

Du har två sätt att få Microsoft 365 Business. En partner kan köpa Microsoft 365 Business åt dig från [Microsoft Partner Center](get-microsoft-365-business.md). Din partner kan också hjälpa dig att övergå till Microsoft 365 Business.
  
Om du hanterar din egen prenumeration kan du [Kontakta sales](https://www.microsoft.com/microsoft-365/business) för att köpa Microsoft 365 Business-licenser. 
  
Se [lägga till, ändra eller ta bort en prenumeration Advisor-partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) för att ta reda på hur du kan börja arbeta med en partner. 
  
Om du får en länk för att köpa dina licenser, kommer du att gå igenom en guide som den nedan. Välj **Ja, Lägg till det i mitt konto**. Du kan också välja antalet licenser och betalningsmetoden.
  
![På länken Microsoft 365 Business Direct-köp väljer du att lägga till ditt nuvarande konto eller registrerar dig för ett nytt konto.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Tilldela Microsoft 365-licenser

1. När du har köpt nya licenser, och detta är första gången du gjorde, visas den setup banner för Microsoft 365 företag på toppen av administratörscenter.
    
    > [!NOTE]
    > Banner för inställningar är en möjlighet att lägga till nya användare, en ny domän och migrera e-post för nya användare. Om du inte planerar att göra något, bör du fortfarande gå igenom guiden och välja standardalternativ för att få det att försvinna från admin hemsida. 
  
   ![Välj Starta installationen på den Microsoft 365 företag är redo att ställa in banner.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Välj **Gör inställningar**.
    
2. På sidan **Anpassa din inloggning och e-post** kan du lägga till en domän genom att välja **Anslut en domän som du redan äger** om du vill använda den här möjligheten för att lägga till en annan domän i prenumerationen. 
    
    Om du redan har konfigurerat en domän, kommer det andra fältet att indikera det och kommer att **säga Fortsätt att använda** \< _ditt domännamn_ \> **för e-post och inloggning**.   Om du inte har konfigurerat en domän med din prenumeration, kommer det att **säga fortsätta att använda** \< _ditt företag Name.onmicrosoft.com_ \> **för e-post och logga in**.  
    
    Välj **Nästa**.
    
    ![På sidan Anpassa din inloggning och e-post väljer du att antingen lägga till en domän eller använder den som du har använt.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. På sidan **Lägg till nya användare** kan du lägga till nya användare om du har nya medarbetare som du vill tilldela Microsoft 365 Business-licenser till. 
    
    Om du inte har nya medarbetare att lägga till och vill tilldela licenser till befintliga användare väljer du **Nästa**.
    
4. På sidan * * migrera e-postmeddelanden * * kan du välja att migrera e-post för alla nya användare som du lade till i steg 3. Du kan hoppa över det här steget också. Välj **Nästa**.
    
5. På den sista sidan väljer **du gå till administratörscenter**och fortsätter installationen där.
    
6. Gå till **användare** \> **aktiva användare**i administratörscenter.
    
7. Välj den användare som du vill tilldela **Microsoft 365 Business** -licensen till och välj sedan **Redigera** bredvid **produktlicenser**.
    
    ![I användarkortet väljer du Redigera bredvid produktlicenser.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. I **produktlicenser** Slide **Microsoft 365 Business** till **på** \> **Spara**, och **Stäng**sedan.
    
När du har köpt den första licensen för Microsoft 365-företag kan du nu också lägga till mer i **fakturering** \> **inköpstjänster**. På sidan **Köp tjänster** kan du klicka på ellipserna på **Microsoft 365 visitkortet** och välja **ändra Licenskvantitet** för att köpa mer. 
  
## <a name="protect-user-devices-and-files"></a>Skydda användarenheter och filer

När du har tilldelat licenser till Microsoft 365 Business kan du börja skydda användarnas enheter och filer.
  
1. I administratörscenter, i det vänstra navigeringsfältet, gå till **** \> **principer**för enheter.
    
2. På sidan **enhetsprinciper** väljer **du Lägg till**.
    
3. I den **Lägg till princip** fönstret ge principen ett namn och välj sedan en **Principtyp** från listrutan. 
    
    Du kan ställa in användningsprinciper för att skydda filer på Android-och iPhone-enheter, samt Windows 10, och du kan ställa in principer för enhetskonfiguration för företagsägda Windows 10-enheter. Se följande länkar för mer information:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
    
   ![I den Lägg till princip rutan, ange ett namn för den och välj principtypen från den nedrullningsbara menyn.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. När du har konfigurerat policyer kan du och dina anställda ställa in enheter:
    
  - Om Windows inte redan finns på Windows Pro Creator Update måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Se [Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) för steg för Windows-enheter. 
    
  - Se [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone. 
    
5. Om du vill installera Office-klientappar automatiskt, se [Förbered för Office-klientdistribution av Microsoft 365 Business](prepare-for-office-client-deployment.md) och [Installera eller avinstallera Office på Windows 10-enheter automatiskt](auto-install-or-uninstall-office.md).
    


