---
title: Vanliga frågor och svar om enhetsidentifiering
description: Hitta svar på vanliga frågor och svar om enhetsidentifiering
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b3fef3479fa2d36806e6657b31f5152c54b9251f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765005"
---
# <a name="device-discovery-frequently-asked-questions"></a>Vanliga frågor och svar om enhetsidentifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Hitta svar på vanliga frågor och svar om enhetsidentifiering.

## <a name="what-is-basic-discovery-mode"></a>Vad är grundläggande identifieringsläge?
Med det här läget kan varje Microsoft Defender för slutpunktsbaserad enhet samla in nätverksdata och upptäcka intilliggande enheter. Inbyggda slutpunkter samlar in händelser in passivt i nätverket och extraherar enhetsinformation från dem. Ingen nätverkstrafik kommer att initieras. Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device. Dessa data används för att lista ohanterade enheter i nätverket.

## <a name="can-i-disable-basic-discovery"></a>Kan jag inaktivera grundläggande identifiering?
Du kan stänga av enhetsidentifiering via sidan [Avancerade](advanced-features.md) funktioner. Men du tappar synen på ohanterade enheter i nätverket. 

## <a name="what-is-standard-discovery-mode"></a>Vad är standardidentifieringsläge?
 I det här läget kan slutpunkter som förs över till Microsoft Defender för Endpoint aktivt registrera observerade enheter i nätverket för att samla in data (och se hur mycket nätverkstrafik det finns). Det här läget rekommenderas starkt för att skapa en tillförlitlig och sammanhängande enhetsinventering. Om du väljer att inaktivera det här läget och väljer Grundläggande identifieringsläge får du sannolikt bara begränsad synlighet för ohanterade slutpunkter i nätverket.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Kan jag styra vilka enheter som utför standardidentifiering?
 Du kan anpassa listan med enheter som används för identifiering av standard. Du kan aktivera standardidentifiering för alla enheter som har stöd för den här funktionen (för närvarande endast Windows 10-enheter) eller välja en delmängd eller delmängder av dina enheter genom att ange deras enhetstaggar. I så fall konfigureras alla andra enheter för endast enkel identifiering. Konfigurationen är tillgänglig på sidan inställningar för enhetsidentifiering.

## <a name="which-onboarded-devices-can-perform-discovery"></a>Vilka onboarded-enheter kan identifieras?
 Onboarded devices running on Windows 10 version 1809 or later can perform discovery.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Vad händer om mina onboarded-enheter är anslutna till mitt hemnätverk eller till en offentlig åtkomstpunkt?
 Identifieringsmotorn skiljer mellan nätverkshändelser som tas emot i företagsnätverket jämfört med utanför företagsnätverket. Genom att korrelera nätverksidentifierare i alla klientorganisationens klienter differentieras mellan dem som tagits emot från privata nätverk och företagsnätverk. Privata nätverksenheter visas inte i inventeringen och kommer inte att sökas aktivt.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Vilka protokoll samlar du in och analyserar?
 Som standard samlar alla onboarded-enheter som kör på Windows 10 version 1809 eller senare in och analyserar följande protokoll: ARP, CDP, WM, DHCPv6, IP (rubriker), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (rubriker), UDP (rubriker), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Vilka protokoll använder du för aktiv sannolikhet vid standardidentifiering?
 När en enhet är konfigurerad för att köra standardidentifiering, används sannolikhet för exponerade tjänster med hjälp av följande protokoll: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Hur kan jag utesluta mål från att få reda på standardidentifiering?
 Om det finns enheter i nätverket som inte bör sökas aktivt kan du också definiera en lista över undantag för att förhindra att de genomsöks. Konfigurationen är tillgänglig på sidan inställningar för enhetsidentifiering.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Kan jag utesluta enheter från att upptäckas?
 Eftersom enhetsidentifiering använder passiva metoder för att upptäcka enheter i nätverket, kan alla enheter som kommunicerar med dina onboarded-enheter i företagsnätverket upptäckas och listas i inventeringen. Du kan utesluta enheter från endast aktiv sannolikhet.

## <a name="how-frequent-is-the-active-probing"></a>Hur ofta är den aktiva boningen?
 Enheter söker aktivt efter ändringar i enhetsegenskaper (var 1:e till 3:e vecka) för att säkerställa att den befintliga informationen är uppdaterad.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mitt säkerhetsverktyg upphöjd varning vid UnicastScanner.ps1 eller portsökningsaktivitet initierad av den, vad ska jag göra?
 De aktiva testskripten är signerade av Microsoft och är säkra. Du kan lägga till följande sökväg till undantagslistan: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Hur stor är mängden trafik som genereras av den aktiva, standardavvikaren för identifiering?
 Med aktiv sannolikhet kan upp till 5 000 trafik genereras mellan den onboarded enheten och den provade enheten, varje försök med sannolikhet

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Varför finns det några avvikelser mellan "kan introduceras" enheter i enhetsinventeringen och antalet "enheter att registrera" i panelen för instrumentpanelen?
Du kan märka skillnader mellan antalet listade enheter under "kan introduceras" i enhetsinventeringen, säkerhetsrekommendationer för "onboard to Microsoft Defender for Endpoint" och "enheter för att registrera"-instrumentpanelswidgeten.

 Säkerhetsrekommendationer och instrumentpanelswidgetar gäller för enheter som är stabila i nätverket. utesluter tillfälliga enheter, gästenheter och andra. Rekommendationen är att använda beständiga enheter som också antyder organisationens övergripande säkerhetsresultat.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Kan jag registrera ohanterade enheter som hittades?
 Ja. Ohanterade slutpunkter i nätverket innebär svagheter och risker för nätverket. Att registrera dem i tjänsten kan öka säkerheten för dem. 


