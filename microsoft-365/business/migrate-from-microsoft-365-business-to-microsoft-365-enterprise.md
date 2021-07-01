---
title: Migrera från Microsoft 365 Business till Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig hur du flyttar företaget från Microsoft 365 Business Premium till Microsoft 365 E3.
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227628"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrera från Microsoft 365 Business Premium till Microsoft 365 E3

Microsoft 365 Business Premium har allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att arbeta på bästa sätt. I vissa fall kan du emellertid behöva migrera din prenumeration Microsoft 365 Business Premium till Microsoft 365 E3.

Företaget har till exempel vuxit och behöver fler än 300 licenser (grattis).

Eller, ditt företag behöver företagsfunktioner, som Microsoft 365-appar för företag, Windows 10 Enterprise E3 eller CALs (Enterprise Client Access Licenses).

Det är enkelt att uppgradera: du kan [starta uppgraderingen från administrationscentret.](../commerce/subscriptions/upgrade-to-different-plan.md) Alla data och konfigurationer i din nuvarande prenumeration behålls. Du behöver inte förbereda dig för migreringen utan att göra något efteråt, förutom att dra nytta av de nya funktionerna.

> [!NOTE]
> Du kan också använda en Microsoft 365 Business Premium-prenumeration för upp till 300 platser och få en Microsoft 365 E3-prenumeration för fler än 300 platser. Men Microsoft Defender för Office 365 ingår inte i Microsoft 365 E3. För fortsatt skydd mot hot bör du lägga till ytterligare Defender för Office 365-licenser så att alla användare som omfattas av Defender för Office 365-säkerhet är licensierade.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.

| Funktion    | Support i Microsoft 365 Business Premium    | Support i Microsoft 365 E3 |
|:-------|:-----|:-----|
| **Lokalt**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3|
| Office appar*    | [Microsoft 365-applikationer för affärsverksamhet](#office-365-business)    |  Microsoft 365 Apps för företag |
| **Produktivitetsprogram för molnet**        | | |
| Exchange Online och Outlook    | 50 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering    | 100 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering |
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| OneDrive för företag    | 1 TB lagringsgräns per användare    | Obegränsat |
| Yammer, SharePoint Online, Planner, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| **Skydd mot hot**        | | |
| Funktioner för att minska attackytan    | [Visa den här listan](#threat-protection) | Företagshantering av maskinvarubaserad avgränsning för Microsoft Edge |
| Microsoft Defender för Office 365 Abonnemang 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte men kan läggas till på |
| **Identitetshantering**        | | |
| Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Identifiering av molnapp, Azure AD Anslut hälsa    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365-appar Enkel inloggning Sign-On (SSO): 10 program per användare (SaaS-galleriappar som Salesforce)* | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: ingen gräns (lokala appar via Azure AD-programproxy och icke-galleriappar med hjälp Self-Service mallar för appintegrering)    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| **Enhets- och apphantering**        | | |
| Microsoft Intune, Windows Autopilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|Virtual Desktop Access (VDA)    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|Windows Virtuellt skrivbord (WVD)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|Aktivering av delad dator (SCA)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Microsofts paket för skrivbordsoptimering    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| **Informationsskydd**        | | |
| Office 365 Dataförlustskydd, Azure Information Protection Plan 1    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Fönsterinformationsskydd för slutpunkt DLP    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| **Klientåtkomstlicens (CAL-rättigheter)**    | | |
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| **Efterlevnad**        | | |
| Obegränsad e-postarkivering    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Efterlevnadshanteraren    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| eDiscovery    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Bevarande av juridiska skäl på plats och bevarande av juridiska skäl    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| Bevarandetaggar (MRM) för hantering av meddelandeposter (MRM) och bevarandeprinciper    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
||||

\* Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 appar. Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst är endast tillåten för 10 appar per användare i taget. Alla Office 365 räknas som en enskild app.

## <a name="migration"></a>Migrering

Migrera genom att samarbeta med din partner för att flytta din Microsoft 365 Business Premium-prenumeration och licenser till ett lämpligt Microsoft 365 E3-abonnemang med dess licenser.

I följande avsnitt beskrivs vilka ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 prenumerationskonfiguration och data

Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:

- Prenumerationskonfiguration, till exempel DNS-domännamn.
- Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.
- Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.

Användarna kan nu använda obegränsat lagringsutrymme i Exchange Online postlådor och OneDrive för företag mappar.

Du kan börja använda Cloud App Discovery, Azure AD Anslut Health och SSO för fler än 10 appar.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Skydd mot hot

Windows 10 Business omfattar följande skydd:

- Tvingande integritet för operativsystemets uppstartsprocess
- Tvingande integritet för känsliga operativsystemkomponenter
- Avancerade sårbarheter och nolldagars minskningar av sårbarheter
- Ryktesbaserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome
- Värdbaserad brandvägg
- Minskning av utpressningstrojaner
- Maskinvarubaserad avgränsning för Microsoft Edge
- Programkontroll som drivs av intelligent Graph
- Enhetskontroll (USB)
- Nätverksskydd för webbaserade hot
- Skydd mot intrång i värden

Windows 10 Enterprise E3 innehåller även företagshantering av maskinvarubaserad avgränsning för Microsoft Edge.

> [!NOTE]
> Användare som migreras till Microsoft 365 E3 måste ha en Microsoft Defender för Office 365 licens för fortsatt skydd mot hot. Se till att köpa ytterligare Defender Office 365 licens så att alla användare som omfattas av Defender för Office 365 licensieras.

### <a name="device-management-with-intune"></a>Enhetshantering med Intune

Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket omfattar registrerade enheter och enhets- och appinställningar.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med Windows AutoPilot. När du migrerar till Microsoft 365 E3 inkluderar varje användarlicens Windows 10 Enterprise E3, som du även kan installera med Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-applikationer för affärsverksamhet

Din Microsoft 365-applikationer för affärsverksamhet klient som är installerad på dina enheter börjar automatiskt använda funktionerna i Microsoft 365-appar för företag. Efter migreringen kan du nu använda:

- Grupprincipstöd
- Spreadsheet compare and inquire
- Business Intelligence
