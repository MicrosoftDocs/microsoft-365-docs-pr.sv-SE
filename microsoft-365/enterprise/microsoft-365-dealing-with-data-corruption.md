---
title: Microsoft 365 att hantera skadade data
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
ms.custom: seo-marvel-apr2020
description: I den här artikeln förklaras datafel i Microsoft 365 och ansträngningar från Microsoft för att förhindra och återställa data.
ms.openlocfilehash: 767be71bb08c49070488cc965165ac86e98836bd
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331878"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a>Hantera datafel i Microsoft 365

En av de utmanande aspekterna att köra en storskalig moln tjänst är att hantera datafel, med den stora volymen av data och oberoende system. Datafel kan orsakas av:

- Program eller infrastruktur program fel, skada vissa eller hela programmets tillstånd
- Problem med maskin vara som ger förlust av data eller omöjligt att läsa data
- Funktions fel för människa
- Illasinnade hackare och Disgruntled anställda
- Incidenter i externa tjänster som medför förlust av data

Eftersom större återhämtning i data integritet innebär färre incidenter för datafel är det möjligt att Microsoft 365 har funktioner för att förhindra korruption från att fungera, samt system och processer som gör att vi kan återställa data om det gör det. Det finns kontroller och processer i de olika stegen i tekniska släpp processen för att öka återhämtning mot skadade data, inklusive:

- System design
- Kod organisation och struktur
- Kod granskning
- Enhets test, integrerings test och systemtest
- Test/portar för rese kablar

I Microsoft 365-produktions miljöer säkerställer peer-replikering mellan data Center att det alltid finns flera aktiva kopior av alla data. Standard bilder och skript används för att återställa förlorade servrar och replikerade data används för att återställa kunddata. På grund av de inbyggda funktionerna för återhämtning och bearbetning av data är det bara att hantera säkerhets kopior av Microsoft 365 information om informations systemet (inklusive säkerhetsrelaterad dokumentation), med inbyggd replikering i SharePoint Online och med det interna kod databas verktyget, Source depå. Dokumentationen till systemet lagras i SharePoint Online och innehåller alla system-och program bilder. Både SharePoint Online och Source depå använder versions hantering och replikeras i nära real tid.
