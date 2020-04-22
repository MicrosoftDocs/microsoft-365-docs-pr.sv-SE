---
title: E-postautentisering i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Lär dig mer om hur Exchange Online och Exchange Online Protection (EOP) i Microsoft 365 använder e-postautentisering (SPF, DKIM och DMARC) för att förhindra förfalskning, nätfiske och skräppost.
ms.openlocfilehash: f3a3ea902cb0c4fede4fcfd919f0969765bc4a96
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637562"
---
# <a name="email-authentication-in-microsoft-365"></a>E-postautentisering i Microsoft 365

E-postautentisering (kallas även för e-postverifiering) är en grupp standarder som försöker sluta förfalskning (e-postmeddelanden från falska avsändare). I Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används standarderna för att verifiera inkommande e-post:

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

E-postautentisering verifierar att e-postmeddelanden från en avsändare (till exempel laura@contoso.com) är giltiga och kommer från förväntade källor för den e-postdomänen (till exempel contoso.com.)

I resten av det här avsnittet förklaras hur dessa tekniker fungerar och hur EOP använder dem för att kontrollera inkommande e-post.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Använda e-postautentisering för att förhindra förfalskning

DMARC förhindrar förfalskning genom att granska **från** adress i meddelanden (den avsändar-e-postadress som användarna ser i sina e-postklienter). Mottagande e-postorganisationer kan också verifiera att e-postdomänen har godkänts i SPF- eller DKIM-kontrollen, vilket betyder att domänen har autentiserats och är därför ingen förfalskning. 

Men problemet är att SPF-, DKIM- och DMARC-poster i DNS för e-postautentisering (kollektivt kallat principer för e-postautentisering) är helt valfria. Det innebär att domäner med kraftfulla autentiseringsprinciper som microsoft.com och skype.com skyddas från förfalskning medan domäner som publicerar svagare autentiseringsprinciper eller ingen princip alls, är mål för att bli förfalskade.

Till och med mars 2018 har endast 9 % av företag på Fortune 500-listan publicerat starka principer för e-postautentisering. Återstående 91% av företagen kan ha manipulerats av en inkräktare. Om du inte har en annan funktion för e-postfiltrering på plats kan e-post från falska avsändare i dessa domäner levereras till användare.

![DMARC-principer för Fortune 500-företag](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Antalet små och medelstora företag som inte finns i Fortune 500-listan som publicerar starka principer för e-postautentisering är mindre, och ännu mindre för domäner som är utanför Nordamerika och Västeuropa.

Det här är ett stort problem, för att även om företagen kanske inte känner till hur e-postautentisering fungerar så vet nätfiskare det och utnyttjar den här bristen. Eftersom nätfiske är ett sådant problem och på grund av det begränsade införandet av principer för stark e-postautentisering, använder Microsoft *implicit e-postautentisering* för att kontrollera inkommande e-post.

Implicit e-postautentisering bygger på flera tillägg till vanliga principer för e-postautentisering. De här tilläggen är bland annat avsändarens rykte, avsändarhistorik, mottagarens historia, beteendeanalys och annan avancerad teknik. Ett meddelande som skickats från en domän som inte publicerar e-postautentisering markeras som förfalskning om det inte innehåller andra signaler som indikerar att det är äkta.

Du kan läsa Microsofts allmänna meddelande i [Ett hav av nätfiskare, del 2 – förbättrat skydd mot förfalskning i Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Sammansatt autentisering

SPF, DKIM och DMARC är alla användbara men de kommunicerar inte tillräckligt om autentiseringsstatus om ett meddelande inte har explicita autentiseringsposter. Därför har Microsoft utvecklat en algoritm för implicit e-postautentisering som kombinerar flera signaler till ett enda värde som kallas _sammansatt autentisering_ – eller förkortat till compauth. Compauth-värden är stämplade i **Autentiseringsresult**-huvudet i meddelandehuvudena.

> Autentiseringsresultat:<br/>&nbsp;&nbsp;&nbsp;compauth =\<misslyckat| godkänt | softpass | ingen\> anledning =\<yyy\>

Dessa värden förklaras i [Meddelanderubriken Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).

Genom att granska meddelandehuvudena kan administratörer eller slutanvändare fastställa hur Microsoft 365 upptäckte att avsändaren är falsk.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Varför e-postautentisering inte alltid är tillräckligt för att stoppa förfalskning

Att bara förlita sig på e-postautentisering för att avgöra om ett inkommande meddelande har manipulerats har följande begränsningar:

- Den sändande domänen kanske saknar de nödvändiga DNS-posterna eller så är posterna felaktigt konfigurerade.

- Källdomänen har konfigurerat DNS-poster som har konfigurerats korrekt men domänen stämmer inte överens med domänen i från-adressen. SPF och DKIM kräver inte att domänen används i från-adressen. Angripare och legitima tjänster kan registrera en domän, konfigurera SPF och DKIM för domänen, använda en helt annan domän i från-adressen och meddelandet klarar SPF och DKIM.

Sammansatt autentisering kan lösa de här begränsningarna genom att godkänna meddelanden som annars skulle ha misslyckat e-postverifiering.

> [!NOTE]
> Som tidigare beskrivits används flera signaler för implicit e-postautentisering för att avgöra om ett meddelande är legitimt. För enkelhetens skull ska följande exempel koncentrera sig på resultat av e-postverifiering. Andra intelligensfaktorer i backend kan identifiera meddelanden som klarar e-postautentisering som falska eller meddelanden som misslyckas e-postautentisering som legitima.

Exempel: fabrikam.com-domänen har inga SPF-, DKIM- eller DMARC-poster. Meddelanden från avsändare i fabrikam.com-domänen kan misslyckas sammansatt autentisering (Observera `compauth` värde och anledning):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Om fabrikam.com konfigurerar en SPF utan en DKIM-post kan meddelandet klara sammansatt autentisering eftersom domänen som passerade SPF justeras mot domänen i från-adressen:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Om fabrikam.com konfigurerar en DKIM-post utan en SPF-post kan meddelandet klara sammansatt autentisering eftersom domänen i den överförda DKIM-signaturen justeras mot domänen i från-adressen:

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

Microsoft 365 håller reda på vilka som skickar icke-autentiserad e-post till organisationen. Om tjänsten inte bedömer avsändaren som legitim markeras e-posten med ett compauth-fel. Du kan undvika det här genom att använda rekommendationerna i det här avsnittet.

### <a name="configure-email-authentication-for-domains-you-own"></a>Konfigurera e-postautentisering för domäner som du äger

Du kan själv använda den här metoden till att lösa förfalskning inom organisationen och förfalskning mellan domäner i fall där du äger eller interagerar med flera klientorganisationer. Det hjälper också till att lösa förfalskning mellan domäner där du skickar till andra kunder inom Microsoft 365 och också tredje parter med andra värdar.

- [Konfigurerar SPF-poster](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för dina domäner.

- [Konfigurera DKIM poster](use-dkim-to-validate-outbound-email.md) för dina primära domäner.

- [Överväg att konfigurera DMARC-poster](use-dmarc-to-validate-email.md) för att fastställa dina legitima avsändare.

Microsoft tillhandahåller inte detaljerade implementeringsriktlinjer för SPF, DKIM eller DMARC. Det finns emellertid mycket information tillgänglig online. Det finns även tredjepartsföretag specialiserade på att hjälpa din organisation att konfigurera poster för e-postautentisering.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Du vet inte för alla källor för din e-post

Många domäner publicerar inte SPF-poster eftersom de inte vet alla e-postkällor för meddelanden i sina domäner. Börja med att publicera en SPF-post som innehåller alla e-postkällor som du vet om (särskilt där din företagstrafik finns), och publicera den neutrala SPF-principen `?all`. Till exempel:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Det här exemplet innebär att e-post från din företagsinfrastruktur ska skicka e-postautentisering, men e-post från okända källor kommer att gå tillbaka till neutrala.

Microsoft 365 behandlar inkommande e-post från företagets infrastruktur som autentiserad, men e-post från oidentifierade källor kan fortfarande vara markerade som falska (beroende på om Microsoft 365 kan verifiera det implicit). Men det här är ändå en förbättring jämfört med att all e-post markeras som falsk av Microsoft 365.

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

Mer information om metodtips för tjänstleverantörer finns i [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf) (M3AAWG:s metodtips för mobila meddelanden för tjänstleverantörer).
