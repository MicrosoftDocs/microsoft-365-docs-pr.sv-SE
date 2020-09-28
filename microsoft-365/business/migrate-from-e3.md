---
title: Migrera till Microsoft 365 Business från Office 365 E3
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Lär dig hur du flyttar ditt företag till Microsoft 365 Business Premium från Office 365 E3.
ms.openlocfilehash: f3f3894a2a5cb69f9f91825d89db4f4b857fac5c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295299"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrera från Office 365 E3 till Microsoft 365 Business Premium 

Microsoft 365 Business Premium innehåller allt du behöver för ditt småföretag och kombinerar de bästa molnbaserade Cloud-baserade produktivitets appar med enkel enhets hantering och säkerhet. Om du för närvarande har ett Office 365 E3-abonnemang men inte har fler än 300 anställda bör du överväga att byta till Microsoft 365 Business Premium för ytterligare säkerhetsfunktioner.

Det är enkelt: först kan du byta licenser och alla dina data och din användar information i ditt nuvarande abonnemang underhålls. Efter migreringen måste du konfigurera funktionerna som läggs till i Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.

| Funktion    | Stöd i Microsoft 365 Business Premium    | Stöd i Office 365 E3 | 
|:-------|:-----|:-----|
| **Lokalt**        | | | 
| Office-program<sup>1</sup>    | Microsoft 365-applikationer för affärsverksamhet    |  Microsoft 365 Apps för företag | 
| **Cloud Productivity-appar**        | | | 
| Exchange Online och Outlook    | 50 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering    | 100 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering | 
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| OneDrive för företag    | 1 TB lagrings gräns per användare    | Oinskränk | 
| Yammer, SharePoint Online, Planner, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| Kund ansvarig för Outlook, MileIQ    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Skydd för hotet**        | | | 
| Office 365 Avancerat skydd (ATP) abonnemang 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte, men kan läggas till på | 
| **Identitets hantering**        | | | 
| Self-Service lösen ords återställning för Hybrid Azure Active Directory-konton (Azure AD), Azure Multi-factority (MFA), villkorsstyrd åtkomst, tillbakaskrivning för lösen ord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Hantera enheter och appar**        | | |
| Microsoft Intune, Windows autopilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Aktivering av delad dator|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| Uppgraderings rättigheter till Windows 10 Pro från Win 7/8.1 Pro-licenser|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Informationsskydd**        | | |
|Office 365 skydd mot data förlust|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|Azure information Protection Plan 1, tvingande för BitLocker|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure information Protection Plan 1, känslighets etiketter|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|**Klient åtkomst licens (CAL-rättigheter)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Ingår i Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 Business Premium-versionen av Office-programmen inkluderar inte volym aktivering via grup princip, app-telemetri, uppdaterings kontroller, kalkyl blads jämförelse och-frågor eller Business Intelligence.

## <a name="migration"></a>Migrering

Om du vill migrera prenumerationen kan du läsa [ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) för anvisningar om du vill flytta några personer till Microsoft 365 Business Premium. Du kan också [Uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md)eller arbeta med en partner för att flytta ditt E3-abonnemang och-licenser till en Microsoft 365 Business Premium-prenumeration.
I följande avsnitt beskrivs de ändringar du behöver göra, om så är fallet och vad du kan göra efter migreringen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 prenumerations konfiguration och data
Du behöver inte göra några ändringar i ditt nuvarande abonnemang eller data före migreringen, vilket inkluderar:

- Prenumerations konfiguration, till exempel DNS-poster och domän namn.
- Inställningar för användare och grupper, till exempel multifaktorautentisering eller villkorsstyrd åtkomst.
- Produktivitets tjänst konfiguration och deras data, till exempel team, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.
- Office-programmen skalas automatiskt. Office 365 moderna licenser kontrollerar användarens licens tilldelning varje 72 timmar och konverterar Office-program till den version som matchar användar abonnemanget.

### <a name="windows-10"></a>Windows 10

Om Windows inte redan är aktiverat i Windows Pro Creator kan [du uppgradera dem till Windows Pro Creator Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Konfigurera principer för att skydda användar enheter och filer

> [!NOTE]
> Om du konfigurerar principer och enheter för Office 365 MDM visas dessa enheter på sidan **enheter** i administrations centret för Microsoft 365. Alla principer du konfigurerar visas i listan över klassiska principer i [Intune-portalen](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

När du har tilldelat licenser till Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.

Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium ser du installations guiden på Start sidan och kan [365](set-up.md) följa anvisningarna för att skydda filer och mobila enheter.

Du kan också slutföra dessa steg på sidan enheter:
  
1. Gå till **enhets** principer i administrations centret i det vänstra navigerings fältet \> **Policies**.
    
2. På sidan **enhets principer** väljer du **Lägg till**.
    
3. Ge principen ett namn i rutan **Lägg till princip** och välj sedan en **princip typ** i list rutan. 
    
     Du kan ställa in program principer för att skydda filer på Android-och iPhone-enheter samt i Windows 10, och du kan konfigurera enhets konfigurations principer för företagsspecifika Windows 10-enheter. Se följande länkar för information:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange inställningar för enhets skydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
  
4. När du har konfigurerat en policy kan du och dina anställda konfigurera enheter:
    
  - Se [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) för instruktioner för Windows-enheter. 
    
  - Se [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md) för att få anvisningar för Android-telefoner och iPhone. 
  
### <a name="mailbox-size"></a>Post lådans storlek

Microsoft 365 Business Premium har en lagrings gräns på 50 GB eftersom den använder Exchange Online plan 1. När du migrerar till Microsoft 365 Business Premium är det lämpligt att tilldela en Exchange Online-plan 2 och ta bort Exchange Online-abonnemanget 1 om någon av dina användare har fler än 50 GB lagrings utrymme.


### <a name="threat-protection"></a>Skydd mot hot

När du har migrerat till Microsoft 365 Business Premium har du Office 365 ATP. Se [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) för en översikt. Om du vill konfigurera läser du [Konfigurera säkra säkerhets](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)meddelanden för ATP, [Konfigurera säkerhet för säkert säkerhets](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)läge för ATP och [Konfigurera anti-nätfiske](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Känslighetsetiketter

Om du vill börja använda känslighets etiketter kan du läsa [Översikt över känslighets etiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) och [skapa och hantera känslighets etiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .
