---
title: Felsöka e-post som skickas till Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: Den här artikeln innehåller felsökningsinformation för avsändare som har problem när de försöker skicka e-post till inkorgar i Office 365 och metodtips för massutskick till Office 365-kunder.
ms.openlocfilehash: 72dd0360038e58c2501728d9032fef95f81d90c2
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42807651"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>Felsöka e-post som skickas till Office 365

Den här artikeln innehåller felsökningsinformation för avsändare som har problem när de försöker skicka e-post till inkorgar i Office 365 och metodtips för massutskick till Office 365-kunder.

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>Felsöka vanliga problem med e-postleverans till Office 365

Välj bland ett av dessa vanliga problem.

- [Hanterar du din IP och domänens skicka rykte?](#are-you-managing-your-ip-and-domains-sending-reputation)

- [Skickar du e-post från nya IP-adresser?](#are-you-sending-email-from-new-ip-addresses)

- [Bekräfta att DNS:en är korrekt konfigurerad](#confirm-that-your-dns-is-set-up-correctly)

- [Se till att du inte annonserar själv som en icke-dirigerbar IP](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [Du har fått en rapport om utebliven leverans (NDR) när du skickade e-post till en användare i Office 365](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [Min e-post landade i mottagarens skräppostmapp i EOP](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [Trafiken från min IP-adress begränsas av EOP](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Hanterar du din IP och domänens skicka rykte?

EOP-filtreringstekniker är utformade för att ge skydd mot skräppost för Microsoft Office 365 och andra Microsoft-produkter som Exchange Server, Microsoft Office Outlook och Windows Live Mail. Vi utnyttjar också SPF, DKIM och DMARC; e-postautentiseringstekniker som hjälper till att lösa problemet med förfalskning och nätfiske genom att verifiera att domänen som skickar e-postmeddelandet har behörighet att göra det. EOP-filtrering påverkas av ett antal faktorer relaterade till den sändande IP, domän, autentisering, lista noggrannhet, klagomål priser, innehåll och mycket mer. Av dessa, en av de viktigaste faktorerna för att köra ner en avsändare rykte och deras förmåga att leverera e-post är deras skräp e klagomål takt.

### <a name="are-you-sending-email-from-new-ip-addresses"></a>Skickar du e-post från nya IP-adresser?

IP-adresser som inte tidigare använts för att skicka e-post har vanligtvis inget rykte byggt upp i våra system. Som ett resultat, e-post från nya IPs är mer benägna att uppleva leveransproblem. När IP har byggt upp ett rykte för att inte skicka skräppost, eop kommer vanligtvis att möjliggöra en bättre e-postleverans upplevelse.

Nya IPs som läggs till för domäner som autentiseras under befintliga SPF-poster får vanligtvis den extra fördelen att ärva en del av domänens sändningsrykte. Om din domän har ett gott sändningsrykt kan nya IPs uppleva en snabbare uppramptid. En ny IP kan förvänta sig att vara helt ramped inom ett par veckor eller tidigare beroende på volym, lista noggrannhet och skräp e-post klagomål priser.

### <a name="confirm-that-your-dns-is-set-up-correctly"></a>Bekräfta att DNS:en är korrekt konfigurerad

Om du vill ha instruktioner om hur du skapar och underhåller DNS-poster, inklusive MX-posten som krävs för e-postroutning, måste du kontakta din DNS-värd.

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Se till att du inte annonserar själv som en icke-dirigerbar IP

Vi kanske inte accepterar e-post från avsändare som misslyckas med en omvänd DNS-sökning. I vissa fall annonserar legitima avsändare sig felaktigt som en icke-internetdigerbar IP när de försöker öppna en anslutning till EOP. IP-adresser som är reserverade för privata (icke-dirigerbara) nätverk inkluderar:

- 192.168.0.0/16 (eller 192.168.0.0 - 192.168.255.255)

- 10.0.0.0/8 (eller 10.0.0.0 - 10.255.255.255)

- 172.16.0.0/11 (eller 172.16.0.0 - 172.31.255.255)

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Du har fått en rapport om utebliven leverans (NDR) när du skickade e-post till en användare i Office 365

Vissa leveransproblem är resultatet av att avsändarens IP-adress blockeras av Microsoft eller på att användarkontot identifieras som förbjudna avsändare på grund av tidigare skräppostaktivitet. Om du tror att du har fått NDR av misstag, följ först eventuella instruktioner i NDR-meddelandet för att lösa problemet.

Mer information om felet du fick finns i listan över felkoder i [rapporter om utebliven leverans via e-post i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Om du till exempel får följande NDR anger den att den sändande IP-adressen har blockerats av Microsoft.

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Om du vill begära borttagning från den här listan kan du [använda avlistningsportalen för att ta bort dig själv från listan Blockerade avsändare i Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>Min e-post landade i mottagarens skräppostmapp i EOP

Om ett meddelande felaktigt har identifierats som skräppost av EOP kan du arbeta med mottagaren för att skicka det här falska positiva meddelandet till Microsoft Spam Analysis Team, som utvärderar och analyserar meddelandet. Beroende på resultatet av analysen kan reglerna för skräppostinnehållsfilter justeras så att meddelandet kan skickas igenom. Du använder e-post för att skicka meddelanden till Microsoft som inte bör klassificeras som skräppost. När du gör det, se till att använda stegen i följande procedur.

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>Så här använder du e-post för att skicka falska positiva meddelanden till Microsoft Spam Analysis Team

1. Spara meddelandet som du vill skicka som icke-skräppost.

2. Skapa ett nytt, tomt meddelande och bifoga meddelandet om icke-skräppost till det.

    Du kan bifoga flera meddelanden som inte är skräppost om det behövs.

3. Kopiera och klistra in den ursprungliga meddelandeämnesraden i den nya ämnesraden för meddelande.

    > [!IMPORTANT]
    > Lämna brödtexten i det nya meddelandet tom.

4. Skicka det nya meddelandet till [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Trafiken från min IP-adress begränsas av EOP

Om du får en NDR från EOP som anger att din IP-adress begränsas av EOP, till exempel:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Du har fått NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har begränsats tillfälligt medan den utvärderas ytterligare. Om misstanken undanröjs genom utvärdering kommer denna begränsning att hävas inom kort.

### <a name="i-cant-receive-email-from-senders-in-office-365"></a>Jag kan inte ta emot e-post från avsändare i Office 365

 För att ta emot meddelanden från våra användare, se till att ditt nätverk tillåter anslutningar från IP-adresser som EOP använder i våra datacenter. Mer information finns i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>Metodtips för massutskick av e-post till Office 365-användare

Om du ofta genomför massutskick av e-post till Office 365-användare och vill se till att dina e-postmeddelanden kommer fram på ett säkert och snabbt sätt följer du tipsen i det här avsnittet.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Se till att namnet Från: återspeglar vem som skickar meddelandet

Ämnet bör vara en kort sammanfattning av vad meddelandet handlar om, och meddelandetexten bör tydligt och kortfattat ange vad erbjudandet, tjänsten eller produkten handlar om. Till exempel:

Korrekt:

> Från: marketing@shoppershandbag.com <br/> Ämne: Uppdaterad katalog för julen!

Felaktig:

> Från: someone@outlook.com <br/> Ämne: Kataloger

Ju lättare du gör det för människor att veta vem du är och vad du gör, desto mindre svårigheter kommer du att ha leverera genom de flesta spamfilter.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Inkludera alltid ett alternativ för att avsluta prenumerationen i kampanjmeddelanden

Marknadsföring e-post, särskilt nyhetsbrev, bör alltid innehålla ett sätt att avregistrera sig från framtida e-postmeddelanden. Till exempel:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`

Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "Avsluta prenumeration" i ämnet. Detta är inte att föredra framför ett klick exempel ovan. Om du väljer att kräva att mottagarna skickar ett e-postmeddelande kontrollerar du att alla obligatoriska fält är förifyllda när de klickar på länken.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Använd alternativet dubbel opt-in för marknadsföring e-post eller nyhetsbrev registrering

Den här bästa branschen rekommenderas om ditt företag kräver eller uppmuntrar användare att registrera sina kontaktuppgifter för att få tillgång till din produkt eller dina tjänster. Vissa företag gör det till en praxis att automatiskt registrera sina användare för marknadsföring e-post eller e-nyhetsbrev under registreringsprocessen, men detta anses vara en tvivelaktig marknadsföring praxis i en värld av e-filtrering.

Under registreringsprocessen, om "Ja, skicka mig ditt nyhetsbrev" eller "Ja, skicka mig specialerbjudanden" kryssrutan är vald som standard, användare som inte betalar stor uppmärksamhet kan oavsiktligt registrera dig för marknadsföring e-post eller nyhetsbrev som de inte vill ta emot.

 Vi rekommenderar alternativet dubbel opt-in i stället, vilket innebär att kryssrutan för marknadsföring av e-postmeddelanden eller nyhetsbrev är avmarkerad som standard. Dessutom, när registreringsformuläret har skickats, en verifiering e-post skickas till användaren med en webbadress som tillåter dem att bekräfta sitt beslut att ta emot marknadsföring e-post.

 Detta bidrar till att säkerställa att endast de användare som vill få marknadsföring e-post är registrerade för e-post, därefter rensa det sändande företaget av tvivelaktiga e-postmarknadsföring praxis.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Se till att e-postmeddelandets innehåll är genomskinligt och spårbart

Lika viktigt som hur e-postmeddelandena skickas är innehållet de innehåller. När du skapar e-postinnehåll använder du följande metodtips för att se till att dina e-postmeddelanden inte flaggas av e-postfiltreringstjänster:

- När e-postmeddelandet begär att mottagarna lägger till avsändaren i adressboken, bör det tydligt anges att en sådan åtgärd inte är en garanti för leverans.

- Omdirigeringar som ingår i meddelandets brödtext ska vara lika och konsekventa och inte flera och varierande. En omdirigering i det här sammanhanget är allt som pekar bort från meddelandet, till exempel länkar och dokument. Om du har många annonserings- eller unsubscribe-länkar eller uppdatera profillänkarna bör de alla peka på samma domän. Till exempel:

  Korrekt:

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Felaktig:

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Undvik innehåll med stora bilder och bifogade filer eller meddelanden som enbart består av en bild.

- Din offentliga integritet eller P3P-inställningar bör tydligt ange förekomsten av spårningspixlar (webbbuggar eller beacons).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Ta bort felaktiga e-postalias från databaserna

Alla e-postalias i databasen som skapar en studsa tillbaka är onödigt och sätter dina utgående e-postmeddelanden i riskzonen för ytterligare granskning av e-filtreringstjänster. Se till att din e-postdatabas är uppdaterad.
