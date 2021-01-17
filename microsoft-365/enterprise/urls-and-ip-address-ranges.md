---
title: URL-adresser och IP-adressintervall för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Sammanfattning: Office 365 kräver internetanslutning. Slutpunkterna nedan bör vara tillgängliga för kunder med Office 365-abonnemang, inklusive Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 386c92d0856b3faa88fb8a05f8ddff58a81e3c4f
ms.sourcegitcommit: a92b150da1e11d4a204c556ab98a4776727dbc22
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49883342"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>URL-adresser och IP-adressintervall för Office 365

Office 365 kräver internetanslutning. Slutpunkterna nedan bör vara tillgängliga för kunder med Office 365-abonnemang, inklusive Government Community Cloud (GCC).
  
*Office 365 Globalt (plus GCC)* | [Office 21 genom 365 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Tyskland](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Uppdaterades senast:** 2021-01-04 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Ändringsloggsprenumeration](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON formaterad](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.  <br/> | **Använd:** våra proxy-[PAC-filer](managing-office-365-endpoints.md#pacfiles) <br/> |

 Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er publicerade 30 dagar i förväg. Det gör det möjligt för kunder som ännu inte har automatiserade uppdateringar att slutföra processerna innan nya anslutningar krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar. Mer information finns i [Ytterligare slutpunkter](additional-office365-ip-addresses-and-urls.md).

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa mer om de här kategorierna och anvisningarna för hur du hanterar dem i [Nya slutpunktskategorier för Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Rekommendationer om IP- och URL-adresser för Yammer finns i [Vi rekommenderar inte att du använder hårdkodade IP-adresser för Yammer](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) på Yammer-bloggen.
>

## <a name="related-topics"></a>Relaterade ämnen

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[Allmänna Microsoft Stream-slutpunkter](https://docs.microsoft.com/stream/network-overview#general-microsoft-stream-endpoints)
  
[Övervaka Microsoft 365 anslutning](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity)

[Rot certifikatutfärdare (CA) och mellanliggande certifikatutfärdare i programsystemet från tredje part](../compliance/encryption-office-365-certificate-chains.md)
  
[Klientanslutning](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Nätverk för innehållsleverans](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure IP-intervall och servicetaggar – offentligt moln](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure IP-intervall och servicetaggar – USA: s regeringsmoln](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure IP-intervaller och servicetaggar – moln i Tyskland](https://www.microsoft.com/download/details.aspx?id=57064)

[Microsoft Azure IP-intervall och servicetaggar – moln i Kina](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)

[Servicenamn och Transportprotokoll portnummerregister](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
