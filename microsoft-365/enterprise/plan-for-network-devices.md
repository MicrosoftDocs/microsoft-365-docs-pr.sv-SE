---
title: Planera för nätverks enheter som ansluter till Office 365-tjänster
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
description: 'Sammanfattning: beskriver överväganden för nätverks kapacitet, WAN-acceleratorer och belastnings Utjämnings enheter som används för att ansluta till Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694569"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planera för nätverks enheter som ansluter till Office 365-tjänster

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*
  
Vissa nätverks enheter kan ha begränsningar för antalet samtidiga sessioner som stöds. För organisationer med fler än 2 000 användare rekommenderar vi att de övervakar sina nätverks enheter så att de kan hantera ytterligare Office 365-tjänst trafik. Med SNMP-programmet (Simple Network Management Protocol) kan du göra det här.

Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune).

Lokala utgående Internet-proxyinställningar påverkar även anslutningar till Office 365-tjänster för dina klient program. Du måste också konfigurera nätenheter för att tillåta anslutningar för URL-adresser och program för Microsofts moln tjänster. Alla organisationer är olika. För att få en uppfattning om hur Microsoft hanterar den här processen och hur mycket bandbredd vi tillhandahåller [läser du fallstudien](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Följande hjälp artiklar för Skype för företag har mer information om Skype för företag-inställningar:
  
- [Felsöka inloggnings problem i Skype för företag – Online för administratörer](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Det går inte att ansluta till Skype för företag, eller vissa funktioner fungerar inte, eftersom en lokal brand vägg blockerar anslutningen](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Även om många av de här inställningarna är Skype för företag-specifika är de allmänna rikt linjerna för nätverks konfiguration användbara för alla Office 365-tjänster.
  
## <a name="determining-network-capacity"></a>Avgöra nätverks kapacitet

Alla nätverks enheter som finns på en anslutning har sin kapacitets gräns. Dessa enheter inkluderar klient-och Server nätverkskort, routrar, växlar och hubbar som sammankopplar dem. Tillräcklig nätverks kapacitet innebär att inga av dem är mättade. Det är viktigt att övervaka nätverks aktivitet för att säkerställa att de faktiska belastningarna på alla nätverks enheter är mindre än deras högsta kapacitet. Nätverks kapaciteten påverkar enhetens prestanda.
  
I de flesta fall anger bandbredden för Internet anslutningen begränsningen för mängden trafik. Svag prestanda under hög trafik tid beror antagligen på att Internet länken används för många. Den här situationen gäller också för ett filial kontors scenario där lokal kontors proxyserver är ansluten till proxyservern på filialens huvud kontor via en långsam WAN-länk (Wide Area Network).
  
Testa nätverks kapacitet genom att övervaka nätverks aktiviteten på proxy-nätverkets gränssnitt. Om det är mer än 75 procent av den maximala bandbredden för ett nätverks gränssnitt, bör du överväga att öka bandbredden hos nätverks infrastrukturen som är otillräcklig. Eller Använd avancerade funktioner, till exempel HTTP-komprimering.
  
## <a name="wan-accelerators"></a>WAN-acceleratorer

Om din organisation använder WAN-acceleration (Wide Area Network) kan du stöta på problem när du använder Office 365-tjänsterna. Du kan behöva optimera nätverks enheter eller enheter för att säkerställa att användarna har en enhetlig upplevelse när de använder Office 365. Office 365-tjänster kryptera till exempel lite Office 365-innehåll och TCP-huvudet. Din enhet kanske inte kan hantera den här typen av trafik.
  
Läs vår support policy om hur du [använder en styrenhet för WAN-optimering eller trafik-och inspektions enheter med Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Belastnings Utjämnings enheter för maskinvaru-och program vara

Din organisation måste använda en maskinvarubaserad belastnings utjämning (HLB) eller en lösning för Utjämning av nätverks belastning (NLB) för att distribuera förfrågningar till dina AD FS-servrar (Active Directory Federation Services) och/eller dina Exchange-hybrider. Enheter för belastnings utjämning styr nätverks trafiken till lokala servrar. Dessa servrar är nödvändiga för att säkerställa tillgänglighet för enkel inloggning och Exchange-hybrid distribution.
  
En programvarubaserad NLB-lösning som är inbyggd i Windows Server tillhandahålls. Office 365 stöder den här lösningen för belastnings utjämning.
  
## <a name="firewalls-and-proxies"></a>Brand väggar och proxyservrar

Mer information om hur du konfigurerar brand väggar och proxyservrar att ansluta till Office 365 finns i [Hantera office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [utvärdera Office 365 nätverks anslutningar](assessing-network-connectivity.md)och [vanliga frågor och svar om Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) för att lära dig mer om enheter och krets val.
  
## <a name="see-also"></a>Se även

[Installations guider för Office 365-tjänster](setup-guides-for-microsoft-365.md)

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
