---
title: Stöd för Microsoft 365-klientprogram – certifikatbaserad verifikation
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
description: I den här artikeln hittar du information om support för Microsoft 365-klient för certifikatbaserad identifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55d3fa4db6abcd7589cf9fadb9084144cd26c8d7
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384944"
---
# <a name="microsoft-365-client-app-support--certificate-based-authentication"></a>Stöd för Microsoft 365-klientprogram – certifikatbaserad verifikation

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Certifikatbaserad autentisering möjliggör autentisering till Azure Active Directory (Azure AD) med ett klient certifikat på Windows-, Android-eller iOS-enheter. Om du konfigurerar den här funktionen behöver du inte ange användar namn och lösen ord i vissa e-post-och Microsoft Office-program på din mobila enhet.

Lär dig mer om [certifikatbaserad identifiering](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Plattformar som stöds

 - Windows 10 skriv bord<sup>2</sup>
 - Windows 10 moderna appar
 - Webbläsare<sup>3</sup>
 - Android<sup>4</sup>
 - iOS
 - macOS<sup>1</sup> <sup>2</sup>

Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Kompatibla klienter

De senaste versionerna av följande klienter har stöd för certifikatbaserad inloggningsautentisering:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access-ikon](../media/o365-access-64x64.png) <br> [Åtkomst](https://products.office.com/access) | ![Azure-ikon](../media/o365-azure-64x64.png) <br> [Azure AD- <br> portalen ](https://azure.microsoft.com/features/azure-portal/) | ![Ikonen företags Portal](../media/o365-microsoft-64x64.png) <br> [Företags <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Delve-ikon](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Dynamics 365-ikon](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Ikonen kant](../media/o365-edge-64x64.png) <br> [Fördel](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-ikon](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Formulär ikon](../media/o365-forms-64x64.png) <br> [Formulär](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Ikonen Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Ikonen Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Administratörs ikon för Office 365](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> administratör](https://products.office.com/business/manage-office-365-admin-app) | ![Lins ikonen](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive för företag-ikon](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![OneNote-ikon](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-ikon](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Planner-ikon](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Ikonen PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps<sup>3</sup>](https://powerapps.microsoft.com) | ![Automatisk ström indikator](../media/o365-flow-64x64.png) <br> [<br>Automatisk strömförsörjning](https://flow.microsoft.com) | ![Ikonen PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![PowerPoint-ikon](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Projekt ikon](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Ikonen Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Skype för företag-ikon](../media/o365-skypeforbusiness-64x64.png) <br> [Skype för <br> företag](https://www.skype.com/business/) | ![Ikonen fästisar](../media/o365-stickynotes-64x64.png) <br> [Fästisar](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) 
| ![Ström ikonen](../media/o365-stream-64x64.png) <br> [Strömma](https://stream.microsoft.com) | ![Sway-ikon](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Ikonen Teams](../media/o365-teams-64x64.png) <br> [Team<sup>2</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![Ikonen att göra](../media/o365-todo-64x64.png) <br> [Att göra](https://todo.microsoft.com) | ![Visio-ikon](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) 
| ![Whiteboard-ikon](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>3</sup>,<sup>4</sup>](https://whiteboard.microsoft.com/) | ![Word-ikon](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Yammer-ikon](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-ikon](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-ikon](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> stöd för OneDrive på MacOS finns snart. <br>
> <sup>2</sup> stöd för Yammer på Windows-skrivbordet och MacOS finns snart. Stöd för Teams på Windows skriv bord finns snart.<br>
> <sup>3</sup> support för PowerApps och whiteboard i webb program är snart tillgängligt. <br>
> <sup>4</sup> support för whiteboard på Android är snart tillgängligt.

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
