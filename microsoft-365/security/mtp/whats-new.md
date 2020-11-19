---
title: Nyheter i Microsoft 365 Defender
description: Här listas de nya funktionerna i Microsoft 365 Defender
keywords: Nyheter i Microsoft Threat Protection, ga, allmänt tillgängliga, funktioner, tillgängliga, ny
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: ade93bf8c89077c117ada764478cc74f4a5f14cc
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357325"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Nyheter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).
>

Följande funktioner är allmänt tillgängliga (GA) i den senaste versionen av Microsoft 365 Defender.

RSS-feed: få ett meddelande när den här sidan uppdateras genom att kopiera och klistra in följande webb adress i din feed-läsare:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook)
>

## <a name="september-2020"></a>September 2020
- [IdentityDirectoryEvents tabell](advanced-hunting-identitydirectoryevents-table.md) <br> Hitta händelser som berör en lokal domänkontrollant som kör Active Directory (AD). Den här [avancerade](advanced-hunting-overview.md) schema tabellen för ökningar täcker ett antal identitets relaterade händelser och system händelser på domänkontrollanten.
- [Funktionen AssignedIPAddresses ()](advanced-hunting-assignedipaddresses-function.md) <br> Med den här funktionen kan du snabbt skaffa de senaste IP-adresserna till en enhet eller de senaste IP-adresserna från en viss tid.

## <a name="july-2020"></a>Juli 2020
- [Funktionen FileProfile ()](advanced-hunting-fileprofile-function.md) <br> Använd den här funktionen när du vill utöka resultaten med fullständig fil information.
- [Identitets-och program tabeller](advanced-hunting-schema-tables.md)<br> Få insyn i autentiseringsmetoderna, Active Directory-frågor och program relaterade aktiviteter med tabellerna [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)och [AppFileEvents](advanced-hunting-appfileevents-table.md) i det avancerade antivirus programmet.
- [Gå på jakt](advanced-hunting-go-hunt.md)<br> Snabbt pivotera en olycka för att inspektera en viss händelse, en användare, en enhet eller andra typer av enheter i en avancerad jakt.

## <a name="june-2020"></a>Juni 2020
- Twitter-feed <br> Få den senaste säkerhets forskningen, Hot intelligens, produkt nyheter och mer-direkt i instrument panelen.
- [EmailPostDeliveryEvents schema tabell](advanced-hunting-emailpostdeliveryevents-table.md) <br> Ta med information om åtgärder efter leverans av dina e-postmeddelanden i dina frågor om avancerad jakt.
- [Inspektera poster i avancerad jakt](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Kontrol lera snabbt poster i frågeresultatet med den nya informations panelen.

## <a name="may-2020"></a>Maj 2020
- [Anpassade identifieringar](custom-detections-overview.md) <br> Använd de avancerade frågorna för att skapa anpassade identifierings regler som automatiskt övervakas för och svarar på säkerhets händelser och system tillstånd.

## <a name="february-2020"></a>Februari 2020
- [Incidenter](incidents-overview.md) <br> Veta exakt var en attack startas och annan information som hjälper dig att se omfattningen av angreppet.
- [Automatiska undersökningar och svar](mtp-autoir.md) <br> AIR gör det möjligt för din säkerhets policy att markant öka organisationens kapacitet att hantera säkerhets varningar och-händelser.
- [Avancerade jakt förbättringar](advanced-hunting-overview.md) <br> Det står proaktivt för hot via den moderna arbets ytan med Kusto frågespråk och ett säkerhetsoptimerat schema.

## <a name="march-2019"></a>Mars 2019
- Avancerad jakt <br> Landnings sida till olika jakt funktioner som gör att du kan hitta hot som påverkar e-post och data, enheter och identiteter.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Mätning av en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder. Om du följer säkerhets poängen kan du skydda din organisation mot hot. 
- [Rapporter](monitoring-and-reporting.md) <br>  Har en värd för kort som omfattar en mängd olika områden som säkerhets analyser och administratörer kan spåra under deras dagliga drift.
