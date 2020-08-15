---
title: Använda BGP-communities i ExpressRoute för Office 365
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
description: Lär dig hur du använder BGP-communities i Azure ExpressRoute för att hantera antalet IP-prefix och nödvändig bandbredd för Office 365-scenarier.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694767"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Använda BGP-communities i ExpressRoute för Office 365

Anslutning till Office 365 med Azure ExpressRoute baseras på BGP-annonser med specifika IP-undernät som representerar nätverk där slut punkter för Office 365 distribueras. På grund av den globala karaktären hos Office 365 och antalet tjänster som utgör Office 365 har kunderna ofta behov att hantera de annonser de accepterar i deras nätverk. Minska antalet IP-undernät; som kallas IP-prefix i hela resten av den här artikeln, för att justeras med BGP Network Management terminologi, hanteras följande mål för kunder:
  
- **Hantera det antal annonserade IP-prefix som accepteras** – kunder som har en intern nätverks infrastruktur eller nätverks operatör som bara stöder ett begränsat antal IP-prefix och kunder som har en nätverks operatör som debiterar för att acceptera prefix ovan ett begränsat nummer vill utvärdera det totala antalet prefix som redan har 365 annonser ATS för ExpressRoute.

- **Hantera den bandbredd som krävs för Azure ExpressRoute-kretsen** – kunderna kan behöva kontrol lera bandbredden hos Office 365-tjänsterna via ExpressRoute-sökvägen kontra Internet-sökvägen. Detta gör att kunderna kan reservera ExpressRoute bandbredd för specifika program, till exempel Skype för företag och dirigera de återstående Office 365-programmen via Internet-sökvägen.

För att hjälpa kunder med dessa mål kan Office 365-IP-prefix som annonseras via ExpressRoute taggas med service specifika BGP community-värden enligt exemplet nedan.
  
> [!NOTE]
> Du bör förvänta dig viss nätverks trafik som är kopplad till andra program att ingå i Community-värdet. Det här är ett globalt program som tjänst erbjudande med delade tjänster och data Center. Det här är minimerat om möjligt med ovanstående två mål, hantera prefix och/eller bandbredd i åtanke.

|**Tjänst**|**Värde för BGP community**|**Kommentarer**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Inkluderar Exchange-och EOP-tjänster\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype för företag\*  <br/> |12076:5030  <br/> |Skype för företag – Online & Microsoft Teams Services  <br/> |
|Andra Office 365-tjänster\*  <br/> |12076:5100  <br/> |Inkluderar Azure Active Directory-(autentiseringsmetoder och-synkroniseringsanvändare) samt Office 365-Portaltjänster  <br/> |
|\* Omfattningen av tjänst scenarier som ingår i ExpressRoute är dokumenterade i artikeln [Office 365-slut punkter](https://aka.ms/o365endpoints) .  <br/> \*\*Ytterligare tjänster och värden för BGP-communityn kan läggas till i framtiden. [Se den aktuella listan över BGP-communities](https://azure.microsoft.com/documentation/articles/expressroute-routing/).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Vilka är de vanligaste scenarierna för användning av BGP-communities?

Kunderna kan använda BGP-grupper för att reglera grupper av IP-prefix som accepteras av sitt nätverk via Azure ExpressRoute, och därför att det påverkar antalet IP-adressprefix och förväntat bandbredd i vissa Office 365-tjänster. Det är viktigt att förstå att alla Office 365 kräver Internet bunden trafik oavsett användning av Azure ExpressRoute eller BGP-communities. Följande tre scenarier är de vanligaste användningarna av den här funktionen.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: minimera antalet Office 365 IP-prefix

Contoso Corporation är ett 50 000 person företag som använder Office 365 för Exchange Online och SharePoint Online. I granska ExpressRoute krav contoso bestäms dess nätverks enheter på många regionala platser, och kan inte hantera vägarnas storlekar ovanför 100 ytterligare väg poster. Contoso granskade det totala antalet IP-prefix som ExpressRoute skulle annonsera för en fullständig uppsättning Office 365-tjänster och slut satsen att den överskrider 100. För att vara med i 100-ytterligare väg poster kan Contoso-scope använda ExpressRoute för Office 365 till endast SharePoint Online BGP community-värde, 12076:5020, mottaget via ExpressRoute Microsoft-peering.

|**Taggen BGP community används**|**Funktionalitet som routas via Azure ExpressRoute**|**Internet vägar krävs**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |&amp;OneDrive för företag för SharePoint Online  <br/> | DNS, CRL, &amp; CDN-begäranden  <br/>  Alla andra Office 365-tjänster stöds inte specifikt för Azure ExpressRoute  <br/>  Alla andra Microsoft Cloud-tjänster  <br/>  Office 365-portal, Office 365-verifikation, &amp; Office i en webbläsare  <br/>  Exchange Online, Exchange Online Protection och Skype för företag – Online  <br/> |

> [!NOTE]
> För att det ska bli mindre prefix för varje tjänst kvarstår en minsta överlappning mellan tjänster. Detta är ett förväntat beteende.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: omfattning ExpressRoute och intern bandbredds användning för vissa Office 365-tjänster

Fabrikam Inc, ett stort företag med flera länder med ett distribuerat heterogent nätverk, är en abonnent av många Office 365-tjänster, inklusive; Exchange Online, SharePoint Online och Skype för företag – online. Infrastrukturen för intern routning i Fabrikam kan hantera tusentals IP-prefix i sina routningstabeller; Fabrikam vill dock bara etablera ExpressRoute och intern bandbredd för Office 365-program som är mest känsliga för nätverks prestanda och använda sin nuvarande Internet bandbredd för alla andra Office 365-program.
  
Av den anledningen kan Skype ExpressRoute bandbredden för ditt Azure för företag Online BGP community-värde, 12076:5030, tas emot via ExpressRoute Microsoft peering. Den återstående nätverks trafik som är kopplad till Office 365 fortsätter att använda Internet avgångs punkter.

|**Taggen BGP community används**|**Funktionalitet som routas via Azure ExpressRoute**|**Internet vägar krävs**|
|:-----|:-----|:-----|
|Skype för företag  <br/> (12076:5030)  <br/> |Skype SIP-signalering, nedladdningar, röst-, video-och skriv bords delning  <br/> | DNS, CRL, &amp; CDN-begäranden  <br/>  Alla andra Office 365-tjänster stöds inte specifikt för Azure ExpressRoute  <br/>  Alla andra Microsoft Cloud-tjänster  <br/>  Office 365-portal, Office 365-verifikation, &amp; Office i en webbläsare  <br/>  Skype för Business-telemetri, Skype-klientens snabb tips, offentliga snabb meddelande anslutningar  <br/>  Exchange Online, Exchange Online Protection och SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: omfångsdefinierande Azure ExpressRoute for Office 365-tjänster endast

Sparbanken bank är en kund av flera Microsoft Cloud-tjänster, inklusive Office 365. När du har bedömt nätverks kapaciteten och förbrukningen från Sparbanken beslutar att distribuera Azure ExpressRoute som den prioriterade sökvägen för de Office 365-tjänster som stöds. Routningstabeller kan stödja den fullständiga uppsättningen av Office 365-IP-prefix och Azure ExpressRoute-kretsar som de har etablerat stöd för alla planerade bandbredder och fördröjnings behov.
  
För att säkerställa nätverks trafik som är kopplad till andra moln tjänster än Office 365-scope används ExpressRoute för Office 365 på alla IP-prefix taggade med Office 365 specifika BGP community-värden, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Taggen BGP community används**|**Funktionalitet som routas via Azure ExpressRoute**|**Internet vägar krävs**|
|:-----|:-----|:-----|
|Exchange, Skype för företag & Microsoft Teams, SharePoint, &amp; andra tjänster  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> &amp;OneDrive för företag för SharePoint Online  <br/> Skype SIP-signalering, nedladdningar, röst-, video-och skriv bords delning  <br/> Office 365-portal, Office 365-verifikation, &amp; Office i en webbläsare  <br/> | DNS, CRL, &amp; CDN-begäranden  <br/>  Alla andra Office 365-tjänster stöds inte specifikt för Azure ExpressRoute  <br/>  Alla andra Microsoft Cloud-tjänster  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Överväganden vid viktiga faktorer för att använda BGP-grupper

Kunder som väljer att dra nytta av BGP-samhällen för att påverka hur ExpressRoute marknadsförs och sprids via kundens nätverk bör tänka på följande:
  
- När BGP-communities används i nätverks utformningen är det viktigt att se till att flödes symmetrin fortfarande upprätthålls. I vissa fall kan tillägget eller borttagningen av BGP-communities skapa en situation där symmetrisk routning är uppkopplad och konfigurationen för routning måste uppdateras för att återupprätta symmetrisk routning.

- Scopet Azure ExpressRoute med BGP community-värden är en kund åtgärd. Microsoft meddelar alla IP-prefix som är kopplade till peering-relationen oavsett vilket scope som har kon figurer ATS av kunden.

- Azure ExpressRoute har inte stöd för några åtgärder på Microsofts nätverk baserat på kund tilldelade BGP-grupper.

- De IP-prefix som används av Office 365 är endast markerade med specifika BGP-community-värden, platsens specifika BGP-grupper stöds inte. Office 365-tjänsterna är globala och kan inte användas för att filtrera prefix som baseras på klient organisationens eller dataens plats i Office 365-molnet. Vi rekommenderar att du konfigurerar nätverket så att det koordinerar den kortaste eller mest önskade nätverks Sök vägen från användarens nätverks plats till Microsofts globala nätverk, oavsett den fysiska platsen för IP-adressen till den Office 365-tjänst de begär.

- IP-prefixen som ingår i varje BGP-community-värde representerar ett undernät som innehåller IP-adresser för Office 365-programmet som är kopplat till värdet. I vissa fall har mer än ett Office 365-program IP-adresser i ett undernät som resulterar i ett IP-prefix som finns i mer än ett community-värde. Det förväntas, men sällan, beteende på grund av tilldelnings fragment och påverkar inte räknarna eller bandbredds hanteringen. Kunder uppmuntras att använda inställningen "Tillåt vad som behövs" i stället för "neka vad som behövs" när man utnyttjar BGP-communities för Office 365 för att minimera effekten.

- Användning av BGP-communities ändrar inte underliggande nätverks anslutnings krav eller konfiguration som krävs för att använda Office 365. Kunder som vill komma åt Office 365 måste fortfarande ha till gång till Internet.

- Scopet Azure ExpressRoute med BGP-communities påverkar bara de vägar det interna nätverket kan se över Microsoft-peering-relationen. Du kan behöva göra ytterligare konfigurationer på program nivå, till exempel användning av en PAC-eller WPAD-konfiguration tillsammans med operationsföljden.

- Förutom att använda Microsoft-tilldelade BGP-communities kan kunder välja att tilldela sina egna BGP-grupper till Office 365 IP-prefix som lärts genom Azure ExpressRoute för att påverka intern routning. Ett populärt användnings fall tilldelar en plats baserad BGP-community till alla vägar som lärts via varje givet ExpressRoute peering-plats och sedan använder den informationen i kundens nätverk för att koordinera den kortaste eller mest önskade nätverks Sök vägen till Microsofts nätverk. Användning av kund tilldelade BGP-grupper med ExpressRoute för Office 365-scenarier är utanför Microsoft-kontroll eller-synlighet.

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) .
  
## <a name="related-topics"></a>Närliggande ämnen

[Utvärdering av Office 365 nätverks anslutning](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365](managing-expressroute-for-connectivity.md)
  
[Routning med ExpressRoute för Office 365](routing-with-expressroute.md)
  
[Nätverks planering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
  
[Media kvalitet och nätverks anslutnings prestanda i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute och QoS i Skype för företag – Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtals flöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Stöd för BGP-communities](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Prestanda justering för Office 365 med bas linjer och prestanda historik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute för Office 365-utbildning](https://channel9.msdn.com/series/aer)
