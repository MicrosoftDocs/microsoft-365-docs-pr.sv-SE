---
title: Hantera åtkomst till Microsoft Threat Protection-data i Microsoft 365-säkerhetscentret
description: Lär dig hur du hanterar behörigheter för data i Microsoft Threat Protection
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, scoping, RBAC
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
ms.openlocfilehash: 110bbe6fe48932217c9bdc009d175161fe9226cd
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809369"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Hantera åtkomst till Microsofts hotskydd

**Gäller:**
- Microsofts hotskydd



Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt Microsoft Threat Protection-funktioner och data:
- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör
- Global läsare
- Säkerhetsläsare

Om du vill granska konton med dessa roller [visar du Behörigheter i Microsoft 365-säkerhetscentret](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Tillgång till funktioner
Åtkomst till specifika funktioner bestäms av din [Azure AD-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Kontakta en global administratör om du behöver åtkomst till specifika funktioner som kräver att du eller din användargrupp tilldelas en ny roll.

### <a name="approve-pending-automated-tasks"></a>Godkänna väntande automatiserade uppgifter
[Automatiserad undersökning och reparation](mtp-autoir-actions.md) kan vidta åtgärder för e-post, vidarebefordran av filer, persistensmekanismer och andra artefakter som hittats under undersökningar. Om du vill godkänna eller avvisa väntande åtgärder som kräver uttryckligt godkännande måste du ha vissa roller tilldelade i Microsoft 365. Mer information finns i [Behörigheter för Åtgärdscenter](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Tillgång till data
Åtkomst till Microsoft Threat Protection-data kan styras med hjälp av det scope som tilldelas användargrupper i Microsoft Defender ATP-rollbaserad åtkomstkontroll (RBAC). Om din åtkomst inte har begränsats till en viss uppsättning enheter i Microsoft Defender ATP har du full åtkomst till data i Microsoft Threat Protection. När ditt konto har scoped visas dock bara data om enheterna i ditt omfång.

Om du till exempel bara tillhör en användargrupp med en Microsoft Defender ATP-roll och den användargruppen endast har fått åtkomst till försäljningsenheter, visas bara data om försäljningsenheter i Microsoft Threat Protection. [Läs mer om RBAC-inställningar i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Åtkomstkontroller för Microsoft Cloud App-säkerhet
Under förhandsversionen framtvingar Microsoft Threat Protection inte åtkomstkontroller baserat på säkerhetsinställningar för Cloud App. Åtkomst till Microsoft Threat Protection-data påverkas inte av dessa inställningar.

## <a name="related-topics"></a>Relaterade ämnen

- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Säkerhetsroller för Molnappar](https://docs.microsoft.com/cloud-app-security/manage-admins)
