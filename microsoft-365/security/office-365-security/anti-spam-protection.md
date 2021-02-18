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
ms.openlocfilehash: f82e3f36d00994a68ed579779bed314318c51f47
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288951"
---
# <a name="anti-spam-protection-in-eop"></a>Skydd mot skräppost i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Det här avsnittet är avsett för administratörer. Mer information om slutanvändare finns i [Översikt över skräppostfiltret och Mer](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) information om skräppost och [nätfiske.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas e-postmeddelanden automatiskt mot skräppost av EOP.

Microsofts översikt över e-postsäkerhet har en omatchad metod för flera produkter. EOP använder teknik mot skräppost och nätfiske på våra e-postplattformar för att ge användarna de senaste verktygen och innovationerna mot skräppost och nätfiske i hela nätverket. Målet för EOP är att erbjuda en omfattande och användbar e-posttjänst som hjälper till att identifiera och skydda användare från skräppost, bedrägliga e-posthot (nätfiske) och skadlig programvara.

I och med att e-postanvändningen har ökat blir det också missbruk. Obevakad skräppost kan täppa igen inkorgar och nätverk, påverka användarnöjdheten och effektivisera legitim e-postkommunikation. Därför fortsätter Microsoft att investera i skräppostskyddstekniker. Enkelt uttryckt börjar den med att innehålla och filtrera skräppost.

> [!TIP]
> Följande tekniker mot skräppost är användbara när du vill tillåta eller blockera meddelanden baserat på meddelandekuvertet (till exempel avsändarens domän eller meddelandets käll-IP-adress). Om du vill tillåta eller blockera meddelanden baserat på nyttolast (till exempel URL:er i meddelandet eller bifogade filer), bör du använda portalen för klientorganisationslistan över [tillåtna/blockerade listor.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Teknik mot skräppost i EOP

För att hjälpa till att minska skräppost inkluderar EOP skräppostskydd som använder egenutvecklad skräppostfiltreringsteknik för att identifiera och separera skräppost från legitima e-postmeddelanden. EOP-filtrering av skräppost lär sig av kända skräppost- och nätfiskehot och användarfeedback från vår konsumentplattform Outlook.com. Löpande feedback från EOP-användare i klassificeringsprogrammet för skräppost hjälper till att säkerställa att EOP-teknikerna har kontinuerlig utbildning och förbättringar.

Inställningarna för skydd mot skräppost i EOP har följande tekniker:

- Anslutningsfiltrering: Identifierar bra och dåliga servrar för e-postkälla tidigt i den inkommande e-postanslutningen via listan över tillåtna IP-adresser, IP-blockeringslistan och listan över betrodda avsändare *(en* dynamisk men icke-redigerbar lista över betrodda avsändare som underhålls av Microsoft). Du konfigurerar de här inställningarna i principen för anslutningsfilter. Läs mer på Konfigurera [anslutningsfiltrering.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > Spoof Intelligence använder anslutningsfiltrering för att skapa listor över tillåtna och spärrade avsändare som förfalskning av din e-postdomän. Mer information finns i Läs [mer om förfalskningsinformation i Microsoft 365.](learn-about-spoof-intelligence.md)

- **Skräppostfiltrering (innehållsfiltrering)**: EOP använder skräppostfiltreringens bedömning  av **skräppost,** hög konfidens för **skräppost,** massutskick,  nätfiske och nätfiske som klassificerar meddelanden.  Du kan konfigurera vilka åtgärder som ska vidtas utifrån dessa beslut och du kan konfigurera alternativ för avisering för slutanvändare för meddelanden som har satts i karantän i stället för att levereras. Mer information finns i Konfigurera [principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > Som standard är skräppostfiltrering konfigurerat för att skicka meddelanden som markerats som skräppost till mottagarens skräppostmapp. Men i hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera två e-postflödesregler (kallas även transportregler) i den lokala Exchange-organisationen för att identifiera de EOP-skräppostrubriker som läggs till i meddelanden. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtrering av utgående skräppost:** EOP kontrollerar också att användarna inte skickar skräppost, antingen i innehåll för utgående meddelanden eller genom att överskrida gränserna för utgående meddelanden. Mer information finns i Konfigurera [utgående skräppostfiltrering i Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Förfalskningsinformation**: Mer information finns i Läs [mer om förfalskningsinformation i Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Hantera fel i skräppostfiltrering

Det är möjligt att bra meddelanden identifieras som skräppost eller att skräppost kan skickas till Inkorgen. Du kan använda förslagen i följande avsnitt för att ta reda på vad som har hänt och förhindra att det händer i framtiden.

Här är några rekommendationer som gäller för något av scenariot:

- Skicka alltid felklassificerade meddelanden till Microsoft. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Undersök rubrikerna för skräppostskydd: De** här värdena förklarar varför ett meddelande har markerats som skräppost eller varför det hoppades över skräppostfiltrering. Mer information finns i [Rubriker för skräppostskydd.](anti-spam-message-headers.md)

- **Peka MX-posten på Microsoft 365:** För att EOP ska ge bästa skydd rekommenderar vi alltid att du skickar e-post till Microsoft 365 först. Instruktioner finns i Skapa [DNS-poster på vilken DNS-värd som helst för Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

  Om MX-posten pekar på någon annan plats (till exempel en tredjepartslösning mot skräppost eller utrustning) är det svårt för EOP att tillhandahålla korrekt skräppostfiltrering. I det här scenariot måste du konfigurera utökad filtrering för kopplingar (kallas även hoppa _över post)._ Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Använd** e-postautentisering: Om du äger en e-postdomän kan du använda DNS för att säkerställa att meddelanden från avsändare i den domänen är legitima. Använd alla följande e-postautentiseringsmetoder för att förhindra skräppost och oönskad förfalskning i EOP:

  - **SPF**: Sender Policy Framework verifierar meddelandets käll-IP-adress mot ägaren av avsändardomänen. En snabb introduktion till SPF finns i Konfigurera SPF för att förhindra [förfalskning.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) För att få en djupare förståelse av hur Microsoft 365 använder SPF, eller om du vill felsöka eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa artikeln om [hur Microsoft 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail lägger till en digital signatur i meddelanderubriken för meddelanden som skickas från din domän. Mer information finns i Använda [DKIM för att verifiera utgående e-post som skickas från din anpassade domän i Microsoft 365.](use-dkim-to-validate-outbound-email.md)

  - **DMARC:** Domänbaserad meddelandeautentisering, rapportering och överensstämmelse hjälper mål-e-postsystem att avgöra vad de ska göra med meddelanden som misslyckas med SPF- eller DKIM-kontroller och ger en annan nivå av förtroende för dina e-postpartners. Mer information finns i Använda [DMARC för att validera e-post i Microsoft 365.](use-dmarc-to-validate-email.md)

- **Kontrollera inställningarna** för massutskick: Tröskelvärdet för massutskick (BCL) som du konfigurerar i principer för skräppostskydd avgör om massutskick (även kallat grå e-post) markeras som skräppost. Inställningen Endast PowerShell med _MarkAsSpamBulkMail_ som är på som standard bidrar också till resultaten. Mer information finns i Konfigurera [principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Förhindra skräppostleverans till Inkorgen

- **Kontrollera organisationens inställningar:** Se upp med inställningar som gör att meddelanden kan hoppa över skräppostfiltrering (till exempel om du lägger till din egen domän i listan med tillåtna domäner i principer för skräppostskydd). Vi rekommenderar inställningar i rekommenderade inställningar för EOP och [Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md) och Skapa listor över [betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

- **Kontrollera att skräppostregeln** är aktiverad i användarens postlåda: Den är aktiverad som standard, men om den är inaktiverad kan meddelanden som markerats som skräppost inte flyttas till mappen Skräppost. Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Använd listorna med spärrade avsändare:** Mer information finns i [Skapa listor med spärrade avsändare.](create-block-sender-lists-in-office-365.md)

- **Avbryta prenumerationen på massutskick** Om meddelandet var något som användaren registrerat sig för (nyhetsbrev, produktmeddelanden o.s.v.) och innehåller en länk för att avsluta prenumerationen från en känd källa kan du be dem att helt enkelt avbryta prenumerationen.

- Fristående EOP: Skapa e-postflödesregler i lokal Exchange för **EOP-filtrering** av skräppost: I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även transportregler) i ett lokalt Exchange för att översätta EOP-skräppostfiltreringen så att skräppostregeln kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Förhindra att bra e-post identifieras som skräppost

Här är några steg som du kan vidta för att förhindra falska positiva resultat:

- **Kontrollera användarens inställningar för skräppostfilter i Outlook:**

  - **Kontrollera att skräppostfiltret** i Outlook är inaktiverat: När outlook-skräppostfiltret har angetts till standardvärdet Ingen automatisk filtrering försöker Outlook inte klassificera klassificera som skräppost.   När den är  inställd på Låg eller Hög använder Outlooks skräppostfilter en egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost så att du kan få falska positiva identifieringar. Observera att Microsoft slutade producera uppdateringar av skräppostdefinitioner för SmartScreen-filtren i Exchange och Outlook i november 2016. De befintliga definitionerna av skräppost på SmartScreen finns kvar, men deras effektivitet kommer sannolikt att försämras med tiden.

  - **Kontrollera att inställningen "Endast** listor över betrodda avsändare" i Outlook är inaktiverad: När den här inställningen är aktiverad levereras endast meddelanden från avsändare i användarens lista över betrodda avsändare eller betrodda mottagare till Inkorgen. E-post från alla andra flyttas automatiskt till mappen Skräppost.

  Mer information om de här inställningarna finns i [Konfigurera skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Använd tillgängliga listor med betrodda avsändare:** Mer information finns i [Skapa listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)

- **Kontrollera att användarna ligger inom gränserna för att skicka och ta** emot enligt beskrivningen i Beskrivningen [av](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) Exchange Online-tjänsten vid mottagande och sändning.

- **Fristående EOP:** Använd katalogsynkronisering: Om du använder fristående EOP för att skydda din lokala Exchange-organisation bör du synkronisera användarinställningar med tjänsten med hjälp av katalogsynkronisering. Det säkerställer att EOP respekterar användarnas listor över betrodda avsändare. Mer information finns i Använda [katalogsynkronisering för att hantera e-postanvändare.](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)

## <a name="anti-spam-legislation"></a>Skydd mot skräppostlagstiftning

På Microsoft anser vi att utvecklingen av ny teknik och självreglering kräver stöd för effektiva myndighetspolicyer och juridiska ramverk. Den globala skräppostspridningen har gjort att flera olika organisationer kan reglera kommersiell e-post. Många länder har nu lagar om skräppostskydd. USA har både federala och statliga lagar som reglerar skräppost, och den här komplementära metoden hjälper till att begränsa skräpposten samtidigt som legitima e-handel kan bli inskr. CAN-SPAM Act utökar de tillgängliga verktygen för att begränsa bedrägliga och bedrägliga e-postmeddelanden.
