---
title: Förstå begrepp inom hotinformation i Microsoft Defender för Endpoint
description: Skapa anpassade aviseringar om hot för din organisation och lär dig mer om begreppen kring hotinformation i Microsoft Defender för Slutpunkt
keywords: hotinformation, aviseringsdefinitioner, indikatorer på kompromett, ioc
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074121"
---
# <a name="understand-threat-intelligence-concepts"></a>Förstå begrepp inom hotinformation

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Avancerade cybersäkerhetsattacker består av flera komplexa skadliga händelser, attribut och sammanhangsberoende information. Att identifiera och avgöra vilka av dessa aktiviteter som är misstänkta kan vara en svår uppgift. Din kunskap om kända attribut och onormala aktiviteter som är specifika för branschen är grundläggande i att veta när ett observerat beteende ska anropas som misstänkt.

Med Microsoft Defender för Endpoint kan du skapa anpassade hotvarningar som kan hjälpa dig att hålla reda på möjliga attackaktiviteter i organisationen. Du kan flagga misstänkta händelser för att få ihop ledtrådar och eventuellt stoppa en attackkedja. Dessa anpassade hotaviseringar visas bara i organisationen och flaggar händelser som du ställer in på att spåras.

Innan du skapar anpassade varningar för hot är det viktigt att känna till begreppen bakom aviseringsdefinitioner och indikatorer på komprometteringar (IOCs) och förhållandet mellan dem.

## <a name="alert-definitions"></a>Aviseringsdefinitioner
Aviseringsdefinitioner är sammanhangsberoende attribut som kan användas gemensamt för att identifiera tidiga ledtrådar om en möjlig cybersäkerhetsattack. Dessa indikatorer är vanligtvis en kombination av aktiviteter, egenskaper och åtgärder som vidtas av en attack för att nå syftet med en attack. Att övervaka de här kombinationerna av attribut är viktigt för att nå en bra punkt mot attacker och eventuellt störa kedjan med händelser innan målet för en attackerare har uppnåtts.

## <a name="indicators-of-compromise-ioc"></a>Indikatorer på kompromett (IOC)
IOS är individuellt kända skadliga händelser som indikerar att ett nätverk eller en enhet redan har brutits. Till skillnad från definitioner av aviseringar betraktas dessa indikatorer som bevis för ett brott. De syns ofta efter att en attack redan har utförts och syftet har uppnåtts, till exempel en exfiltrering. Det är också viktigt att hålla reda på IOS under undersökningarna. Även om det kanske inte ger möjlighet att vidta åtgärder med en attackkedja kan insamling av dessa indikatorer vara användbart för att skapa bättre skydd för möjliga framtida attacker.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relation mellan aviseringsdefinitioner och ICS
I kontexten för Microsoft Defender för Endpoint är aviseringsdefinitioner behållare för IOCS och definierar aviseringen, inklusive metadata som höjs med en viss IOC-matchning. Olika metadata tillhandahålls som en del av aviseringsdefinitionerna. Metadata, till exempel namn för aviseringsdefinition för attack, allvarlighetsgrad och beskrivning, tillhandahålls tillsammans med andra alternativ.

Varje IOC definierar logik för betongidentifiering baserat på dess typ och värde samt dess åtgärd, som avgör hur den matchas. Den är bunden till en viss aviseringsdefinition som definierar hur en identifiering visas som en avisering på Microsoft Defender för slutpunktskonsolen.

Här är ett exempel på en IOC:
- Typ: Sha1
- Värde: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Åtgärd: Lika med

IOS har en många-till-ett-relation med aviseringsdefinitioner så att en aviseringsdefinition kan ha många IOCs som motsvarar den.

## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
:---|:---
[Dra identifieringar till dina SIEM-verktyg](configure-siem.md)| Läs mer om olika sätt att dra identifieringar.
[Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt](enable-siem-integration.md)| Läs mer om hur du aktiverar  funktionen SIEM-integrering på sidan Inställningar i portalen så att du kan använda och generera den information som krävs för att konfigurera de SIEM-verktyg som stöds.
[Konfigurera Splunk för att hämta Microsoft Defender för identifiering av slutpunkter](configure-siem.md)| Läs mer om att installera REST API Modular Input App och andra konfigurationsinställningar för att aktivera Splunk för att hämta Microsoft Defender för identifiering av slutpunkter.
[Konfigurera HP ArcSight att hämta Microsoft Defender för identifiering av slutpunkter](configure-arcsight.md)| Läs mer om hur du installerar HP ArcSight REST FlexConnector-paketet och de filer du behöver för att konfigurera ArcSight för att hämta Microsoft Defender för slutpunktsidentifiering.
[Fälten Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) | Förstå vilka datafält som visas som en del av API:t för varningar och hur de mappas till Microsoft Defender Säkerhetscenter.
[Hämta Microsoft Defender för slutpunktsidentifiering med REST API](pull-alerts-using-rest-api.md) | Använd OAuth 2.0-flödets klientautentiseringsuppgifter för att hämta identifieringar från Microsoft Defender för Slutpunkt med REST API.
[Felsöka problem med SIEM-verktygsintegrering](troubleshoot-siem.md) | Åtgärda problem som kan uppstå när du använder integrationsfunktionen SIEM.



## <a name="related-topics"></a>Relaterade ämnen
- [Hantera indikatorer](manage-indicators.md)
