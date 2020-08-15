---
title: Utvärderar Microsoft 365-nätverksanslutningar
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
description: Microsoft 365 är utformat för att göra det möjligt för kunder över hela världen att ansluta till tjänsten via en Internet anslutning. Allteftersom tjänsten utvecklas förbättras säkerheten, prestandan och tillförlitligheten hos Microsoft 365 utifrån kunder som använder Internet för att upprätta en anslutning till tjänsten.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694714"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Utvärderar Microsoft 365-nätverksanslutningar

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 är utformat för att göra det möjligt för kunder över hela världen att ansluta till tjänsten via en Internet anslutning. Allteftersom tjänsten utvecklas förbättras säkerheten, prestandan och tillförlitligheten hos Microsoft 365 utifrån kunder som använder Internet för att upprätta en anslutning till tjänsten.
  
För att du ska kunna använda Microsoft 365 bör du bedöma befintliga och prognostiserade Internet anslutnings behov som en del av distributions projektet. För företags klass distributioner är pålitlig och lämplig och lämpligt med Internet anslutning en viktig del i att konsumera Microsoft 365-funktioner och-scenarion.
  
Nätverks utvärderingar kan utföras av många olika personer och organisationer beroende på din storlek och dina preferenser. Utvärderingens nätverks omfång kan även variera beroende på var i distributionen du befinner dig. För att hjälpa dig att få en bättre förståelse för vad det tar att utföra en nätverks utvärdering har vi skapat en nätverks utvärderings guide som hjälper dig att förstå de alternativ som är tillgängliga för dig. Denna utvärdering avgör vilka steg och resurser som måste läggas till i distributions projektet för att du ska kunna använda Microsoft 365.
  
En omfattande nätverks utvärdering ger eventuella lösningar för nätverks design utmaningar tillsammans med implementerings uppgifter. Vissa nätverks utvärderingar visar att optimal nätverks anslutning till Microsoft 365 kan anpassas med mindre konfiguration eller design ändringar i befintliga nätverks-och Internetbaserade infrastrukturer.

Vissa utvärderingar indikerar nätverks anslutningen till Microsoft 365 kräver ytterligare investeringar i nätverks komponenter. Företags nätverk som omfattar filial kontor och flera geografiska regioner kan till exempel kräva investeringar i SD-WAN-lösningar eller optimerad infrastruktur för att stödja Internet anslutningen till Microsoft 365. Ibland indikerar en utvärdering att nätverks anslutningen till Microsoft 365 påverkas av regler eller prestanda krav för scenarier som [Skype för företag – Online medie kvalitet](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). Dessa ytterligare krav kan leda till placeringar i infrastrukturen för Internet anslutning, optimering av Routning och särskild direkt anslutning.

Vissa resurser som hjälper dig att utvärdera nätverket:

- Information om Microsoft 365-nätverk finns i [Översikt över microsoft 365-nätverk](microsoft-365-networking-overview.md) .
- Se [microsoft 365 Network Connectivity-principer](https://aka.ms/o365networkingprinciples) för att förstå anslutnings principerna för säker hantering av Microsoft 365-trafik och bästa möjliga prestanda.
- Registrera dig för [Microsoft FastTrack](https://www.microsoft.com/fasttrack) om du behöver hjälp med Microsoft 365 planering, design och distribution. 
- Se avsnittet [Microsoft 365 Connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) nedan för att köra grundläggande anslutnings test med specifika råd om förbättringar av nätverks anslutningar som kan göras mellan en viss webbplats och Microsoft 365.

> [!NOTE]
> Microsoft Authorization krävs för att använda ExpressRoute för Office 365. Microsoft granskar varje kund förfrågan och godkänner endast ExpressRoute för Office 365-användning när en kunds reglerings krav styr direkt anslutningen. Om du har sådana krav måste du ange textutdraget och webb länken till den förordning som du tolkar som att det är direkt anslutnings barhet som krävs i [ExpressRoute för Office 365 för](https://aka.ms/O365ERReview) att påbörja en granskning av Microsoft. Obehöriga abonnemang försöker skapa väg filter för Office 365 att få ett [fel meddelande](https://support.microsoft.com/kb/3181709).
  
Viktiga saker du bör tänka på när du planerar nätverks utvärdering för Microsoft 365:
  
- Microsoft 365 är en säker, pålitlig, högpresterande tjänst som körs över Internet. Vi fortsätter att investera för att förbättra dessa aspekter av tjänsten. Alla Microsoft 365-tjänster är tillgängliga via Internet anslutning.

- Vi optimerar kontinuerligt de grundläggande aspekterna av Microsoft 365, till exempel tillgänglighet, globala funktioner och prestanda för Internetbaserade anslutningar. Många Microsoft 365-tjänster har till exempel en utökande uppsättning med interaktivitet med Internet. Det här Edge-nätverket ger bästa möjliga närhet och prestanda för anslutningar via Internet.

- När du funderar på att använda Microsoft 365 för någon av de inkluderade tjänsterna, till exempel Teams eller Skype för företag – Online röst-, video-och mötes kapacitet, bör kunderna fylla på för nätverks utvärdering och uppfylla anslutnings kraven via [Microsoft FastTrack](https://www.microsoft.com/fasttrack).

Om du utvärderar Microsoft 365 och inte vet var du ska börja med din nätverks utvärdering eller har hittat problem med nätverks design som du behöver hjälp med att lösa kan du arbeta med ditt Microsoft-konto team.

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 Connectivity-test

[Microsoft 365 Connectivity test](https://aka.ms/netonboard) är ett POC-verktyg (proof of Concept) för nätverk med grundläggande anslutnings barhet för din Microsoft 365-klient organisation och gör specifika nätverks design rekommendationer för optimal Microsoft 365-prestanda. Verktyget markerar vanliga alternativ för företags nätverks perimeter som är användbara för Internet-surfning men påverkar prestandan hos stora SaaS-program, till exempel Microsoft 365.

Verktyget nätverks registrering gör följande:

- Identifierar din plats, eller så kan du ange en plats att testa
- Kontrollerar placeringen av nätverket
- Testar nätverks Sök vägen till närmaste Microsoft 365-tjänstens främre dörr
- Ger avancerade test med en nedladdnings bar Windows 10-tillämpning som gör det enklare att utforma nätverks rekommendationer relaterade till proxyservrar, brand väggar och DNS. Verktyget kör dessutom prestanda test för Skype för företag – Online, Microsoft Teams, SharePoint Online och Exchange Online.

Verktyget har två komponenter: ett webbläsarbaserat gränssnitt som samlar in grundläggande anslutnings information och en nedladdnings bar Windows 10-tillämpning som kör avancerade test och returnerar ytterligare utvärderings data.

Det webbläsarbaserade verktyget visar följande information:

- Fliken resultat och effekter
  - Platsen på en karta över den tjänst främre dörren
  - Platsen på en karta över andra tjänst front dörrar som ger optimal anslutning
  - Relativ prestanda jämfört med andra Microsoft 365-kunder nära dig
- Fliken information och lösningar
  - Användarens plats efter ort och land
  - Utgångs plats för nätverk efter ort, delstat och land
  - Användare till utgående nätverk
  - Start dörr plats för Microsoft 365 Exchange Online
  - Optimal Microsoft 365 Exchange Online-tjänstens front dörr (ar) för användarens plats
  - Kunder i din tunnelbane yta med bättre prestanda

Det avancerade test nedladdnings programmet innehåller följande information:

- Fliken information och lösningar (lades till)
  - Användarens standardgateway
  - Klient-DNS-Server
  - Klient DNS-rekursiv lösare
  - Exchange Online DNS-Server
  - SharePoint Online DNS-Server
  - Proxyserver-identifiering
  - Medie anslutnings kontroll
  - Paket förlust för medie kvalitet
  - Svars tid för medie kvalitet
  - Medie kvalitets Darr
  - Omordning för medie kvalitets paket
- Anslutnings test till flera funktions slut punkter
- Nätverksdiagnostik för nätverks Sök vägar som innehåller tracert-och svars tid för Exchange Online, SharePoint Online och Teams Services

Du kan läsa om Microsoft 365 Connectivity test och ge feedback vid den [uppdaterade test POC för microsoft 365-anslutning med nya blogg inlägg för nätverks design](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) . Information om framtida uppdateringar av verktyget och andra Microsoft 365-nätverks uppdateringar kommer att publiceras på [Office 365-nätverks](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) bloggen.
  
Här är en kort länk som du kan använda för att komma tillbaka: [ https://aka.ms/o365networkconnectivity .](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Relaterade ämnen

[Översikt över Microsoft 365-nätverk](microsoft-365-networking-overview.md)

[Principer för nätverks åtkomst för Microsoft 365](https://aka.ms/o365networkingprinciples)

[Hantera slut punkter för Office 365](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[IP-adress och URL för Office 365](microsoft-365-ip-web-service.md)

[Microsoft 365-nätverks-och prestanda inställning](network-planning-and-performance.md)

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
