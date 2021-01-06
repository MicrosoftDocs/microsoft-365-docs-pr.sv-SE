---
title: Felsöka e-post som skickas till Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller felsöknings information för problem med att skicka e-post till Inkorgen i Microsoft 365 & metod tips för Mass utskick till Microsoft 365-kunder.
ms.openlocfilehash: 3504d7518073826f3979c3c837c58d4406886b41
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760488"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Felsöka e-post som skickas till Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Den här artikeln innehåller felsöknings information för avsändare som har problem med att skicka e-post till inkorgar i Microsoft 365 och metod tips för Mass utskick till kunder.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Hanterar du din IP-och domäns sändande rykte?

EOP filter Technologies är avsedda att tillhandahålla skydd mot skräp post för Microsoft 365 samt andra Microsoft-produkter som Exchange Server. Vi använder också SPF, DKIM och DMARC; tekniker för e-postverifiering som hjälper dig att lösa problemet med förfalskningar och nätfiske genom att verifiera att den domän som skickar e-postmeddelandet är behörig att göra det. EOP-filtreringen påverkas av ett antal faktorer som är relaterade till sändnings-IP-, domän-, verifikations-, list precision, klagomåls taxa, innehåll och annat. Av dessa är en av huvud faktorerna för att hålla ned avsändarens rykte och deras förmåga att skicka e-post till sin skräp post.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Skickar du e-post från nya IP-adresser?

IP-adresser som tidigare inte har använts för att skicka e-post har vanligt vis inget rykte inbyggt i våra system. Som ett resultat av detta är det mer sannolikt att skicka e-post från nya IP-adresser. När undersöknings perioden har byggt ett rykte för att inte skicka skräp post, ger EOP vanligt vis bättre funktioner för e-postleverans.

Nya IP-adresser som läggs till för domäner som är autentiserade under befintliga SPF-poster har vanligt vis utnyttjat fördelarna med att ärva en del av domänens avsändnings rykte. Om din domän har ett bra avsändar rykte kan nya IP-adresser uppleva snabbare. En ny IP-adress kan förvänta sig att bli helt ramp inom några veckor eller snart beroende på volym, lista över riktighet och skräp post taxa.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Kontrol lera att din DNS är korrekt konfigurerad

Instruktioner om hur du skapar och hanterar DNS-poster, inklusive MX-posten som krävs för e-postdirigering, måste du kontakta din DNS-värd.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Se till att du inte annonserar dig själv som en icke-Routing-IP

Vi kanske inte accepterar e-post från avsändare som inte har en omvänd DNS-sökning. I vissa fall annonseras legitima avsändare felaktigt som icke-Internetbaserad IP-adress när du försöker öppna en anslutning till EOP. IP-adresser som reserveras för privata (icke-dirigerbart) nätverk inkluderar:

- 192.168.0.0/16 (eller 192.168.0.0 – 192.168.255.255)
- 10.0.0.0/8 (eller 10.0.0.0-10.255.255.255)
- 172.16.0.0/11 (eller 172.16.0.0 – 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Du fick en rapport om utebliven leverans (NDR) när du skickar e-post till en användare i Office 365

Vissa leverans problem är resultatet av avsändarens IP-adress som blockeras av Microsoft eller på grund av att användar kontot identifieras som blockerad avsändare på grund av tidigare spam. Om du tror att du har fått fel meddelandet om MISSLYCKAd leverans problem, följer du först anvisningarna i NDR för att lösa problemet.

Om du vill ha mer information om det fel du fick kan du läsa listan med felkoder i [rapportera inte meddelanden om e-post i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Om du till exempel tar emot följande NDR anger det att den sändande IP-adressen blockerades av Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

För att begära borttagning från den här listan kan du [ta bort dig själv från listan Spärrade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)genom att använda List portalen.

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mitt e-postmeddelande landats i mottagarens mapp för skräp post

Om ett meddelande felaktigt har identifierats som skräp post av EOP kan du arbeta med mottagaren för att skicka detta falska positiva meddelande till Microsoft spam-gruppen, som kommer att utvärdera och analysera meddelandet. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Trafik från min IP-adress begränsas av EOP

Om du får en NDR från EOP att din IP-adress begränsas av EOP, till exempel:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Du fick meddelandet NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har tillfälligt begränsats medan den utvärderas vidare. Om misstanken är klar genom utvärdering kommer denna begränsning att hävas snart.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Jag kan inte ta emot e-post från avsändare i Microsoft 365

 För att ta emot meddelanden från våra användare ska du kontrol lera att nätverket tillåter anslutningar från IP-adresserna som EOP använder i våra data Center. Mer information finns i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Metod tips för Mass utskick via e-post till Microsoft 365-användare

Om du ofta utför Mass utskick av e-post till Microsoft 365-användare och vill försäkra dig om att dina e-postmeddelanden kommer till ett säkert och tidseffektivt sätt, följer du tipsen i det här avsnittet.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Kontrol lera att från-namnet återspeglar vem som skickar meddelandet

Ämnet bör vara en kort sammanfattning av vad meddelandet rör sig om och meddelandets brödtext bör tydligt och succinctly Visa vad erbjudandet, tjänsten eller produkten är till för. Ett exempel:

Rätt:

> Från: marketing@shoppershandbag.com <br> Ämne: Uppdaterad katalog för jul säsongen!

Fel:

> Från: someone@outlook.com <br> Ämne: kataloger

Ju lättare du gör det för folk att veta vem du är och vad du gör är det mindre svårt att få fram de flesta spam.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Inkludera alltid alternativet för att avbryta prenumerationer i e-post för kampanjer

Marknadsförings-e-postmeddelanden, särskilt nyhets brev, bör alltid innehålla ett sätt att avsluta en framtida e-post. Ett exempel:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "avabonnera" i ämnes raden. Det är inte lämpligt att använda ett av exemplen ovan. Om du väljer att kräva att mottagarna skickar ett e-postmeddelande, se till att när de klickar på länken är alla obligatoriska fält ifyllda.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Använd alternativet dubbelt opt-in för marknadsföring via e-post eller nyhets brev

Vi rekommenderar att du använder denna bransch metod om företaget kräver eller uppmuntrar användare att registrera sin kontakt information för att få åtkomst till din produkt eller tjänst. Vissa företag gör det för att automatiskt registrera sina användare för marknadsförings-e-post eller e-postnyhetsbrev under registrerings processen, men det anses vara en tveksam marknadsförings övning i världen med e-postfiltrering.

Under registrerings processen, om kryss rutan "Ja, skicka mig ett nyhets brev" eller "Ja, skicka mig med Special erbjudanden" är markerat som standard kan användare som inte betalar nära uppmärksamheten registrera sig för marknadsföring via e-post eller nyhets brev som de inte vill ta emot.

 Vi rekommenderar alternativet dubbel opt-in i stället, vilket betyder att kryss rutan för marknadsförings-e-post eller nyhets brev inte är markerad som standard. När registrerings formuläret har skickats skickas dessutom en bekräftelse via e-post till användaren med en URL som gör att de kan bekräfta marknadsförings-e-postmeddelanden.

 Då ser du till att bara de användare som vill få marknadsförings-e-post är registrerade för e-postmeddelandena och sedan Rensa det sändande företaget av en tveksam e-postmarknadsförings praxis.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Kontrol lera att e-postmeddelandets innehåll är transparent och kan spåras

Precis så viktigt som att e-postmeddelandena skickas är innehållet de innehåller. När du skapar e-post kan du använda följande metod tips för att se till att dina e-postmeddelanden inte flaggas via e-post filter tjänster:

- När e-postmeddelandet begär att mottagarna lägger till avsändaren i adress boken bör det tydligt uppges att sådan åtgärd inte är en garanti för leverans.

- Omdirigeringar som ingår i meddelandets brödtext ska vara liknande och enhetliga och inte multipla och varierande. Det är bara att omdirigera från meddelandet, till exempel länkar och dokument. Om du har många annonserings-eller avprenumerations länkar eller uppdaterar profil länkarna måste de peka på samma domän. Ett exempel:

  Korrekt (alla domäner är desamma):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Fel (alla domäner är olika):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Undvik innehåll med stora bilder och bifogade filer eller meddelanden som bara består av en bild.

- Dina offentliga integritets-eller P3P-inställningar bör tydligt ange närvaron av spårnings pixlar (webb programs och beacons).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Ta bort felaktiga e-postalias från dina databaser

Alla e-postalias i databasen som skapar en återuppringning är onödigt och gör dina utgående e-postmeddelanden till risk för ytterligare granskning via e-post filter tjänster. Kontrol lera att din e-postdatabas är uppdaterad.
