---
title: Få tillgång till administratörsportalen
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146277"
---
# <a name="access-the-admin-portal"></a>Få tillgång till administratörsportalen

Din gateway till Tjänsten Microsoft Managed Desktop är Microsoft [Azure-portalen](https://portal.azure.com). Mer information om hur du använder och anpassar din Azure-portalupplevelse i allmänhet finns i [Azure-portaldokumentationen](https://docs.microsoft.com/azure/azure-portal/). 

Ditt administrativa konto behöver särskilda behörigheter för att komma åt Microsoft Managed Desktop Admin-portalen. Du kan hantera administratörsåtkomst till dessa funktioner i organisationen med hjälp av Rollbaserad åtkomstkontroll (RBAC). Mer information om Azure Active Directory-roller finns [i Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Tilldela administratörsanvändarkontona någon av följande roller för att säkerställa åtkomst:

|Azure AD-roll  |Behörigheter för Microsoft Managed Desktop  |
|---------|---------|
|Global administratör     | Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.         |
|Global läsare     | Administratörer med den här rollen har **skrivskyddade behörigheter** för alla funktioner i Microsoft Managed Desktop Admin-portalen.         |
|Administratör för Intune-tjänsten     |  Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.       |
|Administratör för servicesupport     | Administratörer med den här rollen har **läs- och skrivbehörighet** till alla funktioner i Microsoft Managed Desktop Admin-portalen.         |

> [!IMPORTANT]
> Endast rollen Global administratör har de behörigheter som krävs för att *registrera* din organisation på Microsoft Managed Desktop. Tänk på att Azure Active Directory-roller ger användarkonton behörighet för en mängd olika Microsoft-tjänster. När du har slutfört registreringen hos Microsoft Managed Desktop bör du alltid använda rollen med de *lägsta* behörigheter som krävs för att utföra dina andra uppgifter.

## <a name="assigning-roles-to-administrators"></a>Tilldela roller till administratörer

Om du behöver hjälp med att tilldela Azure Active Directory-roller läser du [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).
