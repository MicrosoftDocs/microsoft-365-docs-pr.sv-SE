---
title: Content Delivery Networks
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
description: Använd den här informationen för att lära dig hur Office 365 använder nätverk för innehållsleverans (CDN) för att förbättra prestanda.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911102"
---
# <a name="content-delivery-networks-cdns"></a>Content Delivery Networks (CDN)

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

CDNs hjälper till att hålla Office 365 snabbt och tillförlitligt för slutanvändare. Molntjänster som Office 365 använder CDN för att cachelagra statiska tillgångar närmare de webbläsare som begär att de ska snabba på nedladdningar och minska den fördröjning som slutanvändarna upplever. Informationen i det här avsnittet innehåller information om nätverk för innehållsleverans (CDN) och hur de används av Office 365.

## <a name="what-exactly-is-a-cdn"></a>Vad är egentligen en CDN?

Ett CDN är ett geografiskt distribuerat nätverk som består av proxy- och filservrar i datacenter anslutna av stamnätverk med hög hastighet. CDN används för att minska svarstiden och inläsningstiderna för en angiven uppsättning filer och objekt på en webbplats eller tjänst. Ett CDN kan ha många tusentals slutpunkter för optimal service av inkommande förfrågningar från valfri plats.

CDNs används ofta för att ge snabbare nedladdningar av allmänt innehåll för en webbplats eller tjänst, till exempel javascript-filer, ikoner och bilder, och kan även ge privat åtkomst till användarinnehåll, till exempel filer i SharePoint Online-dokumentbibliotek, direktuppspelade mediefiler och anpassad kod.

CDN används av de flesta företagmolntjänster. Molntjänster som Office 365 har miljontals kunder laddat ned en blandning av egenutvecklat innehåll (till exempel e-postmeddelanden) och allmänt innehåll (till exempel ikoner) samtidigt. Det är mer effektivt att placera bilder som alla använder, t.ex. ikoner, så nära användarens dator som möjligt. Det är inte praktiskt för varje molntjänst att skapa CDN-datacenter som lagrar det här allmänna innehållet i varje stadsområde, eller i alla större Internetnav runt om i världen, så vissa av dessa CDN delas.

## <a name="how-do-cdns-make-services-work-faster"></a>Hur gör CDNs så att tjänster fungerar snabbare?

Att ladda ned vanliga objekt som webbplatsbilder och ikoner om och om igen kan ta i så fall upp nätverkets bandbredd som kan användas bättre för att hämta viktigt personligt innehåll, t.ex. e-post eller dokument. Eftersom Office 365 använder en arkitektur som inkluderar CDNs, kan ikoner, skript och annat allmänt innehåll hämtas från servrar närmare klientdatorer, vilket gör hämtningarna snabbare. Det innebär snabbare åtkomst till personligt innehåll, som lagras säkert i Office 365-datacenter.

CDN bidrar till att förbättra prestanda i molntjänster på flera olika sätt:

- CDNs flyttar en del av nätverket och filnedladdningen bort från molntjänsten, frigör molntjänstresurser för att servera användarinnehåll och andra tjänster genom att minska behovet av att servera förfrågningar om statiska tillgångar.
- CDNs är avsedda att ge tillgång till filer med låg fördröjning genom att implementera högprestandanätverk och filservrar, och genom att utnyttja uppdaterade nätverksprotokoll som [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) med mycket effektiv komprimering och begära multiplexing.
- CDN-nätverk använder många globalt distribuerade slutpunkter för att göra innehåll tillgängligt så nära användare som möjligt.

## <a name="the-office-365-cdn"></a>The Office 365 CDN

Med det inbyggda nätverket för innehållsleverans i Office 365 (CDN) kan Office 365-administratörer få bättre prestanda för organisationens SharePoint Online-sidor genom att cachelagra statiska tillgångar närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden. Office 365 CDN använder [HTTP/2-protokollet för](https://en.wikipedia.org/wiki/HTTP/2) förbättrade komprimerings- och nedladdningshastigheter.

> [!NOTE]
> Office 365 CDN är bara tillgängligt för innehavare i molnet **För** produktion (globalt). Klientorganisationen i molnen för myndigheter i USA, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

Office 365 CDN består av flera CDN-nätverk som gör att du kan lagra statiska tillgångar på flera platser, eller ursprung _,_ och hantera dem från globala nätverk med hög hastighet. Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till offentliga **ursprung,** privata ursprung eller båda. 

![Konceptuellt diagram för Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "Konceptuellt diagram för Office 365 CDN")

Innehåll i **offentliga** ursprung i Office 365 CDN är tillgängligt anonymt och kan nås av alla som har URL-adresser till värdtillgångar. Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du bara använda dem för att cachelagra icke-känsligt allmänt innehåll som javascript-filer, skript, ikoner och bilder. Office 365 CDN används som standard för att ladda ned allmänna resurstillgångar, till exempel Office 365-klientprogram från ett offentligt ursprung.

**Privata** ursprung i Office 365 CDN ger privat åtkomst till användarinnehåll, till exempel dokumentbibliotek, webbplatser och egna bilder i SharePoint Online. Åtkomst till innehåll i privata ursprung skyddas med dynamiskt genererade token så att användare med behörighet till det ursprungliga dokumentbiblioteket eller lagringsplatsen endast kan komma åt det. Privata ursprung i Office 365 CDN kan endast användas för SharePoint Online-innehåll och du kan bara komma åt tillgångar genom omdirigering från SharePoint Online-klienten.

Office 365 CDN-tjänsten ingår som en del av din SharePoint Online-prenumeration.

Mer information om hur du använder Office 365 CDN finns i Använda Nätverket för innehållsleverans i [Office 365 med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

Om du vill titta på en serie korta videoklipp som ger konceptuell och HOWTO-information om hur du använder Office 365 CDN kan du besöka [YouTube-kanalen SharePoint Developer Patterns and Practices.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>Andra Microsoft CDN

Även om du inte är en del av Office 365 CDN kan du använda dessa CDN i Office 365-klienten för åtkomst till SharePoint-utvecklingsbibliotek, anpassad kod och andra syften som faller utanför Office 365 CDN.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>Från och med kv 3 2020 börjar SharePoint Online cachelagra videor på Azure CDN för bättre videouppspelning och tillförlitlighet. Populära videor strömmas från CDN-slutpunkten som är närmast användaren. Dessa data ligger kvar inom efterlevnadsgränsen för Microsoft 365. Det här är en kostnadsfri tjänst för alla innehavare och det krävs ingen åtgärd från kunden för att konfigurera den.

Du kan använda **Azure CDN** för att distribuera en egen CDN-instans för värd för anpassade webbdelar, bibliotek och andra resurstillgångar, så att du kan använda snabbnycklar för DIN CDN-lagring och utnyttja större kontroll över CDN-konfigurationen. Användningen av Azure CDN är inte kostnadsfri utan kräver en Azure-prenumeration.

Mer information om hur du konfigurerar en Azure CDN-instans finns i [Snabbstart: Integrera ett Azure-lagringskonto med Azure CDN.](/azure/cdn/cdn-create-a-storage-account-with-cdn)

Ett exempel på hur Azure CDN kan användas som värd för SharePoint-webbdelar finns i Distribuera din [SharePoint-klientwebbdel till Azure CDN.](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)

Information om Azure CDN PowerShell-modulen finns i [Hantera Azure CDN med PowerShell.](/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsofts **Ajax-CDN** är ett skrivskyddat CDN med många populära utvecklingsbibliotek, bland annat jQuery (och alla dess andra bibliotek), ASP.NET Ajax, Bootstrap, Knockout.js med flera.
  
Om du vill ta med de här skripten i projektet ersätter du helt enkelt alla referenser till de här offentligt tillgängliga biblioteken med referenser till CDN-adressen i stället för att ta med den i själva projektet. Använd till exempel följande kod för att länka till jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Mer information om hur du använder Microsoft Ajax CDN finns i [Microsoft Ajax CDN.](/aspnet/ajax/cdn/overview)

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Hur använder Office 365 innehåll från ett CDN?

Oavsett vilket CDN du konfigurerar för Office 365-klienten är den grundläggande datahämtningsprocessen densamma.

1. Din klient (en webbläsare eller Ett Office-klientprogram) begär data från Office 365.

2. Office 365 returnerar antingen data direkt till din klient eller, om data är en del av en uppsättning innehåll som lagras av CDN, omdirigerar din klient till CDN-URL.

    a. Om data redan cachelagras i _ett_ offentligt ursprung laddar klienten ned data direkt från närmaste CDN-plats till klienten.

    b. Om data redan cachelagras  i ett privat ursprung kontrollerar CDN-tjänsten office 365-användarkontots behörigheter för ursprunget. Om du har behörigheter genererar SharePoint Online dynamiskt en anpassad URL som består av sökvägen till tillgången i CDN och två åtkomsttoken, och returnerar den anpassade URL-adressen till klienten. Klienten laddar sedan ned data direkt från närmaste CDN-plats till klienten med hjälp av den anpassade URL:en.

3. Om data inte cachelagras på CDN begär CDN-noden data från Office 365 och cachelagrar sedan data under en viss tid efter att din klient laddat ned data.

CDN tar fram det datacenter som ligger närmast användarens webbläsare och använder omdirigering för att ladda ned den begärda informationen därifrån. CDN-omdirigering går snabbt och kan spara användare mycket nedladdningstid.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Hur ska jag konfigurera nätverket så att CDN fungerar bäst med Office 365?

Att minimera svarstiden mellan klienter i nätverket och CDN-slutpunkter är avgörande för att säkerställa optimala prestanda. Du kan använda de bästa metoderna som beskrivs i Hantera [Office 365-slutpunkter](managing-office-365-endpoints.md) för att säkerställa att nätverkskonfigurationen tillåter att klientwebbläsare får åtkomst till CDN direkt i stället för att dirigera CDN-trafik via central proxy för att undvika onödiga fördröjningar.

Du kan också läsa Principer [för Office 365-nätverksanslutning](./microsoft-365-network-connectivity-principles.md) för att förstå begreppen bakom optimering av Office 365-nätverksprestanda.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Finns det en lista över alla CDN som används i Office 365?

CDNs som används av Office 365 kan alltid komma att ändras och i många fall finns det flera CDN-partner som konfigurerats om en inte är tillgänglig. De primära CDN som används av Office 365 är:

|CDN  |Company  |Användning  |Länk  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Allmänna tillgångar i offentliga ursprung, SharePoint-användarinnehåll i privata ursprung         |[Använda nätverket för innehållsleverans i Office 365 med SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Anpassad kod och SharePoint Framework-lösningar         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (skrivskyddat)     |Microsoft         |Vanliga bibliotek för Ajax, jQuery, ASP.NET, Bootstrap Knockout.js osv.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Vilka prestandaförbättringar tillhandahåller ett CDN?

Det finns många faktorer som mäter specifika prestandaskillnader mellan data som laddas ned direkt från Office 365 och data som hämtas från ett visst CDN, till exempel din plats i förhållande till din klientorganisation och till närmaste CDN-slutpunkt, antalet tillgångar på en sida som kan hämtas genom CDN och tillfälliga ändringar av nätverksfördröjning och bandbredd. Ett enkelt A/B-test kan dock hjälpa till att visa skillnaden i nedladdningstid för en viss fil.

Följande skärmbilder illustrerar skillnaden i nedladdningshastighet mellan den ursprungliga filplatsen i Office 365 och samma fil som finns på [Microsoft Ajax Content Delivery Network.](/aspnet/ajax/cdn/overview) De här skärmbilderna kommer från **fliken** Nätverk i utvecklarverktygen för Internet Explorer 11. De här skärmbilderna visar svarstiden för det populära biblioteket jQuery. Du visar den här skärmen genom att trycka på  **F12** i Internet Explorer och välja fliken Nätverk som symboliseras av en Wi-Fi ikon.
  
![Skärmbild av F12-nätverk](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Den här skärmbilden visar biblioteket som laddats upp till galleriet för huvudsidor på själva SharePoint Online-webbplatsen. Det tog 1,51 sekunder att ladda upp biblioteket.
  
![Skärmbild av inläsningstiden 1,51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
Den andra skärmbilden visar samma fil som levererats av Microsofts CDN. Den här gången är svarstiden omkring 496 millisekunder. Det här är en stor förbättring och visar att den totala tiden för att ladda ned objektet går ned en hel sekund.
  
![Skärmbild av inläsningstider i 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Är mina data säkra?

Vi är mycket noga med att skydda data som driver din verksamhet. Data som lagras i Office 365 CDN krypteras både under överföring och vila, och åtkomst till data i Office 365 SharePoint CDN skyddas med office 365-användarbehörigheter och tokenauktorisering. Databegäranden i Office 365 SharePoint CDN måste hänvisas (omdirigeras) från Office 365-klienten, annars genereras ingen auktoriseringstoken.

För att säkerställa att dina data förblir säkra rekommenderar vi att du aldrig lagrar användarinnehåll eller andra känsliga data i ett offentligt CDN. Eftersom åtkomsten till data i ett offentligt CDN är anonym bör offentliga CDN endast användas för att lagra allmänt innehåll, till exempel webbskriptfiler, ikoner, bilder och andra icke-känsliga tillgångar.

> [!NOTE]
> Tredjepartsleverantörer av CDN kan ha sekretess- och efterlevnadsstandarder som skiljer sig från de åtaganden som anges i Office 365 Säkerhetscenter. Data som cachelagras via CDN-tjänsten kanske inte överensstämmer med Microsofts villkor för databearbetning och kan vara utanför efterlevnadsgränserna för Office 365 Säkerhetscenter.

Mer information om sekretess och dataskydd för Office 365 CDN-leverantörer finns i följande avsnitt:  

- Läs mer om sekretess och dataskydd i Office 365 på [Microsoft Säkerhetscenter](https://www.microsoft.com/trustcenter)
- Läs mer om Akamai's sekretess och dataskydd på [Akamai Privacy Trust Center](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Läs mer om sekretess och dataskydd i [Azure Säkerhetscenter](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Hur skyddar jag mitt nätverk med alla dessa tredjepartstjänster?

Med hjälp av en omfattande uppsättning partnertjänster kan Office 365 anpassa sig och uppfylla tillgänglighetskraven samt förbättra användarupplevelsen när du använder Office 365. De tredjepartstjänster Som Office 365 använder ingår både listor över återkallade certifikat. som crl.microsoft.com eller sa.symcb.com och CDN: som r3.res.outlook.com. Varje CDN-FQDN som genereras av Office 365 är ett anpassat FQDN för Office 365. Om du skickas till ett FQDN på begäran av Office 365 kan du vara säker på att CDN-leverantören styr FQDN och det underliggande innehållet på den platsen.
  
För kunder som vill avgrera begäranden som är avsedda för ett Microsoft- eller Office 365-datacenter från begäranden som är avsedda för en tredje part har vi skrivit en vägledning i Hantera [Office 365-slutpunkter.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Finns det en lista över alla FQDN som använder CDN?

Listan över FQDN och hur de använder CDNs ändras med tiden. I sidan med publicerade [Office 365-URL:er](./urls-and-ip-address-ranges.md) och IP-adressintervall kan du hålla dig uppdaterad om de senaste FQDN som använder CDN.

Du kan också använda IP-adress- och URL-webbtjänsten för [Office 365](microsoft-365-ip-web-service.md) för att begära aktuella Office 365-URL:er och IP-adressintervall formaterade som CSV eller JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kan jag använda mitt eget CDN och cachelagra innehåll på mitt lokala nätverk?

Vi söker kontinuerligt efter nya sätt att stödja våra kunders behov och utforskar för närvarande användning av cachelagring av proxylösningar och andra lokala CDN-lösningar.

Även om det inte är en del av Office 365 CDN kan du också använda **Azure CDN** för värd för anpassade webbdelar, bibliotek och andra resurstillgångar, så att du kan använda snabbtangenter för CDN-lagringen och få bättre kontroll över CDN-konfigurationen. Användningen av Azure CDN är inte kostnadsfri utan kräver en Azure-prenumeration. Mer information om hur du konfigurerar en Azure CDN-instans finns i [Snabbstart: Integrera ett Azure-lagringskonto med Azure CDN.](/azure/cdn/cdn-create-a-storage-account-with-cdn)

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Jag använder Azure ExpressRoute för Office 365, ändrar det på något?

[Azure ExpressRoute för Office 365](azure-expressroute.md) ger en dedikerad anslutning till Office 365-infrastruktur som är avskild från det offentliga Internet. Det innebär att klienter fortfarande måste ansluta via icke-ExpressRoute-anslutningar för att ansluta till CDNs och annan Microsoft-infrastruktur som inte uttryckligen finns med i listan över tjänster som stöds av ExpressRoute. Mer information om hur du dirigerar specifik trafik, till exempel begäranden som är avsedda för CDNs, finns i Hantering av [Office 365-nätverkstrafik.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Kan jag använda CDN med SharePoint Server lokalt?

Användning av CDN är endast meningsfullt i ett SharePoint Online-sammanhang och bör undvikas med SharePoint Server. Det beror på att alla fördelar i fråga om geografisk plats inte gäller om servern ändå finns lokalt eller geografiskt nära. Om det dessutom finns en nätverksanslutning till servrarna där webbplatsen finns kan den användas utan Internetanslutning och kan därför inte hämta CDN-filerna. I annat fall bör du använda ett CDN om det finns ett tillgängligt och stabilt för biblioteket och filerna du behöver för webbplatsen.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Se även

[Office 365 principer för nätverksanslutningar](./microsoft-365-network-connectivity-principles.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](./urls-and-ip-address-ranges.md)

[Använda nätverket för innehållsleverans i Office 365 med SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft säkerhetscenter](https://www.microsoft.com/trustcenter)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)