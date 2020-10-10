---
title: Använda anpassade rapporterings lösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, ATP, automatisk undersökning, integrering, anpassad rapport
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
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Lär dig hur du integrerar automatisk undersökning och svar med en egen rapporterings lösning eller tredje part.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 429ceae87e3beeb9ec0a254b120289be4ab51d16
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411980"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Använda API för hanterings aktivitet för egna eller tredje parts rapporterings lösningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Med [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)får du [detaljerad information om automatiserade utredningar](air-view-investigation-results.md). I vissa organisationer används emellertid en egen rapporterings lösning. Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API för hanterings aktivitet i Office 365.

Använd följande resurser för att konfigurera detta:

****

|Resurspool|Beskrivning|
|---|---|
|[Översikt över API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API för hanterings aktivitet i Office 365 ger information om olika åtgärder för användare, administratörer, system och händelser från Microsoft 365-och Azure Active Directory-aktiviteter.|
|[Komma igång med API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program att få åtkomst till Microsoft 365-data. Följ stegen i den här artikeln för att konfigurera detta.|
|[API-referens för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Du kan använda API: t för hanterings aktiviteten för Office 365 för att hämta information om åtgärder och händelser för användare, administratörer, system och principer från Microsoft 365 och Azure AD-aktivitets loggar. Läs den här artikeln om du vill veta mer om hur det fungerar.|
|[API-schema för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Få en översikt över det [gemensamma schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Office 365 ATP-och Response-undersökningar och svarsmeddelande](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) för att få reda på specifika typer av data som finns tillgängliga via API för hanterings aktivitet i Office 365.|
|

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](office-365-atp.md)

- [Automatisk undersökning och svar i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
