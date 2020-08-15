---
title: Kontroller för Microsoft 365-isolering
ms.author: josephd
author: JoeDavies-MSFT
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
description: Lär dig hur isolerings kontroller fungerar i Microsoft 365, vilket gör det möjligt för tjänsterna att fungera och att vara autonomt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694653"
---
# <a name="microsoft-365-isolation-controls"></a>Kontroller för Microsoft 365-isolering 

Microsoft arbetar kontinuerligt med att kontrol lera att arkitekturen för flera innehavare av Microsoft 365 stöder säkerhet på företags nivå, sekretess, integritet, lokal, internationell [och tillgänglighet.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Skalan och omfattningen av tjänster som tillhandahålls av Microsoft gör det svårt och icke-ekonomiskt att hantera Microsoft 365 med betydande mänsklig interaktion. Microsoft 365-tjänsterna tillhandahålls via flera globalt distribuerade Data Center, och är mycket automatiserade med få saker som kräver mänsklig touch eller åtkomst till kund innehåll. Vår personal har stöd för dessa tjänster och data Center med automatiserade verktyg och lättillgänglig fjärråtkomst. 

Microsoft 365 består av flera tjänster som tillhandahåller viktiga företags funktioner och bidrar till hela Microsoft 365-upplevelsen. Alla de här tjänsterna är fristående och har utformats för att integreras med varandra.

Microsoft 365 är utformat med följande principer:

 - ** [Tjänsteorienterad arkitektur](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** utforma och utveckla program vara i form av driftskompatibla tjänster som ger väl definierade företags funktioner.
 - **[Drift säkerhet](https://www.microsoft.com/download/details.aspx?id=40872):** en struktur som innehåller de kunskaper som erhålls genom olika funktioner som är unika för Microsoft, inklusive [livs cykeln för Microsofts säkerhets utveckling](https://www.microsoft.com/sdl/default.aspx), [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)och djupgående medvetenhet om det Cybersecurity hotet liggande.

Microsoft 365-tjänster tillsammans med varandra, men är utformade och implementerade så att de kan distribueras och användas som autonoma tjänster, oberoende av varandra. Microsoft är åtskilda tullar och ansvars områden för Microsoft 365 för att minska möjligheterna till otillbörlig eller oavsiktlig modifiering av organisationens till gångar. Microsoft 365-team har definierat roller som en del av en omfattande rollbaserad åtkomst kontroll.

## <a name="customer-content-isolation"></a>Innehålls isolering för kunder

Allt kund innehåll i en klient organisation är isolerat från andra klient organisationer och från operationer och system data som används i hanteringen av Microsoft 365. Flera former av skydd implementeras i Microsoft 365 för att minimera risken för problem med Microsoft 365-tjänsten eller ett program. Flera former av skydd hindrar också obehörig åtkomst till klient organisationen eller Microsoft 365-systemet.

Information om hur Microsoft implementerar logisk isolering av klient organisations data i Microsoft 365 finns i avsnittet [klient isolering i Microsoft 365](microsoft-365-tenant-isolation-overview.md).
