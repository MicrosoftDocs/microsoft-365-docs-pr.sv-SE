---
title: Undersöka anslutningshändelser som inträffar bakom framåt proxy
description: Lär dig hur du använder avancerad HTTP-nivåövervakning med nätverksskydd i Microsoft Defender ATP, som visar ett verkligt mål i stället för en proxyserver.
keywords: proxy, nätverksskydd, vidarebefordra proxy, nätverkshändelser, granskning, blockering, domännamn, domän
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7eaa4bb76d7607f0b55c87482d1104a0897c9d36
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186095"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Undersöka anslutningshändelser som inträffar bakom framåt proxy

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender för Endpoint har stöd för övervakning av nätverksanslutningen från olika nivåer av nätverksstacken. Ett svårt fall är när nätverket använder en framåtproxy som en gateway till Internet.

Proxyn fungerar som om den var målslutpunkten.  I sådana fall granskar enkla nätverksanslutningsskärmar anslutningarna med proxyn, vilket är korrekt men har ett lägre undersökningsvärde. 

Defender för Endpoint har stöd för avancerad HTTP-nivåövervakning via nätverksskydd. När den är aktiverad visas en ny typ av händelse där de verkliga domännamnen visas.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Använda nätverksskydd för att övervaka nätverksanslutningen bakom en brandvägg
Det är möjligt att övervaka nätverksanslutningen bakom en vidarebefordrad proxyserver på grund av ytterligare nätverkshändelser som kommer från nätverksskyddet. Om du vill visa dem på en tidslinje på en enhet aktiverar du nätverksskyddet (minst i granskningsläge). 

Nätverksskyddet kan styras med hjälp av följande lägen:

- **Blockera** <br> Användare eller appar kommer att blockeras från att ansluta till skadliga domäner. Du kan se aktiviteten i Microsoft Defender Säkerhetscenter.
- **Granskning** <br> Användare eller appar kommer inte att blockeras från att ansluta till skadliga domäner. Men den här aktiviteten visas fortfarande i Microsoft Defender Säkerhetscenter.


Om du inaktiverar nätverksskydd blockeras inte användare eller appar från att ansluta till skadliga domäner. Du ser ingen nätverksaktivitet i Microsoft Defender Säkerhetscenter.

Om du inte konfigurerar den inaktiveras nätverksblockering som standard.

Mer information finns i [Aktivera nätverksskydd](enable-network-protection.md).

## <a name="investigation-impact"></a>Undersöknings påverkan
När nätverksskyddet är aktiverat ser du att IP-adressen fortsätter representera proxyn på en enhets tidslinje, medan den verkliga måladressen visas.

![Bild av nätverkshändelser på enhetens tidslinje](images/atp-proxy-investigation.png)

Ytterligare händelser som utlöses av nätverkets skyddslager är nu tillgängliga för att ta fram de verkliga domännamnen även bakom en proxy.

Händelsens information:

![Bild av en enskild nätverkshändelse](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Sök efter anslutningshändelser med avancerad sökning 
Alla nya anslutningshändelser är också tillgängliga så att du kan leta efter avancerad sökning. Eftersom dessa händelser är anslutningshändelser kan du hitta dem under tabellen DeviceNetworkEvents under `ConnecionSuccess` åtgärdstyp.

Med den här enkla frågan visas alla relevanta händelser:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Bild av avancerad fråga för sökning](images/atp-proxy-investigation-ah.png)

Du kan också filtrera bort händelser som är relaterade till anslutningen till själva proxyn. 

Använd följande fråga för att filtrera ut anslutningarna till proxyn:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Relaterade ämnen
- [Tillämpa nätverksskydd med GP – princip-CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
