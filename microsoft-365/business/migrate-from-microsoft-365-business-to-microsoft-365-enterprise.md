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
description: Lär dig hur du flyttar ditt företag från Microsoft 365 Business Premium till Microsoft 365 E3.
ms.openlocfilehash: fbd5c0710bffa92cfc17447094bb9b2683641d5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195528"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrera från Microsoft 365 Business Premium till Microsoft 365 E3

Microsoft 365 Business Premium innehåller allt du behöver för Small Business och kombinerar de bästa molnbaserade Cloud-baserade produktivitets appar med enkel enhets hantering och säkerhet som gör det möjligt för dina anställda att sköta sitt bästa arbete. I vissa fall kan du behöva migrera ditt Microsoft 365 Business Premium-abonnemang till Microsoft 365 E3. 

Ditt företag har till exempel vuxit och behöver mer än 300 licenser (gratulerar, på det sätt).

Eller så behöver företaget företags funktioner, till exempel Microsoft 365-appar för Enterprise, Windows 10 Enterprise, E3 eller företags klient åtkomst licenser (CAL).

Det är enkelt att uppgradera: du kan starta uppgraderingen [från administrations centret](../commerce/subscriptions/upgrade-to-different-plan.md). Alla dina data och din konfiguration i ditt nuvarande abonnemang underhålls. Det finns inget som du kan göra för att förbereda för migreringen och ingenting gör efteråt, förutom de nya funktionerna.

>[!Note]
>Du kan också använda ett Microsoft 365 Business Premium-abonnemang för upp till 300-platser och skaffa ett Microsoft 365 E3-abonnemang för fler än 300 platser. Men Office 365 ATP ingår inte i Microsoft 365 E3. För fortsatta hot skydd bör du lägga till ytterligare Office 365 ATP-licenser så att alla användare i omfattningen av dina Office 365 ATP-principer är licensierade.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise

I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.

| Funktion    | Stöd i Microsoft 365 Business Premium    | Stöd i Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Lokalt**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise, E3| 
| Office-appar *    | [Microsoft 365-applikationer för affärsverksamhet](#office-365-business)    |  Microsoft 365 Apps för företag | 
| **Cloud Productivity-appar**        | | | 
| Exchange Online och Outlook    | 50 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering    | 100 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering | 
| Teams    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive för företag    | 1 TB lagrings gräns per användare    | Oinskränk | 
| Yammer, SharePoint Online, Planner, Stream    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Kund ansvarig för Outlook, MileIQ    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Skydd för hotet**        | | | 
| Reducerings kapacitet för attack ytan    | [Visa den här listan](#threat-protection) | Företags hantering av maskinvarubaserad isolering för Microsoft Edge | 
| Office 365 Avancerat skydd (ATP) abonnemang 1 | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | Ingår inte, men kan läggas till på | 
| **Identitets hantering**        | | | 
| Self-Service lösen ords återställning för Hybrid Azure Active Directory-konton (Azure AD), Azure Multi-factority (MFA), villkorsstyrd åtkomst, tillbakaskrivning för lösen ord för lokala identiteter|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect-hälsa    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-appar enkel inloggning (SSO): 10 appar per användare (Galleri SaaS program som Salesforce) * | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: ingen gräns (lokala program via Azure AD Application Proxy och program som inte är gallerier med hjälp av självbetjänings program)    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Hantera enheter och appar**        | | | 
| Microsoft Intune, Windows autopilot|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Åtkomst till virtuellt skriv bord (VDA)    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|Aktivering av delad dator (SCA)    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimization-paket    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Informationsskydd**        | | | 
| Office 365 skydd mot data förlust, Azure information Protection-abonnemang 1    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Fönster informations skydd för slut punktens DLP    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Klient åtkomst licens (CAL-rättigheter)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| **Efterlevnad**        | | | 
| Obegränsad e-postarkivering    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Efterlevnadshanteraren    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| Håll på plats och tvist    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| MRM (Messaging Records Management) och bevarande principer    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Användare som har tilldelats åtkomst till SaaS-appar kan få åtkomst till upp till 10 appar till gång till dem. Administratörer kan konfigurera SSO och ändra användar åtkomst till olika SaaS-program, men SSO-åtkomst tillåts bara för 10 program per användare åt gången. Alla Office 365-appar räknas som en enda app.

## <a name="migration"></a>Migrering

För att migrera kan du samar beta med din partner för att flytta ditt Microsoft 365 Business Premium-abonnemang och-licenser till ett lämpligt Microsoft 365 E3-abonnemang med sina licenser.

I följande avsnitt beskrivs vilka ändringar du behöver göra, om så är fallet och vad du kan göra efter migreringen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Konfiguration och data för Microsoft 365-prenumeration

Du behöver inte göra några ändringar i ditt nuvarande abonnemang eller data före migreringen, vilket inkluderar:

- Prenumerations konfiguration, till exempel DNS-domännamn.
- Inställningar för användare och grupper, till exempel multifaktorautentisering eller villkorsstyrd åtkomst.
- Produktivitets tjänst konfiguration och deras data, till exempel team, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.

Användarna kan nu få obegränsad lagring i Exchange Online-postlådor och OneDrive för företag-mappar.

Du kan börja använda identifiering av moln program, Azure AD Connect-hälsa och SSO för fler än 10 appar.

>[!Note]
>Användare som migrerats till Microsoft 365 E3 kan inte längre använda Outlook Customer Manager och MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Skydd mot hot

Windows 10 Business innehåller följande skydd:

- Tvingande integritets skydd för operativ systemets start process
- Tvingande integritets skydd för känsliga komponenter
- Avancerade säkerhets problem och en Zero-attack
- Rykte-baserat nätverks skydd för Microsoft Edge, Internet Explorer och Chrome
- Värdbaserade brand väggar
- Begränsningar av utpressnings tro Jan
- Maskinvarubaserad isolering för Microsoft Edge
- Program kontroll som drivs av det intelligenta säkerhets diagrammet
- Enhets kontroll (USB)
- Nätverks skydd för webbaserade hot
- Regler för att förhindra intrång i värd

Windows 10 Enterprise, E3 inkluderar också företags hantering av maskinvarubaserad isolering för Microsoft Edge.

>[!Note]
>Användare som migrerats till Microsoft 365 E3 måste var och en ha en licens för Office 365 ATP för fortsatt skydd. Se till att köpa ytterligare Office 365 ATP-licenser så att alla användare i omfattningen av dina Office 365 ATP-principer är licensierade. 
>

### <a name="device-management-with-intune"></a>Enhets hantering med Intune

Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, som innehåller registrerade enheter och inställningar för enhet och appar.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med autopilot i Windows. När du migrerar till Microsoft 365 E3 inkluderar varje användar licens Windows 10 Enterprise E3, som du även kan installera med Windows autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-applikationer för affärsverksamhet

Din Microsoft 365-app för företag-klient installerad på din enhet kommer automatiskt att börja använda funktionerna i Microsoft 365-appar för företag. Efter migrering kan du nu använda:

 - Volym aktivering via grup princip
 - App-telemetri
 - Uppdatera kontroller
 - Jämför och fråga med kalkyl blad
 - Business Intelligence

