---
title: Vanliga frågor om skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Vanliga frågor och svar för administratörer om skydd mot skräppost i Exchange Online och fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 0bd34639d717b979a02272e3c2f5de243c68d3ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636064"
---
# <a name="anti-spam-protection-faq"></a>Vanliga frågor om skydd mot skräppost

Det här avsnittet innehåller vanliga frågor och svar om skydd mot skräppost för Microsoft 365-kunder med postlådor i Exchange Online- eller fristående Exchange Online Protection-kunder (EOP) utan Exchange Online-postlådor.

Frågor och svar om karantänen finns i [Vanliga frågor om karantän](quarantine-faq.md).

Frågor och svar om skydd mot skadlig kod finns i [Vanliga frågor om skydd mot skadlig kod](anti-malware-protection-faq-eop.md).

För frågor och svar om anti-spoofing skydd, se [Anti-spoofing skydd FAQ](anti-spoofing-protection-faq.md).

## <a name="q-by-default-what-happens-to-a-spam-detected-message"></a>F. Vad händer som standard med ett meddelande som har upptäckts av skräppost?

A. **För inkommande meddelanden:** Majoriteten av spam raderas via anslutningsfiltrering, som baseras på IP-adressen för käll-e-postservern. Policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilterregler) inspekterar och klassificerar meddelanden som skräppost, bulk eller nätfiske. Som standard levereras meddelanden som klassificeras som skräppost eller bulk till mottagarens skräppostmapp, medan meddelanden som klassificeras som nätfiske sätts i karantän. Du kan ändra standardpolicyn mot skräppost (gäller alla mottagare) eller skapa anpassade policyer mot skräppost med striktare inställningar för specifika användargrupper (du kan till exempel sätta skräppost i karantän som skickas till chefer). Mer information finns i [Konfigurera policyer mot skräppost](configure-your-spam-filter-policies.md) och rekommenderade [policyinställningar för skräppost](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> I hybriddistributioner där EOP skyddar lokala postlådor måste du konfigurera två Exchange-regler för e-postflöde (kallas även transportregler) i din lokala Exchange-organisation för att identifiera EOP-skräppostfiltreringshuvuden som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **För utgående meddelanden:** Meddelandet dirigeras antingen genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) eller returneras till avsändaren i en rapport om utebliven leverans (kallas även NDR eller avvisningsmeddelande). Mer information om skydd för skräppost från utgående finns i [Utgående skräppostkontroller](outbound-spam-controls.md).

## <a name="q-whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>F. Vad är en zero-day spam variant och hur hanteras den av tjänsten?

A. En zero-day spam variant är en första generation, tidigare okänd variant av spam som aldrig har fångats eller analyserats, så våra anti-spam filter ännu inte har någon information tillgänglig för att upptäcka det. Efter att ett zero-day spam-exempel fångas in och analyseras av våra spamanalytiker, om det uppfyller kriterierna för spamklassificering, uppdateras våra anti-spamfilter för att upptäcka det, och det anses inte längre vara "zero-day".

**Anm.:** Om du får ett meddelande som kan vara en nolldagsrovariant skickar du meddelandet till Microsoft med någon av de metoder som beskrivs i [Rapportmeddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>F. Måste jag konfigurera tjänsten för att ge skydd mot skräppost?

A. När du har registrerat dig för tjänsten och lagt till din domän aktiveras skräppostfiltrering automatiskt. Som standard är skräppostfiltrering inställd för att skydda dig utan att behöva någon ytterligare konfiguration (bortsett från det tidigare noterade undantaget för fristående EOP-kunder i hybridmiljöer). Som administratör kan du redigera standardinställningarna för skräppostfiltrering så att de bäst uppfyller organisationens behov. För större granularitet kan du också skapa policyer mot skräppost och utgående principer mot skräppost som tillämpas på angivna användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (det vill säga den löpande ordningen) för dina anpassade principer.

Mer information finns i följande avsnitt:

[Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md)

[Konfigurera anti-princip](configure-the-connection-filter-policy.md)

[Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md)

[Konfigurera principen för skräppost för utgående](configure-the-outbound-spam-policy.md)

## <a name="q-if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>F. Om jag gör en ändring av en policy mot skräppost, hur lång tid tar det när jag har sparat mina ändringar för att de ska börja gälla?

A. Det kan ta upp till 1 timme innan ändringarna träder i kraft.

## <a name="q-is-bulk-email-filtering-automatically-enabled"></a>F. Är massfiltrering av e-post automatiskt aktiverat?

A. Ja. Mer information om massutskick finns [i Vad är skillnaden mellan skräppost och massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="q-does-the-service-provide-url-filtering"></a>F. Tillhandahåller tjänsten URL-filtrering?

A. Ja, tjänsten har ett URL-filter som söker efter webbadresser i meddelanden. Om webbadresser som är associerade med känd skräppost eller skadligt innehåll upptäcks markeras meddelandet som skräppost.

## <a name="q-how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>F. Hur kan kunder som använder tjänsten skicka falska negativa (skräppost) och falska positiva (icke-spam) meddelanden till Microsoft?

A. Skräppost och icke-skräppostmeddelanden kan skickas till Microsoft för analys på flera sätt. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-can-i-get-spam-reports"></a>F. Kan jag få skräppostrapporter?

A. Ja, du kan till exempel få en rapport om identifiering av skräppost i microsoft 365-administrationscentret. Den här rapporten visar skräppostvolymen som ett antal unika meddelanden. Mer information om rapportering finns i följande länkar:

Exchange Online-kunder: [Övervakning, rapportering och meddelandespårning i Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Fristående EOP-kunder: [Rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="q-someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>F. Någon skickade mig ett meddelande och jag kan inte hitta det. Jag misstänker att det kan ha upptäckts som spam. Finns det ett verktyg som jag kan använda för att ta reda på?

A. Ja, meddelandespårningsverktyget gör att du kan följa e-postmeddelanden när de passerar genom tjänsten, för att ta reda på vad som hände med dem. Mer information om hur du använder meddelandespårningsverktyget för att ta reda på varför ett meddelande har markerats som skräppost finns i [Har ett meddelande markerat som skräppost?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="q-will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>F. Kommer servicelimp (hastighetsbegränsning) min e-post om mina användare skickar skräppost?

A. Om mer än hälften av den e-post som skickas från en användare via tjänsten inom en viss tidsram (till exempel per timme) bedöms vara skräppost av Office 365, blockeras användaren från att skicka meddelanden. I de flesta fall, om ett utgående meddelande bedöms vara skräppost, dirigeras det genom högriskleveranspoolen, vilket minskar sannolikheten för att den normala utgående IP-poolen läggs till i en blockeringslista.

Du kan skicka ett meddelande till en angiven e-postadress när en avsändare blockeras skicka utgående skräppost. Mer information om den här inställningen finns i [Konfigurera principen för skräppost för utgående skräppost](configure-the-outbound-spam-policy.md).

## <a name="q-can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>F. Kan jag använda en tredjepartsleverantör mot skräppost och skadlig kod i samband med Exchange Online?

A. Ja. Även om vi rekommenderar att du pekar din MX-post till Microsoft, inser vi att det finns legitima affärsskäl för att dirigera din e-post till någon annanstans än Microsoft först.

- **Inkommande**: Ändra dina MX-poster så att de pekar på tredjepartsleverantören och omdirigera sedan meddelandena till EOP för ytterligare bearbetning. Mer information finns i [Förbättrad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Utgående**: Konfigurera smart värddirigering från Microsoft 365 till tredjepartsleverantören för mål.

## <a name="q-does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>F. Har Microsoft någon dokumentation om hur jag kan skydda mig mot nätfiske?

A. Ja. Mer information finns i [Skydda din integritet på internet](https://support.microsoft.com/help/4091455)

## <a name="q-are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>F. Undersöks meddelanden om skräppost och skadlig kod om vem som har skickat dem eller överförs till brottsbekämpande enheter?

A. Tjänsten fokuserar på identifiering och borttagning av skräppost och skadlig kod, även om vi ibland kan undersöka särskilt farliga eller skadliga spam- eller attackkampanjer och förfölja förövarna. Detta kan innebära att arbeta med våra juridiska och digitala brott enheter för att ta ner en spammare botnet, blockera spammare från att använda tjänsten (om de använder den för att skicka utgående e-post), och vidarebefordra informationen till brottsbekämpande för åtal.

## <a name="q-what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>F. Vilka är en uppsättning bästa utgående utskicksmetoder som säkerställer att min e-post levereras?

A. Riktlinjerna nedan är metodtips för att skicka utgående e-postmeddelanden.

- **Källe-domänen ska matchas i DNS.**

  Om avsändaren till exempel är user@fabrikam matchas domänen fabrikam till IP-adressen 192.0.43.10.
  
  Om en sändande domän inte har någon A-post och ingen MX-post i DNS dirigerar tjänsten meddelandet genom sin avancerade riskleveranspool oavsett om innehållet i meddelandet är skräppost eller inte. Mer information om leveranspoolen för högre risk finns i [Leveranspool med hög risk för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md).

- **Utgående e-post eserver bör ha en omvänd DNS (PTR) post.**

  Om ip-adressen för e-postkällan till exempel är 192.0.43.10, blir den omvända DNS-posten `43-10.any.icann.org`.'

- **Helo/EHLO- och MAIL FROM-kommandona bör vara konsekventa och finnas i form av ett domännamn i stället för en IP-adress.**

  Kommandot HELO/EHLO bör konfigureras så att det matchar den omvända DNS-adressen för den sändande IP-adressen så att domänen förblir densamma i de olika delarna av meddelanderubrikerna.

- **Kontrollera att rätt SPF-poster ställs in i DNS.**

  SPF-poster är en mekanism för att validera den e-post som skickas från en domän som verkligen kommer från den domänen och inte är förfalskad. Mer information om SPF-poster finns i följande länkar:

  [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Signera e-post med DKIM, underteckna med avslappnad kanonisering.**

  Om en avsändare vill signera sina meddelanden med DKIM (Domain Keys Identified Mail) och de vill skicka utgående e-post via tjänsten bör de signera med hjälp av den avslappnade algoritmen för kanoniskisering av huvuden. Signering med strikt header kanoniskisering kan ogiltigförklara signaturen när den passerar genom tjänsten.

- **Domänägare bör ha korrekt information i WHOIS-databasen.**

  Detta identifierar ägarna till domänen och hur du kontaktar dem genom att ange det stabila moderbolaget, kontaktpunkten och namnservrarna.

- **För massutskick ska namnet Från: återspegla vem som skickar meddelandet, medan meddelandets ämnesrad ska vara en kort sammanfattning av vad meddelandet handlar om.**

  Meddelandetexten ska ha en tydlig indikation på erbjudandet, tjänsten eller produkten. Om en avsändare till exempel skickar ut ett massutskick för Contoso-företaget är följande vad e-postmeddelandet Från och Ämne ska likna:

  > Från: marketing@contoso.com <br/> Ämne: Ny uppdaterad katalog för julen!

  Följande är ett exempel på vad man inte ska göra eftersom det inte är beskrivande:

  > Från: user@hotmail.com <br/> Ämne: Kataloger

- **Om du skickar ett massutskick till många mottagare och meddelandet är i nyhetsbrevsformat bör det finnas ett sätt att avregistrera längst ned i meddelandet.**

  Alternativet Avsluta prenumeration bör likna följande:

  > Det här meddelandet skickades till example@contoso.com av sender@fabrikam.com. Uppdatera profil/e-postadress | Omedelbar borttagning med **SafeUnsubscribe** &trade; | Sekretesspolicy

- **Om du skickar massmeddelande bör listförvärvet utföras med dubbel opt-in. Om du är en bulk mailer, dubbel opt-in är en bransch bästa praxis.**

  Dubbel opt-in är praxis att kräva att en användare att vidta två åtgärder för att registrera dig för marknadsföringsbrev:

  1. En gång när användaren klickar på en tidigare avmarkerad kryssruta där de väljer att ta emot ytterligare erbjudanden eller e-postmeddelanden från marknadsföraren.

  2. En andra gång när marknadsföraren skickar en bekräftelse e-post till användarens angivna e-postadress ber dem att klicka på en tidskänslig länk som kommer att slutföra sin bekräftelse.

  Använda dubbel opt-in bygger ett gott rykte för bulk e-avsändare.

- **Bulk avsändare bör skapa transparent innehåll som de kan hållas ansvariga för:**

  1. Verbiage begär att mottagarna lägger avsändaren till adressboken bör tydligt ange att en sådan åtgärd inte är en garanti för leverans.

  2. När du konstruerar omdirigeringar i meddelandets brödtext använder du ett konsekvent länkformat.

  3. Skicka inte stora bilder eller bifogade filer eller meddelanden som enbart består av en bild.

  4. När du använder spårningspixlar (webbbuggar eller beacons) anger du tydligt deras närvaro i din offentliga integritet eller P3P-inställningar.

- **Formatera utgående avvisningsmeddelanden.**

  När du genererar meddelanden om leveransstatus (kallas även rapporter om utebliven leverans, NDR eller avstudsmeddelanden) bör avsändare följa formatet för en avvisning enligt vad som anges i [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Ta bort avvisade e-postadresser för användare som inte finns.**

  Om du får en NDR som anger att en e-postadress inte längre används tar du bort det icke-existerande e-postaliaset från listan. E-postadresser ändras med tiden och personer ignorerar dem ibland.

- **Använd Hotmails SNDS-program (Smart Network Data Services).**

  Hotmail använder ett program som heter Smart Network Data Services som gör det möjligt för avsändare att kontrollera klagomål som lämnats in av slutanvändare. SNDS är den primära portalen för felsökning av leveransproblem till Hotmail.
