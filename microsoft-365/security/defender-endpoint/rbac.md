---
title: Använd rollbaserad åtkomstkontroll för att bevilja enkel åtkomst till Microsoft Defender Säkerhetscenter
description: Skapa roller och grupper i dina säkerhetsåtgärder för att bevilja åtkomst till portalen.
keywords: rbac, roll, baserad, åtkomst, kontroll, grupper, kontroll, nivå, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071881"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Hantera portalåtkomst med hjälp av rollbaserad åtkomstkontroll

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- Azure Active Directory
- Office 365

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

Med hjälp av rollbaserad åtkomstkontroll (RBAC) kan du skapa roller och grupper i säkerhetsoperationsteamet för att ge lämplig åtkomst till portalen. Utifrån de roller och grupper du skapar har du full koll på vad användare med åtkomst till portalen kan se och göra. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

Stora geobaserade säkerhetsoperationer grupper använder vanligtvis en tierbaserad modell för att tilldela och auktorisera åtkomst till säkerhetsportaler. Vanliga nivåer omfattar följande tre nivåer:

Tier | Beskrivning
:---|:---
Nivå 1 | **Team/IT-team för lokala säkerhetsåtgärder** <br> Gruppen undersöker och undersöker vanligtvis aviseringar som finns inom deras geolokalisering och eskalerar till nivå 2 i fall där en aktiv åtgärd krävs.
Nivå 2 | **Teamet för regionala säkerhetsåtgärder** <br> Det här teamet kan se alla enheter i deras region och utföra åtgärder.
Nivå 3 | **Teamet för globala säkerhetsåtgärder** <br> Det här teamet består av säkerhetsexperter och har behörighet att se och utföra alla åtgärder från portalen.

Defender för Endpoint RBAC har utformats för att stödja din nivå- eller rollbaserade modell och ger dig detaljerad kontroll över vilka roller som kan se, enheter som de kan komma åt och åtgärder de kan vidta. RBAC-ramverket är centrerat runt följande kontroller:

- **Kontrollera vem som kan vidta specifika åtgärder**
  - Skapa anpassade roller och kontrollera vad Defender för Slutpunkt-funktioner de kan komma åt med detaljerad information.
 
- **Styra vilka som kan se information i viss enhetsgrupp eller -grupp**
  - [Skapa enhetsgrupper](machine-groups.md) med specifika villkor, till exempel namn, taggar, domäner och andra, och tilldela rollåtkomst till dem med hjälp av en viss Azure Active Directory-användargrupp (Azure ACTIVE Directory).

Om du vill implementera rollbaserad åtkomst måste du definiera administratörsroller, tilldela motsvarande behörigheter och tilldela Azure AD-användargrupper tilldelade till rollerna.


### <a name="before-you-begin"></a>Innan du börjar
Innan du använder RBAC är det viktigt att du förstår de roller som kan bevilja behörigheter och konsekvenserna av att aktivera RBAC.


> [!WARNING]
> Innan du aktiverar funktionen är det viktigt att du har en global administratörsroll eller säkerhetsadministratörsroll i Azure AD och att du har dina Azure AD-grupper redo att minska risken med att bli utelåst från portalen. 

När du först loggar in på Microsoft Defender Säkerhetscenter får du antingen fullständig åtkomst eller skrivskyddad åtkomst. Fullständig åtkomst ges till användare med roller som säkerhetsadministratör eller global administratör i Azure AD. Skrivskyddad åtkomst ges till användare med rollen Säkerhetsläsare i Azure AD. 

Någon med rollen Defender för global administratör för Slutpunkt har obegränsad åtkomst till alla enheter, oavsett vilken enhetsgruppsassociatorganisation och tilldelningar av Azure AD-användargrupper som ingår i dem.

> [!WARNING]
> Till en början kan endast användare med global administratör eller säkerhetsadministratör för Azure AD skapa och tilldela roller i Microsoft Defender Säkerhetscenter och därför är det viktigt att ha rätt grupper i Azure AD.
>
> **Om du slår på rollbaserad åtkomstkontroll förlorar användare med skrivskyddad behörighet (till exempel användare som tilldelats rollen Azure AD-säkerhetsläsare) åtkomsten tills de tilldelas till en roll.** 
>
>Användare med administratörsbehörigheter tilldelas automatiskt den inbyggda standardrollen Defender för slutpunktens globala administratörsroll med fullständiga behörigheter. När du har valt att använda RBAC kan du tilldela ytterligare användare som inte är globala Azure AD- eller säkerhetsadministratörer till rollen Global administratör i Defender för Slutpunkt. 
>
> När du har valt att använda RBAC kan du inte återgå till de inledande rollerna som när du först loggade in på portalen. 



## <a name="related-topic"></a>Relaterade ämnen
- [Skapa och hantera enhetsgrupper i Microsoft Defender för Slutpunkt](machine-groups.md)
