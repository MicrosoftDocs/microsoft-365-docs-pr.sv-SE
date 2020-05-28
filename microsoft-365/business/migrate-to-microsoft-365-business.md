---
title: Uppgradera till Microsoft 365 Business Premium från Microsoft 365 Business Standard
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig skillnaden mellan Microsoft 365 Business Standard och Microsoft 365 Business Premium och hur du kan uppgradera till Microsoft 365 Business Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401391"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Uppgradera till Microsoft 365 Business Premium från Microsoft 365 Business Standard

Om du har en [Prenumeration på Microsoft 365 för företag,](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)till exempel Microsoft 365 Business Standard, kan du enkelt uppgradera till Microsoft 365 Business Premium. Uppgradera till Microsoft 365 Business Premium om du vill lägga till:

- Windows 10 Pro (till datorer som kör Windows 8 eller senare)

- Enkla kontroller som hanterar affärsdata på enheter

- Avancerade säkerhetsfunktioner.
Läs mer om Microsoft 365 Business Premium på [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>Vad är skillnaden mellan Microsoft 365 Business Standard och Microsoft 365 Business Premium?

Vi har lagt till en jämförelse sida vid sida av dessa två planer i [Microsoft 365 Business Premium Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Innan du börjar

- **När ska jag välja att uppgradera?** Uppgradering är det rätta valet när du vill uppgradera **alla användare** som tilldelats en enda plan. När du väljer uppgradering kopplas alla abonnemangsanvändare till ett annat abonnemang samtidigt. Om du inte vill uppgradera alla som tilldelats ett enda abonnemang köper du licenser för det nya abonnemanget (i det här fallet Microsoft 365 Business Premium) och [tilldelar dessa licenser individuellt](../admin/manage/assign-licenses-to-users.md) till varje användare som du vill uppgradera.

- **Vissa tillägg kan förhindra uppgraderingen** Om du försöker starta en uppgradering och har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till det senare om du fortfarande behöver det.

- **Om du förbetald din plan** Det finns inte en enkel uppgraderingsväg för förbetalda planer. Du vet om du har ett förbetalt abonnemang eftersom du har konfigurerat ditt abonnemang med hjälp av ett produkt-ID som du kan ha köpt i en butik. Kontakta en partner, gå till Microsoft Store eller vänta tills ditt förbetalda abonnemang går ut för att byta till ett nytt abonnemang.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Uppgradera till Microsoft 365 Business Premium

1. Logga in på administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Gå till navigeringsfönstret och välj **Fakturering** \> **dina produkter**. Hitta din nuvarande prenumeration och välj den för att visa informationen.

3. På nästa sida väljer du **Uppgradera**.

  > [!NOTE]
  > Om du ser ett meddelande om att **uppgradera din prenumeration stöds inte med gruppbaserad licensiering i Azure Active Directory**kan du bortse från detta om du inte har en mycket stor organisation. Organisationer som har valt det här alternativet är medvetna om att de använder gruppbaserad licensiering.

4. Därefter kan du visa en lista över planer som du kan uppgradera till. Leta reda på Microsoft 365 Business Premium-abonnemanget i det här fallet. Du kan rulla nedåt om du vill se alla appar och tjänster som ingår i den här planen. Under **Microsoft 365 Business Premium**väljer du **Uppgradera** för att lägga till Microsoft 365 Business Premium i kundvagnen.

5. I vagnen:

    1. Vi tar automatiskt med licenser för alla dina nuvarande användare. Om du behöver fler eller färre licenser måste du [köpa och tilldela dessa licenser individuellt.](../admin/manage/assign-licenses-to-users.md)  
    2. Du kan justera hur du vill betala: månadsvis eller år. Välj den nedrullningsbara menyn för att göra ditt val.

6. Välj **Gå till kassan** där du ser en sammanfattning av ditt köp, inklusive betalningsmetoden för det här kontot. Du kan också lägga till en kampanjkod här om du har en.

7. Välj **Beställ för** att slutföra köpet.\
Det tar Microsoft några minuter att konfigurera dina nya serviceplaner. Om du vill kontrollera förloppet väljer du **Kontrollera uppgraderingsstatus**.

8. När din plan är klar kan du behöva slutföra ytterligare installationssteg i administrationscentret. I navigeringsfönstret väljer du **Hem** för att slutföra eventuella ytterligare installationssteg.

> [!NOTE]
> Du får en proportionell återbetalning för de Microsoft 365-licenser som du inte längre behöver. Ditt bankkonto eller ditt kreditkort debiteras ungefär två dagar efter att du har konfigurerat det nya abonnemanget.
  
## <a name="protect-user-devices-and-files"></a>Skydda användarenheter och filer

Nu när Microsoft 365 Business Premium-licenser har tilldelats, gör du några steg för att börja skydda enheter och filer. Du ska använda några nya alternativ som ingår i navigeringsfönstret för administrationscenter.
  
1. Gå till Enhetsprinciper i **navigeringsfönstret i administrationscentret.** \> **Policies**

2. På sidan **Enhetsprinciper** väljer du **Lägg till**.

3. I fönstret **Lägg till princip** anger du principen ett namn (till exempel Skydda arbetsfiler) och väljer sedan en **principtyp** i listrutan.

    Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter. Mer information finns i följande länkar:

    - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)

    - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)

    - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)

4. När du har ställt in principer kan du och dina anställda konfigurera enheter:

    - Om dina Windows-enheter inte redan använder uppdateringen Windows Pro Creator måste du [uppgradera dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

    - Se [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) för steg för Windows-enheter.

    - Se [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.