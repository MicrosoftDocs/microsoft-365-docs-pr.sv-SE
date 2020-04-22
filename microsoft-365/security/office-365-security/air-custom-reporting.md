---
title: Använda anpassade rapporteringslösningar med automatiserad undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Lär dig hur du integrerar automatisk undersökning och svar med en anpassad rapporteringslösning eller tredjepartsrapportering.
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634724"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Använda API:et för hanteringsaktivitet för anpassade rapporteringslösningar eller tredjepartsrapporteringslösningar

Med [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)får du detaljerad information om [automatiska utredningar](air-view-investigation-results.md). Vissa organisationer använder dock också en anpassad rapporteringslösning eller en tredjepartsrapporteringslösning. Om din organisation vill integrera information om automatiska undersökningar med en sådan lösning kan du använda API:et för hanteringsaktivitet för Office 365.

Använd följande resurser för att ställa in detta:

|Resurs  |Beskrivning  |
|---------|---------|
|[Översikt över Api:er för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |Api:et för office 365-hanteringsaktivitet innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure Active Directory-aktivitetsloggar.         |
|[Komma igång med API:er för Hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för att komma åt Microsoft 365-data. Följ stegen i den här artikeln för att konfigurera detta.          |
|[API-referens för Office 365 Management-aktivitet](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Du kan använda API:et för office 365-hanteringsaktivitet för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure AD-aktivitetsloggar. Läs den här artikeln om du vill veta mer om hur detta fungerar.        |
|[API-schema för office 365-hanteringsaktivitet](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Få en översikt över det [gemensamma schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Office 365 ATP- och hotundersöknings- och svarsschemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) om du vill veta mer om specifika typer av data som är tillgängliga via API:et för hanteringsaktivitet i Office 365.         |

## <a name="related-articles"></a>Relaterade artiklar

- [Office 365 ATP](office-365-atp.md)

- [Läs mer om automatisk undersökning och svar i Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)