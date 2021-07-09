---
title: Nyheter i Microsoft 365 Defender
description: Visar de nya funktionerna i Microsoft 365 Defender
keywords: vad är nytt i Microsoft 365 Defender, ga, allmänt tillgänglig, funktioner, tillgänglig, ny
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: af5efb669b1f73b4008ac2c3fae251a4d08511dd
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340990"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Nyheter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

Följande funktioner är allmänt tillgängliga (GA) i den senaste versionen av Microsoft 365 Defender.

RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="july-2021"></a>Juli 2021
- [Katalog med professionella tjänster](https://sip.security.microsoft.com/interoperability/professional_services)<br>Förbättra plattformens funktioner för identifiering, undersökning och hotinformation med partneranslutningar som stöds.
    

## <a name="may-2021"></a>Maj 2021

- [Ny aviseringssida i Microsoft 365 Defender portalen](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> Ger förbättrad information för kontexten i en attack. Du kan se vilka andra utlösta aviseringar som orsakade den aktuella aviseringen och alla berörda enheter och aktiviteter som var inblandade i attacken, inklusive filer, användare och postlådor. Mer information [finns i](/microsoft-365/security/defender/investigate-alerts) Undersöka aviseringar.
- [Trenddiagram för incidenter och aviseringar på Microsoft 365 Defender portalen](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> Avgör om det finns flera aviseringar om en enstaka incident eller om organisationen är under attack med flera olika incidenter. Mer information [finns](/microsoft-365/security/defender/incident-queue) i Prioritera incidenter.


## <a name="april-2021"></a>April 2021
- Microsoft 365 Defender<br> Den förbättrade [Microsoft 365 Defender](https://security.microsoft.com) är nu tillgänglig. I den här nya upplevelsen samlas Defender för Slutpunkt, Defender för Office 365, Defender för identitet och annat till en enda portal. Det här är det nya hemmet för att hantera dina säkerhetskontroller. [Läs om de senaste](./overview-security-center.md).

- [Microsoft 365 Defender över hotanalyser](threat-analytics.md)<br>
 Hotanalyser hjälper dig att svara på och minimera påverkan på aktiva attacker. Du kan också lära dig mer om attackförsök som blockeras av Microsoft 365 Defender lösningar och vidta förebyggande åtgärder som minimerar risken för ytterligare exponering och ökar motståndskraft. Som en del av den enhetliga säkerhetsupplevelsen finns nu hotanalyser tillgängliga för Microsoft Defender för Endpoint och Microsoft Defender för Office E5-licensinnehavare.

## <a name="march-2021"></a>Mars 2021
- [Tabellen CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Hitta information om händelser i olika molnappar och tjänster som täcks av Microsoft Cloud App Security. Den här tabellen innehåller också information som tidigare var tillgänglig i `AppFileEvents` .
## <a name="february-2021"></a>Februari 2021
- (Förhandsversion) Det förbättrade [Microsoft 365 säkerhetscentret https://security.microsoft.com) (](https://security.microsoft.com) är nu tillgängligt i offentlig förhandsversion. Den här nya upplevelsen tar Defender för Endpoint och Defender Office 365 till mitten. [Läs mer om vad som ändrats](./overview-security-center.md).

## <a name="september-2020"></a>September 2020
- [Tabellen IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Hitta händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD). Den [här tabellen för](advanced-hunting-overview.md) avancerad sökning omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten.
- [Funktionen AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Använd den här funktionen i avancerade frågor för sökning för att snabbt hämta de senaste IP-adresserna som tilldelats en enhet eller de senaste IP-adresserna från en viss tid.

## <a name="july-2020"></a>Juli 2020
- [Funktionen FileProfile()](advanced-hunting-fileprofile-function.md) <br> Använd den här funktionen i avancerade sökfrågor för att utöka resultaten med omfattande filinformation.
- [Identitets- och apptabeller](advanced-hunting-schema-tables.md)<br> Få insyn i autentiseringshändelser, Active Directory-frågor och apprelaterad aktivitet med tabellerna [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)och [AppFileEvents](advanced-hunting-appfileevents-table.md) i det avancerade schemat för sökningar.
- [Gå på jakt](advanced-hunting-go-hunt.md)<br> Du kan snabbt gå från att undersöka en händelse till att kontrollera en viss händelse, en användare, en enhet eller andra enheter som använder avancerad sökning.

## <a name="june-2020"></a>Juni 2020
- Twitter-feed <br> Få den senaste säkerhetsundersökningen, hotinformation, produktnyheter med mera – direkt på instrumentpanelen.
- [Schematabellen EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Införliva information om åtgärder efter leverans som har vidtagits för e-postmeddelanden i dina avancerade sökfrågor.
- [Kontrollera poster under avancerad sökning](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Granska snabbt poster i dina frågeresultat med den nya informationspanelen.

## <a name="may-2020"></a>Maj 2020
- [Anpassade identifieringar](custom-detections-overview.md) <br> Använd avancerade frågor för sökning om du vill skapa anpassade identifieringsregler som automatiskt övervakar och svarar på säkerhetshändelser och systemhändelser.

## <a name="february-2020"></a>Februari 2020
- [Incidenter](incidents-overview.md) <br> Vet exakt var en attack startades och annan information som hjälper dig att se hur omfattande attacken är.
- [Automatiska undersökningar och svar](m365d-autoir.md) <br> AIR gör att ditt säkerhetsteam avsevärt ökar organisationens kapacitet för att hantera säkerhetsvarningar och incidenter.
- [Avancerade förbättringar av sök efter](advanced-hunting-overview.md) <br> Proaktivt leta efter hot på den moderna arbetsytan med Kusto Query Language och ett säkerhetsoptimerat schema.

## <a name="march-2019"></a>Mars 2019
- Avancerad jakt <br> Startsidan för olika sökfunktioner som gör att du proaktivt kan hitta hot som påverkar e-post, data, enheter och identiteter.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas. Om du följer rekommendationerna för säkerhetsresultatet kan du skydda organisationen från hot. 
- [Rapporter](overview-security-center.md) <br>  Har en mängd kort som täcker en mängd olika områden som säkerhetsanalytiker och administratörer spårade som en del av de dagliga åtgärderna.
