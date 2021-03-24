---
title: Tilldela Microsoft 365-licenser till användarkonton
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
description: Här beskrivs hur du tilldelar Microsoft 365-licenser till användarkonton, antingen individuellt eller baserat på gruppmedlemskap.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051538"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Tilldela Microsoft 365-licenser till användarkonton

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För den molnbaserade identitetsmodellen kan du tilldela Microsoft 365-licenser till användarkonton när de skapas, beroende på hur du skapar dem.

När AD DS-användarkonton (Active Directory Domain Services) synkroniseras för första gången för hybrididentitetsmodellen tilldelas de inte automatiskt en plats eller en Microsoft 365-licens. **Du måste konfigurera varje användarkonto med en användarplats innan eller tillsammans med en licens.**

I båda fallen måste du tilldela en licens till användarkonton så att dina användare kan komma åt Microsoft 365-tjänster, till exempel e-post och Microsoft Teams.

Du kan tilldela licenser till användarkonton antingen individuellt eller automatiskt genom gruppmedlemskap.

Om du vill tilldela Microsoft 365-licenser till enskilda användarkonton kan du använda:

- [Administrationscentret för Microsoft 365](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Administrationscentret för Azure AD

## <a name="group-based-licensing"></a>Gruppbaserad licensiering

Du kan konfigurera säkerhetsgrupper i Azure AD för att automatiskt tilldela licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.
>

Mer information finns i [gruppbaserad licensiering i Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>Nästa steg

Med rätt uppsättning användarkonton som har tilldelats licenser är du nu redo att:

- [Implementera säkerhet](../security/defender-365-security/security-roadmap.md)
- [Distribuera klientprogramvara, till exempel Microsoft 365-program](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Konfigurera enhetshantering](device-management-roadmap-microsoft-365.md)
- [Konfigurera tjänster och program](configure-services-and-applications.md)