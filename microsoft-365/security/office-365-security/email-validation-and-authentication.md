---
title: E-postautentisering i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Administratörer kan lära sig hur EOP använder e-autentisering (SPF, DKIM och DMARC) för att förhindra förfalskning, phishing och skräppost.
ms.openlocfilehash: 8db5045ec19c5552feba739628a2c9c1c508f620
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866641"
---
# <a name="email-authentication-in-eop"></a>E-postautentisering i EOP

E-postautentisering (kallas även för e-postverifiering) är en grupp standarder som försöker sluta förfalskning (e-postmeddelanden från falska avsändare). I alla Microsoft 365-organisationer använder EOP dessa standarder för att verifiera inkommande e-post:

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

E-postautentisering verifierar att e-postmeddelanden från en avsändare (till exempel laura@contoso.com) är giltiga och kommer från förväntade källor för den e-postdomänen (till exempel contoso.com.)

Resten av den här artikeln förklarar hur dessa tekniker fungerar och hur EOP använder dem för att kontrollera inkommande e-post.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Använda e-postautentisering för att förhindra förfalskning

DMARC förhindrar förfalskning genom att granska **från** adress i meddelanden. **Från** Adress är avsändarens e-postadress som användarna ser i sina e-postklienter. Destinationens e-postorganisationer kan också verifiera att e-postdomänen har passerat SPF eller DKIM. Med andra ord har domänen verifierats och därför skickas inte avsändarens e-postadress.

DNS-poster för SPF, DKIM och DMARC (gemensamt känd som e-autentiseringspolicy) är valfria. Domäner med starka e-autentiseringsprinciper som microsoft.com och skype.com är skyddade mot falskt fel. Men domäner med svagare e-autentiseringspolicy, eller ingen politik alls, är främsta mål för att bli förfalskade.

Till och med mars 2018 har endast 9 % av företag på Fortune 500-listan publicerat starka principer för e-postautentisering. De återstående 91% av företagen kan bli förfalskade av en angripare. Om du inte har en annan funktion för e-postfiltrering på plats kan e-post från falska avsändare i dessa domäner levereras till användare.

![DMARC-principer för Fortune 500-företag](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Andelen små till medelstora företag som publicerar starka e-autentiseringsprinciper är mindre. Och antalet är ännu mindre för e-postdomäner utanför Nordamerika och Västeuropa.

Brist på starka e-autentiseringsprinciper är ett stort problem. Medan organisationer kanske inte förstår hur e-autentisering fungerar, förstår angriparna fullt ut och de drar fördel. På grund av phishing-problem och det begränsade införandet av principer för stark e-postautentisering använder Microsoft *implicit e-postautentisering* för att kontrollera inkommande e-post.

Implicit e-autentisering är en förlängning av vanliga policyer för e-autentisering. Dessa tillägg inkluderar avsändarens rykte, avsändarhistorik, mottagarhistorik, beteendeanalys och annan avancerad teknik. I avsaknad av andra signaler från dessa tillägg markeras meddelanden som skickas från domäner som inte använder e-autentiseringspolicyer som falsk.

Du kan läsa Microsofts allmänna meddelande i [Ett hav av nätfiskare, del 2 – förbättrat skydd mot förfalskning i Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Sammansatt autentisering

Om det inte finns traditionella SPF-, DKIM-och DMARC-poster i en domän, överförs inte tillräcklig information om autentiserings status vid de post kontrollerna. Därför har Microsoft utvecklat en algoritm för implicit e-autentisering. Med den här algoritmen kombineras flera signaler till ett enda värde som kallas _oseparerad autentisering_eller `compauth` för kort. `compauth` värdet stämplas i **verifierings resultat** rubriken i meddelande rubrikerna.

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

Dessa värden förklaras i [Meddelanderubriken Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).

Genom att granska meddelandehuvudena kan administratörer eller slutanvändare fastställa hur Microsoft 365 upptäckte att avsändaren är falsk.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Varför e-postautentisering inte alltid är tillräckligt för att stoppa förfalskning

Att bara förlita sig på e-postautentisering för att avgöra om ett inkommande meddelande har manipulerats har följande begränsningar:

- Den sändande domänen kanske saknar de nödvändiga DNS-posterna eller så är posterna felaktigt konfigurerade.

- Källdomänen har konfigurerat DNS-poster som har konfigurerats korrekt men domänen stämmer inte överens med domänen i från-adressen. SPF och DKIM kräver inte att domänen används i från-adressen. Angripare eller legitima tjänster kan registrera en domän, konfigurera SPF och DKIM för domänen och använda en helt annan domän i Från-adressen. Meddelanden från avsändare inom den här domänen kommer att skicka SPF och DKIM.

Sammansatt autentisering kan lösa de här begränsningarna genom att godkänna meddelanden som annars skulle ha misslyckat e-postverifiering.

För enkelhetens skull ska följande exempel koncentrera sig på resultat av e-postverifiering. Andra intelligensfaktorer i backend kan identifiera meddelanden som klarar e-postautentisering som falska eller meddelanden som misslyckas e-postautentisering som legitima.

Exempel: fabrikam.com-domänen har inga SPF-, DKIM- eller DMARC-poster. Meddelanden från avsändare i fabrikam.com-domänen kan misslyckas sammansatt autentisering (Observera `compauth` värde och anledning):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Om fabrikam.com konfigurerar en SPF utan en DKIM-post, kan meddelandet passera sammansatt autentisering. Domänen som passerade SPF-kontroller är i linje med domänen i Från-adressen:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Om fabrikam.com konfigurerar en DKIM-post utan SPF-post, kan meddelandet passera sammansatt autentisering. Domänen i DKIM-signaturen är i linje med domänen i från-adressen:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Om domänen i SPF eller DKIM-signaturen inte överensstämmer med domänen i från-adressen kan meddelandet misslyckas med sammansatt autentisering:

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Lösning för legitima avsändare som skickar icke-autentiserade e-postmeddelanden

Microsoft 365 håller reda på vilka som skickar icke-autentiserad e-post till organisationen. Om tjänsten tycker att avsändaren inte är legitim kommer den att markera meddelanden från den här avsändaren som ett sammansatt autentiseringsfel. För att undvika denna dom kan du använda rekommendationerna i detta avsnitt.

### <a name="configure-email-authentication-for-domains-you-own"></a>Konfigurera e-postautentisering för domäner som du äger

Du kan själv använda den här metoden till att lösa förfalskning inom organisationen och förfalskning mellan domäner i fall där du äger eller interagerar med flera klientorganisationer. Det hjälper också till att lösa förfalskning mellan domäner där du skickar till andra kunder inom Microsoft 365 och också tredje parter med andra värdar.

- [Konfigurerar SPF-poster](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för dina domäner.

- [Konfigurera DKIM poster](use-dkim-to-validate-outbound-email.md) för dina primära domäner.

- [Överväg att konfigurera DMARC-poster](use-dmarc-to-validate-email.md) för att fastställa dina legitima avsändare.

Microsoft tillhandahåller inte detaljerade implementeringsriktlinjer för SPF, DKIM eller DMARC. Det finns dock många information online. Det finns också tredjepartsföretag som är dedikerade till att hjälpa din organisation att ställa in autentiseringsposter via e-post.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Du vet inte för alla källor för din e-post

Många domäner publicerar inte SPF-poster eftersom de inte vet alla e-postkällor för meddelanden i sina domäner. Börja med att publicera en SPF-post som innehåller alla e-postkällor som du vet om (särskilt där din företagstrafik finns), och publicera den neutrala SPF-principen `?all`. Till exempel:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Det här exemplet innebär att e-post från din företagsinfrastruktur ska skicka e-postautentisering, men e-post från okända källor kommer att gå tillbaka till neutrala.

Microsoft 365 behandlar inkommande e-post från din företagsinfrastruktur som autentiserad. E-post från oidentifierade källor kan fortfarande markeras som falsk om det misslyckas med implicit autentisering. Men det här är ändå en förbättring jämfört med att all e-post markeras som falsk av Microsoft 365.

När du har börjat med en SPF fallback-princip för `?all` kan du gradvis upptäcka och ta med fler e-postkällor för dina meddelanden och sedan uppdatera SPF-posten med en striktare policy.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Använd förfalskningsinformation för att konfigurera tillåtna avsändare av icke-autentiserad e-post

Du kan också använda [förfalskningsinformation](learn-about-spoof-intelligence.md) för att tillåta avsändare att skicka icke-autentiserade meddelanden till din organisation.

För externa domäner är den falska användaren domänen i från-adressen, medan den sändande infrastrukturen är antingen käll-IP-adressen (indelad i/24 CIDR-intervall), eller organisationsdomänen för PTR-posten.

I skärmbilden nedan kan käll-IP: 131.107.18.4 med PTR-posten outbound.mail.protection.outlook.com. Detta skulle visas som outlook.com för den sändande infrastrukturen.

För att tillåta den här avsändaren att skicka icke-autentiserad e-post ändrar du **Nej** till **Ja**.

![Konfigurera tillåtna avsändare för förfalskning](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Skapa en tillåta-post för avsändare/mottagare-paret

I [Skapa listor över betrodda avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md) finns information om hur du kringgår skräppostfiltrering, t.ex. vissa delar av nätfiskefiltrering, men inte filter för skadlig kod för vissa avsändare.

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Be avsändaren att konfigurera e-postautentisering för domäner som du inte äger

På grund av problem med skräppost och nätfiske rekommenderar Microsoft att alla avsändare konfigurerar e-postautentisering. I stället för att konfigurera manuella åsidosättningar i din organisation kan du be en administratör i den sändande domänen att konfigurera sina poster för e-postverifiering.

- Även om de inte har behövt publicera poster för e-postautentisering tidigare ska de göra det om de skickar e-post till Microsoft.

- Du bör konfigurera SPF för att publicera din domäns avsändande IP-adresser och även konfigurera DKIM (om tillgängligt) för att signera meddelanden digitalt. Du kan också konfigurera DMARC-poster.

- Om användarna massutskick för att skicka e-post åt dem, ska du kontrollera att domänen i från-adressen (om den tillhör dem) stämmer överens med den domän som beviljar SPF- eller DMARC.

- Kontrollera att följande platser (om de använder dem) ingår i SPF-posten:
  
  - Lokala e-postservrar.
  - E-post som skickas från en SaaS-leverantör (Software as-as-service).
  - E-post som skickas från en molnvärdtjänst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services osv.).

- För små domäner som är värd för en ISP konfigurerar du SPF-posten enligt anvisningarna från leverantören.

Det kan till en början vara svårt att få avsändardomäner att autentisera men med tiden, när allt fler e-postfilter markerar deras e-post som skräppost eller till och med avvisar dem så kommer de att konfigurera korrekta poster för att säkerställa bättre leverans. Deltagande i kampen mot nätfiske, och det kan minska risken för nätfiske i organisationer och organisationer som de skickar e-post till.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Information för leverantörer av infrastruktur (ISP:er, ESP:er eller molnvärdtjänster)

Om du är värd för en domäns e-post eller tillhandahåller infrastruktur som kan skicka e-post, ska du göra följande steg:

- Se till att dina kunder har dokumentation som förklarar hur kunderna ska konfigurera sina SPF-poster

- Överväg att signera DKIM-signaturer på utgående e-post även om kunden inte uttryckligen konfigurerar det (signera med en standarddomän). Du kan till och med dubbelsignera e-postmeddelandet med DKIM-signaturer (en gång med kundens domän om det har konfigurerats och en andra gång med företagets DKIM-signatur)

Leveransen till Microsoft garanteras inte även om du autentiserar e-post som kommer från din plattform men det ser åtminstone till att Microsoft inte markerar din e-post som skräppost för att den inte autentiseras.

Mer information om bästa praxis för tjänsteleverantörer finns i [M3AAWG Mobile Messaging Best Practices för tjänsteleverantörer](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
