---
title: Tilldela Microsoft 365-licenser till användar konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326513"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Tilldela Microsoft 365-licenser till användar konton

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För den molnbaserade identitets modellen kan du tilldela Microsoft 365-licenser till användar konton när de skapas, beroende på hur du skapar dem.

För Hybrid identitets modellen, när AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången, kopplas de inte automatiskt till en plats eller Microsoft 365-licens. **Du måste konfigurera varje användar konto med en användar plats före eller tillsammans med tilldelningen av en licens.**

I båda fallen måste du tilldela en licens till användar konton så att användarna kan komma åt Microsoft 365-tjänster, till exempel e-post och Microsoft Teams.

Du kan tilldela licenser till användar konton individuellt eller automatiskt via grupp medlemskap.

Om du vill tilldela Microsoft 365-licenser till enskilda användar konton kan du använda:

- [Administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Administrations centret för Azure AD

## <a name="group-based-licensing"></a>Gruppbaserad licensiering

Du kan konfigurera säkerhets grupper i Azure AD så att de automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.
>

Mer information finns i [gruppbaserad licensiering i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Nästa steg

Med en lämplig uppsättning användar konton som har tilldelats licenser är du nu redo att:

- [Implementera säkerhet](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Distribuera klient program vara, till exempel Microsoft 365-appar](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Konfigurera enhets hantering](device-management-roadmap-microsoft-365.md)
- [Konfigurera tjänster och program](configure-services-and-applications.md)
