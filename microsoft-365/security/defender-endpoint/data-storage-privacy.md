---
title: Datalagring och sekretess i Microsoft Defender för Endpoint
description: Läs mer om hur Microsoft Defender för Endpoint hanterar sekretess och data som samlas in.
keywords: Microsoft Defender för slutpunkt, Microsoft Defender för slutpunkt, datalagring och sekretess, lagring, sekretess, licensiering, geolokalisering, datalagring, data
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
ms.openlocfilehash: 2b191c4a24ce170d23fc3d9e43293cc7bbe59e80
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892824"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Datalagring och sekretess i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Det här avsnittet tar upp några av de vanligaste frågorna om sekretess och datahantering för Defender för Slutpunkt.
> [!NOTE]
> I det här dokumentet förklaras datalagrings- och sekretessinformationen för Defender för Endpoint. Mer information om Defender för Endpoint och andra produkter och tjänster som Microsoft Defender Antivirus och Windows 10 finns i [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?linkid=827576) Mer information finns även i Vanliga frågor och svar om sekretess i [Windows 10.](https://go.microsoft.com/fwlink/?linkid=827577)


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Vilka data samlas in av Microsoft Defender för Endpoint?

Microsoft Defender för Endpoint samlar in och lagrar information från dina konfigurerade enheter i en kund dedikerad och avskild klientorganisation som är specifik för tjänsten för administrations-, spårnings- och rapporteringssyften. 

Information som samlas in omfattar fildata (t.ex. filnamn, storlekar och hash-adresser), processdata (processer som körs, hash-rutiner), registerdata, nätverksanslutningsdata (värd-IP och portar) och enhetsinformation (t.ex. enhetsidentifierare, namn och operativsystemsversionen).

Microsoft lagrar dessa data säkert i Microsoft Azure och upprätthåller dem i enlighet med Microsofts sekretessrutiner och [Microsofts säkerhetscenterpolicyer.](https://go.microsoft.com/fwlink/?linkid=827578)

Med hjälp av dessa data kan Defender för Endpoint:
- Identifiera proaktiva indikatorer på angrepp (IOA) i organisationen
- Generera varningar om en möjlig attack har upptäckts
- Tillhandahåll dina säkerhetsåtgärder med en vy på enheter, filer och URL:er som är relaterade till hotsignaler från ditt nätverk, så att du kan undersöka och utforska förekomsten av säkerhetshot på nätverket.

Microsoft använder inte dina data för reklam.

## <a name="data-protection-and-encryption"></a>Dataskydd och kryptering
Defender för Endpoint-tjänsten utnyttjar de senaste teknikerna för dataskydd som är baserade på Microsoft Azure-infrastrukturen. 

Det finns olika aspekter av relevant informationsskydd som tjänsten tar hand om. Kryptering är en av de viktigaste och den innehåller datakryptering i vila, kryptering under flygning och nyckelhantering med nyckelvalv. Mer information om andra tekniker som används av Defender för slutpunktstjänsten finns i Översikt över [Azure-kryptering.](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) 

I alla scenarier krypteras data med minst 256-bitars [AES-kryptering.](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)


## <a name="data-storage-location"></a>Datalagringsplats

Defender för Endpoint fungerar i Microsoft Azure-datacenter i EU, Storbritannien eller USA. Kunddata som samlas in av tjänsten kan lagras i: (a) klientorganisationens geoplats som identifieras under etableringen eller(b) om Defender för Endpoint använder en annan Microsoft-onlinetjänst för att bearbeta sådana data, den geolokalisering som definieras av datalagringsreglerna för den andra onlinetjänsten.

Kunddata i anonymiserad form kan också lagras i de centrala lagrings- och bearbetningssystemen i USA.

När den har konfigurerats kan du inte ändra platsen där dina data lagras. Det här är ett bekvämt sätt att minimera efterlevnadsrisken genom att aktivt välja de geografiska platser där dina data ska lagras. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>Isoleras mina data från andra kunddata?
Ja, dina data isoleras genom åtkomstautentisering och logisk separering baserat på kundidentifierare. Varje kund kan bara komma åt data som samlas in från sin egen organisation och allmänna data som Microsoft tillhandahåller.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Hur förhindrar Microsoft skadliga Insider-aktiviteter och missbruk av roller med hög behörighet?

Microsofts utvecklare och administratörer har som design fått tillräcklig behörighet för att utföra sina tilldelade uppgifter för att driva och utveckla tjänsten. Microsoft distribuerar kombinationer av förebyggande, intrång och reaktiva kontroller, inklusive följande mekanismer för att skydda mot obehörig utvecklare och/eller administrativ aktivitet:

- Begränsad åtkomstkontroll till känsliga data
- Kombinationer av kontroller som förbättrar oberoende identifiering av skadlig aktivitet
- Flera nivåer av övervakning, loggning och rapportering

Microsoft utför dessutom bakgrundsverifieringskontroller av viss personal och begränsar åtkomsten till program, system och nätverksinfrastruktur i proportion till nivån för bakgrundsverifiering. Verksamhetspersonalen följer en formell process när de krävs för att få åtkomst till en kunds konto eller relaterad information när de utför sina uppgifter.

Åtkomst till data för tjänster som distribueras i Microsoft Azure Government datacenter tilldelas endast till driftspersonal som har skärmats och godkänts för att hantera data som omfattas av vissa myndighetsföreskrifter och krav, till exempel FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 och CJIS.


## <a name="is-data-shared-with-other-customers"></a>Delas data med andra kunder?
Nej. Kunddata isoleras från andra kunder och delas inte. Men insikter om data från Microsofts bearbetning, och som inte innehåller några kundspecifika data, kan delas med andra kunder. Varje kund kan bara komma åt data som samlas in från sin egen organisation och allmänna data som Microsoft tillhandahåller.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Hur länge kommer Microsoft att lagra mina data? Vad är Microsofts policy för datalagring?
**Vid service onboarding**<br>
Du kan välja datalagringsprincip för dina data. Det här anger hur länge Window Defender för slutpunkt lagrar dina data. Du kan välja mellan en månad och sex månader så att du kan uppfylla företagets efterlevnadsbehov av regelverk.

**När avtalet avslutas eller avslutas**<br>
Dina data sparas och blir tillgängliga för dig under respitperioden eller inställt läge för licensen. I slutet av perioden raderas dessa data från Microsofts system för att de inte ska återskapas, senast 180 dagar efter att avtalet avslutats eller avslutats.

**Advanced Hunting data**<br>
Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Kan Microsoft hjälpa oss att upprätthålla regelefterlevnad?

Microsoft ger kunder detaljerad information om Microsofts säkerhets- och efterlevnadsprogram, inklusive granskningsrapporter och efterlevnadspaket, för att hjälpa kunder att utvärdera Defender för Endpoint-tjänster mot sina egna juridiska och reglerande krav. Defender för Endpoint har uppnått ett antal certifieringar inklusive ISO, SOC, FedRAMP High och DEFENDER och fortsätter att uppnå ytterligare nationella, regionala och branschspecifika certifieringar.

Genom att tillhandahålla kunder kompatibla, oberoende verifierade tjänster gör Microsoft det enklare för kunderna att uppfylla efterlevnad för den infrastruktur och de program de kör.

Mer information om Defender för slutpunktscertifieringsrapporter finns i [Microsoft Säkerhetscenter.](https://servicetrust.microsoft.com/) 

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
