---
title: Webbtjänsten Office 365 IP-adress och URL
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Lär dig hur du använder webbtjänsten Office 365 IP-adress and URL för att hjälpa dig att bättre identifiera och skilja Office 365 nätverkstrafik.
ms.openlocfilehash: abcf6eb8ab963749b451e1f0eeef91d963b76b89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696729"
---
# <a name="office-365-ip-address-and-url-web-service"></a>Webbtjänsten Office 365 IP-adress och URL

Webbtjänsten Office 365 IP-adress och URL hjälper dig att bättre identifiera och särskilja Office 365-nätverkstrafik vilket gör det enklare för dig att utvärdera, konfigurera och hålla dig uppdaterad om ändringarna. Den här REST-baserade webbtjänsten ersätter de tidigare nedladdningsbara XML-filerna, som fasades ut den 2 oktober 2018.

Som kund eller leverantör av perimeternätverksenheter kan du bygga mot den webbtjänsten för Office 365 IP-adress och FQDN-poster. Du kan komma åt data direkt i en webbläsare med hjälp av följande URL:er:

- Använd [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) för den senaste versionen av Office 365 URL:er och IP-adressintervaller.
- Använd [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) för data på sidan Office 365 URL:er och IP-adressintervaller för brandväggar och proxyservrar.
- Om du vill få de senaste ändringarna sedan juli 2018 när webbtjänsten först var tillgänglig använder du [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Som kund kan du använda den här webbtjänsten till att:

- Uppdatera PowerShell-skript för att hämta Office 365-slutpunktsdata och ändra eventuell formatering för dina nätverksenheter.
- Använd informationen för att uppdatera PAC-filer som distribueras till klientdatorer.

Som leverantör av perimeternätverksenheter kan du använda den här webbtjänsten till att:

- Skapa och testa enhetsprogramvara för att ladda ned listan för automatiserad konfiguration.
- Sök efter den aktuella versionen.
- Hämta de aktuella ändringarna.

> [!NOTE]
> Om du använder Microsoft Azure ExpressRoute för att ansluta till Office 365 ska du läsa [Azure ExpressRoute for Office 365](azure-expressroute.md) och bekanta dig med de Office 365-tjänster som stöds över Microsoft Azure ExpressRoute. Läs även artikeln [Office 365 URL:er och IP-adressintervaller](urls-and-ip-address-ranges.md) för att förstå på vilka nätverksbegäranden för Office 365-program som kräver internetanslutning. På så sätt kan du konfigurera dina gränssäkerhetsenheter bättre.

Mer information finns i:

- [Blogginlägg med meddelandet i Office 365 Tech Community-forumet](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Office 365 Tech Community-forumet för frågor om användningen av webbtjänster](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Vanliga parametrar

Dessa parametrar är gemensamma för alla metoder i webbtjänsten:

- **format–<JSON | CSV>** – Som standard är det returnerade dataformatet JSON. Använd den här valfria parametern för att returnera data i en fil med kommaavgränsade värden (CSV).
- **ClientRequestId-\<guid>** – En obligatorisk GUID som du genererar för klientassociation. Generera ett unikt GUID för varje dator som anropar webbtjänsten (de skript som finns på den här sidan genererar ett GUID åt dig). Använd inte de GUID som visas i följande exempel eftersom de kan blockeras av webbtjänsten i framtiden. GUID-formatet är _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, där x representerar ett hexadecimalt tal.

  Om du vill generera ett GUID kan du använda [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) Windows PowerShell-kommandot eller använda en onlinetjänst som [online GUID Generator](https://www.guidgenerator.com/).

## <a name="version-web-method"></a>Versionswebbmetod

Microsoft uppdaterar Office 365 IP-adresser och FQDN-poster i slutet av varje månad. Out-of-band-uppdateringar publiceras ibland på grund av supportproblem, säkerhetsuppdateringar och andra operativkrav.

Data för varje publicerad instans tilldelas ett versionsnummer och versionswebbmetoden gör att du kan söka efter den senaste versionen av varje instans av Office 365-tjänsten. Vi rekommenderar att du kontrollerar versionen inte är oftare än en gång i timmen.

Parametrarna för versionswebbmetoden är:

- **AllVersions = <true | false>** – versionen som returneras är den senaste versionen. Ta med den här valfria parametern för att begära alla publicerade versioner sedan webbtjänsten släpptes.
- **Format = <JSON | CSV | RSS>** – förutom JSON- och CSV-format kan du även använda versionswebbmetoden av RSS. Du kan använda den här valfria parametern tillsammans med parametern _AllVersions = True_ för att begära en RSS-feed som kan användas med Outlook eller andra RSS-läsare.
- **Instance = <Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** – i den här valfria parametern anges vilken instans som ska returnera versionen för. Om den utelämnas returneras alla instanser. Giltiga instanser är: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.

Versionswebbmetoden är inte begränsat och returnerar aldrig 429 HTTP-svarskod. Svaret på versionswebbmetoden innehåller ett huvud för cache-kontroll som rekommenderar cachelagring av data i 1 timme. Resultatet av versionswebbmetoden kan vara en enskild post eller en matris med poster. Elementen i varje post är:

- instans – Office 365-tjänstinstansens kortnamn.
- senaste – Den senaste versionen för den angivna instansens slutpunkter.
- versioner – En lista över alla tidigare versioner för den angivna instansen. Det här elementet ingår endast om parametern _Allaversioner_ är sann.

### <a name="examples"></a>Exempel:

Exempel 1 begär URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Denna URI returnerar den senaste versionen av varje Office 365-tjänstinstans. Exempelresultat:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> GUID för parametern ClientRequestID i dessa URI:er är bara ett exempel. Om du vill prova webbtjänstens URI:er måste du generera en egen GUID. De GUID som visas i dessa exempel kan blockeras av webbtjänsten i framtiden.

Exempel 2 begär URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Denna URI returnerar den senaste versionen av den angivna Office 365-tjänstinstansen. Exempelresultat:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

Exempel 3 begär URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Denna URI visas resultatet i CSV-format. Exempelresultat:

```csv
instance,latest
Worldwide,2018063000
```

Exempel 4 begär URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Denna URI visar alla tidigare versioner som har publicerats för den globala Office 365-tjänstinstansen. Exempelresultat:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

Exempel 5 RSS feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)

Den här URI:n visar ett RSS-flöde av publicerade versioner som innehåller länkar till listan över ändringar för varje version. Exempelresultat:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Slutpunktswebbmetod

Slutpunktswebbmetoden returnerar alla poster för IP-adressintervall och URL-adresser som utgör Office 365-tjänsten. De senaste data från webbmetoden för slutpunkter ska alltid användas för nätverksenhetskonfiguration. Microsoft ger dig ett meddelande 30 dagar innan de publicerar nya tillägg för att ge dig tid att uppdatera listor för åtkomstkontroll och förbikopplingslistor för proxyserver. Vi rekommenderar att du bara anropar webbmetoden för slutpunkter igen när versionswebbmetoden anger att en ny version av data är tillgänglig.

Parametrarna för slutpunktswebbmetoden är:

- **ServiceAreas = <Gemensamma | Exchange | SharePoint | Skype>** – en kommaavgränsad lista med tjänstområden. Giltiga objekt är _Gemensamma_, _Exchange_, _SharePoint_, _Skype_. Eftersom _Gemensamma_ tjänstområdesobjekt är en förutsättning för alla andra tjänstområden inkluderar webbtjänsten alltid dem. Om du inte tar med den här parametern returneras alla tjänstområden.
- **Klientorganisationsnamn = <tenant_name>** – ditt Office 365-klientorganisationsnamn. Webbtjänsten tar det angivna namnet och infogar det i delar av URL-adresser som innehåller klientnamnet. Om du inte anger ett klientnamn har de delarna av URL-adresserna jokertecken (\*).
- **NoIPv6=<true | false>** – Ange detta som _sant_ för att utelämna IPv6-adresser från resultatet om du inte använder IPv6 i nätverket.
- **Instance = <Worldwide| China | Germany | USGovDoD | USGovGCCHigh>** – den nödvändiga parametern anger vilken instans som ska returnera slutpunkterna. Giltiga instanser är: _Worldwide_, _China_, _Germany_, _USGovDoD_ och _USGovGCCHigh_.

Om du anropar webbmetoden för slutpunkter för många gånger från samma IP-adress för klient, kan det hända att du får HTTP-svarskod _429 (för många begäranden)_. Om du får svarskoden väntar du i en timme innan du upprepar begäran eller genererar ett nytt GUID för begäran. Som en allmän metod är att bara anropa webbmetoden för slutpunkter när versionswebbmetoden anger att en ny version är tillgänglig.

Resultatet från slutpunktswebbmetoden är en matris med poster där varje post representerar en specifik slutpunktsuppsättning. Elementen för varje post är:

- id – Det oföränderliga ID-numret för slutpunktsuppsättningen.
- serviceArea – Tjänstområdet som detta är en del av: _Gemensamma_, _Exchange_, _SharePoint_ eller _Skype_.
- URL:er – Webbadresser för slutpunktsuppsättningen. En JSON-matris med DNS-poster. Utelämnas om tomt.
- tcpPorts – TCP-portar för slutpunktsuppsättningen. Alla portelement är formaterade som en kommaavgränsad lista med portar eller portintervaller avgränsade med ett bindestreck (-). Portar gäller för alla IP-adresser och alla URL-adresser i slutpunktsuppsättningen för en specifik kategori. Utelämnas om tomt.
- udpPorts – UDP-portar för IP-adressintervallerna i den här slutpunktsuppsättningen. Utelämnas om tomt.
- ips – IP-adressintervallen som är kopplade till den här slutpunktsuppsättningen som är kopplade till de angivna TCP- eller UDP-portarna. En JSON-matris med IP-adressintervall. Utelämnas om tomt.
- kategori – Anslutningskategorin för slutpunktsuppsättningen. Giltiga värden är _Optimera_, _Tillåta_ och _Standard_. Om du söker i webbmetoden för slutpunkter för en viss IP-adress eller URL är det möjligt att frågan returnerar flera olika kategorier. I så fall följer du rekommendationer för kategorin med högsta prioritet. Om till exempel slutpunkten visas i båda _Optimera_ och _Tillåta_ ska du följa kraven för _Optimera_. Obligatoriskt.
- expressRoute – _Sant_ om den här slutpunktsuppsättningen dirigeras över Microsoft Azure ExpressRoute annars _Falskt_.
- obligatoriskt – _Sant_ om den här slutpunktsuppsättningen kräver anslutningar om Office 365 ska stödjas. _False_ om denna slutpunktsuppsättning är valfri.
- anteckningar – För valfria slutpunktsuppsättningar beskriver den här texten Office 365-funktioner som inte skulle vara tillgänglig om IP-adresserna eller webbadresserna i den här slutpunktsuppsättningen inte kan nås i nätverket. Utelämnas om tomt.

### <a name="examples"></a>Exempel:

Exempel 1 begär URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Denna URI hämtar alla slutpunkter för den globala Office 365-instansen för alla arbetsbelastningar. Exempelresultat som visar ett utdrag av utdata:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Observera att den fullständiga utskriften av begäran i det här exemplet skulle innehålla andra slutpunktsuppsättningar.

Exempel 2 begär URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Det här exemplet hämtar slutpunkter för den globala Office 365-instansen för endast Exchange Online och beroenden.

Utdata för exempel 2 liknar exempel 1, förutom att resultatet inte innehåller slutpunkter för SharePoint Online eller Skype för företag – Online.

## <a name="changes-web-method"></a>Ändringswebbmetod

Ändringswebbmetoden returnerar de senaste uppdateringarna som har publicerats är vanligtvis föregående månads ändringar av IP-adressintervall och URL-adresser.

De mest kritiska ändringarna av slutpunkternas data är nya URL:er och IP-adresser. Om det inte går att lägga till en IP-adress i en kontrollista för en brandvägg eller en URL-adress till en förbikopplingslista för proxyserver kan orsaka driftavbrott för Office 365-användare bakom nätverksenheten. Trots operativ krav publiceras nya slutpunkter till webbtjänsten 30 dagar före det datum då slutpunkterna allokeras för att ge dig tid att uppdatera listor för åtkomstkontroll och förbikopplingslistor för proxyserver.

Den obligatoriska parametern för ändringswebbmetoden är:

- **Version-\<YYYYMMDDNN>** – Obligatorisk URL-dirigeringsparameter. Det här värdet är versionen som du för närvarande har implementerat. Webbtjänsten kommer att returnera ändringarna sedan den versionen. Formatet är _YYYYMMDDNN_, där _NN_ är ett naturligt tal som ökas om det finns flera versioner som måste publiceras på en enda dag och _00_ som representerar den första uppdateringen för en viss dag. Webbtjänsten kräver att _version_-parametern innehåller exakt 10 siffror.

Ändringswebbmetoden är begränsad på samma sätt som webbmetoden för slutpunkter. Om du får en 429 HTTP-svarskod väntar du i 1 timme innan du upprepar begäran eller genererar ett nytt GUID för begäran.

Resultatet från ändringswebbmetoden är en matris med poster där varje post representerar en ändring i en specifik version av slutpunkterna. Elementen för varje post är:

- id – Oföränderligt ID för ändringsposten.
- endpointSetId – ID för slutpunktsuppsättningsposten som har ändrats.
- disposition – beskriver vad ändringen gjorde till i slutpunktsuppsättningens post. Värdena är _ändra_, _lägga till_ eller _ta bort_.
- impact – alla förändringar blir inte lika viktiga för alla miljöer. Det här elementet beskriver den förväntade effekten på en företagsnätverksgräns som ett resultat av ändringen. Det här elementet inkluderas bara i ändringsposter av versionen **2018112800** och senare. Alternativ som påverkar effekten är: – AddedIp – en IP-adress har lagts till i Office 365 och kommer snart att vara aktiv för tjänsten. Det här är en ändring som du måste utföra på en brandvägg eller annan nätverksgränsenhet för nivå 3. Om du inte lägger till det innan vi börjar använda det kan du uppleva ett avbrott.
  – AddedUrl – en URL-adress har lagts till i Office 365 och kommer snart att finnas kvar i tjänsten. Det här är en ändring som du måste utföra på en proxyserver eller URL-tolkande nätverksgränsenhet. Om du inte lägger till den här URL:en innan vi börjar använda den, kan du uppleva ett avbrott.
  – AddedIpAndUrl – både en IP-adress och en URL lades till. Det här är en ändring som du måste utföra antingen på en brandväggsenhet på nivå 3 eller proxyserver eller URL-tolkande enhet. Om du inte lägger till detta IP/URL-par innan vi börjar använda det kan du uppleva ett avbrott.
  – RemovedIpOrUrl – minst en IP-adress eller URL har tagits bort från Office 365. Ta bort nätverksslutpunkterna från dina gränsenheter, men det finns ingen deadline för dig att göra det.
  – ChangedIsExpressRoute – Microsoft Azure ExpressRoutens supportattribut har ändrats. Om du använder Microsoft Azure ExpressRoute kan du behöva vidta åtgärder beroende på din konfiguration.
  – MovedIpOrUrl – vi har flyttat en IP-adress eller URL mellan den här slutpunktsuppsättningen och en annan. Generellt krävs ingen åtgärd.
  – RemovedDuplicateIpOrUrl – vi har tagit bort en dubblett av IP-adressen eller URL:en, men den är fortfarande publicerad för Office 365. Generellt krävs ingen åtgärd.
  – OtherNonPriorityChanges – vi har ändrat något som är mindre kritiskt än alla andra alternativ, t. ex. innehållet i ett anteckningsfält.
- version – Version av den publicerade slutpunktsuppsättningen i vilken ändringen infördes. Versionsnummer är i formatet _ÅÅÅÅMMDDNN_, där _NN_ är ett naturligt tal som ökas automatiskt om det finns flera obligatoriska versioner som ska publiceras på samma dag.
- previous – En underordnad struktur med information om tidigare värden för ändrade element i slutpunktsuppsättningen. Det här inkluderas inte för nyligen tillagda slutpunktsuppsättningar. Innehåller  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ och _notes_.
- aktuella – En underordnad struktur med information om uppdaterade värden för ändrade element i slutpunktsuppsättningen. Innehåller _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ och _notes_.
- add – En underordnad struktur med information om objekt som ska läggas till i slutpunktsuppsättningssamlingar. Utelämnas om det inte finns några tillägg.
  – effectiveDate – Definierar data när tilläggen börjar gälla i tjänsten.
  – ips – Objekt som ska läggas till i _ips_-matrisen.
  – urls – Objekt som ska läggas till i _url_-matrisen.
- remove – En underordnad struktur med information om objekt som ska tas bort från slutpunktsuppsättningen. Utelämnas om det inte finns några borttagningar.
  ips – Objekt som ska tas bort från _ips_-matrisen.
  urls – Objekt som ska tas bort från _urls_-matrisen.

### <a name="examples"></a>Exempel:

Exempel 1 begär URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Detta begär alla tidigare ändringar i den globala Office 365-tjänstinstansen. Exempelresultat:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

Exempel 2 begär URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Detta begär ändringar sedan den angivna versionen för den globala Office 365-instansen. I det här fallet är den senaste versionen den som anges. Exempelresultat:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Exempel på Windows PowerShell-skript

Du kan köra detta Windows PowerShell-skript för att se om det finns åtgärder du ska vidta för uppdaterade data. Du kan köra det här skriptet som en schemalagd aktivitet för att söka efter en versionsuppdatering. Om du vill undvika överdriven belastning på webbtjänsten försöker du inte köra skriptet mer än en gång i timmen.

Skriptet gör följande:

- Kontrollera versionsnumret för aktuella Office 365-slutpunkter för hela instansen genom att anropa webbtjänstens REST API.
- Söker efter en aktuell versionsfil på _$Env:TEMP\O365_endpoints_latestversion.txt_. Sökvägen till den globala variabeln **$Env:TEMP** är vanligtvis _C:\Users\\<username\>\AppData\Local\Temp_.
- Om det här är första gången skriptet körs returnerar skriptet den aktuella versionen och alla aktuella IP-adresser och URL-adresser och skriver slutpunktsversionen till fil _$Env:TEMP\O365_endpoints_latestversion.txt_ och slutpunktsdata kommer att skrivas till filen _$Env:TEMP\O365_endpoints_data.txt_. Du kan ändra sökvägen och/eller namnet på utdatafilen genom att redigera dessa rader:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- För varje efterföljande körning av skriptet, om den senaste webbtjänstversionen är identisk med versionen i filen _O365_endpoints_latestversion.txt_ avslutas skriptet utan att några ändringar görs.
- När den senaste webbtjänstversionen är nyare än den version som finns i filen _O365_endpoints_latestversion.txt_ returnerar skriptet slutpunkterna och filter för kategorislutpunkterna **Tillåta** och **Optimera**, uppdaterar versionen i filen _O365_endpoints_latestversion.txt_ och skriver uppdaterad data till _O365_endpoints_data.txt_.

Skriptet genererar ett unikt _ClientRequestId_ för den dator som körs och återanvänder detta ID för flera samtal. Detta ID finns i filen _O365_endpoints_latestversion.txt_.

### <a name="to-run-the-powershell-script"></a>Om du vill köra Windows PowerShell-skriptet

1. Kopiera skriptet och spara det till den lokala hårddisken eller till en skriptplats som _Get-O365WebServiceUpdates.ps1_.
1. Kör skriptet i önskad skriptredigerare, t. ex. Windows PowerShell ISE eller VS-koden eller från en Windows PowerShell-konsol med följande kommando:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Det finns inga parametrar att skicka till skriptet.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Exempel på Python-skript

Här är ett Python-skript, testat med Python 3.6.3 på Windows 10, som du kan köra för att se om det finns åtgärder du ska vidta för de uppdaterade data. Det här skriptet kontrollerar versionsnumret för den globala Office 365-instansens slutpunkter. När det finns en ändring laddar det ned slutpunkterna och filtrerar för slutpunkterna i kategorin _Tillåt_ och _Optimera_. Det använder även en unik ClientRequestId på flera anrop och sparar den senaste versionen som finns i en tillfällig fil. Du ska anropa skriptet en gång i timmen för att söka efter en versionsuppdatering.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Versionshantering av webbtjänstgränssnitt

Uppdateringar av parametrar eller resultat för de här webbtjänstmetoderna kan bli obligatoriska i framtiden. När den allmänt tillgängliga versionen av dessa webbtjänster har publicerats utför Microsoft rimliga åtgärder för att tillhandahålla förhandsinformation om viktiga uppdateringar av webbtjänsten. När Microsoft anser att en uppdatering kräver ändringar av de klienter som använder webbtjänsten, behåller Microsoft den tidigare versionen (en version bakåt) av webbtjänsten tillgänglig under minst 12 månader efter lanseringen av den nya versionen. Kunder som inte uppgraderar under tiden kommer kanske inte att kunna komma åt webbtjänsten och dess metoder. Kunderna måste säkerställa att klienter i webbtjänsten fortsätter att fungera utan fel om följande ändringar görs i webbtjänstens gränssnittssignatur:

- Tillägg av en ny valfri parameter i en befintlig webbmetod som inte behöver tillhandahållas av äldre klienter och inte påverkar det resultat en äldre klient får.
- Tillägg av ett nytt namngivet attribut i något av REST-svarsobjekten eller fler kolumner i CSV-svarsfilen.
- Tillägg av en ny webbmetod med ett nytt namn som inte anropas av äldre klienter.

## <a name="update-notifications"></a>Uppdateringsaviseringar

Du kan använda några olika metoder för att få e-postmeddelanden när ändringar av IP-adresser och URL-adresser publiceras i webbtjänsten.

- Information om hur du använder en Microsoft Flow-lösning finns i [Använda Microsoft Flow för att få ett e-postmeddelande om ändringar i Office 365 IP-adresser och URL:er](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- För att distribuera en Azure Logic-app med en ARM-mall finns i [Office 365 uppdateringsmeddelande (v 1.1)](https://aka.ms/ipurlws-updates-template).
- Om du vill skriva ett eget meddelandeskript med Windows PowerShell kan du läsa [Skicka med e-postmeddelande](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Exportera en proxy-PAC-fil

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) är ett Windows PowerShell-skript som läser de senaste nätverksslutpunkterna från webbtjänsten 365 Office IP-adress och URL och skapar ett exempel på en PAC-fil. Information om hur du använder Get-PacFile finns i [Använda en PAC-fil för direkt routning av vitala Office 365-trafik](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Relaterade ämnen
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)
  
[Office 365-slutpunkter – vanliga frågor och svar](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Office 365 nätverks- och prestandajustering](network-planning-and-performance.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)
  
[Prestanda för mediekvalitet och nätverksanslutning i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimera ditt nätverk för Skype för företag – Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).
