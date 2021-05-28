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
description: Följande tabell innehåller en lista över funktioner som är tillgängliga i den e-postfiltreringstjänst Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62530a7c5da7ab0b7fd0e8415c8c366a1caafdda
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696460"
---
# <a name="eop-features"></a>Funktioner i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)

Följande tabell innehåller en lista över funktioner som är tillgängliga i e-postfiltreringstjänsten Exchange Online Protection (EOP).

> [!TIP]
> Översikt [Microsoft 365 för företag är en](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) bra resurs för att ta reda på information om kommande nya funktioner. En bredare vy över vilka funktioner som är tillgängliga med de olika EOP-abonnemangen finns [Exchange Online Protection Tjänstbeskrivning](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

<br>

****

|Funktion|Beskrivning|
|---|---|
|**Skydd mot skadlig kod**||
|Skydd mot skadlig programvara med flera motor|Flera motorer mot skadlig programvara hjälper till att alltid skydda våra kunder.|
|Filtrering av skadlig programvara som alltid används|Du kan inte inaktivera filtrering av skadlig programvara. Vi tror att en konsekvent och noggrann skyddsnivå för alla våra kunder är en viktig del av den djupgående strategi som krävs för att skydda din e-postmiljö. Då aktiveras filtrering av skadlig programvara automatiskt för alla kunder.|
|Kontroll av skadlig programvara av meddelandets brödtext och bifogade filer|Tjänsten kontrollerar den aktiva nyttolasten i meddelandets brödtext och alla bifogade filer i meddelanden för skadlig kod.|
|Skydd mot spionprogram|Skydd mot skadlig programvara omfattar skydd mot virus och skydd mot spionprogram.|
|Policyer för skadlig programvara|Alla organisationer har en standardprincip för skydd mot skräppost som gäller för alla mottagare. Du kan skapa anpassade principer för skydd mot skadlig programvara som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer tillämpas alltid före standardprincipen, men du kan ändra i vilken ordning anpassade principer används. <p> Du kan konfigurera följande inställningar i principer mot skadlig programvara: <ul><li>**Vanlig filtrering av** bifogade filer: Aktivera en anpassad lista över filtyper som alltid antas vara skadliga för skadlig programvara.</li><li>**ZAP för skadlig programvara:** Sätt retroaktivt karantän när skadlig programvara levereras. Mer information finns i [ZAP (Zero-hour auto purge) i Exchange Online](zero-hour-auto-purge.md).</li><li>**Mottagarmeddelanden:** Sätt meddelandet i karantän eller sätt meddelandet i karantän, och leverera det även med alla bifogade filer ersatta med en enda textfil som innehåller standardtext eller anpassad text.</li><li>**Avsändarmeddelanden:** Meddela avsändarna att meddelandet identifierades som skadlig kod.</li><li>**Administratörsmeddelanden:** Meddela en administratör när meddelanden från interna eller externa avsändare identifierades som skadlig programvara.</li></ul> <p> Mer information finns i Konfigurera [principer för skadlig programvara.](configure-anti-malware-policies.md)|
|**Skydd mot nätfiske**||
|Skydd mot nätfiske|EOP använder en lista över domäner som används av kända skräppostavs spammare.|
|Skydd mot förfalskning|Skydd mot nätfiske i EOP har skydd mot förfalskning. Mer information finns [i Skydd mot förfalskning.](anti-spoofing-protection.md) <p> Skydd mot nätfiske i Microsoft Defender för Office 365 även personifieringsskydd. Mer information finns på [Exklusiva inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).|
|**Skydd mot skräppost**||
|Identifiering av inkommande skräppost|Mer information finns i [Skydd mot skräppost i Microsoft 365](anti-spam-protection.md). <p> Ytterligare steg som krävs i hybridmiljöer finns i Konfigurera EOP för att leverera skräppost till mappen Skräppost [i hybridmiljöer.](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)|
|Skydd mot bakåtcatter|Mer information finns i [Bakåtcatter och EOP.](backscatter-messages-and-eop.md)|
|Massfiltrering|EOP använder tröskelvärdet för mass klagomål (BCL) i principer för skräppostskydd för att markera massutskick av e-postmeddelanden som skräppost. Mer information finns i följande avsnitt: <ul><li>[Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)</li><li>[Nivå för mass klagomål (BCL) i EOP](bulk-complaint-level-values.md)</li><li>[Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md)</li></ul>|
|Skadliga URL-blockeringslistor|EOP använder flera URL-blockeringslistor som hjälper till att identifiera kända skadliga länkar i meddelanden.|
|**Utgående skräppostskydd**||
|Identifiering av utgående skräppost|Skydd mot utgående skräppost är alltid aktiverat om du använder tjänsten för att skicka utgående e-post. Mer information finns i Skydd [mot utgående skräppost.](outbound-spam-controls.md)|
|Principer för utgående skräppost|Alla organisationer har en standardprincip för utgående skräppost som gäller för alla mottagare. För att få mer detaljerad information kan du skapa anpassade principer för skydd mot skräppost som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer tillämpas alltid före standardprincipen, men du kan ändra i vilken ordning anpassade principer används. <p> Du kan konfigurera följande inställningar i principer för skydd mot skräppost: <ul><li>**Messsage limts**: Du kan ange [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) begränsningar som är lägre än standardinställningarna för tjänsten för externa mottagare **per** timme, interna mottagare **per** timme och maximalt antal **mottagare per dag**</li><li>**Åtgärd för att vidta åtgärder för användare som** överskrider en gräns: Begränsa användaren i 24 timmar, begränsa användaren tills den släpps eller aviseringen.</li><li>**Aktivera eller inaktivera automatisk vidarebefordran av extern e-post**: [Läs mer](external-email-forwarding.md)</li><li>**Meddela eller skicka kopior av meddelanden till administratörer**</li></ul> <p> Mer information finns i Konfigurera [utgående skräppostfiltrering i EOP.](configure-the-outbound-spam-policy.md)|
|**Anslutningsfiltrering**||
|Princip för anslutningsfilter|Konfigurera listan över tillåtna IP-adresser och listan över blockerade IP-adresser för organisationen. Mer information finns i Konfigurera [anslutningsfiltrering](configure-the-connection-filter-policy.md)|
|**Hantering av skräppost**||
|Principer mot skräppost|Alla organisationer har en standardprincip för skydd mot skräppost som gäller för alla mottagare. För att få mer detaljerad information kan du skapa anpassade principer för skydd mot skräppost som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer tillämpas alltid före standardprincipen, men du kan ändra i vilken ordning anpassade principer används. <p> Du kan konfigurera följande inställningar i principer för skydd mot skräppost: <ul><li>**Åtgärder för** skräppostfilterval: När ett meddelande upptäcks kan du konfigurera åtgärden att vidta (ta bort, flytta till mappen Skräppost, karantän osv.) baserat på bedömningsåtgärden.</li><li>**Avancerade inställningar för skräppostfilter (ASF):** De här inställningarna beskrivs i inställningarna för avancerat [skräppostfilter (ASF) i EOP](advanced-spam-filtering-asf-options.md)</li><li>**ZAP för nätfiske och** skräppost: Sätt retroaktivt sätt i karantän eller flytta skickade meddelanden till mappen Skräppost. Mer information finns i [ZAP (Zero-hour auto purge) i Exchange Online](zero-hour-auto-purge.md).</li><li>**Aktivera skräppost-aviseringar för slutanvändaren**: [Läs mer om skräppost-aviseringar för slutanvändare]. (use-spam-notifications-to-release-and-report-quarantined-messages.md)</li>**Tillåtna och blockerade avsändare** och domäner: Viktig information om hur du använder listorna på ett säkert sätt finns i Skapa listor över [betrodda](create-safe-sender-lists-in-office-365.md) avsändare och Skapa [listor över spärrade avsändare](create-block-sender-lists-in-office-365.md)</li><li>**Inställningar för internationell skräppost:** Blockera meddelanden baserat på språk eller källland.</li></ul> <p> Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Hantera skräppost via Outlook eller Outlook på webben (kallades tidigare för Outlook Web App)|Användare och administratörer kan skapa personliga listor över betrodda avsändare och spärrade avsändare i Exchange Online postlådor. Mer information finns i [Om skräppostinställningar i Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <p> Om du använder EOP för att skydda lokala Exchange-postlådor ska du se till att använda katalogsynkronisering för att säkerställa att de här inställningarna synkroniseras till tjänsten. Mer information finns i Använda [katalogsynkronisering för att hantera e-postanvändare.](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)|
|Rapportera falska positiva resultat och falska negativa tal till Microsoft.|Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).|
|Visa, hitta och hantera meddelanden i karantänportalen.|Mer information finns i Hantera meddelanden i karantän och filer som administratör i [EOP](manage-quarantined-messages-and-files.md) eller Hitta och släppa meddelanden i [karantän som en användare.](find-and-release-quarantined-messages-as-a-user.md)|
|Visa rubriker i karantänen för skräppost|När du har visa meddelanderubriken i karantän kan du också [](https://mha.azurewebsites.net/) kopiera och klistra in rubriktexten i Analysverktyg för meddelanderubrik för att ta reda på vad som har hänt med meddelandet.|
|**E-postdirigering och kopplingar**||
|
|Villkorsstyrd e-postdirigering|Mer information finns i [Scenario: Villkorsstyrd e-postdirigering i Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisk eller tvingad TLS|<ul><li>Opportunistisk TLS försöker en TLS-anslutning men använder en SMTP-anslutning om TLS-anslutningen inte lyckas.</li><li>Tvingad TLS framtvingar TLS-anslutningar, vilket innebär att meddelandet avvisas om TLS-anslutningen inte lyckas.</li></ul> <p> Mer information om TLS, säkerhet och kopplingar finns i Konfigurera kopplingar för säker [e-postflöde med en partnerorganisation.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)|
|Regional routning (begränsningen för e-postflödet till ett visst område)|Mer information finns i [EOP-datacenter](exchange-online-protection-overview.md#eop-datacenters).|
|Verktyget SMTP-anslutningskontroll|Mer information om hur du använder verktyget för att testa e-postflödet finns i Testa e-postflödet genom [att verifiera Microsoft 365-kopplingarna.](/exchange/mail-flow-best-practices/test-mail-flow)|
|Matcha underdomäner|Mer information om hur du aktiverar e-postflödet till och från underdomäner till godkända domäner finns i [E-postflöde i EOP.](mail-flow-in-eop.md)|
|**E-postflödesregler**||
|E-postflödesregler i EOP|Praktiskt taget alla villkor, undantag och åtgärder som är tillgängliga i e-postflödesregler (kallas även transportregler) i Exchange Online är även tillgängliga i fristående EOP-organisationer utan Exchange Online postlådor. Mer information om e-postflödesregler finns i följande avsnitt: <ul><li>[E-postflödesregler](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</li><li>[Villkor och undantag i e-postflödesregel](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</li><li>[Åtgärder för e-postflödesregel](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</li></ul>|
|Scenarier för e-postflödesregel|Många scenarier är tillgängliga med hjälp av transportregler. Till exempel: <ul><li>**Principbaserad filtrering och** åtgärder: Du kan filtrera efter domän, nyckelord, filnamn, filtyp, ämnesrad, meddelandetext, avsändare, mottagare, rubrik och IP-adress.</li><li>**Filtrera efter textmönster**: E-postflödesregler kan använda en matris eller reguljära uttryck för att matcha text. Du kan också använda en sträng eller en matris med strängar för att matcha många meddelandeegenskaper, till exempel adress, ämne, brödtext eller namn på bifogade filer.</li><li>**Egna ordlistor:** E-postflödesregler kan innehålla långa listor med text och nyckelord och ger samma funktioner som en egen ordlista.</li><li>**Principregler per** domän: Du kan anpassa omfattningen av en e-postflödesregel så att den matchar avsändares eller mottagares domännamn, IP-adressintervall, adressnyckelord eller mönster, gruppmedlemskap och andra villkor.</li><li>**Genomsökning av** bifogade filer: Du kan skapa e-postflödesregler för att söka igenom filnamn, anknytning och innehåll i e-postbilagor.</li><li>Skicka meddelanden om principregel till avsändaren **:** Du kan avvisa meddelanden och skicka en rapport om utebliven  leverans (kallas även NDR eller icke-leveranskavisering) till avsändaren via meddelandet Avvisa meddelandet med en förklaring eller Avvisa meddelandet med åtgärden för utökad **statuskod.**</li><li>**Omdirigera eller kopiera meddelanden:** E-postflödesregler kan omdirigera, lägga till mottagare efter kopia eller Hemlig kopia, helt enkelt lägga till mottagare och andra alternativ.</li><li>**Filtrera meddelanden och ändra meddelandeattribut eller** routning : Du kan filtrera meddelanden utifrån en mängd olika villkor och sedan tillämpa en serie åtgärder på varje meddelande.</li><li>**Ändra skräppostförtroendenivån (SCL) för meddelanden som överförs**</li></ul> <p> Mer information om specifika scenarion för e-postflödesregel finns i [Procedurer för e-postflödesregel.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|**Administration**||
|Webbaserad administration|Du använder följande administrationscenter för att hantera EOP: <ul><li>Säkerhetscenter [Microsoft 365 säkerhetscenter](/microsoft-365/security/defender/overview-security-center)</li><li>Administrationscentret [Exchange administration](/exchange/exchange-admin-center)</li><li>Administrationscentret [Microsoft 365 administration](/microsoft-365/admin/admin-overview/about-the-admin-center)</li></ul>|
|PowerShell|Om din organisation har Exchange Online postlådor kan du hantera EOP-funktioner [Exchange Online PowerShell.](/powershell/exchange/exchange-online-powershell) Om din organisation inte har några Exchange Online postlådor kan du hantera EOP-funktioner [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)|
|**Rapportering och loggning**||
|Meddelandespårning|Administratörer kan följa e-postmeddelanden när de passerar genom tjänsten. Du kan avgöra om ett riktat e-postmeddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. På så sätt kan du svara effektivt på användarnas frågor, felsöka problem i e-postflödet, verifiera principändringar och förbättra behovet av att kontakta teknisk support för att få hjälp. Mer information finns i [Meddelandespårning i Säkerhets- & Kompatibilitetscenter.](message-trace-scc.md)|
|Webbaserade rapporter|E-postskyddsrapporterna i Säkerhets- & Säkerhets- och efterlevnadscenter tillhandahåller meddelandedata. Du kan till exempel övervaka hur mycket skräppost och skadlig programvara som upptäcks eller hur ofta dina e-postflödesregler matchas. Med dessa interaktiva rapporter kan du snabbt få en visuell rapport över sammanfattningsdata och öka detalj detaljinformationen om enskilda meddelanden, upp till 90 dagar. Mer information finns i Använda [rapporter för e-postskydd för att visa data om skadlig programvara, skräppost och regelidentifiering.](/exchange/monitoring/use-mail-protection-reports)|
|Granskningsloggning|Mer information finns i [Granskningsrapporter i Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).|
|**Servicenivåavtal (SLAs) och support**||
|SLA (effektiv skräppost)|\> 99%|
|False positive ratio SLA|\< 1:250,000|
|Virusidentifiering och blockering av SLA|100 % av kända virus|
|SLA för månatlig drifttid|99.999%|
|Telefon support och webb teknisk support dygnet runt sju dagar i veckan|Mer information om hjälp- och supportalternativ för EOP finns i [Hjälp och support för EOP.](help-and-support-for-eop.md)|
|**Andra funktioner**||
|Ett geo-redundant globalt nätverk av servrar|EOP körs i ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Mer information finns i avsnittet "EOP datacenter" i Exchange Online Protection [översikt](exchange-online-protection-overview.md).|
|Köer när den lokala servern inte kan ta emot e-post|Meddelanden med uppsegen post finns kvar i våra köer en dag. Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem. I genomsnitt tas meddelanden om var femte minut. Mer information finns i Vanliga frågor och [svar om EOP i kö, uppskjuten eller oaktiverad e-post.](eop-queued-deferred-and-bounced-messages-faq.yml)|
|Meddelandekryptering i Office 365 tillgänglig som en tilläggstjänst|Mer information finns i [Kryptering i Office 365](../../compliance/encryption.md).|
|
