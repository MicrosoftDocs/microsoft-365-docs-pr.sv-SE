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
description: Läs om hur du flyttar ditt företag till Microsoft 365 Business Premium från Office 365 E3.
ms.openlocfilehash: 23d024ed7f18fe6a5f5dc9b59e3ad20069dc3e6a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402244"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrera från Office 365 E3 till Microsoft 365 Business Premium 

Microsoft 365 Business Premium har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet. Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business Premium för extra säkerhetsfunktioner.

Migrering är enkelt: Först byter du licenser och all data- och användarinformation i din nuvarande prenumeration bibehålls. Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.

| Funktion    | Stöd i Microsoft 365 Business Premium    | Stöd i Office 365 E3 | 
|:-------|:-----|:-----|
| **Lokalt**        | | | 
| Office-appar<sup>1</sup>    | Microsoft 365-appar för företag    |  Microsoft 365 Apps för företag | 
| **Molnproduktivitetsappar**        | | | 
| Exchange Online och Outlook    | Lagringsgräns på 50 GB per postlåda och obegränsad Exchange Online-arkivering    | Lagringsgräns på 100 GB per postlåda och obegränsad Exchange Online-arkivering | 
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| OneDrive för företag    | 1 TB lagringsgräns per användare    | Obegränsad | 
| Yammer, SharePoint Online, Planerare, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| Outlook kundansvarig, MileIQ    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Skydd mot hot**        | | | 
| Office 365 Advanced Threat Protection (ATP) Plan 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte, men kan läggas till på | 
| **Identitetshantering**        | | | 
| Återställning av lösenord för självbetjäning för hybridkonton i Azure Active Directory (Azure AD), Azure Multi-Factor Authentication (MFA), Villkorlig åtkomst, återställning av lösenord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Enhets- och apphantering**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Aktivering av delad dator|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| Uppgradera rättigheter till Windows 10 Pro från Win 7/8.1 Pro-licenser|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Informationsskydd**        | | |
|Förebyggande av dataförlust i Office 365|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, Bitlocker verkställighet|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, känslighetsetiketter|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licens för klientåtkomst (CAL-rättigheter)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Ingår i Office 365 E3](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 Business Premium-versionen av Office-apparna innehåller inte volymaktivering via grupprincip, programtelemetri, uppdateringskontroller, kalkylbladsjämförelse och fråga eller Business Intelligence.

## <a name="migration"></a>Migrering

Information om hur du migrerar prenumerationen finns i [Ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) för instruktioner om du bara vill flytta några personer till Microsoft 365 Business Premium. Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md)eller arbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business Premium-prenumeration.
I följande avsnitt beskrivs de ändringar du behöver göra, om några, och vad du kan göra efter migreringen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Konfiguration och data för Office 365 E3-prenumeration
Du behöver inte göra några ändringar i din aktuella prenumeration eller dina data innan du migrerar, vilket inkluderar:

- Prenumerationskonfiguration, till exempel DNS-poster och domännamn.
- Användar- och gruppkonton och autentiseringsinställningar, till exempel multifaktorautentisering eller principer för villkorlig åtkomst.
- Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.

### <a name="windows-10"></a>Windows 10

Om windows inte redan finns på Windows Pro Creator-uppdateringen [uppgraderar du dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Konfigurera principer för att skydda användarenheter och filer

> [!NOTE]
> Om du konfigurerar Office 365 MDM-principer och -enheter visas dessa enheter på sidan **Enheter** i administrationscentret för Microsoft 365. Alla principer som du har ställt in visas i listan över klassiska principer i [Intune-portalen](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

När du har tilldelat licenser till Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.

Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium visas installationsguiden på startsidan och kan följa [installationsstegen Microsoft 365 Business Premium i installationsguiden](set-up.md) för att skydda filer och mobila enheter.

Du kan också utföra de här stegen på sidan Enheter:
  
1. I administrationscentret, i den vänstra navigeringscentralen, går du till **Enhetsprinciper** \> **Policies**.
    
2. På sidan **Enhetsprinciper** väljer du **Lägg till**.
    
3. I fönstret **Lägg till princip** ger du principen ett namn och väljer sedan en **principtyp** i listrutan. 
    
     Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter. Mer information finns i följande länkar:
    
  - [Ange inställningar för appskydd för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md)
    
  - [Ange programskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md)
    
  - [Ange inställningar för enhetsskydd för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
  
4. När du har ställt in principer kan du och dina anställda konfigurera enheter:
    
  - Se [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) för steg för Windows-enheter. 
    
  - Se [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone. 

### <a name="threat-protection"></a>Skydd mot hot

När du har migrerat till Microsoft 365 Business Premium har du Office 365 ATP. Mer om du vill ha en översikt i [Office 365 ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Information om hur du konfigurerar finns [i konfigurera ATP-säkra länkar,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) [konfigurera ATP-säkra bilagor](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera [ATP-anti-nätfiske](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Känslighetsetiketter

Om du vill börja använda känslighetsetiketter läser du [Översikt över känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) och [skapar och hanterar video för känslighetsetiketter.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
