---
title: Vanliga frågor och svar om skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan visa vanliga frågor och svar om skydd mot skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8620ad3f99c45dae3442ec89d879124053c1a005
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175985"
---
# <a name="anti-spam-protection-faq"></a>Vanliga frågor och svar om skydd mot skräppost

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Det här avsnittet innehåller vanliga frågor och svar om skydd mot skadlig programvara för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.

Frågor och svar om karantän finns i Vanliga frågor [och svar om karantän.](quarantine-faq.md)

Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och svar om skydd mot [skadlig programvara.](anti-malware-protection-faq-eop.md)

Frågor och svar om skydd mot förfalskning finns i Vanliga frågor och svar om skydd mot [förfalskning.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Vad händer som standard med ett meddelande som identifierats av skräppost?

**För inkommande meddelanden:** Majoriteten av skräppost tas bort via anslutningsfiltrering, som baseras på IP-adressen för käll-e-postservern. Principer för skydd mot skräppost (kallas även principer för skräppostfilter eller principer för innehållsfilter) kontrollerar och klassificerar meddelanden som skräppost, massutskick eller nätfiske. Som standard levereras meddelanden som klassificeras som skräppost eller massutskick till mottagarens skräppostmapp, medan meddelanden som klassificeras som nätfiske har satts i karantän. Du kan ändra standardprincipen för skydd mot skräppost (gäller alla mottagare) eller så kan du skapa anpassade principer för skydd mot skräppost med striktare inställningar för specifika användargrupper (du kan till exempel sätta skräppost i karantän som skickas till ledningen). Mer information finns i Konfigurera [principer för skydd mot skräppost och](configure-your-spam-filter-policies.md) rekommenderade [policyinställningar mot skräppost.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

> [!IMPORTANT]
> I hybriddistributioner där EOP skyddar lokala postlådor måste du konfigurera två Exchange-e-postflödesregler (kallas även transportregler) i den lokala Exchange-organisationen för att identifiera rubrikerna för skräppostfiltrering i EOP som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **För utgående meddelanden:** Meddelandet dirigeras antingen [](high-risk-delivery-pool-for-outbound-messages.md) genom högriskleveranspoolen eller returneras till avsändaren i en rapport om utebliven leverans (kallas även NDR- eller icke-leveranskavsändarmeddelande). Mer information om skydd mot utgående skräppost finns i kontrollerna [för utgående skräppost.](outbound-spam-controls.md)

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Vad är en variant av skräppost utan dagar och hur hanteras den av tjänsten?

En variant av skräppost utan dagar är en första generationens, tidigare okänd variant av skräppost som aldrig har fångats eller analyserats, så våra filter mot skräppost har ännu ingen information tillgänglig för att upptäcka den. Efter att vi har fångat och analyserat ett skräppostexempel utan dag för skräppost, och om det uppfyller klassificeringskriterierna för skräppost, uppdateras våra skräppostfilter för att identifiera det och anses inte längre vara "nolldagars".

**Obs!** Om du får ett meddelande som kan vara en variant av skräppost utan dagar, ber vi dig skicka meddelandet till Microsoft med någon av de metoder som beskrivs i Rapportera meddelanden och filer till Microsoft för att hjälpa oss att förbättra [tjänsten.](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Behöver jag konfigurera tjänsten för att skydda mot skräppost?

När du har registrerar dig för tjänsten och lagt till din domän aktiveras skräppostfiltrering automatiskt. Som standard anpassas skräppostfiltreringen för att skydda dig utan att behöva någon ytterligare konfiguration (förutom det tidigare nämnda undantaget för fristående EOP-kunder i hybridmiljöer). Som administratör kan du redigera standardinställningarna för skräppostfiltrering så att de bäst uppfyller organisationens behov. För större detaljnivå kan du också skapa principer för skydd mot skräppost och utgående principer för skydd mot skräppost som tillämpas på vissa användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (det vill säga ordningen) för dina anpassade principer.

Mer information finns i följande avsnitt:

[Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md)

[Konfigurera anslutningsfiltrering i EOP](configure-the-connection-filter-policy.md)

[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)

[Konfigurera policyn för utgående skräppost](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Hur lång tid tar det att ändra en princip mot skräppost efter att jag har sparat ändringarna för att den ska gälla?

Det kan ta upp till 1 timme innan ändringarna verkställs.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Är massfiltrering av e-post automatiskt aktiverat?

Ja. Mer information om massutskick finns i [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)

## <a name="does-the-service-provide-url-filtering"></a>Tillhandahåller tjänsten URL-filtrering?

Ja, tjänsten har ett URL-filter som söker efter URL-adresser i meddelanden. Om URL:er som är associerade med känt skräppost eller skadligt innehåll identifieras markeras meddelandet som skräppost.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hur kan kunder som använder tjänsten skicka falska negativa meddelanden (skräppost) och falska positiva meddelanden (icke skräppost) till Microsoft?

Skräppost- och icke-skräppostmeddelanden kan skickas till Microsoft för analys på flera olika sätt. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan jag få rapporter om skräppost?

Ja, du kan till exempel få en rapport om identifiering av skräppost i administrationscentret för Microsoft 365. I den här rapporten visas skräppostvolymen som antalet unika meddelanden. Mer information om rapportering finns i följande länkar:

Exchange Online-kunder: [Övervaka, rapportera och meddelandespårning i Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Fristående EOP-kunder: [Rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Någon har skickat ett meddelande till mig och jag kan inte hitta det. Jag misstänker att den kan ha identifierats som skräppost. Finns det något verktyg jag kan använda för att ta reda på det?

Ja, med verktyget för meddelandespårning kan du följa upp e-postmeddelanden när de passerar genom tjänsten för att ta reda på vad som har hänt med dem. Mer information om hur du använder verktyget för meddelandespårning för att ta reda på varför ett meddelande har markerats som skräppost finns i Var ett meddelande markerat [som skräppost?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Begränsar tjänsten (rate limit) min e-post om mina användare skickar utgående skräppost?

Om mer än hälften av e-postmeddelandet som skickas från en användare via tjänsten inom en viss tidsperiod (till exempel per timme) har fastställt att det är skräppost av EOP, kommer användaren att blockeras från att skicka meddelanden. Om ett utgående meddelande i de flesta fall avgörs som skräppost dirigeras det genom högriskleveranspoolen, vilket minskar sannolikheten för att den normala utgående IP-poolen läggs till i en blockeringslista.

Du kan skicka ett meddelande till en angiven e-postadress när en avsändare blockeras för att skicka utgående skräppost. Mer information om den här inställningen finns i [Konfigurera policyn för utgående skräppost.](configure-the-outbound-spam-policy.md)

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan jag använda en tredjepartsleverantör för skydd mot skräppost och skadlig programvara tillsammans med Exchange Online?

Ja. Vi rekommenderar att du pekar MX-posten på Microsoft, men vi inser att det finns legitima affärsorsaker till att dirigera din e-post till någon annan plats än Microsoft först.

- **Inkommande:** Ändra mx-posterna så att de pekar på tredjepartsleverantören och omdirigera sedan meddelandena till EOP för ytterligare bearbetning. Mer information finns i [Utökad filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Utgående:** Konfigurera smart värddirigering från Microsoft 365 till tredjepartsleverantörens mål.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Har Microsoft någon dokumentation om hur jag kan skydda mig från nätfiske?

Ja. Mer information finns i [Skydda din integritet på Internet](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Undersöks skräppost och skadlig programvara som till vem som har skickat dem eller överförs till rättstvingande myndigheter?

Tjänsten fokuserar på identifiering och borttagning av skadlig programvara, men vi kan emellanåt undersöka särskilt farligt eller skadligt skräppost eller attackkampanjer och nå ut med intrången. Det här kan innebära att vi arbetar med våra juridiska och digitala brottsplatser för att ta bort en botnät som skickar skräppost, blockerar skräppostavs skräppostavsändaren från att använda tjänsten (om de använder den för att skicka utgående e-post) och att vidarebefordra informationen till brottslingen av brottslingen.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Vad är en uppsättning bästa metoder för utgående e-post som säkerställer att min e-post levereras?

Riktlinjerna nedan är de bästa metoderna för att skicka utgående e-postmeddelanden.

- **Källans e-postdomän ska matcha i DNS.**

  Om avsändaren till exempel är user@fabrikam matchas domänen fabrikam med IP-adressen 192.0.43.10.

  Om en avsändande domän inte har någon A-post och ingen MX-post i DNS, dirigerar tjänsten meddelandet genom sin högriskleveranspool oavsett om innehållet i meddelandet är skräppost eller inte. Mer information om högriskleveranspool finns i [Högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)

- **Utgående e-postserver bör ha en omvänd DNS-post (PTR).**

  Om t.ex. IP-adressen för e-postkällan är 192.0.43.10 blir den omvända DNS-posten `43-10.any.icann.org` .'

- **Kommandona HELO/EHLO och MAIL FROM bör vara konsekventa och finnas i form av ett domännamn i stället för en IP-adress.**

  Kommandot HELO/EHLO bör konfigureras för att matcha den omvända DNS:en för den avsändande IP-adressen så att domänen förblir densamma i de olika delarna av meddelanderubrikerna.

- **Se till att rätt SPF-poster har ställts in i DNS.**

  SPF-poster är en mekanism för att verifiera att e-post som skickas från en domän verkligen kommer från den domänen och inte är kapad. Mer information om SPF-poster finns i följande länkar:

  [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Vanliga frågor och svar om domäner](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Signera e-post med DKIM, signera med lugnt kanonisk ordning.**

  Om en avsändare vill signera sina meddelanden med Domain Keys Identified Mail (DKIM) och de vill skicka utgående e-post via tjänsten, bör de signera med den smarta rubrikalgoritmen för kanonisk ordning. Om du signerar med strikt kanonisk information kan signaturen bli ogiltig när den passerar genom tjänsten.

- **Domänägare bör ha korrekt information i WHOIS-databasen.**

  Då identifieras ägare av domänen och hur de kontaktas genom att de anges i det stabila huvudföretaget, kontakt- och namnservrarna.

- **För massutskick ska från-namnet ange vem som skickar meddelandet, medan ämnesraden i meddelandet ska vara en kort sammanfattning av vad meddelandet handlar om.**

  Meddelandetexten bör ha en tydlig indikation om erbjudandet, tjänsten eller produkten. Om en avsändare till exempel skickar ett massutskick till Contoso-företaget ska e-postmeddelandet Från och Ämne se ut så här:

  > Från: marketing@contoso.com <br> Ämne: Ny uppdaterad katalog för julafton!

  Följande är ett exempel på vad du inte ska göra eftersom det inte är beskrivande:

  > Från: user@hotmail.com <br> Ämne: Kataloger

- **Om du skickar ett massutskick till många mottagare och meddelandet är i nyhetsbrevsformat, bör det finnas ett sätt att avsluta prenumerationen längst ned i meddelandet.**

  Avanmälningsalternativen bör se ut så här:

  > Det här meddelandet skickades till example@contoso.com via sender@fabrikam.com. Uppdatera profil/e-postadress | Snabbborttagning **med SafeUnsubscribe** &trade; | Sekretesspolicy

- **Om du skickar massutskick bör hämtning av listor utföras med dubbel opt-in. Om du använder massutskick är det bäst att dubbelanmäla sig.**

  Dubbel inloggning är att kräva att en användare gör två saker för att registrera sig för marknadsföringsmeddelanden:

  1. En gång när användaren klickar på en tidigare avmarkerad kryssruta där de kan välja att få ytterligare erbjudanden eller e-postmeddelanden från marknadsföraren.

  2. En andra gång när marknadsföraren skickar ett bekräftelsemeddelande till användarens angivna e-postadress och ber dem klicka på en tidskänslig länk som slutför bekräftelsen.

  Genom att använda dubbel välja att delta får man ett gott rykte för avsändare av massutskick.

- **Massavsändare bör skapa transparent innehåll som de kan hållas ansvariga för:**

  1. Utförlig begäran att mottagarna ska lägga till avsändaren i adressboken bör tydligt ange att den åtgärden inte är en leveransgaranti.

  2. Använd ett konsekvent länkformat när du konstruerar omdirigeringar i meddelandets brödtext.

  3. Skicka inte stora bilder eller bifogade filer eller meddelanden som endast består av en bild.

  4. När du använder spårningspunkter (webbbuggar eller beacons) kan du tydligt ange deras närvaro i dina inställningar för offentlig sekretess eller P3P.

- **Formatera utgående obundna meddelanden.**

  När meddelanden om leveransstatus genereras (kallas även rapporter om utebliven leverans, NDR-rapporter eller icke-leveranskaviseringar) ska avsändarna följa formatet för icke-leveranskavvikande enligt givna i [RFC 3464.](https://www.ietf.org/rfc/rfc3464.txt)

- **Ta bort e-postadresser som inte studsar för användare som inte finns.**

  Om du får en NDR som anger att en e-postadress inte längre används tar du bort e-postaliaset som inte finns i listan. E-postadresser ändras med tiden och ibland ignoreras de.

- **Använd Hotmails SNDS-program (Smart Network Data Services).**

  Hotmail använder ett program som kallas Smart Network Data Services som gör att avsändare kan kontrollera klagomål som skickats in av slutanvändare. SNDS är den primära portalen för felsökning av leveransproblem till Hotmail.
