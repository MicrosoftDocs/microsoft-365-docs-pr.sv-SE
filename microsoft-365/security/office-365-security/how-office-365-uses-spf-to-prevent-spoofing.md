---
title: Hur Sender Policy Framework (SPF) förhindrar förfalskning
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur Microsoft 365 använder SPF-posten (Sender Policy Framework) i DNS för att säkerställa att mål-e-postsystem litar på meddelanden som skickas från din anpassade domän.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6b79957f84e660fe952f88dab18d8934937d875
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167533"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Så använder Microsoft 365 SPF (Sender Policy Framework) för att förhindra förfalskning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **Sammanfattning:** I den här artikeln beskrivs hur Microsoft 365 använder SPF-TXT-posten (Sender Policy Framework) i DNS för att säkerställa att mål-e-postsystem litar på meddelanden som skickas från din anpassade domän. Det här gäller utgående e-post som skickas från Microsoft 365. Meddelanden som skickas från Microsoft 365 till en mottagare inom Microsoft 365 passerar alltid SPF.

En SPF TXT-post är en DNS-post som hjälper till att förhindra förfalskning och nätfiske genom att verifiera domännamnet som e-postmeddelanden skickas från. SPF validerar e-postmeddelandens ursprung genom att verifiera avsändarens IP-adress mot den påstådda ägaren till avsändardomänen.

> [!NOTE]
> SPF-posttyper togs bort av IETF (Internet Engineering Task Force) under 2014. Se i stället till att du använder TXT-poster i DNS för att publicera SPF-information. I resten av den här artikeln används termen SPF TXT-post för tydlighets skull.

Domänadministratörer publicerar SPF-information i TXT-poster i DNS. SPF-informationen identifierar behöriga utgående e-postservrar. Mål-e-postsystem kontrollerar att meddelanden kommer från behöriga utgående e-postservrar. Om du redan är bekant med SPF, eller om du har en enkel distribution, och bara behöver veta vad du ska ta med i SPF TXT-posten i DNS för Microsoft 365, kan du gå till Konfigurera SPF i [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)för att förhindra förfalskning. Om du inte har en distribution som har fullständiga värdar i Microsoft 365, eller om du vill ha mer information om hur SPF fungerar eller hur du felsöker SPF för Microsoft 365, kan du fortsätta med läsningen.

> [!NOTE]
> Tidigare var du tvungen att lägga till en annan SPF TXT-post i din anpassade domän om du också använde SharePoint Online. Det behöver du inte göra längre. Den här ändringen kan minska risken för att SharePoint Online-meddelanden hamnar i skräppostmappen. Du behöver inte göra några ändringar omedelbart, men om du får felmeddelandet "för många uppslag" ändrar du SPF TXT-posten enligt beskrivningen i Konfigurera SPF i [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)för att förhindra förfalskning.

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Så här fungerar SPF för att förhindra förfalskning och nätfiske i Microsoft 365
<a name="HowSPFWorks"> </a>

SPF avgör om en avsändare tillåts skicka för en domäns räkning. Om avsändaren inte har tillåtelse att göra det, det vill säga om e-posten misslyckas med SPF-kontrollen på den mottagande servern, avgör skräppostprincipen som konfigurerats på den servern vad som ska göra med meddelandet.

Varje SPF TXT-post innehåller tre delar: deklarationen att det är en SPF TXT-post, DE IP-adresser som tillåts skicka e-post från din domän och de externa domäner som kan skicka för din domän samt en regel för verkställande. Du behöver alla tre i en giltig SPF TXT-post. I den här artikeln beskrivs hur du skapar SPF TXT-posten och metodtips för att arbeta med tjänster i Microsoft 365. Länkar till instruktioner om hur du arbetar med din domänregistrator för att publicera posten till DNS finns också.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Grundläggande om SPF: IP-adresser som tillåts skicka från din egen domän
<a name="SPFBasicsIPaddresses"> </a>

Ta en titt på den grundläggande syntaxen för en SPF-regel:

v=spf1 \<IP\>\<enforcement rule\>

Anta till exempel att följande SPF-regel finns för contoso.com:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

I det här exemplet instruerar SPF-regeln den mottagande e-postservern att endast acceptera e-post från dessa IP-adresser för contoso.com:

- IP-adress #1

- IP-adress #2

- IP-adress #3

Den här SPF-regeln talar om för den mottagande e-postservern att om ett meddelande kommer från contoso.com, men inte från någon av dessa tre IP-adresser, ska den mottagande servern tillämpa tillämpningsregeln på meddelandet. Tillämpningsregeln är vanligtvis ett av följande alternativ:

- **Hårt fel.** Markera meddelandet med "hårt fel" i meddelandekuvertet och följ sedan den mottagande serverns konfigurerade skräppostprincip för den här typen av meddelande.

- **Mjuk fel.** Markera meddelandet med ett mjukt fel i meddelandekuvertet. Vanligtvis är e-postservrar konfigurerade för att leverera dessa meddelanden ändå. De flesta slutanvändare ser inte det här markeringen.

- **Neutral.** Gör ingenting, det vill säga markera inte meddelandekuvertet. Detta är vanligtvis reserverat för teständamål och används sällan.

Följande exempel visar hur SPF fungerar i olika situationer. I de här contoso.com är avsändaren och woodgrovebank.com är mottagaren.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Exempel 1: E-postautentisering av ett meddelande som skickas direkt från avsändare till mottagare
<a name="spfExample1"> </a>

SPF fungerar bäst när sökvägen från avsändare till mottagare är direkt, till exempel:

![Diagram som visar hur SPF autentiserar e-post när den skickas direkt från server till server.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

När woodgrovebank.com får meddelandet, och om IP-adress #1 finns i SPF TXT-posten för contoso.com, skickar meddelandet SPF-kontrollen och är autentiserad.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Exempel 2: Spoofed Sender Address misslyckas SPF-kontrollen
<a name="spfExample2"> </a>

Anta att en phisher hittar ett sätt att contoso.com:

![Diagram som visar hur SPF autentiserar e-post när den skickas från en förfalskningsserver.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Eftersom IP-#12 inte finns i contoso.coms SPF TXT-post misslyckas meddelandet SPF-kontrollen och mottagaren kan välja att markera den som skräppost.

### <a name="example-3-spf-and-forwarded-messages"></a>Exempel 3: SPF och vidarebefordrade meddelanden
<a name="spfExample3"> </a>

En nackdel med SPF är att det inte fungerar när ett e-postmeddelande har vidarebefordrats. Anta till exempel att användaren på woodgrovebank.com har angett en vidarebefordranregel som skickar all e-post till ett outlook.com konto:

![Diagram som visar hur SPF inte kan autentisera e-post när meddelandet vidarebefordras.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Meddelandet skickar ursprungligen SPF-kontrollen på woodgrovebank.com men det misslyckas SPF-kontrollen vid outlook.com eftersom IP #25 inte finns i contoso.coms SPF TXT-post. Outlook.com markera meddelandet som skräppost. Du kan komma runt det här problemet genom att använda SPF tillsammans med andra autentiseringsmetoder för e-post, till exempel DKIM och DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Grundläggande om SPF: Inklusive domäner från tredje part som kan skicka e-post för din domän
<a name="SPFBasicsIncludes"> </a>

Förutom IP-adresser kan du också konfigurera SPF TXT-posten så att domäner inkluderas som avsändare. Dessa läggs till i SPF TXT-posten som "include"-uttryck. Du kanske contoso.com ta med alla IP-adresser för e-postservrarna från contoso.net och contoso.org som den också äger. För att göra detta contoso.com en SPF TXT-post som ser ut så här:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

När den mottagande servern ser den här posten i DNS utför den också ett DNS-uppslag på SPF TXT-posten för contoso.net och sedan för contoso.org. Om det hittar ytterligare ett include-uttryck i posterna för contoso.net eller contoso.org följer även det. För att förhindra denial of service-attacker är det maximala antalet DNS-uppslag för ett enskilt e-postmeddelande 10. Varje include-instruktion representerar ytterligare ett DNS-uppslag. Om ett meddelande överskrider 10 gränsen misslyckas meddelandet SPF. När ett meddelande når den här gränsen, beroende på hur den mottagande servern har konfigurerats, kan avsändaren få ett meddelande om att meddelandet genererat "för många uppslag" eller att "det maximala antalet hopp för meddelandet har överskridits" (vilket kan hända när uppslagsloopen och överskrider DNS-tidsgränsen). Tips om hur du undviker detta finns i [Felsökning: Rekommendationer för SPF i Microsoft 365.](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Krav för SPF TXT-posten och Microsoft 365
<a name="SPFReqsinO365"> </a>

Om du konfigurerade e-post när du konfigurerade Microsoft 365 har du redan skapat en SPF TXT-post som identifierar Microsofts meddelandeservrar som en legitim e-postkälla för din domän. Den här posten ser antagligen ut så här:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Om du är en fullständigt värdbaserade kund, det vill säga du inte har några lokala e-postservrar som skickar utgående e-post, är detta den enda SPF TXT-post som du behöver publicera för Office 365.

Om du har en hybriddistribution (det vill säga du har vissa postlådor lokalt och en del finns i Microsoft 365), eller om du är fristående Exchange Online Protection (EOP) (dvs. din organisation använder EOP för att skydda dina lokala postlådor), ska du lägga till den utgående IP-adressen för var och en av dina lokala edge-e-postservrar till SPF TXT-posten i DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Skapa en SPF TXT-post för Microsoft 365
<a name="FormYourSPF"> </a>

Använd syntaxinformationen i den här artikeln för att skapa SPF TXT-posten för din anpassade domän. Det finns andra syntaxalternativ som inte nämns här, men det här är de vanligaste alternativen. När du har skapat posten måste du uppdatera posten hos domänregistratorn.

Mer information om de domäner som du måste ta med för Microsoft 365 finns i Externa [DNS-poster som krävs för SPF.](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records) Följ de [stegvisa anvisningarna för att](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) uppdatera SPF-poster (TXT) för din domänregistrator.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>SPF TXT-postsyntax för Microsoft 365
<a name="SPFSyntaxO365"> </a>

En vanlig SPF TXT-post för Microsoft 365 har följande syntax:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

där:

- **v=spf1** krävs. Detta definierar TXT-posten som en SPF TXT-post.

- **ip4** anger att du använder IP version 4-adresser. **ip6** anger att du använder IP version 6-adresser. Om du använder IPv6 IP-adresser ersätter du **ip4** med **ip6** i exemplen i den här artikeln. Du kan också ange IP-adressintervall med hjälp av CIDR-notation, till exempel **ip4:192.168.0.1/26.**

- _IP-adressen_ är den IP-adress som du vill lägga till i SPF TXT-posten. Det här är vanligtvis IP-adressen för organisationens utgående e-postserver. Du kan lista flera utgående e-postservrar. Mer information finns i [exempel: SPF TXT-post för flera utgående lokala e-postservrar och Microsoft 365.](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)

- _domännamnet_ är den domän som du vill lägga till som en äkta avsändare. En lista över domännamn som du ska ta med för Microsoft 365 finns i Externa [DNS-poster som krävs för SPF.](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)

- Tillämpningsregel är vanligtvis något av följande:

  - -all

    Anger hårt fel. Om du känner till alla auktoriserade IP-adresser för domänen kan du lista dem i SPF TXT-posten och använda kvalificeraren -all (hard fail). Om du bara använder SPF, det vill säga att du inte använder DMARC eller DKIM, ska du använda -all-kvalificeraren. Vi rekommenderar att du alltid använder den här kvalificeraren.

  - ~all

    Anger mjuk fel. Om du inte är säker på att du har den fullständiga listan med IP-adresser bör du använda kvalificeraren ~all (mjuk fel). Om du använder DMARC med p=karantän eller p=avvisa kan du också använda ~all. Annars använder du -all.

  - ?all

    Indikerar neutral. Det här används vid testning av SPF. Vi rekommenderar inte att du använder den här kvalificeraren i livedistributionen.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Exempel: SPF TXT-post som ska användas när all din e-post skickas av Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Om all din e-post skickas av Microsoft 365 ska du använda den i SPF TXT-posten:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Exempel: SPF TXT-post för ett hybridscenario med en lokal Exchange Server och Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Om IP-adressen för din lokala Exchange Server i en hybridmiljö är 192.168.0.1 utgör du SPF TXT-posten på följande sätt för att ställa in SPF-tvingande regel på ett hårt fel:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Exempel: SPF TXT-post för flera utgående lokala e-postservrar och Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Om du har flera utgående e-postservrar tar du med IP-adressen för varje e-postserver i SPF TXT-posten och avgränsar varje IP-adress med ett blanksteg följt av en "ip4:"-sats. Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Nästa steg: Konfigurera SPF för Microsoft 365
<a name="SPFNextSteps"> </a>

När du har utformat SPF TXT-posten följer du stegen i Konfigurera SPF i [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för att förhindra förfalskning för att lägga till den i din domän.

Även om SPF har utformats för att förhindra förfalskning, men det finns förfalskningsmetoder som SPF inte kan skydda mot. För att skydda mot dessa bör du, när du har konfigurerat SPF, också konfigurera DKIM och DMARC för Microsoft 365. Information om hur du kommer igång [finns i Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Microsoft 365.](use-dkim-to-validate-outbound-email.md) Därefter läser du [Använda DMARC för att validera e-post i Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Felsökning: Rekommendationer för SPF i Microsoft 365
<a name="SPFTroubleshoot"> </a>

Du kan bara skapa en SPF TXT-post för din anpassade domän. Om du skapar flera poster misslyckas en round robin situation och SPF misslyckas. Du kan undvika detta genom att skapa separata poster för varje underdomän. Du kan till exempel skapa en post för contoso.com och en annan post för bulkmail.contoso.com.

Om ett e-postmeddelande orsakar fler än 10 DNS-uppslag innan det levereras svarar den mottagande e-postservern med ett permanent fel, även kallat  _permerror,_ och orsakar att meddelandet misslyckas i SPF-kontrollen. Den mottagande servern kan också svara med en rapport om utebliven leverans (NDR) som innehåller ett fel som liknar följande:

- Meddelandet överskred antalet hopp.

- Meddelandet kräver för många uppslag.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Undviker felet "för många uppslag" när du använder domäner från tredje part med Microsoft 365
<a name="SPFTroubleshoot"> </a>

Vissa SPF TXT-poster för domäner från tredje part dirigerar den mottagande servern till att utföra ett stort antal DNS-uppslag. När det här skrivs innehåller till exempel Salesforce.com 5 uttryck i posten:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Du kan undvika felet genom att implementera en princip där till exempel alla som skickar massutskick måste använda en underdomän specifikt för detta ändamål. Sedan definierar du en annan SPF TXT-post för underdomänen som innehåller massutskicket.

 I vissa fall, till exempel i salesforce.com exempel, måste du använda domänen i SPF TXT-posten, men i andra fall kanske tredje part redan har skapat en underdomän som du kan använda för detta ändamål. Till exempel exacttarget.com skapat en underdomän som du behöver använda för SPF TXT-posten:

```text
cust-spf.exacttarget.com
```

När du inkluderar domäner från tredje part i SPF TXT-posten måste du kontrollera med tredje part vilken domän eller underdomän som ska användas för att undvika att behöva gå in på uppslagsgränsen 10.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Hur du visar din aktuella SPF TXT-post och fastställer antalet uppslag som krävs
<a name="SPFTroubleshoot"> </a>

Du kan använda nslookup för att visa dina DNS-poster, inklusive SPF TXT-posten. Om du föredrar det finns det ett antal kostnadsfria onlineverktyg som du kan använda för att visa innehållet i SPF TXT-posten. Genom att titta på SPF TXT-posten och följa kedjan med include-instruktioner och omdirigeringar, kan du avgöra hur många DNS-uppslag posten kräver. Vissa onlineverktyg räknar och visar dessa uppslag åt dig. Om du håller reda på det här antalet förhindrar du att meddelanden som skickas från organisationen utlöser ett permanent fel, ett så kallat permerror, från den mottagande servern.

## <a name="for-more-information"></a>Mer information
<a name="SPFTroubleshoot"> </a>

Behöver du hjälp med att lägga till SPF TXT-posten? Läs artikeln [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365. [Rubriker som är skräppostskyddade innehåller](anti-spam-message-headers.md) syntax- och rubrikfälten som används av Microsoft 365 för SPF-kontroller.


