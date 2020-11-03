---
title: Skydd mot skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om inställningar och filter mot skräp post för att förhindra skräp post i Exchange Online Protection (EOP).
ms.openlocfilehash: 9a11337e5b9eff1f77d5711fb4cda2a13bdaed24
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844410"
---
# <a name="anti-spam-protection-in-eop"></a>Skydd mot skräp post i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Det här avsnittet är avsett för administratörer. Information om slutanvändare finns i [Översikt över skräp post filtret](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) och [Lär dig mer om skräp post och nätfiske](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor skyddas e-postmeddelanden automatiskt mot spam (skräp post) av EOP.

Microsofts e-postsäkerhets plan omfattar en oöverträffad kors produkt metod. EOP anti-spam och anti-nätfiske-teknik tillämpas på våra e-postplattformar för att förse användarna med de senaste anti-spam-och nät fiske verktygen och nyheterna i hela nätverket. Målet för EOP är att tillhandahålla en omfattande och användbar e-posttjänst som hjälper dig att upptäcka och skydda användare från skräp post, bedrägliga e-posthot (nätfiske) och skadlig program vara.

Eftersom e-postanvändning har vuxit, så har e-POSTMISSBRUK. Du kan täppa igen inkorgar och nätverk, påverka användarnas tillfredsställelse och försvåra den legitima e-postkommunikationens effektivitet. Därför fortsätter Microsoft att investera i reklam teknologi. Det är bara att lägga till och filtrera skräp post.

> [!TIP]
> Följande skydd mot skräp post är användbart när du vill tillåta eller blockera meddelanden baserat på meddelandets kuvert (till exempel avsändarens domän eller Källans IP-adress). Om du vill tillåta eller blockera meddelanden baserat på nytto Last (till exempel URL: er i meddelandet eller bifogade filer) bör du använda [portalen Tillåt/blockera lista](tenant-allow-block-list.md).

## <a name="anti-spam-technologies-in-eop"></a>Skydd mot skräp post i EOP

För att minska skräp posten inkluderar EOP skräp post skydd som använder patentskyddad skräp filtrerings teknik för att identifiera och avgränsa skräp post från legitim e-post. EOP spam tar dig från kända hot för skräp post och nätfiske och feedback från vår konsument plattform, Outlook.com. Med pågående feedback från EOP användare i program varan för skräp post ser du till att EOP-teknikerna är ständigt utbildade och bättre.

Inställningarna för skydd mot skräp post i EOP består av följande tekniker:

- **Anslutnings filtrering** : identifierar bra och dåliga e-postdatakälla i det inkommande e-postmeddelandet via listan med IP-adresser, IP-adressblock och den *säkra listan* (en dynamisk, icke redigerbar lista över betrodda avsändare som hanteras av Microsoft). Du konfigurerar de här inställningarna i anslutnings filter principen. Läs mer i [Konfigurera anslutnings filtrering](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Förfalsknings intelligens använder anslutnings filtrering för att skapa tillåta och blockera avsändare som har falskats för e-postdomänen. Mer information finns i [Läs mer om förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).

- **Skräp post filtrering (innehålls filtrering)** : EOP använder skräp post filtret verdicts **skräp** post, **snabb** meddelanden, **Mass** utskick via e-post, **nät fiske** och **högsäker nät fiske** . Du kan konfigurera åtgärderna så att de utförs utifrån dessa verdicts och du kan konfigurera alternativen för slutanvändare för meddelanden som satts i karantän i stället för att levereras. Mer information finns i [Konfigurera principer för skräp post skydd i Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Standardinställningen är att skräp post filtrering är konfigurerad för att skicka meddelanden som har marker ATS som skräp post till mottagarens mapp för skräp post. I hybrid miljöer där EOP skyddar lokala Exchange-postlådor måste du emellertid konfigurera två regler för e-postflöde (kallas även transport regler) i den lokala Exchange-organisationen för att känna igen de EOP som läggs till i meddelandet. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Utgående skräp post filtrering** : EOP kontrollerar också att användarna inte skickar skräp post, antingen i utgående meddelande innehåll eller genom att överskrida gräns för utgående meddelanden. Mer information finns i [Konfigurera utgående spam i Microsoft 365](configure-the-outbound-spam-policy.md).

- **Förfalsknings intelligens** : Mer information finns i [Läs mer om falsk intelligens i Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Hantera fel i skräp post filtrering

Det är möjligt att bra meddelanden kan identifieras som skräp post (kallas även falska positiva) eller att skräp posten kan skickas till Inkorgen. Du kan använda förslagen i följande avsnitt för att ta reda på vad som hände och hjälpa till att förhindra att det sker i framtiden.

Här är några rekommendationer som gäller för scenariot:

- Skicka alltid underklassificerade meddelanden till Microsoft. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Undersök meddelande rubrikerna** : de här värdena talar om för dig varför ett meddelande har marker ATS som skräp post, eller varför skräp post filtret hoppades över. Mer information finns i [meddelande rubriker med skräp post](anti-spam-message-headers.md).

- **Peka på din MX-post till microsoft 365** : för att EOP ska kunna ge bästa möjliga skydd rekommenderar vi alltid att du har e-post som skickas till Microsoft 365 först. Instruktioner finns i [Skapa DNS-poster hos en DNS-värd för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Om MX-posten pekar på någon annan plats (till exempel en lösning eller utrustning från tredje part) är det svårt för EOP att ge korrekt skräp post filtrering. I det här scenariot måste du konfigurera utökad filtrering för kopplingar (kallas även för att _hoppa över listningar_ ). Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Använd e-postauktorisering** : om du äger en e-postdomän kan du använda DNS för att vara säker på att meddelanden från avsändare i domänen är giltiga. För att förhindra skräp post och oönskade förfalskningar i EOP kan du använda följande metoder för e-postautentiseringsmetoder:

  - **SPF** : policy för avsändaren verifierar meddelandets käll-IP-adress mot ägaren till den sändande domänen. En snabb introduktion till SPF och att få det konfigurerat snabbt finns i [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md). För att få en djupare förståelse av hur Microsoft 365 använder SPF, eller om du vill felsöka eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa artikeln om [hur Microsoft 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM** : DomainKeys identifieras en digital signatur i meddelande huvudet för meddelanden som skickas från din domän. Mer information finns i [använda DKIM för att verifiera utgående e-post som skickas från din egen domän i Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC** : domänbaserad meddelande-, rapporterings-och prosvars plats hjälper mål-e-postsystem att avgöra vad som ska göras med meddelanden som inte är SPF-eller DKIM-kontroller och ger dig en annan förtroende nivå för dina e-postpartner. Mer information finns i [använda DMARC för att verifiera e-post i Microsoft 365](use-dmarc-to-validate-email.md).

- **Kontrol lera dina e-postinställningar** : tröskelvärdet för Mass kompatibel nivå (BCL) som du konfigurerar i principer för skräp post styr om Mass utskick av e-post (kallas även för _grått_ ) har marker ATS som skräp post. Den PowerShell-Only-inställningen _MarkAsSpamBulkMail_ som standard ger också resultaten. Mer information finns i [Konfigurera principer för skräp post skydd i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Förhindra leverans av skräp post till Inkorgen

- **Kontrol lera organisationens inställningar** : se för inställningar som gör att meddelanden kan hoppa över skräp post (om du till exempel lägger till din egen domän i listan över tillåtna domäner i principer för skräp post). För våra rekommenderade inställningar, se [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md) och [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md).

- **Kontrol lera att skräp post regeln är aktive rad i användarens post låda** : den är aktive rad som standard, men om den är inaktive rad kan meddelanden som är markerade som skräp post inte flyttas till mappen skräp post. Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Använd tillgängliga spärrade avsändare listor** : Mer information finns i [skapa spärrade avsändare](create-block-sender-lists-in-office-365.md).

- **Avabonnera från Mass utskick** Om meddelandet var något som användaren registrerade sig för (nyhets brev, produkt meddelanden, etc.) och innehåller en prenumerations länk från en tillförlitlig källa kan du be dem att helt enkelt avsluta prenumerationen.

- **Fristående EOP: skapa regler för e-postflöden i det lokala Exchange för EOP spam filter verdicts** : i fristående EOP miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödes regler (kallas även transport regler) i lokalt Exchange för att översätta EOP spam filter Verdict så att skräp post filtret kan flytta meddelandet till mappen skräp post. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Förhindra att e-post identifieras som skräp post

Här är några steg som du kan vidta för att förhindra falska positiva aktiviteter:

- **Kontrol lera inställningarna för skräp post filtret i Outlook** :

  - **Kontrol lera att skräp post filtret i Outlook är inaktiverat** : när skräp post filtret för Outlook är inställt på standardvärdet **ingen automatisk filtrering görs inget** försök att klassificera massages som skräp post.  När det är inställt på **lågt** eller **högt** använder skräp post filtret i Outlook sin egen SmartScreen-filter teknik för att identifiera och flytta skräp posten till mappen skräp post så att du får falsk positiv användning. Observera att Microsoft slutade att skapa uppdateringar för skräp post definitioner för SmartScreen-filtren i Exchange och Outlook i november 2016. De befintliga skräp post definitionerna för SmartScreen slutade på plats, men deras effektivitet kommer sannolikt att påverka tiden.

  - **Kontrol lera att Outlook-inställningen för endast säkra listor är inaktive rad** : när den här inställningen är aktive rad levereras endast meddelanden från avsändare i listan med betrodda avsändare eller betrodda mottagare. e-post från alla andra flyttas automatiskt till mappen skräp post.

  Mer information om dessa inställningar finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Använd tillgängliga listor med säkra avsändare** : Mer information finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md).

- **Verifiera att användarna ligger inom gränserna för sändning och mottagning** enligt beskrivningen i avsnittet om [mottagning och sändning](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) i tjänst beskrivningen för Exchange Online.

- **Fristående EOP: använda katalog-synkronisering** : om du använder fristående EOP för att skydda din lokala Exchange-organisation, bör du synkronisera användar inställningar med tjänsten genom att använda katalog-synkronisering. Detta garanterar att användarnas listor med betrodda avsändare följs av EOP. Mer information finns i [använda katalog-synkronisering för att hantera e-postanvändare](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Lagstiftning mot skräp post

På Microsoft anser vi att utvecklingen av ny teknik och egen regel kräver stöd för effektiv myndighets politik och rättsliga ramar. Den världs omfattande skräp posten har Spurred flera olika lagstiftnings organ för att reglera kommersiell e-post. Många länder har nu direkt skydd mot skräp post. Amerikas förenta stater har både federala och delstatliga lagar för skräp post, och denna kompletterande metod hjälper till att förhindra skräp post när du aktiverar legitim e-handelsprosper. Med funktionen för att skräp post ska fungera utökas de verktyg som finns tillgängliga för bedrägliga och bedrägliga e-postmeddelanden.
