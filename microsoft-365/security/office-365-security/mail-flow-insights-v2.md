---
title: Insikter för e-postflöde i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratörer kan läsa mer om insikter och rapporter som är tillgängliga i instrument panelen för e-postflöde i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9ac8b8b0d346d78af252a9e427d0ef2b1a4c4ea
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769024"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-postflödesinsikter i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Administratörer kan använda instrument panelen för e-postflöden i säkerhets & efterlevnad för att upptäcka trender, insikter och vidta åtgärder för att åtgärda problem med e-postflöde i organisationen.

![Instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mail-flow-dashboard-v2.png)

Tillgängliga insikter är:

- [Auto-vidarebefordrade meddelanden insikt](mfi-auto-forwarded-messages-report.md)

- [Åtgärda möjliga e-postloop Insight](mfi-mail-loop-insight.md)<sup>1</sup>

- [Åtgärda regler för långsam e-postflöde, inblick](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [E-postflödeskarta](mfi-mail-flow-map-report.md)

- [Nya domäner vidarekopplas med e-post, Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nya användare vidarebefordrar e-post, Insight](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport om icke godkänd domän](mfi-non-accepted-domain-report.md)

- [Rapport om misslyckad leverans](mfi-non-delivery-report.md)

- [Insikt om utgående och inkommande e-postflöden](mfi-outbound-and-inbound-mail-flow.md)

- [Köer insikt](mfi-queue-alerts-and-queues.md)

- [SMTP Auth-klienter insikt och rapport](mfi-smtp-auth-clients-report.md)

- [Insikten E-postflödesstatus för översta domäner](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> denna inblick visas i det **rekommenderade för** området i instrument panelen för e-postflöde först efter att problemet har upptäckts. Annars visas den inte.

<sup>2</sup> denna inblick visas inte på instrument panelen för e-postflöden, men visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) efter problemet. Annars visas den inte.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Behörigheter som krävs för att visa instrument panelen för e-postflöde

Instrument panelen för e-postflöde är tillgänglig för medlemmar i följande roll grupper:

- **Organisations hantering** i säkerhets & efterlevnad (globala administratörer).

- **[Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** i Azure Active Directory.

- **Flödes administratör** i säkerhets & regelefterlevnad: om en medlem i den här roll gruppen inte är medlem i roll grupperna global administratör eller Exchange-administratör bör du tänka på följande:

  - Användaren måste logga in på säkerhets & Compliance Center direkt vid <https://protection.office.com> .
  - Användaren har bara Skriv behörighet i instrument panelen för e-postflöde.
  - Användaren har inte till gång till administrations centret för Microsoft 365.

Mer information om behörigheter i säkerhets & Compliance Center finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md) och [ge användarna åtkomst till säkerhets & Compliance Center](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Här hittar du instrument panelen för e-postflöde

Öppna säkerhets & Compliance Center <https://protection.office.com> , expandera **e-postflöde** och välj **instrument panel** .

Öppna för att gå direkt till instrument panelen för e-postflöde <https://protection.office.com/mailflow/dashboard> .
