---
title: 'URL: er och IP-adressintervall för Office 365 som drivs av 21Vianet'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/08/2020
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
description: Den här artikeln innehåller URL-adresser och IP-adressintervall för Office 365 när de drivs av 21Vianet i Kina.
hideEdit: true
ms.openlocfilehash: dd833ded674ded9e8f291a72f93e61eda2b9aeb8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694475"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>URL: er och IP-adressintervall för Office 365 som drivs av 21Vianet

 *Gäller för Office 365 som drivs av 21Vianet – Small Business admin, Office 365 som drivs av 21Vianet – admin*

**Sammanfattning**: följande slut punkter (FQDN, portar, URL: er, IPv4-och IPv6-prefix) gäller för Office 365 som drivs av 21 Vianet och är avsedda att leverera produktivitets tjänster till organisationer med bara dessa abonnemang.
  
 **Office 365-slutpunkter:** [världen över (inklusive GCC)](urls-and-ip-address-ranges.md)   |  *Office 365 som drivs av 21 Vianet*  |  [Office 365 Tyskland](microsoft-365-germany-endpoints.md)  |  [Office 365 amerikanska myndigheter DoD](microsoft-365-u-s-government-dod-endpoints.md)  |  [Office 365 amerikanska myndigheter gcc](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 07/08/2020 – ![ prenumeration på RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [ändrings logg](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Ladda ned:** alla obligatoriska och valfria destinationer i en [JSON-formaterad](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) lista.  <br/> |

Börja med att [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för att hantera nätverks anslutningen med dessa data. Slut punkter uppdateras i början av varje månad med nya IP-adresser och URL: er publicerade 30 dagar innan de aktive ras. Detta gör det möjligt för kunder som ännu inte har automatiserade uppdateringar att genomföra sina processer innan ny anslutning krävs. Slut punkter kan också uppdateras under den månad som behövs för att adressera supporten, säkerhets tillbud eller andra omedelbara drifts krav. De data som visas på den här sidan nedan är alla som genereras från de REST-baserade webb tjänsterna. Om du använder ett skript eller en nätverks enhet för att komma åt dessa data bör du gå direkt till [webb tjänsten](microsoft-365-ip-web-service.md) .

För slut punkts data nedan visas krav för anslutning från en användares dator till Office 365. Den inkluderar inte nätverks anslutningar från Microsoft till ett kund nätverk, ibland kallade hybrid-eller inkommande nätverks anslutningar.

Slut punkterna är grupperade i fyra service områden. De första tre tjänst områdena kan väljas separat för anslutning. Det fjärde tjänste området är ett vanligt beroende (kallas Microsoft 365 common och Office) och måste alltid ha nätverks anslutning.

Data kolumner visas:

- **ID**: radens ID-nummer, som också kallas för en slut punkts uppsättning. Detta ID är det samma som returneras av webb tjänsten för slut punkts uppsättningen.

- **Kategori**: visar om slut punkts uppsättningen kategoriseras som "optimera", "Tillåt" eller "standard". Du kan läsa om de här kategorierna och vägledningen för att hantera dem [https://aka.ms/pnc](https://aka.ms/pnc) . I den här kolumnen kan du också se vilka slut punkts uppsättningar som krävs för att nätverks anslutningen ska visas. För slut punkts uppsättningar som inte måste ha nätverks anslutning ger vi anteckningar i det här fältet för att ange vilka funktioner som skulle sakna om slut punkts uppsättningen blockeras. Om du utesluter ett helt tjänst område behöver inte slut punkts uppsättningarna som krävs vara anslutningar.

- **Er**: det här är **Ja** om slut punkts uppsättningen stöds via Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de adressprefix som visas är justerade med tjänst området som visas. När ER är **Nej**innebär det att ExpressRoute inte stöds för den här slut punkts uppsättningen. Men det bör inte antas att inga vägar annonseras för en slut punkts uppsättning där ER är **Nej**.

- **Adresser**: Visar FQDN-namnen eller domän namn för jokertecken för slut punkts uppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: visar TCP-eller UDP-portarna som kombineras med adresserna för att bilda nätverks slut punkten. Det kan hända att en del dubbletter i IP-adressintervall där det finns olika portar visas.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


