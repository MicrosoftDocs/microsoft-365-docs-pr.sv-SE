---
title: Förläng avancerad jakt täckning med rätt inställningar
description: Kontrol lera gransknings inställningar på Windows-enheter och andra inställningar så att du får den mest omfattande informationen i avancerad jakt
keywords: Avancerad jakt, händelse, pivot, enhet, gransknings inställningar, användar konto hantering, säkerhets grupp hantering, hot om cyberterrorism, sökning, frågor, telemetri, Microsoft 365, Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 39beff1ea5e983af53cdb954783c11f13569a022
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413956"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Förläng avancerad jakt täckning med rätt inställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

[Avancerad jakt](advanced-hunting-overview.md) bygger på data från olika källor, inklusive dina enheter, dina Office 365-arbetsytor, Azure AD och Azure ATP. För att få den mest omfattande informationen möjlig, se till att du har rätt inställningar i motsvarande data källor.

## <a name="advanced-security-auditing-on-windows-devices"></a>Avancerad säkerhets granskning på Windows-enheter
Aktivera dessa avancerade gransknings inställningar för att få information om aktiviteter på dina enheter, till exempel lokal konto hantering, lokal hantering av säkerhets grupper och tjänst skapande.

| Data | Beskrivning | Schema tabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Konto hantering | Händelser som samlas in som olika `ActionType` värden anger att lokala konton skapas, tas bort och andra relaterade aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska användar konto hantering](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Hantering av säkerhets grupper | Händelser som samlas in som olika `ActionType` värden som anger lokala säkerhets grupper för skapande och andra lokala grupp hanterings aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska hantering av säkerhets grupper](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Tjänst installation | Händelser som fångats in med `ActionType` värdet `ServiceInstalled` , som indikerar att en tjänst har skapats | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska säkerhets tillägg](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Azure ATP-sensor på domänkontrollanten
Om du kör Active Directory lokalt måste du installera Azure ATP-sensorn på domänkontrollanten för att hämta data för Azure ATP. När dessa data installeras och är korrekt konfigurerade feeds de till avancerad jakt genom Azure ATP och ger en mer holistisk bild av identitets information och händelser i ditt nätverk. Dessa data förbättrar också möjligheten för Azure ATP att skapa relevanta larm som också täcks av avancerad jakt. 

| Data | Beskrivning | Schema tabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Domänkontrollant | Data från lokala Active Directory som skickas till Azure ATP och använder identitets relaterad information, till exempel konto uppgifter, inloggnings aktivitet och Active Directory-frågor | Flera tabeller, inklusive [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)och [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installera Azure ATP-sensorn](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivera relevanta Windows-händelser](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
