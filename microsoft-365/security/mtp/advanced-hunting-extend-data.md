---
title: Utöka avancerad jakttäckning med rätt inställningar
description: Kontrollera granskningsinställningarna på Windows-enheter och andra inställningar för att säkerställa att du får de mest omfattande data i avancerad jakt
keywords: avancerad jakt, incident, pivot, enhet, granskningsinställningar, kontohantering, hantering av säkerhetsgrupper, hotjakt, cyberhotjakt, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9c1b9c1853d80d818d97084e2668d3b12b6da0e6
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503226"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Utöka avancerad jakttäckning med rätt inställningar

**Gäller:**
- Microsoft Hotskydd

[Avancerad jakt](advanced-hunting-overview.md) är beroende av data från olika källor, inklusive dina enheter, dina Office 365-arbetsytor, Azure AD och Azure ATP. För att få så omfattande data som möjligt, se till att du har rätt inställningar i motsvarande datakällor.

## <a name="advanced-security-auditing-on-windows-devices"></a>Avancerad säkerhetsgranskning på Windows-enheter
Aktivera de här avancerade granskningsinställningarna för att se till att du får information om aktiviteter på dina enheter, inklusive hantering av lokala konton, hantering av lokala säkerhetsgrupper och skapande av tjänster.

| Data | Beskrivning | Schematabell | Konfigurerar du |
| --- | --- | --- | --- |
| Kontohantering | Händelser som fångas in som olika `ActionType` värden som anger skapande, borttagning av lokala konton och andra kontorelaterade aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en avancerad säkerhetsgranskningsprincip: [Granska hantering av användarkonton](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Hantering av säkerhetsgrupper | Händelser som fångas in som olika `ActionType` värden som anger att lokala säkerhetsgrupper skapas och andra lokala grupphanteringsaktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en avancerad säkerhetsgranskningsprincip: [Granskningssäkerhetsgrupphantering](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Installation av tjänsten | Händelser som fångas med `ActionType` värdet , som anger att en tjänst har `ServiceInstalled` skapats | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuera en avancerad säkerhetsgranskningsprincip: [Tillägg för granskning av säkerhetssystem](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Azure ATP-sensor på domänkontrollanten
Om du kör Active Directory lokalt måste du installera Azure ATP-sensorn på domänkontrollanten för att hämta data för Azure ATP. När de installeras och konfigureras korrekt matas dessa data också in i avancerad jakt via Azure ATP och ger en mer holistisk bild av identitetsinformation och händelser i nätverket. Dessa data förbättrar också möjligheten för Azure ATP att generera relevanta aviseringar som också omfattas av avancerad jakt. 

| Data | Beskrivning | Schematabell | Konfigurerar du |
| --- | --- | --- | --- |
| Domänkontrollant | Data från lokala Active Directory som skickas till Azure ATP, vilket berikar identitetsrelaterad information, till exempel kontoinformation, inloggningsaktivitet och Active Directory-frågor | Flera tabeller, inklusive [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)och [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | [Installera Azure ATP-sensorn](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)|

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)