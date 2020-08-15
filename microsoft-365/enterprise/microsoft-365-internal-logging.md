---
title: Microsoft 365 intern loggning för Microsoft 365-teknik
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
description: I den här artikeln finns en förklaring av hur intern loggning för Microsoft 365 Engineering Teams fungerar.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696723"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Intern loggning för Microsoft 365-teknik

Utöver de händelser och loggdata som är tillgängliga för kunder finns det också ett internt system för data insamling som är tillgängligt för Microsoft 365-tekniker på Microsoft. Många olika typer av loggdata laddas upp från Microsoft 365-servrar till en intern, stor data dator tjänst som heter Cosmos. Varje tjänst team uppladdar gransknings loggar från sina respektive servrar till Cosmos-databasen för agg regering och analys. Denna data överföring sker via en FIPS 140-2-godkänd TLS-anslutning på specifika godkända portar och protokoll med ett eget Automation-verktyg som heter Office data Loader (ODL). De verktyg som används i Microsoft 365 för att samla in och bearbeta gransknings poster tillåter inte permanenta eller irreversibla ändringar av den ursprungliga gransknings postens innehåll eller tidsordning.

Service Teams använder Cosmos som en central lagrings plats för att utföra en analys av program användning, för att mäta system och operativa prestanda och för att söka efter avvikelser och mönster som kan tyda på problem eller säkerhets problem. Varje tjänst team laddar upp en original plan för loggar till Cosmos, beroende på vad de använder för att analysera, som ofta inkluderar:

- Händelse loggar
- AppLocker-loggar
- Prestanda data
- System Center-data
- Samtals detalj poster
- Kvaliteten på upplevelse data
- Webb server loggar för IIS
- SQL Server-loggar
- Syslog-data
- Säkerhets gransknings loggar

Innan du laddar upp data i Cosmos använder ODL-programmet en rensnings tjänst för att obfuscate alla fält som innehåller kunddata, till exempel information om klient organisationen och informationen om identifierbara uppgifter, och ersätta dessa fält med ett hashvärde. Anonymiserad och mellanliggande loggar skrivs om och överförs sedan till Cosmos. Service Teams kör begränsade frågor mot deras data i Cosmos för korrelation, avisering och rapportering. Perioden för gransknings logg data för bevarande i Cosmos bestäms av service Teams, de flesta gransknings loggdata bevaras i 90 dagar eller längre för att hantera säkerhets tillbuds undersökningar och för att uppfylla gällande bestämmelser om bevarande.

Åtkomst till Microsoft 365-data som lagras i Cosmos begränsas till behörig personal. Microsoft begränsar hanteringen av gransknings funktionerna till den begränsade del av tjänst team medlemmar som är ansvariga för gransknings funktionerna. Dessa team medlemmar har inte möjlighet att ändra eller ta bort data från Cosmos och alla ändringar i loggnings mekanismer för Cosmos registreras och granskas.

Varje tjänst team får åtkomst till sina loggdata för analys genom att auktorisera vissa program för att genomföra en viss analys. Säkerhets teamet för Microsoft 365 använder till exempel data från Cosmos via en tillverkarspecifik händelse logg tolkare för att korrelera, Avisera och generera åtgärds bara rapporter om möjlig misstänkt aktivitet i Microsoft 365-produktions miljön. Rapporterna från dessa data används för att åtgärda säkerhets problem och för att förbättra tjänstens allmänna prestanda. Om en viss varning eller rapport kräver ytterligare undersökning kan tjänst personalen begära att data importeras tillbaka till Microsoft 365-tjänsten. Eftersom den specifika loggen som importeras från Cosmos är i krypterad och tjänste personal inte har åtkomst till dekrypteringsnyckeln, skickas mål loggen till program mässigt via en dekrypteringsnyckel som returnerar omfattnings resultat till den behöriga tjänsten. Eventuella säkerhets problem som upptäcks i den här övningen rapporteras och eskaleras med Microsofts standard funktioner för säkerhets tillbuds hantering.
