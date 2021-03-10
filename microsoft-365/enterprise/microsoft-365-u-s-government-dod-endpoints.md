---
title: Office 365 DOD-slutpunkter för myndigheter i USA
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/28/2021
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
description: Office 365 kräver internetanslutning. Slutpunkterna nedan bör endast kunna nås av kunder som använder Office 365 U.S. Government DoD-abonnemang.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7001ac258b0c866c6b41a580394c771d192beae
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596950"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 U.S. Government DoD-slutpunkter

*Gäller för: Office 365 Admin*

 Office 365 kräver internetanslutning. Slutpunkterna nedan bör endast kunna nås av kunder som använder Office 365 U.S. Government DoD-abonnemang.
  
 **Office 365-slutpunkter:** Globalt [(inklusive GCC)](urls-and-ip-address-ranges.md)Office 365 som drivs av  |  [21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Germany](microsoft-365-germany-endpoints.md)Office  |  *365 U.S. Government DoD* Office  |  [365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 2021-01-28 – ![ prenumeration på ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-ändringslogg](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Ladda ned:** den fullständiga listan i [JSON-format](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras efter behov i början av varje månad med nya IP-adresser och URL-adresser som publicerats 30 dagar innan de blir aktiva. Det innebär att kunder som ännu inte har automatiska uppdateringar kan slutföra sina processer innan ny anslutning krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar. Mer information finns i [Ytterligare slutpunkter som inte ingår i webbtjänsten.](additional-office365-ip-addresses-and-urls.md) 

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om de här kategorierna och vägledning för hantering av dem [https://aka.ms/pnc](https://aka.ms/pnc) på. I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**. Om du planerar att använda Azure AD Connect läser du avsnittet [om särskilda](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) överväganden för att säkerställa att du har rätt Azure AD Connect-konfiguration.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Kommentarer för den här tabellen:

- Säkerhets- och efterlevnadscentret (SCC) tillhandahåller support för Azure ExpressRoute för Office 365. Detsamma gäller för många funktioner som exponeras genom SCC, till exempel rapportering, granskning, Advanced eDiscovery, enhetlig DLP och datastyrning. Två specifika funktioner, PST-import och eDiscovery-export, stöder för närvarande inte Azure ExpressRoute med enbart routefilter för Office 365 på grund av deras beroende av Azure Blob Storage. Om du vill använda de här funktionerna behöver du separata anslutningar till Azure Blob Storage med alla Azure-anslutningsalternativ som kan användas, till exempel internetanslutning eller Azure ExpressRoute med offentliga Azure-routefilter. Du måste utvärdera etableringen av sådana anslutningar för båda dessa funktioner. Office 365-teamet bakom informationsskydd är medvetna om den här begränsningen och arbetar aktivt för att ge stöd för Azure ExpressRoute för Office 365, begränsat till routefilter för Office 365 för båda dessa funktioner.

- Det finns ytterligare valfria slutpunkter för Microsoft 365-program för företag som inte visas och som inte är nödvändiga för att användare ska kunna starta Microsoft 365-program för företagsprogram och redigera dokument. Valfria slutpunkter finns i Microsofts datacenter och bearbetar, överför eller lagrar inte kunddata. Vi rekommenderar att användaranslutningar till dessa slutpunkter dirigeras till den utgående perimeter som används som standard för Internet.
