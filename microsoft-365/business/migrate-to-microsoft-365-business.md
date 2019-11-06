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
ms.openlocfilehash: 1e337b908f848da1d33cbd8e662652550d302b14
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002150"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Uppgradera till Microsoft 365 Business från Office 365 Business Premium

Om du har en [office 365 för Business-prenumeration](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), till exempel Office 365 Business Premium, kan du enkelt uppgradera till Microsoft 365 Business. Uppgradera till Microsoft 365 Business om du vill lägga till: 
- Windows 10 Pro (till datorer som kör Windows 8 eller senare)
- Enkla kontroller som hanterar affärsdata på enheter
- Avancerade säkerhetsfunktioner.
Läs mer om Microsoft 365 Business på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Vad är skillnaden mellan Office 365 Business Premium och Microsoft 365 Business?
Vi har lagt till en sida-vid-sida-jämförelse av dessa två planer till [Microsoft 365 Business servicebeskrivning](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

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
    
4. På sidan **migrera e-postmeddelanden** kan du välja att migrera e-post för alla nya användare som du lade till i steg 3. Du kan hoppa över det här steget också. Välj **Nästa**.
    
5. På den sista sidan väljer **du gå till administratörscenter**och fortsätter installationen där.
    
6. Gå till **användare** \> **aktiva användare**i administratörscenter.
    
7. Välj den användare som du vill tilldela **Microsoft 365 Business** -licensen till och välj sedan **Redigera** bredvid **produktlicenser**.
    
    ![I användarkortet väljer du Redigera bredvid produktlicenser.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
## <a name="before-you-get-started"></a>Innan du börjar

- **När ska jag välja Upgrade?** Uppgraderingen är rätt val när du vill uppgradera **alla användare** som tilldelats en enda plan. När du väljer uppgradera får alla plan användare byta till en annan plan samtidigt. Om du inte vill uppgradera alla som är tilldelade till en enda plan, köpa licenser för den nya planen (i det här fallet Microsoft 365 företag) och [tilldela dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) till varje användare som du vill uppgradera. 
- **Vissa tillägg kan förhindra uppgradering** Om du försöker starta en uppgradering och har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till det igen senare-om du fortfarande behöver det. 
- **Om du förbetalt din plan** Det finns inte en enkel uppgraderingsväg för förbetalda abonnemang. Du vet om du har en förutbetald plan eftersom du ställer in din plan med ett produkt-ID som du kan ha köpt i en butik. Kontakta en partner, gå till Microsoft Store eller vänta tills ditt förbetalda abonnemang går ut för att byta till ett nytt abonnemang.

## <a name="upgrade-to-microsoft-365-business"></a>Uppgradera till Microsoft 365 Business
Köp dina licenser genom att följa dessa steg i det [nya administratörscentret](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):
1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administratörscenter.
2. Gå till navigeringsfönstret och välj **fakturerings** \> **produkter & tjänster**. Hitta din Office 365-prenumeration och välj den för att visa detaljerna. 

    ![En skärmbild visar hur du hittar och väljer din prenumeration i administratörscenter.](media/FindYourSubscription.png)

3. På nästa sida väljer du **Uppgradera**. 

      ![En skärmbild visar var du ska välja uppgradering i administratörscenter.](media/SelectUpgrade.png)

  > [!NOTE]
  > Om du ser ett meddelande som säger "uppgradera din prenumeration stöds inte med gruppbaserad licensiering i Azure Active Directory", kan du bortse från detta om du inte har en mycket stor organisation. Organisationer som har valt det här alternativet kommer att vara medveten om att de använder gruppbaserad licensiering.

4. Därefter kan du Visa en lista över Office-planer som du kan uppgradera till. I det här fallet hittar du Microsoft 365 affärsplan. Du kan rulla nedåt om du vill se alla Office-appar och-tjänster som ingår i den här planen. Under **Microsoft 365 Business**väljer du **Uppgradera** för att lägga till Microsoft 365 Business i kundvagnen.
5. I vagnen:
    1. Vi inkluderar automatiskt licenser för alla dina nuvarande användare till kundvagnen. Om du behöver mer eller mindre licenser måste du [köpa och tilldela dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).  
    2. Du kan justera hur du vill betala-månad eller år. Välj den nedrullningsbara menyn för att göra ditt val.
6. Välj **gå till kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetoden för det här kontot. Du kan också lägga till en kampanjkod här om du har en.
7. Välj **Beställ** för att slutföra köpet.
Det tar Microsoft några minuter att ställa in dina nya service planer. Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**. 
1. När planen är klar kan du behöva utföra några ytterligare konfigurationssteg i administratörscenter. I navigeringsfönstret väljer du **hem** för att slutföra eventuella ytterligare inställningssteg.

> [!NOTE]
> Du får en proportionell återbetalning för Ofifce 365-licenser som du inte längre behöver. Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har ställt in den nya planen.
  
## <a name="protect-user-devices-and-files"></a>Skydda användarenheter och filer

Nu när Microsoft 365-företagslicenser har tilldelats, slutför du stegen för att börja skydda enheter och filer. Du kommer att använda några nya alternativ som ingår i Administrationscenter navigeringsfönstret.
  
1. I administratörscenter, i navigeringsfönstret, gå till **principer**för **enheter** \> .
    
2. På sidan **enhetsprinciper** väljer du **Lägg till**.
    
3. I den **Lägg till princip** fönstret ge principen ett namn (till exempel skydda arbetsfiler), och välj sedan en **Principtyp** från listrutan. 
    
    Du kan ställa in användningsprinciper för att skydda filer på Android-och iPhone-enheter, samt Windows 10, och du kan ställa in principer för enhetskonfiguration för företagsägda Windows 10-enheter. Se följande länkar för mer information:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
    
  
4. När du har konfigurerat policyer kan du och dina anställda ställa in enheter:
    
  - Om Windows-enheterna inte redan använder Windows Pro Creator-uppdateringen måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Se [Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) för steg för Windows-enheter. 
    
  - Se [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone. 



