---
title: Använda Office 365 Content Delivery Network (CDN) med SharePoint Online
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
description: Lär dig hur du använder Nätverket för innehållsleverans i Office 365 (CDN) för att snabba på leveransen av dina SharePoint Online-tillgångar.
ms.openlocfilehash: 17c80b8718ea46c9dfba9f803093974e8ce3e706
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222689"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Använda Office 365 Content Delivery Network (CDN) med SharePoint Online

Du kan använda det inbyggda nätverket för innehållsleverans i Office 365 (CDN) för statiska tillgångar för att få bättre prestanda för dina SharePoint Online-sidor. Office 365 CDN förbättrar prestandan genom att cachelagra statiska tillgångar närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden. Office 365 CDN använder också [HTTP/2-protokollet](https://en.wikipedia.org/wiki/HTTP/2) för förbättrad komprimering och HTTP-pipelining. Office 365 CDN-tjänsten ingår som en del av din SharePoint Online-prenumeration.

> [!NOTE]
> Office 365 CDN är bara tillgängligt för innehavare i molnet **För** produktion (globalt). Klientorganisationen i molnen för myndigheter i USA, Kina och Tyskland stöder för närvarande inte Office 365 CDN.

Office 365 CDN består av flera CDN-nätverk som gör att du kan lagra statiska tillgångar på flera platser, eller ursprung _,_ och hantera dem från globala nätverk med hög hastighet. Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till offentliga **ursprung,** privata ursprung eller båda.  Se [Välj om varje ursprung ska vara offentligt eller](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) privat för mer information om skillnaden mellan offentliga och privata ursprung.

![Konceptuellt diagram för Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "Konceptuellt diagram för Office 365 CDN")

Om du redan är bekant med hur CDNs fungerar behöver du bara utföra några få steg för att aktivera Office 365 CDN för din klientorganisation. I det här avsnittet beskrivs hur du gör. Läs vidare för information om hur du kommer igång med värdskap för dina statiska tillgångar.

> [!TIP]
> Det finns andra CDN med Microsoft-värd som kan användas med Office 365 för särskilda användningsscenarier, men som inte diskuteras i det här avsnittet eftersom de faller utanför Office 365 CDN. Mer information finns i Andra [Microsoft CDN.](content-delivery-networks.md#other-microsoft-cdns)

 **Gå tillbaka till [Nätverksplanering och prestandajustering för Office 365.](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Översikt över hur du arbetar med Office 365 CDN i SharePoint Online

Om du vill konfigurera Office 365 CDN för organisationen följer du de här grundläggande stegen:

+ [Planera för distribution av Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bestäm vilka statiska tillgångar du vill ha på CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestäm var du vill lagra tillgångarna](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Platsen kan vara en webbplats, ett bibliotek eller en mapp i SharePoint och kallas _ursprung._
  + [Välj om varje ursprung ska vara offentligt eller privat.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Du kan lägga till flera ursprung för både offentliga och privata typer.

+ Konfigurera och konfigurera CDN med hjälp av antingen PowerShell eller SharePoint Online CLI

  + [Konfigurera och konfigurera CDN med hjälp av SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Konfigurera och konfigurera CDN med hjälp av PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Konfigurera och konfigurera CDN med hjälp av Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  När du slutför det här steget har du:

  + Aktiverat CDN för organisationen.
  + Lagt till ursprungen och identifierar varje ursprung som offentligt eller privat.

När du är klar med konfigurationen kan du hantera [Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) över tid genom att:
  
+ Lägga till, uppdatera och ta bort tillgångar
+ Lägga till och ta bort ursprung
+ Konfigurera CDN-principer
+ Inaktivera CDN om det behövs

Slutligen kan du läsa [Använda dina CDN-tillgångar för](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) att lära dig mer om hur du kommer åt dina CDN-tillgångar från både offentliga och privata ursprung.

Mer information om hur du löser vanliga problem finns i Felsöka [Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planera för distribution av Office 365 CDN

Innan du distribuerar Office 365 CDN för Office 365-klienten bör du tänka på följande faktorer som en del av planeringsprocessen.

  + [Bestäm vilka statiska tillgångar du vill ha på CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestäm var du vill lagra tillgångarna](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Välj om varje ursprung ska vara offentligt eller privat](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bestäm vilka statiska tillgångar du vill ha på CDN

I allmänhet är CDN mest effektiva för värd _för statiska_ tillgångar , eller tillgångar som inte ändras så ofta. En bra tumregel är att identifiera filer som uppfyller vissa eller alla dessa villkor:

+ Statiska filer som är inbäddade i en sida (till exempel skript och bilder) som kan ha en betydande stegvis inverkan på sidornas inläsningstider
+ Stora filer som körbara filer och installationsfiler
+ Resursbibliotek med stöd för klientkod

Till exempel kan små filer som upprepade gånger efterfrågas, t.ex. webbplatsbilder och skript, avsevärt förbättra prestanda för webbplatsåtergivning och stegvis minska belastningen på SharePoint Online-webbplatser när du lägger till dem i ett CDN-ursprung. Större filer, till exempel körbara installationsfiler, kan laddas ned från CDN, vilket ger positiv prestanda påverkan och därefter en minskning av belastningen på SharePoint Online-webbplatsen, även om de inte används så ofta.

Prestandaförbättringar per fil beror på många faktorer, inklusive klientens närhet till närmaste CDN-slutpunkt, tillfälliga villkor i det lokala nätverket och så vidare. Många statiska filer är ganska små och kan laddas ned från Office 365 på mindre än en sekund. En webbsida kan emellertid innehålla många inbäddade filer med en kumulativ nedladdningstid på flera sekunder. Att använda dessa filer från CDN kan avsevärt minska inläsningstiden för sidan. Se [Vilka prestandaförbättringar tillhandahåller ett CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) i ett exempel.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bestäm var du vill lagra tillgångarna

CDN hämtar dina tillgångar från en plats som kallas för _ursprung._ Ett ursprung kan vara en SharePoint-webbplats, ett dokumentbibliotek eller en mapp som kan nås via en URL. Du har stor flexibilitet när du anger ursprung för organisationen. Du kan till exempel ange flera ursprung eller ett enda ursprung där du vill placera alla CDN-tillgångar. Du kan välja att ha både offentliga och privata ursprung för organisationen. De flesta organisationer väljer att implementera en kombination av de två.

Du kan skapa en ny behållare för ursprungen, till exempel mappar eller dokumentbibliotek, och lägga till filer som du vill göra tillgängliga från CDN. Det här är ett bra sätt om du har en särskild uppsättning tillgångar som du vill ska vara tillgänglig från CDN, och vill begränsa uppsättningen CDN-tillgångar till endast de filerna i behållaren.

Du kan också konfigurera en befintlig webbplatssamling, webbplats, bibliotek eller mapp som ursprung, vilket gör alla kvalificerade tillgångar i behållaren tillgänglig från CDN. Innan du lägger till en befintlig behållare som ursprung är det viktigt att du är medveten om dess innehåll och behörigheter så att du inte oavsiktligt visar tillgångar för anonym åtkomst eller obehöriga användare.

Du kan definiera _CDN-principer_ för att utesluta innehåll i dina ursprung från CDN. CDN-principer utesluter tillgångar i offentliga eller  privata ursprung efter attribut, till exempel filtyp och webbplatsklassificering, och tillämpas på alla ursprung för den CdnType (privat eller offentlig) du anger i principen. Om du till exempel lägger till ett privat ursprung som består av en webbplats som  innehåller flera underwebbplatser kan du definiera en princip för att utesluta webbplatser som markerats som konfidentiellt, så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN. Principen gäller för innehåll från alla _privata ursprung_ som du har lagt till i CDN.
  
Tänk på att ju större antal ursprung, desto större inverkan på tiden det tar CDN-tjänsten att bearbeta begäranden. Vi rekommenderar att du så mycket som möjligt begränsar antalet ursprung.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Välj om varje ursprung ska vara offentligt eller privat

När du identifierar ett ursprung anger du om det ska göras _offentligt eller_ _privat._ Åtkomst till CDN-tillgångar i offentliga ursprung är anonym och CDN-innehåll i privata ursprung skyddas av dynamiskt genererade token för större säkerhet. Oavsett vilket alternativ du väljer gör Microsoft allt grovjobb åt dig när det gäller administration av själva CDN. Du kan också ändra dig senare, när du har konfigurerat CDN och identifierat dina ursprung.

Både offentliga och privata alternativ ger liknande prestandaförbättringar, men var och en har unika attribut och fördelar.

**Offentliga** ursprung i Office 365 CDN är anonymt tillgängliga och värdtillgångar kan nås av alla som har URL-adressen till tillgången. Eftersom åtkomsten till innehåll i offentliga ursprung är anonym bör du bara använda dem för att cachelagra icke-känsligt allmänt innehåll som javascript-filer, skript, ikoner och bilder.

**Privata** ursprung i Office 365 CDN ger privat åtkomst till användarinnehåll, till exempel dokumentbibliotek, webbplatser och egna bilder i SharePoint Online. Åtkomst till innehåll i privata ursprung skyddas av dynamiskt genererade tokens så att användare med behörighet till det ursprungliga dokumentbiblioteket eller lagringsplatsen endast kan komma åt det. Privata ursprung i Office 365 CDN kan endast användas för SharePoint Online-innehåll och du kan bara komma åt tillgångar i privata ursprung genom omdirigering från SharePoint Online-klienten.

Du kan läsa mer om hur CDN-åtkomst till tillgångar i ett privat ursprung fungerar i [Använda tillgångar i privata ursprung.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attribut och fördelar med att ha tillgångar i offentliga ursprung
  
+ Tillgångar som exponeras i en offentlig tillgång är åtkomliga för alla anonymt.
    > [!IMPORTANT]
    > Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.
+ Om du tar bort en tillgång från ett offentligt ursprung kan tillgången fortsätta att vara tillgänglig i upp till 30 dagar från cachen. Länkar till tillgången blir ogiltiga i CDN inom 15 minuter.
+ När du är värd för formatmallar (CSS-filer) i ett offentligt ursprung kan du använda relativa sökvägar och URI:er i koden. Det innebär att du kan referera till platsen för bakgrundsbilder och andra objekt i förhållande till platsen för tillgången som anropar den.
+ Du kan skapa URL-adressen för ett offentligt ursprung, men du bör vara försiktig och se till att du använder sidkontextegenskapen och följer instruktionerna för att göra det. Anledningen är att om åtkomsten till CDN blir otillgänglig matchas inte URL-adressen automatiskt med din organisation i SharePoint Online och kan leda till brutna länkar och andra fel. URL:en kan också komma att ändras. Det är därför den inte bara ska vara hårdkodad till sitt nuvarande värde.
+ Standardfiltyperna som ingår för offentliga ursprung är .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff och .woff2. Du kan ange ytterligare filtyper.
+ Du kan konfigurera en princip för att utesluta tillgångar som har identifierats av webbplatsklassificeringarna som du anger. Du kan till exempel välja att utesluta alla tillgångar som markeras som "konfidentiell" eller "begränsad" även om de är en tillåten filtyp och finns i ett offentligt ursprung.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attribut och fördelar med att ha tillgångar i privata ursprung

+ Privata ursprung kan endast användas för SharePoint Online-tillgångar.
+ Användare kan bara komma åt tillgångarna från ett privat ursprung om de har behörighet att komma åt behållaren. Anonym åtkomst till tillgångarna förhindras.
+ Tillgångar i privata ursprung måste hänvisas från SharePoint Online-klienten. Direkt åtkomst till privata CDN-tillgångar fungerar inte.
+ Om du tar bort en tillgång från det privata ursprunget kan tillgången fortsätta att vara tillgänglig i upp till en timme från cachen. Länkarna till tillgången blir ogiltiga i CDN inom 15 minuter efter att tillgången tas bort.
+ Standardfiltyperna som ingår för privata ursprung är .gif, .ico, .jpeg, .jpg, .js och .png. Du kan ange ytterligare filtyper.
+ Precis som för offentliga ursprung kan du konfigurera en princip för att utesluta tillgångar som har identifierats av webbplatsklassificeringarna som du anger även om du använder jokertecken för att inkludera alla tillgångar i en mapp eller ett dokumentbibliotek.

Mer information om varför du använder Office 365 CDN, allmänna CDN-begrepp och andra Microsoft CDN-namn som du kan använda med din Office 365-klientorganisation finns i [Nätverk](content-delivery-networks.md)för innehållsleverans.

### <a name="default-cdn-origins"></a>Standard-CDN-ursprung

Om du inte anger något annat uppsättningar Office 365 några standard ursprung åt dig när du aktiverar Office 365 CDN. Om du först väljer att inte tillhandahålla dem kan du lägga till dessa ursprung när du har slutfört konfigurationen. Om du inte förstår konsekvenserna av att hoppa över konfigurationen av standard ursprung och har en särskild orsak till att göra det, bör du tillåta att de skapas när du aktiverar CDN.
  
Privata CDN-standardsprung:
  
+ \*/userphoto.aspx
+ \*/siteassets

Offentliga CDN-standardsprung:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ är ett offentligt standard ursprung som lades till i Office 365 CDN-tjänsten i december 2017. Det här ursprunget måste finnas för att SharePoint Framework-lösningar i CDN ska fungera. Om du aktiverade Office 365 CDN innan december 2017, eller om du hoppade över konfigurationen av standard ursprung när du aktiverade CDN, kan du manuellt lägga till det här ursprunget. Mer information finns i [Min klientwebbdel eller SharePoint Framework-lösning fungerar inte.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Konfigurera och konfigurera Office 365 CDN med hjälp av SharePoint Online Management Shell

Procedurerna i det här avsnittet kräver att du använder SharePoint Online Management Shell för att ansluta till SharePoint Online. Instruktioner finns i [Ansluta till SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med SharePoint Online Management Shell.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivera organisationen för att använda Office 365 CDN

Innan du gör ändringar i klientorganisationens CDN-inställningar bör du hämta aktuell status för den privata CDN-konfigurationen i Office 365-klienten. Ansluta till klientorganisationen med SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Använd nu cmdleten **Get-SPOTenantCdnEnabled** till att hämta CDN-statusinställningarna från klientorganisationen:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Status för CDN för den angivna CdnType matas ut på skärmen.

Använd cmdleten **Set-SPOTenantCdnEnabled** till att aktivera organisationen för att använda Office 365 CDN. Du kan aktivera organisationen för att använda offentliga ursprung, privata ursprung eller båda samtidigt. Du kan också konfigurera CDN att hoppa över konfigurationen av standard ursprung när du aktiverar det. Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.
  
I Windows Powershell för SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Om du till exempel vill aktivera organisationen för att använda både offentliga och privata ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Om du vill aktivera organisationen för att använda både offentliga och privata ursprung men hoppa över att konfigurera standard ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Mer information [om ursprung som etableras](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) som standard när du aktiverar Office 365 CDN finns i Standard-CDN-ursprung och eventuell inverkan med att hoppa över konfigurationen av standard ursprung.

Om du vill aktivera organisationen för att använda offentliga ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Om du vill aktivera din organisation för att använda privata ursprung skriver du följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Mer information om den här cmdleten finns [i Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)

> [!TIP]
> När du definierar filtyper med hjälp av cmdleten **Set-SPOTenantCdnPolicy** skriver du över den aktuella definierade listan. Om du vill lägga till ytterligare filtyper i listan använder du först cmdleten för att ta reda på vilka filtyper som redan är tillåtna och inkludera dem i listan tillsammans med dina nya.
  
Använd cmdleten **Set-SPOTenantCdnPolicy** till att definiera statiska filtyper som kan lagras av offentliga och privata ursprung i CDN. Som standard tillåts vanliga tillgångstyper, till exempel .css, .gif, .jpg och .js.

I Windows PowerShell för SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Om du till exempel vill aktivera CDN som värd för .css- och .png-filer anger du kommandot:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Om du vill se vilka filtyper som tillåts av CDN använder du cmdleten **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Mer information om dessa cmdlets finns i [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) och [Get-SPOTenantCdnPolicies.](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN (valfritt)

> [!TIP]
> När du utesluter webbplatsklassificeringarna med hjälp av cmdleten **Set-SPOTenantCdnPolicy** skriver du över den aktuella definierade listan. Om du vill utesluta ytterligare webbplatsklassificeringarna använder du cmdleten först för att ta reda på vilka klassificeringar som redan har uteslutits och sedan lägga till dem tillsammans med dina nya.

Använd **cmdleten Set-SPOTenantCdnPolicy** till att utesluta webbplatsklassificering som du inte vill ska vara tillgängliga via CDN. Som standard utesluts inga webbplatsklassificeringar.

I Windows PowerShell för SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Om du vill se vilka webbplatsklassificeringarna som är begränsade använder du cmdleten **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Egenskaperna som returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ _och ExcludeIfNoScriptDisabled._

Egenskapen _IncludeFileExtensions_ innehåller listan över filnamnstillägg som kan användas i CDN.

> [!NOTE]
> Standardtilläggen för filer skiljer sig åt mellan offentliga och privata.

Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller webbplatsklassificeringarna som du vill utesluta från CDN. Du kan till exempel utesluta webbplatser som markerats som **konfidentiella** så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN.

Egenskapen _ExcludeIfNoScriptDisabled_ utesluter innehåll från CDN baserat på inställningar för _NoScript-attribut_ på webbplatsnivå. Som standard är _attributet NoScript_ inställt på **Aktiverad för** _moderna_ webbplatser och **Inaktiverat** för _klassiska_ webbplatser. Det beror på klientorganisationens inställningar.

Mer information om dessa cmdlets finns i [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) och [Get-SPOTenantCdnPolicies.](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Lägga till ett ursprung för dina tillgångar

Definiera ett **ursprung med cmdleten Add-SPOTenantCdnOrigin.** Du kan definiera flera ursprung. Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.
  
> [!IMPORTANT]
> Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Värdet på _sökvägen_ är den relativa sökvägen till biblioteket eller mappen som innehåller tillgångarna. Du kan använda jokertecken utöver relativa sökvägar. Ursprung stöder jokertecken som finns i url-adressen. På så sätt kan du skapa ursprung som spänner över flera webbplatser. Om du till exempel vill ta med alla tillgångar i mappen masterpages för alla dina webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Jokertecknet * kan bara användas i början av sökvägen och matchar **/** alla URL-segment under den angivna URL:en.
+ Sökvägen kan peka på ett dokumentbibliotek, en mapp eller en webbplats. Sökvägen _*/webbplats1_ matchar till exempel alla dokumentbibliotek under webbplatsen.

Du kan lägga till ett ursprung med en viss relativ sökväg. Du kan inte lägga till ett ursprung med den fullständiga sökvägen.

I det här exemplet läggs ett privat ursprung till webbplatssamlingsbiblioteket på en viss webbplats:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Det här exemplet lägger till ett privat ursprung _för mappen mapp1_ i webbplatssamlingens bibliotek för webbplatstillgångar:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Om det finns ett blanksteg i sökvägen kan du antingen omge sökvägen med dubbla citattecken eller ersätta blanksteget med URL-kodningen %20. Följande exempel lägger till ett privat ursprung för _mappen mapp 1_ i webbplatssamlingens bibliotek för webbplatstillgångar:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

> [!NOTE]
> I privata ursprung måste tillgångar som delas från ett ursprung ha en huvudversion publicerad innan de kan nås från CDN.
  
När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exempel: Konfigurera ett offentligt ursprung för huvudsidorna och för formatbiblioteket för SharePoint Online

Normalt konfigureras dessa ursprung åt dig som standard när du aktiverar Office 365 CDN. Men om du vill aktivera dem manuellt följer du de här stegen.
  
+ Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera formatbiblioteket som ett offentligt ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera huvudsidorna som ett offentligt ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för dina webbplatstillgångar, webbplatssidor och publiceringsbilder för SharePoint Online

+ Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för webbplatstillgångar som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för webbplatssidor som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera mappen för publiceringsbilder som ett privat ursprung.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)

När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för en webbplatssamling för SharePoint Online

Använd **cmdleten Add-SPOTenantCdnOrigin** till att definiera en webbplatssamling som ett privat ursprung. Till exempel:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Mer information om kommandot och dess syntax finns i [Add-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)
  
När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Du kanske ser ett _meddelande om väntande_ konfiguration som förväntas när SharePoint Online-klienten ansluter till CDN-tjänsten. Det kan ta upp till 15 minuter.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Hantera Office 365 CDN

När du har ställt in CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Lägga till, uppdatera eller ta bort tillgångar från Office 365 CDN

När du har slutfört konfigurationsstegen kan du lägga till nya tillgångar och uppdatera eller ta bort befintliga tillgångar när du vill. Gör bara ändringar av tillgångarna i den mapp eller det SharePoint-bibliotek som du har identifierat som ursprung. Om du lägger till en ny tillgång är den tillgänglig via CDN direkt. Men om du uppdaterar tillgången tar det upp till 15 minuter för den nya kopian av spridas och bli tillgänglig i CDN.
  
Om du behöver hämta platsen för ursprunget kan du använda cmdleten **Get-SPOTenantCdnOrigins.** Information om hur du använder denna cmdlet finns i [Get-SPOTenantCdnOrigins.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Ta bort ett ursprung från Office 365 CDN

Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ursprung. Det gör du med cmdleten **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Information om hur du använder denna cmdlet finns [i Remove-SPOTenantCdnOrigin.](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändra ett ursprung i Office 365 CDN

Du kan inte ändra ett ursprung som du har skapat. Ta istället bort ursprunget och lägg sedan till ett nytt. Mer information finns i Ta [bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) och Lägga till ett ursprung för dina [tillgångar.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Använd **cmdleten Set-SPOTenantCdnEnabled** till att inaktivera CDN för organisationen. Om du har aktiverat både offentliga och privata ursprung för CDN måste du köra cmdleten två gånger enligt följande exempel.
  
Inaktivera användningen av offentliga ursprung i CDN genom att ange följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Inaktivera användningen av privata ursprung i CDN genom att ange följande kommando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Mer information om den här cmdleten finns [i Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Konfigurera och konfigurera Office 365 CDN med PnP PowerShell

Procedurerna i det här avsnittet kräver att du använder PnP PowerShell för att ansluta till SharePoint Online. Anvisningar finns i [Komma igång med PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med PnP PowerShell.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivera organisationen för att använda Office 365 CDN

Innan du gör ändringar i klientorganisationens CDN-inställningar bör du hämta aktuell status för den privata CDN-konfigurationen i Office 365-klienten. Anslut till klientorganisationen med PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Använd nu cmdleten **Get-PnPTenantCdnEnabled** för att hämta CDN-statusinställningarna från klientorganisationen:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Status för CDN för den angivna CdnType matas ut på skärmen.

Använd **cmdleten Set-PnPTenantCdnEnabled** till att aktivera organisationen för att använda Office 365 CDN. Du kan aktivera organisationen för att använda offentliga ursprung, privata ursprung eller båda samtidigt. Du kan också konfigurera CDN att hoppa över konfigurationen av standard ursprung när du aktiverar det. Du kan alltid lägga till dessa ursprung senare enligt beskrivningen i det här avsnittet.
  
I PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Om du till exempel vill aktivera organisationen för att använda både offentliga och privata ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Om du vill aktivera organisationen för att använda både offentliga och privata ursprung men hoppa över att konfigurera standard ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Mer information [om ursprung som etableras](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) som standard när du aktiverar Office 365 CDN finns i Standard-CDN-ursprung och eventuell inverkan med att hoppa över konfigurationen av standard ursprung.

Om du vill aktivera organisationen för att använda offentliga ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Om du vill aktivera din organisation för att använda privata ursprung skriver du följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Mer information om den här cmdleten finns [i Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändra listan över filtyper som ska ingå i Office 365 CDN (valfritt)

> [!TIP]
> När du definierar filtyper med hjälp av cmdleten **Set-PnPTenantCdnPolicy** skriver du över den aktuella definierade listan. Om du vill lägga till ytterligare filtyper i listan använder du först cmdleten för att ta reda på vilka filtyper som redan är tillåtna och inkludera dem i listan tillsammans med dina nya.
  
Använd **cmdleten Set-PnPTenantCdnPolicy** till att definiera statiska filtyper som kan lagras av offentliga och privata ursprung i CDN. Som standard tillåts vanliga tillgångstyper, till exempel .css, .gif, .jpg och .js.

I PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Om du till exempel vill aktivera CDN som värd för .css- och .png-filer anger du kommandot:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Om du vill se vilka filtyper som tillåts av CDN använder du cmdleten **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Mer information om dessa cmdlets finns i [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) och [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN (valfritt)

> [!TIP]
> När du utesluter webbplatsklassificeringarna med hjälp av cmdleten **Set-PnPTenantCdnPolicy** skriver du över den aktuella definierade listan. Om du vill utesluta ytterligare webbplatsklassificeringarna använder du cmdleten först för att ta reda på vilka klassificeringar som redan har uteslutits och sedan lägga till dem tillsammans med dina nya.

Använd **cmdleten Set-PnPTenantCdnPolicy** till att utesluta webbplatsklassificeringarna som du inte vill ska vara tillgängliga via CDN. Som standard utesluts inga webbplatsklassificeringar.

I PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Om du vill se vilka webbplatsklassificeringarna är begränsade använder du cmdleten **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Egenskaperna som returneras är _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ _och ExcludeIfNoScriptDisabled._

Egenskapen _IncludeFileExtensions_ innehåller listan över filnamnstillägg som kan användas i CDN.

> [!NOTE]
> Standardtilläggen för filer skiljer sig åt mellan offentliga och privata.

Egenskapen _ExcludeRestrictedSiteClassifications_ innehåller webbplatsklassificeringarna som du vill utesluta från CDN. Du kan till exempel utesluta webbplatser som markerats som **konfidentiella** så att innehåll från webbplatser med den klassificering som tillämpas inte kommer att användas från CDN.

Egenskapen _ExcludeIfNoScriptDisabled_ utesluter innehåll från CDN baserat på inställningar för _NoScript-attribut_ på webbplatsnivå. Som standard är _attributet NoScript_ inställt på **Aktiverad för** _moderna_ webbplatser och **Inaktiverat** för _klassiska_ webbplatser. Det beror på klientorganisationens inställningar.

Mer information om dessa cmdlets finns i [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) och [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Lägga till ett ursprung för dina tillgångar

Definiera ett **ursprung med cmdleten Add-PnPTenantCdnOrigin.** Du kan definiera flera ursprung. Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.
  
> [!IMPORTANT]
> Du ska aldrig placera resurser som innehåller användarinformation eller som anses vara känsliga för organisationen i ett offentligt ursprung.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Värdet på _sökvägen_ är den relativa sökvägen till biblioteket eller mappen som innehåller tillgångarna. Du kan använda jokertecken utöver relativa sökvägar. Ursprung stöder jokertecken som finns i url-adressen. På så sätt kan du skapa ursprung som spänner över flera webbplatser. Om du till exempel vill ta med alla tillgångar i mappen masterpages för alla dina webbplatser som ett offentligt ursprung i CDN skriver du följande kommando:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Jokertecknet * kan bara användas i början av sökvägen och matchar **/** alla URL-segment under den angivna URL:en.
+ Sökvägen kan peka på ett dokumentbibliotek, en mapp eller en webbplats. Sökvägen _*/webbplats1_ matchar till exempel alla dokumentbibliotek under webbplatsen.

Du kan lägga till ett ursprung med en viss relativ sökväg. Du kan inte lägga till ett ursprung med den fullständiga sökvägen.

I det här exemplet läggs ett privat ursprung till biblioteket med webbplatstillgångar till på en viss webbplats:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Det här exemplet lägger till ett privat ursprung _för mappen mapp1_ i webbplatssamlingens bibliotek för webbplatstillgångar:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Om det finns ett blanksteg i sökvägen kan du antingen omge sökvägen med dubbla citattecken eller ersätta blanksteget med URL-kodningen %20. Följande exempel lägger till ett privat ursprung för _mappen mapp 1_ i webbplatssamlingens bibliotek för webbplatstillgångar:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

> [!NOTE]
> I privata ursprung måste tillgångar som delas från ett ursprung ha en huvudversion publicerad innan de kan nås från CDN.
  
När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exempel: Konfigurera ett offentligt ursprung för huvudsidorna och för formatbiblioteket för SharePoint Online

Normalt konfigureras dessa ursprung åt dig som standard när du aktiverar Office 365 CDN. Men om du vill aktivera dem manuellt följer du de här stegen.
  
+ Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera formatbiblioteket som ett offentligt ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera huvudsidorna som ett offentligt ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för dina webbplatstillgångar, webbplatssidor och publiceringsbilder för SharePoint Online

+ Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för webbplatstillgångar som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för webbplatssidor som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera mappen för publiceringsbilder som ett privat ursprung.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Det kan ta upp till 15 minuter.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exempel: Konfigurera ett privat ursprung för en webbplatssamling för SharePoint Online

Använd **cmdleten Add-PnPTenantCdnOrigin** till att definiera en webbplatssamling som ett privat ursprung. Till exempel:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Mer information om kommandot och dess syntax finns i [Add-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)
  
När du har kört kommandot synkroniserar systemet konfigurationen i datacentret. Du kanske ser ett _meddelande om väntande_ konfiguration som förväntas när SharePoint Online-klienten ansluter till CDN-tjänsten. Det kan ta upp till 15 minuter.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Hantera Office 365 CDN

När du har ställt in CDN kan du göra ändringar i konfigurationen när du uppdaterar innehåll eller när dina behov ändras, enligt beskrivningen i det här avsnittet.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Lägga till, uppdatera eller ta bort tillgångar från Office 365 CDN

När du har slutfört konfigurationsstegen kan du lägga till nya tillgångar och uppdatera eller ta bort befintliga tillgångar när du vill. Gör bara ändringar av tillgångarna i den mapp eller det SharePoint-bibliotek som du har identifierat som ursprung. Om du lägger till en ny tillgång är den tillgänglig via CDN direkt. Men om du uppdaterar tillgången tar det upp till 15 minuter för den nya kopian av spridas och bli tillgänglig i CDN.
  
Om du behöver hämta platsen för ursprunget kan du använda cmdleten **Get-PnPTenantCdnOrigin.** Information om hur du använder denna cmdlet finns i [Get-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Ta bort ett ursprung från Office 365 CDN

Du kan ta bort åtkomst till en mapp eller ett SharePoint-bibliotek som du har identifierat som ursprung. Det gör du med cmdleten **Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Information om hur du använder denna cmdlet finns [i Remove-PnPTenantCdnOrigin.](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändra ett ursprung i Office 365 CDN

Du kan inte ändra ett ursprung som du har skapat. Ta istället bort ursprunget och lägg sedan till ett nytt. Mer information finns i Ta [bort ett ursprung från Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) och Lägga till ett ursprung för dina [tillgångar.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Använd **cmdleten Set-PnPTenantCdnEnabled** till att inaktivera CDN för organisationen. Om du har aktiverat både offentliga och privata ursprung för CDN måste du köra cmdleten två gånger enligt följande exempel.
  
Inaktivera användningen av offentliga ursprung i CDN genom att ange följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Inaktivera användningen av privata ursprung i CDN genom att ange följande kommando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Mer information om den här cmdleten finns [i Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Konfigurera och konfigurera Office 365 CDN med hjälp av Office 365 CLI

Procedurerna i det här avsnittet kräver att du har installerat [Office 365 CLI.](https://aka.ms/o365cli) Anslut sedan till Din Office 365-klientorganisation med hjälp av [kommandot för](https://pnp.github.io/office365-cli/cmd/login/) inloggning.

Utför de här stegen för att konfigurera och konfigurera CDN som värd för dina tillgångar i SharePoint Online med Office 365 CLI.

<details>
  <summary>Klicka för att Visa</summary>

### <a name="enable-the-office-365-cdn"></a>Aktivera Office 365 CDN

Du kan hantera statusen för Office 365 CDN i klientorganisationen med hjälp av [kommandot för spo cdn-uppsättningen.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)

Så här aktiverar du det offentliga Office 365 CDN i klientorganisationen:

```sh
spo cdn set --type Public --enabled true
```

Om du vill aktivera Office 365 SharePoint CDN kör du:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Visa aktuell status för Office 365 CDN

Använd kommandot [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) om du vill kontrollera om den specifika typen av Office 365 CDN är aktiverad eller inaktiverad.

För att kontrollera om den offentliga Office 365 CDN är aktiverad kör du:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visa Office 365 CDN-ursprung

Så här visar du de konfigurerade offentliga Office 365 CDN-ursprungen:

```sh
spo cdn origin list --type Public
```

Se [Standard-CDN-ursprung](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) för information om ursprung som etableras som standard när du aktiverar Office 365 CDN.

### <a name="add-an-office-365-cdn-origin"></a>Lägga till ett Office 365 CDN-ursprung

> [!IMPORTANT]
> Du ska aldrig placera resurser som anses vara känsliga för organisationen i ett SharePoint-dokumentbibliotek som konfigurerats som ett offentligt ursprung.

Använd lägg till [ett spo cdn-ursprung för](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) att definiera ett CDN-ursprung. Du kan definiera flera ursprung. Ursprunget är en URL-adress som pekar på ett bibliotek eller en mapp i SharePoint som innehåller tillgångarna du vill ska lagras av CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Var `path` finns den relativa sökvägen till mappen som innehåller tillgångarna. Du kan använda jokertecken utöver relativa sökvägar.

Om du vill ta med alla tillgångar **i huvudsidesgalleriet** för alla webbplatser som ett offentligt ursprung kör du:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Om du vill konfigurera ett privat ursprung för en viss webbplatssamling kör du:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> När du har lagt till ett CDN-ursprung kan det ta upp till 15 minuter innan du kan hämta filer via CDN-tjänsten. Du kan kontrollera om det specifika ursprunget redan har aktiverats med hjälp av [kommandot för spo cdn-ursprung.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)

### <a name="remove-an-office-365-cdn-origin"></a>Ta bort ett Office 365 CDN-ursprung

Använd kommandot [ta bort spo cdn-ursprung](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) för att ta bort ett CDN-ursprung för den angivna CDN-typen.

Om du vill ta bort ett offentligt ursprung från CDN-konfigurationen kör du:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> När du tar bort ett CDN-ursprung påverkar det inte de filer som lagrats i något dokumentbibliotek som matchar ursprunget. Om tillgångarna har refererats med hjälp av deras SharePoint-URL kommer SharePoint automatiskt att växla tillbaka till den ursprungliga URL-adressen som pekar till dokumentbiblioteket. Om tillgångar har refererats med en offentlig CDN-URL bryter borttagningen länken och du måste ändra dem manuellt.

### <a name="modify-an-office-365-cdn-origin"></a>Ändra ett Office 365 CDN-ursprung

Det går inte att ändra ett befintligt CDN-ursprung. I stället bör du ta bort det tidigare definierade CDN-ursprunget med `spo cdn origin remove` kommandot och lägga till ett nytt med `spo cdn origin add` kommandot.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Ändra vilka typer av filer som ska ingå i Office 365 CDN

Som standard ingår följande filtyper i CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff och .woff2_. Om du behöver ta med ytterligare filtyper i CDN kan du ändra CDN-konfigurationen med hjälp av [kommandot för spo cdn-principen.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)

> [!NOTE]
> När du ändrar listan över filtyper skriver du över den definierade listan. Om du vill ta med ytterligare filtyper använder du först [spo cdn-principlistan](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) för att ta reda på vilka filtyper som är konfigurerade.

Om du vill _lägga till JSON-filtypen_ i standardlistan över filtyper som ingår i det offentliga CDN kör du:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Ändra listan över webbplatsklassificeringarna som du vill utesluta från Office 365 CDN

Använd kommandot [för SPO CDN-principuppsättning](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) till att utesluta webbplatsklassificeringarna som du inte vill ska vara tillgängliga via CDN. Som standard utesluts inga webbplatsklassificeringar.

> [!NOTE]
> När du ändrar listan med undantagna webbplatsklassificeringar skriver du över den definierade listan. Om du vill utesluta ytterligare klassificeringar använder du först [listkommandot för spo cdn-principen](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) för att ta reda på vilka klassificeringar som är konfigurerade.

Om du vill utesluta webbplatser som klassificerats som _HBI_ från den offentliga CDN kör du

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Inaktivera Office 365 CDN

Om du vill inaktivera Office 365 CDN använder `spo cdn set` du kommandot, till exempel:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Använda dina CDN-tillgångar

Nu när du har aktiverat CDN och konfigurerade ursprung och principer kan du börja använda dina CDN-tillgångar.

Det här avsnittet hjälper dig att förstå hur du använder CDN-URL:er i dina SharePoint-sidor och innehåll så att SharePoint omdirigerar förfrågningar för tillgångar i både offentliga och privata ursprung till CDN.

+ [Uppdatera länkar till CDN-tillgångar](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Använda tillgångar i offentliga ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Använda tillgångar i privata ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Information om hur du använder CDN för värd för klientwebbdelar finns i avsnittet Vara värd för din klientwebbdel från [Office 365 CDN (Hello World del 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Om du lägger till _mappen ClientSideAssets_ i den privata CDN-ursprungslistan går det inte att återge CDN-värdbaserade anpassade webbdelar.  Filer som används av SPFX-webbdelar kan endast använda den offentliga CDN och mappen ClientSideAssets är ett standard ursprung för offentlig CDN. 

### <a name="updating-links-to-cdn-assets"></a>Uppdatera länkar till CDN-tillgångar

Om du vill använda tillgångar som du har lagt till i ett ursprung uppdaterar du bara länkar till den ursprungliga filen med sökvägen till filen i ursprunget.

+ Redigera sidan eller innehållet som innehåller länkar till tillgångar som du har lagt till i ett ursprung. Du kan också använda en av flera metoder för att globalt söka och ersätta länkar över en ange webbplats eller webbplatssamling om du vill uppdatera länken till en viss tillgång överallt där den visas.
+ För varje länk till en tillgång i ett ursprung ersätter du sökvägen med sökvägen till filen i CDN-ursprunget. Du kan använda relativa sökvägar.
+ Spara sidan eller innehållet.

Överväg till exempel bilden _/site/SiteAssets/images/image.png_, som du har kopierat till dokumentbiblioteksmappen _/site/CDN_origins/public/_. Om du vill använda CDN-tillgången ersätter du den ursprungliga sökvägen till bildfilens plats med sökvägen till ursprunget för att göra den nya _URL:en /webbplats/CDN_origins/offentlig/image.png_.

Om du vill använda den fullständiga URL:en till tillgången i stället för en relativ sökväg skapar du länken så här:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> I allmänhet bör du inte hårdkoda URL-adresser direkt till tillgångar i CDN. Du kan dock manuellt skapa URL-adresser för tillgångar i offentliga ursprung om det behövs. Mer information finns i [Hardcoding CDN URL:er för offentliga tillgångar.](use-microsoft-365-cdn-with-spo.md)

Mer information om hur du verifierar att tillgångar kommer från CDN finns i Hur bekräftar jag att tillgångar används i [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) i avsnittet Felsökning av [Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Använda tillgångar i offentliga ursprung

Publiceringsfunktionen **i** SharePoint Online skriver automatiskt om URL-adresser för tillgångar som lagras i offentliga ursprung till sina CDN-motsvarigheter så att tillgångar hämtas från CDN-tjänsten i stället för från SharePoint.

Om ditt ursprung är på en webbplats där publiceringsfunktionen är aktiverad och tillgångarna du vill lägga i för tillgångar till CDN finns i någon av följande kategorier, skriver SharePoint automatiskt om URL-adresser för tillgångar i ursprunget, förutsatt att tillgången inte har uteslutits av en CDN-princip.

Nedan följer en översikt över vilka länkar som automatiskt skrivs om av funktionen för SharePoint-publicering:

+ HTML-svar för IMG/LINK/CSS
  + Det omfattar bilder som har lagts till av författare i HTML-innehåll på en sida
+ URL-adresser för webbdelen Bildspel för bildbibliotek
+ Bildfält i SPList REST API-resultat (RenderListDataAsStream)
  + Använda den nya egenskapen _ImageFieldsToTryRewriteToCdnUrls_ till att ange en kommaavgränsad lista med fält
  + Stöd för hyperlänkfält och publiceringsbildfält
+ SharePoint-bildåtergivningar

I följande diagram visas arbetsflödet när SharePoint tar emot en begäran om en sida som innehåller tillgångar från ett offentligt ursprung.

![Arbetsflödesdiagram: Hämta Office 365 CDN-tillgångar från ett offentligt ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Arbetsflöde: Hämta Office 365 CDN-tillgångar från ett offentligt ursprung")

> [!TIP]
> Om du vill inaktivera automatisk omskrivning av specifika URL:er på en sida kan du gå till sidan och lägga till frågesträngparametern **? NoAutoReWrites=true** i slutet av varje länk du vill inaktivera.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Konstruera CDN-URL:er för offentliga tillgångar

Om funktionen _Publicera_ inte är aktiverad för ett offentligt ursprung, eller om tillgången inte är en av länktyperna som stöds av funktionen för automatisk omskrivning i CDN-tjänsten, kan du manuellt skapa URL:er till CDN-platsen för tillgångarna och använda url:erna i innehållet.

> [!NOTE]
> Du kan inte hårdkoda eller skapa CDN-URL:er till tillgångar i ett privat ursprung eftersom den obligatoriska åtkomsttoken som utgör url-adressens sista avsnitt genereras när resursen begärs. Du kan skapa URL-adressen för offentlig CDN och URL-adressen ska inte vara hårdkodad eftersom den kan komma att ändras.

För offentliga CDN-tillgångar ser URL-formatet ut så här:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Ersätt **TenantHostName** med ditt klientnamn. Exempel:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> Sidsammanhangsegenskapen ska användas för att skapa prefixet i stället för hårdkodning " https://publiccdn.sharepointonline.com ". URL-adressen kan komma att ändras och ska inte vara hårdkodad. Om du använder visningsmallar med klassiska SharePoint Online kan du använda egenskapen "window._spPageContextInfo.publicCdnBaseUrl" i visningsmallen för prefixet på URL-adressen. Om du är SPFx-webbdelar för moderna och klassiska SharePoint kan du använda egenskapen "this.context.pageContext.legacyPageContext.publicCdnBaseUrl". Det ger prefixet så att din implementering uppdateras med den om den ändras. Som exempel för SPFx kan URL-adressen skapas med egenskapen "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL för objektet". Se [Använda CDN i Klientkod som är](https://youtu.be/IH1RbQlbhIA) en del av prestandaserien [för säsong 1](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Använda tillgångar i privata ursprung

Ingen ytterligare konfiguration krävs för att använda tillgångar i privata ursprung. SharePoint Online skriver automatiskt om URL-adresser för tillgångar i privata ursprung så att förfrågningar om dessa tillgångar alltid kommer att hämtas från CDN. Du kan inte skapa URL-adresser till CDN-tillgångar manuellt i privata ursprung eftersom dessa URL:er innehåller token som måste skapas automatiskt av SharePoint Online när tillgången begärs.

Åtkomst till tillgångar i privata ursprung skyddas av dynamiskt genererade token baserat på användarbehörigheter till ursprunget, med de varningar som beskrivs i följande avsnitt. Användarna måste ha minst **läsbehörighet** till ursprungen för att CDN ska kunna återge innehåll.

Följande diagram visar arbetsflödet när SharePoint tar emot en begäran om en sida som innehåller tillgångar från ett privat ursprung.

![Arbetsflödesdiagram: Hämta Office 365 CDN-tillgångar från ett privat ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Arbetsflöde: Hämta Office 365 CDN-tillgångar från ett privat ursprung")

#### <a name="token-based-authorization-in-private-origins"></a>Tokenbaserad auktorisering i privata ursprung

Åtkomst till tillgångar i privata ursprung i Office 365 CDN tilldelas med token som genereras av SharePoint Online. Användare som redan har åtkomst till mappen eller biblioteket som anges av ursprunget tilldelas automatiskt token som tillåter användaren att komma åt filen baserat på deras behörighetsnivå. De här åtkomsttoken är giltiga i 30 till 90 minuter efter att de har skapats för att förhindra attacker vid tokenuppspelning.

När åtkomsttoken har genererats returnerar SharePoint Online en anpassad  URI till klienten som innehåller två auktoriseringsparametrar äter (edge-auktoriseringstoken) och _oat_ (origin authorization token). Strukturen för varje token _är< förfallotid i Epoch-tidsformatet som >__< säkra signaturens >._ Till exempel:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Alla som äger token kan komma åt resursen i CDN. Url-adresser som innehåller dessa åtkomsttoken delas däremot bara över HTTPS, så om inte URL:en uttryckligen delas av en slutanvändare innan tokenen löper ut kommer tillgången inte att vara tillgänglig för obehöriga användare.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Behörigheter på objektnivå stöds inte för tillgångar i privata ursprung

Det är viktigt att observera att SharePoint Online inte stöder behörigheter på objektnivå för tillgångar i privata ursprung. För en fil som finns på `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , har användarna till exempel effektiv åtkomst till filen enligt följande villkor:

|Användare  |Behörigheter  |Effektiv åtkomst  |
|---------|---------|---------|
|Användare 1     |Har åtkomst till mapp1         |Kan komma image1.jpg från CDN         |
|Användare 2     |Har inte åtkomst till mapp1         |Kan inte image1.jpg från CDN         |
|Användare 3     |Har inte åtkomst till mapp1, men tilldelas uttrycklig åtkomstbehörighet för image1.jpg i SharePoint Online         |Kan komma åt image1.jpg direkt från SharePoint Online, men inte från CDN         |
|Användare 4     |Har åtkomst till mapp1, men har uttryckligen nekats åtkomst till image1.jpg i SharePoint Online         |Kan inte komma åt tillgången från SharePoint Online, men kan komma åt tillgången från CDN trots att åtkomst till filen nekas i SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Felsöka Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Hur bekräftar jag att tillgångar används av CDN?

När du har lagt till länkar till CDN-tillgångar på en sida kan du bekräfta att tillgången kommer från CDN genom att gå till sidan, högerklicka på bilden när den har visats och granskat bild-URL:en.

Du kan också använda webbläsarens utvecklarverktyg för att visa URL-adressen för varje tillgång på en sida, eller använda ett nätverksspårningsverktyg från tredje part.

> [!NOTE]
> Om du använder ett nätverksverktyg, till exempel Fiddler, för att testa dina tillgångar utanför att återge tillgången från en SharePoint-sida, måste du manuellt lägga till refererhuvudet "Referer: " i GET-begäran där URL:en är rot-URL:en för `https://yourdomain.sharepoint.com` SharePoint Online-klientorganisationen.

Du kan inte testa CDN-URL:er direkt i en webbläsare eftersom du måste ha en referent från SharePoint Online. Men om du lägger till CDN-resurs-URL:en på en SharePoint-sida och sedan öppnar sidan i en webbläsare, ser du CDN-tillgången återges på sidan.

Mer information om hur du använder utvecklarverktygen i webbläsaren Microsoft Edge finns i [Utvecklarverktyg för Microsoft Edge.](/microsoft-edge/devtools-guide)

Om du vill titta på en kort video som finns i [YouTube-kanalen SharePoint Developer Patterns and Practices](https://aka.ms/sppnp-videos) och visa hur du verifierar att CDN fungerar kan du gå till Verifiera din CDN-användning och säkerställa [optimal nätverksanslutning.](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Varför är tillgångar från ett nytt ursprung inte tillgängliga?
Tillgångar i nya ursprung blir inte omedelbart tillgängliga för användning eftersom det tar tid för registreringen att spridas via CDN och för tillgångar som ska laddas upp från ursprunget till CDN-lagringen. Hur lång tid som krävs för att tillgångar ska vara tillgänglig i CDN beror på hur många tillgångar och filstorlekar som krävs.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Min klientwebbdel eller SharePoint Framework-lösning fungerar inte

När du aktiverar Office 365 CDN för offentliga ursprung skapar CDN-tjänsten automatiskt följande standard origins:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Om ursprunget */clientsideassets saknas kommer SharePoint Framework-lösningar att misslyckas och inga varningar eller felmeddelanden skapas. Det här ursprunget kanske saknas antingen eftersom CDN aktiverades med parametern _-NoDefaultOrigins_ inställd **på $true**, eller eftersom ursprunget togs bort manuellt.

Du kan kontrollera vilka ursprung som finns med följande PowerShell-kommando:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Eller så kan du kontrollera med Office 365 CLI:

``` powershell
spo cdn origin list
```

Så här lägger du till ursprunget i PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Så här lägger du till ursprunget i Office 365 CLI:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Vilka PowerShell-moduler och CLI-gränssnitt behöver jag arbeta med Office 365 CDN?

Du kan välja att arbeta med Office 365 CDN med hjälp av **antingen SharePoint Online Management Shell** PowerShell-modulen eller **Office 365 CLI.**

+ [Komma igång med SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installera Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Se även

[Nätverk för innehållsleverans (CDN)](./content-delivery-networks.md)

[Network planning and performance tuning for Office 365](./network-planning-and-performance.md)

[SharePoint Performance Series – Office 365 CDN-videoserie](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)