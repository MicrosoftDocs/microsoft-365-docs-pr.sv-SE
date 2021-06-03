---
title: Office 365 Slutpunkter för DOD för amerikanska myndigheter
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 kräver internetanslutning. Slutpunkterna nedan bör endast kunna nås av kunder Office 365 abonnemang för myndigheter i USA.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fcfad7e0ad3ddafeffc79490ff99d949a8bfa7b
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730756"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 U.S. Government DoD-slutpunkter

*Gäller för: Office 365 Admin*

 Office 365 kräver internetanslutning. Slutpunkterna nedan bör endast kunna nås av kunder Office 365 abonnemang för myndigheter i USA.
  
 **Office 365 slutpunkter:** Globalt [(inklusive GCC)](urls-and-ip-address-ranges.md)Office 365 som drivs av  |  [21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Germany](microsoft-365-germany-endpoints.md)Office 365  |  *U.S. Government DoD* Office 365  |  [U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 2021-05-28 – ![ prenumeration på ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-ändringslogg](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Ladda ned:** hela listan i [JSON-format](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er som publicerats 30 dagar i förväg. På så sätt kan kunder som ännu inte har automatiska uppdateringar slutföra sina processer innan ny anslutning krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar. Mer information finns i [Ytterligare slutpunkter som inte ingår i webbtjänsten.](additional-office365-ip-addresses-and-urls.md) 

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om kategorierna och vägledning för hantering av dem på [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) . I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**. Om du planerar att använda Azure AD Anslut läser du avsnittet om särskilda [hänsynstaganden](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) för att säkerställa att du har rätt Azure AD Anslut konfiguration.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Kommentarer för den här tabellen:

- Säkerhets- och efterlevnadscentret (SCC) tillhandahåller stöd för Azure ExpressRoute för Office 365. Detsamma gäller för många funktioner som exponeras genom SCC, till exempel rapportering, granskning, Advanced eDiscovery, enhetlig DLP och datastyrning. Två specifika funktioner, PST-import och eDiscovery-export, stöder för närvarande inte Azure ExpressRoute med endast Office 365-routefilter på grund av deras beroende av Azure Blob Storage. Om du vill använda de här funktionerna behöver du separat anslutning till Azure Blob Storage med alla Azure-anslutningsalternativ som kan användas, till exempel internetanslutning eller Azure ExpressRoute med offentliga Azure-routefilter. Du måste utvärdera etableringen av sådana anslutningar för båda dessa funktioner. Teamet Office 365 Information Protection är medvetna om den här begränsningen och arbetar aktivt för att ge stöd för Azure ExpressRoute för Office 365 som begränsat till Office 365-route-filter för båda dessa funktioner.

- Det finns ytterligare valfria slutpunkter för Microsoft 365-appar för företag som inte visas och som inte krävs för att användare ska Microsoft 365-appar för företag program och redigera dokument. Valfria slutpunkter finns i Microsofts datacenter och bearbetar, överför eller lagrar inte kunddata. Vi rekommenderar att användaranslutningar till dessa slutpunkter dirigeras till den utgående perimeter som används som standard för Internet.