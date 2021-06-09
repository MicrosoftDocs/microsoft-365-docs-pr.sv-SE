---
title: Planera för nätverksenheter som ansluter till Office 365 tjänster
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Sammanfattning: Här beskrivs överväganden för nätverkskapacitet, WAN-acceleratorer och enheter för belastningsutjämning som används för att ansluta till Office 365.'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927506"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planera för nätverksenheter som ansluter till Office 365 tjänster

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*
  
Viss nätverksmaskinvara kan ha begränsningar på antalet samtidiga sessioner som stöds. För organisationer som har fler än 2 000 användare rekommenderar vi att de övervakar sina nätverksenheter för att säkerställa att de kan hantera ytterligare Office 365-tjänstetrafik. Med SNMP-övervakningsprogramvara (Simple Network Management Protocol) kan du få hjälp att göra detta.

Den här artikeln är en [del av Nätverksplanering och prestandajustering för Office 365](./network-planning-and-performance.md).

Lokala utgående proxyinställningar för Internet påverkar också anslutningen Office 365 dina klientprogram. Du måste också konfigurera nätverkets proxyenheter för att tillåta anslutningar för URL:er och program för Microsofts molntjänster. Varje organisation är olika. Läs fallstudien för att få en uppfattning om hur Microsoft hanterar den här processen och hur mycket bandbredd [vi erbjuder.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
I följande Skype för företag finns mer information om inställningar Skype för företag hjälpartiklar:
  
- [Felsökning Skype för företag online inloggningsfel för administratörer](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Du kan inte Skype för företag eller till vissa funktioner, eftersom en lokal brandvägg blockerar anslutningen](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Även om många av de Skype för företag är väldigt specifika är de allmänna råden om nätverkskonfiguration användbara för Office 365 tjänster.
  
## <a name="determining-network-capacity"></a>Fastställa nätverkskapaciteten

Varje nätverksenhet som finns på en anslutning har en kapacitetsgräns. Dessa enheter omfattar klient- och servernätverkskort, routrar, switchar och hubbar som kopplar ihop dem. Tillräcklig nätverkskapacitet innebär att ingen av dem är mättad. Det är viktigt att övervaka nätverksaktiviteten för att säkerställa att de verkliga belastningarna på alla nätverksenheter är lägre än deras högsta kapacitet. Nätverkskapaciteten påverkar proxyenhetens prestanda.
  
I de flesta fall är det Internetanslutningens bandbredd som sätter gränsen för mängden trafik. Svag prestanda under tider med hög trafik beror troligen på överdriven användning av Internetlänken. Den här situationen gäller även ett scenario med en filial, där filialens proxyservrar är anslutna till proxyenheten på filialens huvudkontor via en långsam WAN-länk (Wide Area Network).
  
För att testa nätverkskapaciteten övervakar du nätverksaktiviteten på proxynätverksgränssnittet. Om det är mer än 75 procent av den maximala bandbredden för något nätverksgränssnitt ska du överväga att öka bandbredden på den nätverksinfrastruktur som är otillräcklig. Du kan också fundera på att använda avancerade funktioner, till exempel HTTP-komprimering.
  
## <a name="wan-accelerators"></a>WAN-acceleratorer

Om din organisation använder proxyservrar för WAN-acceleration (wide area network) kan det uppstå problem när du använder Office 365 tjänster. Du kan behöva optimera nätverksenheten eller -enheterna för att säkerställa att användarna har en enhetlig upplevelse när de använder Office 365. Om du till Office 365 krypterar vissa Office 365 innehåll och TCP-huvudet. Din enhet kanske inte kan hantera den här typen av trafik.
  
Läs vår supportinformation om att [använda styrenhet för WAN-optimering eller trafik-/kontrollenheter med Office 365.](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>Enheter för belastningsutjämning för maskin- och programvara

Organisationen måste använda en lösning för maskinvarufördelning (HLB) eller utjämning av nätverksbelastning (NLB) för att distribuera förfrågningar till AD FS-servrarna (Active Directory Federation Services) och/eller Exchange-hybridservrarna. Belastningsutjämningsenheterna styr nätverkstrafiken till de lokala servrarna. Servrarna är avgörande för att säkerställa tillgängligheten för enkel inloggning och Exchange-hybriddistribution.
  
Vi tillhandahåller en programvarubaserad NLB-lösning inbyggd i Windows Server. Office 365 den här lösningen för att få belastningsutjämning.
  
## <a name="firewalls-and-proxies"></a>Brandväggar och proxy

Mer information om hur du konfigurerar brandväggar och proxyenheter för att ansluta till Office 365 finns i Hantera Office 365-slutpunkter , Utvärdera [Office 365](assessing-network-connectivity.md)nätverksanslutning och vanliga frågor och [svar om Office 365-slutpunkter](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) om du vill veta mer om enheter och kretsval. [](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
## <a name="see-also"></a>Se även

[Installationsguider för Office 365 tjänster](setup-guides-for-microsoft-365.md)

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)