---
title: Så här använder Office 365 Sender Policy Framework (SPF) för att förhindra förfalskning
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 'Sammanfattning: I den här artikeln beskrivs hur Office 365 använder SPF-posten (Sender Policy Framework) i DNS för att säkerställa att e-postsystem för mål litar på meddelanden som skickas från din anpassade domän. Detta gäller utgående e-post som skickas från Office 365. Meddelanden som skickas från Office 365 till en mottagare inom Office 365 kommer alltid att passera SPF.'
ms.openlocfilehash: e2863c0b8a66fa511c4ce842dc8026e880594292
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806034"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Så här använder Office 365 Sender Policy Framework (SPF) för att förhindra förfalskning

 **Sammanfattning:** I den här artikeln beskrivs hur Office 365 använder SPF-posten (Sender Policy Framework) i DNS för att säkerställa att måle-e-postsystem litar på meddelanden som skickas från din anpassade domän. Detta gäller utgående e-post som skickas från Office 365. Meddelanden som skickas från Office 365 till en mottagare inom Office 365 kommer alltid att passera SPF.

En SPF TXT-post är en DNS-post som förhindrar förfalskning och nätfiske genom att verifiera domännamnet som e-postmeddelanden skickas från. SPF validerar ursprunget för e-postmeddelanden genom att verifiera avsändarens IP-adress mot den påstådda ägaren av den sändande domänen.

> [!NOTE]
> SPF-posttyper inaktuella av Internet Engineering Task Force (IETF) 2014. Se i stället till att du använder TXT-poster i DNS för att publicera din SPF-information. Resten av den här artikeln använder termen SPF TXT-post för tydlighetens skull.

Domänadministratörer publicerar SPF-information i TXT-poster i DNS. SPF-informationen identifierar auktoriserade utgående e-postservrar. Mål e-postsystem verifiera att meddelanden kommer från auktoriserade utgående e-postservrar. Om du redan är bekant med SPF, eller om du har en enkel distribution, och bara behöver veta vad du ska inkludera i din SPF TXT-post i DNS för Office 365, kan du gå till [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Om du inte har en distribution som är helt värd i Office 365, eller om du vill ha mer information om hur SPF fungerar eller hur du felsöker SPF för Office 365, fortsätter du läsa.

> [!NOTE]
> Tidigare var du tvungen att lägga till en annan SPF TXT-post i din anpassade domän om du också använde SharePoint Online. Detta behövs inte längre. Den här ändringen bör minska risken för att Meddelanden om SharePoint Online-meddelanden hamnar i mappen Skräppost. Du behöver inte göra några ändringar omedelbart, men om du får felet "för många sökninger" ändrar du SPF TXT-posten enligt beskrivningen i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a>Så här fungerar SPF för att förhindra förfalskning och nätfiske i Office 365
<a name="HowSPFWorks"> </a>

SPF avgör om en avsändare tillåts skicka för en domän. Om avsändaren inte tillåts göra det, det vill säga om e-postmeddelandet misslyckas SPF-kontrollen på den mottagande servern, avgör skräppostprincipen som konfigurerats på den servern vad meddelandet ska göra.

Varje SPF TXT-post innehåller tre delar: deklarationen att det är en SPF TXT-post, IP-adresser som tillåts skicka e-post från din domän och de externa domäner som kan skicka för domänens räkning och en tvingande regel. Du behöver alla tre i en giltig SPF TXT-post. I den här artikeln beskrivs hur du skapar din SPF TXT-post och innehåller metodtips för hur du arbetar med tjänsterna i Office 365. Länkar till instruktioner om hur du arbetar med domänregistratorer för att publicera din post till DNS finns också.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Grunderna i SPF: IP-adresser som tillåts skicka från din anpassade domän
<a name="SPFBasicsIPaddresses"> </a>

Ta en titt på den grundläggande syntaxen för en SPF-regel:

v=spf1 \<\> \<IP-efterlevnadsregel\>

Anta till exempel att följande SPF-regel finns för contoso.com:

v=spf1 \<IP-adress #1\> \<IP-adress #2\> \<IP-adress #3\> \<tvingande regel\>

I det här exemplet instruerar SPF-regeln den mottagande e-postservern att endast ta emot e-post från dessa IP-adresser för domänen contoso.com:

- IP-adress #1

- IP-adress #2

- IP-adress #3

Den här SPF-regeln talar om för den mottagande e-postservern att om ett meddelande kommer från contoso.com, men inte från någon av dessa tre IP-adresser, bör den mottagande servern tillämpa tvingande regeln på meddelandet. Verkställighetsregeln är vanligtvis ett av följande alternativ:

- **Hårt misslyckande.** Markera meddelandet med "svårt fel" i meddelandekuvertet och följ sedan den mottagande serverns konfigurerade skräppostprincip för den här typen av meddelande.

- **Mjuk misslyckas.** Markera meddelandet med "mjukt fel" i meddelandekuvertet. Vanligtvis är e-postservrar konfigurerade för att leverera dessa meddelanden ändå. De flesta slutanvändare ser inte det här märket.

- **Neutral.** Gör ingenting, det vill säga markera inte meddelandet kuvertet. Detta är vanligtvis reserverad för teständamål och används sällan.

Följande exempel visar hur SPF fungerar i olika situationer. I dessa exempel är contoso.com avsändaren och woodgrovebank.com är mottagaren.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Exempel 1: E-postautentisering av ett meddelande som skickas direkt från avsändare till mottagare
<a name="spfExample1"> </a>

SPF fungerar bäst när sökvägen från avsändare till mottagare är direkt, till exempel:

![Diagram som visar hur SPF autentiserar e-post när det skickas direkt från server till server.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

När woodgrovebank.com tar emot meddelandet, om IP-adressen #1 finns i SPF TXT-posten för contoso.com, skickar meddelandet SPF-kontrollen och autentiseras.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Exempel 2: Förfalskad avsändaradress misslyckas SPF-kontrollen
<a name="spfExample2"> </a>

Anta att en phisher hittar ett sätt att förfalska contoso.com:

![Diagram som visar hur SPF autentiserar e-post när det skickas från en förfalskad server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Eftersom IP-adressen #12 inte finns i contoso.com s SPF TXT post, misslyckas meddelandet SPF kontroll och mottagaren kan välja att markera det som spam.

### <a name="example-3-spf-and-forwarded-messages"></a>Exempel 3: SPF och vidarebefordrade meddelanden
<a name="spfExample3"> </a>

En nackdel med SPF är att det inte fungerar när ett e-postmeddelande har vidarebefordrats. Anta till exempel att användaren på woodgrovebank.com har ställt in en vidarebefordringsregel för att skicka all e-post till ett outlook.com-konto:

![Diagram som visar hur SPF inte kan autentisera e-post när meddelandet vidarebefordras.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Meddelandet passerar ursprungligen SPF-kontrollen vid woodgrovebank.com men det misslyckas SPF-kontrollen vid outlook.com eftersom IP-#25 inte finns i contoso.com:s SPF TXT-post. Outlook.com kan sedan markera meddelandet som skräppost. För att komma runt det här problemet, använd SPF tillsammans med andra e-postautentiseringsmetoder som DKIM och DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Grunderna i SPF: Inklusive domäner från tredje part som kan skicka e-post för din domän
<a name="SPFBasicsIncludes"> </a>

Förutom IP-adresser kan du också konfigurera SPF TXT-posten så att den inkluderar domäner som avsändare. Dessa läggs till i SPF TXT-posten som "include"-satser. Till exempel kanske contoso.com vill inkludera alla IP-adresser till e-postservrarna från contoso.net och contoso.org som den också äger. För att göra detta publicerar contoso.com en SPF TXT-post som ser ut så här:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

När den mottagande servern ser den här posten i DNS utförs även en DNS-sökning på SPF TXT-posten för contoso.net och sedan för contoso.org. Om den hittar ytterligare en inkludera uttalande i posterna för contoso.net eller contoso.org, kommer det att följa dem också. För att förhindra överbelastningsattacker är det maximala antalet DNS-sökningar för ett enskilt e-postmeddelande 10. Varje include-sats representerar ytterligare en DNS-sökning. Om ett meddelande överskrider 10-gränsen misslyckas SPF. När ett meddelande når den här gränsen, beroende på hur den mottagande servern är konfigurerad, kan avsändaren få ett meddelande som säger att meddelandet genereras "för många sökninger" eller att "maximalt hoppantal för meddelandet har överskridits" (vilket kan hända när uppslag slingan och överträffa DNS-timeouten). Tips om hur du undviker detta finns i [Felsökning: Metodtips för SPF i Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-office-365"></a>Krav för din SPF TXT-post och Office 365
<a name="SPFReqsinO365"> </a>

Om du konfigurerar e-post när du konfigurerar Office 365 har du redan skapat en SPF TXT-post som identifierar Microsofts meddelandeservrar som en legitim e-postkälla för din domän. Denna post ser förmodligen ut så här:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Om du är en fullständigt värd office 365-kund, det vill säga du har inga lokala e-postservrar som skickar utgående e-post, är detta den enda SPF TXT-post som du behöver publicera för Office 365.

Om du har en hybriddistribution (det vill säga du har vissa postlådor lokalt och vissa i Office 365), eller om du är en fristående eop-kund (Exchange Online Protection) (det vill säga din organisation använder EOP för att skydda dina lokala postlådor), bör du lägga till den utgående IP-adressen för var och en av dina lokala kantpostservrar i SPF TXT-posten i DNS.

## <a name="form-your-spf-txt-record-for-office-365"></a>Skapa din SPF TXT-post för Office 365
<a name="FormYourSPF"> </a>

Använd syntaxinformationen i den här artikeln för att skapa SPF TXT-posten för din anpassade domän. Även om det finns andra syntaxalternativ som inte nämns här, är dessa de vanligaste alternativen. När du har skapat din post måste du uppdatera posten på din domänregistratorer.

Information om de domäner som du måste inkludera för Office 365 finns i [Externa DNS-poster som krävs för SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Använd [steg-för-steg-instruktionerna](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) för uppdatering av SPF-poster (TXT) för domänregistratorer.

### <a name="spf-txt-record-syntax-for-office-365"></a>Syntax för SPF TXT-post för Office 365
<a name="SPFSyntaxO365"> </a>

En typisk SPF TXT-post för Office 365 har följande syntax:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

Där:

- **v=spf1** krävs. Detta definierar TXT-posten som en SPF TXT-post.

- **ip4** anger att du använder IP version 4-adresser. **ip6** anger att du använder IP version 6-adresser. Om du använder IPv6 IP-adresser, ersätta **ip4** med **ip6** i exemplen i den här artikeln. Du kan också ange IP-adressintervall med CIDR-notation, till exempel **ip4:192.168.0.1/26**.

- _IP-adress_ är den IP-adress som du vill lägga till i SPF TXT-posten. Detta är vanligtvis IP-adressen för den utgående e-postservern för din organisation. Du kan lista flera utgående e-postservrar. Mer information finns i [Exempel: SPF TXT-post för flera utgående lokala e-postservrar och Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _domännamn_ är den domän som du vill lägga till som en legitim avsändare. En lista över domännamn som du bör inkludera för Office 365 finns i [Externa DNS-poster som krävs för SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).

- Verkställighetsregel är vanligtvis en av följande:

  - -alla

    Indikerar ett hårt fel. Om du känner till alla auktoriserade IP-adresser för din domän, lista dem i SPF TXT-posten och använda -all (hard fail) kvalificeraren. Om du bara använder SPF, det vill säga du använder inte DMARC eller DKIM, bör du också använda -all-kvalificeraren. Vi rekommenderar att du alltid använder den här kvalificeraren.

  - ~ alla

    Indikerar mjuk misslyckas. Om du inte är säker på att du har en fullständig lista över IP-adresser, bör du använda kvalificeraren ~all (soft fail). Dessutom, om du använder DMARC med p = karantän eller p = avvisa, då kan du använda ~ alla. Annars använder -alla.

  - ?alla

    Anger neutral. Detta används vid testning av SPF. Vi rekommenderar inte att du använder den här kvalificeraren i din livedistribution.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a>Exempel: SPF TXT-post som ska användas när all din e-post skickas av Office 365
<a name="ExampleSPFNoSP"> </a>

Om all din e-post skickas av Office 365 använder du den i SPF TXT-posten:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a>Exempel: SPF TXT-post för ett hybridscenario med en lokal Exchange Server och Office 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Om IP-adressen för din lokala Exchange Server är 192.168.0.1, för att ställa in tvingande SPF-regeln på ett hårt fel, bildar du SPF TXT-posten enligt följande:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a>Exempel: SPF TXT-post för flera utgående lokala e-postservrar och Office 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Om du har flera utgående e-postservrar, inkludera IP-adressen för varje e-postserver i SPF TXT-posten och separera varje IP-adress med ett blanksteg följt av en "ip4:"-sats. Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a>Nästa steg: Konfigurera SPF för Office 365
<a name="SPFNextSteps"> </a>

När du har formulerat din SPF TXT-post följer du stegen i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för att lägga till den i domänen.

Även om SPF är utformat för att förhindra förfalskning, men det finns förfalskningstekniker som SPF inte kan skydda mot. För att skydda mot dessa, när du har ställt in SPF, bör du också konfigurera DKIM och DMARC för Office 365. Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md). Se sedan [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a>Felsökning: Metodtips för SPF i Office 365
<a name="SPFTroubleshoot"> </a>

Du kan bara skapa en SPF TXT-post för din anpassade domän. Om du skapar flera poster misslyckas en round robin-situation och SPF misslyckas. Undvik detta kan du skapa separata poster för varje underdomän. Skapa till exempel en post för contoso.com och en annan post för bulkmail.contoso.com.

Om ett e-postmeddelande orsakar fler än 10 DNS-sökningar innan det levereras, svarar den mottagande e-postservern med ett permanent fel, även kallat _permerror_och gör att meddelandet misslyckas med SPF-kontrollen. Den mottagande servern kan också svara med en icke-leveransrapport (NDR) som innehåller ett fel som liknar dessa:

- Meddelandet överskred antalet hopp.

- Meddelandet krävde för många uppslag.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a>Undvika felet "för många sökninger" när du använder domäner från tredje part med Office 365
<a name="SPFTroubleshoot"> </a>

Vissa SPF TXT-poster för domäner från tredje part leder den mottagande servern att utföra ett stort antal DNS-sökningar. Till exempel, vid tidpunkten för denna skrift, innehåller Salesforce.com 5 innehålla satser i sin post:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

För att undvika felet kan du implementera en princip där alla som skickar massutskick av e-post, till exempel, måste använda en underdomän specifikt för detta ändamål. Du definierar sedan en annan SPF TXT-post för underdomänen som innehåller massmeddelandet.

 I vissa fall, till exempel salesforce.com exempel, måste du använda domänen i din SPF TXT-post, men i andra fall kan tredje part redan har skapat en underdomän som du kan använda för detta ändamål. Till exempel har exacttarget.com skapat en underdomän som du behöver använda för din SPF TXT-post:

```text
cust-spf.exacttarget.com
```

När du inkluderar domäner från tredje part i SPF TXT-posten måste du bekräfta med den tredje parten vilken domän eller underdomän som ska användas för att undvika att köra in i 10-uppslagsgränsen.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Så här visar du din aktuella SPF TXT-post och bestämmer antalet uppslag som krävs
<a name="SPFTroubleshoot"> </a>

Du kan använda nslookup för att visa dina DNS-poster, inklusive din SPF TXT-post. Eller, om du föredrar, det finns ett antal gratis, online-verktyg tillgängliga som du kan använda för att visa innehållet i din SPF TXT post. Genom att titta på din SPF TXT-post och följa kedjan med inkludera-satser och omdirigeringar kan du bestämma hur många DNS-sökningar posten kräver. Vissa online-verktyg kommer även att räkna och visa dessa uppslag för dig. Om du håller reda på det här numret förhindrar du att meddelanden som skickas från din organisation utlöser ett permanent fel, som kallas permerror, från den mottagande servern.

## <a name="for-more-information"></a>Mer information
<a name="SPFTroubleshoot"> </a>

Behöver du hjälp med att lägga till SPF TXT-posten? Läs artikeln [Skapa DNS-poster hos valfri DNS-värd för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) för detaljerad information om användning av Avsänarprincipramverk med din anpassade domän i Office 365. [Meddelandehuvuden mot skräppost](anti-spam-message-headers.md) innehåller syntax- och rubrikfält som används av Office 365 för SPF-kontroller.


