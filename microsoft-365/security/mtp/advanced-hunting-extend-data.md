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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842482"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Förläng avancerad jakt täckning med rätt inställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[Avancerad jakt](advanced-hunting-overview.md) är beroende av data som kommer från olika källor, inklusive dina enheter, dina Office 365-arbetsytor, Azure AD och Microsoft Defender för identiteten. För att få den mest omfattande informationen möjlig, se till att du har rätt inställningar i motsvarande data källor.

## <a name="advanced-security-auditing-on-windows-devices"></a>Avancerad säkerhets granskning på Windows-enheter
Aktivera dessa avancerade gransknings inställningar för att få information om aktiviteter på dina enheter, till exempel lokal konto hantering, lokal hantering av säkerhets grupper och tjänst skapande.

| Data | Beskrivning | Schema tabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Konto hantering | Händelser som samlas in som olika `ActionType` värden anger att lokala konton skapas, tas bort och andra relaterade aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska användar konto hantering](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Hantering av säkerhets grupper | Händelser som samlas in som olika `ActionType` värden som anger lokala säkerhets grupper för skapande och andra lokala grupp hanterings aktiviteter | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska hantering av säkerhets grupper](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Tjänst installation | Händelser som fångats in med `ActionType` värdet `ServiceInstalled` , som indikerar att en tjänst har skapats | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuera en avancerad säkerhets granskning: [Granska säkerhets tillägg](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Läs mer om avancerade säkerhets gransknings principer](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender för identitets sensor på domänkontrollant
Om du kör Active Directory lokalt måste du installera Microsoft Defender för identitets sensorn på domänkontrollanten för att hämta data för Microsoft Defender för identiteten. När dessa data installeras och är korrekt konfigurerade feeds de till en avancerad jakt genom Microsoft Defender för identitet och ger en mer holistisk bild av identitets information och händelser i ditt nätverk. Dessa data förbättrar också förmågan hos Microsoft Defender för att skapa relevanta aviseringar som också täcks av Advanced jakt. 

| Data | Beskrivning | Schema tabell | Så här konfigurerar du |
| --- | --- | --- | --- |
| Domänkontrollant | Data från lokala Active Directory-meddelanden som skickas till Microsoft Defender för identitets-och omfattande identitets information, till exempel konto uppgifter, inloggnings aktivitet och Active Directory-frågor | Flera tabeller, inklusive [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)och [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installera Microsoft Defender för identitets sensorn](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Aktivera relevanta Windows-händelser](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
