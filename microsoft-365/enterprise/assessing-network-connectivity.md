---
title: Utvärdera Microsoft 365 nätverksanslutningar
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 har utformats för att kunder i hela världen ska kunna ansluta till tjänsten via en Internetanslutning. I takt med att tjänsten utvecklas förbättras säkerheten, prestanda och tillförlitligheten i Microsoft 365 baserat på kunder som använder Internet för att upprätta en anslutning till tjänsten.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905482"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Utvärdera Microsoft 365 nätverksanslutningar

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 har utformats för att kunder i hela världen ska kunna ansluta till tjänsten via en Internetanslutning. I takt med att tjänsten utvecklas förbättras säkerheten, prestanda och tillförlitligheten i Microsoft 365 baserat på kunder som använder Internet för att upprätta en anslutning till tjänsten.
  
Kunder som planerar att Microsoft 365 bör utvärdera befintliga och prognostiserade anslutningsbehov som en del av distributionsprojektet. För distributioner i företagsklass är en pålitlig Internetanslutning med lämplig storlek en viktig del av användningen Microsoft 365 funktioner och scenarier.
  
Nätverksutvärderingar kan utföras av många olika personer och organisationer beroende på din storlek och dina inställningar. Utvärderingens omfattning kan också variera beroende på var du är i distributionsprocessen. För att hjälpa dig att få bättre förståelse för vad som krävs för en nätverksutvärdering har vi tagit fram en nätverksutvärderingsguide som hjälper dig att förstå de tillgängliga alternativen. Den här utvärderingen avgör vilka steg och resurser som måste läggas till i distributionsprojektet för att du ska kunna införa Microsoft 365.
  
En omfattande nätverksutvärdering kommer att tillhandahålla möjliga lösningar på problem med nätverksdesign tillsammans med implementeringsinformation. Vissa nätverksutvärderingar visar att optimal nätverksanslutning till Microsoft 365 kan tillgodoses med mindre konfigurations- eller designändringar av den befintliga internet- och nätverksinfrastrukturen för utgående trafik.

Vissa utvärderingar indikerar att nätverksanslutningen till Microsoft 365 kräver ytterligare investeringar i nätverkskomponenter. Till exempel kan företagsnätverk som spänner över filialer och flera geografiska regioner kräva investeringar i SD-WAN-lösningar eller optimerad routningsinfrastruktur för att stödja Internetanslutningen till Microsoft 365. Ibland kan en utvärdering ange att nätverksanslutningen till Microsoft 365 påverkas av bestämmelser eller prestandakrav för scenarier [som Skype för företag mediekvaliteten online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Dessa ytterligare krav kan leda till investeringar i infrastrukturen för Internetanslutningar, optimering av nätverksroutning och särskild direktanslutning.

Några resurser som hjälper dig att utvärdera nätverket:

- Se [Microsoft 365 översikt över nätverksanslutningen för](microsoft-365-networking-overview.md) konceptuell information om Microsoft 365 nätverk.
- Se [Microsoft 365 för nätverksanslutningsprinciper](./microsoft-365-network-connectivity-principles.md) för att förstå anslutningsprinciperna för säker hantering Microsoft 365 trafik och få bästa möjliga prestanda.
- Registrera dig för [Microsoft FastTrack för](https://www.microsoft.com/fasttrack) guidad hjälp med Microsoft 365, design och distribution. 
- I avsnittet [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) anslutningstest nedan kan du köra grundläggande anslutningstester som innehåller specifik vägledning om förbättringar av nätverksanslutningen som kan göras mellan en viss användarplats och en Microsoft 365.

> [!NOTE]
> Microsoft-auktorisering krävs för att använda ExpressRoute för Office 365. Microsoft granskar alla kundförfrågningar och godkänner bara ExpressRoute för Office 365 användning när en kunds föreskrifter kräver direkt anslutning. Om du har sådana krav kan du skicka textutdrag och webblänk till förordningen som du tolkar för att innebära att direkt anslutning krävs i [ExpressRoute](https://aka.ms/O365ERReview) för Office 365 Begär formulär för att påbörja en Microsoft-granskning. Obehöriga prenumerationer som försöker skapa routefilter för Office 365 får [ett felmeddelande.](https://support.microsoft.com/kb/3181709)
  
Viktiga punkter att tänka på när du planerar en nätverksutvärdering för Microsoft 365:
  
- Microsoft 365 är en säker och tillförlitlig tjänst med höga prestanda som körs på det offentliga Internet. Vi fortsätter att investera för att förbättra dessa aspekter av tjänsten. Alla Microsoft 365 är tillgängliga via internetanslutning.

- Vi optimerar kontinuerligt viktiga aspekter av Microsoft 365 som tillgänglighet, global räckvidd och prestanda för Internetbaserad anslutning. Exempelvis använder många Microsoft 365 av en växande uppsättning edge-noder mot Internet. Detta gränsnätverk erbjuder bästa möjliga närhet och prestanda för anslutningar via Internet.

- Kunder som överväger att använda Microsoft 365 med någon av tjänsterna som ingår, till exempel Teams eller Skype för företag Online röst-, video- eller mötesfunktioner, bör genomföra en nätverksutvärdering från ända till slutet och uppfylla anslutningskraven med [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Om du utvärderar Microsoft 365 och inte är säker på var du ska börja med nätverksutvärderingen eller har hittat utmaningar med nätverksdesignen som du måste hantera bör du kontakta Microsoft-kontoteamet.

## <a name="the-microsoft-365-connectivity-test"></a>Test Microsoft 365 anslutningstest

[Anslutningstestet Microsoft 365](https://aka.ms/netonboard) är ett poc-nätverksutvärderingsverktyg (Proof of Concept) som kör grundläggande anslutningstester mot Microsoft 365-klienten och som gör specifika rekommendationer för nätverksdesign för optimal Microsoft 365 prestanda. Verktyget framhäver vanliga designval för företagsnätverksdesign som är användbara för internetsurfning men påverkar prestandan för stora SaaS-program som Microsoft 365.

Verktyget nätverks onboarding gör följande:

- Identifierar din plats eller så kan du ange en plats att testa
- Kontrollerar platsen för nätverkets utgående position
- Testar nätverkssökvägen till närmaste Microsoft 365 fronten
- Tillhandahåller avancerade tester med hjälp av ett nedladdningsbart Windows 10 program som gör att rekommendationer för perimeternätverksdesign relaterat till proxyservrar, brandväggar och DNS. Verktyget kör även prestandatester för Skype för företag Online, Microsoft Teams, SharePoint Online och Exchange Online.

Verktyget består av två komponenter: ett webbläsarbaserat användargränssnitt som samlar in grundläggande anslutningsinformation och ett hämtningsbart Windows 10-program som kör avancerade tester och returnerar ytterligare utvärderingsdata.

I det webbläsarbaserade verktyget visas följande information:

- Fliken Resultat och påverkan
  - Platsen på en karta över tjänstportporten
  - Platsen på en karta över andra tjänste dörrar fram som ger optimal anslutning
  - Relativ prestanda jämfört med andra Microsoft 365 nära dig
- Fliken Information och lösningar
  - Användarplats efter stad och land
  - Nätverkets utgående plats efter stad, delstat och land
  - Användare till nätverkets utgående avstånd
  - Microsoft 365 Exchange Online serviceplats vid fronten
  - Optimal Microsoft 365 Exchange Online tjänst före användarnas plats
  - Kunder i din metro-område med bättre prestanda

Det nedladdningsbara programmet Advanced Tests ger följande ytterligare information:

- Fliken Information och lösningar (tillagd)
  - Användarens standardgateway
  - DNS-klientserver
  - Klient-DNS Rekursiv resolver
  - Exchange Online DNS-server
  - SharePoint DNS-server online
  - Proxyserveridentifiering
  - Kontroll av medieanslutningar
  - Paketförlust för mediakvalitet
  - Svarstid för mediekvalitet
  - Mediekvalitetsjitter
  - Omsortering av mediakvalitetspaket
- Anslutningstester till flera funktionsspecifika slutpunkter
- Diagnostik för nätverkssökväg som innehåller tracert- och svarstidsdata för Exchange Online, SharePoint Online Teams tjänsten

Du kan läsa om Microsoft 365 anslutningstest och ge feedback på blogginlägget om Microsoft 365-anslutningstest [med](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) nya rekommendationer om nätverksdesign. Information om kommande uppdateringar av verktyget och andra Microsoft 365 och nätverksuppdateringar kommer att publiceras [på Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) Blog.
  
Här är en kort länk som du kan använda för att komma tillbaka: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Relaterade ämnen

[Översikt för Microsoft 365 nätverksanslutning](microsoft-365-networking-overview.md)

[Microsoft 365 Principer för nätverksanslutning](./microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Microsoft 365 nätverks- och prestandajustering](network-planning-and-performance.md)

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)