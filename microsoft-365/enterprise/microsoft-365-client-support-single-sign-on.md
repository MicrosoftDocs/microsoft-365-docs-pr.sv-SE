---
title: Microsoft 365-klientprogram – enkel inloggning
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
ms.openlocfilehash: d0a45c30ffe736cf67e811bce6eb029d6fb50674
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384800"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Microsoft 365-klientprogram – enkel inloggning

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Enkel inloggning (SSO) lägger till säkerhet och bekvämlighet när användarna loggar in på program i Azure Active Directory (Azure AD). Med enkel inloggning loggar användarna in en gång med ett konto för att komma åt lokala Active Directory Domain Services (AD DS)-anslutna enheter, program som tjänst (SaaS) och webb program.

Läs mer om [enkel inloggning](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-platforms"></a>Plattformar som stöds

 - Windows 10 skriv bord<sup>2</sup>
 - Windows 10 moderna appar
 - Webbläsare
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Kompatibla klienter

De senaste versionerna av följande klienter har stöd för enkel inloggning:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access-ikon](../media/o365-access-64x64.png) <br> [Åtkomst](https://products.office.com/access) | ![Ikonen företags Portal](../media/o365-microsoft-64x64.png) <br> [Företags <br> Portal<sup>3, 4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Delve-ikon](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Ikonen kant](../media/o365-edge-64x64.png) <br> [Kant<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-ikon](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Ikonen Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Ikonen Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Lins ikonen](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive för företag-ikon](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![OneNote-ikon](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Outlook-ikon](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Planner-ikon](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Automatisk ström indikator](../media/o365-flow-64x64.png) <br> [<br>Automatisk strömförsörjning](https://flow.microsoft.com) | ![Ikonen PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![PowerPoint-ikon](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Projekt ikon](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Ikonen Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Ikonen fästisar](../media/o365-stickynotes-64x64.png) <br> [Fästisar](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Sway-ikon](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Ikonen Teams](../media/o365-teams-64x64.png) <br> [Team<sup>2, 4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![Ikonen att göra](../media/o365-todo-64x64.png) <br> [Att göra](https://todo.microsoft.com) | ![Visio-ikon](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard-ikon](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Word-ikon](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Yammer-ikon](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-ikon](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-ikon](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> support för Edge-och Kaizala på iOS är snart tillgängligt. <br>
> <sup>2</sup> stöd för OneNote, PowerBI, team och Yammer på Windows 10-skrivbordet finns snart. <br>
> <sup>3</sup> support för whiteboard på Android är snart tillgängligt. <br>
> <sup>4</sup> support för Outlook-, team-och företags portaler på MacOS finns snart. <br>

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
