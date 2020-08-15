---
title: Azure ExpressRoute för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Lär dig att använda Azure ExpressRoute med Office 365 och planera nätverks implementerings projektet om du distribuerar det.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694308"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute för Office 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Lär dig hur Azure ExpressRoute används med Office 365 och hur du planerar det nätverks implementerings projekt som krävs om du distribuerar Azure ExpressRoute för användning med Office 365. Infrastruktur-och plattforms tjänster som körs i Azure kan ofta utnyttja för att adressera nätverks arkitektur och prestanda. Vi rekommenderar ExpressRoute för Azure i de här fallen. Program vara som service offerter som Office 365 och Dynamics 365 har byggts för åtkomst till säkert och tillförlitligt via Internet. Du kan läsa om Internet prestanda och säkerhet och när du kan betrakta Azure ExpressRoute för Office 365 i artikeln om att [kontrol lera nätverks anslutningen för office 365](assessing-network-connectivity.md).

> [!NOTE]
> Microsoft Authorization krävs för att använda ExpressRoute för Office 365. Microsoft granskar varje kund förfrågan och auktoriserar ExpressRoute för Office 365-användning när en kunds reglerings krav styr direkt anslutning. Om du har sådana krav måste du ange textutdraget och webb länken till den förordning som du tolkar som att det är direkt anslutnings barhet som krävs i [ExpressRoute för Office 365 för](https://aka.ms/O365ERReview) att påbörja en granskning av Microsoft. Obehöriga abonnemang försöker skapa väg filter för Office 365 att få ett [fel meddelande](https://support.microsoft.com/kb/3181709).

Du kan nu lägga till en direkt nätverks anslutning till Office 365 för vald Office 365-nätverks trafik. Azure ExpressRoute erbjuder en direkt anslutning, förutsägbar prestanda och har ett tids periods SLA för 99,95% för Microsoft-nätverks komponenter. Du behöver fortfarande en Internet anslutning för tjänster som inte stöds via Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Planera Azure ExpressRoute för Office 365

Utöver Internet anslutning kan du välja att dirigera en delmängd av sin Office 365-nätverks trafik via en direkt anslutning som ger enastående och en drift tid på 99,95% för Microsoft-nätverksklienter. Azure ExpressRoute ger dig den här dedicerade nätverks anslutningen till Office 365 och andra moln tjänster från Microsoft.

Oavsett om du har en befintlig MPLS WAN kan ExpressRoute läggas till i nätverks arkitekturen på ett av tre sätt: via en Cloud Exchange Co-location-leverantör som stöds, en Ethernet Point-to-point-anslutning eller via en MPLS. Se vilka [leverantörer som är tillgängliga i din region](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Den direkta ExpressRoute anslutningen gör det möjligt att ansluta till programmen som beskrivs i [vilka Office 365-tjänster som ingår?](azure-expressroute.md#BKMK_WhatDoIGet) nedan. Nätverks trafik för alla andra program och tjänster fortsätter att gå över till Internet.

Tänk på följande nätverks diagram med hög nivå som visar en typisk Office 365-kund som ansluter till Microsofts Data Center via Internet för att få till gång till alla Microsoft-program, till exempel Office 365, Windows Update och TechNet. Kunder använder en liknande nätverks Sök väg oavsett om de ansluter från ett lokalt nätverk eller från en oberoende Internet anslutning.

![Office 365 nätverks anslutning](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Titta på det uppdaterade diagrammet som visar en Office 365-kund som använder både Internet-och ExpressRoute för att ansluta till Office 365. Observera att vissa anslutningar som offentliga DNS-och Content-Network-noder kräver ändå den offentliga Internet anslutningen. Observera också att kundens användare inte är placerade i sin ExpressRoute anslutna byggnad ansluter via Internet.

![Office 365-anslutning med ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Vill du fortfarande ha mer information? Lär dig hur du [hanterar nätverks trafiken med Azure ExpressRoute för office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) och hur du [konfigurerar Azure ExpressRoute för Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Vi har också spelat in en 10-part [för Azure ExpressRoute for Office 365-utbildning](https://channel9.msdn.com/series/aer) på kanal 9 för att beskriva begreppen mer noggrant.

## <a name="what-office-365-services-are-included"></a>Vilka Office 365-tjänster ingår?
<a name="BKMK_WhatDoIGet"> </a>

I följande tabell finns de Office 365-tjänster som stöds via ExpressRoute. Läs artikeln om [Office 365-slutpunkter](https://aka.ms/o365endpoints) för att förstå vilka nätverks förfrågningar för dessa program som kräver Internet anslutning.

|**Program som ingår**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype för företag – Online<sup>1</sup> <br/> Microsoft team <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive för företag<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal och delad<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> de här programmen har Internet anslutnings krav som inte stöds av ExpressRoute, finns i [artikeln Office 365-slut punkter](https://aka.ms/o365endpoints) för att få mer information.

Tjänsterna som inte ingår i ExpressRoute för Office 365 är Microsoft 365-appar för Enterprise-klient-ladda ned, lokal identitets leverantör inloggning och Office 365 (drivs av 21 Vianet) service i Kina.

## <a name="implementing-expressroute-for-office-365"></a>Implementera ExpressRoute för Office 365

Implementering av ExpressRoute kräver att nätverks-och program ägare deltar och att du måste planera för att fastställa den nya [arkitekturen för nätverks dirigering](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandbredds krav, var säkerheten implementeras, hög tillgänglighet och så vidare. För att implementera ExpressRoute måste du:

1. Helt förstå behovet ExpressRoute uppfyller kraven för att planera din Office 365-anslutning. Förstå vilka program som kommer att använda Internet eller ExpressRoute och fullt ut planera nätverks kapacitet, säkerhet och lättillgängliga behov i samband med användning av både Internet och ExpressRoute för Office 365-trafik.

2. Fastställ utgångs-och peering-platser för både Internet-och ExpressRoute trafik<sup>1</sup>.

3. Fastställ vilken kapacitet som behövs för Internet-och ExpressRoute-anslutningar.

4. Ha en plan för att implementera säkerhet och andra standard gräns kontroller<sup>1</sup>.

5. Ha ett giltigt Microsoft Azure-konto för att abonnera på ExpressRoute.

6. Välj en anslutnings modell och en [godkänd leverantör](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Kom ihåg att kunder kan välja flera anslutnings modeller eller partners och att partnern inte behöver vara samma som din befintliga nätverks leverantör.

7. Verifiera distributionen innan du dirigerar trafik till ExpressRoute.

8. Implementera eventuellt [QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) och utvärdera regional expansion.

<sup>1</sup> viktig information om prestanda. Beslut här kan dramatiskt påverka svars tiden som är viktig för program som Skype för företag.

Mer information finns i vår [Guide för routning](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) utöver [ExpressRoute dokumentation](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

För att kunna köpa ExpressRoute för Office 365 måste du arbeta med en eller flera [godkända leverantörer](https://azure.microsoft.com/documentation/articles/expressroute-locations/) för att tillhandahålla önskat nummer och storleks kretsar med en ExpressRoute Premium-prenumeration. Det finns inga ytterligare licenser att köpa från Office 365.

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Är du redo att registrera dig för [ExpressRoute för Office 365](https://aka.ms/ert)?

## <a name="related-topics"></a>Närliggande ämnen

[Utvärdering av Office 365 nätverks anslutning](assessing-network-connectivity.md)

[Hantera ExpressRoute för Office 365](managing-expressroute-for-connectivity.md)

[Routning med ExpressRoute för Office 365](routing-with-expressroute.md)

[Nätverks planering med ExpressRoute för Office 365](network-planning-with-expressroute.md)

[Implementera ExpressRoute för Office 365](implementing-expressroute.md)

[Använda BGP-communities i ExpressRoute för Office 365](bgp-communities-in-expressroute.md)

[Media kvalitet och nätverks anslutnings prestanda i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Prestanda justering för Office 365 med bas linjer och prestanda historik](performance-tuning-using-baselines-and-history.md)

[Plan för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Office 365-nätverks-och prestanda inställning](network-planning-and-performance.md)

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
