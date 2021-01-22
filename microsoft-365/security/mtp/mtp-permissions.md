---
title: Hantera åtkomst till Microsoft 365 Defender-data i Säkerhetscenter för Microsoft 365
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930144"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Hantera åtkomst till Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Konton som tilldelats följande Azure Active Directory-roller (AD) har åtkomst till funktioner och data i Microsoft 365 Defender:
- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

Om du vill granska konton med dessa [roller kan du visa behörigheter i Säkerhetscenter för Microsoft 365.](https://security.microsoft.com/permissions)

## <a name="access-to-functionality"></a>Åtkomst till funktioner
Åtkomst till specifika funktioner bestäms av din [Azure AD-roll.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.

### <a name="approve-pending-automated-tasks"></a>Godkänna väntande automatiserade uppgifter
[Automatiserad undersökning och åtgärd kan](mtp-autoir-actions.md) vidta åtgärder på e-postmeddelanden, regler för vidarebefordran, filer, mekanismer för beständighet och andra artefakter som påträffas under undersökningar. Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365. Mer information finns i behörigheter [för Åtgärdscenter.](mtp-action-center.md#required-permissions-for-action-center-tasks)

## <a name="access-to-data"></a>Åtkomst till data
Åtkomst till data i Microsoft 365 Defender kan kontrolleras med hjälp av omfattningen som tilldelats användargrupper i Microsoft Defender för slutpunktsrollbaserad åtkomstkontroll (RBAC). Om åtkomsten inte har begränsad till en viss uppsättning enheter i Defender för Slutpunkten har du fullständig åtkomst till data i Microsoft 365 Defender. Men när ditt konto har begränsad omfattning visas bara data om enheterna i din omfattning.

Om du till exempel bara tillhör en användargrupp med rollen Microsoft Defender för slutpunkt och den användargruppen endast har åtkomst till försäljningsenheter visas bara data om säljenheter i Microsoft 365 Defender. [Läs mer om RBAC-inställningar i Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Åtkomstkontroller för Microsoft Cloud App-säkerhet
Under förhandsgranskningen tillämpar Microsoft 365 Defender inte åtkomstkontroller baserat på inställningar för molnappsäkerhet. Åtkomst till data i Microsoft 365 Defender påverkas inte av de här inställningarna.

## <a name="related-topics"></a>Relaterade ämnen

- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender för slutpunkt RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Roller för molnappsäkerhet](https://docs.microsoft.com/cloud-app-security/manage-admins)
