---
title: 'Stöd för Microsoft 365-klientprogram: Single Sign-On'
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
description: I den här artikeln lär du dig vilka plattformar, klienter och PowerShell-moduler som stöder enkel inloggning för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806675"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Stöd för Microsoft 365-klientprogram: Single Sign-On

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Enkel inloggning (SSO) lägger till säkerhet och bekvämlighet när användarna loggar in på program i Azure Active Directory. Med enkel inloggning loggar användarna in en gång med ett konto för att komma åt lokala Active Directory Domain Services (AD DS)-anslutna enheter, program som tjänst (SaaS) och webb program.

Läs mer om [enkel inloggning](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för enkel inloggning. Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://products.office.com/office-system-requirements).
<br>
<br>

| Förvirra | Android | iOS | Mac| Windows 10 <br> Moderna appar| Windows 10 <br> Datorer |
|:---|:---:|:---:|:---:|:---:|:---:|
| Åtkomst | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Företags Portal | Saknas | ![Stöds](../media/check-mark.png) | Disponera | ![Stöds](../media/check-mark.png) | Saknas |
| Cortana | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Delve | Disponera | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Fördel | ![Stöds](../media/check-mark.png) | Disponera | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Excel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Kaizala | ![Stöds](../media/check-mark.png) | Disponera | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Lens| ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Mobile | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office-Portal | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| OneDrive | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera | ![Stöds](../media/check-mark.png) | Disponera |
| OneNote | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera |
| Outlook | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera | ![Stöds](../media/check-mark.png) |
| Planner | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power Apps | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | Disponera | Saknas |
| Automatisk strömförsörjning | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power BI | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Disponera |
| PowerPoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Project | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Publisher | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Skype för företag | Disponera | Disponera | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| SharePoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Fästisar | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Strömma | Disponera | Disponera | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Sway | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Teams | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera | Saknas | Disponera |
| Att göra | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Visio | Saknas | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Whiteboard | Saknas | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Word | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Yammer | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | Disponera |

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
