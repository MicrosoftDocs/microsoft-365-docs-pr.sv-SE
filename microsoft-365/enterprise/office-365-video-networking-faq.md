---
title: Vanliga frågor och svar om Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Hitta svar på de vanligaste frågorna kring bandbredds planering, kryptering & hur tjänsten utnyttjar innehålls leverans nätverk (CDN).
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696654"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Vanliga frågor och svar om Office 365

Med Office 365 Video-och streaming-tjänsterna blir det enkelt att lagra och strömma videor i organisationen. Det finns mycket bra [information om Office 365-Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50). dessa vanliga frågor om nätverk är avsedda att besvara de vanligaste frågorna kring bandbredds planering, kryptering och hur tjänsten utnyttjar [innehålls leverans nätverk](content-delivery-networks.md) (CDN).
  
Om du inte redan har en grundlig förståelse av vad som händer när en video laddas upp eller spelas upp kan du titta på den här videon tillsammans, [Vad händer med en videofil när den laddas upp till Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Vilka är bandbredds kraven för Office 365?

Det finns ett flertal [video format som stöds](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) och kan laddas upp till Office 365. Alla videofiler kodas då till standardformat med olika video kvaliteter för uppspelning. I Office 365-Video används anpassad bit hastighet för strömning för att välja den bästa videouppspelnings kvaliteten baserat på den tillgängliga bandbredden och storleken på videos pelaren. För att göra detta efterfrågar den lägsta uppspelnings kvaliteten från början. Tjänsten börjar sedan skicka 2-näst-video-segment till Videos pelaren. Spelaren kan sedan begära högre eller lägre uppspelnings kvalitet baserat på hur snabbt varje segment levereras.
  
Den anpassningsbara bit hastigheten gör allt detta i bakgrunden medan videon spelas upp med minsta störning eller buffring. Under videouppspelning låter visnings läsaren manuellt åsidosätta den automatiska uppspelnings kvaliteten, för att välja en specifik video uppspelnings kvalitet.
  
Här är en snabb tabell som beskriver nätverks kraven för varje videouppspelnings kvalitet. Den minsta bandbredd som behövs för att spela upp en video är 802Kbps.
  
| Uppspelnings kvalitet | Nätverks hastighet |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Hur kan jag använda CDN för innehålls överföring?

Om flera personer från samma organisation inom samma geografiska plats direktuppspelar samma video (t) lagras en kopia av dessa videoklipp på en plats närmare den geografiska regionen. Med den video som lagras eller är lagrad på den närmaste platsen direktuppspelar varje person videon från den plats som är närmast i stället för en plats längre bort. I Office 365-Video används Azure Media Services för att hantera vad som cachelagras i Azure CDN och för hur länge. Azure Media Services kan använda någon av [Azure CDN-platserna](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) för att cachelagra videofragment och-manifest i några dagar. Om personer i din organisation fortsätter att titta på de cachelagrade videoklippen sparas de i cacheminnet. Om ingen får åtkomst till videon i flera dagar kommer videon att släppas ned från cachen. Nästa gång någon försöker titta på videon den är en gång till på den närmaste CDN-platsen.
  
Alla som försöker titta på videon medan innehållet cachelagras vid ett nära CDN-bidrag från videon blir högre och i de flesta fall färre hopp. Detta förbättrar videouppspelnings hastigheten; men det ändrar inte nätverks kravet för att spela upp videon.
  
> [!NOTE]
> Det finns vissa omständigheter, till exempel vår kapacitets gräns nås, där videon kan tas bort innan tre dagar har uppnåtts.
  
([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kan jag cachelagra videor lokalt för snabbare uppspelning?

Ja. Office 365 hindrar dig inte från att använda en lokal CDN eller en Cache-proxy för att hämta video eller annan Office 365-information till ditt lokala nätverk för snabbare åtkomst. Det finns flera sätt att implementera en lokal caching-lösning i nätverket, den vanligaste metoden är att använda en proxyserver som cachelagrar innehåll lokalt. När en proxy eller ett privat CDN har cachelagrat videofragmenten och-manifesten hämtas framtida förfrågningar för de filer som dirigerar via proxy eller privat CDN från den lokala cachen och hämtas inte från en Internet plats. Betrakta bandbredd, kapacitet och video uppspelnings concurrency under planeringen av en lösning som den här.
  
([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="how-videos-are-encrypted-and-secured"></a>Hur är filmer och är krypterade?

Office 365 Video vet hur viktigt det är att skydda dina data och privata. [Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) beskriver vårt engagemang för sekretess och säkerhet för innehållet. Med videouppspelning är hastigheten viktig för en bra upplevelse; men vi kommer inte att äventyra din säkerhet eller integritet i Exchange för snabb fart. Så här gör vi för att få fart, säkerhet och sekretess.
  
När du eller någon i din organisation laddar upp en ny video är den kodad, krypterad med AES-128-kryptering och lagras i Azure Media Services. Det innebär att videoklippen är krypterade och går vidare.
  
När någon i organisationen försöker titta på en ny video följer de de här stegen:
  
1. Fråga SharePoint Online om de har behörighet att visa videon.

2. SharePoint Online använder fil behörigheterna för att avgöra om personen kan titta på videon.

3. Om de tillåts hämtar SharePoint Online ett token från Azure för att ge Videos pelaren.

4. Videos pelaren använder sedan token för att begära dekrypteringsnyckeln från Azure.

5. Med krypterings tangenten i handen kan Videos pelaren strömma videon.

![O365 videouppspelning](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Vilka är kraven för att spela upp Office 365-Video?

Office 365-kompatibla operativ system och webbläsare är samma som SharePoint Online-kraven i [system krav för office 365](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45). Beroende på vilket operativ system och vilken webb läsar konfiguration du har avgör Videos pelarens specifika behov. Här finns mer information om [krav för videouppspelning](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Jag kan inte få Office 365-Video att fungera, var ska jag börja?

Med fel sökning av anslutning till Office 365-Video kan du felsöka nätverket, Internet leverantören och din konfiguration av Office 365. Den första start platsen är instrument panelen för tjänstens hälsa. Det visar att Office 365-videon har problem eller inte. Om allting ser bra ut finns här några ytterligare resurser som hjälper dig.
  
- Kontrol lera att du kan ansluta till de [nätverks slut punkter som krävs för Office 365-Video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

- Kontrol lera nätverks anslutningen med hjälp av vår [Office 365-nätverks fel söknings guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Se vår [metod för att använda Office 365 på ett långsamt nätverk](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).

- [Hitta hjälp om konfiguration av Office 365-Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Överst på](office-365-video-networking-faq.md)sidan)
  
## <a name="office-365-video-resources"></a>Video resurser för Office 365

Här är några andra resurser som hjälper dig att distribuera och använda Office 365-Video:
  
[Hitta hjälp om konfiguration av Office 365-Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Träffa Office 365-Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Skapa och hantera en kanal i Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Hantera din Office 365 Video-Portal](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Video format som fungerar i Office 365 Video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Överst på](office-365-video-networking-faq.md)sidan)
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
