---
title: Utöka den avancerade söktäckningen med rätt inställningar
description: Kontrollera granskningsinställningarna på Windows-enheter och andra inställningar för att se till att du får den mest omfattande informationen under avancerad sökning
keywords: avancerad sökning, incident, pivot, entitet, granskningsinställningar, användarkontohantering, hantering av säkerhetsgrupper, hot efter hot, sökning, sökning, fråga, telemetri, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f4b1399b77583e95b109575a9577d8b1af89e6ad
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952674"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Utöka den avancerade söktäckningen med rätt inställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

[Avancerad sökning](advanced-hunting-overview.md) använder data från olika källor, till exempel dina enheter, Office 365-arbetsytor, Azure AD och Microsoft Defender för identitet. För att få så omfattande data som möjligt bör du kontrollera att du har rätt inställningar i motsvarande datakällor.

## <a name="advanced-security-auditing-on-windows-devices"></a>Avancerad säkerhetsgranskning på Windows-enheter
Aktivera de här avancerade granskningsinställningarna för att säkerställa att du får data om aktiviteter på dina enheter, inklusive lokal kontohantering, hantering av lokala säkerhetsgrupper och skapande av tjänster.

| Data | Beskrivning | Schematabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Kontohantering | Händelser som skapats med olika `ActionType` värden som anger när ett lokalt konto skapas, tas bort och andra kontorelaterade aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Distribuera en princip för avancerad säkerhetsgranskning: [Hantera användarkonton](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Hantering av säkerhetsgrupper | Händelser som fångas som olika `ActionType` värden som anger att lokala säkerhetsgrupper skapas och andra aktiviteter för lokal grupphantering | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en princip för avancerad säkerhetsgranskning: [Granskning av grupphantering för säkerhetsgrupper](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Tjänstinstallation | Händelser som fångats `ActionType` med värdet , som anger att en tjänst har `ServiceInstalled` skapats | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en princip för avancerad säkerhetsgranskning: [Granskningssäkerhetssystemtillägg](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender för identitets sensor på domänkontrollanten
Om du kör Active Directory lokalt måste du installera Microsoft Defender för identitets sensor på domänkontrollanten för att hämta data för Microsoft Defender för identitet. När dessa data är installerade och korrekt konfigurerade hittar du också avancerad sökning via Microsoft Defender för identitet och ger en mer detaljerad bild av identitetsinformation och händelser i nätverket. Dessa data förbättrar också möjligheten för Microsoft Defender för identitet att generera relevanta aviseringar som även omfattas av avancerad sökning. 

| Data | Beskrivning | Schematabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Domänkontrollant | Data från lokalt Active Directory som skickas till Microsoft Defender för identitet, och identifiering av identitetsrelaterad information, till exempel kontoinformation, inloggningsaktivitet och Active Directory-frågor | Flera tabeller, inklusive [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)och [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installera Microsoft Defender för identitets sensor](/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivera relevanta Windows-händelser](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint. [Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor. Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)