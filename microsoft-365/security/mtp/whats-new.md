---
title: Nyheter i Microsoft 365 Defender
description: En lista över de nya funktionerna i Microsoft 365 Defender
keywords: vad är nytt i microsoft threat protection, ga, generally available, capabilities, available, new
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 1f5fa231c371ca7a8d6a22ca0b4ff388fd89004c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711922"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Nyheter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)
>

Följande funktioner är allmänt tillgängliga (GA) i den senaste versionen av Microsoft 365 Defender.

RSS-feed: Få ett meddelande när den här sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a>Mars 2021
- [CloudAppEvents-tabell](advanced-hunting-cloudappevents-table.md) <br>Hitta information om händelser i olika molnappar och tjänster som omfattas av Microsoft Cloud App Security. Den här tabellen innehåller också information som tidigare varit tillgänglig `AppFileEvents` i.
## <a name="february-2021"></a>Februari 2021
- (Förhandsversion) Det förbättrade [säkerhetscentret i Microsoft https://security.microsoft.com) 365 (är](https://security.microsoft.com) nu tillgängligt i offentlig förhandsversion. Den här nya upplevelsen tar Defender för Endpoint och Defender för Office 365 till mitten. [Läs mer om vad som har ändrats.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)

## <a name="september-2020"></a>September 2020
- [IdentityDirectoryEvents-tabell](advanced-hunting-identitydirectoryevents-table.md) <br> Hitta händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den [här avancerade](advanced-hunting-overview.md) tabellen för sökning omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten.
- [Funktionen AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Använd den här funktionen i dina avancerade sökningsfrågor för att snabbt hämta de senaste IP-adresserna som tilldelats en enhet eller de senaste IP-adresserna från en viss tid.

## <a name="july-2020"></a>Juli 2020
- [Funktionen FileProfile()](advanced-hunting-fileprofile-function.md) <br> Använd den här funktionen i dina avancerade sökfrågor för att utöka resultaten med omfattande filinformation.
- [Identitets- och apptabeller](advanced-hunting-schema-tables.md)<br> Få insyn i autentiseringshändelser, Active Directory-frågor och apprelaterad aktivitet med tabellerna [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)och [AppFileEvents](advanced-hunting-appfileevents-table.md) i det avancerade sökschemat.
- [Gå på jakt](advanced-hunting-go-hunt.md)<br> Du kan snabbt gå från att undersöka en händelse till att inspektera en viss händelse, en användare, en enhet eller andra enheter på avancerad sökning.

## <a name="june-2020"></a>Juni 2020
- Twitter-feed <br> Få den senaste säkerhetsundersökningen, hotinformation, produktnyheter med mera – direkt i instrumentpanelen.
- [Schematabellen EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Införliva information om åtgärder efter leverans som har förts på e-postmeddelanden i dina avancerade sökningsfrågor.
- [Inspektera poster i avancerad sökning](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Granska snabbt poster i frågeresultatet med den nya informationspanelen.

## <a name="may-2020"></a>Maj 2020
- [Anpassade identifieringar](custom-detections-overview.md) <br> Använd avancerade sökfrågor för att skapa anpassade identifieringsregler som automatiskt övervakar för och svarar på säkerhetshändelser och systemhändelser.

## <a name="february-2020"></a>Februari 2020
- [Incidenter](incidents-overview.md) <br> Vet exakt var en attack startades och annan information som hjälper dig att se hur omfattande attacken är.
- [Automatiska undersökningar och svar](mtp-autoir.md) <br> AIR gör att ditt säkerhetsteam avsevärt ökar organisationens kapacitet för att hantera säkerhetsvarningar och säkerhetstillbud.
- [Avancerade förbättringar av sökning](advanced-hunting-overview.md) <br> Proaktivt leta efter hot på den moderna arbetsytan med Kusto Query Language och ett säkerhetsoptimerat schema.

## <a name="march-2019"></a>Mars 2019
- Avancerad jakt <br> Startsidan för olika sökfunktioner där du proaktivt kan hitta hot som påverkar e-post, data, enheter och identiteter.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Mått på en organisations säkerhetssäkerhet, med ett högre tal som anger åtgärder för ytterligare förbättringar. Om du följer rekommendationerna för säkerhetsresultat kan du skydda organisationen från hot. 
- [Rapporter](monitoring-and-reporting.md) <br>  Har en mängd kort som täcker en mängd olika områden som säkerhetsanalytiker och administratörer spårar som en del av sin dagliga verksamhet.
