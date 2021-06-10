---
title: Hantera åtkomst till Microsoft 365 Defender-data i Microsoft 365 säkerhetscenter
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, Microsoft 365 Defender, M365, säkerhet, MCAS, Cloud App Security, Microsoft Defender för slutpunkt, omfattning, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935635"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Hantera åtkomst till Microsoft 365 Defender med Azure Active Directory globala roller

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Det finns två sätt att hantera åtkomsten till Microsoft 365 Defender
- **Ad-Azure Active Directory (Global Azure Active Directory)**
- **Anpassad rollåtkomst**

Konton som tilldelats **följande AD Azure Active Directory roller (Global Azure Active Directory)** kan komma åt Microsoft 365 Defender-funktioner och data:
- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

Om du vill granska konton med de [här rollerna visar du Behörigheter Microsoft 365 Säkerhetscenter](https://security.microsoft.com/permissions).

**Anpassad rollåtkomst** är en ny funktion i Microsoft 365 Defender och gör att du kan hantera åtkomst till specifika data, uppgifter och funktioner i Microsoft Defender 365. Anpassade roller ger mer kontroll än globala Azure AD-roller, vilket ger användarna bara den åtkomst de behöver med de minst tillåtande rollerna som krävs.  Anpassade roller kan skapas utöver globala Azure AD-roller. [Läs mer om anpassade roller.](custom-roles.md)

> ! [OBS] Den här artikeln gäller endast för hantering av Azure Active Directory rollroller. Mer information om hur du använder en anpassad rollbaserad åtkomstkontroll finns i [Anpassade roller för rollbaserad åtkomstkontroll](custom-roles.md)

## <a name="access-to-functionality"></a>Åtkomst till funktioner
Åtkomst till specifika funktioner bestäms av din [Azure AD-roll.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.

### <a name="approve-pending-automated-tasks"></a>Godkänna väntande automatiserade uppgifter
[Automatisk undersökning och åtgärder kan](m365d-autoir-actions.md) vidta åtgärder för e-postmeddelanden, regler för vidarebefordran, filer, beständighetsmetoder och andra artefakter som påträffades under undersökningar. Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365. Mer information finns i Behörigheter [för Åtgärdscenter](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Tillgång till data
Åtkomst till Microsoft 365 Defender-data kan kontrolleras med hjälp av omfattningen som tilldelats användargrupper i Microsoft Defender för rollbaserad åtkomstkontroll för slutpunkt (RBAC). Om din åtkomst inte har begränsad till en viss uppsättning enheter i Defender för Slutpunkt har du fullständig åtkomst till data i Microsoft 365 Defender. Men när kontot har begränsad omfattning kan du bara se data om enheterna i din omfattning.

Om du till exempel bara tillhör en användargrupp med rollen Microsoft Defender för slutpunkt och den användargruppen endast har åtkomst till säljenheter, visas endast data om säljenheter i Microsoft 365 Defender. [Läs mer om RBAC-inställningar i Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security för åtkomst
Under förhandsgranskningen Microsoft 365 Defender inte åtkomstkontroller baserat på Cloud App Security inställningar. Åtkomst till Microsoft 365 Defender-data påverkas inte av de här inställningarna.

## <a name="related-topics"></a>Relaterade ämnen
- [Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender](custom-roles.md)
- [Azure AD-roller](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender för slutpunkt RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security roller](/cloud-app-security/manage-admins)