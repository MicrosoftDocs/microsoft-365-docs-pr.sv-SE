---
title: URL-adresser och IP-adressintervall för Office 365 som drivs av 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/28/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: Den här artikeln innehåller URL-adresser och IP-adressintervall för Office 365 när det drivs av 21Vianet i Kina.
hideEdit: true
ms.openlocfilehash: dae2b5feb4fbf7fc3e9bdd2419e2d114b5507ee8
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597076"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>URL-adresser och IP-adressintervall för Office 365 som drivs av 21Vianet

 *Gäller för: Office 365 som drivs av 21Vianet – Small Business Admin, Office 365 som drivs av 21Vianet – Admin*

**Sammanfattning:** Följande slutpunkter (FQDN, portar, URL-adresser, IPv4- och IPv6-prefix) gäller för Office 365 som drivs av 21 Vianet och är utformade för att ge produktivitetstjänster till organisationer som bara använder de här abonnemangen.
  
 **Office 365-slutpunkter:** Globalt [(inklusive GCC)](urls-and-ip-address-ranges.md)Office 365 som drivs av   |  *21 Vianet*  |  [Office 365 Germany](microsoft-365-germany-endpoints.md)Office  |  [365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)Office  |  [365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 2020-08-28 – ![ prenumeration på ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-ändringslogg](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON formaterad](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.  <br/> |

Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras efter behov i början av varje månad med nya IP-adresser och URL-adresser som publicerats 30 dagar innan de blir aktiva. Det gör det möjligt för kunder som ännu inte har automatiserade uppdateringar att slutföra processerna innan nya anslutningar krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

Slutpunktsdata nedan visar krav på anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar.

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori:** Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om de här kategorierna och vägledning för hantering av dem [https://aka.ms/pnc](https://aka.ms/pnc) på. I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


