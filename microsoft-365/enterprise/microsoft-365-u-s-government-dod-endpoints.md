---
title: Office 365 amerikanska myndigheters DOD-slut punkter
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
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
description: Office 365 kräver internetanslutning. Slut punkterna nedan bör vara tillgängliga för kunder som använder Office 365 amerikanska myndigheter för offentliga DoD-abonnemang.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c19aa281dea439f1ae41e6b20f917f8fe7439d3e
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787781"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 amerikanska myndigheters DoD-slut punkter

*Gäller för Office 365-administratör*

 Office 365 kräver internetanslutning. Slut punkterna nedan bör vara tillgängliga för kunder som använder Office 365 amerikanska myndigheter för offentliga DoD-abonnemang.
  
 **Office 365-slutpunkter:** [världen över (inklusive GCC)](urls-and-ip-address-ranges.md)  |  [Office 365 som drivs av 21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Tyskland](microsoft-365-germany-endpoints.md)  |  *Office 365 amerikanska myndigheter DoD*  |  [Office 365 amerikanska myndigheter gcc](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 2021-01-04 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Ändringsloggsprenumeration](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Ladda ned:** hela listan i [JSON-format](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Börja med [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för hantering av nätverksanslutningar med dessa data. Slutpunktsdata uppdateras i början av varje månad med nya IP-adresser och URL:er publicerade 30 dagar i förväg. Detta gör att kunder som ännu inte har automatiserat uppdateringar kan slutföra sina processer innan nya anslutningar krävs. Slutpunkter kan också uppdateras under månaden om det behövs för att lösa stöd för eskalering, säkerhetstillbud och andra omedelbara driftskrav. De data som visas på den här sidan nedan skapas från de REST-baserade webbtjänsterna. Om du använder ett skript eller en nätverksenhet för att komma åt dessa data ska du gå direkt till [Webbtjänst](microsoft-365-ip-web-service.md).

I slutpunktsdata nedan visar krav för anslutning från en användares dator till Office 365. Den innehåller inte nätverksanslutningar från Microsoft till ett kundnätverk, som ibland kallas hybrid-eller inkommande nätverksanslutningar. Mer information finns i [ytterligare slut punkter som inte ingår i webb tjänsten](additional-office365-ip-addresses-and-urls.md). 

Slutpunkterna är grupperade i fyra tjänstområden. De tre första tjänsterna kan väljas oberoende för anslutning. Det fjärde tjänstområdet är ett vanligt beroende (kallat Microsoft 365 Common och Office) och måste alltid ha nätverksanslutning.

Data kolumnerna som visas är:

- **ID**: Raden för ID-numret, som även kallas för en slutpunktsuppsättning. Detta ID är samma som returneras av webbtjänsten för slutpunktsuppsättningen.

- **Kategori**: Visar om slutpunktsuppsättningen kategoriseras som "Optimera", "Tillåt" eller "Standard". Du kan läsa om de här kategorierna och vägledningen för att hantera dem [https://aka.ms/pnc](https://aka.ms/pnc) . I den här kolumnen visas även vilka slutpunktsuppsättningar som krävs för nätverksanslutningar. För slutpunktsuppsättningar som inte är nödvändiga för att ha nätverksanslutning tillhandahåller vi anteckningar i det här fältet för att ange vilka funktioner som skulle saknas om slutpunktsuppsättningen är blockerad. Om du undantar ett helt tjänstområde kräver inte slutpunktsuppsättningarna som anges som krav anslutning.

- **ER**: Det här är **Ja** om slutpunktsuppsättningen stöds över Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de väg-prefix som visas är justeras med tjänstområdet som visas. När ER är **Nej**, innebär det att ExpressRoute inte stöds för denna slutpunktsuppsättning. Tänk dock på att det inte ska finnas några vägar som annonseras för en slutpunkt där ER är **Nej**. Om du planerar att använda Azure AD Connect läser du [avsnittet särskilda överväganden](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) för att kontrol lera att du har rätt Azure AD Connect-konfiguration.

- **Adresser**: listar FQDN-namn eller domännamn med jokertecken och IP-adressintervall för slutpunktsuppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: Listar de TCP-eller UDP-portar som kombineras med adresserna för att skapa nätverksslutpunkten. Du märker kanske att det finns dubbletter i IP-adressintervall där olika portar finns med i listan.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Anteckningar för den här tabellen:

- Säkerhets-och efterlevnad Center (SCC) tillhandahåller stöd för Azure ExpressRoute för Office 365. Samma sak gäller för många funktioner som exponeras genom SCC, till exempel rapportering, granskning, Avancerad eDiscovery, enhetlig DLP och data styrning. Två specifika funktioner, PST-import och eDiscovery-export stöder för närvarande inte Azure-ExpressRoute med bara Office 365-vägfilter på grund av deras beroende av Azure Blob Storage. För att du ska kunna använda de här funktionerna måste du ha en separat anslutning till Azure Blob Storage med eventuella alternativ för Azure-anslutningar, som inkluderar Internet-anslutning eller Azure-ExpressRoute med Azure Public Route filter. Du måste utvärdera upprättandet av sådana anslutningar för båda dessa funktioner. Office 365 informations skydd-teamet känner till det här problemet och arbetar aktivt för att få support för Azure ExpressRoute för Office 365 som begränsat till Office 365-väg filter för båda dessa funktioner.

- Det finns fler valfria slut punkter för Microsoft 365-appar för företag som inte är listade och som inte behövs för att användare ska kunna starta Microsoft 365-appar för företags program och redigera dokument. Valfria slut punkter finns i Microsoft-datacenter och bearbetar, överför eller lagrar inte kunddata. Vi rekommenderar att användarnas anslutningar till dessa slut punkter dirigeras till Standardsvars gräns för Internet.
