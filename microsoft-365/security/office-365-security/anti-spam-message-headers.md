---
title: Meddelandehuvuden för antiskräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Lär dig mer om de fält och värden för rubriker som läggs till i meddelanden av Exchange Online Protection.
ms.openlocfilehash: da5ceae73f0d4748a2011427cd521a8a06ff00a7
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42807137"
---
# <a name="anti-spam-message-headers"></a>Meddelandehuvuden för antiskräppost

När Exchange Online Protection söker igenom ett inkommande e-postmeddelande infogas **X-Forefront-Antispam-Report**-rubriken i varje meddelande. Fälten i denna rubrik kan hjälpa administratörer med information om meddelandet och hur det bearbetades. I fälten i **X-Microsoft-antispam**-rubriken finns mer information om massutskick och nätfiske. Utöver dessa två rubriker infogar Exchange Online Protection även resultat av e-postautentisering för varje meddelande det bearbetar i rubriken **Authentication-results**.

För information om hur man visar ett e-postmeddelandes meddelanderubrik i olika e-postklienter, se [Visa e-postmeddelandehuvud i Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> Du kan kopiera och klistra in innehållet i ett meddelandehuvud i verktyget [Message Analyzer](https://testconnectivity.microsoft.com/?tabid=mha). Det här verktyget hjälper till att tolka rubriker och lägga till dem i ett mer läsbart format.

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report meddelanderubrikfält

När du har använt meddelanderubrikens information kan du söka efter **X-Forefront-Antispam-Report** och sedan söka efter de här fälten. Andra fält i den här rubriken används exklusivt av Microsofts anti-spam-team av diagnostiska skäl.

|**Rubrikfält**|**Beskrivning**|
|:-----|:-----|
|CIP: \[IP-adress\]|Den anslutande IP-adressen. Du kanske vill ange den här IP-adressen när du skapar en lista över tillåtna IP-adresser eller IP-adresser att blockera i anslutningsfiltret. Mer information finns i [konfigurera policy för anslutningsfilter](configure-the-connection-filter-policy.md).|
|CTRY|Det land från vilket meddelandet anslöt till tjänsten. Detta bestäms av den anslutande IP-adressen, som kanske inte är samma som den ursprungliga IP-adressen.|
|LANG|Det språk på vilket meddelandet skrevs, specificerat av landskoden (till exempel ru_RU för ryska).|
|SCL|Meddelandets SCL-värde (Spam Confidence Level). Se [spamkonfidensnivåer](spam-confidence-levels.md) gällande tolkning av dessa värden.|
|SRV:BULK|Meddelandet har identifierats som ett massutskick av e-post. Om alternativet **Blockera alla massutskick av e-postmeddelanden** är aktiverat markeras det som skräppost. Om det inte är aktiverat kommer det endast att markeras som skräppost om filterreglerna angör att meddelandet är skräppost.|
|SFV:SFE|Filtreringen hoppades över och meddelandet släpptes igenom eftersom det skickades från en adress på individens lista med betrodda avsändare.|
|SFV:BLK|Filtreringen hoppades över och meddelandet blockerades eftersom det skickades från en adress på individens lista med blockerade avsändare.  <br/> **Tips**: Mer information om hur slutanvändare kan skapa listor med betrodda och blockerade avsändare finns i [Filtrera skräppost i Outlook på webben](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) och [Översikt över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (Outlook).|
|IPV:CAL|Meddelandet släpptes igenom skräppostfiltret då IP-adressen specificerades i en lista över tillåtna IP-adresser i anslutningsfiltret.|
|IPV:NLI|IP-adressen listade inte i någon IP-rykteslista.|
|SFV:SPM|Meddelandet markerades som skräppost av innehållsfiltret.|
|SFV:SKS|Meddelandet markerades som skräppost innan det bearbetades av innehållsfiltret. Detta inkluderar meddelanden där meddelandet har matchat en e-postflödesregel (även känt som transportregel) som automatiskt markerat det som skräppost och förbigått all ytterligare filtrering.|
|SFV:SKA|Meddelandet hoppade över filtreringen och levererades till inkorgen eftersom det matchade en lista över tillåtna i filterpolicyn för skräppost, som till exempel listan med **Betrodda avsändare**.|
|SFV:SKB|Meddelandet markerades som skräppost eftersom det matchade en blockeringslista i policyn för skräppostfilter, t. ex. listan över **Blockerade avsändare**.|
|SFV:SKN|Meddelandet markerades som icke skräppost innan det bearbetades av innehållsfiltret. Detta inkluderar meddelanden där meddelandet har matchat en e-postflödesregel som automatiskt markerat det som icke skräppost och förbigått all ytterligare filtrering.|
|SFV:SKI|I likhet med SFV:SKN har meddelandet hoppat över filtreringen av annan orsak, till exempel att det är ett e-postmeddelande inom organisationen med en mottagare.|
|SFV:SKQ|Meddelandet har släppts ur sin karantän och skickats till avsedda mottagare.|
|SFV:NSPM|Meddelandet har markerats som icke skräppost och skickats till avsedda mottagare.|
|H:\[helostring\]|En anslutande mailservers HELO- eller OEHLO-sträng.|
|PTR:\[ReverseDNS\]|PTR-registret, eller pekarregistret, för den sändande IP-adressen, även känt som omvänd DNS-adress.|
|ARC|ARC-protokollet har följande rubriker: <br/>• AAR: registrerar innehållet i rubriken för verifieringsresultat från DMARC. <br/>• AMS: denna rubrik innehåller kryptografiska signaturer för meddelandet. <br/>• AS: innehåller kryptografiska signaturer för meddelanderubriker. Den här rubriken innehåller en tagg för en kedjeverifiering som kallas "cv=", som inkluderar resultatet av kedjeverifieringen som **ingen**, **gick igenom**och **misslyckades**.|
|CAT:|Kategori för den skyddspolicy som används för meddelandet: <br/>MALW: Malware <br/>HPHSH or HPHISH : High confidence phishing <br/>PHSH: Phishing <br/>HSPM: High confidence spam <br/>SPOOF: Spoofing <br/>SPM: Spam <br/>BULK: Bulk <br/>DIMP: Domain Impersonation <br/>UIMP: User Impersonation <br/>GIMP: Mailbox Intelligence<br/>Det kan hända att ett inkommande meddelande flaggas av flera olika typer av skydd och flera identifieringsgenomsökningar. Policyer har olika prioriteringar och den policy som har högst prioritet kommer att gälla. Se [Vilken policy gäller när flera skyddsmetoder och identifieringsgenomsökningar körs på din e-post](how-policies-and-protections-are-combined.md).|
|SFTY|Meddelandet identifierades som phishing och kommer att markeras med något av följande värden: <br/>9.1: Standardvärde. Meddelandet innehåller en URL-adress för nätfiske, kan innehålla annat innehåll för nätfiske eller kan ha markerats som phishing av ett annat e-postfilter som till exempel en lokal version av Exchange Server innan meddelandet vidarebefordrats till Office 365. <br/>9.11: Meddelande om anti-spoofing-skydd där den sändande domänen i rubriken Från: är samma som, eller i linje med, eller är en del av samma organisation som den mottagande domänen. Detta indikerar att ett säkerhetstips om spoofing inom organisationen kommer att läggas till meddelandet. <br/>9.19: Meddelandet gick inte igenom imiteringskontroller där den sändande domänen försöker att imitera en domän som ägs av mottagaren, eller en anpassad domän som skyddas av anti-phishing-policyn. Detta indikerar att ett säkerhetstips om imitation kommer att läggas till meddelandet om detta aktiverats i anti-phishing-policyn. <br/>9.20: Meddelandet gick inte igenom användarimitationskontroller där den sändande användaren försöker att imitera en användare inom mottagarens organisation, eller en anpassad användare som skyddas av anti-phishing-policyn. Detta indikerar att ett säkerhetstips om imitation kommer att läggas till meddelandet om detta aktiverats i anti-phishing-policyn. <br/>9.21: Meddelandet gick inte igenom anti-spoofing-kontroller och den sändande domänen i rubriken Från: autentiserar inte och är från en extern domän. Används i kombination med CompAuth (se Authentication-Results). <br/>9.22: Samma som 9.21, förutom att användaren har en säker avsändare som har åsidosatts. <br/>9.23: Samma som 9.22, förutom att organisationen har en betrodd användare eller domän som har åsidosatts. <br/>9.24: Samma som 9.23, förutom att användaren har en Exchange-dataflödesregel som har åsidosatts.|
|X-CustomSpam: \[ASFOption\]|Meddelandet matchade ett avancerat alternativ för skräppostfiltrering. **X-CustomSpam: Image links to remote sites** anger till exempel att **en bild länkar till fjärrplatser** ASF-alternativet matchade. För att få read på vilken text för X-header som läggs till för varje specifikt ASF-alternativ, se [Avancerade alternativ för skräppostfiltrering](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam meddelanderubrikfält

Följande tabell beskriver användbara fält i meddelanderubriken **X-Microsoft-Antispam**. Andra fält i den här rubriken används exklusivt av Microsofts anti-spam-team av diagnostiska skäl.

|**Rubrikfält**|**Beskrivning**|
|:-----|:-----|
|BCL|I meddelandets BCL (Bulk Complaint Level) får du hjälp att skilja mellan olika typer av massutskick. Detta representeras av ett värde mellan 0 och 9. Se [Bulk Complaint Level-värden](bulk-complaint-level-values.md) för värden och annan information om BCL.|

## <a name="authentication-results-message-header"></a>Authentication-results meddelanderubrik

Resultaten av kontroller mot SPF, DKIM och DMARC registreras, eller stämplas, av Office 365 i meddelanderubriken **Authentication-results** när våra e-postservrar tar emot ett e-postmeddelande.

### <a name="check-stamp-syntax-and-examples"></a>Kontrollera märkningssyntax och exempel

Följande syntax exemplifierar en del av textens märkning som Office 365 tillämpar på meddelanderubriken för varje e-postmeddelande som genomgår en e-postautnetiseringskontroll när det tas emot av våra servrar. Märket läggs till i rubriken **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Syntax: SPF-kontrollmärkning

För SPF gäller följande syntax.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**Exempel: SPF-kontrollmärkning

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Syntax: DKIM-kontrollmärkning

För DKIM gäller följande syntax.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**Exempel: DKIM-kontrollmärkning

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Syntax: DMARC-kontrollmärkning

För DMARC gäller följande syntax.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

#### <a name="examples-dmarc-check-stamp"></a>Exempel: DMARC-kontrollmärkning

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Authentication-results meddelanderubrikfält används av Office 365-e-postautentisering

Denna tabell beskriver fälten och möjliga värden för varje autentiseringskontroll av e-post.

|**Rubrikfält**|**Beskrivning**|
|:-----|:-----|
|spf|Beskriver resultaten av SPF-kontrollen av meddelandet. Möjliga värden inkluderar: <br/>**pass (IP-adress)**: anger att SPF-kontrollen av meddelandet gick igenom och inkluderar avsändarens IP-adress. Klienten har tillåtelse att skicka eller vidarebefordra e-post på avsändarens domän. <br/>**fail (IP-adress)**: anger att SPF-kontrollen av meddelande misslyckades och inkluderar avsändarens IP-adress. Det här kallas ibland för en _hard fail_. <br/>**softfail (orsak)**: anger att SPF-registret har konstaterat att värden inte har rätt att skicka men är i en övergångsfas. <br/>**neutral**: anger att SPF-registret uttryckligen angett att det inte kontrollerar huruvida IP-adressen är godkänd. <br/>**none**: anger att domänen saknar SPF-register eller att SPF-registret inte ger något resultat. <br/>**temperror**: anger att ett fel har inträffat som kan vara temporärt, till exempel ett DNS-fel. Att försöka igen senare kanske lyckas utan åtgärd från administratören. <br/>**permerror**: anger att ett permanent fel har inträffat. Detta är fallet när en domän till exempel har ett felaktigt formaterat SPF-register.|
|smtp.mailfrom|Innehåller källdomänen som meddelandet skickades ifrån. Eventuella fel gällande detta e-postmeddelande kommer att skickas till postmaster eller den som är ansvarig för domänen. Detta kallas ibland för 5321.MailFrom-adressen eller reverse-path-adressen på meddelandets kuvert.|
|dkim|Beskriver resultaten av meddelandets DKIM-kontroll. Möjliga värden inkluderar: <br/>**pass**: anger att meddelandet gick igenom DKIM-kontrollen. <br/>**fail (orsak)**: anger att meddelandet inte gick igenom DKIM-kontrollen och varför. Om du till exempel inte har signerat meddelandet eller om signaturen inte har verifierats. <br/>**none**: anger att meddelandet inte signerats. Detta indikerar kanske, men kanske inte, att domänen har ett DKIM-register eller att DKIM-registret inte utvärderats till ett resultat, endast att meddelandet inte signerats.|
|header.d|Domän som identifierats i DKIM-signaturen om någon. Detta är den domän som tillfrågas om den publika nyckeln.|
|dmarc|Beskriver resultaten av DMARC-kontrollen av meddelandet. Möjliga värden inkluderar: <br/>**pass**: anger att meddelandet gick igenom DMARC-kontrollen. <br/>**fail**: anger att meddelandet inte gick igenom DMARC-kontrollen. <br/>**bestguesspass**: anger att det inte finns något DMARC TXT-register för domänen, men om ett sådant fanns skulle meddelandet ha gått igenom DMARC-kontrollen. Det beror på att domänen i adressen 5321.MailFrom matchar domänen i adressen 5322.From. <br/>**none**: anger att det inte finns något DKIM TXT-register för den sändande domänen i DNS.|
|åtgärd|Anger att den åtgärd som utförs av skräppostfiltret baseras på resultaten av DMARC-kontrollen. Till exempel: <br/>**PermError**: ett permanent fel uppstod när DMARC utvärderades, t. ex. ett felaktigt utformat DMARC register i DNS. Att försöka skicka meddelandet igen ger antagligen samma resultat. Försök istället att kontakta domänens ägare för att lösa problemet. <br/>**temperror**: ett temporärt fel inträffade under DMARC-utvärderingen. Du kanske kan begära att avsändaren skickar meddelandet igen senare för att bearbeta e-postmeddelandet ordentligt. <br/>**oreject** eller **o.reject**: står för override reject. I detta fall använder Office 365 åtgärden när det tar emot ett meddelande som misslyckas med DMARC-kontrollen från en domän vars DMARC TXT-register har en policy av p=reject. I stället för att ta bort eller avvisa meddelandet markerar Office 365 meddelandet som skräppost. Se [Så hanterar Office 365 inkommande e-postmeddelanden som inte går igenom DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail) för mer information om varför Office 365 är konfigurerat på det viset. <br/>**pct.quarantine**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på karantän, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen. <br/>**pct.reject**: anger att en procentsats på mindre än 100 % av meddelanden som inte går igenom DMARC kommer att levereras ändå. Det innebär att meddelandet inte gick igenom DMARC och att policyn ställdes in på att avslå, men fältet PCT var inte inställt på 100 % och systemet bestämde sig slumpmässigt för att inte tillämpa DMARC-åtgärden enligt principen för den angivna domänen.|
|header.from|Domänen för Från-adressen i e-postmeddelanderubriken. Detta kallas ibland för _5322.From_-adressen.|
|compauth|Resultat av sammansatt autentisering. Används av Office 365 för att kombinera flera typer av autentisering som SPF, DKIM, DMARC eller andra delar av meddelandet för att avgöra huruvida meddelandet är autentiserat eller inte. Använder Från:-domänen som grund för utvärderingen.|
|orsak|Orsaken till att den sammansatta autentiseringen gick igenom eller inte. Orsakens värde består av tre siffror: <br/>**000**: meddelandet gick uttryckligen inte igenom autentiseringen. Till exempel kan meddelandet ha tagit emot en fail från DMARC med karantän eller avslag som åtgärd. <br/>**001**: meddelandet har underförstått inte gått igenom autentiseringen och den avsändande domänen publicerade inte autentiseringspolicyer. Till exempel en DMARC-policy på p=none. <br/>**1xx** eller **7xx**: meddelandet gick igenom autentiseringen. De andra två siffrorna är interna koder som används av Office 365. <br/>**2xx**: meddelandet gick igenom autentiseringen mjukt. De andra två siffrorna är interna koder som används av Office 365. <br/>**3xx**: meddelandet kontrollerades inte för sammansatt autentisering. <br/>**4xx** eller **9xx**: meddelande förbigick sammansatt autentisering. De andra två siffrorna är interna koder som används av Office 365.|
|
