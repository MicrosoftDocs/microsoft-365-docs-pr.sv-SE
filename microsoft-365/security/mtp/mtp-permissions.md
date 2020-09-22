---
title: Hantera åtkomst till Microsoft Threat Protection data i Microsoft 365 säkerhets Center
description: Lär dig hur du hanterar behörigheter till data i Microsoft Threat Protection
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
ms.openlocfilehash: 96a8694f5cbc7c27d27acbd5ec0aabe8712c6f06
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201081"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Hantera åtkomst till skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt funktioner och data för Microsoft Threat Protection:
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
Åtkomst till Microsoft Threat Protection data kan styras med det scope som tilldelats till användar grupper i Microsoft Defender ATP-baserad åtkomst kontroll (RBAC). Om din åtkomst inte har beställts till en viss uppsättning enheter i Microsoft Defender ATP får du fullständig åtkomst till data i Microsoft Threat Protection. Men när ditt konto har begränsad räckvidd visas bara data om enheterna i ditt område.

Om du till exempel tillhör bara en användar grupp med en Microsoft Defender ATP-roll och den användar gruppen endast har åtkomst till försäljnings enheter kan du endast se data om försäljnings enheter i Microsoft Threat Protection. [Läs mer om RBAC-inställningar i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Kontroller för säkerhets åtkomst för Microsoft Cloud App
Under förhands granskningen upprätthålls inte åtkomst kontroller baserade på säkerhets inställningar för moln programmet. Åtkomst till Microsoft Threat Protection data påverkas inte av de här inställningarna.

## <a name="related-topics"></a>Relaterade ämnen

- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP-RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Säkerhets roller för Cloud App](https://docs.microsoft.com/cloud-app-security/manage-admins)
