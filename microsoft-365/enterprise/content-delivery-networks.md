---
title: Nätverk för innehålls leverans
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Använd den här informationen för att få reda på 365 hur innehålls leverans nätverk (CDN) används för att förbättra prestanda.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694502"
---
# <a name="content-delivery-networks-cdns"></a>Innehålls leverans nätverk (CDN)

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

CDN hjälper till att hålla Office 365 snabbt och tillförlitligt för slutanvändarna. Moln tjänster som Office 365 använder CDN för att cachelagra statiska till gångar i webbläsare för att kunna göra nedladdningar snabbare och minska svars tiden. Informationen i det här avsnittet hjälper dig att lära dig om innehålls leverans nätverk (CDN) och hur de används i Office 365.

## <a name="what-exactly-is-a-cdn"></a>Vad är det för ett CDN?

Ett CDN är ett geografiskt distribuerat nätverk bestående av proxyservrar och fil servrar i Data Center som är anslutna via höghastighets stamnät nätverk. CDN används för att minska svars tid och inläsnings tid för en viss uppsättning filer och objekt på en webbplats eller tjänst. Ett CDN kan ha många tusen slut punkter för optimal behandling av inkommande förfrågningar från valfri plats.

CDN används ofta för att ge snabbare nedladdning av allmänt innehåll för en webbplats eller tjänst, till exempel JavaScript-filer, ikoner och bilder och kan ge privat åtkomst till användar innehåll som filer i SharePoint Online-dokumentbibliotek, direktuppspelade mediefiler och anpassad kod.

CDN används av de flesta moln tjänster för företag. Moln tjänster som Office 365 har miljon tals kunder som laddar ner en blandning av eget innehåll (till exempel e-post) och allmänt innehåll (till exempel ikoner) samtidigt. Det är mer effektivt att placera bilder som alla använder, till exempel ikoner, så nära användarens dator som möjligt. Det är inte praktiskt för varje moln tjänst att bygga CDN-Datadata som lagrar detta generiska innehåll i varje huvudlands område, eller till och med i varje tilldelat Internet nav världen över, så att vissa av dessa CDN delas.

## <a name="how-do-cdns-make-services-work-faster"></a>Hur kan CDN-tjänsterna fungera snabbare?

Om du laddar ned vanliga objekt, till exempel webbplats bilder och ikoner på nytt kan det ta upp nätverks bandbredd som kan användas för att ladda ner viktig personligt innehåll, som e-post eller dokument. Eftersom Office 365 använder en arkitektur som innehåller CDN, kan ikoner, skript och annat allmänt innehåll hämtas från servrar närmare klient datorer, vilket gör nedladdningarna snabbare. Det innebär snabbare åtkomst till ditt personliga innehåll, som är säkert lagrat i Office 365-datacenter.

CDN hjälp för att förbättra moln tjänstens prestanda på flera olika sätt:

- CDN byta del av nätverket och få fil nedladdning borta från moln tjänsten och frigör moln tjänst resurser för att betjäna användar innehåll och andra tjänster genom att minska behovet av att hantera förfrågningar för statiska till gångar.
- CDN är syfte som är utformade för att tillhandahålla begränsad fil åtkomst genom att implementera högpresterande nätverk och fil servrar och genom att använda uppdaterade nätverks protokoll som [http/2](https://en.wikipedia.org/wiki/HTTP/2) med mycket effektiv komprimering och begäran om multiplexering.
- CDN-nätverk använder många globalt distribuerade slut punkter för att göra innehållet tillgängligt så nära som möjligt för användarna.

## <a name="the-office-365-cdn"></a>Office 365 CDN

Med det inbyggda Office-365 innehålls leverans nätverk (CDN) kan Office 365-administratörer bättre prestanda för organisationens SharePoint Online-sidor genom att cachelagra statiska till gångar i webbläsarens begär Ande för att snabba på nedladdningar och minska svars tiden. Office 365 CDN använder [http/2-protokollet](https://en.wikipedia.org/wiki/HTTP/2) för förbättrad komprimering och nedladdnings hastighet.

> [!NOTE]
> Office 365 CDN är bara tillgängligt för klient organisationer i **produktions** -molnet (världen över). Klient organisationer i Förenta staternas myndigheter, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

Office 365 CDN består av flera CDN som låter dig hantera fasta till gångar på flera platser, eller _ursprung_, och betjäna dem från globala nätverk med snabb hastighet. Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till **offentliga** ursprung, **privata** ursprung eller båda.

![Office 365 CDN-koncept diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-koncept diagram")

Innehåll i **offentliga** ursprung i Office 365 CDN är lättillgängligt och kan nås av alla som har URL-adresser till tillhörbaserade till gångar. Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du endast använda dem för att cachelagra icke-känsligt allmänt innehåll, till exempel JavaScript-filer, skript, ikoner och bilder. Office 365 CDN används som standard för att ladda ned allmänna resurs till gångar som Office 365-klientprogram från ett offentligt ursprung.

**Privata** ursprung i Office 365 CDN ger privat åtkomst till användar innehåll som SharePoint Online-dokumentbibliotek, webbplatser och grafik. Åtkomst till innehåll i privata ursprung skyddas med dynamiskt genererade token så att användare som har behörighet till det ursprungliga dokument biblioteket eller lagrings platsen endast kan komma åt det. Privata ursprung i Office 365 CDN kan endast användas för SharePoint Online-innehåll och du kan bara komma åt till gångar via omdirigering från din SharePoint Online-klient organisation.

Office 365 CDN-tjänsten är inkluderad som en del av SharePoint Online-prenumerationen.

Mer information om hur du använder Office 365 CDN finns i [använda office 365-innehålls leverans nätverk med SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Om du vill titta på en serie korta videoklipp som innehåller begreppsmässig och HOWTO information om hur du använder Office 365 CDN kan du besöka [YouTube-kanalen för SharePoint-utvecklare](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Andra Microsoft-CDN

Även om det inte är en del av Office 365 CDN kan du använda dessa CDN i din Office 365-klient organisation för åtkomst till utvecklings bibliotek för SharePoint, anpassade koder och andra ändamål som faller utanför omfånget för Office 365 CDN.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>Från och med Q3 2020 cachelagrar SharePoint Online videofiler på Azure CDN för att hantera bättre videouppspelning och-pålitlighet. Populära Videoklipp kommer att strömmas från CDN-slutpunkten närmast användaren. Dessa data behålls i Microsoft 365-kompatibilitetskontrollen. Det här är en gratis tjänst för alla innehavare och kräver ingen kund åtgärd för att konfigureras.

Du kan använda **Azure CDN** för att distribuera din egen CDN-instans för anpassade webb delar, bibliotek och andra resurs till gångar, som låter dig använda snabb tangenterna till ditt CDN-lagring och låta större kontroll över din CDN-konfiguration. Användning av Azure CDN är inte gratis och kräver en Azure-prenumeration.

Mer information om hur du konfigurerar en Azure CDN-instans finns i [snabb start: integrera ett Azure Storage-konto med Azure CDN](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

Ett exempel på hur Azure CDN kan användas för att vara värd för SharePoint-webbdelar finns i [distribuera webb delen för SharePoint-klient till Azure CDN](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Information om modulen Azure CDN PowerShell finns i [Hantera Azure CDN med PowerShell](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsofts **Ajax CDN** är en skrivskyddad CDN som erbjuder många populära utvecklings bibliotek, inklusive jQuery (och alla dess andra bibliotek), ASP.NET AJAX, start, Knockout.js och andra.
  
Om du vill inkludera dessa skript i projektet ersätter du bara referenser till dessa offentligt tillgängliga bibliotek med referenser till CDN-adressen i stället för att inkludera den i själva projektet. Använd till exempel följande kod för att länka till jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Mer information om hur du använder Microsoft Ajax CDN finns i [Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Hur använder Office 365 innehåll från ett CDN?

Oavsett vilken CDN du konfigurerar för din Office 365-klient organisation är den grundläggande data hämtnings processen samma sak.

1. Din klient (en webbläsare eller ett Office-klientprogram) begär data från Office 365.

2. Office 365 returnerar antingen data direkt till klienten eller, om data är en del av en uppsättning innehåll som hanteras av CDN, dirigerar klienten till CDN-URL: en.

    a. Om data redan har cachelagrats i _offentligt_ ursprung laddar din klient ned data direkt från närmaste CDN-plats till klienten.

    b. Om data redan är cachelagrade i ett _privat_ ursprung kontrollerar CDN-tjänsten om ditt Office 365-kontos behörigheter i origo. Om du har behörighet skapar SharePoint Online dynamiskt en egen URL-adress som består av sökvägen till till gången i CDN och två åtkomsttoken och returnerar den anpassade URL-adressen till din klient. Din klient laddar sedan ned informationen direkt från den närmaste CDN-platsen till din klient via den anpassade URL-adressen.

3. Om data inte cachelagras i CDN efterfrågar CDN-noden data från Office 365 och cachelagrar sedan data under en viss tid efter att klienten laddat ner data.

CDN tar bort det närmaste datacentret till användarens webbläsare och använder omdirigering, hämtar begärda data från den där. Omdirigering av CDN är snabbt och kan spara användare mycket av nedladdnings tiden.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Hur ska jag konfigurera nätverket så att CDN fungerar bäst med Office 365?

Det är viktigt att du minimerar fördröjningen mellan klienter i nätverks-och CDN-slutpunkter för att säkerställa optimal prestanda. Du kan använda de metod tips som beskrivs i [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) för att se till att din nätverks konfiguration tillåter att klient webbläsare får åtkomst till CDN direkt i stället för att dirigera den onödigt svars tiden.

Du kan också läsa [principer för office 365-nätverks anslutningar](https://aka.ms/o365networkingprinciples) för att förstå begreppen bakom optimering av nätverks prestanda i Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Finns det en lista över alla CDN som Office 365 använder?

CDN som används av Office 365 är alltid föremål för ändringar och det finns flera olika CDN-partners konfigurerade i händelsen som inte är tillgängliga. De primära CDN som används av Office 365 är:

|CDN  |Company  |Egenskaper  |Länknamn  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Allmänna till gångar i offentliga ursprung, SharePoint-användarnamn i privata ursprung         |[Använda Office 365 innehålls leverans nätverk med SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Anpassad kod, lösningar för SharePoint-ramverk         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (skrivskyddat)     |Microsoft         |Vanliga bibliotek för Ajax, jQuery, ASP.NET, bootstrap, Knockout.js etc.         |[Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Vilka prestanda vinster har ett CDN?

Det finns många faktorer som är förknippade med att mäta specifika skillnader i prestanda mellan data som hämtas direkt från Office 365 och data som hämtas från ett specifikt CDN, till exempel din plats i förhållande till din klient organisation och till närmaste CDN-slutpunkt, antalet till gångar på en sida som hanteras av CDN samt tillfälliga ändringar i nätverks fördröjning och bandbredd. Men ett enkelt A/B-test kan visa skillnaden i nedladdnings tid för en viss fil.

Följande skärm dum par illustrerar skillnaden i nedladdnings hastigheten mellan den ursprungliga fil platsen i Office 365 och den fil som finns på [Microsoft Ajax-innehållet](https://docs.microsoft.com/aspnet/ajax/cdn/overview). Dessa skärm dum par visas på fliken **nätverk** i utvecklingsverktygen för Internet Explorer 11. Dessa skärm dum par visar svars tiden för det populära jQuery. Öppna den här skärmen genom att trycka på **F12** i Internet Explorer och välja fliken **nätverk** som symbol med en Wi-Fi-ikon.
  
![Skärm bild av F12-nätverk](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Denna skärm bild visar biblioteket som laddats upp till galleriet för huvud sidor på SharePoint Online-webbplatsen. Det tog för lång tid att ladda upp biblioteket 1,51 sekunder.
  
![Skärm bild av inläsnings tid 1.51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
Den andra skärmdumpen visar samma fil som Microsofts CDN har levererat. Den här gången blir fördröjningen cirka 496 millisekunder. Det här är en stor förbättring och visar att hela sekunden shaved av den totala tiden för att ladda ned objektet.
  
![Skärm bild av laddnings tider i 469 MS](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Är mina data säkra?

Vi är mycket försiktig för att skydda dina uppgifter. Data som lagras i Office 365 CDN är krypterade både i transit och på andra och åtkomst till data i Office 365 SharePoint CDN skyddas av Office 365 användar behörigheter och token Authorization. Begär Anden om data i Office 365 SharePoint CDN måste hänvisas till (omdirigerade) från din Office 365-klient organisation eller en autentiseringstoken kommer inte att genereras.

För att se till att dina data förblir säkra rekommenderar vi att du aldrig lagrar användar innehåll eller annan känslig information i ett offentligt CDN. Eftersom åtkomst till data i ett offentligt CDN är anonymt ska endast offentliga CDN användas för att vara värd för generiskt innehåll, till exempel webbskriptfil, ikoner, bilder och andra icke-känsliga till gångar.

> [!NOTE]
> tredjeparts CDN-leverantörer kan ha integritets-och efterföljandekrav som skiljer sig från åtaganden som beskrivs i säkerhets Center för Office 365. Data som cachelagras via CDN-tjänsten kanske inte stämmer överens med villkoren för Microsoft-databearbetning (DPT) och kan vara utanför Office 365-funktionen för säkerhets Center.

Mer ingående information om sekretess och data skydd för Office 365 CDN-leverantörer finns på följande:  

- Läs mer om sekretess och data skydd för Office 365 i [Microsoft säkerhets Center](https://www.microsoft.com/trustcenter)
- Läs mer om Akamai integritet och data skydd i [Akamai integritets säkerhets Center](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Läs mer om Azure Privacy och data skydd i [Azure Trust Center](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Hur kan jag skydda mitt nätverk med alla dessa tjänster från tredje part?

Genom att använda en omfattande uppsättning partner tjänster kan Office 365 bygga ut och uppfylla tillgänglighets kraven samt förbättra användar upplevelsen när du använder Office 365. Office 365-tjänsterna från tredje part omfattar bland annat listor över återkallade certifikat; till exempel crl.microsoft.com eller sa.symcb.com, och CDN; till exempel r3.res.outlook.com. Varje CDN FQDN som genereras av Office 365 är ett anpassat FQDN för Office 365. Om du har skickat till en FQDN på begäran av Office 365, kan du vara säker på att CDN-leverantören kontrollerar FQDN och underliggande innehåll på den platsen.
  
För kunder som vill ansvara för ett Microsoft-eller Office 365-datacenter från en begäran som är avsedd för tredje part, har vi skrivit vägledning om hur du [hanterar slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Finns det en lista över alla FQDN-namn som utnyttjar CDN?

Listan över FQDN: er och hur de utnyttjar CDN ändras med tiden. Gå till sidan med [URL-adresser och IP-adressintervall](https://go.microsoft.com/fwlink/p/?LinkID=293744) för publicering av Office 365 för att komma fram till den senaste FQDN som berör CDN.

Du kan också använda [office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md) för att begära de aktuella Office 365 URL-adresser och IP-adressintervall formaterade som CSV eller JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kan jag använda mitt eget CDN och cachelagrat innehåll i mitt lokala nätverk?

Vi letar ständigt efter nya sätt att stödja våra kunders behov och utforskar för närvarande användning av proxyservrar och andra lokala CDN-lösningar.

Även om det inte är en del av Office 365 CDN kan du också använda **Azure CDN** för att vara värd för anpassade webb delar, bibliotek och andra resurs till gångar, som gör att du kan använda snabb tangenterna till din CDN-lagring och låta större kontroll över din CDN-konfiguration. Användning av Azure CDN är inte gratis och kräver en Azure-prenumeration. Mer information om hur du konfigurerar en Azure CDN-instans finns i [snabb start: integrera ett Azure Storage-konto med Azure CDN](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Jag använder Azure ExpressRoute för Office 365, ändrar det?

[Azure ExpressRoute for Office 365](azure-expressroute.md) ger en dedikerad anslutning till infrastrukturen för Office 365 som är åtskild från det offentliga Internet. Det innebär att klienterna ändå måste ansluta via icke-ExpressRoute anslutningar för att ansluta till CDN och andra Microsoft-infrastrukturer som inte uttryckligen ingår i listan över tjänster som stöds av ExpressRoute. Mer information om hur du dirigerar specifik trafik, till exempel begär Anden för CDN, finns i [Hantera nätverks trafik hantering i Office 365](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Kan jag använda CDN med SharePoint Server lokalt?

Det är bara att använda CDN i en SharePoint Online-kontext och det bör undvikas med SharePoint Server. Det beror på att alla fördelar kring den geografiska platsen inte är sanna om servern finns lokalt eller på ett geografiskt sätt. Om det finns en nätverks anslutning till servrarna där den är värd, kan webbplatsen användas utan en Internet anslutning och därför inte kunna hämta CDN-filerna. Annars bör du använda ett CDN om det finns en tillgänglig och stabil för det bibliotek och de filer du behöver för webbplatsen.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>Se även

[Principer för nätverks anslutning för Office 365](https://aka.ms/o365networkingprinciples)

[Utvärdering av Office 365 nätverks anslutning](assessing-network-connectivity.md)

[Hantera slut punkter för Office 365](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[Använda Office 365 innehålls leverans nätverk med SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft säkerhetscenter](https://www.microsoft.com/trustcenter)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)
