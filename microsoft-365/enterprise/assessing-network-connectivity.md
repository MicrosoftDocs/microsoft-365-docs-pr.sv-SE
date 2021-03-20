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
  
Kunder som planerar att använda Microsoft 365 bör utvärdera befintliga och prognostiserade anslutningsbehov som en del av distributionsprojektet. För distributioner i företagsklass är en pålitlig Internetanslutning med lämplig storlek viktig del i användningen av Microsoft 365-funktioner och -scenarier.
  
Nätverksutvärderingar kan utföras av många olika personer och organisationer beroende på din storlek och dina inställningar. Utvärderingens omfattning kan också variera beroende på var du är i distributionsprocessen. För att hjälpa dig att få bättre förståelse för vad som krävs för en nätverksutvärdering har vi tagit fram en nätverksutvärderingsguide som hjälper dig att förstå de tillgängliga alternativen. Den här utvärderingen avgör vilka steg och resurser som måste läggas till i distributionsprojektet för att du ska kunna använda Microsoft 365 utan problem.
  
En omfattande nätverksutvärdering kommer att tillhandahålla möjliga lösningar på problem med nätverksdesign tillsammans med implementeringsinformation. Vissa nätverksutvärderingar visar att optimala nätverksanslutning till Microsoft 365 kan tillgodoses med mindre konfigurations- eller designändringar av den befintliga internet- och nätverksinfrastrukturen för utgående trafik.

Vissa utvärderingar indikerar att nätverksanslutningen till Microsoft 365 kräver ytterligare investeringar i nätverkskomponenter. Till exempel kan företagsnätverk som spänner över filialer och flera geografiska regioner kräva investeringar i SD-WAN-lösningar eller optimerad routningsinfrastruktur för att stödja Internetanslutning till Microsoft 365. Ibland påverkas en utvärdering av att nätverksanslutningen till Microsoft 365 påverkas av bestämmelser eller prestandakrav för scenarier som mediakvalitet för Skype för [företag – Online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Dessa ytterligare krav kan leda till investeringar i infrastrukturen för Internetanslutningar, optimering av nätverksroutning och särskild direktanslutning.

Några resurser som hjälper dig att utvärdera nätverket:

- Se [Översikt över Microsoft 365-nätverksanslutning för](microsoft-365-networking-overview.md) konceptuell information om Microsoft 365-nätverk.
- Se [Principer för Microsoft 365-nätverksanslutning](./microsoft-365-network-connectivity-principles.md) för att förstå anslutningsprinciperna för säker hantering av Microsoft 365-trafik och få bästa möjliga prestanda.
- Registrera dig för [Microsoft FastTrack för](https://www.microsoft.com/fasttrack) guidad hjälp med planering, utformning och distribution av Microsoft 365. 
- Se [Microsoft 365-anslutningstest](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) nedan om du vill köra grundläggande anslutningstester som innehåller specifik vägledning om förbättringar av nätverksanslutningar som kan göras mellan en viss användarplats och Microsoft 365.

> [!NOTE]
> Microsoft-auktorisering krävs för att använda ExpressRoute för Office 365. Microsoft granskar alla kundförfrågningar och godkänner bara ExpressRoute för Office 365-användning när en kunds föreskrifter kräver direkt anslutning. Om du har sådana krav kan du skicka textutdrag och webblänk till förordningen som du tolkar som att direkt anslutning krävs i ExpressRoute för [Office 365-begäran](https://aka.ms/O365ERReview) för att påbörja en Microsoft-granskning. Obehöriga prenumerationer som försöker skapa routefilter för Office 365 får [ett felmeddelande.](https://support.microsoft.com/kb/3181709)
  
Viktiga punkter att tänka på när du planerar din nätverksutvärdering för Microsoft 365:
  
- Microsoft 365 är en säker och tillförlitlig tjänst med höga prestanda som körs på det offentliga Internet. Vi fortsätter att investera för att förbättra dessa aspekter av tjänsten. Alla Microsoft 365-tjänster är tillgängliga via internetanslutning.

- Vi optimerar kontinuerligt viktiga aspekter av Microsoft 365 som tillgänglighet, global räckvidd och prestanda för Internetbaserad anslutning. Exempelvis utnyttjar många Microsoft 365-tjänster en växande uppsättning edge-noder mot Internet. Detta gränsnätverk erbjuder bästa möjliga närhet och prestanda för anslutningar via Internet.

- Kunder som överväger att använda Microsoft 365 med någon av tjänsterna som ingår, till exempel röst-, video- eller mötesfunktionerna i Skype för företag – Online, bör genomföra en nätverksutvärdering från ända till slutet och uppfylla anslutningskraven med [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Om du utvärderar Microsoft 365 och inte är säker på var du ska börja med nätverksutvärderingen eller har hittat utmaningar med nätverksdesignen som du måste hantera bör du kontakta Microsoft-kontoteamet.

## <a name="the-microsoft-365-connectivity-test"></a>Anslutningstest för Microsoft 365

[Microsoft 365-anslutningstestet](https://aka.ms/netonboard) är ett poc-nätverksutvärderingsverktyg (Proof of Concept) som kör grundläggande anslutningstester mot Microsoft 365-klienten och som gör specifika rekommendationer om nätverksdesign för optimal Microsoft 365-prestanda. Verktyget markerar de vanligaste alternativen för perimeterdesign för företagsnätverk som är användbara för internetsurfning men påverkar prestandan i stora SaaS-program som Microsoft 365.

Verktyget nätverks onboarding gör följande:

- Identifierar din plats eller så kan du ange en plats att testa
- Kontrollerar platsen för nätverkets utgående position
- Testar nätverkssökvägen till närmaste Microsoft 365-tjänst front dörr
- Tillhandahåller avancerade tester med ett nedladdningsbart Windows 10-program som gör att rekommendationer för perimeternätverksdesign rekommendationer relaterade till proxyservrar, brandväggar och DNS. Verktyget kör även prestandatester för Skype för företag – Online, Microsoft Teams, SharePoint Online och Exchange Online.

Verktyget består av två komponenter: ett webbläsarbaserat användargränssnitt som samlar in grundläggande anslutningsinformation och ett nedladdningsbart Windows 10-program som kör avancerade tester och returnerar ytterligare utvärderingsdata.

I det webbläsarbaserade verktyget visas följande information:

- Fliken Resultat och påverkan
  - Platsen på en karta över tjänstportporten
  - Platsen på en karta över andra tjänste dörrar fram som ger optimal anslutning
  - Relativ prestanda jämfört med andra Microsoft 365-kunder nära dig
- Fliken Information och lösningar
  - Användarplats efter stad och land
  - Nätverkets utgående plats efter stad, delstat och land
  - Användare till nätverkets utgående avstånd
  - Microsoft 365 Exchange Online-tjänstens framsida
  - Optimal Microsoft 365 Exchange Online-tjänst hos användarna
  - Kunder i din metro-område med bättre prestanda

Det nedladdningsbara programmet Advanced Tests ger följande ytterligare information:

- Fliken Information och lösningar (tillagd)
  - Användarens standardgateway
  - DNS-klientserver
  - Klient-DNS Rekursiv resolver
  - DNS-server för Exchange Online
  - SHAREPoint Online DNS-server
  - Proxyserveridentifiering
  - Kontroll av medieanslutningar
  - Paketförlust för mediakvalitet
  - Svarstid för mediekvalitet
  - Mediekvalitetsjitter
  - Omsortering av mediakvalitetspaket
- Anslutningstester till flera funktionsspecifika slutpunkter
- Diagnostik för nätverkssökväg som innehåller spårnings- och svarstidsdata för Exchange Online-, SharePoint Online- och Teams-tjänsterna

Du kan läsa om Microsoft 365-anslutningstestet och ge feedback på den uppdaterade bloggposten om [Microsoft 365-anslutningstest](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) med rekommendationer om nätverksdesign. Information om kommande uppdateringar av verktyget och andra Microsoft 365-nätverksuppdateringar kommer att publiceras på [Office 365-nätverksbloggen.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Här är en kort länk som du kan använda för att komma tillbaka: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Relaterade ämnen

[Översikt för Microsoft 365 nätverksanslutning](microsoft-365-networking-overview.md)

[Microsoft 365-nätverksanslutningsprinciper](./microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Nätverks- och prestandajustering för Microsoft 365](network-planning-and-performance.md)

[Microsoft 365 Enterprise – översikt](microsoft-365-overview.md)