---
title: Utöka den avancerade söktäckningen med rätt inställningar
description: Kontrollera granskningsinställningarna på Windows-enheter och andra inställningar för att se till att du får den mest omfattande informationen under avancerad sökning
keywords: avancerad sökning, incident, pivot, entitet, granskningsinställningar, användarkontohantering, hantering av säkerhetsgrupper, hot efter hot, sökning efter cyberhot, sökning, fråga, telemetri, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500617"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Utöka den avancerade söktäckningen med rätt inställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[Avancerad sökning](advanced-hunting-overview.md) är beroende av data från hela organisationen. För att få så omfattande data som möjligt bör du kontrollera att du har rätt inställningar i motsvarande datakällor.

## <a name="advanced-security-auditing-on-windows-devices"></a>Avancerad säkerhetsgranskning på Windows-enheter

Aktivera de här avancerade granskningsinställningarna för att säkerställa att du får data om aktiviteter på dina enheter, inklusive lokal kontohantering, hantering av lokala säkerhetsgrupper och skapande av tjänster.

Data | Beskrivning | Schematabell | Så här konfigurerar du
-|-|-|-
Kontohantering | Händelser som skapats med olika `ActionType` värden som anger när ett lokalt konto skapas, tas bort och andra kontorelaterade aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Distribuera en princip för avancerad säkerhetsgranskning: [Hantera användarkonton](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Hantering av säkerhetsgrupper | Händelser som fångas som olika `ActionType` värden som anger att lokala säkerhetsgrupper skapas och andra aktiviteter för lokal grupphantering | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en princip för avancerad säkerhetsgranskning: [Granskning av grupphantering för säkerhetsgrupper](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Tjänstinstallation | Händelser som fångats `ActionType` med värdet , som anger att en tjänst har `ServiceInstalled` skapats | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en princip för avancerad säkerhetsgranskning: [Granskningssäkerhetssystemtillägg](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
