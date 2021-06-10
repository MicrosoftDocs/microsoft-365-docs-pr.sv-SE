---
title: Office 365 Vanliga frågor och svar om videonätverk
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
description: Hitta svar på några av de vanligaste frågorna om bandbreddsplanering, kryptering & hur tjänsten använder Content Delivery Networks (CDN:er).
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921576"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365 Vanliga frågor och svar om videonätverk

Med Office 365 lagringsplats för video och direktuppspelningstjänster blir det enkelt att lagra och strömma videoklipp inom organisationen. Det finns mycket bra information om [Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)– Det här nätverkets vanliga frågor och svar är utformade för att besvara de vanligaste frågorna om bandbreddsplanering, kryptering och hur tjänsten utnyttjar [Nätverk](content-delivery-networks.md) för innehållsleverans (CDN).
  
Om du inte redan har goda kunskaper om vad som händer när en video laddas upp eller spelas upp kan du ta en titt på den här videon som vi har satt ihop. Vad händer med en videofil när den laddas upp [till Office 365 Video.](https://www.youtube.com/watch?v=HXSZ0jYBKlM)
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Vilka är bandbreddskraven för Office 365 video?

Det finns en mängd [videoformat som](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) stöds som kan laddas upp till Office 365. Varje videofil kodas sedan till ett standardformat med flera olika videokvaliteter för uppspelning. Office 365 Video använder direktuppspelning med anpassningsbar bithastighet för att välja bästa videouppspelningskvalitet baserat på den tillgängliga nätverksbandbredden och storleken på videospelaren. För att göra detta begär spelaren först den lägsta uppspelningskvaliteten. Tjänsten börjar sedan skicka två sekunders videosegment till videospelaren. Spelaren kan sedan begära högre eller lägre uppspelningskvalitet baserat på hur snabbt varje segment levereras.
  
Funktionen för direktuppspelning med anpassningsbar bithastighet fungerar i bakgrunden medan videon spelas upp med minsta möjliga störning och buffring. Under videouppspelningen kan tittaren manuellt åsidosätta den automatiska uppspelningskvaliteten och välja en viss videouppspelningskvalitet.
  
Här är en översiktstabell över nätverkskraven för var och en av videouppspelningskvaliteterna. Den minsta bandbredd per person som behövs för att spela upp en video är 802 kbit/s.
  
| Uppspelningskvalitet | Nätverkshastighet |
|:-----|:-----|
|288p  <br/> |802 kbit/s  <br/> |
|360p  <br/> |1,2 Mbit/s  <br/> |
|576p  <br/> |2,5 Mbit/s  <br/> |
|720p  <br/> |3,8 Mbit/s  <br/> |

([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Hur kan videouppspelning underlättas vid uppspelning av innehållsleveransnätverk (CDN)?

Om flera personer från samma organisation inom samma geografiska område direktuppspelar samma video, lagrar CDN en kopia av videon på en plats som ligger närmare det geografiska området. Med videon lagrad, eller cachelagrad, på den närmaste platsen, strömmar varje person videon från den plats som är närmast dem i stället för från en plats som ligger längre bort. Office 365 Video använder Azure Media Services för att hantera vad som cachelagras i Azure CDN och hur länge. Azure Media Services använda någon av de [Azure CDN för](/azure/cdn/cdn-pop-locations) att cachelagra videofragment och manifest i några dagar. Om personer i organisationen fortsätter att titta på cachelagrade videor finns de kvar i cachen. Om ingen tittar på videon under flera dagar kommer videon så småningom att tas bort från cachen. Nästa gång någon tittar på videon cachelagras den igen på den CDN platsen.
  
Alla som tittar på videon medan innehållet cachelagras på en närliggande CDN dra nytta av att videon finns närmare och i de flesta fall färre hopp bort. Detta förbättrar videouppspelningshastigheten. Men nätverkskravet för att spela upp videon ändras inte.
  
> [!NOTE]
> Under vissa omständigheter, till exempel om vår kapacitetsgräns är nådd, kan videon tas bort innan de tre dagarna har uppnåtts.
  
([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kan jag cachelagra videor lokalt för snabbare uppspelning?

Ja. Office 365 hindrar dig inte från att använda en lokal CDN eller en cachelagringsproxy för att hämta video eller annat Office 365 innehåll till det lokala nätverket för snabbare åtkomst. Det finns flera sätt att implementera en lokal cachelagringslösning på nätverket. Den vanligaste metoden är att använda en proxylösning som cachelagrar innehåll lokalt. När en proxy eller privat CDN har cachelagrat videofragment och manifest hämtas framtida förfrågningar för de filer som dirigeras via proxyn eller den privata CDN från den lokala cachen och hämtas inte från en plats på Internet. Ta hänsyn till nätverkets bandbredd, kapacitet och videouppspelningens samtidighet vid planering av en lösning som den här.
  
([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Hur krypteras och skyddas videor?

Office 365 Videon vet hur viktigt det är att hålla dina data skyddade och privata. [Microsoft Säkerhetscenter](https://products.office.com/business/office-365-trust-center-welcome) beskriver vårt arbete med sekretess och säkerhet för ditt innehåll. Vid videouppspelning är hastigheten viktig för en bra upplevelse. Men vi äventyrar inte din säkerhet och sekretess i utbyte mot hastighet. Så här kan vi hantera hastighet, säkerhet och sekretess.
  
När du eller någon annan i organisationen laddar upp en ny video kodas den om, krypteras med AES-128-kryptering och lagras i Azure Media Services. Det innebär att videorna är krypterade både under överföring och vilan.
  
När någon i organisationen försöker titta på en ny video följer de de här stegen:
  
1. Fråga SharePoint Online om de har behörighet att visa videon.

2. SharePoint Online använder filbehörigheterna för att avgöra om personen kan titta på videon.

3. Om det är tillåtet hämtar SharePoint Online en token från Azure som han/hon kan ge till videospelaren.

4. Videospelaren använder sedan denna token för att begära dekrypteringsnyckeln från Azure.

5. Med dekrypteringsnyckeln kan videospelaren direktuppspela videon.

![O365 Video-uppspelning](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Vilka är kraven för uppspelning av Office 365 Video?

Office 365 Operativsystem som stöds av video och webbläsare är samma som SharePoint Online i Office 365 [systemkraven.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) Beroende på vilket operativsystem och vilken webbläsarkonfiguration du har kan du avgöra vilka behov videospelaren har. Här finns mer information om [videouppspelningskrav](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Jag kan inte få Office 365 att fungera, var ska jag börja?

Felsökning av anslutningen Office 365 video innebär felsökning nätverket, din Internetleverantör och konfigurationen av Office 365. Du börjar med hälsoinstrumentpanelen för tjänsten. Då ser du om det Office 365 ett problem eller inte. Om allt ser bra ut där finns det ytterligare resurser som kan hjälpa dig.
  
- Se till att du kan ansluta till de [nätverksslutpunkter som krävs för Office 365 Video.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Kontrollera nätverksanslutningen med hjälp av vår [Office 365 felsökningsguide för nätverk.](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- Se [metodtipsen för att Office 365 i ett långsamt nätverk.](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)

- [Hitta hjälp om Office 365 videokonfiguration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Överst på sidan](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365 Videoresurser

Här är några andra resurser som hjälper dig att distribuera och använda Office 365 Video:
  
[Hitta hjälp om Office 365 Video-konfiguration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Video om Office 365 möte](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Skapa och hantera en kanal i Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Hantera din Office 365 Video-portal](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Videoformat som fungerar i Office 365 Video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Överst på sidan](office-365-video-networking-faq.md))
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/video365networkfaq]()