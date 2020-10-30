---
title: 'Support för Microsoft 365-klientprogram: villkorlig åtkomst'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig vilka plattformar, klienter och PowerShell-moduler som stöder villkorlig åtkomst för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806688"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Support för Microsoft 365-klientprogram: villkorlig åtkomst

På den moderna arbets platsen kan användarna komma åt organisationens resurser med olika enheter och appar var som helst. Det innebär att du inte längre kan fokusera på vem som har åtkomst till en resurs. Din organisation måste också ha stöd för hur och var en resurs används i din åtkomst kontroll infrastruktur.

Med Azure Active Directory-enhet, plats och multifaktorautentisering-baserad villkorlig åtkomst kan du uppfylla det här nya kravet. Villkorsstyrd åtkomst är en funktion i Azure Active Directory som gör att du kan använda kontroller för åtkomst till appar i din miljö, allt baserat på specifika villkor och hanteras från en central plats.

Läs mer om [villkorlig åtkomst för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar stöder villkorlig åtkomst. Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

<br>
<br>

| Förvirra | Android | iOS | Mac| Windows 10 <br> Moderna appar| Windows 10 <br> Datorer |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Åtkomst | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Azure-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Företags Portal | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Cortana | Disponera | Disponera | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Delve | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Fördel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Excel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Exchange Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Formulär | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office 365-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |  |
| Kaizala | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Lens| ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Office Mobile | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office-Portal | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| OneDrive | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| OneNote | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Outlook | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Planner | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power Apps | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | Disponera | Saknas |
| Automatisk strömförsörjning | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power BI | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| PowerPoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Project | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Publisher | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Skype för företag | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT ||
| SharePoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| SharePoint Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Fästisar | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Strömma | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Sway | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Teams | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |
| Att göra | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Visio | Saknas | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Whiteboard | Disponera | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Word | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Företags analys | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Yammer | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
