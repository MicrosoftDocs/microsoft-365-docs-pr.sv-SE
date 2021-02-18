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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller felsökningsinformation för problem med att skicka e-post till inkorgar i Microsoft 365 & metodtips för massutskick till Microsoft 365-kunder.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286387"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Felsöka e-post som skickas till Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)

Den här artikeln innehåller felsökningsinformation för avsändare som har problem med att skicka e-post till inkorgar i Microsoft 365 och rekommendationer för massutskick till kunder.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Hanterar du ditt IP- och domäns rykte?

EOP-filtreringstekniken är utformad för att skydda mot skräppost för Microsoft 365 och andra Microsoft-produkter som Exchange Server. Vi använder även SPF, DKIM och DMARC. E-postautentiseringsteknik som hjälper dig att lösa problemet med förfalskning och nätfiske genom att verifiera att den domän som skickar e-postmeddelandet har behörighet att göra det. EOP-filtrering påverkas av ett antal faktorer relaterade till avsändande IP, domän, autentisering, korrekt lista, klagomålshastigheter, innehåll med mera. Av dessa är en av de viktigaste faktorerna för att skada avsändarens rykte och möjligheten att leverera e-post är klagomålsfrekvensen för skräppost.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Skickar du e-post från nya IP-adresser?

IP-adresser som inte tidigare använts för att skicka e-post har vanligtvis inte något rykte uppbyggt i våra system. Därför är det troligare att e-postmeddelanden från nya IP-adresser upplever leveransproblem. När IP-adressen har skapat ett rykte för att inte skicka skräppost ger EOP vanligtvis bättre upplevelse för e-postleverans.

Nya IP-adresser som läggs till för domäner som autentiseras under befintliga SPF-poster har vanligtvis den extra fördelen att ärva en del av domänens sändande rykte. Om din domän har goda möjligheter att skicka ryktet för nya IP-adresser kan det gå snabbare. En ny IP-adress kan förväntas bli helt nyare inom några veckor eller tidigare beroende på volym, listprecision och klagomålsfrekvens för skräppost.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Bekräfta att DNS-posterna är korrekt konfigurerade

Om du vill ha anvisningar om hur du skapar och underhåller DNS-poster, inklusive den MX-post som krävs för e-postdirigering, måste du kontakta din DNS-värd.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Se till att du inte annonserar dig själv som icke-dirigerbar IP

Vi kanske inte accepterar e-post från avsändare som misslyckas med en omvänd DNS-sökning. I vissa fall annonserar legitima avsändare sig själva felaktigt som en icke-dirigerbar IP när de försöker öppna en anslutning till EOP. IP-adresser som är reserverade för privata (icke-dirigerbara) nätverk:

- 192.168.0.0/16 (eller 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (eller 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (eller 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Du har fått en rapport om utebliven leverans (NDR) när du skickar e-post till en användare i Office 365

Vissa leveransproblem beror på att avsändarens IP-adress blockeras av Microsoft eller att användarkontot identifieras som spärrad avsändare på grund av tidigare skräppostaktivitet. Om du anser att du fått NDR-meddelandet av misstag ska du först följa instruktionerna i NDR-meddelandet för att lösa problemet.

Mer information om felet du fick finns i listan över felkoder i rapporter om utebliven leverans via [e-post i Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

 Om du till exempel får följande NDR visar det att den avsändande IP-adressen har blockerats av Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Om du vill begära borttagning från listan kan du använda [delist-portalen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)för att ta bort dig själv från listan med spärrade avsändare.

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mitt e-postmeddelande hamnar i mottagarens skräppostmapp

Om ett meddelande felaktigt identifierats som skräppost av EOP kan du samarbeta med mottagaren för att skicka det här falska positiva meddelandet till Microsofts team för skräppostanalys, som ska utvärdera och analysera meddelandet. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Trafiken från min IP-adress begränsas av EOP

Om du får en NDR från EOP som anger att din IP-adress begränsas av EOP, till exempel:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Du har fått NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har tillfälligt begränsats medan den utvärderas ytterligare. Om det finns en bedömning av vad som kan göras tas begränsningen bort inom kort.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Jag kan inte ta emot e-post från avsändare i Microsoft 365

 För att kunna ta emot meddelanden från våra användare ska du se till att nätverket tillåter anslutningar från IP-adresserna som EOP använder i våra datacenter. Mer information finns i [IP-adresser för Exchange Online Protection.](../../enterprise/urls-and-ip-address-ranges.md)

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Metodtips för massutskick till Microsoft 365-användare

Om du ofta gör massutskick av e-postkampanjer till Microsoft 365-användare och vill se till att dina e-postmeddelanden kommer in på ett säkert sätt i rätt tid följer du tipsen i det här avsnittet.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Kontrollera att från-namnet motsvarar vem som skickar meddelandet

Ämnet ska vara en kort sammanfattning av vad meddelandet handlar om, och meddelandets brödtext ska tydligt och tydligt ange vad erbjudandet, tjänsten eller produkten handlar om. Till exempel:

Rätt:

> Från: marketing@shoppershandbag.com <br> Ämne: Uppdaterad katalog för julafton!

Fel:

> Från: someone@outlook.com <br> Ämne: Kataloger

Ju enklare du gör det för andra att veta vem du är och vad du gör, desto mindre svårt är det att leverera via de flesta skräppostfilter.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Inkludera alltid ett alternativ för att avsluta prenumerationen i kampanjmeddelanden

Marknadsföringsmeddelanden, särskilt nyhetsbrev, bör alltid innehålla ett sätt att avsluta prenumerationen från framtida e-postmeddelanden. Till exempel:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "Avbryt prenumeration" i ämnesämnet. Detta är inte bättre än exemplet med ett klick ovan. Om du väljer att kräva att mottagarna skickar e-post ska du se till att alla obligatoriska fält är ifyllda när de klickar på länken.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Använd alternativet för dubbel registrering av e-post eller nyhetsbrev

Den här metoden rekommenderas om företaget kräver eller uppmuntrar användarna att registrera sin kontaktinformation för att få åtkomst till din produkt eller dina tjänster. Vissa företag gör det till en metod att automatiskt registrera sina användare för marknadsföringsmeddelanden eller e-nyhetsbrev under registreringen, men det här är en tveksam marknadsföringsmetod inom e-postfiltrering.

Om kryssrutan "Ja, skicka mig ditt nyhetsbrev" eller "Ja, skicka specialerbjudanden" är markerad som standard under registreringen, kan användare som inte är extra noga registrera sig för reklamutskick eller nyhetsbrev som de inte vill få.

 Vi rekommenderar dubbelval i stället, vilket innebär att kryssrutan för marknadsföringsmeddelanden eller nyhetsbrev är avmarkerad som standard. När registreringsformuläret har skickats skickas dessutom ett e-postmeddelande med en URL till användaren för att bekräfta att han eller hon vill ta emot marknadsföringsmeddelanden.

 På så sätt kan du se till att bara de användare som vill ta emot marknadsföringsmeddelanden har registrerat sig för e-postmeddelandena, och därefter rensar företaget för alla tveksamma marknadsföringsmetoder för e-postmeddelanden.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Kontrollera att e-postmeddelandets innehåll är transparent och kan spåras

Lika viktigt som hur e-postmeddelanden skickas är innehållet de innehåller. När du skapar e-postinnehåll ska du använda följande metodtips för att säkerställa att dina e-postmeddelanden inte flaggas med e-postfiltreringstjänster:

- När e-postmeddelandet begär att mottagarna ska lägga till avsändaren i adressboken bör det tydligt anges att en sådan åtgärd inte är en leveransgaranti.

- Omdirigeringar som ingår i brödtexten i meddelandet bör vara lika och konsekventa, och inte flera och varierade. En omdirigering i det här sammanhanget är någonting som pekar bort från meddelandet, till exempel länkar och dokument. Om du har många annonser eller länkar för att avsluta prenumerationen eller uppdatera profillänkarna, bör de alla peka på samma domän. Till exempel:

  Rätt (alla domäner är desamma):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Fel (alla domäner är olika):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Undvik innehåll med stora bilder och bifogade filer eller meddelanden som endast består av en bild.

- Din offentliga integritet eller P3P-inställningar bör tydligt ange förekomsten av spårningspunkter (webbbuggar eller beacons).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Ta bort felaktiga e-postalias från dina databaser

Alla e-postalias i databasen som skapar en icke-återstudsning är onödiga och innebär att dina utgående e-postmeddelanden riskerar att granskas ytterligare genom e-postfiltreringstjänster. Kontrollera att din e-postdatabas är uppdaterad.
