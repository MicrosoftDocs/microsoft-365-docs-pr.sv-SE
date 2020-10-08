---
title: Klient isolering i Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Den här artikeln innehåller en sammanfattning av hur Microsoft tillämpar klient isolering i moln tjänster som Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384934"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Klient isolering i Microsoft 365

En av de främsta fördelarna med Cloud Computing är begreppet gemensam, gemensam infrastruktur för många kunder samtidigt, vilket leder till stor drifts för delar. Det här konceptet kallas för *flera organisationer*. Microsoft arbetar kontinuerligt för att säkerställa att multi-Tenant-arkitekturer i våra moln tjänster har stöd för säkerhet, konfidentialitet, integritet, integritet och tillgänglighet.

Baserat på de betydande investeringar och erfarenhet som samlats in från [tillförlitliga datorer](https://www.microsoft.com/trust-center) och [livs cykeln för säkerhets utveckling](https://www.microsoft.com/securityengineering/sdl/)har Microsofts moln tjänster utformats med antagandet att alla klient organisationer kan vara farliga för alla andra klient organisationer, och vi har implementerat säkerhets åtgärder för att förhindra att en klient organisation påverkar säkerheten eller tjänsten hos en annan klient organisation eller åtkomst till innehållet i en annan klient organisation.

Två primära mål för underhåll av klient isolering i en miljö med flera innehavare är:

1.    Förhindra läckage av eller obehörig åtkomst till kund innehåll mellan klient organisationer; och
2.    Förhindra att en klient organisations åtgärder påverkar tjänsten för en annan klient organisation negativt

Flera former av skydd har implementerats i Microsoft 365 för att förhindra att kunder kan kompromissa med Microsoft 365-tjänster och-program eller skaffa obehörig åtkomst till information om andra klient organisationer eller Microsoft 365-systemet, inklusive:

- Logisk isolering av kund innehåll inom varje klient organisation för Microsoft 365-tjänster uppnås genom Azure Active Directory-auktorisering och rollbaserad åtkomst kontroll.
- I SharePoint Online finns mekanismer för data isolering på lagrings nivån.
- Microsoft använder rigorös fysisk säkerhet, bakgrunds gallrings och en kryptering med flera nivåer för att skydda konfidentialitet och integritet hos kund innehåll. Alla Microsoft 365-datacenter har till gång till bio metriska kontroller, med de flesta krav på att en hand dator får fysisk åtkomst. Dessutom måste alla amerikanska Microsoft-anställda genomföra en vanlig bakgrunds kontroll som en del av anslags processen. Mer information om de kontroller som används för administrativ åtkomst i Microsoft 365 finns i [microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).
- I Microsoft 365 används teknikbaserade tekniker som krypterar kund innehåll på rest och under överföring, inklusive BitLocker, kryptering för alla filer, TLS (Transport Layer Security) och IPsec (Internet Protocol Security). Specifik information om kryptering i Microsoft 365 finns i [data krypterings teknologier i microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Tillsammans ger de ovanstående skydden robusta logiska isolerings kontroller som skyddar mot hotets skydd och mildrande ämnen.

## <a name="related-links"></a>Relaterade länkar

- [Isolering och åtkomstkontroll i Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Klientisolering i Office Graph och Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Klient isolering i Microsoft 365 search](microsoft-365-isolation-in-microsoft-365-search.md)
- [Klient isolering i Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Resursgränser](microsoft-365-resource-limits.md)
- [Övervaka och testa klientorganisations begränsningar](microsoft-365-monitoring-and-testing.md)
- [Isolering och åtkomst kontroll i Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
