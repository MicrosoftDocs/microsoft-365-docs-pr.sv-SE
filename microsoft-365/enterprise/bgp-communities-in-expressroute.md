---
title: Använda BGP-communities i ExpressRoute för Office 365 scenarier
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Lär dig hur du använder BGP-communities i Azure ExpressRoute för att hantera antalet IP-prefix och den bandbredd som krävs för Office 365 scenarier.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905218"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Använda BGP-communities i ExpressRoute för Office 365 scenarier

Anslutning till Office 365 med hjälp av Azure ExpressRoute baseras på BGP-annonsering av specifika IP-undernät som representerar nätverk där Office 365-slutpunkter distribueras. På grund av den globala Office 365 och antalet tjänster som utgör Office 365 behöver kunder ofta hantera de annonseringar som de accepterar på sitt nätverk. Minska antalet IP-undernät. Refererad till IP-prefix i resten av den här artikeln, i enlighet med terminologin för BGP-nätverkshantering, har följande slutmål för kunderna:
  
- Hantera antalet godkända annonserade **IP-prefix** – Kunder som har en intern nätverksinfrastruktur eller en nätverksoperatör som bara stöder ett begränsat antal IP-prefix och kunder som har en nätverksoperatör som tar ut avgifter för att acceptera prefix över ett begränsat antal kommer att vilja utvärdera det totala antalet prefix som redan annonseras till deras nätverk och välja vilka Office 365-program som passar bäst för ExpressRoute.

- **Hantera mängden bandbredd som krävs** på Azure ExpressRoute-kretsen – Kunder kanske vill kontrollera bandbreddskuvertningen av Office 365-tjänsterna över ExpressRoute-sökvägen respektive Internet-sökvägen. Det gör att kunderna kan reservera ExpressRoute-bandbredd för specifika program, till exempel Skype för företag och dirigera de återstående Office 365-programmen över Internet-sökvägen.

För att hjälpa kunder med detta Office 365 är IP-prefix som annonseras via ExpressRoute märkta med tjänstspecifika BGP-communityvärden som visas i exemplet nedan.
  
> [!NOTE]
> Du bör räkna med att viss nätverkstrafik som är kopplad till andra program kan ingå i communityvärdet. Det här är normalt så här det fungerar för en global programvara som är ett tjänsteerbjudande med delade tjänster och datacenter. Här har det minimerats där det är möjligt med tanke på de båda ovannämnda målen, hanteringen av antalet prefix och/eller bandbredden.

|**Tjänst**|**BGP-communityvärde**|**Kommentarer**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Innehåller Exchange och EOP-tjänster\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype för företag\*  <br/> |12076:5030  <br/> |Skype för företag Online& Microsoft Teams tjänster  <br/> |
|Andra Office 365 tjänster\*  <br/> |12076:5100  <br/> |Innehåller Azure Active Directory (scenarier för autentisering och katalogsynkronisering) Office 365 även portaltjänster  <br/> |
|\*Omfattningen av tjänstscenarier som ingår i ExpressRoute beskrivs i artikeln [Office 365 slutpunkter.](./urls-and-ip-address-ranges.md)  <br/> \*\*Ytterligare tjänster och BGP-communityvärden kan läggas till framöver. [Se den aktuella listan över BGP-communities.](/azure/expressroute/expressroute-routing)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Vilka är de vanligaste scenarierna för att använda BGP-communities?

Kunder kan använda BGP-communities för att reglera grupper med IP-prefix som accepteras av deras nätverk via Azure ExpressRoute och på så sätt påverka det totala antalet IP-prefix och den förväntade bandbreddskuvertering för vissa Office 365-tjänster. Det är viktigt att förstå att Office 365 måste ha internetbunden trafik oavsett om Azure ExpressRoute eller BGP-communities används. Följande tre scenarier är de vanligaste sätten att använda den här funktionen.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: Minimera antalet IP Office 365 prefix

Contoso Corporation är ett företag med 50 000 anställda som för närvarande använder Office 365 för Exchange Online och SharePoint Online. När Contoso granskar kraven för ExpressRoute fastställs dess nätverksenheter på många regionala platser som inte kan hantera routningstabellstorlekar på över 100 ytterligare routningsposter. Contoso granskade det totala antalet IP-prefix som ExpressRoute annonserade ut för hela uppsättningen Office 365-tjänster och kom fram till att det överträffar 100. För att hålla sig under de 100 ytterligare routeposterna omfattningar Contoso användningen av ExpressRoute för Office 365 till bara SharePoint Online BGP-communityvärdet, 12076:5020, som tas emot via ExpressRoute Microsoft-peering.

|**BGP-communitytagg som används**|**Funktioner som kan dirigeras över Azure ExpressRoute**|**Internetvägar krävs**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint &amp;Online-OneDrive för företag  <br/> | DNS-, &amp; CRL- CDN förfrågningar  <br/>  Alla andra Office 365-tjänster som inte specifikt stöds via Azure ExpressRoute  <br/>  Alla andra Microsoft-molntjänster  <br/>  Office 365, Office 365, &amp; autentisering Office i en webbläsare  <br/>  Exchange Online, Exchange Online Protection och Skype för företag Online  <br/> |

> [!NOTE]
> För att det ska gå att få ett lägre antal prefix för respektive tjänst kommer en minimal överlappning mellan tjänsterna att kvarstå. Detta är ett förväntat beteende.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: Användning av ExpressRoute och intern bandbredd till vissa Office 365 tjänster

Fabrikam Inc, ett stort multinationellt företag med ett distribuerat heterellt nätverk, är prenumerant på många Office 365 tjänster inklusive: Exchange Online, SharePoint Online och Skype för företag Online. Fabrikams interna routningsinfrastruktur kan hantera tusentals IP-prefix i sina routningstabeller. Fabrikam vill dock bara tillhandahålla ExpressRoute och intern bandbredd för Office 365-program som är mest känsliga för nätverksprestanda och använder sin befintliga Internetbandbredd för alla andra Office 365 program.
  
Därför omfattningar Fabrikam sin Azure ExpressRoute-bandbredd till bara Skype för företag Online BGP-communityvärdet, 12076:5030, som tas emot via ExpressRoute Microsoft-peering. Återstående nätverkstrafik som är kopplad till Office 365 fortsätter att använda de utgående internetpunkterna.

|**BGP-communitytagg som används**|**Funktioner som kan dirigeras över Azure ExpressRoute**|**Internetvägar krävs**|
|:-----|:-----|:-----|
|Skype för företag  <br/> (12076:5030)  <br/> |Skype SIP-signalering, nedladdningar, röst-, video- och skrivbordsdelning  <br/> | DNS-, &amp; CRL- CDN förfrågningar  <br/>  Alla andra Office 365-tjänster som inte specifikt stöds via Azure ExpressRoute  <br/>  Alla andra Microsoft-molntjänster  <br/>  Office 365, Office 365, &amp; autentisering Office i en webbläsare  <br/>  Skype för företag telemetri, Skype snabbtips för klienten, anslutning till offentliga snabbmeddelanden  <br/>  Exchange Online, Exchange Online Protection och SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: Azure ExpressRoute används endast för Office 365 tjänster

Kunden Woodgrove Bank använder sig av flera olika Microsoft-molntjänster, bland annat Office 365. Woodgrove Bank utvärderar sin nätverkskapacitet och nätverksförbrukning och beslutar att använda Azure ExpressRoute som primär väg för de Office 365 tjänsterna. Routningstabellerna har stöd för alla IP Office 365 prefix för Office 365 och Azure ExpressRoute-kretsarna som de har etablerat har stöd för allt projekterat behov av bandbredd och svarstid.
  
För att säkerställa att nätverkstrafik som är kopplad till andra Microsoft-molntjänster än Office 365 omfattar Woodgrove Bank användningen av ExpressRoute för Office 365 till alla IP-prefix som är märkta med Office 365-specifika BGP-communityvärden, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**BGP-communitytagg som används**|**Funktioner som kan dirigeras över Azure ExpressRoute**|**Internetvägar krävs**|
|:-----|:-----|:-----|
|Exchange, Skype för företag & Microsoft Teams, SharePoint och &amp; andra tjänster  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp;Exchange Online Exchange Online Protection  <br/> SharePoint &amp;Online-OneDrive för företag  <br/> Skype SIP-signalering, nedladdningar, röst-, video- och skrivbordsdelning  <br/> Office 365, Office 365, &amp; autentisering Office i en webbläsare  <br/> | DNS-, &amp; CRL- CDN förfrågningar  <br/>  Alla andra Office 365-tjänster som inte specifikt stöds via Azure ExpressRoute  <br/>  Alla andra Microsoft-molntjänster  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Viktiga överväganden vid planeringen av hur BGP-communities ska används

Kunder som väljer att dra nytta av BGP-communities för att påverka hur ExpressRoute annonseras ut och sprids i kundnätverket bör ta hänsyn till följande:
  
- När du använder BGP-communities i din nätverksutformning är det viktigt att se till att bibehålla routesymmetrin. I vissa fall skapar tillägg och borttagning av BGP-communities en situation där den symmetriska routningen bryts och routningskonfigurationen måste uppdateras för att återställa den symmetriska dirigeringen.

- Det är kunden som förser Scoping Azure ExpressRoute med BGP-communityvärden. Microsoft annonserar alla IP-prefix som är kopplade till peeringrelationen oavsett hur mycket som konfigureras av kunden.

- Azure ExpressRoute stöder inte åtgärder i Microsofts nätverk baserat på kundens tilldelade BGP-communities.

- De IP-prefix som används Office 365 bara markeras med tjänstspecifika BGP-communityvärden, platsspecifika BGP-communities stöds inte. Office 365 tjänster är globala till sin natur stöds inte filtrering av prefix baserat på klientorganisationens plats eller data i Office 365 moln. Det rekommenderade sättet är att konfigurera nätverket så att det koordinerar den kortaste eller mest prioriterade nätverkssökvägen från användarens nätverksplats till Microsofts globala nätverk, oavsett den fysiska platsen för IP-adressen för den Office 365-tjänst som begärs av användaren.

- DE IP-prefix som ingår i varje BGP-communityvärde representerar ett undernät som innehåller IP-adresser för det Office 365 program som är kopplat till värdet. I vissa fall har flera Office 365 IP-adresser i ett undernät som resulterar i ett IP-prefix som finns i fler än ett community-värde. Detta är normalt, men sällan på grund av en uppdelning av tilldelning och påverkar inte antalet prefix eller mål för bandbreddshantering. Kunderna uppmanas att använda metoden "tillåt vad som behövs" i motsats till "neka vad som inte behövs" när de utnyttjar BGP-communities för Office 365 för att minimera effekten.

- Användningen av BGP-communities ändrar inte de underliggande nätverksanslutningskrav eller den konfiguration som krävs för att använda Office 365. Kunder som vill ha Office 365 måste fortfarande kunna komma åt Internet.

- Att använda Azure ExpressRoute med BGP-communities påverkar bara de vägar det interna nätverket kan se över Microsoft-peeringrelationen. Du kan behöva göra ytterligare konfigurationer på programnivån, till exempel att använda en PAC- eller WPAD-konfiguration i samband med den begränsade routningen.

- Utöver att använda Microsofts tilldelade BGP-communities kan kunder välja att tilldela egna BGP-communities till Office 365 IP-prefix som lärts via Azure ExpressRoute för att påverka intern routning. Ett populärt användningsfall är att tilldela en platsbaserad BGP-community till alla vägar som lärts via de angivna ExpressRoute-peeringplatserna och sedan använda informationen nedåt i kundnätverket för att koordinera den kortaste eller mest prioriterade nätverkssökvägen till Microsofts nätverk. Hur kundtilldej terna BGP-communities används med ExpressRoute för Office 365 är utanför Microsofts kontroll eller synlighet.

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/bgpexpressroute365]() .
  
## <a name="related-topics"></a>Relaterade ämnen

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365 anslutning](managing-expressroute-for-connectivity.md)
  
[Dirigering med ExpressRoute för Office 365](routing-with-expressroute.md)
  
[Nätverksplanering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
  
[Prestanda för mediekvalitet och nätverksanslutning i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute och QoS i Skype för företag Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtalsflöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Stöd för BGP-communities](/azure/expressroute/expressroute-routing)
  
[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).
  
[Azure ExpressRoute för Office 365 utbildning](https://channel9.msdn.com/series/aer)