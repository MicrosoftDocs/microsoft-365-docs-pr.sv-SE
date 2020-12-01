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
ms.openlocfilehash: deeced350ad867a374a486967c2cbd278ba91710
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519335"
---
# <a name="access-the-admin-portal"></a>Gå till administrations portalen

Din gateway till Microsoft Managed Desktop-tjänsten är Microsoft [Azure-portalen](https://portal.azure.com). Mer information om hur du använder och anpassar din Azure Portal-upplevelse finns i [dokumentationen för Azure-portalen](https://docs.microsoft.com/azure/azure-portal/). Tillgänglig i förhands granskning nu kan du också hitta Microsoft Managed Desktop i [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Om du inte känner till funktionerna i den här portalen för enhets hantering kan du läsa [dokumentationen för Microsoft slut punkts hanteraren](https://docs.microsoft.com/mem/).

> [!NOTE]
> Om du väljer att få åtkomst till Microsoft Managed Desktop, i [Microsoft slut punkts Manager](https://endpoint.microsoft.com/) eller från [Azure-portalen](https://portal.azure.com), stöds följande webbläsare:
> - Microsoft Edge (senaste versionen)
> - Microsoft Internet Explorer 11
> - Safari (senaste versionen, endast Mac)
> - Chrome (senaste versionen)
> - Firefox (senaste versionen)

Ditt administratörs konto behöver specifika behörigheter för att få till gång till de administrativa Microsoft-hanterade Skriv bords funktionerna i antingen Azure Portal eller Microsoft Endpoint Manager. Du kan hantera administratörs åtkomst till dessa funktioner inom organisationen med hjälp av RBAC (rollbaserad åtkomst kontroll). Flera administratörs roller för Azure Active Directory (Azure AD) och inbyggda anpassade roller är tillgängliga för att ge mer detaljerad kontroll till olika funktioner på Microsoft Managed Desktop admin-portalen. Mer information om Azure Active Directory-roller finns i [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Till skillnad från roller för Azure AD-administratörer som gäller för en mängd olika Microsoft-produkter och-tjänster är anpassade roller specifika för Microsoft Managed Desktop och garanterar bara åtkomst till administratörs funktionerna för den här tjänsten. Administratörer kan tilldela användare egna roller individuellt eller tillsammans med Azure AD-administratörs roller för att lägga till behörigheter för Microsoft Managed Desktop till befintliga administratörs konton.

Alla roller nedan kan tilldelas för att ge olika åtkomst nivåer:

|Azure AD-roll  |Behörigheter för Microsoft Managed Desktop  |
|---------|---------|
|Global administratör     | Administratörer med den här rollen får **Läs-och Skriv behörighet till alla funktioner** på Microsoft Managed Desktop admin-portalen.         |
|Global läsare     | Administratörer med den här rollen får **skrivskyddade behörigheter till alla funktioner** på Microsoft Managed Desktop admin-portalen.         |
|Intune tjänst administratör     |  Administratörer med den här rollen får **Läs-och Skriv behörighet till funktioner som inte är relaterade till säkerhet** på Microsoft Managed Desktop admin-portalen.       |
|Support administratör för tjänsten     | Administratörer med den här rollen får **skrivskyddade behörigheter till funktioner som inte är relaterade till säkerhet** och **Skriv behörigheter för att hantera support ärenden** på Microsoft Managed Desktop admin-portalen.         |
|Säkerhets administratör | Administratörer med den här rollen får **skrivskyddade behörigheter till alla funktioner** och **Skriv behörigheter för säkerhetsrelaterade funktioner** i Microsoft Managed Desktop i administrations portalen. |
|Säkerhets läsare |Administratörer med den här rollen får **skrivskyddade behörigheter till alla funktioner** på Microsoft Managed Desktop admin-portalen.|

> [!IMPORTANT]
> Endast den globala administratörs rollen har den behörighet som krävs för att *Registrera* din organisation på Microsoft Managed Desktop. Observera att Azure Active Directory-roller ger behörigheter för användar konton i en mängd olika Microsoft-tjänster. När du har slutfört registreringen med Microsoft Managed Desktop bör du alltid använda rollen med *minst* nödvändiga privilegier för att utföra dina andra uppgifter.

 
|Anpassad roll  |Behörigheter för Microsoft Managed Desktop  |
|---------|---------|
|Administratör för Microsoft Managed Desktop service  | När den här rollen tilldelats till en användare ger den administratören **behörighet att läsa och skriva för funktioner som inte är relaterade till säkerhet** på Microsoft Managed Desktop admin-portalen.  |
|Tjänst läsare för Microsoft Managed Desktop | När den här rollen är tilldelad till en användare ger den administratören **skrivskyddade behörigheter till funktioner som inte är relaterade till säkerhet** på Microsoft Managed Desktop admin-portalen. |
|Säkerhets hanteraren i Microsoft Managed Desktop |När den här rollen har tilldelats till en användare får du **bara administratörs behörigheterna läsa och skriva för säkerhetsrelaterade funktioner** på administrations portalen för Microsoft Managed Desktop.   |

> [!NOTE]
> Säkerhetsfunktioner innehåller Säkerhetsrelaterad kommunikation, hantering av säkerhets kontakter, hantering av säkerhetsrelaterade support förfrågningar och åtkomst till säkerhetsrelaterade rapporter. 

## <a name="assigning-roles-to-administrators"></a>Tilldela roller till administratörer

Om du behöver hjälp med att tilldela Azure Active Directory-roller kan du läsa [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

För enkel hantering av de inbyggda rollerna har en säkerhets grupp skapats för varje anpassad roll (till exempel "moderna arbets plats roller – säkerhets chef"). Följ de här stegen om du vill tilldela användare till en av säkerhets grupperna:
1.  Gå till Microsoft Endpoint Manager-portalen
2.  Välj grupper på vänster sida.
3.  Sök efter moderna arbets plats roller och välj sedan gruppen som är kopplad till den roll du vill tilldela. 
4.  Välj medlemmar på vänster sida och välj sedan + Lägg till medlemmar i kommando fältet.
5.  Ange e-postmeddelandet för den person som ska läggas till. Om det är en extern användare måste du bjuda in dem innan du kan tilldela gruppen.
6.  Välj Välj längst ned.

> [!NOTE]
> Det går för närvarande inte att kapsla in säkerhets grupper för roll tilldelning. 
