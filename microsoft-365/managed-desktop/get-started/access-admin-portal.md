---
title: Tillgång till administrationsportalen
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
description: Hur du hittar och använder administrationsportalen, inklusive att kontrollera åtkomsten till den.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 5b7ba0db52f06f7b3f6fce596015b56c8e46c6c2
ms.sourcegitcommit: 2c4c7ebe9bea52765ece0ed27d3ea77313711b10
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50068959"
---
# <a name="access-the-admin-portal"></a>Åtkomst till administrationsportalen

Din gateway till Microsofts tjänst för hanterade skrivbord är [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Om du inte är bekant med funktionerna i den här portalen för enhetshantering kan du läsa dokumentationen för [Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) stöds följande webbläsare:
> - Microsoft Edge (senaste versionen)
> - Microsoft Internet Explorer 11
> - Safari (endast senaste versionen, Mac)
> - Chrome (senaste versionen)
> - Firefox (senaste versionen)

Ditt administratörskonto behöver specifika behörigheter för att få åtkomst till de administrativa funktionerna i Microsoft Managed Desktop i Microsoft Endpoint Manager. Du kan hantera administratörsåtkomst till de här funktionerna i organisationen genom att använda rollbaserad åtkomstkontroll. Det finns flera Azure Active Directory-administratörsroller (Azure AD) och inbyggda Microsoft Managed Desktop-roller för att ge mer detaljerad kontroll över olika funktioner i administrationsportalen för Microsoft Managed Desktop. Mer information om Azure Active Directory-roller finns i [Administratörsrollbehörigheter i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Till skillnad från Azure AD-administratörsroller som gäller för olika produkter och tjänster från Microsoft, är de inbyggda rollerna specifika för Microsoft Hanterat skrivbord och garanterar bara åtkomst till administratörsfunktioner för den här tjänsten. Administratörer kan tilldela inbyggda roller till användare individuellt eller i kombination med Azure AD-administratörsroller för att lägga till Microsoft Hanterad skrivbordsbehörighet till befintliga administratörskonton.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory-roller med Microsoft Hanterad skrivbordsåtkomst

|Azure AD-roll  |Microsoft Hanterad skrivbordsbehörighet  |
|---------|---------|
|Global administratör     | Administratörer med den här rollen får **läs- och skrivbehörighet till alla funktioner i** administrationsportalen för hanterade datorer.         |
|Global läsare     | Administratörer med den här rollen har **skrivskyddad behörighet till alla funktioner i** Administrationsportalen för hanterade datorer.         |
|Intune-tjänstadministratör     |  Administratörer med den här rollen får **läs- och skrivbehörighet till funktioner som inte är relaterade till säkerhet i** Microsofts administrationsportal för stationära datorer.       |
|Tjänstsupportadministratör     | Administratörer med den här  rollen har skrivskyddad behörighet till funktioner som inte är relaterade till säkerhets- och skrivbehörigheter för att hantera **supportbegäranden** i administrationsportalen för Microsoft Managed Desktop.         |
|Säkerhetsadministratör | Administratörer med den här rollen har **skrivskyddad** behörighet till alla funktioner och skrivbehörigheter för säkerhetsrelaterade funktioner i Microsoft Managed Desktop i administrationsportalen.  |
|Säkerhetsläsare |Administratörer med den här rollen har **skrivskyddad behörighet till alla funktioner i** Administrationsportalen för hanterade datorer.|

Om du behöver hjälp med att tilldela Azure Active Directory-roller kan du läsa mer om [administratörsrollbehörigheter i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Endast rollen Global administratör har nödvändiga behörigheter för att *registrera organisationen* i Microsoft Managed Desktop. Tänk på att Azure Active Directory-roller ger användarkontobehörigheter i en mängd olika Microsoft-tjänster. När du har slutfört registrering på Microsoft Managed  Desktop bör du alltid använda rollen med minst den behörighet som krävs för att utföra dina andra uppgifter.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Inbyggda roller från Microsoft Managed Desktop


|Inbyggd roll  |Microsoft Hanterad skrivbordsbehörighet  |
|---------|---------|
|Microsoft-administratör för hanterad skrivbordstjänst  | När den här rollen tilldelas  till en användare ger den här rollen administratören läs- och skrivbehörighet till funktioner som inte är relaterade till säkerhet i administrationsportalen för Microsoft Hanterad stationär dator.  |
|Microsoft Managed Desktop Service Reader | När den här rollen tilldelas  till en användare ger den här rollen administratören skrivskyddad behörighet till funktioner som inte är relaterade till säkerhet i administrationsportalen för Microsoft Hanterad stationär dator. |
|Microsoft Managed Desktop Security Manager |När den här rollen tilldelas till en användare ger den här rollen administratören läs- och skrivbehörighet endast för säkerhetsrelaterade **funktioner** i administrationsportalen för hanterade microsoft-datorer.   |

> [!NOTE]
> Säkerhetsfunktionerna omfattar säkerhetsrelaterad kommunikation, hantering av säkerhetskontakter, hantering av säkerhetsrelaterade supportförfrågningar och åtkomst till säkerhetsrelaterade rapporter. 

### <a name="assigning-built-in-roles-to-administrators"></a>Tilldela inbyggda roller till administratörer

För att hantera inbyggda roller finns det en säkerhetsgrupp för varje anpassad roll med namnet "Roller på den moderna arbetsplatsen _–_ rollnamn "(t.ex. "Roller på den moderna arbetsplatsen – Säkerhetshanteraren"). Följ de här stegen om du vill tilldela användare till någon av dessa säkerhetsgrupper:
1.  Gå till Microsoft Endpoint Manager-portalen.
2.  Välj **Grupper** till vänster.
3.  Sök efter **roller på den moderna** arbetsplatsen och välj sedan den grupp som är kopplad till den roll som du vill tilldela. 
4.  Välj **Medlemmar** till vänster och välj sedan **+ Lägg till medlemmar** i kommandofältet.
5.  Ange e-postadressen till den person som läggs till. Om de är gäster måste du bjuda in dem innan du kan tilldela gruppen.
6.  Välj **Välj** längst ned.

> [!NOTE]
> Kapsla säkerhetsgrupper för rolltilldelning stöds inte för närvarande. 
