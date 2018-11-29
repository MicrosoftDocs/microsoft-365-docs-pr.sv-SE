---
title: Migrera till Microsoft 365 Business från Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig hur du flyttar verksamheten till Microsoft 365 Business.
ms.openlocfilehash: fd6f18c02453e6751d6163ab79e726eae9c951a9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983499"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migrera till Microsoft 365 Business från Office 365 Business Premium

Om du redan har ett Office 365 business abonnemang, till exempel Office 365 Business Premium, kan du enkelt lägga till licenser för Microsoft 365 Business och tilldela dem till vissa eller alla användare.
  
> [!NOTE]
> Du kan inte använda knappen [Växla planer](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) för att uppgradera till Microsoft 365 Business ännu. 
  
## <a name="add-microsoft-365-business-licenses"></a>Lägga till licenser för Microsoft 365 Business

Du har två sätt att få Microsoft 365 Business. Om du har en partner kan kan han eller hon köpa Microsoft 365 Business du från [Microsoft Partner Center](get-microsoft-365-business.md). Din partner kan du också övergången till Microsoft 365 Business.
  
Om du hanterar din prenumeration kan du [Kontakta försäljningsavdelningen](https://www.microsoft.com/microsoft-365/business) att köpa Microsoft 365 Business licenser. 
  
Se [lägga till, ändra eller ta bort en prenumeration klassificering av partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) för att ta reda på hur du kan börja arbeta med en partner. 
  
Om du får en länk för att köpa dina licenser vägleder genom en guide som i exemplet nedan. Välj **Ja, lägga till mitt konto**. Du kan också välja antalet licenser och betalningsmetod.
  
![Köp Microsoft 365 verksamhet direkt länk, välja att lägga till ditt nuvarande konto eller registrera dig för ett nytt konto.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Tilldela licenser för Microsoft 365

1. När du har köpt nya licenser och det är första gången du gjorde, visas banderollen installationsprogrammet för Microsoft 365 Business på administratörscenter.
    
    > [!NOTE]
    > Banderoll för installationsprogrammet är en möjlighet att lägga till nya användare, en ny domän och migrera e-post för nya användare. Om du inte tänker göra något ska fortfarande gå igenom guiden och välj alternativ så att det försvinner från sidan Hem. 
  
   ![Välj startar du installationsprogrammet på Microsoft 365 Business är redo att ställa in banderoll.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Välj **Gör inställningar**.
    
2. Du kan lägga till en domän genom att välja **Anslut en domän du redan äger** om du vill använda den här möjligheten att lägga till en annan domän i din prenumeration på sidan **Anpassa din inloggning och e-post** . 
    
    Om du redan har registrerat en domän, det andra fältet visar som och säger **Fortsätt med** \< _domännamnet_ \> **för e-post och logga in**. Om du inte har registrerat en domän med prenumeration du säger det **Fortsätt med** \< _företag-name.onmicrosoft.com_ \> **för e-post och logga in**.    
    
    Välj **Next**.
    
    ![På Anpassa din inloggning och e-sida kan du antingen lägga till en domän eller använda den som du har använt.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. Du kan lägga till nya användare, om du har nya medarbetare som du vill tilldela licenser till Microsoft 365 Business på sidan **Lägg till nya användare** . 
    
    Välj **Nästa**om du inte har nya medarbetare att lägga till och vill tilldela licenser till befintliga användare.
    
4. På den ** migrera e-postmeddelanden ** sidan som du kan välja att migrera e-post för alla nya användare som du lade till i steg 3. Du kan också hoppa över det här steget. Välj **Nästa**.
    
5. Välj **Gå till administratörscenter**på den sista sidan och fortsätta installationen där.
    
6. Gå till **användare** i administratörscenter, \> **aktiva användare**.
    
7. Markera den användare du vill tilldela **Microsoft 365 Business** licens till och välj sedan **Redigera** bredvid **Produktlicenser**.
    
    ![Välj Redigera bredvid produktlicenser i kortet användaren.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. I **produktlicenser** bild **Microsoft 365 Business** **on** \> **Spara**och **Stäng**.
    
När du har köpt den första licensen för Microsoft 365 företag, du kan nu också lägga till mer i **Fakturering** \> **Inköp tjänster**. På sidan **köpa tjänster** kan du på punkter på **Microsoft 365** visitkort och välj **Ändra licensantal** att köpa mer. 
  
## <a name="protect-user-devices-and-files"></a>Skydda användare, enheter och filer

När du har tilldelat Microsoft 365 Business licenser kan du börja med att skydda användarnas enheter och filer.
  
1. Gå till **enheter** i administratörscenter, i vänstra navigeringsfältet \> **principer**.
    
2. Välj **Lägg till**på sidan **principer för enheten** .
    
3. Ge ett namn för principen i rutan **Lägg till principen** och välj en **typ** från nedrullningsbara. 
    
    Du kan ställa in användningsprinciper för att skydda filer på Android och iPhone-enheter samt Windows 10 och du kan ställa in enhetens konfiguration principer för företag som ägs av Windows 10 enheter. Se följande länkar för mer information:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange inställningar för enhetsskydd för Windows 10](protection-settings-for-windows-10-pcs.md)
    
   ![Ange ett namn för den i fönstret Lägg till principen och välja principtypen från den nedrullningsbara menyn.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. När du ställer in principerna kan kan du och dina anställda ställa in enheter:
    
  - Om Windows inte redan Pro Creator för Windows Update, behöver du [uppgradera dem till Windows Pro skapare Update](upgrade-to-windows-pro-creators-update.md).
    
  - Steg för Windows-enheter finns i [ställa in Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) . 
    
  - Anvisningar för Android Telefoner och iPhones finns i [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) . 
    
5. Om du vill installera Office-klientprogram automatiskt finns i [förbereda för distribution av Office-klienten av Microsoft 365 Business](prepare-for-office-client-deployment.md) och [automatiskt installera eller avinstallera Office på Windows 10 enheter](auto-install-or-uninstall-office.md).
    


