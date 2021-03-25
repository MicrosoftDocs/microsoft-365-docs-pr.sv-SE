---
title: Meddelandehuvuden för antiskräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig mer om de fält som läggs till i meddelanden av Exchange Online Protection (EOP). De här huvudfälten innehåller information om meddelandet och hur det behandlades.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04b98ad6b1ca136429395dfd1636b43bbbc6878a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207516"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Meddelandehuvuden för antiskräppost i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I alla Microsoft 365-organisationer används Exchange Online Protection (EOP) för att söka igenom alla inkommande meddelanden för skräp post, skadlig kod och andra hot. Resultatet av dessa genomsökningar läggs till i följande huvud fält i meddelanden:

- **X-Forefront-Antispam-rapport**: Innehåller information om meddelandet och hur det behandlades.

- **X-Microsoft-Antispam**: Innehåller ytterligare information om bulk mail och phishing.

- **Autentiseringsresultat**: Innehåller information om SPF, DKIM och DMARC (e-autentisering).

Den här artikeln beskriver vad som är tillgängligt i dessa rubrikfält.

För information om hur man visar ett e-postmeddelandes meddelanderubrik i olika e-postklienter, se [Visa e-postmeddelandehuvud i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Du kan kopiera och klistra in innehållet i ett meddelandehuvud i [Analysverktyg för meddelanderubrik](https://mha.azurewebsites.net/). Det här verktyget hjälper till att tolka rubriker och lägga till dem i ett mer läsbart format.

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report meddelanderubrikfält

När du har information om meddelande rubriken hittar du i rubriken **X-Forefront-Antispam-Report**. Det kommer att finnas flera fält- och värdepar i denna rubrik separerade med semikolon (;). Till exempel:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

De enskilda fälten och värdena beskrivs i följande tabell.

> [!NOTE]
> **X-Forefront-antispam-Report**-huvudet innehåller många olika fält och värden. Fält som inte beskrivs i tabellen används uteslutande av Microsofts anti-spam-team för diagnostiska ändamål.

****

|Fält|Beskrivning|
|---|---|
|`ARC`|I `ARC` protokoll finns följande fält: <ul><li>`AAR`: Sparar innehållet i **verifierings resultat** huvud från DMARC.</li><li>`AMS`: Inkluderar kryptografiska signaturer för meddelandet.</li><li>`AS`: Inkluderar kryptografiska signaturer för meddelande rubrikerna. Detta fält innehåller en tagg av en kedjevalidering som heter `"cv="`, som inkluderar resultatet av kedjevalideringen **som ingen**, **godkänd** eller **misslyckad**.</li></ul>|
|`CAT:`|Kategori för den skyddspolicy som används för meddelandet: <ul><li>`BULK`: Bulk</li><li>`DIMP`: Domän personifiering</li><li>`GIMP`: [Postbaserad intelligensbaserad efterligning](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` eller `HPHISH` : phishing med högt förtroende</li><li>`HSPM`: Spam med högt förtroende</li><li>`MALW`: Malware</li><li>`PHSH`: Phishing</li><li>`SPM`: Skräppost</li><li>`SPOOF`: Förfalskning</li><li>`UIMP`: Användar personifiering</li><li>`AMP`: Anti-malware</li><li>`SAP`: Säkra bifogade filer</li><li>`OSPM`: Utgående skräp post</li></ul> <p> Ett inkommande meddelande kan flaggas av flera olika typer av skydd och flera identifieringsgenomsökningar. Policyer har olika prioriteringar och den policy som har högst prioritet kommer att tillämpas först. Se [Vilken policy gäller när flera skyddsmetoder och identifieringsgenomsökningar körs på din e-post](how-policies-and-protections-are-combined.md) för mer information.|
|`CIP:[IP address]`|Den anslutande IP-adressen. Du kan använda den här IP-adressen i listan över tillåtna IP-adresser eller IP-adresser som ska blockeras. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).|
|`CTRY`|Källlandet, vilket bestäms av den anslutande IP-adressen, som kanske inte är samma som den ursprungliga IP-adressen.|
|`H:[helostring]`|En anslutande e-mailservers HELO- eller OEHLO-sträng.|
|`IPV:CAL`|Meddelandet hoppade över skräppostfiltrering eftersom IP-adressen fanns i listan över tillåtna IP-adresser. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).|
|`IPV:NLI`|IP-adressen hittades inte på någon IP-rykte-lista.|
|`LANG`|Det språk på vilket meddelandet skrevs, specificerat av landskoden (till exempel ru_RU för ryska).|
|`PTR:[ReverseDNS]`|PTR-posten (även kallad omvänd DNS-sökning) för källans IP-adress.|
|`SCL`|Meddelandets SCL (Spam Confidence Level). Ett högre värde innebär att det är mer troligt att meddelandet är skräppost. Mer information finns i [Konfidensnivå för skräppost (SCL)](spam-confidence-levels.md).|
|`SFTY`|Meddelandet identifierades som phishing och kommer att markeras med något av följande värden: <ul><li>9.1: Standardvärde. Meddelandet innehåller några eller alla av följande element: en nät fiske webb adress, ett annat phishing-innehåll eller har marker ATS som nätfiske via lokalt Exchange.</li><li>9.11: [intra-org eller inom organisationen](anti-spoofing-protection.md#different-types-of-spoofing). Säkerhetstipset för förfalskningar inom organisationen läggs till i meddelandet.</li><li>9.19: Domänimitation. Den sändande domänen försöker [imitera en skyddad domän](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Säkerhetstipset för domänskydd läggs till i meddelandet (om det är aktiverat).</li><li>9.20: Användarimitation. Den sändande användaren försöker imitera en användare i mottagarens organisation eller en skyddad användare som anges i en skyddprincip i Microsoft Defender för Office 365. Säkerhetstipset för användarefersonlighet läggs till i meddelandet (om det är aktiverat).</li><li>9.21: [Förfalskning mellan domäner](anti-spoofing-protection.md#different-types-of-spoofing). Meddelandet misslyckade skydd mot förfalskning. Avsändarens e-postdomän i från-huvudet verifierar inte och är en extern domän. Används i kombination med [sammansatt autentisering](#authentication-results-message-header-fields).</li><li>9.22: Samma som 9.21, förutom att användaren har en säker avsändare som har åsidosatts.</li><li>9.23: Samma som 9.22, förutom att organisationen har en betrodd användare eller domän som har åsidosatts.</li><li>9.24: Samma som 9.23, förutom att användaren har en Exchange-dataflödesregel (även känt som en transportregel) som har åsidosatts.</li></ul>|
|`SFV:BLK`|Filtreringen hoppades över och meddelandet blockerades eftersom det skickades från en adress i en användares lista med spärrade avsändare. <p> Mer information om hur administratörer kan hantera användarens lista med blockerade avsändare finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:NSPM`|Meddelandet har markerats som icke skräppost av skräppostfiltret och det har skickats till avsedda mottagare.|
|`SFV:SFE`|Filtreringen hoppades över och meddelandet tilläts eftersom det skickades från en adress i en användares listan Betrodda avsändare. <p> Mer information om hur administratörer kan hantera användarens lista med säkra avsändare finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:SKA`|Meddelandet hoppades över skräp post filtreringen och skickades till Inkorgen eftersom avsändaren fanns i listan med tillåtna avsändare eller listan över tillåtna domäner i en princip för skräp post skydd. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|`SFV:SKB`|Meddelandet markeras som skräp post eftersom det matchade en avsändare i listan med spärrade avsändare eller listan över blockerade domäner i en princip för skräp post skydd. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|`SFV:SKI`|I likhet med SFV: SKN hoppade skräp post filter av en annan anledning (till exempel en inomeuropeisk e-post i en klient organisation).|
|`SFV:SKN`|Meddelandet markerades som icke skräp post före bearbetningen av skräp post filtreringen. Exempelvis markerades meddelandet som SCL-1 eller **kringgå skräp post filtrering** de av en regel för e-postflöde.|
|`SFV:SKQ`|Meddelandet har släppts ur sin karantän och skickats till avsedda mottagare.|
|`SFV:SKS`|Meddelandet markeras som skräp post före bearbetningen av skräp post filtreringen. Meddelandet är till exempel markerat som SCL 5 till 9 i en regel för e-postflöde.|
|`SFV:SPM`|Meddelandet markerades som skräppost av skräppostfiltret.|
|`SRV:BULK`|Meddelandet identifierades som massutskick av skräppostfiltreringen och tröskeln för BCL (Bulk Complaint Level). När parametern _MarkAsSpamBulkMail_ är `On` (det är aktiverat som standard) markeras ett massutskick av e-postmeddelanden som högprioriterad skräppost (SCL 9). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|`X-CustomSpam: [ASFOption]`|Meddelandet matchade ett avancerat alternativ för skräppostfiltrering (ASF). Om du vill visa värdet för X-header för respektive ASF-inställning läser du [Inställningar för avancerat skräppostfilter (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam meddelanderubrikfält

Följande tabell beskriver användbara fält i meddelanderubriken **X-Microsoft-Antispam**. Andra fält i den här rubriken används exklusivt av Microsofts anti-spam-team av diagnostiska skäl.

****

|Fält|Beskrivning|
|---|---|
|`BCL`|Meddelande BCL (Bulk Complaint Level). En högre BCL anger att ett Mass utskick innebär att det är mer troligt att vi skapar klagomål (och är därför förmodligen mer sannolikt att få skräp post). Se [Klagomålsnivå på massutskick (BCL)](bulk-complaint-level-values.md) för mer information.|
|

## <a name="authentication-results-message-header"></a>Authentication-results meddelanderubrik

Resultatet av kontroller för e-postautentisering för SPF, DKIM och DMARC registreras (stämplas) i **verifierings resultat** meddelande rubriken i inkommande meddelanden.

I följande lista beskrivs den text som läggs till i **verifierings resultat** huvud för varje typ av verifiering av e-postkontroll:

- SPF använder följande syntax:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Till exempel:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM använder följande syntax:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Till exempel:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC använder följande syntax:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Till exempel:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Autentisering-resultat meddelande rubrik fält

I följande tabell beskrivs fälten och möjliga värden för alla kontroller för e-postverifiering.

****

|Fält|Beskrivning|
|---|---|
|`action`|Anger att den åtgärd som utförs av skräppostfiltret baseras på resultaten av DMARC-kontrollen. Till exempel: <ul><li>**oreject** eller **o.reject**: står för override reject. I detta fall använder Microsoft 365 åtgärden när det tar emot ett meddelande som misslyckas med DMARC-kontrollen från en domän vars DMARC TXT-register har en policy av p=reject. I stället för att ta bort eller avvisa meddelandet markerar Microsoft 365 meddelandet som skräppost. Se [Så hanterar Microsoft 365 inkommande e-postmeddelanden som inte går igenom DMARC](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc) för mer information om varför Microsoft 365 är konfigurerat på det viset.</li><li>**pct.quarantine**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på karantän, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen.</li><li>**pct.reject**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på att avslå, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen.</li><li>**PermError**: ett permanent fel uppstod när DMARC utvärderades, t. ex. ett felaktigt utformat DMARC register i DNS. Att försöka skicka meddelandet igen ger antagligen samma resultat. Försök istället att kontakta domänens ägare för att lösa problemet.</li><li>**temperror**: ett temporärt fel inträffade under DMARC-utvärderingen. Du kanske kan begära att avsändaren skickar meddelandet igen senare för att bearbeta e-postmeddelandet ordentligt.</li></ul>|
|`compauth`|Resultat av sammansatt autentisering. Används av Microsoft 365 för att kombinera flera typer av autentisering som SPF, DKIM, DMARC eller andra delar av meddelandet för att avgöra huruvida meddelandet är autentiserat eller inte. Använder Från:-domänen som grund för utvärderingen.|
|`dkim`|Beskriver resultaten av meddelandets DKIM-kontroll. Möjliga värden inkluderar: <ul><li>**pass**: anger att meddelandet gick igenom DKIM-kontrollen.</li><li>**fail (orsak)**: anger att meddelandet inte gick igenom DKIM-kontrollen och varför. Om du till exempel inte har signerat meddelandet eller om signaturen inte har verifierats.</li><li>**none**: anger att meddelandet inte signerats. Detta indikerar kanske, men kanske inte, att domänen har ett DKIM-register eller att DKIM-registret inte utvärderats till ett resultat, endast att meddelandet inte signerats.</li></ul>|
|`dmarc`|Beskriver resultaten av DMARC-kontrollen av meddelandet. Möjliga värden inkluderar: <ul><li>**pass**: anger att meddelandet gick igenom DMARC-kontrollen.</li><li>**fail**: anger att meddelandet inte gick igenom DMARC-kontrollen.</li><li>**bestguesspass**: anger att det inte finns något DMARC TXT-register för domänen, men om ett sådant fanns skulle meddelandet ha gått igenom DMARC-kontrollen. Det beror på att domänen i `5321.MailFrom`-adressen (t. ex. E-POST FRÅN-adress, P1-avsändare eller avsändare av kuvert) stämmer överens med domänen i `5322.From`-adressen (kallas även för Från-adressen eller P2-avsändaren).</li><li>**none**: anger att det inte finns något DMARC TXT-register för den sändande domänen i DNS.|
|`header.d`|Domän som identifierats i DKIM-signaturen om någon. Detta är den domän som tillfrågas om den publika nyckeln.|
|`header.from`|Domänen för `5322.From`-adressen i e-postmeddelanderubriken. (även känd som Från-adressen eller P2-avsändaren). Mottagaren ser Från-adressen i e-postklienter.|
|`reason`|Orsaken till att den sammansatta autentiseringen gick igenom eller inte. Värdet är en tresiffrig kod. Till exempel: <ul><li>**000**: meddelandet misslyckades explicit autentisering (`compauth=fail`). Till exempel kan meddelandet ha tagit emot en misslyckande från DMARC med karantän eller avslag som åtgärd.</li><li>**001**: Meddelandet misslyckades implicit autentisering (`compauth=fail`). Det innebär att avsändardomänen inte hade publicerade poster för e-postautentisering eller hade en svagare felprincip (SPF SoftFail (lindrigt fel) eller neutral, DMARC-principen `p=none`).</li><li>**002**: Organisationen har en princip för avsändare/domän par som uttryckligen förbjuds från att skicka falska e-postmeddelanden. Den här inställningen anges manuellt av en administratör.</li><li>**010**: betyder att meddelandet inte klarade DMARC, med åtgärden att avvisa eller placera i karantän och avsändardomänen är en av organisationens godkända domäner (det här är en del av förfalskning inom organisationen (”self-to-self” eller ”intra-org”)).</li><li>**1xx** eller **7xx**: meddelandet gick igenom autentiseringen (`compauth=pass`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**2xx**: Meddelandet gick igenom implicit autentisering mjukt (`compauth=softpass`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**3xx**: meddelandet kontrollerades inte för sammansatt autentisering (`compauth=none`).</li><li>**4xx** eller **9xx**: meddelande förbigick sammansatt autentisering (`compauth=none`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**6xx**: Meddelandet inte klarade implicit e-postautentisering, och avsändardomänen är en av organisationens godkända domäner (det här är en del av förfalskning inom organisationen (”self-to-self” eller ”intra-org”)).</li></ul>|
|`smtp.mailfrom`|Domänen för `5321.MailFrom`-adressen (kallas även för E-POST FRÅN-adress, P1-avsändare eller avsändare av kuvert). Det är den e-postadress som används för rapporter om utebliven leverans (kallas även för NDR-rapporter eller bouncemeddelanden).|
|`spf`|Beskriver resultaten av SPF-kontrollen av meddelandet. Möjliga värden inkluderar: <ul><li>`pass (IP address)`: SPF-kontrollen för meddelandet har skickats och inkluderar avsändarens IP-adress. Klienten har tillåtelse att skicka eller vidarebefordra e-post på avsändarens domän.</li><li>`fail (IP address)`: SPF-kontrollen för meddelandet misslyckades och inkluderar avsändarens IP-adress. Det här kallas ibland för en _hard fail_.</li><li>`softfail (reason)`: SPF-posten som anges som värddator som inte tillåts skicka, men är i över gången.</li><li>`neutral`: SPF-posten anger explicit att den inte kräver att IP-adressen har tillåtelse att skicka.</li><li>`none`: Domänen saknar en SPF-post eller så utvärderas SPF-posten inte som ett resultat.</li><li>`temperror`: Ett tillfälligt fel har inträffat. Till exempel ett DNS-fel. Samma kontroll kan senare lyckas.</li><li>`permerror`: Ett permanent fel har inträffat. Domänen har till exempel en dåligt formaterad SPF-post.</li></ul>|
|
