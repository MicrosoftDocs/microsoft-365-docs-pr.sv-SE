---
title: Vanliga frågor om skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Det här avsnittet innehåller vanliga frågor och svar om skydd mot skräppost. Svar gäller för EOP-kunder (Microsoft Exchange Online and Exchange Online Protection).
ms.openlocfilehash: 9be51b4967a558aec254262052d7c01446a7d643
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810744"
---
# <a name="anti-spam-protection-faq"></a>Vanliga frågor om skydd mot skräppost

Det här avsnittet innehåller vanliga frågor och svar om skydd mot skräppost. Svar gäller för EOP-kunder (Microsoft Exchange Online and Exchange Online Protection).

> [!TIP]
> För frågor och svar om betroddavsändare och blockerade avsändarlistor finns i [Betrodd avsändare och blockerade avsändarlistor i Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). Frågor och svar om karantänen finns i [Vanliga frågor om karantän](quarantine-faq.md).

 **F. Som standard, vad händer med ett meddelande som upptäckts av skräppost?**

A. **För inkommande meddelanden:** Majoriteten av skräpposten raderas via anslutningsfiltrering, som baseras på avsändarens IP-adress. Tjänsten granskar sedan innehållet i meddelandet. Som standard skickas skräppost som standard till mottagarens skräppostmapp. Du kan ändra den här åtgärden. Du kan till exempel välja att skicka skräppost till karantänen i stället genom att konfigurera innehållsfilterprincipen.

> [!IMPORTANT]
> För EOP-fristående kunder: För att säkerställa att åtgärden **Flytta meddelande till skräppostmapp** fungerar med lokala postlådor måste du konfigurera två Exchange-flödesregler för e-post (kallas även transportregler) på dina lokala servrar för att identifiera skräppostrubriker som lagts till av EOP. Mer information finns i [Se till att skräppost dirigeras till varje användares skräppostmapp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **För utgående meddelanden:** Meddelandet dirigeras antingen genom leveranspoolen för högre risk eller studsas och inte levereras, i vilket fall avsändaren ska få ett meddelande om leveransstatus (DSN) som talar om för dem att meddelandet inte kunde levereras.

 **F. Vad är en nolldagars skräppostvariant och hur hanteras den av tjänsten?**

A. En nolldagars skräppostvariant är en första generationens, tidigare okänd variant av skräppost som aldrig har fångats eller analyserats, så våra skräppostfilter har ännu ingen information tillgänglig för att upptäcka den. Efter en noll-dagars spam prov fångas och analyseras av våra spam analytiker, om den uppfyller kriterierna spam klassificering, våra spam innehåll filter uppdateras för att upptäcka det, och det är inte längre betraktas som "noll-dag." **(Obs:** Om du får ett meddelande som kan vara en noll dagars skräppostvariant, för att hjälpa oss att förbättra tjänsten, skicka meddelandet till Microsoft med hjälp av en av de metoder som beskrivs i [Skicka skräppost, icke-spam och phishing bluff meddelanden till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)

 **F. Måste jag konfigurera tjänsten för att ge skydd mot skräppost?**

A. När du har registrerat dig för tjänsten och lagt till din domän aktiveras skräppostfiltrering automatiskt hela företaget genom standardpolicyerna för skräppost. Standardprinciperna är inställda för att skydda dig utan att behöva någon ytterligare konfiguration (bortsett från det undantag som anges ovan för EOP fristående kunder). Som administratör kan du redigera standardpolicyerna för skräppost så att de är anpassade för att på bästa sätt uppfylla organisationens behov. För större granularitet kan du också skapa anpassade innehållsfilterprinciper och använda dem på angivna användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (d.v.s. körordningen) för dina anpassade principer.

Mer information om hur du konfigurerar dina anti-spam-policyer finns i följande avsnitt:

[Konfigurera principen för anslutningsfilter](configure-the-connection-filter-policy.md)

[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)

[Konfigurera den utgående skräppostprincipen](configure-the-outbound-spam-policy.md)

 **F. Om jag gör en ändring av en anti-spam politik, hur lång tid tar det när jag sparar mina ändringar för dem att träda i kraft?**

A. Det kan ta upp till 1 timme innan ändringarna börjar gälla.

 **F. Är massfiltrering av e-post automatiskt aktiverat?**

A. Som standard är alternativet Avancerad skräppostfiltrering för **massutskick** av skräppost aktiverat för nya kunder. För migrerade kunder matchar den här inställningen FOPE-konfigurationen. Mer information om masse-e-post finns i [Vad är skillnaden mellan skräppost och masse-e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)

 **F. Tillhandahåller tjänsten URL-filtrering?**

A. Ja tjänsten har ett URL-filter som söker efter webbadresser i meddelanden. Om webbadresser som är associerade med känt skräppost eller skadligt innehåll upptäcks markeras meddelandet som skräppost.

 **F. Hur kan kunder som använder tjänsten skicka falska negativa meddelanden (skräppost) och falska positiva (icke-skräppost) meddelanden till Microsoft?**

A. Skräppost meddelanden och icke-skräppost meddelanden kan skickas till Microsoft för analys på flera sätt. Mer information finns i [Skicka meddelanden om skräppost, icke-skräppost och nätfisketill Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

 **F. Kan jag få skräppostrapporter?**

A. Ja, till exempel kan du få en rapport om identifiering av skräppost i administrationscentret för Microsoft 365. Den här rapporten visar skräppostvolymen som ett antal unika meddelanden. Mer information om rapportering finns i följande länkar:

Exchange Online-kunder: [Övervakning, rapportering och meddelandespårning i Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Exchange Online Protection kunder: [Rapportering och meddelande spårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

 **F. Någon skickade mig ett meddelande och jag kan inte hitta det. Jag misstänker att det kan ha upptäckts som spam. Finns det något verktyg som jag kan använda för att ta reda på?**

A. Ja, med meddelandespårningsverktyget kan du följa e-postmeddelanden när de passerar genom tjänsten, för att ta reda på vad som hände med dem. Mer information om hur du använder meddelandespårningsverktyget för att ta reda på varför ett meddelande har markerats som skräppost finns i [Har ett meddelande markerat som skräppost?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

 **F. Kommer tjänsten att begränsa (hastighetsgräns) min e-post om mina användare skickar utgående skräppost?**

A. Om mer än hälften av e-postmeddelandet som skickas från en användare via tjänsten inom en viss tidsram (till exempel per timme) bedöms vara skräppost av Office 365, blockeras användaren från att skicka meddelanden. I de flesta fall, om ett utgående meddelande bedöms vara skräppost, dirigeras det genom högriskleveranspoolen, vilket minskar sannolikheten för att den normala utgående IP-poolen läggs till i en blockeringslista.

Du kan skicka ett meddelande till en angiven e-postadress när en avsändare blockeras skicka utgående skräppost. Mer information om den här inställningen finns i [Konfigurera den utgående skräppostprincipen](configure-the-outbound-spam-policy.md).

 **F. Kan jag använda en tredjepartsleverantör mot skräppost och skadlig kod i samband med Exchange Online?**

A. Ja, du kan konfigurera en annan filtreringstjänst för skräppost och skadlig kod för att skydda dina Exchange Online-postlådor. Om du vill göra detta för inkommande e-post bör du omdirigera dina e-postmeddelanden till tredjepartsleverantören genom att ändra MX-posterna så att de pekar på tredjepartsleverantören och sedan omdirigera meddelandena till EOP för ytterligare bearbetning. För att göra detta för utgående e-post, konfigurera leveransmålet för meddelandet till tredjepartsleverantören (smart värd).

 **F. Har Microsoft någon dokumentation om hur jag kan skydda mig från nätfiskebedrägerier?**

A. Ja det gör vi, läs [Skydda din integritet på internet](https://support.microsoft.com/help/4091455)

 **F. Utreds skräppost och malware-meddelanden om vem som skickade dem eller överförs till brottsbekämpande enheter?**

A. Tjänsten fokuserar på identifiering och borttagning av skräppost och skadlig kod, även om vi ibland kan undersöka särskilt farliga eller skadliga spam- eller attackkampanjer och förfölja förövarna. Detta kan innebära att arbeta med våra juridiska och digitala enheter brottslighet för att ta ner en spammare botnet, blockerar spammare från att använda tjänsten (om de använder den för att skicka utgående e-post), och vidarebefordra information till brottsbekämpning för åtal.

 **F. Vilka är en uppsättning bästa utgående utskicksmetoder som säkerställer att min e-post levereras?**

A. Riktlinjerna nedan är metodtips för att skicka utgående e-postmeddelanden.

1. **Skicka domänen för e-postmeddelandet ska lösa i DNS.**

    Om avsändaren till exempel user@example.com, example.com domänen till IP-adressen 192.0.43.10. Om en sändningsdomän inte har någon A-post och ingen MX-post i DNS dirigeras meddelandet via dess leveranspool med högre risk oavsett om innehållet i meddelandet är skräppost eller inte. Mer information om leveranspoolen med högre risk finns i [Leveranspool med hög risk för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md).

2. **Den sändande IP-adressen för den utgående e-postservern bör ha en omvänd DNS-post (PTR).**

    Om du till exempel skickar från IP-adressen 192.0.43.10, är den omvända DNS-posten för den här IP:en 43-10.any.icann.org.

3. **Helo/EHLO- och MAIL FROM-kommandona ska vara konsekventa och finnas i form av ett domännamn i stället för en IP-adress.**

    Kommandot HELO/EHLO bör konfigureras så att det matchar den omvända DNS:en för den sändande IP-adressen så att domänen förblir densamma i de olika delarna av meddelanderubrikerna.

4. **Kontrollera att rätt SPF-poster ställs in i DNS.**

    SPF-poster är en mekanism för att validera att e-post som skickas från en domän verkligen kommer från den domänen och är inte förfalskad. Mer information om SPF-poster finns i följande länkar:

    [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

    [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

5. **Signera e-post med DKIM, skriv under med avslappnad kanonikalisering.**

    Om en avsändare vill signera sina meddelanden med Hjälp av DKIM (Domain Keys Identified Mail) och de vill skicka utgående e-post via tjänsten, bör de signera med hjälp av algoritmen för avslappnad kanonisering av huvudet. Signering med strikt kanoniicalisering av huvudet kan ogiltigförklara signaturen när den passerar genom tjänsten.

6. **Domänägare bör ha korrekt information i WHOIS-databasen.**

    Detta identifierar domänens ägare och hur du kontaktar dem genom att ange det stabila moderbolaget, kontaktpunkten och namnservrarna.

7. **För massutskick bör namnet Från: återspegla vem som skickar meddelandet, medan meddelandets ämnesrad bör vara en kort sammanfattning av vad meddelandet handlar om.**

    Meddelandetexten bör ha en tydlig indikation på erbjudandet, tjänsten eller produkten. Om en avsändare till exempel skickar ut ett massutskick för Contoso-företaget, är följande vad e-postmeddelandet från och angående ska likna:

    Från: marketing@contoso.com

    Ämne: Ny uppdaterad katalog för julen!

    Följande är ett exempel på vad man inte ska göra eftersom det inte är beskrivande:

    Från: user@hotmail.com

    Ämne: Kataloger

8. **Om du skickar ett massutskick till många mottagare och meddelandet är i nyhetsbrevsformat bör det finnas ett sätt att avregistrera sig längst ned i meddelandet.**

    Alternativet för avregistrerande bör likna följande:

    Det här meddelandet skickades till example@contoso.com av sender@fabrikam.com. Uppdatera profil/e-postadress | Omedelbar borttagning med **SafeUnsubscribe**™ | Sekretesspolicy

9. **Om du skickar masse-e-post ska listförvärvet utföras med dubbel opt-in. Om du är en bulk mailer, dubbel opt-in är en bransch bästa praxis.**

    Dubbel opt-in är praxis att kräva en användare att vidta två åtgärder för att registrera dig för marknadsföring e-post:

   1. En gång när användaren klickar på en tidigare avmarkerad kryssruta där de väljer att ta emot ytterligare erbjudanden eller e-postmeddelanden från marknadsföraren.

   2. En andra gång när marknadsföraren skickar en bekräftelse via e-post till användarens angivna e-postadress och ber dem att klicka på en tidskänslig länk som kommer att slutföra sin bekräftelse.

      Använda dubbla opt-in bygger ett gott rykte för bulk e-avsändare.

10. **Bulk avsändare bör skapa transparent innehåll som de kan hållas ansvariga:**

    1. Verbiage begär att mottagarna lägger till avsändaren i adressboken bör tydligt ange att en sådan åtgärd inte är en garanti för leverans.

    2. När du skapar omdirigeringar i meddelandets brödtext använder du ett konsekvent länkformat.

    3. Skicka inte stora bilder eller bilagor eller meddelanden som enbart består av en bild.

    4. När du använder spårningspixlar (webbbuggar eller beacons) anger tydligt deras närvaro i dina allmänna sekretess- eller P3P-inställningar.

11. **Formatera utgående leveransstatusmeddelanden.**

    När du genererar meddelanden om leveransstatus bör avsändare följa formatet på en studs enligt vad som anges i [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

12. **Ta bort avvisade e-postadresser för användare som inte finns.**

    Om du får en NDR som anger att en e-postadress inte längre används tar du bort det obefintliga e-postaliast från listan. E-postadresser ändras med tiden och andra ignorerar dem ibland.

13. **Använd Hotmails SNDS-program (Smart Network Data Services).**

    Hotmail använder ett program som heter Smart Network Data Services som gör det möjligt för avsändare att kontrollera klagomål som lämnas in av slutanvändare. SNDS är den primära portalen för felsökning av leveransproblem till Hotmail.

## <a name="for-more-information"></a>Mer information

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Betrodd avsändare och blockerade avsändarlistor i Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

[Rubriker för skräppostmeddelanden](anti-spam-message-headers.md)

[Meddelanden på grund av bakåtspridning och EOP](backscatter-messages-and-eop.md)
