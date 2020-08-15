---
title: Office 365 amerikanska myndigheters GCC höga slut punkter
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/28/2020
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
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: I den här artikeln hittar du slut punkter som kan nås av kunder som använder Office 365 amerikanska myndigheters GCC höga abonnemang.
hideEdit: true
ms.openlocfilehash: 6c7424b487f107d1459996ac9ee6e880e11b08c5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694330"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 amerikanska myndigheters GCC höga slut punkter

 *Gäller för Office 365-administratör*

Office 365 kräver anslutning till Internet. Slut punkterna nedan bör vara tillgängliga för kunder som använder Office 365 amerikanska myndigheter för endast GCC.
  
 **Office 365-slutpunkter:** [världen över (inklusive GCC)](urls-and-ip-address-ranges.md)  |  [Office 365 som drivs av 21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Tyskland](microsoft-365-germany-endpoints.md)   |  [Office 365 amerikanska myndigheter DoD](microsoft-365-u-s-government-dod-endpoints.md)  |  *Office 365 amerikanska myndigheter gcc* |
  
|||
|:-----|:-----|
|**Uppdaterades senast:** 07/28/2020 – ![ prenumeration på RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [ändrings logg](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Ladda ned:** hela listan i [JSON-format](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Börja med att [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att förstå våra rekommendationer för att hantera nätverks anslutningen med dessa data. Slut punkter uppdateras i början av varje månad med nya IP-adresser och URL: er publicerade 30 dagar innan de aktive ras. Detta gör att kunder som ännu inte har automatiserat uppdateringar kan slutföra sina processer innan nya anslutningar krävs. Slut punkter kan också uppdateras under den månad som behövs för att adressera supporten, säkerhets tillbud eller andra omedelbara drifts krav. De data som visas på den här sidan nedan är alla som genereras från de REST-baserade webb tjänsterna. Om du använder ett skript eller en nätverks enhet för att komma åt dessa data bör du gå direkt till [webb tjänsten](microsoft-365-ip-web-service.md) .

För slut punkts data nedan visas krav för anslutning från en användares dator till Office 365. Den inkluderar inte nätverks anslutningar från Microsoft till ett kund nätverk, ibland kallade hybrid-eller inkommande nätverks anslutningar.

Slut punkterna är grupperade i fyra service områden. De första tre tjänst områdena kan väljas separat för anslutning. Det fjärde tjänste området är ett vanligt beroende (kallas Microsoft 365 common och Office) och måste alltid ha nätverks anslutning.

Data kolumner visas:

- **ID**: radens ID-nummer, som också kallas för en slut punkts uppsättning. Detta ID är det samma som returneras av webb tjänsten för slut punkts uppsättningen.

- **Kategori**: visar om slut punkts uppsättningen kategoriseras som "optimera", "Tillåt" eller "standard". Du kan läsa om de här kategorierna och vägledningen för att hantera dem [https://aka.ms/pnc](https://aka.ms/pnc) . I den här kolumnen kan du också se vilka slut punkts uppsättningar som krävs för att nätverks anslutningen ska visas. För slut punkts uppsättningar som inte måste ha nätverks anslutning ger vi anteckningar i det här fältet för att ange vilka funktioner som skulle sakna om slut punkts uppsättningen blockeras. Om du utesluter ett helt tjänst område behöver inte slut punkts uppsättningarna som krävs vara anslutningar.

- **Er**: det här är **Ja** om slut punkts uppsättningen stöds via Azure ExpressRoute med Office 365-väg-prefix. BGP-communityn som innehåller de adressprefix som visas är justerade med tjänst området som visas. När ER är **Nej**innebär det att ExpressRoute inte stöds för den här slut punkts uppsättningen. Men det bör inte antas att inga vägar annonseras för en slut punkts uppsättning där ER är **Nej**. Om du planerar att använda Azure AD Connect läser du [avsnittet särskilda överväganden](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) för att kontrol lera att du har rätt Azure AD Connect-konfiguration.

- **Adresser**: Visar FQDN-namnen eller domän namn för jokertecken för slut punkts uppsättningen. Observera att ett IP-adressintervall är i CIDR-format och kan innehålla många enskilda IP-adresser i det angivna nätverket.
 
- **Portar**: visar TCP-eller UDP-portarna som kombineras med adresserna för att bilda nätverks slut punkten. Det kan hända att en del dubbletter i IP-adressintervall där det finns olika portar visas.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Anteckningar för den här tabellen:

- Säkerhets-och efterlevnad Center (SCC) tillhandahåller stöd för Azure ExpressRoute för Office 365. Samma sak gäller för många funktioner som exponeras genom SCC, till exempel rapportering, granskning, Avancerad eDiscovery, enhetlig DLP och data styrning. Två specifika funktioner, PST-import och eDiscovery-export stöder för närvarande inte Azure-ExpressRoute med bara Office 365-vägfilter på grund av deras beroende av Azure Blob Storage. För att du ska kunna använda de här funktionerna måste du ha en separat anslutning till Azure Blob Storage med eventuella alternativ för Azure-anslutningar, som inkluderar Internet-anslutning eller Azure-ExpressRoute med Azure Public Route filter. Du måste utvärdera upprättandet av sådana anslutningar för båda dessa funktioner. Office 365 informations skydd-teamet känner till det här problemet och arbetar aktivt för att få support för Azure ExpressRoute för Office 365 som begränsat till Office 365-väg filter för båda dessa funktioner.

- Det finns fler valfria slut punkter för Microsoft 365-appar för företag som inte är listade och som inte behövs för att användare ska kunna starta Microsoft 365-appar för företags program och redigera dokument. Valfria slut punkter finns i Microsoft-datacenter och bearbetar, överför eller lagrar inte kunddata. Vi rekommenderar att användarnas anslutningar till dessa slut punkter dirigeras till Standardsvars gräns för Internet.

