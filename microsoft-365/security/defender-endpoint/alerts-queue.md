---
title: Visa och ordna kön Microsoft Defender för slutpunktsaviseringar
description: Lär dig hur köer av Microsoft Defender för slutpunktsaviseringar fungerar och hur du sorterar och filtrerar listor med aviseringar.
keywords: aviseringar, köer, aviseringar, sortera, ordna, filtrera, hantera aviseringar, nya, pågående, lösta, nyaste, tid i kö, allvarlighetsgrad, tidsperiod, microsoft threat experts varningar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934339"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Visa och ordna kön Microsoft Defender för slutpunktsaviseringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

I **kön Aviseringar** visas en lista med aviseringar som har flaggats från enheter i nätverket. Som standard visar kön aviseringar som setts de senaste 30 dagarna i en grupperad vy. De senaste aviseringarna visas högst upp i listan, vilket hjälper dig att se de senaste aviseringarna först.

> [!NOTE]
> Alerts queue is significantly reduced with automated investigation and remediation, allowing security operations experts to focus on more sophisticated threats and other high value initiatives. När en avisering innehåller en enhet som stöds för automatiserad undersökning (t.ex. en fil) på en enhet som har ett operativsystem som stöds kan en automatiserad undersökning och åtgärd starta. Mer information om automatiserade undersökningar finns i [Översikt över automatiserade undersökningar.](automated-investigations.md)

Du kan välja mellan flera alternativ för att anpassa vyn aviseringsköer. 

I det övre navigeringsfältet kan du:

- Välj grupperad vy eller listvy
- Anpassa kolumner för att lägga till eller ta bort kolumner 
- Markera de objekt som ska visas per sida
- Navigera mellan sidor
- Använda filter

![Bild på aviseringskö](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>Sortera, filtrera och gruppera aviseringskön

Du kan använda följande filter för att begränsa listan med aviseringar och få en mer fokuserad vy av aviseringarna.

### <a name="severity"></a>Allvarlighetsgrad

Aviserings allvarlighetsgrad | Beskrivning
:---|:---
Högsta </br>(Röd) | Varningar som ofta ses associerade med avancerade beständiga hot (APT). Dessa varningar indikerar en hög risk på grund av hur allvarlig skada de kan orsaka på enheter. Några exempel är: aktiviteter för autentiseringsstöld, aktiviteter för utpressningstrojaner som inte associeras med någon grupp, ändring av säkerhetssensorer eller skadliga aktiviteter som utser människor.
Medel </br>(Orange) | Varningar från identifiering och åtgärd på slutpunkt efter intrång som kan vara en del av ett avancerat beständigt hot (APT). Detta omfattar observerade beteenden som är typiska för attackfaser, avvikande registerändring, körning av misstänkta filer och så vidare. Även om vissa kan vara en del av intern säkerhetstestning kräver det undersökning eftersom det också kan vara en del av en avancerad attack.
Låg </br>(Gul) | Varningar om hot som är associerade med vanligt skadlig programvara. Till exempel hacka-verktyg, icke-skadlig hacka verktyg, som att köra utforskningskommandon, rensa loggar, som ofta inte anger ett avancerat hot som riktar sig till organisationen. Det kan också komma från en isolerad säkerhetsverktygstestning av en användare i organisationen.
Informativ </br>(Grå) | Varningar som inte kan anses vara skadliga för nätverket, men som kan öka organisationens säkerhetskännedom om potentiella säkerhetsproblem.

#### <a name="understanding-alert-severity"></a>Förstå allvarlighetsgrad för aviseringar

Microsoft Defender Antivirus (Microsoft Defender AV) och Defender för slutpunktsvarningens allvarlighetsgrad är olika eftersom de representerar olika omfattningar.

Allvarlighetsgraden för AV-hot i Microsoft Defender motsvarar den absoluta allvarlighetsgraden för det identifierade hotet (skadlig kod), och tilldelas utifrån den potentiella risken för den enskilda enheten, om smittad.

Defender för slutpunktsvarningens allvarlighetsgrad representerar allvarlighetsgraden för det identifierade beteendet, den faktiska risken för enheten men viktigare den potentiella risken för organisationen.

Så till exempel:

- Allvarlighetsgraden för en Defender för Slutpunkt-varning om att en Microsoft Defender AV upptäckte hot som fullständigt förhindrades och inte smittade enheten kategoriseras som "informationsal" eftersom det inte fanns några faktiska skador.
- En avisering om kommersiell skadlig programvara identifierades när den körs, men blockeras och åtgärdas av Microsoft Defender AV, kategoriseras som "Låg" eftersom den kan ha orsakat en del skada på den enskilda enheten men inte utgör något hot för organisationen.
- En varning om skadlig programvara som upptäckts när program körs och som kan utgöra ett hot för inte bara den enskilda enheten utan för organisationen, oavsett om den blockerades så småningom, kan rangordnas som "Medel" eller "Hög".
- Misstänkta beteendevarningar, som inte blockerades eller åtgärdats, rangordnas "Låg", "Medium" eller "Hög" efter samma överväganden för organisationens hot.

#### <a name="understanding-alert-categories"></a>Förstå aviseringskategorier

Vi har omdefinierat [aviseringskategorierna](https://attack.mitre.org/tactics/enterprise/) för att passa företagets attacktaktik i [MITRE ATT&CK-matrisen](https://attack.mitre.org/). Nya kategorinamn gäller för alla nya aviseringar. Befintliga aviseringar behåller de tidigare kategorinamnen.

I tabellen nedan visas aktuella kategorier och hur de i allmänhet mappar till tidigare kategorier. 

| Ny kategori       | API-kategorinamn   | Identifierade hotaktivitet eller -komponent                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Samling           | Samling          | Hitta och samla in data för exfiltrering                                                                                         |
| Kommando och kontroll  | CommandAndControl   | Ansluta till den attackerade nätverksinfrastrukturen för att vidarebefordra data eller ta emot kommandon                                          |
| Åtkomst till autentiseringsuppgifter    | CredentialAccess    | Skaffa giltiga autentiseringsuppgifter för att utöka kontrollen över enheter och andra resurser i nätverket                                       |
| Försvar      | DefenseEvasion      | Undviker säkerhetskontroller genom att till exempel inaktivera säkerhetsappar, ta bort program och köra rotverktyg                        |
| Upptäckt            | Upptäckt           | Samla in information om viktiga enheter och resurser, till exempel administratörsdatorer, domänkontrollanter och filservrar  |
| Körning            | Körning           | Starta attackersverktyg och skadlig kod, inklusive RATs och backdoors                                                             |
| Exfiltration         | Exfiltration        | Extrahera data från nätverket till en extern, attackkontrollerad plats                                                         |
| Sårbarhet              | Sårbarhet             | Utnyttja kod och möjlig användningsaktivitet                                                                                       |
| Inledande åtkomst       | InitialAccess       | Få första posten i målnätverket, vanligtvis med lösenordsr gissning, sårbarheter eller nätfiskemeddelanden                      |
| Rörelsen i Movement     | Så här ser det ut:     | Flytta mellan enheter i målnätverket för att nå viktiga resurser eller få nätverksbeständighet                                |
| Skadlig programvara              | Skadlig programvara             | Bakåtdotörer, trojaner och andra typer av skadlig kod                                                                                 |
| Beständighet          | Beständighet         | Skapa asep:er (Autostart extensibility points) för att förbli aktiva och överleva systemstarter                                        |
| Eskalering av behörigheter | PrivilegeEscalation | Skaffa högre behörighetsnivåer för kod genom att köra den i samband med en behörighetsprocess eller ett konto                         |
| Utpressningstrojaner           | Utpressningstrojaner          | Skadlig programvara som krypterar filer och upptar betalning för att återställa åtkomsten                                                                     |
| Misstänkt aktivitet  | SuspiciousActivity  | Atypisk aktivitet som kan vara skadlig aktivitet eller en del av en attack                                                                 |
| Oönskad programvara    | UnwantedSoftware    | Ryktesbaserade appar och appar som påverkar produktiviteten och användarens upplevelse. identifierade som potentiellt oönskade program (PUAs) |

### <a name="status"></a>Status

Du kan välja att begränsa listan med aviseringar baserat på deras status.

### <a name="investigation-state"></a>Undersökningstillstånd

Motsvarar läget för automatiserad undersökning.

### <a name="category"></a>Kategori

Du kan välja att filtrera kön för att visa vissa typer av skadlig aktivitet.

### <a name="assigned-to"></a>Tilldelad till

Du kan välja mellan att visa aviseringar som tilldelats dig eller automatisering.

### <a name="detection-source"></a>Identifieringskälla

Välj den källa som utlöste aviseringen. Microsoft Hotexperter deltagare i förhandsversionen kan nu filtrera och se identifieringar från den nya expert hanterade säkerhetstjänsten för hot.

>[!NOTE]
>Antivirusfiltret visas bara om enheterna använder Microsoft Defender Antivirus som skydd mot skadlig programvara i realtid.

| Identifieringskälla                  | API-värde                  |
|-----------------------------------|----------------------------|
| Tredjepartssensorer                 | ThirdParty Sensors          |
| Antivirus                         | WindowsDefenderAv          |
| Automatiserad undersökning           | AutomatedInvestigation     |
| Anpassad identifiering                  | AnpassadDetection            |
| Anpassat TI                         | CustomerTI                 |
| Identifiering och åtgärd på slutpunkt                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender för Office 365 | OfficeATP                  |
| Microsoft Hotexperter          | ThreatExperts              |
| SmartScreen                       | WindowsDefender SmartScreen |

### <a name="os-platform"></a>OS-plattform

Begränsa vyn för aviseringar i kön genom att välja den OS-plattform som du vill undersöka.

### <a name="device-group"></a>Enhetsgrupp

Om du har specifika enhetsgrupper som du är intresserad av att kontrollera kan du välja grupperna för att begränsa vyn aviseringsköer. 

### <a name="associated-threat"></a>Associerade hot

Använd det här filtret för att fokusera på aviseringar som är relaterade till hot med hög profil. Du kan se en fullständig lista över högkvalitativa hot i [Hotanalys.](threat-analytics.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-files.md)
- [Undersöka enheter i listan Microsoft Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-domain.md)
- [Undersöka ett användarkonto i Microsoft Defender för Endpoint](investigate-user.md)
