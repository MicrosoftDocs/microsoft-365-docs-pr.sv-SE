---
title: Funktioner i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: Följande tabell innehåller en lista över funktioner som är tillgängliga i den värdbaserade e-postfiltreringstjänsten i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ff3c889f3e4d6779b08584ba6537da36d6f2660e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916952"
---
# <a name="eop-features"></a>Funktioner i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

Följande tabell innehåller en lista över funktioner som är tillgängliga i den värdbaserade e-postfiltreringstjänsten i Exchange Online Protection (EOP).

> [!TIP]
> Översikt [över Microsoft 365 för företag är](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en bra resurs för att ta reda på information om kommande nya funktioner. Mer information om vilka funktioner som är tillgängliga med de olika EOP-abonnemangen finns i Tjänstbeskrivning [för Exchange Online Protection.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

****

|Funktion|Beskrivning|
|---|---|
|**Skydd mot skräppost**||
|Identifiering av inkommande skräppost|Mer information finns i [Skydd mot skräppost i Microsoft 365.](anti-spam-protection.md) <p> I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Identifiering av utgående skräppost|Skydd mot utgående skräppost är alltid aktiverat om du använder tjänsten för att skicka utgående e-post. Mer information finns i Skydd [mot utgående skräppost.](outbound-spam-controls.md)|
|Skydd mot bakåtcatter|Mer information finns i [Bakåtcatter och EOP.](backscatter-messages-and-eop.md)|
|Massfiltrering|EOP använder tröskelvärdet för mass klagomål (BCL) för att markera massutskick av e-postmeddelanden som skräppost. Mer information finns i följande avsnitt: <p> [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Nivå för mass klagomål (BCL) i EOP](bulk-complaint-level-values.md) <p> [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md)|
|Skadliga URL-blockeringslistor|EOP använder flera URL-blockeringslistor som hjälper till att identifiera kända skadliga länkar i meddelanden.|
|Skydd mot nätfiske|EOP innehåller 750 000 domäner för kända skräppostavs spammare.|
|Skydd mot förfalskning|Mer information finns [i Skydd mot förfalskning.](anti-spoofing-protection.md)|
|**Hantering av skräppost**||
|Konfigurera betrodda avsändare och spärrade avsändare|Mer information finns i Skapa [listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md) och Skapa listor med [spärrade avsändare.](create-block-sender-lists-in-office-365.md)|
|Skapa anpassade principer för skydd mot skräppost|Du kan skapa anpassade principer för skydd mot skräppost och tillämpa dem på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprinciper, men du kan ändra prioriteten (det vill säga ordningen) för dina anpassade principer. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Konfigurera åtgärder för skräppostfiltreade meddelanden|Du kan till exempel ta bort innehållsfiltreerade meddelanden eller skicka dem till mappen Skräppost eller karantän. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Internationell skräppostfiltrering|Du kan konfigurera skräppostskyddsfiltrering för att filtrera meddelanden som skrivits på vissa språk eller som skickas från vissa länder eller regioner. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Hantera skräppost via Outlook eller Outlook på webben (tidigare kallat Outlook Web App)|Administratörer och slutanvändare kan skapa listor över betrodda avsändare och spärrade avsändare. Mer information finns i [Om skräppostinställningar i Outlook.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Om du använder EOP för att skydda lokala postlådor ska du se till att använda katalogsynkronisering för att säkerställa att de här inställningarna synkroniseras till tjänsten. Mer information om hur du inställningar för katalogsynkronisering finns i "Använda katalogsynkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP.](manage-mail-users-in-eop.md)|
|Rapportera falska positiva resultat och falska negativa tal till Microsoft.|Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).|
|Karantänmeddelanden för skräppost för slutanvändare|Mer information finns i [Skräppost-aviseringar för slutanvändare](use-spam-notifications-to-release-and-report-quarantined-messages.md) [och Konfigurera skräppost-aviseringar för slutanvändare.](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)|
|Visa, hitta och hantera meddelanden i karantänportalen.|Mer information finns i Hantera meddelanden i karantän och filer som administratör i [EOP](manage-quarantined-messages-and-files.md) eller Hitta och släppa meddelanden i [karantän som en användare.](find-and-release-quarantined-messages-as-a-user.md)|
|Visa rubriker i karantänen för skräppost|När du har visa meddelanderubriken i karantän kan du också [](https://mha.azurewebsites.net/) kopiera och klistra in rubriktexten i Analysverktyg för meddelanderubrik för att ta reda på vad som har hänt med meddelandet.|
|**Skydd mot skadlig kod**||
|Skydd mot skadlig programvara med flera motor|Flera motorer mot skadlig programvara hjälper till att alltid skydda våra kunder.|
|Möjlighet att inaktivera filtrering av skadlig programvara|Du kan inte inaktivera filtrering av skadlig programvara. Vi tror att en konsekvent och noggrann skyddsnivå för alla våra kunder är en viktig del av den djupgående strategi som krävs för att skydda din e-postmiljö. Då aktiveras filtrering av skadlig programvara automatiskt för alla kunder.|
|Kontroll av skadlig programvara av meddelandets brödtext och bifogade filer|Tjänsten kontrollerar den aktiva nyttolasten i meddelandets brödtext och alla bifogade filer i meddelanden för skadlig kod.|
|Standardaviseringar och aviseringar om anpassad skadlig programvara|Du kan skicka ett meddelande till avsändare eller administratörer. Mer information finns i Konfigurera [principer för skadlig programvara.](configure-anti-malware-policies.md)|
|Mottagarens meddelanden|Sätt meddelandet i tyst läge eller sätt meddelandet i karantän och leverera det också med alla bifogade filer ersatta med en enda textfil som innehåller vanlig eller anpassad text. Mer information finns i Konfigurera [principer för skadlig programvara.](configure-anti-malware-policies.md)|
|Vanlig filtrering av bifogade filer|Du kan aktivera och anpassa en lista över filtyper som alltid antas vara skadlig programvara. Mer information finns i Skydd [mot skadlig programvara i EOP.](anti-malware-protection.md)|
|Skydd mot spionprogram|Skydd mot skadlig programvara omfattar skydd mot virus och skydd mot spionprogram.|
|Skapa anpassade principer för skadlig programvara|Du kan skapa principer för anpassade skadlig programvara och tillämpa dem på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprinciper, men du kan ändra prioriteten (det vill säga ordningen) för dina anpassade principer. Mer information finns i Konfigurera [principer för skadlig programvara.](configure-anti-malware-policies.md)|
|**E-postdirigering och kopplingar**||
|Villkorsstyrd e-postdirigering|Mer information finns i [Scenario: Villkorsstyrd e-postdirigering i Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisk eller tvingad TLS|Opportunistisk eller tvingad TLS är tillgänglig med kopplingar. Opportunistisk TLS försöker en TLS-anslutning men använder en SMTP-anslutning om TLS-anslutningen inte lyckas. Tvinga TLS att använda TLS-anslutningar, vilket innebär att meddelandet avvisas om TLS-anslutningen inte lyckas. Mer information om TLS, säkerhet och kopplingar finns i Konfigurera kopplingar för säker [e-postflöde med en partnerorganisation.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)|
|Regional routning (begränsningen för e-postflödet till ett visst område)|Mer information finns i avsnittet "EOP-datacenter" i översikten över [Exchange Online Protection.](exchange-online-protection-overview.md)|
|Verktyget SMTP-anslutningskontroll|Mer information om hur du använder det här verktyget för att testa e-postflödet finns i Testa e-postflödet genom att validera [dina Microsoft 365-kopplingar.](/exchange/mail-flow-best-practices/test-mail-flow)|
|Matcha underdomäner|Mer information om hur du aktiverar e-postflödet till och från underdomäner till godkända domäner finns i [E-postflöde i EOP.](mail-flow-in-eop.md)|
|**E-postflödesregler**||
|Principbaserad filtrering och åtgärder|Anpassade principer är baserade på e-postflödesregler i Exchange (kallas även transportregler). Du kan filtrera efter domän, nyckelord, filnamn, filtyp, ämnesrad, meddelandetext, avsändare, mottagare, rubrik och IP-adress. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online Protection.](mail-flow-rules-transport-rules-0.md)|
|Filtrera efter textmönster|E-postflödesregler kan använda en matris eller reguljära uttryck för att matcha text. Du kan också använda en sträng eller en matris med strängar för att matcha många meddelandeegenskaper, till exempel adress, ämne, brödtext eller namn på bifogade filer. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Egna ordlistor|E-postflödesregler kan innehålla långa listor med text och nyckelord som ger samma funktioner som en egen ordlista.|
|Policyregler per domän|Omfattningen av en e-postflödesregel kan anpassas så att den matchar avsändarens eller mottagarens domännamn, IP-adressintervall, adressnyckelord eller mönster, gruppmedlemskap och andra villkor.|
|Skanning av bifogade filer|Du kan skapa regler för att söka igenom filnamn, filnamnstillägg och innehåll för den bifogade filen.|
|Skicka principregelaviseringar till avsändaren|Du kan avvisa meddelanden och skicka en rapport om utebliven leverans (kallas även  NDR eller icke-leveranskända meddelanden) till avsändaren via meddelandet Avvisa meddelandet med en förklaring eller Avvisa meddelandet med åtgärden utökad **statuskod.** Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Omdirigera eller kopiera meddelanden|E-postflödesregler kan omdirigera, lägga till mottagare efter Kopia eller Hemlig kopia, helt enkelt lägga till mottagare och andra alternativ. Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Justera regelprioritet över flera regler|Använd Exchange admin center för att ändra i vilken ordning regler bearbetas.|
|Filtrera meddelanden och ändra sedan routning eller attribut för ett meddelande|Du kan filtrera meddelanden utifrån en mängd olika villkor och sedan tillämpa en serie åtgärder på varje meddelande. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online Protection.](mail-flow-rules-transport-rules-0.md)|
|Ändra skräppostförtroendenivån (SCL) för ett meddelande enligt regel.|Du kan kontrollera ett transitmeddelande och ange ett förtroendenivå för skräppost baserat på kriterier som du väljer. Mer information finns i Använda [e-postflödesregler för att ange SCL (Spam Confidence Level) i meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)|
|Kontrollera bifogade filer i meddelanden|Du kan undersöka innehållet i en bifogad fil eller egenskaperna för en bifogad fil och definiera en åtgärd att vidta baserat på vad som hittas. Mer information finns i Inspektera bifogade filer i Exchange Online med hjälp [av e-postflödesregler.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)|
|**Administration**||
|Webbaserad administration|Administratörer kan hantera tjänsten i administrationscentret för Exchange (EAC), som stöds på 60 språk. Mer information finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)|
|Katalogsynkronisering:|Katalogsynkronisering är tillgänglig via azure Active Directory-synkroniseringsverktyget. Mer information finns i avsnittet "Använda katalogsynkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP.](manage-mail-users-in-eop.md)|
|Katalogbaserat gränsblockering (DBEB)|Med DBEB-funktionen kan du avvisa meddelanden till ogiltiga mottagare i tjänstens nätverks perimeter. Med DBEB kan administratörer lägga till e-postaktiverade mottagare i Microsoft 365 och blockera alla meddelanden som skickas till e-postadresser som inte finns i Microsoft 365. Mer information om hur du konfigurerar DBEB finns i [Använda katalogbaserad edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare.](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|PowerShell|Fullständiga EOP-funktioner är tillgängliga i fristående EOP PowerShell. Mer information finns i [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)|
|**Rapportering och loggning**||
|Meddelandespårning|Administratörer kan följa e-postmeddelanden när de passerar genom tjänsten. Du kan avgöra om ett riktat e-postmeddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. På så sätt kan du svara effektivt på användarnas frågor, felsöka problem i e-postflödet, verifiera principändringar och förbättra behovet av att kontakta teknisk support för att få hjälp. Mer information finns i [Meddelandespårning i Säkerhets- & Kompatibilitetscenter.](message-trace-scc.md)|
|Webbaserade rapporter|E-postskyddsrapporterna i Säkerhets- & Säkerhets- och efterlevnadscenter tillhandahåller meddelandedata. Du kan till exempel övervaka hur mycket skräppost och skadlig programvara som upptäcks eller hur ofta dina e-postflödesregler matchas. Med dessa interaktiva rapporter kan du snabbt få en visuell rapport över sammanfattningsdata och öka detalj detaljinformationen om enskilda meddelanden, upp till 90 dagar. Mer information finns i Använda [rapporter för e-postskydd för att visa data om skadlig programvara, skräppost och regelidentifiering.](/exchange/monitoring/use-mail-protection-reports)|
|Granskningsloggning|Administratörsrollgruppens rapport och administratörens granskningslogg är tillgängliga för EOP-administratörer. Mer information finns i [Granskningsrapporter i EOP.](auditing-reports-in-eop.md)|
|**Servicenivåavtal (SLAs) och support**||
|SLA (effektiv skräppost)|\> 99%|
|False positive ratio SLA|\< 1:250,000|
|Virusidentifiering och blockering av SLA|100 % av kända virus|
|SLA för månatlig drifttid|99.999%|
|Teknisk support via telefon och webb dygnet runt, sju dagar i veckan|Mer information om hjälp- och supportalternativ för EOP finns i [Hjälp och support för EOP.](help-and-support-for-eop.md)|
|**Andra funktioner**||
|Ett geo-redundant globalt nätverk av servrar|EOP körs i ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Mer information finns i avsnittet "EOP datacenter" i Exchange [Online Protection översikt](exchange-online-protection-overview.md).|
|Köer när den lokala servern inte kan ta emot e-post|Meddelanden med uppsegen post finns kvar i våra köer en dag. Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem. I genomsnitt tas meddelanden om var femte minut. Mer information finns i Vanliga frågor och [svar om EOP i kö, uppskjuten eller oaktiverad e-post.](eop-queued-deferred-and-bounced-messages-faq.md)|
|Meddelandekryptering i Office 365 finns som en tilläggstjänst|Mer information finns i [Kryptering i Office 365.](../../compliance/encryption.md)|
|