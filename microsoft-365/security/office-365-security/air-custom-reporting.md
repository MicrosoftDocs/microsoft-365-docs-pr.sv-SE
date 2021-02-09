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
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142981"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Anpassade rapportlösningar eller rapportlösningar från tredje part för Microsoft Defender för Office 365

Med [Microsoft Defender för Office 365](office-365-atp.md)får du detaljerad information om automatiska [undersökningar.](air-view-investigation-results.md) Men vissa organisationer använder också en anpassad lösning eller en rapportlösning från tredje part. Om din organisation vill integrera information om [automatiserade undersökningar](office-365-air.md) med en sådan lösning kan du använda API:t för hanteringsaktivitet i Office 365.

Resurser för att konfigurera integrering

|Resurs|Beskrivning|
|:---|:---|
|[Översikt över API:er för Hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API:t för hanteringsaktivitet i Office 365 innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365 och Azure Active Directory-aktivitetsloggar.|
|[Komma igång med API:er för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för åtkomst till Microsoft 365-data. Följ anvisningarna i den här artikeln för att konfigurera det här.|
|[API för hanteringsaktivitet i Office 365, referens](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Du kan använda API:t för hanteringsaktivitet i Office 365 för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från aktivitetsloggarna för Microsoft 365 och Azure AD. Läs den här artikeln om du vill veta mer om hur det fungerar.|
|[API för hanteringsaktivitet i Office 365. schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Få en översikt över det vanliga [schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och Defender för [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) samt hotundersöknings- och svarsschemat om du vill lära dig mer om specifika typer av data som är tillgängliga via API:t för hanteringsaktivitet i Office 365.|
|

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](office-365-atp.md)
- [Automatiserad undersökning och svar i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
