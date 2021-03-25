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
description: Administratörer kan läsa mer om inställningarna för skydd mot skräppost och filter som hjälper till att förhindra skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f19330d7af9c4a6601baa9562766eb5a6e7052a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207509"
---
# <a name="anti-spam-protection-in-eop"></a>Skydd mot skräppost i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Det här avsnittet är avsett för administratörer. Mer information om slutanvändare finns i [Översikt över skräppostfiltret och](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) Läs mer om skräppost och [nätfiske.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas e-postmeddelanden automatiskt mot skräppost av EOP.

Microsofts översikt över e-postsäkerhet har en omatchad metod för flera produkter. EOP-teknik mot skräppost och nätfiske används på våra e-postplattformar för att ge användarna de senaste verktygen och innovationerna mot skräppost och nätfiske i hela nätverket. Målet för EOP är att erbjuda en omfattande och användbar e-posttjänst som hjälper till att identifiera och skydda användare från skräppost, bedrägliga e-posthot (nätfiske) och skadlig programvara.

Eftersom e-postanvändningen har vuxit har det även blivit missbruk av e-post. Obevakad skräppost kan täppa igen inkorgar och nätverk, påverka användarnas nöjdhet och effektivisera den legitima e-postkommunikationen. Därför fortsätter Microsoft att investera i teknik mot skräppost. Kort sagt börjar den med att innehålla och filtrera skräppost.

> [!TIP]
> Följande skräppostskyddstekniker är användbara när du vill tillåta eller spärra meddelanden baserat på meddelandekuvertet (till exempel avsändarens domän eller meddelandets käll-IP-adress). Om du vill tillåta eller blockera meddelanden baserat på nyttolast (till exempel URL:er i meddelandet eller de bifogade filerna) bör du använda klientorganisationens portal för att [tillåta/blockera listor.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Teknik mot skräppost i EOP

För att minska skräppost inkluderar EOP skräppostskydd som använder egenutvecklad skräppostfiltreringsteknik för att identifiera och separera skräppost från legitima e-postmeddelanden. EOP-skräppostfiltrering lär sig av kända hot om skräppost och nätfiske samt användarfeedback från vår konsumentplattform, Outlook.com. Löpande feedback från EOP-användare i klassificeringsprogrammet för skräppost bidrar till att EOP-teknikerna får kontinuerlig utbildning och förbättringar.

Inställningarna för skydd mot skräppost i EOP görs av följande tekniker:

- Anslutningsfiltrering: Identifierar bra och dåliga servrar för e-postkällor tidigt i den inkommande e-postanslutningen via listan över tillåtna IP-adresser, IP-blockeringslistan och listan över betrodda avsändare *(en* dynamisk men icke redigerbar lista över betrodda avsändare som underhålls av Microsoft). Du konfigurerar de här inställningarna i principen för anslutningsfilter. Mer information finns i [Konfigurera anslutningsfiltrering](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Förfalskningsinformation använder anslutningsfiltrering för att skapa tillåta- och blockeringslistor med avsändare som kapar din e-postdomän. Mer information finns i [Läs mer om förfalskningsinformation i Microsoft 365.](learn-about-spoof-intelligence.md)

- **Skräppostfiltrering (innehållsfiltrering)**: EOP använder skräppostfiltreringens bedömning  av **skräppost,** hög konfidens för **skräppost,** massutskick,  nätfiske och nätfiske med hög konfidens för att klassificera meddelanden.  Du kan konfigurera åtgärderna som ska vidtas utifrån de här bedömningarna, och du kan konfigurera aviseringsalternativen för slutanvändaren för meddelanden som har satts i karantän i stället för att levereras. Mer information finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > Som standard är skräppostfiltrering konfigurerat för att skicka meddelanden som har markerats som skräppost till mottagarens skräppostmapp. Men i hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera två e-postflödesregler (kallas även transportregler) i den lokala Exchange-organisationen så att de känner igen EOP-skräppostrubrikerna som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Utgående skräppostfiltrering:** EOP kontrollerar också att användarna inte skickar skräppost, antingen i utgående meddelandeinnehåll eller genom att överskrida begränsningar för utgående meddelanden. Mer information finns i Konfigurera [utgående skräppostfiltrering i Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Förfalskningsinformation:** Mer information finns i Läs [mer om förfalskningsinformation i Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Hantera fel i skräppostfiltrering

Det är möjligt att bra meddelanden kan identifieras som skräppost (kallas även falska positiva resultat) eller att skräppost kan levereras till Inkorgen. Du kan använda förslagen i följande avsnitt för att ta reda på vad som har hänt och förhindra att det händer i framtiden.

Här är några metodtips som gäller för något av de olika situationerna:

- Skicka alltid felklassificerade meddelanden till Microsoft. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Undersök rubrikerna för skräppostskydd:** De här värdena talar om varför ett meddelande markerades som skräppost eller varför det hoppade över skräppostfiltrering. Mer information finns i [Rubriker för skräppostmeddelanden.](anti-spam-message-headers.md)

- **Peka MX-posten på Microsoft 365:** För att EOP ska ge bästa skydd rekommenderar vi alltid att du har e-post levererad till Microsoft 365 först. Anvisningar finns i Skapa [DNS-poster på vilken DNS-värd som helst för Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

  Om MX-posten pekar på någon annan plats (till exempel en skräppostskyddslösning eller utrustning från tredje part) är det svårt för EOP att tillhandahålla korrekt skräppostfiltrering. I det här scenariot måste du konfigurera utökad filtrering för kopplingar (kallas även för hoppa _över post)._ Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Använd e-postautentisering:** Om du äger en e-postdomän kan du använda DNS för att säkerställa att meddelanden från avsändare i den domänen är legitima. Använd alla följande e-postautentiseringsmetoder för att förhindra skräppost och oönskad förfalskning i EOP:

  - **SPF**: Sender Policy Framework verifierar meddelandets käll-IP-adress mot ägaren av avsändardomänen. En snabb introduktion till SPF och hur du får den konfigurerad snabbt finns i Konfigurera SPF för att [förhindra förfalskning.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) För att få en djupare förståelse av hur Microsoft 365 använder SPF, eller om du vill felsöka eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa artikeln om [hur Microsoft 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail lägger till en digital signatur i meddelanderubriken på meddelanden som skickas från din domän. Mer information finns i [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md)(Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Microsoft 365).

  - **DMARC:** Domänbaserad meddelandeautentisering, rapportering och överensstämmelse hjälper mål-e-postsystem att avgöra vad de ska göra med meddelanden som misslyckas med SPF- eller DKIM-kontroller och ger ytterligare en nivå av förtroende för dina e-postpartners. Mer information finns i Använda [DMARC för att validera e-post i Microsoft 365.](use-dmarc-to-validate-email.md)

- **Kontrollera inställningarna för** massutskick: Tröskelvärdet för massutskick (BCL) som du konfigurerar i principer för massutskick avgör om massutskick (kallas även grå e-post) markeras som skräppost. Inställningen Endast PowerShell för _MarkAsSpamBulkMail_ som är på som standard bidrar också till resultaten. Mer information finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Förhindra skräppostleverans till Inkorgen

- **Kontrollera organisationens inställningar:** Se upp med inställningar som tillåter att meddelanden hoppar över skräppostfiltrering (till exempel om du lägger till en egen domän i listan över tillåtna domäner i principer för skräppostskydd). Vi rekommenderar inställningar i Rekommenderade inställningar för EOP och Microsoft Defender för [Office 365-säkerhet](recommended-settings-for-eop-and-office365.md) och [Skapa listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

- **Kontrollera att skräppostregeln** är aktiverad i användarens postlåda : Den är aktiverad som standard, men om den är inaktiverad kan meddelanden som har markerats som skräppost inte flyttas till mappen Skräppost. Mer information finns i Konfigurera [inställningar för skräppost i Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Använda tillgängliga listor med spärrade avsändare**: Mer information finns i [Skapa listor med spärrade avsändare.](create-block-sender-lists-in-office-365.md)

- **Avbryta prenumerationen på massutskick** Om meddelandet var något som användaren registrerat sig för (nyhetsbrev, produktmeddelanden osv.) och innehåller en länk för att avsluta prenumerationen från en känd källa kan du be dem att avbryta prenumerationen.

- Fristående **EOP:** skapa e-postflödesregler i lokal Exchange för EOP-skräppostfiltrering av skräppost: I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även transportregler) i lokal Exchange för att omvandla EOP-skräppostfiltreringen så att skräppostregeln kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Förhindra att bra e-post identifieras som skräppost

Här är några åtgärder som du kan vidta för att förhindra falska positiva resultat:

- **Kontrollera användarens inställningar för skräppostfilter i Outlook:**

  - **Kontrollera att skräppostfiltret i Outlook** är inaktiverat: När Outlook-skräppostfiltret är inställt på standardvärdet Ingen automatisk filtrering **försöker** Outlook inte klassificera klassificerade som skräppost.  När den är  inställd på Låg eller Hög använder Skräppostfiltret i Outlook sin egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost, så att du kan få falska positiva identifieringar. Observera att Microsoft slutade producera uppdateringar av skräppostdefinitioner för SmartScreen-filtren i Exchange och Outlook i november 2016. De befintliga definitionerna av skräppost på SmartScreen finns kvar, men deras effektivitet kommer sannolikt att försämras med tiden.

  - **Kontrollera att inställningen "Endast listor** över betrodda avsändare" i Outlook är inaktiverad: När den här inställningen är aktiverad levereras endast meddelanden från avsändare i användarens lista över betrodda avsändare eller betrodda mottagare till Inkorgen. e-post från alla andra flyttas automatiskt till mappen Skräppost.

  Mer information om de här inställningarna finns i [Konfigurera skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Använd tillgängliga listor över betrodda avsändare**: Mer information finns i [Skapa listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

- **Kontrollera att användarna ligger inom gränserna för att skicka och ta** emot enligt beskrivningen i Ta emot och skicka [gränser](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) i tjänstbeskrivningen för Exchange Online.

- **Fristående EOP:** använd katalogsynkronisering: Om du använder fristående EOP för att skydda din lokala Exchange-organisation bör du synkronisera användarinställningar med tjänsten med hjälp av katalogsynkronisering. Det gör att EOP respekterar användarnas listor över betrodda avsändare. Mer information finns i Använda [katalogsynkronisering för att hantera e-postanvändare.](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)

## <a name="anti-spam-legislation"></a>Anti-spam-lagstiftning

På Microsoft anser vi att utvecklingen av ny teknik och självreglering kräver stöd för effektiva myndighetspolicyer och juridiska ramverk. Den globala skräppostspridningen har gjort många människor behöriga för att reglera kommersiell e-post. Många länder har nu lagar om skräppostskydd. USA har både federala och statliga lagar som reglerar skräppost, och den här kompletterande metoden hjälper till att begränsa skräppost samtidigt som den legitima e-handel kan bli vår. CAN-SPAM Act utökar verktygen som är tillgängliga för att begränsa bedrägliga och bedrägliga e-postmeddelanden.