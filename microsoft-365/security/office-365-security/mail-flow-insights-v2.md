---
title: Insikter i e-postflöde på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratörer kan läsa mer om de insikter och rapporter som är tillgängliga i instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7432eca577fb264126b9fc8f10bdd83de32711cf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289681"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-postflödesinsikter i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Administratörer kan använda instrumentpanelen för e-postflöde i Säkerhets- & efterlevnadscenter för att upptäcka trender, insikter och vidta åtgärder för att åtgärda problem relaterade till e-postflödet i organisationen.

![Instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter](../../media/mail-flow-dashboard-v2.png)

De tillgängliga insikterna är:

- [Auto-vidarebefordrade meddelanden insikt](mfi-auto-forwarded-messages-report.md)

- [Åtgärda möjliga insikter i e-postslingan](mfi-mail-loop-insight.md)<sup>1</sup>

- [Åtgärda insikter för långsamt e-postflöde](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [E-postflödeskarta](mfi-mail-flow-map-report.md)

- [Nya domäner som vidarebefordras e-post, information](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nya användare som vidarebefordrar e-post, information](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport om icke godkänd domän](mfi-non-accepted-domain-report.md)

- [Rapport om misslyckad leverans](mfi-non-delivery-report.md)

- [Insikt om utgående och inkommande e-postflöden](mfi-outbound-and-inbound-mail-flow.md)

- [Köer insikt](mfi-queue-alerts-and-queues.md)

- [SMTP Auth-klienter insikt och rapport](mfi-smtp-auth-clients-report.md)

- [Insikten E-postflödesstatus för översta domäner](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Den här insikten visas **i området Rekommenderas** för dig på instrumentpanelen för e-postflöde först när problemet har upptäckts. Annars visas det inte.

<sup>2</sup> Den här insikten visas inte på instrumentpanelen [](view-mail-flow-reports.md#forwarding-report) för e-postflöde, men visas på sidan Med vidarebefordransrapport när problemet har upptäckts. Annars visas det inte.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Behörigheter som krävs för att visa instrumentpanelen för e-postflöde

Instrumentpanelen för e-postflöde är tillgänglig för medlemmar i följande rollgrupper:

- **Organisationshantering** i Säkerhets- & Efterlevnadscenter (globala administratörer).

- **[Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** i Azure Active Directory.

- **MailFlow-administratör** i Säkerhets- & Efterlevnadscenter. Om kontot inte är medlem i rollgrupperna Organisationshantering eller Exchange-administratör bör du tänka på följande:
  - Användaren måste logga in på säkerhets- & direkt <https://protection.office.com> på.
  - Användaren har skrivskyddsbehörighet endast för instrumentpanelen för e-postflöde.
  - Användaren har inte åtkomst till administrationscentret för Microsoft 365.

Mer information om behörigheter finns i Behörigheter i Säkerhets- [& Efterlevnadscenter](permissions-in-the-security-and-compliance-center.md) och Ge användare åtkomst till Säkerhets- [& Efterlevnadscenter.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Här hittar du instrumentpanelen för e-postflöde

Öppna Säkerhets- & efterlevnadscenter <https://protection.office.com> för, expandera **e-postflödet** och välj sedan **Instrumentpanel.**

Om du vill gå direkt till instrumentpanelen för e-postflöde öppnar du <https://protection.office.com/mailflow/dashboard> .
