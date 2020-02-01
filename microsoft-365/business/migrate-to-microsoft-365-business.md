---
title: Uppgradera till Microsoft 365 Business från Office 365 Business Premium
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
ms.openlocfilehash: 0732f76e5bd8540e5954bd7ea7b88061326901b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593688"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Uppgradera till Microsoft 365 Business från Office 365 Business Premium

Om du har en [Office 365 för företag-prenumeration,](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)till exempel Office 365 Business Premium, kan du enkelt uppgradera till Microsoft 365 Business. Uppgradera till Microsoft 365 Business om du vill lägga till: 
- Windows 10 Pro (till datorer som kör Windows 8 eller senare)
- Enkla kontroller som hanterar affärsdata på enheter
- Avancerade säkerhetsfunktioner.
Läs mer om Microsoft 365 Business på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Vad är skillnaden mellan Office 365 Business Premium och Microsoft 365 Business?
Vi har lagt till en sida-vid-sida jämförelse av dessa två planer till [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Innan du börjar

- **När ska jag välja att uppgradera?** Uppgradering är rätt val när du vill uppgradera **alla användare** som tilldelats en enda plan. När du väljer uppgradering, alla plan användare får byta till en annan plan samtidigt. Om du inte vill uppgradera alla som har tilldelats en enda plan köper du licenser för den nya planen (i det här fallet Microsoft 365 Business) och [tilldelar dessa licenser individuellt](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) till varje användare som du vill uppgradera. 
- **Vissa tillägg kan förhindra uppgraderingen** Om du försöker starta en uppgradering och du har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till den senare om du fortfarande behöver det. 
- **Om du förbetalt din plan** Det finns inte en enkel uppgraderingsväg för förbetalda planer. Du vet om du har en förbetald plan eftersom du ställer in din plan med ett produkt-ID som du kan ha köpt i en butik. Kontakta en partner, gå till Microsoft Store eller vänta tills din förbetalda plan går ut för att växla till en ny plan.

## <a name="upgrade-to-microsoft-365-business"></a>Uppgradera till Microsoft 365 Business
Köp dina licenser genom att följa dessa steg i det [nya administrationscentret:](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)
1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administratörscentret på .
2. Gå till navigeringsfönstret och välj \> **Faktureringsprodukter & Tjänster**. **** Leta reda på din Office 365-prenumeration och välj den för att visa informationen. 

    ![En skärmbild visar hur du hittar och väljer din prenumeration i administrationscentret.](media/FindYourSubscription.png)

3. På nästa sida väljer du **Uppgradera**. 

      ![En skärmbild visar var du vill välja Uppgradera i administrationscentret.](media/SelectUpgrade.png)

  > [!NOTE]
  > Om du ser ett meddelande om att **uppgradera din prenumeration inte stöds med gruppbaserad licensiering i Azure Active Directory**kan du ignorera detta om du inte har en mycket stor organisation. Organisationer som har valt det här alternativet är medvetna om att de använder gruppbaserad licensiering.

4. Därefter kan du visa en lista över Office-planer som du kan uppgradera till. I det här fallet hittar du Microsoft 365 Business-planen. Du kan rulla nedåt om du vill se alla Office-appar och tjänster som ingår i den här planen. Under **Microsoft 365 Business**väljer du **Uppgradera** för att lägga till Microsoft 365 Business i kundvagnen.
5. I vagnen:
    1. Vi kommer automatiskt att inkludera licenser för alla dina nuvarande användare. Om du behöver fler eller färre licenser måste du [köpa och tilldela dessa licenser individuellt.](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)  
    2. Du kan justera hur du vill betala: månadsvis eller årligen. Välj rullgardinsmenyn för att göra ditt val.
6. Välj **Gå till Kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetodför det här kontot. Du kan också lägga till en kampanjkod här om du har en.
7. Välj **Placera order** för att slutföra köpet.
Det tar Microsoft några minuter att ställa in dina nya serviceplaner. Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**. 
1. När planen är klar kan du behöva slutföra några ytterligare inställningssteg i administrationscentret. I navigeringsfönstret väljer du **Start för** att slutföra ytterligare inställningssteg.

> [!NOTE]
> Du får en proportionell återbetalning för de Office 365-licenser som du inte längre behöver. Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har ställt in den nya planen.
  
## <a name="protect-user-devices-and-files"></a>Skydda användarenheter och filer

Nu när Microsoft 365 Business-licenser har tilldelats, slutför du stegen för att börja skydda enheter och filer. Du använder några nya alternativ som ingår i navigeringsfönstret för administrationscenter.
  
1. Gå till \> **Enhetsprinciper**i navigeringsfönstret **** i administrationscentret .
    
2. På sidan **Enhetsprinciper** väljer du **Lägg till**.
    
3. I fönstret **Lägg till princip** ger principen ett namn (till exempel Skydda arbetsfiler) och välj sedan en **principtyp** i listrutan. 
    
    Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter, samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter. Se följande länkar för detaljer:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange enhetsskyddsinställningar för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
    
  
4. När du har konfigurerat principer kan du och dina anställda konfigurera enheter:
    
  - Om windows-enheterna inte redan använder Windows Pro Creator-uppdateringen måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Se [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) för steg för Windows-enheter. 
    
  - Se [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone. 
