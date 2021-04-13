---
title: Översikt över enhetsidentifiering
description: Lär dig hur du använder slutpunktsidentifiering i Microsoft 365 Defender för att hitta ohanterade enheter i nätverket
keywords: identifiering av enheter, upptäck, passiv, proaktiv, nätverk, synlighet, server, arbetsstation, onboard, ohanterade enheter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 2e58b6048f9d815d759cd78ceb3316eb2ed6f66d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698483"
---
# <a name="device-discovery-overview"></a>Översikt över enhetsidentifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

För att du ska kunna skydda din miljö måste du göra en inventering av de enheter som finns i nätverket. Det kan dock vara dyr, utmanande och tidskrävande att mappa enheter i ett nätverk. 

Microsoft Defender för slutpunkt ger en funktion för enhetsidentifiering som hjälper dig att hitta ohanterade enheter som är anslutna till företagsnätverket utan att behöva extra utrustning eller krångliga processändringar.


Med funktionen för enhetsidentifiering kan du:

- **Upptäck slutpunkter för företag som är anslutna till företagets nätverk** <br>
Med hjälp av grundläggande identifieringsalternativ eller standardidentifieringsalternativ kan du hitta arbetsstationer, servrar och mobila slutpunkter som ännu inte har introducerats till Microsoft Defender för Slutpunkt.  

- **Onboard discovered endpoints**<br>
Ohanterade slutpunkter i nätverket innebär svagheter och risker för nätverket. Att registrera dem i tjänsten kan öka säkerheten för dem. 

Tillsammans med den här funktionen kommer en ny säkerhetsrekommendationer om att registrera enheter i Microsoft Defender för Endpoint att finnas tillgänglig som en del av den befintliga upplevelsen av hantering av hot och sårbarhet.



## <a name="discovery-methods"></a>Identifieringsmetoder
Det finns två identifieringslägen: 

-   Grundläggande identifiering 
-   Standardidentifiering (rekommenderas) 


> [!IMPORTANT]
> Identifieringen är inställd på standardläge. Du kan välja att behålla den här konfigurationen via inställningssidan. Standardidentifieringen kommer att vara standardläget för alla förhandsversionskunder som startar den 10 maj 2021 , om de inte ändrats via inställningssidan före detta datum.

### <a name="basic-discovery"></a>Grundläggande identifiering 

I det här läget samlar slutpunkter in händelser in passivt i nätverket och extraherar enhetsinformation från dem. Grundläggande identifiering använder den SenseNDR.exe för insamling av passiva nätverksdata och ingen nätverkstrafik kommer att initieras. Slutpunkter extraherar helt enkelt data från varje nätverkstrafik som visas för en onboarded-enhet. 

### <a name="standard-discovery"></a>Standardidentifiering 

Med det här läget kan slutpunkter aktivt registrera observerade enheter i nätverket för att utveckla insamlade data – vilket hjälper dig att skapa en tillförlitlig och sammanhängande enhetsinventering. I standardläget används smart och aktiv sannolikhet för att upptäcka ännu mer information om observerade enheter för att utöka befintlig enhetsinformation.  

När standardläget är aktiverat kan minimal och inaktiverad nätverksaktivitet som genereras av identifieringssensoren observeras av organisationens nätverksövervakningsverktyg.  

 Om du väljer att inte aktivera det här läget får du bara begränsad insyn i ohanterade slutpunkter i nätverket.

Standardidentifiering använder olika PowerShell-skript för att aktivt söka enheter i nätverket. Dessa PowerShell-skript är Microsoft signerade och körs från följande plats: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` . Till exempel `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.

Du kan ändra och anpassa dina identifieringsinställningar för mer information i [Konfigurera enhetsidentifiering.](configure-device-discovery.md)

> [!NOTE]
> Identifieringsmotorn skiljer mellan nätverkshändelser som tas emot i företagsnätverket jämfört med utanför företagsnätverket. Enheter som inte är anslutna till företagets nätverk upptäcks eller listas inte i enhetsinventeringen. 



## <a name="device-inventory"></a>Enhetsinventering 
Enheter som har identifierats men ännu inte har introducerats och skyddats av Microsoft Defender för Slutpunkt visas i Enhetsinventering på fliken Slutpunkter. Du kan nu använda ett nytt filter i enhetsinventeringslistan med namnet Onboarding status som kan ha något av följande värden:

- Introduktion – Slutpunkten introduceras till Microsoft Defender för Endpoint.
- Kan introduceras – Slutpunkten identifierades i nätverket och operativsystemet identifierades som ett som stöds av Microsoft Defender för Endpoint, men det är för närvarande inte introducerat. Vi rekommenderar att du använder dessa enheter.
- Stöds inte – Slutpunkten upptäcktes i nätverket men stöds inte av Microsoft Defender för Slutpunkt.
- Otillräcklig information – Systemet kunde inte fastställa enhetens supportmöjlighet. Genom att aktivera standardidentifiering på fler enheter i nätverket kan de identifierade attributen utökas. 
 

![Bild på instrumentpanel för enhetsinventering](images/2b62255cd3a9dd42f3219e437b956fb9.png)



## <a name="vulnerability-assessment-on-discovered-devices"></a>Sårbarhetsbedömning på identifierade enheter
Säkerhetsproblem och risker på dina enheter samt andra identifierade ohanterade enheter i nätverket är en del av de aktuella TVM-flödena under "Säkerhetsrekommendationer" och representeras på entitetssidor i portalen. Sök efter SSH-relaterade säkerhetsrekommendationer för att hitta svagheter i SSH som är relaterade till ohanterade och hanterade enheter. 

![Bild av instrumentpanelen med säkerhetsrekommendationer](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a>Använda Avancerad sökning på identifierade enheter
Du kan använda Avancerad sökning för att se vilka enheter som finns.
Hitta information om identifierade slutpunkter i tabellen DeviceInfo eller nätverksrelaterad information om dessa enheter i tabellen DeviceNetworkInfo.
  

![Bild på avancerad användning av sökning](images/f48ba1779eddee9872f167453c24e5c9.png)


Enhetsidentifieringen utnyttjar Microsoft Defender för slutpunktsbaserade enheter som en nätverksdatakälla för att attributaktiviteter till enheter som inte är registrerade. Det innebär att om en Microsoft Defender för slutpunktsbaserad enhet kommuniceras med en enhet som inte är onboarded kan aktiviteter på enheter som inte är onboarded-enheter visas på tidslinjen och via tabellen Advanced hunting DeviceNetworkEvents. 



Nya händelser är TCP-anslutningar (Transmission Control Protocol) och kommer att passa till det aktuella DeviceNetworkEvents-schemat. TCP-anslutning till Microsoft Defender för slutpunktsaktiverad enhet från en enhet som inte är Microsoft Defender för slutpunkt aktiverad.  

Följande åtgärdstyper har också lagts till:  

- ConnectionAttempt – Ett försök att upprätta en TCP-anslutning (syn)  
- ConnectionAcknowledged – En bekräftelse på att en TCP-anslutning har accepterats (syn\ack)  

Du kan prova den här exempelfrågan:  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behaviour"></a>Ändrad 10:a
I följande avsnitt visas de ändringar som du ser i Microsoft Defender för Endpoint och/eller Microsoft 365 Säkerhetscenter när den här funktionen är aktiverad. 
 
1.  Enheter som inte är onboarded till Microsoft Defender till Endpoint förväntas visas i enhetsinventeringen, avancerad sökning och API-frågor. Det kan öka storleken på frågeresultatet avsevärt. 
    1. Tabellerna "DeviceInfo" och "DeviceNetworkInfo" i Avancerad sökning kommer nu att innehålla identifierade enheter. Du kan filtrera bort dessa enheter med hjälp av attributet "OnboardingStatus".

    2. Identifierade enheter förväntas visas i resultat för streaming-API-frågor. Du kan filtrera bort dessa enheter genom att `OnboardingStatus` använda filtret i frågan. 

2.  Ohanterade enheter tilldelas till befintliga enhetsgrupper baserat på definierade villkor. 
3.  I sällsynta fall kan Standard-identifiering utlösa aviseringar på nätverksbildskärmar eller säkerhetsverktyg. Lämna gärna feedback om du upplever sådana händelser för att undvika återkommande problem. Du kan uttryckligen utesluta specifika mål eller hela undernät från aktivt söka efter standardidentifiering. 



## <a name="next-steps"></a>Nästa steg
- [Konfigurera enhetsidentifiering](configure-device-discovery.md)
- [Vanliga frågor och svar om enhetsupptäckt](device-discovery-faq.md)
