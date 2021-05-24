---
title: Migrera till Microsoft 365 Business från Office 365 E3
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Om du har en Office 365 E3-prenumeration men inte har fler än 300 anställda kan du överväga att byta till Microsoft 365 Business Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623614"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrera från E3 Office 365 till Microsoft 365 Business Premium

Microsoft 365 Business Premium finns allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet. Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business Premium för ytterligare säkerhetsfunktioner.

Det är enkelt att migrera: Först byter du licens och alla data och användarinformation i den aktuella prenumerationen bevaras. Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.

| Funktion    | Support i Microsoft 365 Business Premium    | Support i Office 365 E3 |
|:-------|:-----|:-----|
| **Lokalt**        | | |
| Office appar<sup>1</sup>    | Microsoft 365-applikationer för affärsverksamhet    | Microsoft 365-applikationer för företag |
| **Produktivitetsprogram för molnet**        | | |
| Exchange Online och Outlook    | 50 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering    | 100 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering |
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| OneDrive för företag    | 1 TB lagringsgräns per användare    | Obegränsat | 
| Yammer, SharePoint Online, Planner, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) |
| **Skydd mot hot**        | | |
| Microsoft Defender för Office 365 Abonnemang 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte men kan läggas till på |
| **Identitetshantering**        | | |
| Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| **Enhets- och apphantering**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Aktivering på delad dator|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| Uppgraderingsrättigheter till Windows 10 Pro från Win 7/8.1 Pro licenser|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    ||
| **Informationsskydd**        | | |
|Office 365 Dataförlustskydd|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|Azure Information Protection plan 1, BitLocker verkställande|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection plan 1, känslighetsetiketter|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|**Klientåtkomstlicens (CAL-rättigheter)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Ingår i Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 Business Premium-versionen av Office-apparna omfattar inte volymaktivering via grupprinciper, app telemetri, uppdateringskontroller, kalkylbladsjämförelse och inquire samt Business Intelligence.

## <a name="migration"></a>Migrering

Anvisningar om hur du migrerar [din prenumeration finns i](../commerce/subscriptions/change-plans-manually.md) Ändra abonnemang manuellt om du bara vill flytta några få Microsoft 365 Business Premium. Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md), eller samarbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business Premium prenumeration.
I följande avsnitt beskrivs de ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 Konfiguration och data för E3-prenumeration
Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:

- Prenumerationskonfiguration, till exempel DNS-poster och domännamn.
- Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.
- Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.
- Office skalas automatiskt. Office 365 modern licensiering kommer att kontrollera användarens licenstilldelning var 72:e timme och konverterar Office-program till den version som överensstämmer med användarprenumerationen.

### <a name="windows-10"></a>Windows 10

Om din Windows inte redan är på Windows Pro,uppgradera dem till [Creators Update Windows Pro dem.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Konfigurera principer för att skydda användares enheter och filer

> [!NOTE]
> Om du inställningar Office 365 MDM-principer och -enheter visas  de enheterna på sidan Enheter Microsoft 365 administrationscentret. Alla principer som du har angett visas i listan med klassiska principer i [Intune-portalen.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

När du har tilldelat licenser Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.

Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium visas installationsguiden på startsidan och du kan följa Konfigurera [Microsoft 365 Business Premium](set-up.md) i installationsguiden för att skydda filer och mobila enheter.

Du kan också utföra de här stegen på sidan Enheter:
  
1. I det vänstra navigeringsfältet i administrationscentret går du till **Principer för** \> **enheter.**

2. På sidan **Enhetsprinciper** väljer du Lägg **till**.

3. I fönstret **Lägg till** princip ger du principen ett namn och väljer sedan **en principtyp** i listrutan.

     Du kan konfigurera programprinciper för att skydda filer på Android och iPhone-enheter, samt Windows 10, och du kan konfigurera principer för enhetskonfiguration för företagsägda Windows 10 enheter. Se följande länkar för mer information:

  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)

  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)

  - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
  
4. När du har angett principer kan du och dina anställda konfigurera enheter:

  - Se [Konfigurera Windows enheter för Microsoft 365 Business Premium för](set-up-windows-devices.md) anvisningar för Windows enheter. 

  - Se [Konfigurera mobila enheter för Microsoft 365 Business Premium för anvisningar](set-up-mobile-devices.md) för Android-telefoner och iPhone. 
  
### <a name="mailbox-size"></a>Postlådans storlek

Microsoft 365 Business Premium har en lagringsgräns på 50 GB eftersom den använder Exchange Online abonnemang 1. När du migrerar till Microsoft 365 Business Premium rekommenderar vi att du tilldelar användaren ett Exchange Online abonnemang 2 och tar bort Exchange Online abonnemang 1 eftersom det inte är möjligt att tilldela båda.

### <a name="threat-protection"></a>Skydd mot hot

När du har migrerat till Microsoft 365 Business Premium har du Defender för Office 365. Se [Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md) en översikt. Konfigurera genom att gå till [Konfigurera Valv,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)konfigurera [Valv](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera Skydd mot nätfiske [i Defender för Office 365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>Känslighetsetiketter

Om du vill börja använda känslighetsetiketter kan [du gå till Översikt över känslighetsetiketter](../compliance/sensitivity-labels.md) och skapa och hantera [känslighetsetiketter](../business-video/create-sensitivity-labels.md) video.

## <a name="related-content"></a>Relaterat innehåll

[Ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) (artikel)\
[Uppgradera Windows enheter till Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)\
[Ange programskyddsinställningar för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md) (artikel)\
[Ange eller redigera programskyddsinställningar för Windows 10](protection-settings-for-windows-10-devices.md) (artikel)\
[]

