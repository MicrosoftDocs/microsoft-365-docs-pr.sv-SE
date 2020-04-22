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
description: Lär dig mer om inställningarna och filtren mot skräppost som hjälper dig att förhindra skräppost i Exchange Online och Microsoft 365. Får du för mycket skräppost i Microsoft 365? Du kan anpassa dina skräppostfilter och inställningar för skräppost.
ms.openlocfilehash: d7c7a0166fbcbf3334325aeef153f2d82f27aac3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636052"
---
# <a name="anti-spam-protection-in-microsoft-365"></a>Skydd mot skräppost i Microsoft 365

> [!NOTE]
> Det här avsnittet är avsett för Microsoft 365-administratörer. För slutanvändaravsnitt finns [i Översikt över skräppostfiltret](https://support.Microsoft.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) och lär dig mer om skräppost och [nätfiske](https://support.Microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

Om du är en Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection -kund (EOP) utan Exchange Online-postlådor skyddas dina e-postmeddelanden automatiskt mot skräppost (skräppost) av EOP.

Microsofts färdplan för e-postsäkerhet innebär en oöverträffad produktövergripande metod. EOP:s anti-spam- och anti-phishing-teknik tillämpas på våra e-postplattformar för att ge användarna de senaste anti-spam- och anti-phishing-verktygen och innovationerna i hela nätverket. Målet för EOP är att erbjuda en omfattande och användbar e-posttjänst som hjälper till att upptäcka och skydda användare från skräppost, bedrägliga e-posthot (nätfiske) och skadlig kod.

Som e-postanvändning har ökat, så har e missbruk. Oövervakad skräppost kan täppa till inkorgar och nätverk, påverka användarnas tillfredsställelse och hindra effektiviteten i legitim e-postkommunikation. Det är därför Microsoft fortsätter att investera i anti-spam-teknik. Enkelt uttryckt, det börjar med att innehålla och filtrera skräppost.

## <a name="anti-spam-technologies-in-eop"></a>Anti-spam-teknik i EOP

För att minska skräpposten innehåller EOP skräppostskydd som använder proprietär skräppostfiltreringsteknik för att identifiera och separera skräppost från legitim e-post. EOP-skräppostfiltrering lär sig av kända skräppost- och nätfiskehot och användarfeedback från vår konsumentplattform, Outlook.com. Pågående feedback från EOP-användare i skräppostklassificeringsprogrammet hjälper till att säkerställa att EOP-teknikerna tränas och förbättras kontinuerligt.

Anti-spam-inställningarna i EOP är gjorda av följande tekniker:

- **Anslutningsfiltrering:** Identifierar bra och dåliga e-postkällservrar tidigt i den inkommande e-postanslutningen via IP Allow List, IP Block List och den *säkra listan* (en dynamisk men icke-redigerbar lista över betrodda avsändare som underhålls av Microsoft). Du konfigurerar dessa inställningar i anslutningsfilterprincipen. Läs mer vid [Konfigurera anslutningsfiltrering i Microsoft 365](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Spoof intelligence använder anslutningsfiltrering för att skapa tillåta och blockera listor över avsändare som förfalskar din e-postdomän. Mer information finns [i Läs mer om falska underrättelser i Microsoft 365](learn-about-spoof-intelligence.md).

- **Skräppostfiltrering (innehållsfiltrering)**: EOP använder spamfiltreringsutslag **Skräppost,** Skräppost med **högt förtroende,** **Massmeddelande,** **Nätfiske e-post** och **nätfiske-e-post med högt förtroende** för att klassificera meddelanden. Du kan konfigurera åtgärderna som ska vidtas baserat på dessa domar och du kan konfigurera meddelandealternativen för slutanvändare för meddelanden som har satts i karantän i stället för levererade. Mer information finns [i Konfigurera principer mot skräppost i Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Som standard är skräppostfiltrering konfigurerad för att skicka meddelanden som har markerats som skräppost till mottagarens skräppostmapp. I hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera två regler för e-postflöde (kallas även transportregler) i din lokala Exchange-organisation för att känna igen EOP-skräppostrubrikerna som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Skräppostfiltrering:** EOP kontrollerar också att användarna inte skickar skräppost, antingen i utgående meddelandeinnehåll eller genom att överskrida gränser för utgående meddelanden. Mer information finns [i Konfigurera skräppostfiltrering i Microsoft 365](configure-the-outbound-spam-policy.md).

- **Falska uppgifter**: Mer information finns i [Läs mer om falska underrättelser i Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Hantera fel i skräppostfiltrering

Det är möjligt att bra meddelanden kan identifieras som skräppost (kallas även falska positiva) eller att skräppost kan levereras till Inkorgen. Du kan använda förslagen i följande avsnitt för att ta reda på vad som hände och förhindra att det händer i framtiden.

Här är några metodtips som gäller för båda scenarierna:

- Skicka alltid felklassificerade meddelanden till Microsoft. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Undersök rubrikerna mot skräppost:** Dessa värden kommer att berätta varför ett meddelande har markerats som skräppost, eller varför det hoppade över skräppostfiltrering. Mer information finns i [Rubriker för skräppostmeddelande](anti-spam-message-headers.md).

- **Rikta din MX-post till Microsoft 365:** För att EOP ska kunna ge det bästa skyddet rekommenderar vi alltid att du har e-post levererat till Microsoft 365 först. Instruktioner finns i [Skapa DNS-poster hos alla DNS-värdar för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Om MX-posten pekar på någon annan plats (till exempel en tredje parts anti-spam-lösning eller apparat) är det svårt för EOP att tillhandahålla korrekt skräppostfiltrering. I det här fallet måste du konfigurera utökad filtrering för kopplingar (kallas även _hoppa över notering_). Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Använd e-postautentisering**: Om du äger en e-postdomän kan du använda DNS för att försäkra att meddelanden från avsändare i den domänen är legitima. Använd alla följande metoder för e-postautentisering för att förhindra skräppost och oönskad förfalskning i EOP:

  - **SPF**: Avsändarprincipram verifierar meddelandets käll-IP-adress mot ägaren till den sändande domänen. En snabb introduktion till SPF och snabbt konfigurera den finns i [Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Om du vill ha en mer djupgående förståelse för hur Microsoft 365 använder SPF, eller för felsökning eller icke-standarddistributioner som hybriddistributioner, börjar du med [Hur Microsoft 365 använder Sender Policy Framework (SPF) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail lägger till en digital signatur i meddelandehuvudet för meddelanden som skickas från domänen. Information finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: Domänbaserad meddelandeautentisering, rapportering och konformance hjälper målej.e-postsystem att avgöra vad du ska göra med meddelanden som misslyckas med SPF- eller DKIM-kontroller och ger en annan förtroendenivå för dina e-postpartner. Mer information finns i [Använda DMARC för att validera e-post i Microsoft 365](use-dmarc-to-validate-email.md).

- **Kontrollera dina massinställningar för e-post**: Tröskelvärdet för masskompatibla nivåer (BCL) som du konfigurerar i anti-spam-principer avgör om massutskick av e-post (kallas även _grå e-post)_ är markerat som skräppost. PowerShell-inställningen _MarkAsSpamBulkMail_ som som standard bidrar också till resultatet. Mer information finns [i Konfigurera principer mot skräppost i Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Förhindra leverans av skräppost till Inkorgen

- **Verifiera organisationens inställningar**: Se upp för inställningar som gör att meddelanden kan hoppa över skräppostfiltrering (till exempel om du lägger till din egen domän i listan över tillåtna domäner i anti-spam-principer). Våra rekommenderade inställningar finns i [Rekommenderade inställningar för EOP och Microsoft 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md) och [Skapa säkra avsändarelistor](create-safe-sender-lists-in-office-365.md).

- **Kontrollera att skräppostregeln är aktiverad i användarens postlåda**: Den är aktiverad som standard, men om det inte är meddelanden som markerats som skräppost kan inte flyttas till mappen Skräppost. Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Använd de tillgängliga spärrade avsändarna:** Mer information finns i [Skapa blockerade avsändarelistor](create-block-sender-lists-in-office-365.md).

- **Avsluta prenumerationen på massutskick av e-post** Om meddelandet var något som användaren registrerat sig för (nyhetsbrev, produktmeddelanden, etc.) och innehåller en avregistreringslänk från en ansedd källa, överväga att be dem att helt enkelt avsluta prenumerationen.

- **Fristående EOP: skapa regler för e-postflöde i lokala Exchange for EOP-skräppostfiltreringsutslag:** I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera regler för e-postflöde (kallas även transportregler) i lokala Exchange för att översätta EOP-skräppostfiltreringsutlåtandet så att skräppostregeln kan flytta meddelandet till skräppostmappen. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Förhindra bra e-post från att identifieras som spam

Här är några steg som du kan vidta för att förhindra falska positiva resultat:

- **Verifiera användarens inställningar för skräppostfilter i Outlook:**

  - **Kontrollera att skräppostfiltret i Outlook är inaktiverat:** När skräppostfiltret i Outlook är inställt på standardvärdet **Ingen automatisk filtrering**försöker Outlook inte klassificera massage som skräppost.  När den är inställd på **Låg** eller **Hög**använder Outlook Junk Email Filter sin egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost, så att du kan få falska positiva identifieringar. Observera att Microsoft slutade producera uppdateringar av skräppostdefinition för SmartScreen-filtren i Exchange och Outlook i november 2016. De befintliga SmartScreen-spamdefinitionerna lämnades på plats, men deras effektivitet kommer sannolikt att försämras med tiden.

  - **Kontrollera att inställningen endast säkra listor i Outlook är inaktiverad**: När den här inställningen är aktiverad levereras endast meddelanden från avsändare i användarens lista över betrodda avsändare eller listan Betrodda mottagare till Inkorgen. e-post från alla andra automatiskt flyttas till mappen Skräppost.

  Mer information om de här inställningarna finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Använd de tillgängliga listorna för betrodda avsändare:** Mer information finns i [Skapa listor över betrodda avsändare](skapa säkra avsändare-listor-i-office-365.md.

- **Kontrollera att användarna befinner sig inom de sändnings- och mottagningsgränser** som beskrivs i [Mottagnings- och sändningsgränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) i exchange online-tjänstbeskrivningen.

- **Fristående EOP: använd katalogsynkronisering**: Om du använder fristående EOP för att skydda din lokala Exchange-organisation bör du synkronisera användarinställningarna med tjänsten med hjälp av katalogsynkronisering. Detta säkerställer att användarnas listor över betrodda avsändare respekteras av EOP. Mer information finns i [Använda katalogsynkronisering för att hantera e-postanvändare](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Lagstiftning mot skräppost

På Microsoft anser vi att utvecklingen av ny teknik och självreglering kräver stöd från effektiv statlig politik och rättsliga ramar. Den världsomspännande spam spridning har sporrat många lagstiftande organ att reglera kommersiella e-post. Många länder har nu lagar om förebyggande av skräppost. USA har både federala och statliga lagar som styr spam, och denna kompletterande strategi hjälper till att begränsa spam samtidigt som legitima e-handel att blomstra. CAN-SPAM Act utökar de verktyg som finns tillgängliga för att stävja bedrägliga och bedrägliga e-postmeddelanden.