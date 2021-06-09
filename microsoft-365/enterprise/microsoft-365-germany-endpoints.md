---
title: Office 365 för Tyskland
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
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
description: I den här artikeln hittar du slutpunkter som kan nås av kunder som använder Office 365 i Tyskland.
hideEdit: true
ms.openlocfilehash: 0d96300e77c67ac05ea18ab23d63c01d4f840dfb
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759900"
---
# <a name="office-365-germany-endpoints"></a>Slutpunkter för Office 365 Germany

 *Gäller för: Office 365 Admin*

Office 365 kräver internetanslutning. Slutpunkterna nedan bör endast kunna nås av kunder som använder **Office 365 Germany.**

> [!NOTE]
> För kunder som befinner sig i övergången till den nya Microsoft 365 datacenterområdet i Tyskland kommer slutpunkterna att ändras.
> Mer information finns i Migrering från [Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena.](ms-cloud-germany-transition.md)
  
 **Office 365 slutpunkter:** Globalt [(inklusive GCC)](urls-and-ip-address-ranges.md)Office 365 som drivs av   |  [21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  *Office 365 Germany* Office 365  |  [U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)Office 365  |  [U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 2020-12-01 – ![ prenumeration på ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-ändringslogg](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON formaterad](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.  <br/> |

Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er som publicerats 30 dagar i förväg. På så sätt kan kunder som ännu inte har automatiska uppdateringar slutföra sina processer innan ny anslutning krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. Du kan alltid referera till prenumerationen [på ändringsloggen.](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar.

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om kategorierna och vägledning för hantering av dem på [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) . I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

