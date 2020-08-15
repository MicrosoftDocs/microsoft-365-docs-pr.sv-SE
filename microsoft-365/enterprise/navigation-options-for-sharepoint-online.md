---
title: Navigerings alternativ för SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: Den här artikeln beskriver navigerings alternativ webbplatser med SharePoint-publicering aktiverat i SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696688"
---
# <a name="navigation-options-for-sharepoint-online"></a>Navigerings alternativ för SharePoint Online

Den här artikeln beskriver navigerings alternativ webbplatser med SharePoint-publicering aktiverat i SharePoint Online. Valet och konfigurationen av navigeringen påverkar markant prestanda och skalbarhet för webbplatser i SharePoint Online. Mallen för publicerings webbplatsen för SharePoint bör bara användas om den är nödvändig för en centraliserad Portal och publicerings funktionen bör endast aktive ras på specifika webbplatser och bara när det är absolut obligatoriskt som kan påverka prestanda när den används felaktigt.

>[!NOTE]
>Om du använder moderna navigerings alternativ för SharePoint, till exempel menyn megapixlar, navigerings navigering eller navigering, gäller inte den här artikeln för din webbplats. Moderna SharePoint-webbplatserna har en mer förplattad Webbplatshierarki och en nav-och-eker-modell. Detta gör att många scenarier kan uppfyllas som inte kräver användning av SharePoint-publiceringen.

## <a name="overview-of-navigation-options"></a>Översikt över navigerings alternativ

Konfiguration av navigerings leverantör kan påverka prestanda avsevärt för hela webbplatsen och det är viktigt att tänka på att välja en navigations leverantör och en konfiguration som kan anpassas efter kraven på en SharePoint-webbplats. Det finns två avsluts bara navigerings leverantörer och anpassade navigerings implementeringar.

Det första alternativet, [**strukturell navigering**](#using-structural-navigation-in-sharepoint-online), är det rekommenderade navigerings alternativet i SharePoint Online för klassiska SharePoint-webbplatser **om du aktiverar cachelagring av strukturell navigering för webbplatsen**. Den här navigerings leverantören visar navigerings alternativen under den aktuella webbplatsen, och även på den aktuella webbplatsen och dess objekt. Det ger ytterligare funktioner som säkerhets trimning och uppräkning av webbplats strukturer. Om cachelagring är inaktiverat påverkar detta prestanda och skalbarhet negativt och kan komma att begränsas.

Det andra alternativet, [**hanterad navigering (metadata)**](#using-managed-navigation-and-metadata-in-sharepoint-online), representerar navigerings objekt med en term uppsättning för hanterade metadata. Vi rekommenderar att säkerhets trimning är inaktiverat om det inte behövs. Säkerhets trimning är aktiverat som standard för den här navigerings leverantören; många webbplatser kräver emellertid inte att säkerhets trimning används eftersom navigerings element ofta är konsekventa för alla användare av webbplatsen. Den rekommenderade konfigurationen för att inaktivera säkerhets optimering kräver inte att den här navigerings leverantören räknar upp webbplats strukturen och är mycket skalbar med acceptabel prestanda.

Utöver de navigerings leverantörer som inte är i kartongen har många kunder lyckats implementera alternativa anpassade navigerings implementeringar. Se [Sök drivna klient skript](#using-search-driven-client-side-scripting) i den här artikeln.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>För-och nack delar av navigerings alternativ i SharePoint Online

I följande tabell sammanfattas de olika alternativen för för-och nack delar.

|Strukturell navigering  |Hanterad navigering  |Sök drivna navigering  |Anpassad navigerings leverantör  |
|---------|---------|---------|---------|
|Tekniker<br/><br/>Lätt att underhålla<br/>Säkerhetstrimmer<br/>Uppdateringar sker automatiskt inom 24 timmar när innehållet ändras<br/>     |Tekniker<br/><br/>Lätt att underhålla<br/>|Tekniker<br/><br/>Säkerhetstrimmer<br/>Automatisk uppdatering när webbplatser läggs till<br/>Snabb inläsnings tid och lokalt cachelagrad navigerings struktur<br/>|Tekniker<br/><br/>Det finns fler tillgängliga alternativ<br/>Snabb laddning när cachelagring används korrekt<br/>Många alternativ fungerar bra med sidlayouten<br/>|
|Nack<br/><br/>**Påverkar prestanda om cachelagring är inaktiverat**<br/>Föremål för begränsning<br/>|Nack<br/><br/>Uppdateras inte automatiskt för att spegla webbplats strukturen<br/>**Påverkar prestanda om säkerhets trimning är aktiverat** eller när navigerings strukturen är komplex<br/>|Nack<br/><br/>Ingen möjlighet att enkelt ordna webbplatser<br/>Kräver anpassning av huvud sidan (tekniska kunskaper krävs)<br/>|Nack<br/><br/>Anpassad utveckling krävs<br/>Extern data källa/cache lagras, t. ex.<br/>|

Det lämpligaste alternativet för webbplatsen beror på dina webbplats krav och din tekniska funktion. Om du vill använda en lättanvänd navigerings leverantör som uppdateras automatiskt när innehållet ändras, är strukturell navigering [med cachelagring aktiverat](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) ett bra alternativ.

>[!NOTE]
>Genom att använda samma princip som moderna SharePoint-webbplatser genom att förenkla den övergripande webbplatsens struktur till en Flatter, icke hierarkisk struktur förbättras prestanda och enklare att flytta till moderna SharePoint-webbplatser. Vad det innebär är att i stället för att ha en samlad webbplats samling med hundratals webbplatser (under webbplatser), är en bättre metod att få många webbplats samlingar med mycket få under webbplatser (under webbplatser).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Analysera navigerings prestanda i SharePoint Online

[Verktyget för nätverksdiagnostik för SharePoint](https://aka.ms/perftool) är ett webb läsar tillägg för webbläsarna Microsoft Edge och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Det här verktyget fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

Verktyget genererar en rapport för varje sida som visar hur sidan fungerar mot en fördefinierad uppsättning regler och visar detaljerad information när resultaten för ett test ligger utanför bas linjen. SharePoint Online-administratörer och designer kan använda verktyget för att felsöka prestanda problem för att säkerställa att nya sidor optimeras före publiceringen.

**SPRequestDuration** är i synnerhet den tid det tar för SharePoint att bearbeta sidan. Omfattande navigering (till exempel sidor i navigering), komplexa webbplatserna och andra inställningar för konfiguration och topologi kan avsevärt bidra till längre varaktigheter.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Använda strukturell navigering i SharePoint Online

Det här är den här navigerings navigeringen som används som standard och är den enklaste lösningen. Ingen anpassning behövs och en icke-teknisk användare kan också enkelt lägga till objekt, dölja objekt och hantera navigeringen från inställnings sidan. Vi rekommenderar att du [aktiverar cachelagring](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), annars är det dyrt att kompromissa.

### <a name="how-to-implement-structural-navigation-caching"></a>Så här implementerar du cachelagring av strukturell navigering

Under **Site Settings**  >  **Look and Feel**  >  **navigerings**-och känsla kan du kontrol lera om strukturell navigering är markerat för antingen global navigering eller aktuell navigering. Att välja **Visa sidor** påverkar prestanda negativt.

![Strukturell navigering med Visa under webbplatser markerade](../media/SPONavOptionsStructuredShowSubsites.png)

Cachelagring kan aktive ras eller avaktiveras på webbplats samlings nivå och på webbplats nivå och är aktiverat för båda som standard. Aktivera på webbplats samlings nivå genom **att gå till**webbplats samlingens webbplats samlings  >  **Site Collection Administration**  >  **navigering**och markera kryss rutan för att **Aktivera cachelagring**.

![Aktivera cachelagring på webbplats nivå](../media/structural-nav/structural-nav-caching-site-coll.png)

Om du vill aktivera på webbplats nivå **Site Settings**  >  markerar du kryss rutan för **att aktivera cachelagring**under**navigering**för webbplats inställningar.

![Aktivera cachelagring på webbplats nivå](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Använda hanterad navigering och metadata i SharePoint Online

Hanterad navigering är ett annat icke-skrivskyddat alternativ som du kan använda för att återskapa de flesta av samma funktioner som strukturell navigering. Hanterade metadata kan konfigureras för att få säkerhets trimning aktive rad eller inaktive rad. När du har konfigurerat med säkerhets trimning inaktive rad är hanterad navigering ganska effektiv när du läser in alla navigations länkar med ett konstant antal Server samtal. Genom att aktivera säkerhets putsning kan du göra en del av prestanda fördelarna med hanterad navigering.

Om du behöver aktivera säkerhets trimning rekommenderar vi att du:

- Uppdatera alla egna webb adress länkar till enkla länkar
- Lägga till begärda säkerhetstrimmade noder som egna URL: er
- Begränsa antalet navigerings objekt till högst 100 och högst 3 nivåer djupt

Många webbplatser kräver inte säkerhetstrimning eftersom navigerings strukturen ofta är konsekvent för alla användare på webbplatsen. Om säkerhets trimning är inaktiverat och en länk läggs till för navigering som inte alla användare har åtkomst till, kommer länken ändå att visas men kommer att leda till ett meddelande om nekad åtkomst. Det finns ingen risk för oavsiktlig åtkomst till innehållet.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Implementera hanterad navigering och resultaten

Det finns flera artiklar om docs.microsoft.com information om hanterad navigering. Se [Översikt över hanterad navigering i SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).

För att implementera hanterad navigering kan du ange villkor med URL: er som motsvarar webbplatsens navigerings struktur. Hanterad navigering kan till och med ses manuellt för att ersätta strukturell navigering i många fall. Till exempel:

![Webbplats struktur för SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Använda Sök drivna klient skript

En vanlig klass med anpassade navigerings implementeringar omfattar klient åter givnings mönster som lagrar en lokal cache med navigeringsnoder.

Dessa navigerings leverantörer har många viktiga fördelar:

- De fungerar i allmänhet bra med sid design.
- De är oerhört skalbara och utförda eftersom de kan återges utan resurs kostnad (och uppdateras i bakgrunden efter en tids gräns).
- Dessa navigerings leverantörer kan hämta navigerings data med olika strategier, från enkla statiska konfigurationer till olika dynamiska data leverantörer.

Ett exempel på en DataProvider är att använda en **sökstyrd navigering**som gör det enklare att räkna upp navigeringsnoder och hantera säkerhets optimering.

Det finns andra populära alternativ för att bygga **anpassade navigerings leverantörer**. För mer information om hur du skapar en anpassad navigerings leverantör kan du läsa mer i [navigerings lösningarna för SharePoint online-portaler](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) .

Med Sök kan du använda de index som är inbyggda i bakgrunden med kontinuerlig crawlning. Sök resultaten hämtas från Sök indexet och resultaten blir säkerhetstrimmade. Detta är vanligt vis snabbare än ej obligatoriska navigations leverantörer när säkerhets trimning krävs. Genom att använda Sök funktionen för strukturell navigering, särskilt om du har en komplex webbplats struktur, blir det betydligt snabbare att läsa upp sidan. Den största fördelen med detta via hanterad navigering är att du har nytta av säkerhets trimning.

Den här metoden handlar om att skapa en anpassad huvud sida och ersätta den avslutande navigerings koden med anpassade HTML. Följ den här proceduren som beskrivs i följande exempel för att ersätta navigerings koden i filen `seattle.html` . I det här exemplet öppnar du `seattle.html` filen och ersätter hela elementet `id="DeltaTopNavigation"` med anpassad HTML-kod.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Exempel: ersätta den föråldrade navigerings koden på en huvud sida

1. Gå till sidan webbplats inställningar.
2. Öppna huvud sid galleriet genom att klicka på **huvud sidor**.
3. Härifrån kan du navigera i biblioteket och ladda ned filen `seattle.master` .
4. Redigera koden med en text redigerare och ta bort kod blocket i följande skärm bild.<br/>![Ta bort det kodblock som visas](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Ta bort koden mellan `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` taggarna och och ersätt den med följande kod avsnitt:<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. Ersätt URL-adressen i början av bildens fäst punkt med en länk till en inläsnings bild i webbplats samlingen. När du har gjort ändringarna byter du namn på filen och överför den sedan till galleriet för huvud sidor. Då skapas en ny huvud fil.<br/>
7. Den här HTML-koden är den bas märkning som kommer att fyllas i med Sök resultaten från JavaScript-koden. Du måste redigera koden för att ändra värdet för Variansens rot = "URL-adress för webbplats samling" enligt följande kod utdrag:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Resultatet tilldelas till själv. Arrays-matrisen och en hierarki är inbyggd av objekten genom att linq.js tilldelar utdata till en matris själv. hierarki. Den här matrisen är det objekt som är bundet till HTML. Det här görs i funktionen toggleView () genom att skicka det Self-objektet till funktionen ko. applyBinding ().<br/>Då blir hierarki-matrisen bunden till följande HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Händelse hanterarna för `mouseenter` och `mouseexit` läggs till i navigering på översta nivån för att hantera de nedrullningsbara menyn under webbplatser som görs i `addEventsToElements()` funktionen.

I vårt komplexa navigerings exempel visas en ny sid belastning utan lokal cachelagring för att visa hur lång tid det tog för servern att få ett liknande resultat som den hanterade navigeringen.

### <a name="about-the-javascript-file"></a>Om JavaScript-filen...

>[!NOTE]
>Om du använder anpassat Java Script kontrollerar du att offentlig CDN är aktiverat och att filen är på en CDN-plats.

Hela JavaScript-filen ser ut så här:

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

Om du vill summera koden ovan i `jQuery $(document).ready` funktionen är en `viewModel object` skapad och sedan `loadNavigationNodes()` funktionen för det objektet. Med den här funktionen laddas antingen den tidigare skapade navigerings hierarkin i den lokala HTML5-lagringen i klient webbläsaren eller så anropas funktionen `queryRemoteInterface()` .

`QueryRemoteInterface()` skapar en begäran med `getRequest()` funktionen med den frågeparameter som definierats tidigare i skriptet och returnerar sedan data från servern. Dessa data är i stort sett en matris med alla webbplatser i webbplats samlingen som representerar data överförings objekt med olika egenskaper.

Dessa data parsas sedan till de tidigare definierade `SPO.Models.NavigationNode` objekten som används `Knockout.js` för att skapa observerbara egenskaper för data bindning till den HTML-kod som vi definierade tidigare.

Objekten placeras i en resultat mat ris. Den här matrisen tolkas i JSON med blockering och lagras i den lokala webbläsarens lagrings utrymme för bättre prestanda på framtida sid inläsningar.

### <a name="benefits-of-this-approach"></a>Fördelar med den här metoden

En stor fördel med [den här metoden](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) är att med hjälp av HTML5 lokal lagring sparas navigeringen lokalt för användaren nästa gång de läser in sidan. Vi får viktiga förbättringar av prestandan genom att använda Sök-API: t för strukturell navigering. men det tar lite teknisk möjlighet att köra och anpassa den här funktionen.

I [exemplet med implementeringen](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)ordnas webbplatserna på samma sätt som i den nedrullningsbara strukturell navigeringen. alfabetisk ordning. Om du vill avvika från den här ordningen blir det mer komplicerat att utveckla och underhålla. Dessutom kräver den här metoden att du avviker från huvud sidorna som stöds. Om den anpassade huvud sidan inte är underordnad missar webbplatsen uppdateringar och förbättringar som Microsoft gör till huvud sidorna.

[Koden ovan](#about-the-javascript-file) har följande beroenden:

- jQuery https://jquery.com/
- KnockoutJS https://knockoutjs.com/
- Linq.js- https://linqjs.codeplex.com/ eller github.com/neuecc/linq.js

Den aktuella versionen av LinqJS innehåller inte den ByHierarchy-metod som används i ovanstående kod och delar navigerings koden. Lös det genom att lägga till följande metod i Linq.js-filen före raden `Flatten: function ()` .

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>Relaterade ämnen

[Översikt över hanterad navigering i SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[Cachelagring och prestanda för strukturell navigering](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
