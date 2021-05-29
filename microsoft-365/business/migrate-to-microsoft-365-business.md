---
title: Uppgradera till Microsoft 365 Business Premium från Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
ms.openlocfilehash: 0968b877820590987f6f3ceca3efbd106b62cbd1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705499"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Uppgradera till Microsoft 365 Business Premium från Microsoft 365 Business Standard

Om du har en [Microsoft 365 för](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)företag-prenumeration, till exempel Microsoft 365 Business Standard, kan du enkelt uppgradera till Microsoft 365 Business Premium. Uppgradera till Microsoft 365 Business Premium om du vill lägga till:

- Windows 10 Pro (på datorer med Windows 8 eller senare)

- Enkla kontroller som hanterar affärsdata på enheter

- Avancerade säkerhetsfunktioner.
Mer information om Microsoft 365 Business Premium finns [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>Vad är skillnaden mellan Microsoft 365 Business Standard och Microsoft 365 Business Premium?

Vi har lagt till en jämförelse sida vid sida av dessa två abonnemang i [Microsoft 365 Business Premium Tjänstbeskrivning](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-begin"></a>Innan du börjar

- **När ska jag välja att uppgradera?** Uppgradera är rätt val när du vill uppgradera alla **användare som tilldelats** ett enda abonnemang. När du väljer uppgradera byter alla abonnemangsanvändare till ett annat abonnemang samtidigt. Om du inte vill uppgradera alla som har tilldelats ett enda abonnemang köper du licenser [](../admin/manage/assign-licenses-to-users.md) för det nya abonnemanget (i det här fallet Microsoft 365 Business Premium) och tilldelar licenserna individuellt till varje användare som du vill uppgradera.

- **Vissa tillägg kan förhindra uppgraderingen** Om du försöker starta en uppgradering och har ett tillägg som hindrar dig från att fortsätta kan du ta bort tillägget först och sedan lägga till det igen senare om du fortfarande behöver det.

- **Om du har förbetalt abonnemanget** Det finns ingen enkel uppgraderingsväg för förbetalda abonnemang. Du vet om du har ett förbetalt abonnemang eftersom du konfigurerade ditt abonnemang med ett produkt-ID som du kanske har köpt i en butik. Kontakta en partner, gå till Microsoft Store eller vänta tills ditt förbetalda abonnemang går ut om du vill byta till ett nytt abonnemang.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Uppgradera till Microsoft 365 Business Premium

1. Logga in i administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Gå till navigeringsfönstret och välj **Fakturering** \> **dina produkter.** Hitta din nuvarande prenumeration och välj den för att visa information.

3. På nästa sida väljer du **Uppgradera**.

  > [!NOTE]
  > Om meddelandet Uppgradera din prenumeration inte stöds med gruppbaserad licensiering i **Azure Active Directory** kan du bortse från detta såvida du inte har en mycket stor organisation. Organisationer som har valt det här alternativet kommer att vara medvetna om att de använder gruppbaserad licensiering.

4. Sedan kan du visa en lista med planer som du kan uppgradera till. I det här fallet ska du Microsoft 365 Business Premium planen. Du kan rulla nedåt om du vill se alla program och tjänster som ingår i det här abonnemanget. Under **Microsoft 365 Business Premium** väljer du **Uppgradera för** att lägga Microsoft 365 Business Premium till din kundvagn.

5. I kundvagnen:

    1. Vi inkluderar automatiskt licenser för alla dina aktuella användare. Om du behöver fler eller färre licenser måste du köpa och [tilldela licenserna individuellt.](../admin/manage/assign-licenses-to-users.md)  
    2. Du kan justera hur du vill betala: per månad eller år. Välj listrutan för att göra ditt val.

6. Välj **Gå till kassan** där du ser en sammanfattning av köpet, inklusive betalningsmetoden för det här kontot. Du kan även lägga till en kampanjkod här om du har en.

7. Välj **Lägg order** för att slutföra köpet.\
Det tar microsoft några minuter att konfigurera dina nya tjänstplaner. Om du vill kontrollera förloppet väljer **du Kontrollera uppgraderingsstatus**.

8. När abonnemanget är klart kan du behöva slutföra några ytterligare konfigurationssteg i administrationscentret. I navigeringsfönstret väljer du **Start för** att slutföra alla ytterligare konfigurationssteg.

> [!NOTE]
> Du får en återbetalning i procent för de licenser Microsoft 365 du inte längre behöver. Ditt bankkonto eller kreditkort debiteras ungefär två dagar efter att du har angett det nya abonnemanget.
  
## <a name="protect-user-devices-and-files"></a>Skydda användarenheter och filer

Nu när Microsoft 365 Business Premium licenser har tilldelats kan du börja skydda enheter och filer. Du kommer att använda några nya alternativ i navigeringsfönstret i administrationscentret.
  
1. I administrationscentret går du till Principer  för enheter i \> **navigeringsfönstret.**

2. På sidan **Enhetsprinciper** väljer du Lägg **till**.

3. I fönstret **Lägg till** princip ger du principen ett namn (till exempel Skydda arbetsfiler) och väljer sedan en **principtyp** i listrutan.

    Du kan konfigurera programprinciper för att skydda filer på Android och iPhone-enheter, samt Windows 10, och du kan konfigurera principer för enhetskonfiguration för företagsägda Windows 10 enheter. Se följande länkar för mer information:

    - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)

    - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)

    - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)

4. När du har konfigurerat principer kan du och dina anställda konfigurera enheter:

    - Om dina Windows-enheter inte redan använder Windows Pro Creator-uppdateringen måste du uppgradera dem till [Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

    - Se [Konfigurera Windows enheter för Microsoft 365 Business Premium för](set-up-windows-devices.md) anvisningar för Windows enheter.

    - Se [Konfigurera mobila enheter för Microsoft 365 Business Premium för anvisningar](set-up-mobile-devices.md) för Android-telefoner och iPhone.