---
title: Tenant Isolation i Microsoft 365
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
description: Den här artikeln innehåller en sammanfattning av hur Microsoft tillämpar innehavarisolering i molntjänster som Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923082"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Tenant Isolation i Microsoft 365

En av de främsta fördelarna med molnbaserad databehandling är konceptet med en delad, gemensam infrastruktur över flera kunder samtidigt, vilket leder till att många kunder blir större. Det här begreppet kallas *för flera innehavare.* Microsoft arbetar kontinuerligt för att säkerställa att arkitekturer för flera innehavare i våra molntjänster har stöd för säkerhet på företagsnivå, konfidentialitet, sekretess, integritet och tillgänglighetsstandarder.

Microsofts molntjänster har utformats utifrån antagandet [](https://www.microsoft.com/securityengineering/sdl/)att alla innehavare potentiellt är aktuella för alla andra klientorganisationen och vi har implementerat säkerhetsåtgärder för att förhindra att en klientorganisations säkerhet eller tjänst påverkar säkerheten eller tjänsten hos en annan klientorganisation, eller att få åtkomst till innehållet i en annan klientorganisation. [](https://www.microsoft.com/trust-center)

De två primära målen med att behålla innehavarisolering i en miljö med flera klientorganisationen är:

1.    Förhindra läckage av, eller obehörig åtkomst till, kundinnehåll i flera klientorganisationen. och
2.    Förhindra att en klientorganisations åtgärder påverkar tjänsten för en annan klientorganisation negativt

Flera olika former av skydd har implementerats i hela Microsoft 365 för att förhindra att kunder komprometteras Microsoft 365-tjänster eller -program eller få obehörig åtkomst till informationen från andra klientprogram eller till Microsoft 365-systemet, inklusive:

- Logisk avgränsning av kundinnehållet i varje klientorganisation för Microsoft 365 tjänster kan åstadkommas Azure Active Directory auktorisering och rollbaserad åtkomstkontroll.
- SharePoint Online tillhandahåller mekanismer för dataisolering på lagringsnivån.
- Microsoft använder fysisk säkerhet, bakgrundskontroller och en flerlagerskrypteringsstrategi för att skydda kundinnehållets konfidentialitet och integritet. Alla Microsoft 365 har biometriska åtkomstkontroller, med mest krav på palmutskrifter för att få fysisk åtkomst. Dessutom krävs alla USA-baserade Microsoft-anställda för att genomföra en standardbakgrundskontroll som en del av anställningsprocessen. Mer information om de kontroller som används för administrativ åtkomst i Microsoft 365 finns i [Microsoft 365 Administrationsåtkomstkontroller.](/compliance/assurance/assurance-administrative-access-controls-overview)
- Microsoft 365 använder tjänstebaserade tekniker som krypterar kundinnehåll i vila och överföring, inklusive BitLocker, kryptering per fil, TLS (Transport Layer Security) och IPsec (Internet Protocol Security). Specifik information om kryptering i Microsoft 365 finns i [Datakrypteringsteknik i Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)

Tillsammans tillhandahåller de ovan listade skydden robusta logiska avgränsningskontroller som tillhandahåller skydd mot hot och åtgärder som motsvarar det som tillhandahålls av fysisk avgränsning.

## <a name="related-links"></a>Relaterade länkar

- [Isolering och åtkomstkontroll i Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Klientisolering i Office Graph och Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Innehavarisolering i Microsoft 365 sökning](microsoft-365-isolation-in-microsoft-365-search.md)
- [Tenant Isolation i Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Resursgränser](/compliance/assurance/assurance-resource-limits)
- [Övervaka och testa klientorganisations begränsningar](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolerings- och åtkomstkontroll i Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)