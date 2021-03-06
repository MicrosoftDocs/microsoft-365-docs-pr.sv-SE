---
title: Grunderna i att identifiera hot i Utforskaren och i realtid i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Använd Utforskaren eller identifieringar i realtid för att undersöka och reagera på hot effektivt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083194"
---
# <a name="explorer-and-real-time-detections-basics"></a>Grundläggande om identifiering av realtid i Utforskaren

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I den här artikeln:

- [Skillnader mellan Identifiering av Utforskaren och Realtidsidentifiering](#differences-between-explorer-and-real-time-detections)
- [Obligatoriska licenser och behörigheter](#required-licenses-and-permissions)

> [!NOTE]
> Det här är en del av en **serie** med tre artiklar om **Utforskaren (kallas även Hotutforskaren),** e-postsäkerhet och Grundläggande identifieringar i Utforskaren och **Realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem). De andra två artiklarna i den här serien är [Hot efter hot i Utforskaren](threat-hunting-in-threat-explorer.md) och [E-postsäkerhet med Utforskaren.](email-security-in-microsoft-defender.md)

I den här artikeln förklaras skillnaden mellan rapportering av identifiering av realtid och de licenser och behörigheter som krävs.

Om din organisation har Microsoft Defender för [Office 365](defender-for-office-365.md) [](#required-licenses-and-permissions)och du har behörighet kan du använda  **Utforskaren** (kallas även **Threat Explorer)** eller identifiering i realtid för att upptäcka och åtgärda hot.

Gå till Microsoft 365 Defender <https://security.microsoft.com> **e-postsamarbete** **i & Microsoft 365 Defender och** välj sedan **Utforskaren** _eller_ Identifiering av realtid.

Med dessa verktyg kan du:

- Se skadlig programvara som upptäckts Microsoft 365 säkerhetsfunktioner.
- Visa nätfiske-URL och klicka på bedömningsdata.
- Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren.
- Undersök skadlig e-post med mera.

Mer information finns i [E-postsäkerhet med Utforskaren.](email-security-in-microsoft-defender.md)

## <a name="differences-between-explorer-and-real-time-detections"></a>Skillnader mellan Identifiering av Utforskaren och Realtidsidentifiering

- *Realtidsidentifiering är* ett rapporteringsverktyg som finns i Defender för Office 365 abonnemang 1. *Threat Explorer* är ett sök- och åtgärdsverktyg för hot som finns i Defender för Office 365 abonnemang 2.
- Med rapporten Realtidsidentifiering kan du visa identifieringar i realtid. Threat Explorer gör detta också, men det ger ytterligare information för en viss attack, till exempel markera attackkampanjer och [](automated-investigation-response-office.md)ger säkerhetsgrupper möjlighet att åtgärda hot (inklusive utlösa en automatiserad undersökning och svarsundersökning).
- Vyn *All e-post* är tillgänglig i Utforskaren med hot, men ingår inte i rapporten om identifieringar i realtid.
- Filtreringsfunktioner och åtgärder för filtrering ingår i Utforskaren för hot. Mer information finns i [Microsoft Defender för Office 365 Beskrivning: Funktionstillgänglighet i Defender för Office 365 abonnemang.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>Obligatoriska licenser och behörigheter

Du måste ha [Microsoft Defender Office 365](defender-for-office-365.md) kunna använda Utforskaren eller identifieringar i realtid:

- Utforskaren ingår endast i Defender för Office 365 abonnemang 2.
- Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.

Säkerhetsåtgärder-team måste tilldela licenser för alla användare som ska skyddas av Defender för Office 365 och vara medvetna om att identifieringar i Utforskaren och Realtidsidentifiering visar identifieringsdata för licensierade användare.

Om du vill visa och *använda Utforskaren* eller Identifiering i realtid måste du ha följande behörigheter:

- I Defender för Office 365:
  - Organisationshantering
  - Säkerhetsadministratör (det här kan tilldelas Azure Active Directory administrationscentret ( <https://aad.portal.azure.com> )
  - Säkerhetsläsare
- I Exchange Online:
  - Organisationshantering
  - View-Only organisationshantering
  - View-Only mottagare
  - Efterlevnadshantering

Mer information om roller och behörigheter finns i följande artiklar:

- [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md)
- [Behörigheter i Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Mer information

- [Hotutforskaren samlar in e-postinformation på sidan för e-post entitet](mdo-email-entity-page.md)
- [Hitta och undersöka skadlig e-post som har levererats](investigate-malicious-email-that-was-delivered.md)
- [Visa skadliga filer som upptäckts SharePoint Online, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Automatisk undersökning och svar i Microsoft Threat Protection](automated-investigation-response-office.md)
