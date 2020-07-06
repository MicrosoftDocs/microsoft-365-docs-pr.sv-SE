---
title: Om Intune-administratörsroller i administrationscentret för Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: Administratörsroller mappar till affärsfunktioner och ger behörighet att utföra särskilda uppgifter i administrationscentret. Tjänstadministratören öppnar till exempel supportbegäranden hos Microsoft.
ms.openlocfilehash: 767cd8dbb44da51f0d26844f761eee7d5862b753
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432477"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Intune-administratörsroller i administrationscentret för Microsoft 365

Din Microsoft 365- eller Office 365-prenumeration innehåller en uppsättning administratörsroller som du kan tilldela användare i organisationen i Administrationscenter för Microsoft 365. Varje administratörsroll mappar till vanliga affärsfunktioner och ger personerna i organisationen behörighet att utföra särskilda uppgifter i administrationscentret.

I Administrationscenter för Microsoft 365 kan du hantera vissa Microsoft Intune-roller. Dessa roller är dock en deluppsättning av rollerna som finns tillgängliga i administrationscentret för Intune. Letar du efter de detaljerade rollbeskrivningarna för Microsoft Intune? Ta en titt på [Rollbaserad åtkomstkontroll (RBAC) med Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Mer information om hur du tilldelar roller i Administrationscenter för Microsoft 365 finns i [Tilldela administratörsroller](assign-admin-roles.md).

::: moniker range="o365-worldwide"

I Administrationscenter för Microsoft 365 går du till **Roller** och väljer sedan en roll för att öppna informationsfönstret. Välj fliken **Behörigheter** om du vill visa en detaljerad lista över vilka behörigheter som administratörer som tilldelats rollen har. Välj fliken **Tilldelad** eller **Tilldelade administratörer** om du vill lägga till användare i roller.

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft Intune-roller i Administrationscenter för Microsoft 365

|Administratörsroll     |Vem ska ha tilldelas denna roll?  |
|---------|---------|
|Programhanterare     |   Tilldela rollen som programhanterare till användare som hanterar livscykel för mobilappar, konfigurerar princip-hanterade appar och visar enhetsinformation och konfigurationsprofiler.  |
|Supportoperatör     |   Tilldela rollen supportoperatör till användare som tilldelar appar och principer till användare och enheter. |
|Intune rolladministratör    |   Tilldela Intune rolladministratör till användare som kan tilldela Intune-behörigheter till andra administratörer och kan hantera anpassade och inbyggda Intune-roller.   |
|Princip- och profilhanterare     |   Tilldela rollen princip- och profilhanterare till användare som hanterar principer för efterlevnad, konfigurationsprofiler och Apple-registrering.   |
|Skrivskyddsoperatör     |   Tilldela rollen skrivskyddsoperatör till användare som endast kan visa användare, enheter, registreringsinformation och konfigureringar.   |
|Skoladministratör     |   Tilldela rollen skoladministratör till användare för fullständig åtkomst till hantering av Windows 10 och iOS-enheter, appar och konfigurationer i Intune for Education.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Delegerad administration för Microsoft-partners

Om du arbetar med en Microsoft-partner kan du tilldela dem administratörsroller. De kan i sin tur tilldela användare i ditt företag – eller i sitt företag – administratörsroller. Det kanske du vill göra om de till exempel konfigurerar och hanterar din onlineorganisation åt dig.
  
Ett partnerföretag kan tilldela följande roller: 
  
- Fullständig administrering, som har samma behörigheter som en global administratör, förutom behörighet att hantera flerfaktorautentisering via partnercentret.

- Begränsad administration, som har samma behörigheter som en supportadministratör.

För att partnerföretaget ska kunna tilldela de här rollerna till användare måste du lägga till partnern som delegerad administratör i kontot. Initiativet till en sådan här process tas av en auktoriserad partner. Partnern skickar ett e-postmeddelande till dig med frågan om du vill ge dem behörighet att fungera som delegerad administratör. Anvisningar finns i [Auktorisera eller ta bort partnerrelationer](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Relaterade artiklar

[Om administratörsroller i Microsoft 365](about-admin-roles.md)

[Tilldela administratörsroller](assign-admin-roles.md)

[Aktivitetsrapporter i administrationscentret för Microsoft 365](../activity-reports/activity-reports.md)