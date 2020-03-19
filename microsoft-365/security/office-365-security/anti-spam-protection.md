---
title: Office 365 email anti-spam protection
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
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
description: Lär dig mer om inställningarna och filtren mot skräppost som hjälper dig att förhindra skräppost i Exchange Online och Office 365. Får du för mycket skräppost i Office 365? Du kan anpassa dina skräppostfilter och policyinställningar för skräppost.
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808122"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 email anti-spam protection

Är du orolig för för mycket skräppost i Office 365? Vi har skapat flera skräppostfilter i din Office 365- eller Exchange Online Protection-tjänst (EOP), så att din e-post skyddas från det ögonblick du får ditt första meddelande. För att förhindra skräppost i Office 365 kanske du vill ändra en skyddsinställning för att hantera ett visst problem i organisationen – säg att du får mycket skräppost från en viss avsändare, till exempel – eller för att helt enkelt finjustera dina inställningar så att de skräddarsydda för att bäst möta behoven i din organisation. Det gör du genom att ändra inställningarna för skräppost &amp; mot skräppost i Office 365 Security Compliance Center.

Den här artikeln är avsedd för Office 365-administratörer. Om du inte är administratör, men är office 365-användare och vill lära dig hur du hanterar skräppost som du får, är det inte den artikel du letar efter. Om du använder Outlook för PC eller Outlook för Mac börjar du i stället med [Översikt över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Om du använder Outlook på webben börjar du med [Lär dig mer om skräppost och nätfiske](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>De här alternativen hjälper dig att förhindra skräppost i Office 365

 **Anslutningsfiltrering**: När du använder anslutningsfiltrering kontrollerar Office 365 avsändarens rykte innan ett meddelande kan komma igenom. Du kan skapa en tillåt-lista, eller en säker avsändarlista, för att se till att du får alla meddelanden som skickas till dig från en viss IP-adress eller IP-adressintervall. Du kan också skapa en lista med IP-adresser som du vill blockera meddelanden från, så kallade blockeringslista. Mer information finns i [Konfigurera anslutningsfilterprincipen](configure-the-connection-filter-policy.md). Om du är orolig för skräppost i Office 365 använder du anslutningsfiltrering för att förhindra skräppost.

För kunder som har Office 365 Enterprise E5 eller har köpt ATP-licenser (Advanced Threat Protection) används anslutningsfiltrering av falska underrättelser för att skapa tillåta och blockera listor över avsändare som förfalskar din domän. Mer information finns i [Läs mer om falska underrättelser](learn-about-spoof-intelligence.md).

 **Skräppostfiltrering**: Office 365 söker efter meddelandeegenskaper som överensstämmer med skräppost med hjälp av skräppostfiltrering. Du kan ändra vilka åtgärder som ska vidtas på meddelanden som identifieras som skräppost och välja om du vill filtrera meddelanden som skrivits på specifika språk eller skickas från vissa länder eller regioner. Du kan också aktivera avancerade alternativ för skräppostfiltrering om du vill ha en aggressiv metod för skräppostfiltrering. Dessutom kan du konfigurera skräppostmeddelanden för slutanvändare för att informera användarna när meddelanden som är avsedda för dem skickades till karantänen i stället. (Att skicka meddelanden till karantänen är en av de konfigurerbara åtgärderna.) Från dessa meddelanden kan slutanvändare släppa falska positiva identifieringar och rapportera dem till Microsoft för analys. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Använd skräppostfiltrering om du är orolig för för mycket skräppost i Office 365 för att förhindra skräppost i Office 365 för att förhindra skräppost om du är orolig för för mycket skräppost i Office 365.

> [!NOTE]
> För fristående EOP-kunder: Som standard skickar EOP-skräppostfiltren skräppostmeddelanden till varje mottagares skräppostmapp. För att säkerställa att åtgärden **Flytta meddelande till skräppost** fungerar med lokala postlådor måste du dock konfigurera två Exchange-regler för e-postflöde (kallas även transportregler) på dina lokala servrar för att identifiera skräpposthuvuden som lagts till av EOP. Mer information finns [i Se till att skräppost dirigeras till varje användares skräppostmapp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Extra information om du får för mycket skräppost i Office 365

Följande video ger en översikt över att konfigurera skräppostfiltrering i EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

Mer information finns i avsnittet Konfigurera principer [för skräppostfilter.](configure-your-spam-filter-policies.md)

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Kontrollera dina utgående meddelanden för att förhindra skräppost i Office 365

 **Utgående filtrering:** Office 365 kontrollerar också att användarna inte skickar skräppost. Till exempel kan en användares dator bli infekterad med skadlig kod som gör att den skickar skräppost, så vi skapar skydd mot den som kallas *utgående filtrering*. Du kan inte inaktivera utgående filtrering, men du kan konfigurera inställningarna som beskrivs i [Konfigurera principen för utgående skräppost](configure-the-outbound-spam-policy.md). Om du är orolig för för mycket skräppost i Office 365 använder du utgående filtrering för att förhindra skräppost i Exchange Online.

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Utöver grunderna: Fler sätt att förhindra skräppost i Office 365

 Regler för **e-postflöde**: Om du vill gå längre än inbyggd skräppostfiltrering och skapa anpassade regler som baseras på dina affärspolicyer är _[regler för e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_ (kallas även _transportregler)_ ett annat filter som hjälper dig att förhindra skräppost i Office 365. Du kan till exempel använda regler för e-postflöde för att ange värdet för spam confidence level (SCL) för meddelanden som matchar specifika villkor, enligt beskrivningen i [Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

 **E-postautentisering**: Tekniker som använder DNS (Domain Name System) för att lägga till verifierbar information i e-postmeddelanden om avsändaren av ett e-postmeddelande kallas e-postautentisering. Mer avancerade Office 365-administratörer kan använda dessa metoder för e-postautentisering:

- **Avsändarprincipram (SPF)**: SPF validerar e-postmeddelandenas ursprung genom att verifiera avsändarens IP-adress mot den påstådda ägaren av den sändande domänen. En snabb introduktion till SPF och snabbt konfigurera den finns [i Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Om du vill ha en mer ingående förståelse för hur SPF används i Office 365 eller för felsökning eller icke-standarddistributioner, till exempel hybriddistributioner, börjar du med [Hur Office 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).

- **DomainKeys Identified Mail (DKIM)**: DKIM kan du bifoga en digital signatur till e-postmeddelanden i meddelandet huvudet av e-postmeddelanden du skickar. E-postsystem som tar emot e-post från din domän använder den här digitala signaturen för att avgöra om inkommande e-post som de får är legitimt. Information om DKIM och Office 365 finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md).

- **Domänbaserad meddelandeautentisering, rapportering och konformance (DMARC):** DMARC hjälper till att ta emot e-postsystem avgöra vad du ska göra med meddelanden som misslyckas SPF eller DKIM-kontroller och ger en annan förtroendenivå för dina e-postpartner. Information om hur du konfigurerar DMARC finns i [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).

Om du är orolig för skräppost, nätfiske och förfalskning i Office 365 använder du SPF, DKIM och DMARC tillsammans för att förhindra skräppost och oönskad förfalskning.

 Hanterade inställningar för slutanvändare: Om du letar efter information om hur slutanvändare kan hantera sina egna skräppostinställningar kan du läsa [Översikt över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (för Microsoft **Outlook-användare)** eller [Läs mer om skräppost och nätfiske](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31) (för Outlook på webben). Om du använder EOP för att skydda lokala postlådor måste du använda katalogsynkronisering för att säkerställa att dessa inställningar synkroniseras med tjänsten. Mer information om hur du konfigurerar katalogsynkronisering finns i "Använd katalogsynkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).

## <a name="for-more-information"></a>Mer information

[Blogg: Varför kommer skräppost och nätfiske via Office 365?](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)

[Förhindra falsk positiv e-post markerad som skräppost med en safelist eller andra tekniker](prevent-email-from-being-marked-as-spam.md)

[Konfigurera skräppostfiltrering i Office 365 för att blockera skräppost](reduce-spam-email.md)

[Vad är skillnaden mellan skräppost och massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Rubriker mot skräppost](anti-spam-message-headers.md)

[Meddelanden på grund av bakåtspridning och EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>Fler resurser

[Du kan få hjälp i forumen på Office 365-communityn](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[Administratörer: Logga in och skapa en tjänstförfrågning](https://portal.office.com/AdminPortal/Home?ref=support)

[AContact-support för företagsprodukter - Administratörshjälp](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
