---
title: Konfigurera sökning för Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar sökning i en multi-geo-miljö. Endast vissa klienter, till exempel OneDrive för företag, kan returnera resultat i en multi-geo-miljö.
ms.openlocfilehash: 22c71661e8f3b643a1fd7afa33b38584a1cd1be5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695091"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Konfigurera sökning för Microsoft 365 multi-geo

I en multi-geo-miljö har varje Geo-plats ett eget Sök index och Sök Center. När en användare söker är frågan fanned ut till alla index och resultaten som returneras kopplas.

En användare på en Geo-plats kan till exempel söka efter innehåll som lagras på en annan Geo-plats eller för innehåll på en SharePoint-webbplats som är begränsad till en annan Geo-plats. Om användaren har till gång till innehållet visas resultatet i sökningen.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>Vilka Sök klienter fungerar i en multi-geo-miljö?

Dessa klienter kan returnera resultat från alla geo-platser:

-   OneDrive för företag

-   Delve

-   Start sidan för SharePoint

-   Sök Center

-   Anpassade Sök program som använder SharePoint Search API

### <a name="onedrive-for-business"></a>OneDrive för företag

När multi-geo-miljön har kon figurer ATS får användare som söker i OneDrive resultat från alla geo platser.

### <a name="delve"></a>Delve

När multi-geo-miljön har ställts in får användare som söker i Delve resultat från alla geo platser.

Delve-feeden och profil kortet visar bara förhands granskningar av filer som lagras på Central platsen. För filer som lagras på satellit platser visas ikonen för filtypen i stället.

### <a name="the-sharepoint-home-page"></a>Start sidan för SharePoint

Så fort multi-geo-miljön har kon figurer ATS ser användarna nyheter, senaste och följda webbplatser från flera geo platser på Start sidan för SharePoint. Om de använder sökrutan på Start sidan för SharePoint får de sammankopplade resultat från flera geo platser.

### <a name="the-search-center"></a>Sök Center

När multi-geo-miljön har ställts in fortsätter varje Sök Center att bara visa resultat från sin egen Geo-plats. Administratörer måste [ändra inställningarna för varje Sök Center](#_Set_up_a_1) för att få resultat från alla geo platser. Därefter får användare som söker i Sök centret resultat från alla geo platser.

### <a name="custom-search-applications"></a>Anpassade Sök program

Som vanligt kan anpassade Sök program interagera med Sök indexen med hjälp av de befintliga SharePoint-sökningens REST-API: er. För att få resultat från alla, eller vissa geo platser, måste programmet [anropa API: t och inkludera de nya multi-geo-frågeparametrarna](#_Get_custom_search) i begäran. Då utlöses en fläkt från frågan till alla geo-platser.

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>Vad är skillnaden mellan sökning i en multi-geo-miljö?

Vissa Sök funktioner du kanske känner till, fungerar annorlunda i en multi-geo-miljö.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Funktion</strong></th>
<th align="left"><strong>Så fungerar det</strong></th>
<th align="left"><strong>Lösning</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Framhävda resultat</td>
<td align="left">Du kan skapa Frågeregler med framhävda resultat på olika nivåer: för hela klient organisationen, för en webbplats samling eller för en webbplats. I en multi-geo-miljö definierar du framhävda resultat på klient organisations nivå för att marknadsföra resultaten till Sök Center på alla geo platser. Om du bara vill framhäva resultaten i Sök centret som finns på Geo-platsen för webbplats samlingen eller webbplatsen definierar du de framhävda resultaten på webbplats samlingen eller webbplats nivån. Dessa resultat marknadsförs inte på andra geo platser.</td>
<td align="left">Om du inte behöver olika framhävda resultat per Geo-plats, till exempel olika regler för resor, rekommenderar vi att du definierar framhävda resultat på klient organisations nivå.</td>
</tr>
<tr class="even">
<td align="left">Sök förfiningar</td>
<td align="left">Sök returnerar förfiningar från alla geo-platser hos en klient organisation och aggregerar dem. Aggregation är ett bra sätt, vilket innebär att förfiningen kanske inte är 100% korrekt. För de flesta Sök-drivna scenarier är denna noggrannhet tillräckligt. 
</td>
<td align="left">För Sök drivna program som är beroende av att förfining är klart kan du fråga varje Geo-plats oberoende.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">Multi-geo-sökning stöder inte dynamisk upphållning för numeriska förfiningar.</td>
<td align="left">Använd <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parametern "Discretize"</a> för numeriska förfiningar.</td>
</tr>
<tr class="even">
<td align="left">Dokument-ID</td>
<td align="left">Om du utvecklar ett Sök drivna program som är beroende av dokument-ID: na kan du observera att dokument-ID i en multi-geo-miljö inte är unika för geo platser, de är unika per Geo-plats.</td>
<td align="left">Vi har lagt till en kolumn som identifierar geo platsen. Använd den här kolumnen för att uppnå unika. Denna kolumn kallas "GeoLocationSource".</td>
</tr>
<tr class="odd">
<td align="left">Antal resultat</td>
<td align="left">Sök Resultat sidan visar sammanslagna resultat från geo platser, men det går inte att bläddra bortom 500-resultaten.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">HYBRIDS ökning</td>
<td align="left">I en hybrid SharePoint-miljö med <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">moln HYBRIDS ökning</a>läggs lokalt innehåll till i Microsoft 365-indexet för den centrala platsen.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>Vad stöds inte för sökning i en multi-geo-miljö?

Vissa av de Sök funktioner du kanske är van vid, stöds inte i en multi-geo-miljö.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Sök funktion</strong></th>
<th align="left"><strong>Fotnot</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Endast app-only</td>
<td align="left">Endast app-inloggningsautentisering (privilegie rad åtkomst från tjänster) stöds inte i multi-geo-sökning.</td>
</tr>
<tr class="even">
<td align="left">Gästanvändare</td>
<td align="left">Gäst användare får bara resultat från den Geo-plats som de söker från.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>Hur fungerar sökning i en multi-geo-miljö?

Alla Sök klienter använder de befintliga SharePoint-sökningens REST-API: er för att interagera med Sök indexen.

<img src="../media/configure-search-for-multi-geo-image1-1.png" />

1. En Sök klient anropar Sök öknings slut punkten med Frågeparametern EnableMultiGeoSearch = True.
2. Frågan skickas till alla geo-platser i klient organisationen.
3. Sök Resultat från varje Geo-plats slås samman och rangordnas.
4. Klienten får enhetliga Sök resultat.



<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Observera att vi inte sammanfogar Sök resultaten förrän vi har fått resultat från alla geo platser. Det innebär att multi-geo-sökningar har ytterligare fördröjning jämfört med sökningar i en miljö med bara en Geo-plats.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Hämta ett Sök Center för att visa resultat från alla geo platser

Varje Sök Center innehåller flera lodräta och du måste ställa in varje lodrätt.

1.  Kontrol lera att du utför de här stegen med ett konto som har behörighet att redigera Sök Resultat sidan och webb delen Sök resultat.

2.  Gå till sidan med Sök resultat (se [listan](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) med Sök Resultat sidor)

3.  Markera kryss rutan lodrätt och klicka på **Inställningar** kugg hjul i det övre högra hörnet och klicka sedan på **Redigera sida**. Sidan Sök Resultat öppnas i redigerings läge.

     ![](../media/configure-search-for-multi-geo-image2.png)
1.  I webb delen Sök Resultat flyttar du pekaren till det övre högra hörnet av webb delen, klickar på pilen och sedan på **Redigera webbdel** på menyn. Verktygs fönstret för webb delen Sök Resultat öppnas under menyfliksområdet längst upp till höger på sidan. ![](../media/configure-search-for-multi-geo-image3.png)

1.  I verktygs fönstret webbdel, i avsnittet **Inställningar** , under **resultat kontroll inställningar**väljer du **Visa multi-geo Results** för att få webb delen Sök Resultat för att visa resultat från alla geo-platser.

2.  Klicka på **OK** för att spara ändringen och stänga verktygs fönstret för webb delen.

3.  Kontrol lera dina ändringar i webb delen Sök resultat genom att klicka på **checka** in på fliken sida i huvud menyn.

4.  Publicera ändringarna med länken i anteckningen högst upp på sidan.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Få anpassade Sök program för att visa resultat från alla eller vissa geo-platser

Anpassade Sök program får resultat från alla eller vissa geo platser genom att ange frågeparametrar med begäran till den REST-API för SharePoint-sökning.Beroende på frågeparametrarna är frågan fanned ut till alla geo platser eller till vissa geo platser. Om du till exempel bara behöver fråga en delmängd geo platser för att hitta relevant information kan du bara kontrol lera fläkten till dessa. Om begäran lyckas returneras svars data i SharePoint Search REST API.

**Krav**

För varje Geo-plats måste du se till att alla användare i organisationen har fått behörighets nivån **läsa** för rot webbplatsen (till exempel contoso**APAC**. SharePoint.com/och contoso**EU**. SharePoint.com/). [Läs mer om behörigheter](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).

### <a name="query-parameters"></a>Frågeparametrar

EnableMultiGeoSearch-det här är ett booleskt värde som anger om frågan ska fanned till indexen för andra geo platser i multi-geo-klienten. Ange att det ska vara **Sant** för att det ska vara. **falskt** för att inte framhäva frågan. Om du inte tar med den här parametern är standardvärdet **falskt**, förutom när du skapar ett REST API-samtal på en webbplats där mallen Enterprise Search Center används, i det här fallet är standardvärdet **Sant**. Om du använder en parameter i en miljö som inte är multi-geo ignoreras parametern.

ClientType-det här är en sträng. Ange ett unikt klient namn för varje sökprogram. Om du inte tar med den här parametern fanned inte frågan ut till andra geo platser.

MultiGeoSearchConfiguration – det här är en valfri lista över vilka geo-platser i multi-geo-klient organisationen som kan utnyttja frågan på när **EnableMultiGeoSearch** är **Sant**. Om du inte tar med den här parametern, eller lämnar den tom, fanned frågan ut till alla geo-platser. För varje Geo-plats anger du följande objekt i JSON-format:

<table>
<thead>
<tr class="header">
<th align="left">Objekt</th>
<th align="left">Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">DataLocation</td>
<td align="left">Geo platsen, till exempel.</td>
</tr>
<tr class="even">
<td align="left">Änd</td>
<td align="left">Slut punkten för att ansluta till till exempel https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">Käll</td>
<td align="left">GUID för resultat källan, till exempel B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</td>
</tr>
</tbody>
</table>

Om du utelämnar DataLocation eller slut punkter, eller om en DataLocation har dubblerats Miss lyckas begäran. [Du kan få information om slut punkten för en innehavares geo platser genom att använda Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).

### <a name="response-data"></a>Svars data

MultiGeoSearchStatus – det här är en egenskap som SharePoint Search API returnerar som svar på en begäran. Värdet för egenskapen är en sträng och ger följande information om resultaten som returneras av SharePoint Search API:

<table>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Fullständiga</td>
<td align="left">Fullständiga resultat från <strong>alla</strong> geo-platser.</td>
</tr>
<tr class="even">
<td align="left">Partiell</td>
<td align="left">Delar av resultat från en eller flera geo platser. Resultaten är ofullständiga på grund av ett tillfälligt fel.</td>
</tr>

</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Fråga med REST-tjänsten

Med en GET-begäran anger du frågeparametrarna i URL: en. Med en POST-begäran skickar du frågeparametrarna i bröd texten i JSON-format (Java Script Object Notation).


#### <a name="request-headers"></a>Begärandehuvuden

<table>
<thead>
<tr class="header">
<th align="left">Namn</th>
<th align="left">Värde</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Innehålls typ</td>
<td align="left">Application/JSON; OData = verbose</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>TA en fanned på **alla** geo platser

https:// \<tenant\> / \_ API/sökning/fråga? querytext = ' SharePoint ' &Properties = ' EnableMultiGeoSearch: true ' &ClientType = ' mitt \_ klient \_ -ID '

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Exempel på GET-begäran för att utnyttja **vissa** geo platser

https:// \<tenant\> / \_ API/Sök/fråga? querytext = ' site ' &ClientType = ' my_client_id ' &egenskaper = ' EnableMultiGeoSearch: true, MultiGeoSearchConfiguration: [{DataLocation \\ : "," \\ slut punkt \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceId \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {DataLocation \\ : "kan" \\ ; slut punkt \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}] "

> [!NOTE]
> Kommatecken och kolon i listan med geo-platser för egenskapen MultiGeoSearchConfiguration föregås av det **omvända snedstrecket** . Det beror på att GET-begäranden använder kolon för att avgränsa egenskaper och kommatecken för att skilja mellan egenskaper. Utan omvänt snedstreck som escape-tecken tolkas egenskapen MultiGeoSearchConfiguration som felaktig.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Exempel på inlägg som fanned ut till **alla** geo-platser

    {
        "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }


#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Exempel på inlägg som fanned ut till **vissa** geo platser


    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }

### <a name="query-using-csom"></a>Fråga med CSOM

Här är ett exempel på en CSOM fråga som fanned på **alla** geo platser:

    var keywordQuery = new KeywordQuery(ctx);
    keywordQuery.QueryText = query.SearchQueryText;
    keywordQuery.ClientType = <enter a string here>;
    keywordQuery["EnableMultiGeoSearch"] = true;

