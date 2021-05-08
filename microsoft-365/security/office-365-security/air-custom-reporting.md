---
title: Anpassade rapportlösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad undersökning, integrering, anpassad rapport
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig att integrera automatisk undersökning och svar med en anpassad eller tredje parts rapporteringslösning.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275018"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Anpassade eller tredjepartsrapporteringslösningar för Microsoft Defender för Office 365

Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar](air-view-investigation-results.md). Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part. Om din organisation vill integrera information om [automatiserade undersökningar](office-365-air.md) med en sådan lösning kan du använda API:t Office 365 för hanteringsaktivitet.

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar](air-view-investigation-results.md). Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part. Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API:t för Office 365 hanteringsaktivitet.

|Resurs|Beskrivning|
|:---|:---|
|[Office 365 Översikt över API:er för hantering](/office/office-365-management-api/office-365-management-apis-overview)|API:Office 365 för hanteringsaktivitet innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365 och Azure Active Directory aktivitetsloggar.|
|[Komma igång Office 365 API:er för hantering](/office/office-365-management-api/get-started-with-office-365-management-apis)|I Office 365 Management API används Azure AD för att tillhandahålla autentiseringstjänster för ditt program för åtkomst Microsoft 365 data. Följ stegen i den här artikeln för att konfigurera detta.|
|[API för hanteringsaktivitet i Office 365, referens](/office/office-365-management-api/office-365-management-activity-api-reference)|Du kan använda API:t Office 365 Management Activity för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure AD-aktivitetsloggar. Läs den här artikeln om du vill veta mer om hur det fungerar.|
|[API för hanteringsaktivitet i Office 365. schema](/office/office-365-management-api/office-365-management-activity-api-schema)|Få en översikt över [Common-schemat](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och Defender för Office 365 och threat [investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) om du vill veta mer om specifika typer av data som är tillgängliga via API:t för hanteringsaktivitet Office 365 säkerhetshanteringsaktivitet.|
|

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](defender-for-office-365.md)
- [Automatiserad undersökning och svar i Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
