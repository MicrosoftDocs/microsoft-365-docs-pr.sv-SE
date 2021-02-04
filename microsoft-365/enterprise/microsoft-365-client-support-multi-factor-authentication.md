---
title: 'Stöd för Microsoft 365-klientappen: Multifaktorautentisering'
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
description: I den här artikeln får du lära dig vilka plattformar, klienter och PowerShell-moduler som har stöd för multifaktorautentisering för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097486"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Stöd för Microsoft 365-klientappen: Multifaktorautentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För att ge ytterligare säkerhetsnivå för inloggningar kan klienter konfigureras för att använda multifaktorautentisering (MFA), som använder både ett användarlösenord och en ytterligare metod för användarverifiering baserat på:

- Något som de äger som inte är lätt dubblerat, till exempel en smartphone.
- Något som användaren har unikt och oumbärligt, till exempel fingeravtryck, ansikte eller annat biometriskt attribut

Läs mer om [multifaktorautentisering.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för multifaktorautentisering. Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Klienter | Android | iOS | Mac| Windows 10 <br> Moderna appar| Windows 10 <br> Skrivbord |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Åtkomst | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Azure Admin | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Företagsportal | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Cortana | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Delve | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Edge | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Excel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Exchange Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Formulär | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office 365 Admin | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |  |
| Kaizala | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Lens| ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Office mobile | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office-portalen | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| OneDrive | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
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
| SharePoint Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Fästisar | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Strömma | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Sway | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Teams | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |
| To Do | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Visio | Saknas | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Whiteboard | Planerat | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Word | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Workplace-analys | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Yammer | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)