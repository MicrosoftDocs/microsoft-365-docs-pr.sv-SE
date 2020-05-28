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
description: Läs om hur du flyttar ditt företag från Microsoft 365 Business Premium till Microsoft 365 E3.
ms.openlocfilehash: 6a795d96ccae7e054e7e52d4fd60a4e73b3c71dd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401996"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrera från Microsoft 365 Business Premium till Microsoft 365 E3

Microsoft 365 Business Premium har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att göra sitt bästa. I vissa fall kan du dock behöva migrera din Microsoft 365 Business Premium-prenumeration till Microsoft 365 E3. 

Ditt företag har till exempel vuxit och behöver mer än 300 licenser (grattis, förresten).

Eller så behöver ditt företag företagsfunktioner, till exempel Microsoft 365 Apps for Enterprise, Windows 10 Enterprise E3 eller Enterprise Client Access Licenses (CALs).

Uppgradering är enkelt: du kan starta [uppgraderingen från administrationscentret](../commerce/subscriptions/upgrade-to-different-plan.md). Alla dina data och konfiguration i din nuvarande prenumeration underhålls. Det finns inget för dig att göra för att förbereda migreringen och inget att göra efteråt, förutom att dra nytta av de nya funktionerna.

>[!Note]
>Du kan också använda en Microsoft 365 Business Premium-prenumeration på upp till 300 platser och få en Microsoft 365 E3-prenumeration på mer än 300 platser. Office 365 ATP ingår dock inte i Microsoft 365 E3. För fortsatt skydd av hot bör du lägga till ytterligare Office 365 ATP-licenser så att alla användare i office 365 ATP-polisen är licensierade.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.

| Funktion    | Stöd i Microsoft 365 Business Premium    | Stöd i Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Lokalt**        | | | 
| Windows 10    | Windows 10 Företag  |     Windows 10 Företag E3| 
| Office-appar*    | [Microsoft 365-appar för företag](#office-365-business)    |  Microsoft 365 Apps för företag | 
| **Molnproduktivitetsappar**        | | | 
| Exchange Online och Outlook    | Lagringsgräns på 50 GB per postlåda och obegränsad Exchange Online-arkivering    | Lagringsgräns på 100 GB per postlåda och obegränsad Exchange Online-arkivering | 
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive för företag    | 1 TB lagringsgräns per användare    | Obegränsad | 
| Yammer, SharePoint Online, Planerare, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Outlook kundansvarig, MileIQ    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Skydd mot hot**        | | | 
| Angripa ytreduceringsfunktioner    | [Se den här listan](#threat-protection) | Företagshantering av maskinvarubaserad isolering för Microsoft Edge | 
| Office 365 Advanced Threat Protection (ATP) Plan 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte, men kan läggas till på | 
| **Identitetshantering**        | | | 
| Återställning av lösenord för självbetjäning för hybridkonton i Azure Active Directory (Azure AD), Azure Multi-Factor Authentication (MFA), Villkorlig åtkomst, återställning av lösenord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Identifiering av molnapp, Azure AD Connect-hälsotillstånd    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-appar Enkel inloggning (SSO): 10 appar per användare (Galleri SaaS-appar som Salesforce)* | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| SSO för Azure AD Premium 1: ingen gräns (Lokala appar via Azure AD Application Proxy och appar som inte är gallerier med självbetjäningsmallar för appintegrering)    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Enhets- och apphantering**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Virtuell skrivbordsåtkomst (VDA)    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Virtuellt windows-skrivbord (WVD)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Delad datoraktivering (SCA)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Optimeringspaket för Microsoft Desktop    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Informationsskydd**        | | | 
| Office 365 Data Loss Prevention, Azure Information Protection Plan 1    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Windows-informationsskydd för slutpunktS-DLP    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Licens för klientåtkomst (CAL-rättigheter)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Efterlevnad**        | | | 
| Obegränsad e-postarkivering    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Efterlevnadspoäng/efterlevnadshanterare    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Ediscovery    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| På plats och tvistemål    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| BEVARANDETAGGAR och bevarandeprinciper för meddelandehandlingar (MESSAGING Records Management) och bevarandeprinciper    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
||||

\*Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 appar. Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst tillåts endast för 10 appar per användare åt gången. Alla Office 365-appar räknas som ett enda program.

## <a name="migration"></a>Migrering

Om du vill migrera kan du arbeta med din partner för att flytta din Microsoft 365 Business Premium-prenumeration och dina licenser till en lämplig Microsoft 365 E3-prenumeration med sina licenser.

I följande avsnitt beskrivs vilka ändringar du behöver göra, om några, och vad du kan göra efter migreringen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Konfiguration och data för Microsoft 365-prenumeration

Du behöver inte göra några ändringar i din aktuella prenumeration eller dina data innan du migrerar, vilket inkluderar:

- Prenumerationskonfiguration, till exempel DNS-domännamn.
- Användar- och gruppkonton och autentiseringsinställningar, till exempel multifaktorautentisering eller principer för villkorlig åtkomst.
- Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.

Användarna kan nu njuta av obegränsat lagringsutrymme i Exchange Online-postlådorna och OneDrive för företag-mapparna.

Du kan börja använda Cloud App Discovery, Azure AD Connect Health och SSO för mer än 10 appar.

>[!Note]
>Användare som migreras till Microsoft 365 E3 kan inte längre använda Outlook Customer Manager och MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Skydd mot hot

Windows 10 Business innehåller följande skydd:

- Integritet verkställighet av operativsystemet starta upp processen
- Integritetstillverkning av känsliga driftkomponenter
- Avancerad sårbarhet och zero-day utnyttja mildrande åtgärder
- Ryktesbaserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome
- Värdbaserad brandvägg
- Reduceringar av ransomware
- Maskinvarubaserad isolering för Microsoft Edge
- Programstyrning som drivs av Intelligent Security Graph
- Enhetskontroll (USB)
- Nätverksskydd för webbaserade hot
- Regler för intrångsskydd för värdbrott

Windows 10 Enterprise E3 innehåller även företagshantering av maskinvarubaserad isolering för Microsoft Edge.

>[!Note]
>Användare som migreras till Microsoft 365 E3 kräver var och en en Office 365 ATP-licens för fortsatt hotskydd. Var noga med att köpa ytterligare Office 365 ATP-licenser så att alla användare i office 365 ATP-polisen har licens. 
>

### <a name="device-management-with-intune"></a>Enhetshantering med Intune

Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket inkluderar registrerade enheter och enhets- och appinställningar.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med Windows AutoPilot. När du migrerar till Microsoft 365 E3 innehåller varje användarlicens Windows 10 Enterprise E3, som du också kan installera med Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-appar för företag

Din Microsoft 365 Apps for business-klient som är installerad på dina enheter börjar automatiskt använda funktionerna i Microsoft 365 Apps för företag. Efter migreringen kan du nu använda:

 - Volymaktivering via grupprincip
 - App telemetri
 - Uppdatera kontroller
 - Kalkylblad jämföra och fråga
 - Business intelligens

