---
title: Insikter för e-postflöde i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratörer kan läsa mer om insikter och rapporter som är tillgängliga i instrument panelen för e-postflöde i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 977dcef82a4f32980898c7b4392d011340e3d0a2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577799"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-postflödesinsikter i Säkerhets- och efterlevnadscenter

Administratörer kan använda instrument panelen för e-postflöden i säkerhets & efterlevnad för att upptäcka trender, insikter och vidta åtgärder för att åtgärda problem med e-postflöde i organisationen.

![Instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mail-flow-dashboard-v2.png)

Tillgängliga insikter är:

- [Inblick i meddelanden som skickas automatiskt](mfi-auto-forwarded-messages-report.md)

- [Åtgärda möjliga e-postloop Insight](mfi-mail-loop-insight.md)<sup>1</sup>

- [Åtgärda regler för långsam e-postflöde, inblick](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Översikt över e-postflöde](mfi-mail-flow-map-report.md)

- [Nya domäner vidarekopplas med e-post, Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nya användare vidarebefordrar e-post, Insight](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport om icke godkänd domän](mfi-non-accepted-domain-report.md)

- [Rapport om misslyckad leverans](mfi-non-delivery-report.md)

- [Ingående och inkommande e-postflöde](mfi-outbound-and-inbound-mail-flow.md)

- [Inblick i köer](mfi-queue-alerts-and-queues.md)

- [SMTP-AUTH-klienter inblick och rapport](mfi-smtp-auth-clients-report.md)

- [Insikten E-postflödesstatus för översta domäner](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> denna inblick visas i det **rekommenderade för** området i instrument panelen för e-postflöde först efter att problemet har upptäckts. Annars visas den inte.

<sup>2</sup> denna inblick visas inte på instrument panelen för e-postflöden, men visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) efter problemet. Annars visas den inte.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Behörigheter som krävs för att visa instrument panelen för e-postflöde

Instrument panelen för e-postflöde är tillgänglig för medlemmar i följande väg grupper:

- **Organisations hantering** i säkerhets & efterlevnad (globala administratörer).

- **[Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** i Azure AD.

- **Flödes administratör** i säkerhets & regelefterlevnad: om en medlem i den här roll gruppen inte är medlem i roll grupperna global administratör eller Exchange-administratör bör du tänka på följande:

  - Användaren måste logga in på säkerhets & Compliance Center direkt vid <https://protection.office.com> .
  - Användaren har bara Skriv behörighet i instrument panelen för e-postflöde.
  - Användaren har inte till gång till administrations centret för Microsoft 365.

Mer information om behörigheter i säkerhets & Compliance Center finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md) och [ge användarna åtkomst till säkerhets & Compliance Center](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Här hittar du instrument panelen för e-postflöde

Öppna säkerhets & Compliance Center <https://protection.office.com> , expandera **e-postflöde**och välj **instrument panel**.

Öppna för att gå direkt till instrument panelen för e-postflöde <https://protection.office.com/mailflow/dashboard> .
