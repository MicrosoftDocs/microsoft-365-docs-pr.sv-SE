---
title: Microsoft 365-klientprogram – stöd för villkorlig åtkomst
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
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
ms.openlocfilehash: 60e1c7e9d8208682b715007d527d39b6f9613992
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694916"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Microsoft 365-klientprogram – stöd för villkorlig åtkomst

På den moderna arbets platsen kan användarna komma åt organisationens resurser med olika enheter och appar var som helst. Det innebär att du inte längre kan fokusera på vem som har åtkomst till en resurs. Din organisation måste också ha stöd för hur och var en resurs används i din åtkomst kontroll infrastruktur.

Med Azure Active Directory (Azure AD)-enhet, plats och multifaktorautentisering-baserad villkorlig åtkomst kan du uppfylla det här nya kravet. Villkorsstyrd åtkomst är en funktion i Azure AD som gör att du kan använda kontroller på åtkomsten till appar i din miljö, allt baserat på särskilda villkor och hanterat från en central plats.

Få mer information om [Villkorsstyrd åtkomst i Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Plattformar som stöds

 - Windows 10-skrivbordet
 - Windows 10 moderna appar
 - Webbläsare
 - Android
 - iOS
 - macOS<sup>1</sup>

Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Kompatibla klienter

De senaste versionerna av följande klienter har stöd för villkorlig åtkomst:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-ikon](../media/o365-azure-64x64.png) <br> [Azure AD- <br> portalen ](https://azure.microsoft.com/features/azure-portal/) | ![Access-ikon](../media/o365-access-64x64.png) <br> [Åtkomst](https://products.office.com/access) | ![Ikonen företags Portal](../media/o365-microsoft-64x64.png) <br> [Företags <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Cortana-ikon](../media/o365-cortana-64x64.png) <br> [Cortana](https://www.microsoft.com/cortana) | ![Delve-ikon](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Dynamics 365-ikon](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Ikonen kant](../media/o365-edge-64x64.png) <br> [Fördel](https://www.microsoft.com/windows/microsoft-edge) | ![Exchange-ikon](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Excel-ikon](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Formulär ikon](../media/o365-forms-64x64.png) <br> [Formulärautentisering](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Ikonen Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Ikonen Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Lins ikonen](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Administratörs ikon för Office 365](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> administratör](https://products.office.com/business/manage-office-365-admin-app) | ![OneDrive för företag-ikon](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![OneNote-ikon](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-ikon](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Planner-ikon](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Ikonen PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Automatisk ström indikator](../media/o365-flow-64x64.png) <br> [<br>Automatisk strömförsörjning](https://flow.microsoft.com)
| ![Ikonen PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![PowerPoint-ikon](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Projekt ikon](../media/o365-project-64x64.png) <br> [Massanställningsprojektet](https://products.office.com/project) | ![Ikonen Publisher](../media/o365-publisher-64x64.png) <br> [Skapas](https://products.office.com/publisher) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) 
| ![Skype för företag-ikon](../media/o365-skypeforbusiness-64x64.png) <br> [Skype för <br> företag](https://www.skype.com/business/) | ![Ikonen fästisar](../media/o365-stickynotes-64x64.png) <br> [Fästisar](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Ström ikonen](../media/o365-stream-64x64.png) <br> [Strömma](https://stream.microsoft.com) | ![Sway-ikon](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Ikonen Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![Ikonen att göra](../media/o365-todo-64x64.png) <br> [Att göra](https://todo.microsoft.com) | ![Visio-ikon](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Word-ikon](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Yammer-ikon](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-ikon](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-ikon](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![SharePoint-ikon](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> stöd för OneDrive på MacOS finns snart.

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
