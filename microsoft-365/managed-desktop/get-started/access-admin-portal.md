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
ms.openlocfilehash: 2facd506497cbdab42f2d8b051fbd50f82432927
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770607"
---
# <a name="access-the-admin-portal"></a>Få åtkomst till administrationsportalen

Din gateway till Microsoft Hanterat skrivbord är [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Om du inte känner till funktionerna i den här portalen för enhetshantering kan du läsa mer [Microsoft Endpoint Manager .](/mem/)

> [!NOTE]
> I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) stöds följande webbläsare:
> - Microsoft Edge (senaste versionen)
> - Safari (endast den senaste versionen, Mac)
> - Chrome (senaste versionen)
> - Firefox (senaste versionen)

Ditt administratörskonto behöver särskilda behörigheter för att få åtkomst Microsoft Hanterat skrivbord administratörsfunktioner i Microsoft Endpoint Manager. Du kan hantera administratörsåtkomst till de här funktionerna i organisationen genom att använda rollbaserad åtkomstkontroll. Flera Azure Active Directory-administratörsroller (Azure AD) och inbyggda Microsoft Hanterat skrivbord-roller är tillgängliga för att ge mer detaljerad kontroll över olika funktioner Microsoft Hanterat skrivbord administrationsportalen. Mer information om hur Azure Active Directory roller finns i [Behörigheter för administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Till skillnad från Azure AD-administratörsroller som gäller för olika produkter och tjänster från Microsoft är de inbyggda rollerna specifika för Microsoft Hanterat skrivbord och garanterar bara åtkomst till administratörsfunktionerna för den här tjänsten. Administratörer kan tilldela inbyggda roller till användare individuellt eller i kombination med Azure AD-administratörsroller för att lägga Microsoft Hanterat skrivbord behörighet till befintliga administratörskonton.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory roller med Microsoft Hanterat skrivbord åtkomst

|Azure AD-roll  |Microsoft Hanterat skrivbord behörigheter  |
|---------|---------|
|Global administratör     | Administratörer med den här rollen får **läs- och skrivbehörighet till alla funktioner** Microsoft Hanterat skrivbord administrationsportalen.         |
|Global läsare     | Administratörer med den här rollen har **skrivskyddad behörighet till alla funktioner** Microsoft Hanterat skrivbord administrationsportalen.         |
|Intune-tjänstadministratör     |  Administratörer med den här rollen får **läs- och skrivbehörighet till funktioner som inte är relaterade till säkerhet** Microsoft Hanterat skrivbord administrationsportalen.       |
|Tjänstsupportadministratör     | Administratörer med den här rollen har skrivskyddad behörighet till funktioner som inte är relaterade till **säkerhets-** och skrivbehörigheter för att hantera **supportbegäranden** i Microsoft Hanterat skrivbord-administrationsportalen.         |
|Säkerhetsadministratör | Administratörer med den här rollen har **skrivskyddad** behörighet till alla funktioner och skrivbehörigheter för säkerhetsrelaterade funktioner i Microsoft Hanterat skrivbord administrationsportalen.  |
|Säkerhetsläsare |Administratörer med den här rollen har **skrivskyddad behörighet till alla funktioner** Microsoft Hanterat skrivbord administrationsportalen.|

Om du behöver hjälp med att tilldela Azure Active Directory kan du läsa behörigheter [för administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Endast rollen Global administratör har de behörigheter som krävs för *att registrera* organisationen i Microsoft Hanterat skrivbord. Observera att Azure Active Directory med roller ger användarkonton behörighet för flera olika Microsoft-tjänster. När du har slutfört Microsoft Hanterat skrivbord bör du alltid använda  rollen med minst den behörighet som krävs för att utföra dina andra uppgifter.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Inbyggda roller som tillhandahålls av Microsoft Hanterat skrivbord


|Inbyggd roll  |Microsoft Hanterat skrivbord behörigheter  |
|---------|---------|
|Microsoft Hanterat skrivbord Tjänstadministratör  | När den här rollen tilldelas till en användare ger den här rollen administratören läs- och skrivbehörighet till **funktioner** som inte är relaterade till säkerhet Microsoft Hanterat skrivbord administrationsportalen.  |
|Microsoft Hanterat skrivbord Service Reader | När den här rollen tilldelas till en användare ger den här rollen administratören skrivskyddad behörighet till **funktioner** som inte är relaterade till säkerhet Microsoft Hanterat skrivbord administrationsportalen. |
|Microsoft Hanterat skrivbord Säkerhetshanteraren |När den här rollen tilldelas till en användare, ger den här rollen administratör endast behörighet att läsa och skriva för säkerhetsrelaterade **funktioner** Microsoft Hanterat skrivbord administrationsportalen.   |

> [!NOTE]
> Säkerhetsfunktionerna omfattar säkerhetsrelaterad kommunikation, hantering av säkerhetskontakter, hantering av säkerhetsrelaterade supportförfrågningar och åtkomst till säkerhetsrelaterade rapporter. 

### <a name="assigning-built-in-roles-to-user"></a>Tilldela inbyggda roller till användaren

För enkel hantering av inbyggda roller finns det en säkerhetsgrupp för varje anpassad roll med namnet "Roller på en modern arbetsplats _–_ rollnamn"(t.ex. "Roller på modern arbetsplats – säkerhetshanteraren"). Så här tilldelar du användare till någon av dessa säkerhetsgrupper:
1.  Gå till Microsoft Endpoint Manager portalen.
2.  Välj **Grupper** till vänster.
3.  Sök efter **Roller på den moderna** arbetsplatsen och välj sedan den grupp som är kopplad till den roll som du vill tilldela. 
4.  Välj **Medlemmar** till vänster och välj sedan **+ Lägg till medlemmar** i kommandofältet.
5.  Ange e-postadressen till den person som läggs till. Om de är gäster måste du bjuda in dem innan du kan tilldela gruppen.
6.  Välj **Välj** längst ned.

> [!NOTE]
> Kapslade säkerhetsgrupper för rolltilldelning stöds inte för närvarande. 

### <a name="assigning-built-in-roles-to-groups"></a>Tilldela inbyggda roller till grupper

Om du behöver tilldela en eller flera av de inbyggda rollerna till en befintlig grupp gör du så här:
1. Gå till [portal.azure.com](https://portal.azure.com/).
2. Sök efter och öppna **Enterprise-program.**
3. Ändra **programtypsfiltret** till _Microsoft-program_ och välj sedan **Använd**.
4. Sök efter och välj _Moderna workplace kund-API:er._
5. Välj **Användare och grupper** i fönstret till vänster och välj sedan + Lägg till **användare/grupp.**
6. Sök efter den grupp du vill använda **i Användare och grupper.**
7. Sök efter den aktuella rollen **från Välj en** roll och välj den.
8. Välj **Tilldela**.
