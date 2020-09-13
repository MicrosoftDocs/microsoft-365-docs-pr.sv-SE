---
title: Tillgång till administrationsportalen
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 2ac0bb01c1a941d460e92c7e75e765ceb85b2bc0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546580"
---
# <a name="access-the-admin-portal"></a>Gå till administrations portalen

Din gateway till Microsoft Managed Desktop-tjänsten är Microsoft [Azure-portalen](https://portal.azure.com). Mer information om hur du använder och anpassar din Azure Portal-upplevelse finns i [dokumentationen för Azure-portalen](https://docs.microsoft.com/azure/azure-portal/). Tillgänglig i förhands granskning nu kan du också hitta Microsoft Managed Desktop i [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Om du inte känner till funktionerna i den här portalen för enhets hantering kan du läsa [dokumentationen för Microsoft slut punkts hanteraren](https://docs.microsoft.com/mem/).

Ditt administratörs konto behöver specifika behörigheter för att få till gång till de administrativa Microsoft-hanterade Skriv bords funktionerna i antingen Azure Portal eller Microsoft Endpoint Manager. Du kan hantera administratörs åtkomst till dessa funktioner inom organisationen med hjälp av RBAC (rollbaserad åtkomst kontroll). Flera administratörs roller för Azure AD och inbyggda anpassade roller är tillgängliga för att ge mer detaljerad kontroll till olika funktioner på Microsoft Managed Desktop admin-portalen. Mer information om Azure Active Directory-roller finns i [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Till skillnad från AAD-administratörs roller som gäller för en mängd olika Microsoft-produkter och-tjänster är anpassade roller specifika för Microsoft Managed Desktop och garanterar bara åtkomst till administratörs funktionerna för den här tjänsten. Administratörer kan tilldela anpassade roller till enskilda användare eller tillsammans med administratörs roller i AAD för att lägga till behörigheter för Microsoft Managed Desktop till befintliga administratörs konton.

Alla roller nedan kan tilldelas för att ge olika åtkomst nivåer:

|Azure AD-roll  |Behörigheter för Microsoft Managed Desktop  |
|---------|---------|
|Global administratör     | Administratörer med den här rollen får **Läs-och Skriv behörighet** till alla funktioner på Microsoft Managed Desktop admin-portalen.         |
|Global läsare     | Administratörer med den här rollen får **skrivskyddade behörigheter** till alla funktioner på Microsoft Managed Desktop admin-portalen.         |
|Intune tjänst administratör     |  Administratörer med den här rollen får **Läs-och Skriv behörighet** till alla funktioner på Microsoft Managed Desktop admin-portalen. **Ändra:** Det går inte att komma åt säkerhetsfunktionerna i Microsoft Managed Station ära datorer för september 2020-administratörer med den här rollen.       |
|Support administratör för tjänsten     | Administratörer med den här rollen får **Läs-och Skriv behörighet** till alla funktioner på Microsoft Managed Desktop admin-portalen. **Ändra:** Det går inte att komma åt säkerhetsfunktionerna i Microsoft Managed Station ära datorer för september 2020-administratörer med den här rollen.         |
|Säkerhets administratör | **(I förhands granskning 2020)** Administratörer med den här rollen får skrivskyddade behörigheter till alla funktioner och skriv behörigheter för säkerhetsrelaterade funktioner i Microsoft Managed Desktop i administrations portalen. |
|Säkerhets läsare | **(I förhands granskning 2020)**  Administratörer med den här rollen får skrivskyddade behörigheter till alla funktioner på Microsoft Managed Desktop admin-portalen.|

> [!IMPORTANT]
> Endast den globala administratörs rollen har den behörighet som krävs för att *Registrera* din organisation på Microsoft Managed Desktop. Observera att Azure Active Directory-roller ger behörigheter för användar konton i en mängd olika Microsoft-tjänster. När du har slutfört registreringen med Microsoft Managed Desktop bör du alltid använda rollen med *minst* nödvändiga privilegier för att utföra dina andra uppgifter.

 
|Anpassad roll  |Behörigheter för Microsoft Managed Desktop  |
|---------|---------|
|Administratör för Microsoft Managed Desktop service  | **(I förhands granskning 2020)** När den här rollen kopplas till en användare får administratören **läs & Skriv behörigheter till funktioner som inte är relaterade till säkerhet** på Microsoft Managed Desktop admin-portalen.  |
|Tjänst läsare för Microsoft Managed Desktop | **(I förhands granskning 2020)** När den här rollen kopplas till en användare får administratören **Läs behörighet för funktioner som inte är relaterade till säkerhet** på Microsoft Managed Desktop admin-portalen. |
|Säkerhets hanteraren i Microsoft Managed Desktop | **(I förhands granskning 2020)** När den här rollen tilldelats till en användare får administratören **läs & bara Skriv behörighet för säkerhetsrelaterade funktioner** på Microsoft-administrerad administratör.   |

> [!NOTE]
> Säkerhetsfunktioner innehåller Säkerhetsrelaterad kommunikation, hantering av säkerhets kontakter, hantering av säkerhetsrelaterade support förfrågningar och åtkomst till säkerhetsrelaterade rapporter. 

## <a name="assigning-roles-to-administrators"></a>Tilldela roller till administratörer

Om du behöver hjälp med att tilldela Azure Active Directory-roller kan du läsa [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

För enkel hantering av de inbyggda rollerna har en säkerhets grupp skapats för varje anpassad roll (till exempel "moderna arbets plats roller – säkerhets chef"). Följ de här stegen om du vill tilldela användare till en av säkerhets grupperna:
1.  Gå till Azure-portalen och navigera till Azure Active Directory-bladet.
2.  Välj grupper på vänster sida.
3.  Sök efter moderna arbets plats roller och välj sedan gruppen som är kopplad till den roll du vill tilldela. 
4.  Välj medlemmar på vänster sida och välj sedan + Lägg till medlemmar i kommando fältet.
5.  Ange e-postmeddelandet för den person som ska läggas till. Om det är en extern användare måste du bjuda in dem innan du kan tilldela gruppen.
6.  Välj Välj längst ned.

> [!NOTE]
> Det går för närvarande inte att kapsla in säkerhets grupper för roll tilldelning. 
