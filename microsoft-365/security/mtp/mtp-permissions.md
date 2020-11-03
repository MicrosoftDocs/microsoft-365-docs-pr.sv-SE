---
title: Hantera åtkomst till Microsoft 365 Defender-data i Microsoft 365 säkerhets Center
description: Lär dig hur du hanterar behörigheter till data i Microsoft 365 Defender
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Avancerat skydd, scope, omfattning, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847254"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Hantera åtkomst till Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt Microsoft 365 Defender-funktioner och-data:
- Global administratör
- Säkerhetsadministratör
- Säkerhets ansvarig
- Global läsare
- Säkerhets läsare

[Visa behörigheter i säkerhets Center för Microsoft 365](https://security.microsoft.com/permissions)för att granska konton med de här rollerna.

## <a name="access-to-functionality"></a>Till gång till funktioner
Åtkomsten till specifika funktioner bestäms av din [Azure AD-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användar grupp är tilldelad en ny roll.

### <a name="approve-pending-automated-tasks"></a>Godkänn väntande automatiska uppgifter
[Automatisk undersökning och reparation](mtp-autoir-actions.md) kan utföra åtgärder på e-post, vidarebefordrings regler, filer, beständiga mekanismer och andra artefakter under undersökningar. För att godkänna eller avvisa väntande åtgärder som kräver explicit godkännande måste du ha vissa roller tilldelade i Microsoft 365. Mer information finns i [behörigheter för åtgärds Center](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Till gång till data
Åtkomst till Microsoft 365 Defender-data kan styras med det scope som är tilldelat till användar grupper i Microsoft Defender för slut punkts rollbaserad åtkomst kontroll (RBAC). Om din åtkomst inte har beställts till en viss uppsättning enheter i Defender för slut punkt får du fullständig åtkomst till data i Microsoft 365 Defender. Men när ditt konto har begränsad räckvidd visas bara data om enheterna i ditt område.

Om du till exempel tillhör bara en användar grupp med en Microsoft Defender för slut punkts roll och den användar gruppen endast har åtkomst till försäljnings enheter kan du endast se data om försäljnings enheter i Microsoft 365 Defender. [Läs mer om RBAC-inställningar i Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Kontroller för säkerhets åtkomst för Microsoft Cloud App
Under förhands granskningen upprätthåller inte Microsoft 365 Defender åtkomst kontroller baserade på säkerhets inställningar för Cloud App. Åtkomst till Microsoft 365 Defender-data påverkas inte av de här inställningarna.

## <a name="related-topics"></a>Relaterade ämnen

- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender för slut punkts RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Säkerhets roller för Cloud App](https://docs.microsoft.com/cloud-app-security/manage-admins)
