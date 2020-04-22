---
title: Använda DMARC för att validera e-post i Office 365
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
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Lär dig hur du konfigurerar DMARC (Domain-based Message Authentication, Reporting, and Conformance) för att validera meddelanden som skickats från din Office 365-organisation.
ms.openlocfilehash: c71d4edabcacd2cd4d98dad69aa134cbaf75a111
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608144"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>Använda DMARC för att validera e-post i Office 365

[DMARC](https://dmarc.org) (Domain-based Message Authentication, Reporting, and Conformance) fungerar med SPF (Sender Policy Framework) och DKIM (DomainKeys Identified Mail) för autentisering av e-postavsändare och ser till att mål-e-postsystem litar på meddelanden som skickats från din domän. Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller.

> [!TIP]
> Gå till [Microsoft Intelligent Security Association](https://www.microsoft.com/misapartnercatalog)-katalogen (MISA) för att se externa leverantörer som erbjuder DMARC-rapportering för Office 365. 

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>Hur fungerar SPF och DMARC tillsammans för att skydda e-post i Office 365?
<a name="SPFandDMARC"> </a>

 Ett e-postmeddelande kan innehålla flera avsändaradresser. Adresserna används för olika ändamål. Tänk på följande adresser till exempel: 
  
- **”E-post från”-adress**: Identifierar avsändaren och anger vart returmeddelanden ska skickas om problem uppstår med leveransen av meddelandet, till exempel meddelanden om utebliven leverans. Det här visas i kuvertdelen av ett e-postmeddelande och visas normalt inte av e-postprogrammet. Detta kallas ibland för 5321.MailFrom-adressen eller reverse-path-adressen.

- **”Från”-adressen**: Adressen som visas som Från-adressen av e-postprogrammet. Adressen identifierar e-postmeddelandets upphovsman. Det vill säga, postlådan för personen eller systemet som ansvarar för att skriva meddelandet. Detta kallas ibland för 5322.From-adressen.

SPF använder en DNS TXT-post för att tillhandahålla en lista över godkända avsändande IP-adresser för en viss domän. Normalt utförs bara SPF-kontroller mot 5321.MailFrom-adressen. Det betyder att 5322.From-adressen autentiseras inte när du använder SPF enskilt. Det möjliggör ett scenario där en användare kan ta emot ett meddelande som godkänns i en SPF-kontroll men har en förfalskad 5322.From-avsändaradress. Tänk dig till exempel den här SMTP-utskriften:
  
```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

I den här utskriften är avsändaradresserna följande:
  
- E-post från-adress (5321.MailFrom): phish@phishing.contoso.com

- Från-adress (5322.From): security@woodgrovebank.com

Om du har konfigurerat SPF utför den mottagande servern en kontroll mot E-post från-adressen phish@phishing.contoso.com. Om meddelandet kom från en giltig källa för domänen phishing.contoso.com godkänns sedan SPF-kontrollen. Eftersom e-postklienten visar Från-adressen ser användaren att meddelandet kommer från security@woodgrovebank.com. Med bara SPF så autentiserades aldrig giltigheten för woodgrovebank.com.
  
När du använder DMARC utför den mottagande servern också en kontroll mot Från-adressen. Om det i exemplet ovan finns en DMARC TXT-post på plats för woodgrovebank.com misslyckas sedan kontrollen mot Från-adressen.
  
## <a name="what-is-a-dmarc-txt-record"></a>Vad är en DMARC TXT-post?
<a name="WhatisDMARC"> </a>

Liksom DNS-posterna för SPF är posten för DMARC en DNS-textpost (TXT) som hjälper till att förhindra förfalskning och nätfiske. Du publicerar DMARC TXT-poster i DNS. DMARC TXT-poster validerar e-postmeddelandens ursprung genom att verifiera e-postförfattarens IP-adress mot den påstådda ägaren till avsändardomänen. DMARC TXT-posten identifierar auktoriserade servrar för utgående e-post. Mål-e-postsystem kan verifiera att meddelanden de får härstammar från auktoriserade servrar för utgående e-post.
  
Microsofts DMARC TXT-post ser ut ungefär så här:
  
```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

Microsoft skickar sina DMARC-rapporter till [Agari](https://agari.com), en tredje part. Agari samlar in och analyserar DMARC-rapporter. Gå till [MISA-katalogen](https://www.microsoft.com/misapartnercatalog) för att se fler externa leverantörer som erbjuder DMARC-rapportering för Office 365.
  
## <a name="implement-dmarc-for-inbound-mail"></a>Implementerar DMARC-för inkommande e-post
<a name="implementDMARCinbound"> </a>

Du behöver inte göra något för att konfigurera DMARC för e-post som du har tagit emot i Office 365. Vi har tagit hand om allt åt dig. Om du vill veta vad som händer med e-post som inte godkänns i våra DMARC-kontroller kan du läsa [Så hanterar Office 365 inkommande e-post som misslyckas i DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>Implementera DMARC för utgående e-post från Office 365
<a name="implementDMARCoutbound"> </a>

Om du använder Office 365 men du inte använder en egen domän, det vill säga du använder onmicrosoft.com, behöver du inte göra något annat för att konfigurera eller implementera DMARC för din organisation. SPF är redan konfigurerat för dig och Office 365 genererar automatiskt en DKIM-signatur för utgående e-post. Mer information om den här signaturen finns i [Standardbeteende för DKIM och Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
 Om du har en egen domän eller om du använder lokala Exchange-servrar förutom Office 365 måste du manuellt implementera DMARC för utgående e-post. Implementering av DMARC för din egen domän omfattar följande steg:
  
- [Steg 1: Identifiera giltiga e-postkällor för din domän](use-dmarc-to-validate-email.md#IdentifyValidSources)

- [Steg 2: Konfigurera SPF för din domän i Office 365](use-dmarc-to-validate-email.md#ConfigSPF)

- [Steg 3: Konfigurera DKIM för din egen domän i Office 365](use-dmarc-to-validate-email.md#ConfigDKIM)

- [Steg 4: Skapa DMARC TXT-posten för din domän i Office 365](use-dmarc-to-validate-email.md#CreateDMARCRecord)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Steg 1: Identifiera giltiga e-postkällor för din domän
<a name="IdentifyValidSources"> </a>

Om du redan har konfigurerat SPF har du redan gått igenom den här övningen. Men för DMARC finns det fler överväganden. När du identifierar e-postkällor för din domän finns det två frågor du måste besvara:
  
- Vilka IP-adresser skickar meddelanden från min domän?

- För e-post som skickats från tredje parter för mig, kommer 5321.MailFrom- och 5322.From-domänen matcha?

### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>Steg 2: Konfigurera SPF för din domän i Office 365
<a name="ConfigSPF"> </a>

Nu när du har en lista över alla giltiga avsändare kan du följa stegen i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  
Om till exempel att contoso.com skickar e-post från Exchange Online, en lokal Exchange-server har en IP-adress som är 192.168.0.1 och ett webbprogram har en IP-adress som är 192.168.100.100, så skulle SPF TXT-posten se ut så här:
  
```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Vi rekommenderar att din SPF TXT-post tar hänsyn till externa avsändare.
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>Steg 3: Konfigurera DKIM för din egen domän i Office 365
<a name="ConfigDKIM"> </a>

När du har konfigurerat SPF måste du konfigurera DKIM. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Om du inte konfigurerar DKIM och istället tillåter Office 365 att använda den standardinställda DKIM-konfigurationen för din domän kanske DMARC misslyckas. Det beror på att den standardinställda DKIM-konfigurationen använder din första onmicrosoft.com-domän som 5322.From-adress, inte din egen domän. Det tvingar fram en felmatchning mellan 5321.MailFrom- och 5322.From-adressen i all e-post som skickas från din domän.
  
Om du har externa avsändare som skickar e-post för din räkning och e-posten de skickar har felmatchade 5321.MailFrom- och 5322.From-adresser så misslyckas DMARC för det e-postmeddelandet. Du kan undvika det här genom att konfigurera DKIM för din domän specifikt med den externa avsändaren. Det gör att Office 365 kan autentisera e-post från den tredjepartstjänsten. Men det gör också att andra, till exempel Yahoo, Gmail och Comcast, kan verifiera e-post som skickats av dem med den tredje parten som om det skulle vara e-post som skickats av dig. Det här är fördelaktigt eftersom dina kunder då kan bygga upp ett förtroende för din domän oavsett var deras postlåda finns, och samtidigt markerar Office 365 inte ett meddelande som skräppost på grund av förfalskning eftersom det godkänns i autentiseringskontroller för din domän.
  
Instruktioner för konfiguration av DKIM för externa användare så att de kan förfalska din domän finns i [Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md).
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>Steg 4: Skapa DMARC TXT-posten för din domän i Office 365
<a name="CreateDMARCRecord"> </a>

Det finns andra syntaxalternativ som inte nämns här men dessa är de vanligaste alternativen för Office 365. Skapa DMARC TXT-posten för din domän i följande format:
  
```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

där:
  
- *domain* är den domän du vill skydda. Som standard skyddar posten e-post från domänen och alla underdomäner. Om du till exempel anger \_dmarc.contoso.com skyddar sedan DMARC e-post från domänen och alla underdomäner, till exempel housewares.contoso.com eller plumbing.contoso.com.

- *TTL* ska alltid vara motsvarigheten till en timme. Enheten som används för TTL, antingen timmar (1 timme), minuter (60 minuter) eller sekunder (3 600 sekunder) varierar beroende på domänens registrator.

- *pct=100* anger att regeln ska användas för 100 % av e-posten.

- *policy* anger vilken princip du vill att den mottagande servern ska följa om DMARC misslyckas. Du kan ange none (ingen), quarantine (karantän) eller reject (avvisa) som princip.

Information om vilka alternativ du ska använda ska du bekanta dig med begreppen i [Metodtips för implementering av DMARC i Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).
  
Exempel:
  
- Principen inställd på none (ingen)
  
    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Principen inställd på quarantine (karantän)
  
    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Principen inställd på reject (avvisa)
  
    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

När du har skapat posten måste du uppdatera posten hos domänregistratorn. Instruktioner för hur du lägger till DMARC TXT-posten till dina DNS-poster för Office 365 finns i [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>Metodtips för implementering av DMARC i Office 365
<a name="DMARCbestpractices"> </a>

Du kan implementera DMARC gradvis utan att det påverkar resten av ditt e-postflöde. Skapa och implementera en lanseringsplan som följer de här stegen. Utför vart och ett av de här stegen först med en underdomän, sedan med andra underdomäner och till sist med domänen på den översta nivån i organisationen innan du går vidare till nästa steg.
  
1. Övervaka effekten av att implementera DMARC

    Börja med en ”monitoring-mode”-post (övervakningsläge) för en underdomän eller domän som begär att DMARC-mottagare skickar dig statistik om meddelanden som de ser via den domänen. En ”monitoring-mode”-post är en DMARC TXT-post som har sin princip inställd på ingen (p=none). Många företag publicerar en DMARC TXT-post med p=none eftersom de är osäkra på hur mycket e-post de kan förlora genom att publicera en mer restriktiv DMARC-princip. 

    Du kan göra detta även innan du har implementerat SPF eller DKIM i meddelandeinfrastrukturen. Men du kan inte på ett effektivt sätt sätta e-post i karantän eller avvisa den med DMARC tills du också implementerar SPF och DKIM. När du inför SPF och DKIM ger rapporterna som genererats genom DMARC siffrorna och källorna för meddelanden som godkänns i dessa kontroller och sådana som inte godkänns. Du kan enkelt se hur mycket av din legitima trafik som täcks eller inte täcks av dem, och felsöka problem. Du börjar också se hur många falska meddelanden som skickas, och varifrån.

2. Begära att externa e-postsystem placerar e-post i karantän som inte klarar DMARC

    När du tror att all eller det mesta av din legitima trafik skyddas av SPF och DKIM, och du förstår effekten med att implementera DMARC, kan du implementera en karantänprincip. En karantänprincip är en DMARC TXT-post som har principen inställd på karantän (p=quarantine). Genom att göra detta uppmanar du DMARC-mottagare att placera meddelanden från din domän som inte klarar DMARC i den lokala motsvarigheten till en skräppostmapp istället för kundernas inkorgar.

3. Begära att externa e-postsystem inte accepterar meddelanden som inte klarar DMARC

    Det sista steget är att implementera en avvisningsprincip. En avvisningsprincip är en DMARC TXT-post som har principen inställd på avvisa (p=reject). När du gör det här uppmanar du DMARC-mottagare att inte acceptera meddelanden som inte klarar DMARC-kontrollerna. 

## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Så hanterar Office 365 utgående e-post som inte klarar DMARC
<a name="outbounddmarcfail"> </a>

Om ett meddelande är utgående från Office 365 och inte klarar DMARC, och du har ställt in principen på p=quarantine eller p=reject, dirigeras meddelandet genom [Pool med hög riskleverans för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md). Det finns ingen åsidosättning för utgående e-post.
  
Om du publicerar en DMARC-avvisningsprincip (p=reject) kan ingen annan kund i Office 365 förfalska din domän eftersom meddelanden inte kan godkännas i SPF- eller DKIM-kontroller för din domän vid vidarebefordran av ett meddelande utgående via tjänsten. Men om du publicerar en DMARC-avvisningsprincip men inte har all din e-post som autentiseras via Office 365 kan en del av den markeras som skräppost för inkommande e-post (enligt beskrivningen ovan), eller så avvisas den om du inte publicerar SPF och försöker vidarebefordra den utgående genom tjänsten. Det sker, till exempel, om du glömmer att ta med några av IP-adresserna för servrar och appar som skickar e-post för din domän när du skapar din DMARC TXT-post.
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Så hanterar Office 365 ingående e-post som inte klarar DMARC
<a name="inbounddmarcfail"> </a>

Om DMARC-principen för den sändande servern är `p=reject`, markerar EOP meddelandet som falska istället för att avvisa det. Med andra ord hanterar Office 365`p=reject` och `p=quarantine` på samma sätt för inkommande e-post. Administratörer kan ange vilken åtgärd som ska utföras på meddelanden som klassificeras som falska i [principen för skydd mot nätfiske](set-up-anti-phishing-policies.md).
  
Office 365 är konfigurerat så här eftersom viss legitim e-post kanske inte klarar DMARC. Till exempel ett meddelande som skickas till en distributionslista som sedan vidarebefordrar meddelandet till alla listdeltagare. Om Office 365 har avvisat dessa meddelanden kan mottagare förlora legitim e-post och har inget sätt att hämta den. Istället så underkänns meddelandena fortfarande i DMARC men markeras som falska och avvisas inte. Användarna kan fortfarande få dessa meddelanden i inkorgen genom följande metoder:
  
- Användare lägger till betrodda avsändare individuellt med hjälp av sina e-postklienter.

- Administratörer kan uppdatera rapporteringen av [förfalskningsinformation](learn-about-spoof-intelligence.md) för att tillåta förfalskningen.

- Administratörer skapar en Exchange-e-postflödesregel (även kallad transportregel) för alla användare som tillåter meddelanden för dessa särskilda avsändare.

Mer information finns i [Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365).

## <a name="how-office-365-utilizes-authenticated-received-chain-arc"></a>Så använder Office 365 ARC (Authenticated Received Chain)
<a name="ARC"> </a>

Alla värdbaserade postlådor i Office 365 får du fördelen med ARC med leveransförbättringar för meddelanden och förbättrat förfalskningsskydd. ARC bevarar resultat av e-postautentisering från alla deltagande mellanhänder, eller hopp, när ett e-postmeddelande dirigeras från ursprungsservern till mottagarpostlådan. Innan ARC kan modifiering som utförs av mellanhänder i e-postdirigering, som regler för vidarebefordran eller automatiska signaturer, orsaka DMARC-fel när e-postmeddelandet har nått mottagarpostlådan. Med ARC tillåter det kryptografiska bevarandet av autentiseringsresultat Office 365 att verifiera autenticiteten för avsändaren av ett e-postmeddelande. 

Office 365 använder för närvarande ARC för att verifiera autentiseringsresultat när Microsoft är ARC-förseglare men planerar att lägga till support för ARC-förseglare från tredje part i framtiden. 

## <a name="troubleshooting-your-dmarc-implementation"></a>Felsöka din DMARC-implementering
<a name="dmarctroubleshoot"> </a>

Om du har konfigurerat din domäns MX-poster där EOP inte är den första posten tillämpas inte DMARC-fel för domänen. 
  
Om du är Office 365-kund pekar din domäns primära MX-post inte på EOP får du inte fördelarna med DMARC. DMARC fungerar till exempel inte om du pekar MX-posten på din lokala e-postserver och dirigerar sedan e-post till EOP med hjälp av ett anslutningsprogram. I det här scenariot är den mottagande domänen en av dina godkända domäner men EOP inte är primär MX. Anta till exempel att contoso.com pekar MX mot sig själv och använder EOP som en sekundär MX-post, så ser MX-posten för contoso.com ut så här:
  
```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Alla, eller de flesta, e-postmeddelanden dirigeras först till mail.contoso.com eftersom det är den primära MX-posten och sedan dirigeras e-post till EOP. I vissa fall kanske du inte listar EOP som en MX-post alls och använder bara anslutningsprogram för att dirigera e-post. EOP måste inte vara den första posten för att DMARC-validering ska göras. Den säkerställer bara valideringen, eftersom vi inte kan vara säkra på att alla lokala servrar/icke-O365-servrar kommer att göra DMARC-kontroller.  DMARC kan tillämpas för en kunds domän (inte server) när du konfigurerar DMARC TXT-posten men det är upp till den mottagande servern att faktiskt göra tillämpningen.  Om du konfigurerar EOP som mottagande server gör EOP DMARC-tillämpningen.
  
## <a name="for-more-information"></a>Mer information
<a name="sectionSection8"> </a>

Vill du ha mer information om DMARC? De här resurserna kan hjälpa dig.
  
- [Meddelandehuvuden för antiskräppost](anti-spam-message-headers.md) innehåller syntaxen och rubrikerna som används i Office 365 för DMARC-kontroller. 

- Genomför [DMARC-utbildningsserien](https://www.m3aawg.org/activities/training/dmarc-training-series) från M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Använd checklistan på [dmarcian](https://space.dmarcian.com/deployment/).

- Gå direkt till källan på [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Snabbreferens
<a name="sectionSection8"> </a>

[Så använder Office 365 SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md)
