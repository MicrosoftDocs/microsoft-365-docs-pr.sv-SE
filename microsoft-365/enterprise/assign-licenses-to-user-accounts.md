---
title: Tilldela Microsoft 365-licenser till användar konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beskriver hur du tilldelar Microsoft 365-licenser till användar konton, antingen individuellt eller baserat på grupp medlemskap.
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694365"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Tilldela Microsoft 365-licenser till användar konton

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

För den molnbaserade identitets modellen kan du tilldela Microsoft 365-licenser till användar konton när de skapas, beroende på hur du skapar dem.

För Hybrid identitets modellen, när AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången, kopplas de inte automatiskt till en Microsoft 365-licens. Du måste först konfigurera varje användar konto till en användare.

I båda fallen måste du tilldela en licens till användar konton så att användarna kan komma åt Microsoft 365-tjänster, till exempel e-post och Microsoft Teams.

Du kan tilldela licenser till användar konton individuellt eller automatiskt via grupp medlemskap.

Om du vill tilldela Microsoft 365-licenser till enskilda användar konton kan du använda:

- [Administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell för Microsoft 365](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

För automatisk licens tilldelning, se [gruppbaserad licensiering i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Nästa steg

Med alla användar konton som har tilldelats licenser är du nu redo att:

- [Implementera säkerhet](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Distribuera klient program vara, till exempel Microsoft 365-appar](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Konfigurera hantering av mobila enheter i Microsoft 365](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [Konfigurera tjänster och program](configure-services-and-applications.md)
