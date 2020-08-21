---
title: Meddelandehuvuden för antiskräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om de fält som läggs till i meddelanden av Exchange Online Protection (EOP). De här huvudfälten innehåller information om meddelandet och hur det behandlades.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5400bdbc9d3eef0b8005619f9820a9e71b829a5a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825203"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Meddelandehuvuden för antiskräppost i Microsoft 365

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor söker EOP igenom och infogar huvudet **X-Forefront-Antispam-Report** i varje inkommande e-postmeddelande. Fälten i denna rubrik kan hjälpa administratörer med information om meddelandet och hur det bearbetades. I fälten i **X-Microsoft-antispam**-rubriken finns mer information om massutskick och nätfiske. Utöver dessa två rubriker infogar Exchange Online Protection även resultat av e-postautentisering för varje meddelande det bearbetar i rubriken **Authentication-results**.

För information om hur man visar ett e-postmeddelandes meddelanderubrik i olika e-postklienter, se [Visa e-postmeddelandehuvud i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Du kan kopiera och klistra in innehållet i ett meddelandehuvud i [Analysverktyg för meddelanderubrik](https://mha.azurewebsites.net/). Det här verktyget hjälper till att tolka rubriker och lägga till dem i ett mer läsbart format.

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report meddelanderubrikfält

När du har information om meddelande rubriken hittar du i rubriken **X-Forefront-Antispam-Report**. Det finns flera fält för rubriknamn och värdepar i denna rubrik som är avgränsade med semikolon (;). Till exempel:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

De enskilda fälten och värdena beskrivs i följande tabell.

> [!NOTE]
> Rubriken **X-Forefront-Antispam-Report** innehåller många olika fält och värden för rubriker. Andra fält i den här rubriken som inte beskrivs i tabellen används exklusivt av Microsofts anti-spam-team av diagnostiska skäl.

****

|Rubrikfält|Beskrivning|
|---|---|
|ARC|ARC-protokollet har följande rubriker: <ul><li>AAR: registrerar innehållet i rubriken för verifieringsresultat från DMARC.</li><li>AMS: denna rubrik innehåller kryptografiska signaturer för meddelandet.</li><li>AS: innehåller kryptografiska signaturer för meddelanderubriker. Den här rubriken innehåller en tagg för en kedjeverifiering som kallas "cv=", som inkluderar resultatet av kedjeverifieringen som **ingen**, **gick igenom**och **misslyckades**.</li></ul>|
|CAT:|Kategori för den skyddspolicy som används för meddelandet: <ul><li>BULK: Bulk</li><li>DIMP: Domain Impersonation</li><li>GIMP: imitationsskydd baserat på postlådeinformation</li><li>HPHSH or HPHISH : High confidence phishing</li><li>HSPM: High confidence spam</li><li>MALW: Malware</li><li>PHSH: Phishing</li><li>SPM: Spam</li><li>SPOOF: Spoofing</li><li>UIMP: User Impersonation</li><li>AMP: Anti-malware</li><li>SAP: Säkra bifogade filer</li><li>OSPM: Utgående skräppost</li></ul><br/>Ett inkommande meddelande kan flaggas av flera olika typer av skydd och flera identifieringsgenomsökningar. Policyer har olika prioriteringar och den policy som har högst prioritet kommer att tillämpas först. Se [Vilken policy gäller när flera skyddsmetoder och identifieringsgenomsökningar körs på din e-post](how-policies-and-protections-are-combined.md) för mer information.|
|CIP: \[IP-adress\]|Den anslutande IP-adressen. Du kan använda den här IP-adressen i listan över tillåtna IP-adresser eller IP-adresser som ska blockeras. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).|
|CTRY|Källlandet, vilket bestäms av den anslutande IP-adressen, som kanske inte är samma som den ursprungliga IP-adressen.|
|H:\[helostring\]|En anslutande e-mailservers HELO- eller OEHLO-sträng.|
|IPV:CAL|Meddelandet hoppade över skräppostfiltrering eftersom IP-adressen fanns i listan över tillåtna IP-adresser. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).|
|IPV:NLI|IP-adressen listade inte i någon IP-rykteslista.|
|LANG|Det språk på vilket meddelandet skrevs, specificerat av landskoden (till exempel ru_RU för ryska).|
|PTR:\[ReverseDNS\]|PTR-posten (även kallad omvänd DNS-sökning) för källans IP-adress.|
|SCL|Meddelandets SCL (Spam Confidence Level). Ett högre värde innebär att det är mer troligt att meddelandet är skräppost. Mer information finns i [Konfidensnivå för skräppost (SCL)](spam-confidence-levels.md).|
|SFTY|Meddelandet identifierades som phishing och kommer att markeras med något av följande värden: <ul><li>9.1: Standardvärde. Meddelandet innehåller en URL-adress för nätfiske, kan innehålla annat nätfiske-innehåll eller så kan de ha markerats som nätfiske av ett annat e-postfilter (till exempel lokal Exchange) innan det vidarebefordras till Microsoft 365.</li><li>9.11: [intra-org eller inom organisationen](anti-spoofing-protection.md#different-types-of-spoofing). Meddelande om skydd mot nätfiske där den sändande domänen i rubriken Från: är samma som eller i linje med eller är en del av samma organisation som den mottagande domänen. Säkerhetstipset för förfalskningar inom organisationen läggs till i meddelandet.</li><li>9.19: Domänimitation. Den sändande domänen försöker imitera en skyddad domän (en domän som ägs av mottagarens organisation eller en anpassad domän) som anges i en ATP-skyddsprincip. Säkerhetstipset för domänimitation läggs till i meddelandet (om säkerhetstipset är aktiverat i ATP-skyddsprincipen).</li><li>9.20: Användarimitation. Den sändande användaren försöker imitera en användare i mottagarens organisation eller en skyddad användare som anges i en ATP-skyddsprincip. Säkerhetstipset för imitering av användare läggs till i meddelandet (om säkerhetstipset är aktiverat i ATP-skyddsprincipen).</li><li>9.21: [Förfalskning mellan domäner](anti-spoofing-protection.md#different-types-of-spoofing). Meddelandet gick inte igenom kontroller mot förfalskning och den sändande domänen i rubriken Från: autentiserar inte och är en extern domän. Används i kombination med [CompAuth](#authentication-results-message-header-fields-used-by-microsoft-email-authentication)).</li><li>9.22: Samma som 9.21, förutom att användaren har en säker avsändare som har åsidosatts.</li><li>9.23: Samma som 9.22, förutom att organisationen har en betrodd användare eller domän som har åsidosatts.</li><li>9.24: Samma som 9.23, förutom att användaren har en Exchange-dataflödesregel (även känt som en transportregel) som har åsidosatts.</li></ul>|
|SFV:BLK|Filtreringen hoppades över och meddelandet blockerades eftersom det skickades från en adress i användarens lista över spärrade användare i Outlook (användarens lista med blockerade avsändare).<br/></br> Mer information om hur administratörer kan hantera användarens lista med blockerade avsändare finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:NSPM|Meddelandet har markerats som icke skräppost av skräppostfiltret och det har skickats till avsedda mottagare.|
|SFV:SFE|Filtreringen hoppades över och meddelandet släpptes igenom eftersom det skickades från en adress i användarens lista över säkra användare i Outlook (användarens lista med säkra avsändare).<br/></br> Mer information om hur administratörer kan hantera användarens lista med säkra avsändare finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:SKA|Meddelandet hoppade över skräppostfiltreringen och skickades till inkorgen eftersom det matchade en post i listan med tillåtna avsändare eller listan över tillåtna domäner i en anti-spam-policy. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|SFV:SKB|Meddelandet markeras som skräppost eftersom det matchade en post i listan med blockerade avsändare eller listan över blockerade domäner i en anti-spam-policy. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|SFV:SKI|I likhet med SFV:SKN har meddelandet hoppat över skräppostfiltreringen av annan orsak (till exempel att det är ett e-postmeddelande inom organisationen med en mottagare).|
|SFV:SKN|Meddelandet markerades som icke skräppost före bearbetningen av skräppostfiltreringen (till exempel har meddelandet markerats som SCL-1 eller **kringgå skräppostfiltrering** av en regel för e-postflöde).|
|SFV:SKQ|Meddelandet har släppts ur sin karantän och skickats till avsedda mottagare.|
|SFV:SKS|Meddelandet markerades som icke skräppost före bearbetningen av skräppostfiltreringen (till exempel har meddelandet markerats som SCL-5 till 9 av en regel för e-postflöde).|
|SFV:SPM|Meddelandet markerades som skräppost av skräppostfiltret.|
|SRV:BULK|Meddelandet identifierades som massutskick av skräppostfiltreringen och tröskeln för BCL (Bulk Complaint Level). När parametern _MarkAsSpamBulkMail_ är `On` (det är aktiverat som standard) markeras ett massutskick av e-postmeddelanden som högprioriterad skräppost (SCL 9). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|X-CustomSpam: \[ASFOption\]|Meddelandet matchade ett avancerat alternativ för skräppostfiltrering (ASF). Om du vill visa värdet för X-header för respektive ASF-inställning läser du [Inställningar för avancerat skräppostfilter (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam meddelanderubrikfält

Följande tabell beskriver användbara fält i meddelanderubriken **X-Microsoft-Antispam**. Andra fält i den här rubriken används exklusivt av Microsofts anti-spam-team av diagnostiska skäl.

****

|Rubrikfält|Beskrivning|
|---|---|
|BCL|Meddelande BCL (Bulk Complaint Level). En högre BCL anger att ett massutskick (som också kallas _grå e-post_) är mer sannolikt att skapa klagomål (och därmed med större sannolikhet skräppost). Se [Klagomålsnivå på massutskick (BCL)](bulk-complaint-level-values.md) för mer information.|
|

## <a name="authentication-results-message-header"></a>Authentication-results meddelanderubrik

Resultaten av kontroller mot SPF, DKIM och DMARC registreras, eller stämplas, av Microsoft 365 i meddelanderubriken **Authentication-results** när våra e-postservrar tar emot ett e-postmeddelande.

### <a name="check-stamp-syntax-and-examples"></a>Kontrollera märkningssyntax och exempel

Följande syntax exemplifierar en del av textens märkning som Microsoft 365 tillämpar på meddelanderubriken för varje e-postmeddelande som genomgår en e-postautentiseringskontroll när det tas emot av våra servrar. Märket läggs till i rubriken **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Syntax: SPF-kontrollmärkning

För SPF gäller följande syntax.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Exempel: SPF-kontrollmärkning

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Syntax: DKIM-kontrollmärkning

För DKIM gäller följande syntax.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Exempel: DKIM-kontrollmärkning

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Syntax: DMARC-kontrollmärkning

För DMARC gäller följande syntax.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Exempel: DMARC-kontrollmärkning

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-microsoft-email-authentication"></a>Authentication-results meddelanderubrikfält används av Microsoft-e-postautentisering

Denna tabell beskriver fälten och möjliga värden för varje autentiseringskontroll av e-post.

****

|Rubrikfält|Beskrivning|
|---|---|
|åtgärd|Anger att den åtgärd som utförs av skräppostfiltret baseras på resultaten av DMARC-kontrollen. Till exempel: <ul><li>**oreject** eller **o.reject**: står för override reject. I detta fall använder Microsoft 365 åtgärden när det tar emot ett meddelande som misslyckas med DMARC-kontrollen från en domän vars DMARC TXT-register har en policy av p=reject. I stället för att ta bort eller avvisa meddelandet markerar Microsoft 365 meddelandet som skräppost. Se [Så hanterar Microsoft 365 inkommande e-postmeddelanden som inte går igenom DMARC](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc) för mer information om varför Microsoft 365 är konfigurerat på det viset.</li><li>**pct.quarantine**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på karantän, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen.</li><li>**pct.reject**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på att avslå, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen.</li><li>**PermError**: ett permanent fel uppstod när DMARC utvärderades, t. ex. ett felaktigt utformat DMARC register i DNS. Att försöka skicka meddelandet igen ger antagligen samma resultat. Försök istället att kontakta domänens ägare för att lösa problemet.</li><li>**temperror**: ett temporärt fel inträffade under DMARC-utvärderingen. Du kanske kan begära att avsändaren skickar meddelandet igen senare för att bearbeta e-postmeddelandet ordentligt.</li></ul>|
|compauth|Resultat av sammansatt autentisering. Används av Microsoft 365 för att kombinera flera typer av autentisering som SPF, DKIM, DMARC eller andra delar av meddelandet för att avgöra huruvida meddelandet är autentiserat eller inte. Använder Från:-domänen som grund för utvärderingen.|
|dkim|Beskriver resultaten av meddelandets DKIM-kontroll. Möjliga värden inkluderar: <ul><li>**pass**: anger att meddelandet gick igenom DKIM-kontrollen.</li><li>**fail (orsak)**: anger att meddelandet inte gick igenom DKIM-kontrollen och varför. Om du till exempel inte har signerat meddelandet eller om signaturen inte har verifierats.</li><li>**none**: anger att meddelandet inte signerats. Detta indikerar kanske, men kanske inte, att domänen har ett DKIM-register eller att DKIM-registret inte utvärderats till ett resultat, endast att meddelandet inte signerats.</li></ul>|
|dmarc|Beskriver resultaten av DMARC-kontrollen av meddelandet. Möjliga värden inkluderar: <ul><li>**pass**: anger att meddelandet gick igenom DMARC-kontrollen.</li><li>**fail**: anger att meddelandet inte gick igenom DMARC-kontrollen.</li><li>**bestguesspass**: anger att det inte finns något DMARC TXT-register för domänen, men om ett sådant fanns skulle meddelandet ha gått igenom DMARC-kontrollen. Det beror på att domänen i `5321.MailFrom`-adressen (t. ex. E-POST FRÅN-adress, P1-avsändare eller avsändare av kuvert) stämmer överens med domänen i `5322.From`-adressen (kallas även för Från-adressen eller P2-avsändaren).</li><li>**none**: anger att det inte finns något DMARC TXT-register för den sändande domänen i DNS.|
|header.d|Domän som identifierats i DKIM-signaturen om någon. Detta är den domän som tillfrågas om den publika nyckeln.|
|header.from|Domänen för `5322.From`-adressen i e-postmeddelanderubriken. (även känd som Från-adressen eller P2-avsändaren). Mottagaren ser Från-adressen i e-postklienter.|
|orsak|Orsaken till att den sammansatta autentiseringen gick igenom eller inte. Värdet är en tresiffrig kod. Till exempel: <ul><li>**000**: meddelandet misslyckades explicit autentisering (`compauth=fail`). Till exempel kan meddelandet ha tagit emot en misslyckande från DMARC med karantän eller avslag som åtgärd.</li><li>**001**: Meddelandet misslyckades implicit autentisering (`compauth=fail`). Det innebär att avsändardomänen inte hade publicerade poster för e-postautentisering eller hade en svagare felprincip (SPF SoftFail (lindrigt fel) eller neutral, DMARC-principen `p=none`).</li><li>**002**: Organisationen har en princip för avsändare/domän par som uttryckligen förbjuds från att skicka falska e-postmeddelanden. Den här inställningen anges manuellt av en administratör.</li><li>**010**: betyder att meddelandet inte klarade DMARC, med åtgärden att avvisa eller placera i karantän och avsändardomänen är en av organisationens godkända domäner (det här är en del av förfalskning inom organisationen (”self-to-self” eller ”intra-org”)).</li><li>**1xx** eller **7xx**: meddelandet gick igenom autentiseringen (`compauth=pass`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**2xx**: Meddelandet gick igenom implicit autentisering mjukt (`compauth=softpass`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**3xx**: meddelandet kontrollerades inte för sammansatt autentisering (`compauth=none`).</li><li>**4xx** eller **9xx**: meddelande förbigick sammansatt autentisering (`compauth=none`). De två sista siffrorna är interna koder som används av Microsoft 365.</li><li>**6xx**: Meddelandet inte klarade implicit e-postautentisering, och avsändardomänen är en av organisationens godkända domäner (det här är en del av förfalskning inom organisationen (”self-to-self” eller ”intra-org”)).</li></ul>|
|smtp.mailfrom|Domänen för `5321.MailFrom`-adressen (kallas även för E-POST FRÅN-adress, P1-avsändare eller avsändare av kuvert). Det är den e-postadress som används för rapporter om utebliven leverans (kallas även för NDR-rapporter eller bouncemeddelanden).|
|spf|Beskriver resultaten av SPF-kontrollen av meddelandet. Möjliga värden inkluderar: <ul><li>**pass (IP-adress)**: anger att SPF-kontrollen av meddelandet gick igenom och inkluderar avsändarens IP-adress. Klienten har tillåtelse att skicka eller vidarebefordra e-post på avsändarens domän.</li><li>**fail (IP-adress)**: anger att SPF-kontrollen av meddelande misslyckades och inkluderar avsändarens IP-adress. Det här kallas ibland för en _hard fail_.</li><li>**softfail (orsak)**: anger att SPF-registret har konstaterat att värden inte har rätt att skicka men är i en övergångsfas.</li><li>**neutral**: anger att SPF-registret uttryckligen angett att det inte kontrollerar huruvida IP-adressen är godkänd.</li><li>**none**: anger att domänen saknar SPF-register eller att SPF-registret inte ger något resultat.</li><li>**temperror**: anger att ett fel har inträffat som kan vara temporärt, till exempel ett DNS-fel. Att försöka igen senare kanske lyckas utan åtgärd från administratören.</li><li>**permerror**: anger att ett permanent fel har inträffat. Detta är fallet när en domän till exempel har ett felaktigt formaterat SPF-register.</li></ul>|
|
