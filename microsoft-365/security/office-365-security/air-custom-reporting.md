---
title: Anpassade rapportlösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, ATP, automatisk undersökning, integrering, anpassad rapport
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207452"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Anpassade eller tredjepartsrapporteringslösningar för Microsoft Defender för Office 365

Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar.](air-view-investigation-results.md) Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part. Om din organisation vill integrera information om [automatiserade undersökningar](office-365-air.md) med en sådan lösning kan du använda API:t för hanteringsaktivitet i Office 365.

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar.](air-view-investigation-results.md) Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part. Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API:t för hanteringsaktivitet i Office 365.

|Resurs|Beskrivning|
|:---|:---|
|[Översikt över API:er för hantering av Office 365](/office/office-365-management-api/office-365-management-apis-overview)|API:t för hanteringsaktivitet i Office 365 innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure Active Directory-aktivitetsloggar.|
|[Komma igång med API:er för hantering av Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för att få åtkomst till Microsoft 365-data. Följ stegen i den här artikeln för att konfigurera detta.|
|[API för hanteringsaktivitet i Office 365, referens](/office/office-365-management-api/office-365-management-activity-api-reference)|Du kan använda API:t för hanteringsaktivitet i Office 365 för att hämta information om användar-, administratörs-, system- och principåtgärder och -händelser från Microsoft 365- och Azure AD-aktivitetsloggar. Läs den här artikeln om du vill veta mer om hur det fungerar.|
|[API för hanteringsaktivitet i Office 365. schema](/office/office-365-management-api/office-365-management-activity-api-schema)|Få en översikt över det vanliga [schemat](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och Defender för [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) och undersökning av hot och svarsschema om du vill veta mer om specifika typer av data som är tillgängliga via API:t för hanteringsaktivitet i Office 365.|
|

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](defender-for-office-365.md)
- [Automatiserad undersökning och svar i Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
