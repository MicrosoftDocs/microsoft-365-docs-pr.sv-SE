---
title: 'Stöd för Microsoft 365-klientappen: Certifikatbaserad autentisering'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: I den här artikeln hittar du information om stöd för Microsoft 365-klientappen för certifikatbaserad autentisering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097264"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Stöd för Microsoft 365-klientappen: Certifikatbaserad autentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Modern autentisering är en övergripande term för en kombination av autentiserings- och auktoriseringsmetoder. De omfattar:

- **Autentiseringsmetoder:** Multifaktorautentisering; Certifikatbaserad autentisering för klient.
- **Auktoriseringsmetoder:** Microsofts implementering av Open Authorization (OAuth).

Modern autentisering aktiveras via ett autentiseringsbibliotek, till exempel Active Directory Authentication Library (ADAL) eller Microsoft Authentication Library (MSAL). Modern autentisering är det som klienter använder för att autentisera och auktorisera åtkomst till Microsoft 365-resurser. Modern autentisering utnyttjar OAuth och ger klienter tillgång till Microsoft 365-tjänster på ett säkert sätt utan åtkomst till användarautentiseringsuppgifter. Vid inloggning autentiserar användaren direkt med Azure Active Directory och får ett åtkomst-/uppdateringstokenpar i retur. Åtkomsttoken beviljar klientåtkomst till lämpliga resurser i Microsoft 365-klienten. En uppdateringstoken används för att erhålla en ny åtkomst- eller uppdateringstokenpar när den aktuella åtkomsttoken upphör att gälla.

Modern autentisering har stöd för olika autentiseringsmetoder, till exempel certifikatbaserad autentisering. Klienter på Windows-, Android- eller iOS-enheter kan använda certifikatbaserad autentisering (CBA) för autentisering i Azure Active Directory med ett klientcertifikat på enheten. I stället för ett vanligt användarnamn/lösenord används certifikatet för att hämta ett par åtkomst-/uppdateringstoken från Azure Active Directory.

Läs mer om [certifikatbaserad autentisering.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för certifikatbaserad autentisering när du loggar in på Azure Active Directory-konton i klienten (till exempel när du lägger till ett konto i appen). Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Klienter | Android | iOS | Mac| Windows 10 <br> Moderna appar| Windows 10 <br> Skrivbord |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Åtkomst | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Azure Admin | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Företagsportal | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Cortana | Planerat | Planerat | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Delve | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Edge<sup>1</sup> | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Excel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Exchange Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Formulär | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office 365 Admin | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |  |
| Kaizala | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Lens| ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Office mobile | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office-portalen | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| OneDrive | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Planerat | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| OneNote | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Outlook | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Planner | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power Apps | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Power Automate | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power BI | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| PowerPoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Project | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Publisher | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Skype för företag | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |
| Skype för företag-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| SharePoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| SharePoint Online-administratör | Planerat | Planerat | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Fästisar | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Strömma | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Sway | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Teams | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | Planerat |
| To Do | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Visio | Saknas | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Whiteboard | Planerat | Planerat | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Word | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Workplace-analys | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Yammer | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Planerat | Saknas | Planerat |

>[!NOTE]
><sup>1</sup> Edge för iOS och Android har stöd för certifikatbaserad autentisering när konto lägg till flöden. Edge för iOS och Android stöder inte certifikatbaserad autentisering när autentisering utförs mot webbplatser, som normalt är intranätplatser. <br><br>  I det här scenariot navigerar användaren till en webbplats (vanligtvis i intranätet) där användaren måste autentisera via ett certifikat. Det innebär inte modern autentisering alls och utnyttjar inte ett Microsoft-autentiseringsbibliotek. Det här beror på en begränsning i iOS: iOS förhindrar att appar från tredje part kommer åt [](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) systemnyckelringen där certifikaten lagras (endast Apple-appar och Safari-webbvykontroll kan komma åt systemnyckelringen). <br><br> När Edge förlitar sig på [WebKit-ramverket](https://developer.apple.com/documentation/webkit) för rendering av webbplatser kan Edge inte komma åt systemnyckelringen och ge användaren ett certifikatval. Det här är tyvärr enligt design på grund av Apples arkitektur.

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

