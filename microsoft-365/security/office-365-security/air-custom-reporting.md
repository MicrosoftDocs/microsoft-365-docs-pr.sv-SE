---
title: Använda anpassade rapporterings lösningar med automatiserad undersökning och svar
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
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
description: Lär dig hur du integrerar automatisk undersökning och svar med en egen rapporterings lösning eller tredje part.
ms.openlocfilehash: cd7eb016ecd250eef56039e0135237c1caebadf8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656903"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Använda API för hanterings aktivitet för egna eller tredje parts rapporterings lösningar

Med [Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)får du [detaljerad information om automatiserade utredningar](air-view-investigation-results.md). I vissa organisationer används emellertid en egen rapporterings lösning. Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API för hanterings aktivitet i Office 365.

Använd följande resurser för att konfigurera detta:

****

|Resurspool|Beskrivning|
|---|---|
|[Översikt över API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API för hanterings aktivitet i Office 365 ger information om olika åtgärder för användare, administratörer, system och händelser från Microsoft 365-och Azure Active Directory-aktiviteter.|
|[Komma igång med API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program att få åtkomst till Microsoft 365-data. Följ stegen i den här artikeln för att konfigurera detta.|
|[API-referens för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Du kan använda API: t för hanterings aktiviteten för Office 365 för att hämta information om åtgärder och händelser för användare, administratörer, system och principer från Microsoft 365 och Azure AD-aktivitets loggar. Läs den här artikeln om du vill veta mer om hur det fungerar.|
|[API-schema för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Få en översikt över det [gemensamma schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Office 365 ATP-och Response-undersökningar och svarsmeddelande](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) för att få reda på specifika typer av data som finns tillgängliga via API för hanterings aktivitet i Office 365.|
|

## <a name="related-articles"></a>Relaterade artiklar

- [Office 365 Avancerat skydd](office-365-atp.md)

- [Lär dig mer om automatisk undersökning och svar i skydd mot Microsoft Threat](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)