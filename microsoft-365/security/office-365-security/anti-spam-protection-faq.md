---
title: Vanliga frågor och svar om skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan se vanliga frågor och svar om skydd mot skräp post i Exchange Online Protection (EOP).
ms.openlocfilehash: d2505eea572e512b306cf26c7a57d1dc1b705c0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844470"
---
# <a name="anti-spam-protection-faq"></a>Vanliga frågor och svar om skydd mot skräppost

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Det här avsnittet innehåller vanliga frågor och svar om skydd mot skadlig program vara för Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor.

Frågor och svar om karantänen finns i [vanliga frågor om karantän](quarantine-faq.md).

Frågor och svar om skydd mot skadlig program vara finns i [vanliga frågor om skydd mot skadlig program vara](anti-malware-protection-faq-eop.md).

Frågor och svar om skydd mot förfalskning finns i [vanliga frågor](anti-spoofing-protection-faq.md)och svar om skydd mot förfalskning.

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Vad händer som standard med skräp post?

**För inkommande meddelanden:** Majoriteten av skräp posten tas bort med anslutnings filtrering, som baseras på e-postserverns IP-adress. Principer mot skräp post (kallas även för principer för skräp post filter eller principer för innehålls filter) inspektera och klassificera meddelanden som skräp post, bulk eller nätfiske. Som standard skickas meddelanden som klassificeras som skräp post eller bulk till i mottagarens mapp för skräp post, medan meddelanden som klassificeras som nätfiske placeras i karantän. Du kan ändra standard principen för skräp post (gäller alla mottagare), eller så kan du skapa anpassade principer för skräp post med striktare inställningar för specifika grupper med användare (till exempel att du kan skicka skräp post till chefer). Mer information finns i [Konfigurera principer för skräp post](configure-your-spam-filter-policies.md) och [rekommenderade princip inställningar för skräp post](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> I hybrid distributioner där EOP skyddar lokala post lådor måste du konfigurera två regler för Exchange-flöden (kallas även transport regler) i din lokala Exchange-organisation för att identifiera de EOP spam-meddelandehuvuden som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **För utgående meddelanden:** Meddelandet dirigeras antingen via [poolen för högrisk leveranser](high-risk-delivery-pool-for-outbound-messages.md) eller återförs till avsändaren i en rapport om utebliven leverans (kallas även en NDR eller ett studs meddelande). Mer information om utgående skräp post finns i [Inställningar för utgående e-post](outbound-spam-controls.md).

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Vad är en nollängdssträng och hur hanteras den av tjänsten?

En variant av skräp post med nollängd är en första generation, tidigare okänd variant av skräp post som aldrig har fångats eller analyser ATS, så våra filter för skräp post har ingen information tillgänglig för att upptäcka den. Efter att ett skräp exempel från en tom dag har samlats och analyser ATS av våra skräp post analyser, om det uppfyller kraven för skräp post, uppdateras våra skydd mot skräp post filter för att det ska identifieras och det anses inte längre "noll dag".

**Obs!** Om du får ett meddelande om att du får ett e-postmeddelande som är noll under en tom dag kan du skicka meddelandet till Microsoft via någon av de metoder som beskrivs i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Måste jag konfigurera tjänsten för att tillhandahålla skydd mot skräp post?

När du har registrerat dig för tjänsten och lagt till din domän aktive ras skräp post filtrering automatiskt. Standardinställningen är att skräp post filtreringen är inställd för att skydda dig utan ytterligare konfiguration (utöver det tidigare noterade undantaget för fristående EOP fristående kunder i hybrid miljöer). Som administratör kan du redigera standardinställningarna för skräp post filtrering så att de passar bäst för din organisation. För högre precision kan du även skapa principer för skräp post och utgående principer för skräp post som används för angivna användare, grupper eller domäner i organisationen. Anpassade principer har alltid högre prioritet än standard principen, men du kan ändra prioriteten (d.v.s. den kör ande ordningen) på dina anpassade principer.

Mer information finns i följande avsnitt:

[Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md)

[Konfigurera anslutnings filtrering i EOP](configure-the-connection-filter-policy.md)

[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)

[Konfigurera principen för utgående skräp post](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Om jag ändrar en policy mot skräp post, hur lång tid tar det innan jag sparar mina ändringar så att de börjar gälla.

Det kan ta upp till 1 timme innan ändringarna börjar gälla.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Är Mass utskick av e-post automatiskt aktiverat?

Ja. Mer information om Mass utskick av e-post finns i [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="does-the-service-provide-url-filtering"></a>Tillhandahåller tjänsten URL-filtrering?

Ja, tjänsten har ett URL-filter som söker efter URL-adresser i meddelanden. Om URL-adresser som är associerade med känt skräp post eller skadligt innehåll identifieras markeras meddelandet som skräp post.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hur kan kunder som använder tjänsten skicka falsk negativ (spam) och falska positiva (icke-spam) meddelanden till Microsoft?

Skräp post och meddelanden som inte är skräp post kan skickas till Microsoft för analys på flera olika sätt. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan jag få skräp post rapporter?

Ja, till exempel för att få en rapport om skräp identifiering i administrations centret för Microsoft 365. Den här rapporten visar spam volymen som ett antal unika meddelanden. Mer information om rapportering finns i följande länkar:

Exchange Online-kunder: [övervakning, rapportering och meddelande spårning i Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Fristående EOP kunder: [rapportering och meddelande spårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Någon skickade mig ett meddelande och jag kan inte hitta det. Jag misstänker att den kan ha identifierats som skräp post. Finns det något verktyg som jag kan använda för att ta reda på det?

Ja, verktyget för meddelande spårning gör att du kan följa e-postmeddelanden när de passerar via tjänsten, för att ta reda på vad som hände med dem. Mer information om hur du använder verktyget för meddelande spårning för att ta reda på varför ett meddelande har marker ATS som skräp post finns i [ett meddelande som marker ATS som skräp post?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Kan tjänstens begränsning (kostnads gräns) My mail om mina användare skickar utgående skräp post?

Om mer än hälften av e-postmeddelandet som skickas från en användare via tjänsten inom en viss tidsram (till exempel per timme) fastställs som skräp post av EOP, hindras användaren från att skicka meddelanden. Om ett utgående meddelande bedöms vara skräp post dirigeras de vanligt vis via poolen med högsta risk, vilket minskar sannolikheten för att den vanliga utgående IP-poolen läggs till i en blockeringslistan.

Du kan skicka ett meddelande till en viss e-postadress när en avsändare skickar utgående skräp post. Mer information om den här inställningen finns i [Konfigurera principen för utgående skräp post](configure-the-outbound-spam-policy.md).

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan jag använda en tredjeparts leverantör för skräp post och skydd mot skadlig kod tillsammans med Exchange Online?

Ja. Även om vi rekommenderar att du pekar din MX-post till Microsoft inser vi att det finns legitima affärs skäl för att dirigera din e-post till annan plats än Microsoft först.

- **Inkommande** : ändra dina MX-poster så att de pekar på tredjepartsleverantörer och dirigera sedan om dem till EOP för ytterligare bearbetning. Mer information finns i [förbättrade filter för kopplingar i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Utgående** : konfigurera routning för smarta värden från Microsoft 365 till den mottagande tredje partens leverantör.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Har Microsoft någon dokumentation om hur jag kan skydda mig från nätfiske-bedrägerier?

Ja. Mer information finns i [skydda din integritet på Internet](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Kontrol leras skräp post och meddelanden om skadlig kod som skickas till dem som skickade dem eller överförs till juridiska enheter?

Tjänsten fokuserar på identifiering och borttagning av skräp post och skadlig program vara, men vi kan emellanåt undersöka särskilt farliga eller skadliga skräp post-eller angrepps kampanjer och perpetrators. Detta kan vara att arbeta med våra juridiska och digitala brottslighet enheter för att ta bort skräp post botnet, blockering av skräp post från att använda tjänsten (om de använder den för att skicka utgående e-post) och överföra informationen om att efterleva straffrättsliga påföljder.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Vilka är de bästa metoderna för utgående e-post för att se till att min e-post levereras?

Rikt linjerna nedan är tips för att skicka utgående e-postmeddelanden.

- **Käll-e-postdomänen bör kunna matchas i DNS.**

  Om avsändaren är user@fabrikam är domänen fabrikam matcha till IP-adress 192.0.43.10.
  
  Om en sändande domän saknar en-post och ingen MX-post i DNS dirigeras meddelandet via den högre risk leveransen oavsett om innehållet i meddelandet är skräp post. Mer information om poolen med högre risk leverans finns i [poolen för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md).

- **Eserver för utgående e-post ska ha en omvänd DNS-post (PTR).**

  Om till exempel e-postkällans IP-adress är 192.0.43.10 är omvänd DNS-post `43-10.any.icann.org` ".

- **Kommandona HELO/EHLO och e-post från bör vara konsekventa och finnas i samma form som ett domän namn i stället för en IP-adress.**

  Kommandot HELO/EHLO bör konfigureras så att det stämmer överens med omvänd DNS för den sändande IP-adressen så att domänen förblir likadan i olika delar av meddelande rubrikerna.

- **Kontrol lera att rätt SPF-poster är inställda i DNS.**

  SPF-poster är en mekanism för att verifiera att e-post som skickas från en domän verkligen kommer från den domänen och inte är falsk. Mer information om SPF-poster finns i följande länkar:

  [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Vanliga frågor och svar om domäner](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Signerar e-post med DKIM, tecken med avslappnad kanonare.**

  Om en avsändare vill signera sina meddelanden med domän nycklar som identifieras via e-post (DKIM) och de vill skicka utgående e-post via tjänsten, ska de signera med den avslappnade-algoritmen för mellanliggande huvud. Om du loggar med strikt huvudauktorisering för huvuden kan signaturen bli verifierad när den passerar via tjänsten.

- **Domän ägare bör ha korrekt information i WHOIS-databasen.**

  Då identifieras domänernas ägare och hur du kontaktar dem genom att ange det stabila moder bolaget, kontakt punkten och namnservrarna.

- **För olika e-postprogram ska alternativet från: namnet på den som skickar meddelandet visas, medan ämnes raden i meddelandet bör vara en kort sammanfattning av vad meddelandet rör sig om.**

  Meddelande texten bör ha en tydlig indikation på erbjudandet, tjänsten eller produkten. Om till exempel en avsändare skickar ett Mass utskick för företaget contoso ser du följande för e-post från och ämne:

  > Från: marketing@contoso.com <br/> Ämne: ny uppdaterad katalog för jul säsongen!

  Här följer ett exempel på vad du inte kan göra eftersom det inte är beskrivande:

  > Från: user@hotmail.com <br/> Ämne: kataloger

- **Om du skickar ett Mass utskick till många mottagare och meddelandet är i nyhets brevs format, bör det finnas ett sätt att avsluta prenumerationen längst ned i meddelandet.**

  Alternativet avabonnera bör se ut så här:

  > Detta meddelande skickades till example@contoso.com av sender@fabrikam.com. Uppdatera profil/e-postadress | Snabb borttagning med **SafeUnsubscribe** &trade; | Integritets policy

- **Om du skickar Mass utskick av e-post ska du göra det med dubbel deltagande. Om du är en Mass utskick är dubbel deltagande en bransch metod.**

  Dubbel opt-in är det bästa är att kräva att en användare ska kunna registrera sig för marknadsföring via e-post:

  1. När användaren klickar på en tidigare avmarkerad kryss ruta där de väljer att få ytterligare erbjudanden eller e-postmeddelanden från marknaden.

  2. En andra gång när marknadsaren skickar en bekräftelse via e-post till användarens e-postadress som ber dem klicka på en tids känslig länk som ska bekräftas.

  Om du använder dubbelt så skapas ett bra rykte för Mass utskick av e-post.

- **Mass avsändare bör skapa transparent innehåll för vilka de kan bevaras i sin egen räkning:**

  1. Verbiage begär att mottagarna lägger till avsändaren i adress boken tydligt om att sådan åtgärd inte är en garanti för leverans.

  2. När du skapar omdirigeringar i meddelandets brödtext kan du använda ett enhetligt länk format.

  3. Skicka inte stora bilder eller bifogade filer eller meddelanden som bara består av en bild.

  4. När du anställer spårnings pixlar (webb programs-eller beacons) kan du tydligt uppge deras närvaro i dina offentliga integritets-eller P3P-inställningar.

- **Formatera utgående studs meddelanden.**

  När aviserings meddelanden om leverans status genereras (kallas även för rapporter, NDR eller studsade meddelanden) ska avsändarna följa formatet för ett studs enligt vad som anges i [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Ta bort studsade e-postadresser för ej existerande användare.**

  Om du får ett meddelande om att en e-postadress inte längre används tar du bort det icke befintliga e-postaliaset från listan. E-postadresserna ändras med tiden och andra ignorerar dem.

- **Använd Hotmail-programmet Smart Network Data Services (SNDS).**

  I Hotmail används ett program som heter smarta nätverks data tjänster som gör att avsändare kan kontrol lera klagomål som lämnats av slutanvändare. SNDS är den primära portalen för att felsöka leverans problem till hotmail.
