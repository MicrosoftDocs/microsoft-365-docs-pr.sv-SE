---
title: Hur avsändarens princip ramverk (SPF) förhindrar förfalskning
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
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur Microsoft 365 använder SPF-posten (avsändarens Policy Framework) i DNS för att säkerställa att mål-e-postsystemen litar på meddelanden som skickas från din egen domän.
ms.openlocfilehash: 702c5de90c53388a3d55ad752010fbaa04b5556b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307655"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Så använder Microsoft 365 SPF (Sender Policy Framework) för att förhindra förfalskning

 **Sammanfattning:** I den här artikeln beskrivs hur Microsoft 365 använder SPF-posten (avsändarens Policy Framework) i DNS för att säkerställa att mål-e-postsystemen litar på meddelanden som skickas från din egen domän. Detta gäller för utgående e-post som skickas från Microsoft 365. Meddelanden som skickas från Microsoft 365 till en mottagare inom Microsoft 365 kommer alltid att skicka SPF.

En SPF TXT-post är en DNS-post som kan förhindra förfalskning och nätfiske genom att verifiera det domän namn som e-postmeddelanden skickas från. SPF verifierar origo för e-postmeddelanden genom att verifiera avsändarens IP-adress mot den påstådda ägaren till den sändande domänen.

> [!NOTE]
> SPF-posttyperna har föråldrats av Internet Engineering Task Force (IETF) i 2014. I stället bör du kontrol lera att du använder TXT-poster i DNS för att publicera din SPF-information. Resten av den här artikeln använder termen SPF TXT-post för klarhet.

Domän administratörer publicerar SPF-information i TXT-poster i DNS. SPF-informationen identifierar godkända utgående e-postservrar. Mål-e-postsystem verifiera att meddelanden kommer från godkända servrar för utgående e-post. Om du redan är bekant med SPF, eller om du har en enkel distribution, och bara behöver veta vad som ska ingå i SPF TXT-posten i DNS för Microsoft 365, kan du gå till [Konfigurera SPF i Microsoft 365 för att förhindra förfalskningar](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Om du inte har en distribution som är fullständigt värd i Microsoft 365, eller om du vill ha mer information om hur SPF fungerar eller hur du felsöker SPF för Microsoft 365, fortsätter du att läsa.

> [!NOTE]
> Tidigare var du tvungen att lägga till en annan SPF TXT-post i din domän om du också använde SharePoint Online. Det behöver du inte göra längre. Den här ändringen kan minska risken för att SharePoint Online-meddelanden hamnar i skräppostmappen. Du behöver inte göra några ändringar direkt, men om du får fel meddelandet "för många sökningar" kan du ändra din SPF TXT-post enligt beskrivningen i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hur SPF fungerar för att förhindra förfalskning och nätfiske i Microsoft 365
<a name="HowSPFWorks"> </a>

SPF avgör om en avsändare tillåts skicka åt en domän. Om avsändaren inte har tillstånd att göra det, det vill säga om e-postmeddelandet inte orsakar SPF-kontrollen på den mottagande servern, bestämmer den skräp post princip som är konfigurerad för den servern vad som ska utföras med meddelandet.

Varje SPF TXT-post innehåller tre delar: den deklaration som den är en SPF TXT-post, de IP-adresser som tillåts för att skicka e-post från din domän och de externa domänerna som kan skicka till domänen och en tvingande regel. Du behöver alla tre i en giltig SPF TXT-post. I den här artikeln beskrivs hur du skapar en SPF TXT-post och ger rekommendationer för att arbeta med tjänsterna i Microsoft 365. Det finns också länkar till instruktioner om hur du arbetar med domän registratorn för att publicera posten till DNS.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-grunderna: IP-adresser tillåts skicka från din egen domän
<a name="SPFBasicsIPaddresses"> </a>

Ta en titt på den grundläggande syntaxen för en SPF-regel:

v = spf1 \<IP\>\<enforcement rule\>

Låt oss säga att följande SPF-regel finns för contoso.com:

v = spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

I det här exemplet får SPF-regeln den mottagande e-postservern endast för att acceptera e-post från de här IP-adresserna för domänen contoso.com:

- IP-adress #1

- IP-adress #2

- IP-adress #3

Denna SPF-regel beordrar den mottagande e-postservern som om ett meddelande kommer från contoso.com, men inte från en av dessa tre IP-adresser, ska den mottagande servern tillämpa den tvingande regeln på meddelandet. Regeln är vanligt vis ett av följande alternativ:

- **Svårt att fungera.** Markera meddelandet med "hårda misslyckande" i meddelandets kuvert och följ sedan mottagar serverns konfiguration för skräp post för den här typen av meddelande.

- **Mjukt fel.** Markera meddelandet med "Soft fail" i meddelandets kuvert. Vanligt vis är e-postservrar konfigurerade för att leverera dessa meddelanden ändå. De flesta slutanvändare ser inte det här märket.

- **Lös.** Gör inget, det är bara att markera meddelandets kuvert. Detta är vanligt vis reserverat för testning och används sällan.

Följande exempel visar hur SPF fungerar i olika situationer. I de här exemplen är contoso.com avsändare och woodgrovebank.com mottagaren.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Exempel 1: e-postauktorisering av ett meddelande som skickats direkt från avsändare till mottagare
<a name="spfExample1"> </a>

SPF fungerar bäst när sökvägen från avsändaren till mottagaren är direkt, till exempel:

![Diagram som visar hur SPF autentiserar e-post när det skickas direkt från server till server.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

När woodgrovebank.com tar emot meddelandet överförs SPF-kontrollen om IP-adress #1 finns i SPF TXT-posten för contoso.com:

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Exempel 2: avsändarens adress är inte en SPF-kontroll
<a name="spfExample2"> </a>

Anta att ett phisher hittar ett sätt att contoso.com:

![Diagram som visar hur SPF autentiserar e-post när det skickas från en falsk Server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Eftersom IP-adressen #12 inte finns i contoso. com-SPF TXT-posten Miss lyckas SPF-kontrollen och mottagaren kan välja att markera den som skräp post.

### <a name="example-3-spf-and-forwarded-messages"></a>Exempel 3: SPF och vidarebefordrade meddelanden
<a name="spfExample3"> </a>

En nackdel med SPF är att den inte fungerar när ett e-postmeddelande har vidarekopplats. Anta till exempel att användaren på woodgrovebank.com har konfigurerat en regel för vidarebefordring för att skicka e-post till ett outlook.com-konto:

![Diagram som visar hur SPF inte kan autentisera e-post när meddelandet vidarebefordras.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Meddelandet skickar först SPF-kontrollen på woodgrovebank.com, men det går inte att kontrol lera SPF-kontrollen på outlook.com eftersom IP #25 inte finns i contoso. com s SPF TXT Record. Outlook.com kan sedan markera meddelandet som skräp post. Undvik problemet genom att använda SPF tillsammans med andra e-postautentiseringsmetoder, till exempel DKIM och DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-grunderna: inklusive domäner från tredje part som kan skicka e-post åt din domän
<a name="SPFBasicsIncludes"> </a>

Förutom IP-adresser kan du också konfigurera SPF TXT-posten så att den omfattar domäner som avsändare. Dessa läggs till i SPF TXT-posten som "include"-satser. Contoso.com kanske till exempel vill ta med alla IP-adresser till e-postservrarna från contoso.net och contoso.org som också äger. För att göra det här publicerar contoso.com en SPF TXT-post som ser ut så här:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

När den mottagande servern ser den här posten i DNS utförs också en DNS-sökning på SPF TXT-posten för contoso.net och sedan för contoso.org. Om en ytterligare include-sats hittas i posterna för contoso.net eller contoso.org följer den också. För att förhindra denial of Service-attacker är det maximala antalet DNS-sökningar för ett enda e-postmeddelande 10. Varje include-instruktion representerar en ytterligare DNS-sökning. Om ett meddelande överskrider den 10 gränsen Miss lyckas SPF. När ett meddelande har nått den här gränsen, beroende på hur den mottagande servern är konfigurerad, får avsändaren få ett meddelande om att meddelandet genererade "för många sökningar" eller att det högsta tillåtna antalet hopp för meddelandet har överskridits (vilket kan hända när uppslagen går fortare och överskrider DNS-timeoutvärdet). Tips om hur du undviker det här finns i [fel sökning: metod tips för SPF i Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Krav för din SPF TXT-post och Microsoft 365
<a name="SPFReqsinO365"> </a>

Om du har konfigurerat e-post när du konfigurerar Microsoft 365 har du redan skapat en SPF TXT-post som identifierar Microsoft Messaging servers som en legitim källa för din domän. Posten ser antagligen ut så här:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Om du är en full kund, det vill säga att du inte har några lokala e-postservrar som skickar utgående e-post, är detta den enda SPF TXT-posten som du måste publicera för Office 365.

Om du har en hybrid distribution (det vill säga du har vissa post lådor lokalt och vissa som finns i Microsoft 365), eller om du är en fristående kund för Exchange Online Protection (EOP) (det innebär att din organisation använder EOP för att skydda dina lokala post lådor), bör du lägga till den utgående IP-adressen för varje lokal server för e-post till SPF-TXT-posten i DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Skapa en SPF TXT-post för Microsoft 365
<a name="FormYourSPF"> </a>

Använd syntaxen i den här artikeln för att skapa SPF TXT-posten för din egen domän. Även om det finns andra alternativ för syntax som inte nämns här är de vanligaste alternativen. När du har skapat posten måste du uppdatera posten hos domänregistratorn.

Information om de domäner du måste inkludera för Microsoft 365 finns i [externa DNS-poster som krävs för SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records). Följ de [stegvisa anvisningarna](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) för att uppdatera SPF-posterna för din domän registrator.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>SPF TXT Record-syntax för Microsoft 365
<a name="SPFSyntaxO365"> </a>

En typisk SPF TXT-post för Microsoft 365 har följande syntax:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

där:

- **v = spf1** krävs. Detta definierar TXT-posten som en SPF TXT-post.

- **IP4** anger att du använder IP version 4-adresser. **ip6** anger att du använder IP version 6-adresser. Om du använder IPv6-IP-adresser ersätter du **IP4** med **ip6** i exemplen i den här artikeln. Du kan också ange IP-adressintervall med CIDR-notering, till exempel **ip4:192.168.0.1/26**.

- _IP-adress_ är den IP-adress som du vill lägga till i SPF txt-posten. Det här är vanligt vis IP-adressen till servern för utgående e-post för din organisation. Du kan visa flera utgående e-postservrar. Mer information finns i [exempel: SPF-TXT-post för flera utgående lokala e-postservrar och Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _domän namn_ är den domän som du vill lägga till som en legitim avsändare. En lista över domän namn som du bör inkludera för Microsoft 365 finns i [externa DNS-poster som krävs för SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).

- Den här regeln är vanligt vis något av följande:

  - -all

    Anger hårda fel. Om du känner till alla godkända IP-adresser för din domän visar du dem i SPF TXT-posten och använder avgränsaren-all (hårda Fail). Om du bara använder SPF, det vill säga att du inte använder DMARC eller DKIM, bör du använda kvalificeraren-all. Vi rekommenderar att du använder alltid denna kvalificerare.

  - ~ alla

    Anger att det inte går att redundansväxla. Om du inte är säker på att du har en fullständig lista med IP-adresser bör du använda symbolen ~ all (mjuk Fail). Om du använder DMARC med p = Quarantine eller p = neka kan du också använda ~ alla. Annars används-alla.

  - ? alla

    Anger neutralt. Den används när du testar SPF. Vi rekommenderar inte att du använder den här omfallet i din drift sättning.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Exempel: SPF TXT-post som ska användas när alla dina e-postmeddelanden skickas av Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Om du har skickat all e-post från Microsoft 365 kan du använda den i din SPF TXT-post:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Exempel: SPF TXT-post för ett hybrid scenario med en lokal Exchange-Server och Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Om IP-adressen för den lokala Exchange-servern är 192.168.0.1 i en hybrid miljö kan du skapa en SPF TXT-post så här:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Exempel: SPF TXT-post för flera utgående lokala e-postservrar och Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Om du har flera utgående e-postservrar inkluderar du IP-adressen för varje e-postserver i SPF TXT-posten och avgränsar varje IP-adress med ett blank steg följt av en "IP4:"-instruktion. Till exempel:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Nästa steg: Konfigurera SPF för Microsoft 365
<a name="SPFNextSteps"> </a>

När du har formulerat din SPF TXT-post följer du stegen i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskningar](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för att lägga till den till din domän.

Trots att SPF är utformat för att förhindra förfalskning, men det finns en falsk behandlings teknik som SPF inte kan skydda mot. För att skydda mot dessa, bör du även konfigurera DKIM och DMARC för Microsoft 365 när du har konfigurerat SPF. För att komma igång, se [använda DKIM för att verifiera utgående e-post som skickas från din anpassade domän i Microsoft 365](use-dkim-to-validate-outbound-email.md). Därefter läser du [Använda DMARC för att validera e-post i Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Fel sökning: metod tips för SPF i Microsoft 365
<a name="SPFTroubleshoot"> </a>

Du kan bara skapa en SPF TXT-post för din anpassade domän. Om du skapar flera poster Miss lyckas en och samma resursallokering. För att undvika detta kan du skapa separata poster för varje under domän. Du kan till exempel skapa en post för contoso.com och en annan post för bulkmail.contoso.com.

Om ett e-postmeddelande orsakar mer än 10 DNS-sökningar innan det levereras, svarar den mottagande e-postservern med ett permanent fel, som även kallas  _PermError_, och orsakar meddelandet att neka SPF-kontrollen. Den mottagande servern kan även svara med en rapport om utebliven leverans (NDR) som innehåller ett fel liknande dessa:

- Meddelandet överskred antalet hopp.

- Meddelandet behövde för många uppslag.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Om du undviker fel meddelandet "för många sökningar" med Microsoft 365
<a name="SPFTroubleshoot"> </a>

Vissa SPF TXT-poster för domäner från tredje part styr den mottagande servern för att utföra ett stort antal DNS-sökningar. Vid den här skrivningen innehåller Salesforce.com till exempel 5 include-satser i posten:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Du kan undvika felet genom att implementera en policy där alla som skickar Mass utskick av e-post, till exempel, måste använda en under domän specifikt för detta syfte. Du anger sedan en annan SPF TXT-post för under domänen som innehåller Mass utskick via e-post.

 I vissa fall, till exempel salesforce.com-exemplet, måste du använda domänen i SPF TXT-posten, men i andra fall kanske tredje part redan har skapat en under domän som du kan använda i det här syftet. Exacttarget.com har till exempel skapat en under domän som du måste använda för din SPF TXT-post:

```text
cust-spf.exacttarget.com
```

När du inkluderar domäner från tredje part i din SPF TXT-post måste du bekräfta med den andra partens domän eller under domän som ska användas för att undvika att de 10 uppslags gräns värden körs.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Så här visar du den aktuella SPF TXT-posten och bestämmer antalet uppslag som krävs
<a name="SPFTroubleshoot"> </a>

Du kan använda nslookup för att visa dina DNS-poster, inklusive din SPF TXT-post. Om du hellre vill, det finns ett antal kostnads fria, online-verktyg som du kan använda för att visa innehållet i din SPF TXT-post. Genom att titta på din SPF TXT-post och följa kedjan med inkludera satser och omdirigeringar kan du bestämma hur många DNS-sökningar som behövs i posten. Vissa online-verktyg räknar och visar dessa uppslag för dig. Genom att hålla reda på detta nummer kan du förhindra att meddelanden som skickas från din organisation löser ett permanent fel, som kallas PermError, från den mottagande servern.

## <a name="for-more-information"></a>Mer information
<a name="SPFTroubleshoot"> </a>

Behöver du hjälp med att lägga till SPF TXT-posten? Läs artikeln [Skapa DNS-poster hos en DNS-värd för microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) för detaljerad information om användning av princip ramverket för avsändare med din anpassade domän i Microsoft 365. [Meddelandehuvuden i meddelande](anti-spam-message-headers.md) huvudet innehåller de syntax och huvud fält som används av Microsoft 365 för SPF-kontroller.


