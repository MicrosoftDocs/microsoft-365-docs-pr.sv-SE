---
title: Använda Office 365 innehålls leverans nätverk (CDN) med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
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
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Lär dig hur du använder Office 365 Content Delivery Network (CDN) för att påskynda leveransen av dina SharePoint Online-till gångar.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694341"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online

Du kan använda det inbyggda Office-365 innehålls leverans nätverk (CDN) för att hantera statiska till gångar för bättre prestanda för SharePoint Online-sidorna. Office 365 CDN förbättrar prestandan genom att cachelagra statiska till gångar i webbläsare som begär dem, vilket hjälper dig att påskynda nedladdningen och minska svars tiden. Dessutom använder Office 365 CDN [http/2](https://en.wikipedia.org/wiki/HTTP/2) för förbättrad komprimering och http-försäljning. Office 365 CDN-tjänsten är inkluderad som en del av SharePoint Online-prenumerationen.

> [!NOTE]
> Office 365 CDN är bara tillgängligt för klient organisationer i **produktions** -molnet (världen över). Klient organisationer i Förenta staternas myndigheter, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

Office 365 CDN består av flera CDN som låter dig hantera fasta till gångar på flera platser, eller _ursprung_, och betjäna dem från globala nätverk med snabb hastighet. Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till **offentliga** ursprung, **privata** ursprung eller båda. Se [välja om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) för mer information om skillnaden mellan offentliga och privata ursprung.

![Office 365 CDN-koncept diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-koncept diagram")

Om du redan är bekant med hur CDN fungerar behöver du bara utföra några steg för att aktivera Office 365 CDN för din klient organisation. I det här avsnittet beskrivs hur. Läs mer om hur du kommer igång med dina statiska till gångar.

> [!TIP]
> Det finns andra Microsoft-värdbaserade CDN som kan användas med Office 365 för specialiserade användnings scenarier, men diskuteras inte i det här avsnittet eftersom de ligger utanför omfattningen av Office 365 CDN. Mer information finns i [andra Microsoft-CDN](content-delivery-networks.md#other-microsoft-cdns).

 **Gå tillbaka till [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Översikt över hur du arbetar med Office 365 CDN i SharePoint Online

Följ de här grundläggande stegen för att konfigurera Office 365 CDN för din organisation:

+ [Planera för distribution av Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Avgöra vilka statiska till gångar som du vill använda i CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Bestäm var du vill lagra dina till gångar](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Denna plats kan vara en SharePoint-webbplats, ett bibliotek eller en mapp och kallas för ett _ursprung_.
  + [Välj om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate). Du kan lägga till flera ursprung för både offentliga och privata typer.

+ Konfigurera och konfigurera CDN med antingen PowerShell eller SharePoint Online-CLI

  + [Konfigurera och konfigurera CDN genom att använda SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Konfigurera och konfigurera CDN med hjälp av PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Konfigurera och konfigurera CDN med hjälp av Office 365-CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  När du är klar med det här steget har du:

  + Aktiverat CDN för din organisation.
  + Lade till dina ursprung och identifierar varje ursprung som offentligt eller privat.

När du är klar med konfigurationen kan du [Hantera Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) över tiden genom att:
  
+ Lägga till, uppdatera och ta bort till gångar
+ Lägga till och ta bort ursprung
+ Konfigurera CDN-principer
+ Vid behov kan du avaktivera CDN

Slutligen kan du läsa om hur du [använder CDN-till](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) gångar från både offentliga och privata ursprung.

Se [fel sökning av Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) för vägledning för lösning av vanliga problem.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planera för distribution av Office 365 CDN

Innan du distribuerar Office 365 CDN för din Office 365-klient bör du tänka på följande faktorer som en del av planerings processen.

  + [Avgöra vilka statiska till gångar som du vill använda i CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestämma var du vill spara till gångarna](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Välja om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Avgöra vilka statiska till gångar som du vill använda i CDN

I allmänhet är CDN mest effektiva för att vara värd för _fasta till gångar_eller till gångar som inte ändras ofta. En bra tumregel är att identifiera filer som uppfyller vissa eller samtliga av dessa villkor:

+ Statiska filer som bäddats in på en sida (till exempel skript och bilder) som kan ha avsevärda effekter på sid inläsnings tider
+ Stora filer, till exempel körbara filer och installationsfiler
+ Resurs bibliotek med stöd för klientbaserade koder

Till exempel kan små filer som är upprepade gånger begärda med webbplats bilder och skript förbättra prestandan för webbplats åter givningen och inkrementellt minska belastningen på SharePoint Online-webbplatserna när du lägger till dem i ett CDN-ursprung. Större filer, till exempel körbara installations program, kan hämtas från CDN och ger en positiv effekt som påverkar belastningen på SharePoint Online-webbplatsen även om de inte är tillgängliga så ofta.

Förbättring av prestanda på en fil är beroende av många faktorer, inklusive klientens närhet till närmaste CDN-slutpunkt, tillfälliga förhållanden i det lokala nätverket. Många statiska filer är ganska små och kan laddas ned från Office 365 på mindre än en sekund. En webb sida kan innehålla många inbäddade filer med en kumulativ nedladdnings tid på flera sekunder. Om du betjänar dessa filer från CDN kan det avsevärt minska sid inläsnings tiden. Se [vilka resultat vinster ett CDN tillhandahåller?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) för ett exempel.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bestämma var du vill spara till gångarna

CDN hämtar dina till gångar från en plats som kallas _ursprung_. Ett ursprung kan vara en SharePoint-webbplats, ett dokument bibliotek eller en mapp som är tillgänglig via en URL-adress. Du har stor flexibilitet när du anger ursprung för din organisation. Du kan till exempel ange flera ursprung eller ett enda ursprung där du vill lägga till alla dina CDN-till gångar. Du kan välja att ha både offentliga eller privata ursprung för organisationen. De flesta organisationer väljer att implementera en kombination av båda.

Du kan skapa en ny behållare för dina ursprung, till exempel mappar eller dokument bibliotek, och lägga till filer som du vill göra tillgängliga från CDN. Det här är en bra metod om du har en specifik uppsättning till till gångar som du vill ska vara tillgängliga från CDN och bara vill begränsa uppsättningen av CDN-till gångar till filerna i behållaren.

Du kan också konfigurera en befintlig webbplats samling, en webbplats, ett bibliotek eller en mapp som ursprung, som gör alla godkända till gångar i behållaren tillgängliga från CDN. Innan du lägger till en befintlig behållare som ett ursprung är det viktigt att se till att du är medveten om dess innehåll och behörigheter så att du inte oavsiktligt exponerar till gångar för anonym åtkomst eller obehöriga användare.

Du kan definiera _CDN-principer_ för att exkludera innehåll i ursprungen från CDN. CDN-principer exkluderar till gångar i offentliga eller privata ursprung utifrån attribut som _filtyp_ och _webbplats klassificering_och tillämpas på alla ursprung i CdnType (privat eller offentlig) som du anger i principen. Om du till exempel lägger till ett privat ursprung som består av en webbplats som innehåller flera under webbplatser kan du definiera en princip som utesluter webbplatser som är markerade som **hemliga** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN. Policyn gäller för innehåll från _alla_ privata ursprung som du har lagt till i CDN.
  
Kom ihåg att det större antalet ursprung, desto större är effekten på den tid det tar för CDN-tjänsten att bearbeta förfrågningar. Vi rekommenderar att du begränsar antalet ursprung så mycket som möjligt.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Välja om varje ursprung ska vara offentligt eller privat

När du identifierar ett ursprung anger du om det ska göras _offentligt_ eller _privat_. Åtkomst till CDN-till gångar i offentliga ursprung är anonymt och CDN-innehåll i privata ursprung skyddas genom dynamiskt genererade token för ökad säkerhet. Oavsett vilket alternativ du väljer gör Microsoft all den tungan när det gäller administrationen av själva CDN. Du kan också ändra dina tankar senare, efter att du har konfigurerat CDN och identifierat dina ursprung.

Både offentliga och privata alternativ ger liknande prestanda vinster men alla har unika attribut och fördelar.

**Offentliga** ursprung i Office 365 CDN är tillgängliga anonymt och värdbaserade till gångar kan nås av alla som har URL-adressen till till gången. Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du endast använda dem för att cachelagra icke-känsligt allmänt innehåll, till exempel JavaScript-filer, skript, ikoner och bilder.

**Privata** ursprung i Office 365 CDN ger privat åtkomst till användar innehåll som SharePoint Online-dokumentbibliotek, webbplatser och grafik. Åtkomst till innehåll i privata ursprung skyddas genom dynamiskt genererade token så att användare som har behörighet till det ursprungliga dokument biblioteket eller lagrings platsen endast kan komma åt det. Privata ursprung i Office 365 CDN kan endast användas till till gångar i privata ursprung genom omdirigering från din SharePoint Online-klient.

Du kan läsa mer om hur CDN får åtkomst till till gångar i ett privat ursprung i [använda till gångar i privata ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attribut och fördelar med att låta till gångar i offentliga ursprung
  
+ Till gångar som är utsatta med offentligt ursprung är tillgängliga för alla anonymt.
    > [!IMPORTANT]
    > Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.
+ Om du tar bort en till gång från ett offentligt ursprung kan till gången fortsätta vara tillgänglig i upp till 30 dagar från cachen; Vi kommer inte att validera länkar till till gången i CDN inom 15 minuter.
+ När du är värd för formatmallar (CSS-filer) i ett offentligt ursprung kan du använda relativa sökvägar och URI: er i koden. Det innebär att du kan referera till platsen för bakgrunds bilder och andra objekt i förhållande till den plats där den som ringer till till gången finns.
+ Vi rekommenderar inte att du använder en fast kod för ett offentligt ursprung. Anledningen till detta är att om åtkomsten till CDN inte är tillgänglig kommer URL-adressen inte automatiskt att lösas till din organisation i SharePoint Online och kan leda till felaktiga länkar och andra fel.
+ De standard fil typer som ingår i offentliga ursprung är. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. SVG,. ttf,. WOFF och. woff2. Du kan ange Ytterligare filtyper.
+ Du kan konfigurera en princip för att exkludera till gångar som identifieras av webbplats klassificeringar som du anger. Du kan till exempel välja att exkludera alla till gångar som är markerade som "konfidentiella" eller "begränsade" även om de är en tillåten filtyp och är placerade i ett offentligt ursprung.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attribut och fördelar med att vara värd för till gångar i privata ursprung

+ Privata ursprung kan endast användas för SharePoint Online-till gångar.
+ Användare kan bara komma åt till gångar från ett privat ursprung om de har behörighet att komma åt behållaren. Anonym åtkomst till dessa till gångar förhindras.
+ Till gångar i privata ursprung måste hänvisas till i SharePoint Online-klient organisationen. Direkt åtkomst till privata CDN-objekt fungerar inte.
+ Om du tar bort en till gång från privat ursprung kan till gången fortsätta vara tillgänglig för upp till en timme från cachen; Vi kommer att validera länkar till till gången i CDN inom 15 minuter efter det att du har avlägsnat den.
+ De standard fil typer som ingår i privata ursprung är. gif,. ico,. jpeg,. jpg,. js och. png. Du kan ange Ytterligare filtyper.
+ Precis som med offentliga ursprung kan du konfigurera en princip för att exkludera till gångar som identifieras av webbplats klassificeringar som du anger även om du använder jokertecken för att inkludera alla till gångar i en mapp eller ett dokument bibliotek.

Mer information om varför du ska använda Office 365 CDN, allmänna CDN-begreppen och andra Microsoft-CDN som du kan använda med Office 365-klient organisationen finns i avsnittet [innehålls leverans nätverk](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Standard ursprung för CDN

Om du inte anger något annat kommer Office 365 att ställa in vissa standard ursprung när du aktiverar Office 365 CDN. Om du inte har avaktiverat dem kan du lägga till dessa ursprung när du har slutfört installationen. Om du inte förstår följderna av att hoppa över inställningen av standard ursprung och har särskilda skäl för att göra det, bör du tillåta att dessa skapas när du aktiverar CDN.
  
Standard privata CDN-ursprung:
  
+ \*/userphoto.aspx
+ \*/siteassets

Standard allmänna CDN-ursprung:
  
+ \*/masterpage
+ \*/Style-bibliotek
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ är ett offentligt standard ursprung som lagts till i Office 365 CDN-tjänsten i december 2017. Detta måste finnas för att SharePoint Framework-lösningarna i CDN ska fungera. Om du har aktiverat Office 365 CDN före den 2017 december, eller om du hoppat över installationen av standard ursprung när du aktiverade CDN, kan du manuellt lägga till det här ursprunget. Mer information finns i min webbdel för [klient-eller SharePoint-ramverk fungerar inte](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Konfigurera och konfigurera Office 365 CDN med hjälp av SharePoint Online Management Shell

Procedurerna i det här avsnittet kräver att du använder SharePoint Online Management Shell för att ansluta till SharePoint Online. Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Utför de här stegen för att konfigurera och konfigurera CDN så att dina till gångar i SharePoint Online används med SharePoint Online Management Shell.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivera din organisation för att använda Office 365 CDN

Innan du ändrar status för klient organisationen måste du hämta den aktuella statusen för privat CDN-konfigurationen i Office 365-klient organisationen. Anslut till klient organisationen med SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Använd cmdleten **Get-SPOTenantCdnEnabled** för att hämta status inställningar för CDN från klient organisationen:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Statusen för CDN för angiven CdnType kommer att matas ut till skärmen.

Använd cmdleten **set-SPOTenantCdnEnabled** för att göra det möjligt för organisationen att använda Office 365 CDN. Du kan göra det möjligt för organisationen att använda offentliga ursprung, privata ursprung eller båda samtidigt. Du kan också konfigurera CDN för att hoppa över inställningen av standard ursprung när du aktiverar det. Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.
  
I Windows PowerShell för SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Om du till exempel vill aktivera organisationen att använda både offentliga och privata ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Om du vill göra det möjligt för organisationen att använda både offentliga och privata ursprung men hoppa till standard ursprungen skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN och den potentiella effekten av att hoppa över inställningen av standard ursprung.

Om du vill aktivera organisationen att använda offentliga ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Om du vill aktivera din organisation att använda privata ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Mer information om den här cmdleten finns i [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)

> [!TIP]
> När du definierar filtyper med hjälp av cmdleten **set-SPOTenantCdnPolicy** skriver du över den för tillfället definierade listan. Om du vill lägga till fler filtyper i listan kan du använda cmdleten först för att ta reda på vilka filtyper som redan är tillåtna och lägga till dem i listan tillsammans med nya filer.
  
Använd cmdleten **set-SPOTenantCdnPolicy** för att definiera statiska filtyper som kan hanteras av offentliga och privata ursprung i CDN. Som standard tillåts vanliga typer av till gångar, till exempel. CSS,. gif,. jpg och. js.

I Windows PowerShell för SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Om du till exempel vill aktivera CDN som Host. CSS-och. png-filer anger du kommandot:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Använd cmdleten **Get-SPOTenantCdnPolicies** för att se vilka filtyper som för närvarande tillåts av CDN:

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Mer information om dessa cmdletar finns i [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN (valfritt)

> [!TIP]
> När du undantar webbplats klassificeringar med cmdleten **set-SPOTenantCdnPolicy** skriver du över den för tillfället definierade listan. Om du vill undanta ytterligare webbplats klassificeringar kan du använda cmdleten först för att ta reda på vilka klassificeringar som redan är undantagna och sedan lägga till dem tillsammans med dina nya.

Använd cmdleten **set-SPOTenantCdnPolicy** för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN. Som standard utesluts inga webbplats klassificeringar.

I Windows PowerShell för SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Om du vill se vilka webbplats klassificeringar som är begränsade använder du cmdleten **Get-SPOTenantCdnPolicies** :

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

De egenskaper som kommer att returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ och _ExcludeIfNoScriptDisabled_.

Egenskapen _IncludeFileExtensions_ innehåller en lista över fil namns tillägg som kommer att betjänas från CDN.

> [!NOTE]
> Standard fil namns tilläggen skiljer sig mellan offentliga och privata.

Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller de webbplats klassificeringar som du vill undanta från CDN. Du kan till exempel utesluta webbplatser som marker ATS som **konfidentiella** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN.

Egenskapen _ExcludeIfNoScriptDisabled_ exkluderar innehåll från CDN baserat på Inställningar för _NoScript_ på webbplats nivå. Som standard är attributet _NoScript_ **aktiverat** för _moderna_ webbplatser och är **inaktiverat** för _klassiska_ webbplatser. Detta beror på klientens inställningar.

Mer information om dessa cmdletar finns i [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Lägga till ett ursprung för dina till gångar

Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera ett ursprung. Du kan definiera flera ursprung. Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.
  
> [!IMPORTANT]
> Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Värdet för _Path_ är den relativa sökvägen till det bibliotek eller den mapp som innehåller till gångarna. Du kan använda jokertecken utöver relativa sökvägar. Ursprung stöd för jokertecken läggs till till URL-adressen. Det gör att du kan skapa ursprung som sträcker sig över flera webbplatser. Om du till exempel vill ta med alla till gångar i masterpages-mappen för alla webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Jokertecknet * **/** kan bara användas i början av sökvägen och matchar alla URL-segment under den angivna URL-adressen.
+ Sökvägen kan peka på ett dokument bibliotek, en mapp eller en webbplats. Till exempel matchar sökvägen _*/site1_ alla dokument bibliotek under webbplatsen.

Du kan lägga till ett ursprung med en specifik relativ sökväg. Du kan inte lägga till ett ursprung med den fullständiga sökvägen.

I det här exemplet läggs ett privat ursprung för siteassets-biblioteket till på en specifik webbplats:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Det här exemplet lägger till ett privat ursprung i mappen _Mapp1_ i webbplats samlingens webbplats till gångar-bibliotek:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Om det finns ett blank steg i sökvägen kan du antingen omge vägen med citat tecken eller ersätta blank steget med URL-kodningen %20. Följande exempel lägger till ett privat ursprung för _mappen 1_ i webbplats samlingens webbplats till gångar-bibliotek:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

> [!NOTE]
> I privata ursprung måste till gångar som delas från ett ursprung ha en huvud version publicerad innan de kan nås från CDN.
  
När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exempel: Konfigurera ett offentligt ursprung för huvud sidorna och för format biblioteket för SharePoint Online

Vanligt vis är dessa ursprung för dig som standard när du aktiverar Office 365 CDN. Om du vill aktivera dem manuellt följer du de här stegen.
  
+ Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera format biblioteket som ett offentligt ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera huvud sidorna som ett offentligt ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för webbplats till gångar, webbplats sidor och publicerings bilder för SharePoint Online

+ Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för webbplats till gångar som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för webbplats sidor som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera mappen för publicerings bilder som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för en webbplats samling för SharePoint Online

Använd cmdleten **Add-SPOTenantCdnOrigin** för att definiera en webbplats samling som ett privat ursprung. Till exempel:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Mer information om det här kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).
  
När du har kört kommandot synkroniseras konfigurationen via data Center. Du kan se ett meddelande om _väntande konfiguration_ som förväntas som en SharePoint Online-klient ansluter till CDN-tjänsten. Det kan ta upp till 15 minuter.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Hantera Office 365 CDN

När du har konfigurerat CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Lägga till, uppdatera eller ta bort till gångar från Office 365 CDN

När du har slutfört konfigurations stegen kan du lägga till nya till gångar och uppdatera eller ta bort befintliga till gångar när du vill. Gör dina ändringar i till gångarna i den mapp eller det SharePoint-bibliotek som du angav som ursprung. Om du lägger till en ny till gång är den tillgänglig via CDN omedelbart. Men om du uppdaterar till gången tar det upp till 15 minuter innan den nya kopian sprids och blir tillgänglig i CDN.
  
Om du behöver hämta plats för ursprunget kan du använda cmdleten **Get-SPOTenantCdnOrigins** . Information om hur du använder denna cmdlet finns i [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Ta bort ett ursprung från Office 365 CDN

Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ett ursprung. För att göra det, Använd cmdleten **Remove-SPOTenantCdnOrigin** .

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Information om hur du använder den här cmdleten finns i [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändra ett ursprung i Office 365 CDN

Du kan inte ändra ett ursprung som du har skapat. I stället kan du ta bort Origo och sedan lägga till ett nytt. Mer information finns i [så här tar du bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) och hur [du lägger till till gångar](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Använd cmdleten **set-SPOTenantCdnEnabled** för att inaktivera CDN för organisationen. Om både offentliga och privata ursprung är aktiverade för CDN måste du köra cmdleten två gånger enligt följande exempel.
  
Om du vill inaktivera användning av offentliga ursprung i CDN skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Om du vill inaktivera användningen av de privata ursprungen i CDN skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Mer information om den här cmdleten finns i [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Konfigurera och konfigurera Office 365 CDN med PnP PowerShell

Procedurerna i det här avsnittet kräver att du använder PnP PowerShell för att ansluta till SharePoint Online. Anvisningar finns i [komma igång med PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Utför de här stegen för att konfigurera och konfigurera CDN för att hantera dina till gångar i SharePoint Online med hjälp av PnP PowerShell.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivera din organisation för att använda Office 365 CDN

Innan du ändrar status för klient organisationen måste du hämta den aktuella statusen för privat CDN-konfigurationen i Office 365-klient organisationen. Ansluta till klient organisationen med PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Använd cmdleten **Get-PnPTenantCdnEnabled** för att hämta status inställningar för CDN från klient organisationen:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Statusen för CDN för angiven CdnType kommer att matas ut till skärmen.

Använd cmdleten **set-PnPTenantCdnEnabled** för att göra det möjligt för organisationen att använda Office 365 CDN. Du kan göra det möjligt för organisationen att använda offentliga ursprung, privata ursprung eller båda samtidigt. Du kan också konfigurera CDN för att hoppa över inställningen av standard ursprung när du aktiverar det. Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.
  
I PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Om du till exempel vill aktivera organisationen att använda både offentliga och privata ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Om du vill göra det möjligt för organisationen att använda både offentliga och privata ursprung men hoppa till standard ursprungen skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN och den potentiella effekten av att hoppa över inställningen av standard ursprung.

Om du vill aktivera organisationen att använda offentliga ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Om du vill aktivera din organisation att använda privata ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Mer information om den här cmdleten finns i [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)

> [!TIP]
> När du definierar filtyper med hjälp av cmdleten **set-PnPTenantCdnPolicy** skriver du över den för tillfället definierade listan. Om du vill lägga till fler filtyper i listan kan du använda cmdleten först för att ta reda på vilka filtyper som redan är tillåtna och lägga till dem i listan tillsammans med nya filer.
  
Använd cmdleten **set-PnPTenantCdnPolicy** för att definiera statiska filtyper som kan hanteras av offentliga och privata ursprung i CDN. Som standard tillåts vanliga typer av till gångar, till exempel. CSS,. gif,. jpg och. js.

I PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Om du till exempel vill aktivera CDN som Host. CSS-och. png-filer anger du kommandot:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Använd cmdleten **Get-PnPTenantCdnPolicies** för att se vilka filtyper som för närvarande tillåts av CDN:

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Mer information om dessa cmdletar finns i [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN (valfritt)

> [!TIP]
> När du undantar webbplats klassificeringar med cmdleten **set-PnPTenantCdnPolicy** skriver du över den för tillfället definierade listan. Om du vill undanta ytterligare webbplats klassificeringar kan du använda cmdleten först för att ta reda på vilka klassificeringar som redan är undantagna och sedan lägga till dem tillsammans med dina nya.

Använd cmdleten **set-PnPTenantCdnPolicy** för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN. Som standard utesluts inga webbplats klassificeringar.

I PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Om du vill se vilka webbplats klassificeringar som är begränsade använder du cmdleten **Get-PnPTenantCdnPolicies** :

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

De egenskaper som kommer att returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ och _ExcludeIfNoScriptDisabled_.

Egenskapen _IncludeFileExtensions_ innehåller en lista över fil namns tillägg som kommer att betjänas från CDN.

> [!NOTE]
> Standard fil namns tilläggen skiljer sig mellan offentliga och privata.

Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller de webbplats klassificeringar som du vill undanta från CDN. Du kan till exempel utesluta webbplatser som marker ATS som **konfidentiella** så att innehållet från webbplatser med den klassificeringen inte kommer att betjänas från CDN.

Egenskapen _ExcludeIfNoScriptDisabled_ exkluderar innehåll från CDN baserat på Inställningar för _NoScript_ på webbplats nivå. Som standard är attributet _NoScript_ **aktiverat** för _moderna_ webbplatser och är **inaktiverat** för _klassiska_ webbplatser. Detta beror på klientens inställningar.

Mer information om dessa cmdletar finns i [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Lägga till ett ursprung för dina till gångar

Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera ett ursprung. Du kan definiera flera ursprung. Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.
  
> [!IMPORTANT]
> Du bör aldrig placera resurser som innehåller användar information eller anses vara känsliga för organisationen i ett offentligt ursprung.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Värdet för _Path_ är den relativa sökvägen till det bibliotek eller den mapp som innehåller till gångarna. Du kan använda jokertecken utöver relativa sökvägar. Ursprung stöd för jokertecken läggs till till URL-adressen. Det gör att du kan skapa ursprung som sträcker sig över flera webbplatser. Om du till exempel vill ta med alla till gångar i masterpages-mappen för alla webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Jokertecknet * **/** kan bara användas i början av sökvägen och matchar alla URL-segment under den angivna URL-adressen.
+ Sökvägen kan peka på ett dokument bibliotek, en mapp eller en webbplats. Till exempel matchar sökvägen _*/site1_ alla dokument bibliotek under webbplatsen.

Du kan lägga till ett ursprung med en specifik relativ sökväg. Du kan inte lägga till ett ursprung med den fullständiga sökvägen.

I det här exemplet läggs biblioteket webbplats till gångar till på en specifik webbplats:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Det här exemplet lägger till ett privat ursprung i mappen _Mapp1_ i webbplats samlingens webbplats till gångar-bibliotek:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Om det finns ett blank steg i sökvägen kan du antingen omge vägen med citat tecken eller ersätta blank steget med URL-kodningen %20. Följande exempel lägger till ett privat ursprung för _mappen 1_ i webbplats samlingens webbplats till gångar-bibliotek:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> I privata ursprung måste till gångar som delas från ett ursprung ha en huvud version publicerad innan de kan nås från CDN.
  
När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exempel: Konfigurera ett offentligt ursprung för huvud sidorna och för format biblioteket för SharePoint Online

Vanligt vis är dessa ursprung för dig som standard när du aktiverar Office 365 CDN. Om du vill aktivera dem manuellt följer du de här stegen.
  
+ Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera format biblioteket som ett offentligt ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera huvud sidorna som ett offentligt ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för webbplats till gångar, webbplats sidor och publicerings bilder för SharePoint Online

+ Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för webbplats till gångar som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för webbplats sidor som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera mappen för publicerings bilder som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

När du har kört kommandot synkroniseras konfigurationen via data Center. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för en webbplats samling för SharePoint Online

Använd cmdleten **Add-PnPTenantCdnOrigin** för att definiera en webbplats samling som ett privat ursprung. Till exempel:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Mer information om det här kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
När du har kört kommandot synkroniseras konfigurationen via data Center. Du kan se ett meddelande om _väntande konfiguration_ som förväntas som en SharePoint Online-klient ansluter till CDN-tjänsten. Det kan ta upp till 15 minuter.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Hantera Office 365 CDN

När du har konfigurerat CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Lägga till, uppdatera eller ta bort till gångar från Office 365 CDN

När du har slutfört konfigurations stegen kan du lägga till nya till gångar och uppdatera eller ta bort befintliga till gångar när du vill. Gör dina ändringar i till gångarna i den mapp eller det SharePoint-bibliotek som du angav som ursprung. Om du lägger till en ny till gång är den tillgänglig via CDN omedelbart. Men om du uppdaterar till gången tar det upp till 15 minuter innan den nya kopian sprids och blir tillgänglig i CDN.
  
Om du behöver hämta plats för ursprunget kan du använda cmdleten **Get-PnPTenantCdnOrigin** . Information om hur du använder denna cmdlet finns i [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Ta bort ett ursprung från Office 365 CDN

Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ett ursprung. För att göra det, Använd cmdleten **Remove-PnPTenantCdnOrigin** .

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Information om hur du använder den här cmdleten finns i [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändra ett ursprung i Office 365 CDN

Du kan inte ändra ett ursprung som du har skapat. I stället kan du ta bort Origo och sedan lägga till ett nytt. Mer information finns i [så här tar du bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) och hur [du lägger till till gångar](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Använd cmdleten **set-PnPTenantCdnEnabled** för att inaktivera CDN för organisationen. Om både offentliga och privata ursprung är aktiverade för CDN måste du köra cmdleten två gånger enligt följande exempel.
  
Om du vill inaktivera användning av offentliga ursprung i CDN skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Om du vill inaktivera användningen av de privata ursprungen i CDN skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Mer information om den här cmdleten finns i [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Konfigurera och konfigurera Office 365 CDN med Office 365-CLI

Procedurerna i det här avsnittet kräver att du har installerat [Office 365-CLI](https://aka.ms/o365cli). Anslut sedan till Office 365-klient organisationen med kommandot [Logga in](https://pnp.github.io/office365-cli/cmd/login/) .

Utför de här stegen för att konfigurera och konfigurera CDN så att du kan vara värd för dina till gångar i SharePoint Online med hjälp av Office 365-CLI.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-the-office-365-cdn"></a>Aktivera Office 365 CDN

Du kan hantera statusen för Office 365 CDN i klient organisationen med kommandot [SPO CDN set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) .

Så här aktiverar du Office 365 Public CDN i klient organisationen:

```sh
spo cdn set --type Public --enabled true
```

Aktivera Office 365 SharePoint CDN genom att köra:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Visa aktuell status för Office 365 CDN

Om du vill kontrol lera om den särskilda typen av Office 365 CDN är aktiverat eller inaktive rad använder du kommandot [SPO CDN get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .

Så här kontrollerar du om Office 365 Public CDN är aktiverat:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visa Office 365 CDN-ursprung

Så här visar du de aktuella konfigurerade Office 365 Public CDN-ursprungen kör:

```sh
spo cdn origin list --type Public
```

Se [standard ursprung för CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som är etablerade som standard när du aktiverar Office 365 CDN.

### <a name="add-an-office-365-cdn-origin"></a>Lägga till ett Office 365 CDN-ursprung

> [!IMPORTANT]
> Du bör aldrig placera resurser som anses vara känsliga för organisationen i ett SharePoint-dokumentbibliotek som är konfigurerat som ett offentligt ursprung.

Använd kommandot [SPO CDN Origin Add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) för att definiera ett CDN-ursprung. Du kan definiera flera ursprung. Origo är en URL som pekar på ett SharePoint-bibliotek eller en mapp som innehåller de objekt som du vill ska hanteras av CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Var `path` finns den relativa sökvägen till mappen som innehåller till gångarna. Du kan använda jokertecken utöver relativa sökvägar.

Om du vill inkludera alla till gångar i **huvud sid galleriet** på alla webbplatser som ett offentligt ursprung kör du:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Om du vill konfigurera ett privat ursprung för en viss webbplats samling kör du:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> När du har lagt till ett CDN-ursprung kan det ta upp till 15 minuter innan du kan hämta filer via CDN-tjänsten. Du kan kontrol lera om det specifika ursprungs ursprunget redan har Aktiver ATS med kommandot [SPO CDN Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) .

### <a name="remove-an-office-365-cdn-origin"></a>Ta bort ett Office 365 CDN-ursprung

Använd kommandot [SPO CDN Origin ta bort](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) om du vill ta bort ett CDN-ursprung för den angivna CDN-typen.

Om du vill ta bort ett offentligt ursprung från CDN-konfigurationen kör du:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Om du tar bort ett CDN-ursprung påverkas inte filerna som lagras i ett dokument bibliotek som matchar ursprunget. Om de här till gångarna har refererats till med deras SharePoint-URL växlar SharePoint automatiskt tillbaka till den ursprungliga URL-adressen som pekar på dokument biblioteket. Om till gångar har refererats till med en offentlig CDN-URL kommer länken att brytas och du måste ändra dem manuellt.

### <a name="modify-an-office-365-cdn-origin"></a>Ändra ett Office 365 CDN-ursprung

Det går inte att ändra ett befintligt CDN-ursprung. I stället bör du ta bort det tidigare definierade CDN-ursprunget med `spo cdn origin remove` kommandot och lägga till ett nytt med `spo cdn origin add` kommandot.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Ändra vilka typer av filer som ska ingå i Office 365 CDN

Följande filtyper ingår som standard i CDN: _. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. SVG,. ttf,. WOFF och. woff2_. Om du behöver ta med fler filtyper i CDN kan du ändra CDN-konfigurationen med hjälp av [SPO CDN-princip uppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) .

> [!NOTE]
> När du ändrar listan med filtyper skriver du över den för tillfället definierade listan. Om du vill inkludera fler filtyper måste du först använda kommandot [SPO CDN policy List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) för att ta reda på vilka filtyper som är konfigurerade för tillfället.

Om du vill lägga till _JSON_ -filtypen i standard listan med filtyper som ingår i Public CDN kör du:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Ändra listan över webbplats klassificeringar som du vill undanta från Office 365 CDN

Använd kommandot [SPO CDN-princip uppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) för att undanta webbplats klassificeringar som du inte vill göra tillgängliga via CDN. Som standard utesluts inga webbplats klassificeringar.

> [!NOTE]
> När du ändrar listan med undantagna webbplats klassificeringar skriver du över den för tillfället definierade listan. Om du vill undanta ytterligare klassificeringar bör du först använda kommandot [SPO CDN policy List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) för att ta reda på vilka klassificeringar som för tillfället är konfigurerade.

Om du vill undanta webbplatser som klassificerats som _HBI_ från Public CDN kör du

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Så här inaktiverar du Office 365 CDN Använd `spo cdn set` kommandot, till exempel:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Använda dina CDN-till gångar

Nu när du har aktiverat CDN och konfigurerat ursprung och policy kan du börja använda dina CDN-till gångar.

I det här avsnittet får du lära dig hur du använder CDN-URL: er på dina SharePoint-sidor och-innehåll så att SharePoint dirigerar om förfrågningar till till gångar i både offentliga och privata ursprung till CDN.

+ [Uppdatera länkar till CDN-till gångar](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Använda till gångar i offentliga ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Använda till gångar i privata ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Information om hur du använder CDN för att vara värd för klient webb delar finns i artikeln värd för [klient sidan från Office 365 CDN (Hej världen 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Om du lägger till mappen _ClientSideAssets_ i listan **privata** CDN-ursprung går det inte att rendera CDN-anpassade webb delar. Filer som används av SPFX webb delar kan bara använda det offentliga CDN och ClientSideAssets-mappen är ett standard ursprung för offentlig CDN. 

### <a name="updating-links-to-cdn-assets"></a>Uppdatera länkar till CDN-till gångar

Om du vill använda till gångar som du har lagt till i ett ursprung uppdaterar du bara länkar till den ursprungliga filen med sökvägen till filen i origo.

+ Redigera sidan eller innehållet som innehåller länkar till till gångar som du har lagt till i ett ursprung. Du kan också använda en av flera metoder för att globalt söka och ersätta länkar på en webbplats eller webbplats samling om du vill uppdatera länken till en viss till gång överallt där den visas.
+ För varje länk till en till gång i ett ursprung ersätter du sökvägen med sökvägen till filen i CDNs ursprung. Du kan använda relativa sökvägar.
+ Spara sidan eller innehållet.

Titta exempelvis på bild _/site/SiteAssets/images/image.png_som du har kopierat till mappen dokument bibliotek _/Site/CDN_origins/Public/_. Om du vill använda CDN-resursen ersätter du den ursprungliga sökvägen till bild filens plats med sökvägen till origo för att skapa den nya URL-adressen _/site/CDN_origins/public/image.png_.

Om du vill använda den fullständiga URL-adressen till resursen i stället för en relativ sökväg skapar du länken så här:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> I allmänhet ska du inte hardcode URL-adresser direkt till till gångar i CDN. Du kan dock manuellt skapa URL-adresser till till gångar i offentliga ursprung om det behövs. Mer information finns i [HARDCODING CDN URL: er för offentliga till gångar](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Om du vill veta mer om hur du kontrollerar att till gångar bearbetas från CDN kan [du läsa Hur kontrollerar jag att till gångar betjänas av CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) i [fel sökning i avsnittet Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .

### <a name="using-assets-in-public-origins"></a>Använda till gångar i offentliga ursprung

Med **publicerings funktionen** i SharePoint Online skrivs automatiskt om URL-adresser till till gångar som lagras i offentliga ursprung till deras CDN-motsvarigheter, så att till gångar behandlas från CDN-tjänsten i stället för SharePoint.

Om ditt ursprung finns på en webbplats där publicerings funktionen är aktive rad och de till gångar som du vill ladda in till CDN finns i någon av följande kategorier, skrivs URL-adresser automatiskt om till till gångar i ursprungslandet, förutsatt att till gången inte har uteslutits av en CDN policy.

Här följer en översikt över vilka länkar som automatiskt skrivs om av publicerings funktionen för SharePoint:

+ IMG/LINK/CSS URL-adresser i klassisk publicerings sida HTML-svar
  + Här ingår bilder som lagts till av författare i HTML-innehåll på en sida
+ Bild-URL: er för bild bibliotek
+ Bildfält i RenderListDataAsStream-resultat (SPList REST API)
  + Använd den nya egenskapen _ImageFieldsToTryRewriteToCdnUrls_ för att ange en kommaseparerad lista med fält
  + Stöd för hyperlänkfält och PublishingImage-fält
+ Bild åter givningar för SharePoint

I följande diagram visas arbets flödet när SharePoint tar emot en begäran om en sida som innehåller till gångar från ett offentligt ursprung.

![Arbets flödes diagram: Hämta Office 365 CDN-till gångar från ett offentligt ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Arbets flöde: Hämta Office 365 CDN-till gångar från ett offentligt ursprung")

> [!TIP]
> Om du vill inaktivera automatisk omskrivning för specifika URL-adresser på en sida kan du checka ut sidan och lägga till parametern frågesträng **? NoAutoReWrites = sant** till slutet av varje länk som du vill inaktivera.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>Hardcoding CDN-URL: er för offentliga till gångar

Om _publicerings_ funktionen inte är aktive rad för ett offentligt ursprung, eller om till gången inte är en av de länk typer som stöds av funktionen automatisk omskrivning i CDN-tjänsten, kan du skapa URL-adresser till till GÅNGARnas CDN-plats och använda dessa URL-adresser i innehållet.

> [!NOTE]
> Du kan inte hardcode CDN-URL: er till till gångar i ett privat ursprung eftersom den nödvändiga åtkomsttoken som utgör den sista delen av URL-adressen genereras när resursen begärs.

För offentliga CDN-till gångar ser URL-formatet ut så här:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Ersätt **TenantHostName** med klient namnet. Exempel:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Använda till gångar i privata ursprung

Ingen ytterligare konfiguration krävs för att använda till gångar i privata ursprung. I SharePoint Online skrivs URL-adresser automatiskt om för till gångar i privata ursprung så att begär Anden för dessa till gångar alltid kommer från CDN. Du kan inte skapa URL: er till CDN-till gångar manuellt i privata ursprung eftersom dessa URL: er innehåller tokens som måste genereras automatiskt av SharePoint Online när du begär till gången.

Åtkomst till till gångar i privata ursprung skyddas av dynamiskt genererade token baserat på användar behörigheter till ursprung, med de villkor som beskrivs i följande avsnitt. Användare måste minst ha **Läs** behörighet till ursprungen för att det ska gå att rendera innehållet.

I följande diagram visas arbets flödet när SharePoint tar emot en begäran om en sida som innehåller till gångar från ett privat ursprung.

![Arbets flödes diagram: Hämta Office 365 CDN-till gångar från ett privat ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Arbets flöde: Hämta Office 365 CDN-till gångar från ett privat ursprung")

#### <a name="token-based-authorization-in-private-origins"></a>Token-baserad auktorisering i privata ursprung

Åtkomst till till gångar i privata ursprung i Office 365 CDN beviljas av tokens som genererats av SharePoint Online. Användare som redan har behörighet att komma åt mappen eller biblioteket som anges av ursprunget beviljas automatiskt token som gör att användaren kan komma åt filen baserat på deras behörighets nivå. Dessa åtkomsttoken är giltiga i 30 till 90 minuter efter att de genererats för att förhindra repetition av token.

När Access-token har genererats returnerar SharePoint Online en anpassad URI till klienten med två verifierings _Parametrar:_ dela (Edge Authorization token) och _OAT_ (ursprunglig Authorization token). Strukturen för varje token är _< "förfallo tid i test perioden" >__< "säker signatur" >_. Till exempel:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Alla som har ett token kan komma åt resursen i CDN. URL-adresser med dessa åtkomsttoken delas bara över HTTPS, så såvida inte URL: en uttryckligen delas av en slutanvändare innan token går ut är till gången inte tillgänglig för obehöriga användare.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Behörigheter på objekt nivå stöds inte för till gångar i privata ursprung

Det är viktigt att du är medveten om att SharePoint Online inte hanterar behörigheter på objekt nivå för till gångar i privata ursprung. Användare har till exempel en `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` effektiv åtkomst till filen med följande villkor:

|Användare  |Behörigheter  |Effektiv åtkomst  |
|---------|---------|---------|
|Användare 1     |Har åtkomst till Mapp1         |Kan komma åt image1.jpg från CDN         |
|Användare 2     |Har inte åtkomst till Mapp1         |Det går inte att komma åt image1.jpg från CDN         |
|Användare 3     |Har inte åtkomst till Mapp1, men har uttryckligen tillåtelse att komma åt image1.jpg i SharePoint Online         |Kan komma åt till gången image1.jpg direkt från SharePoint Online, men inte från CDN         |
|Användare 4     |Har åtkomst till Mapp1, men har uttryckligen nekats åtkomst till image1.jpg i SharePoint Online         |Det går inte att komma åt till gången från SharePoint Online men kan komma åt till gången från CDN trots att den nekas åtkomst till filen i SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Felsöka Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Hur bekräftar jag att till gångar betjänas av CDN?

När du har lagt till länkar till CDN-till gångar på en sida kan du bekräfta att till gången betjänas från CDN genom att bläddra till sidan och högerklicka på bilden när den har Render ATS och granska bild-URL: en.

Du kan också använda din webbläsares utvecklingsverktyg för att Visa webb adressen för varje objekt på en sida eller använda en tredjepartsleverantör för nätverks spårning.

> [!NOTE]
> Om du använder ett nätverks verktyg som/Fiddler-loggar för att testa dina till gångar från en SharePoint-sida, måste du lägga till referens rubriken "referering: `https://yourdomain.sharepoint.com` " till GET-begäran där URL-adressen är rot-URL för SharePoint Online-klienten.

Du kan inte testa CDN-adresser direkt i en webbläsare eftersom det finns en refererare från SharePoint Online. Om du däremot lägger till URL-adressen till till gången på en SharePoint-sida och sedan öppnar sidan i en webbläsare visas CDN-resursen som återges på sidan.

Mer information om hur du använder utvecklingsverktygen i webbläsaren Microsoft Edge finns i [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).

Om du vill titta på en kort video som finns i [SharePoint-utvecklingsverktygen och Practices YouTube-kanalen](https://aka.ms/sppnp-videos) som visar hur du kontrollerar att CDN fungerar, se [Verifiera ditt CDN-bruk och säkerställa optimal nätverks anslutning](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Varför är inte till gångar från ett nytt ursprungs ursprung?
Till gångar i nya ursprung är inte omedelbart tillgängliga för användning, eftersom det tar tid för registreringen att sprida sig genom CDN och för till gångar att laddas upp från origo till CDN-lagring. Den tid som krävs för att till gångar ska vara tillgänglig i CDN beror på hur många till gångar och filernas storlek.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Min webb dels klient eller SharePoint Framework-lösning fungerar inte

När du aktiverar Office 365 CDN för offentliga ursprung, skapar CDN-tjänsten automatiskt dessa standard ursprung:

+ */MASTERPAGE
+ */STYLE-BIBLIOTEK
+ */CLIENTSIDEASSETS

Om */clientsideassets-Origo saknas Miss lyckas SharePoint Framework-lösningar och ingen varnings-eller fel meddelanden genereras. Detta ursprung kan saknas antingen på grund av att CDN aktiverades med parametern _-NoDefaultOrigins_ inställd på **$True**, eller på grund av att origo togs bort manuellt.

Du kan kontrol lera vilka ursprung som finns med följande PowerShell-kommando:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Eller så kan du kontrol lera med Office 365-CLI:

``` powershell
spo cdn origin list
```

Så här lägger du till ursprung i PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Så här lägger du till ursprunget i Office 365-CLI:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Vilka PowerShell-moduler och CLI-gränssnitt behöver jag för att arbeta med Office 365 CDN?

Du kan välja att arbeta med Office 365 CDN med antingen **SharePoint Online Management Shell** PowerShell-modulen eller **Office 365-CLI**.

+ [Komma igång med SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installera Office 365-CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Se även

[Nätverk för innehålls leverans](https://aka.ms/o365cdns)

[Network planning and performance tuning for Office 365](https://aka.ms/tune)

[SharePoint-prestandaräknare – Office 365 CDN-videoserie](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
