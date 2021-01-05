---
title: Office 365-slutpunkter för Tyskland
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: I den här artikeln hittar du slut punkter som kan nås för kunder som använder Office 365 i Tyskland.
hideEdit: true
ms.openlocfilehash: 767c7dd570ac03ae1ceb784b4917ee816837530a
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751633"
---
# <a name="office-365-germany-endpoints"></a>Slutpunkter för Office 365 Germany

 *Gäller för Office 365-administratör*

Office 365 kräver internetanslutning. Slut punkterna nedan bör kunna nås för kunder som använder endast **Office 365 Germany** -abonnemang.
  
 **Office 365-slutpunkter:** [världen över (inklusive GCC)](urls-and-ip-address-ranges.md)   |  [Office 365 som drivs av 21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  *Office 365 Tyskland*  |  [Office 365 amerikanska myndigheter DoD](microsoft-365-u-s-government-dod-endpoints.md)  |  [Office 365 amerikanska myndigheter gcc](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 01/04/2021 – ![ prenumeration på RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [ändrings logg](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON formaterad](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.  <br/> |

Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er publicerade 30 dagar i förväg. Detta gör att kunder som ännu inte har automatiserat uppdateringar kan slutföra sina processer innan nya anslutningar krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. Du kan alltid hänvisa till [ändrings logg prenumerationen](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar.

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om de här kategorierna och vägledningen för att hantera dem [https://aka.ms/pnc](https://aka.ms/pnc) . I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

