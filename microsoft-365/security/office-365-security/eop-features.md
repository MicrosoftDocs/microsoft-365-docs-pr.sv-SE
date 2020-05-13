---
title: Funktioner i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: I följande tabell finns en lista över funktioner som är tillgängliga i EOP-tjänsten (Exchange Online Protection).
ms.openlocfilehash: fc9a13ce7a2fc8782ed260ce0ce64aec456a4d51
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213430"
---
# <a name="eop-features"></a>Funktioner i EOP

I följande tabell finns en lista över funktioner som är tillgängliga i EOP-tjänsten (Exchange Online Protection).

> [!TIP]
> [Microsoft 365 för företag-färdplanen](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) är en bra resurs för att ta reda på information om kommande nya funktioner. En bredare vy över vilka funktioner som är tillgängliga med de olika EOP-prenumerationsplanerna finns i [Beskrivning av Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

|||
|---|---|
|**Funktion**|**Beskrivning**|
|**Skydd mot skräppost**||
|Identifiering av inkommande skräppost|Mer information finns [i Skydd mot skräppost i Microsoft 365](anti-spam-protection.md). <br/><br/> I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Identifiering av skräppost utanför mängden skräppost|Skydd mot skräppost är alltid aktiverat om du använder tjänsten för att skicka utgående e-post. Mer information finns i [Skydd för utgående skräppost](outbound-spam-controls.md).|
|Backscatter skydd|Mer information finns i [Backscatter och EOP](backscatter-messages-and-eop.md).|
|Massfiltrering av e-post|EOP använder tröskelvärdet för massklagomål (BCL) för att markera massmeddelanden som skräppost. Mer information finns i följande avsnitt: <br/><br/> [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Massklagomålsnivå (BCL) i EOP](bulk-complaint-level-values.md) <br/> [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md)|
|Listor med skadlig URL-blockering|EOP använder flera URL-blocklistor som hjälper till att identifiera kända skadliga länkar i meddelanden.|
|Skydd mot nätfiske|EOP innehåller 750 000 domäner av kända spammare.|
|Skydd mot förfalskning|Mer information finns i [Skydd mot](anti-spoofing-protection.md)förfalskning .|
|**Hantering av skräppost**||
|Konfigurera betrodda avsändare och blockerade avsändare|Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md) och [Skapa blockerade avsändarelistor](create-block-sender-lists-in-office-365.md).|
|Skapa anpassade policyer mot skräppost|För större granularitet kan du skapa anpassade principer mot skräppost och tillämpa dem på angivna användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (det vill säga den löpande ordningen) för dina anpassade principer. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Konfigurera åtgärderna för skräppostfiltrerade meddelanden|Du kan till exempel ta bort innehållsfiltrerade meddelanden eller skicka dem till mappen Skräppost eller karantänen. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Internationellt skräppostfiltrering|Du kan konfigurera skräppostfiltrering för att filtrera meddelanden skrivna på specifika språk eller skickas från specifika länder eller regioner. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Hantera skräppost via Outlook eller Outlook på webben (tidigare kallat Outlook Web App)|Administratörer och slutanvändare kan skapa säkra avsänningslistor och blockerade avsändarelistor. Mer information finns [i Om inställningar för skräppost i Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <br/><br/> Om du använder EOP för att skydda lokala postlådor måste du använda katalogsynkronisering för att säkerställa att dessa inställningar synkroniseras med tjänsten. Mer information om hur du konfigurerar katalogsynkronisering finns i "Använd katalogsynkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).|
|Rapportera falska positiva identifieringar och falska negativ till Microsoft.|Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).|
|Aviseringar om skräppost i slutanvändare|Mer information finns i [Skräppostmeddelanden för slutanvändare](use-spam-notifications-to-release-and-report-quarantined-messages.md) och [Konfigurera skräppostmeddelanden för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Visa, hitta och hantera meddelanden i karantänportalen.|Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md) eller [Hitta och släppa meddelanden i karantän som användare](find-and-release-quarantined-messages-as-a-user.md).|
|Visa meddelandehuvuden i skräppost i karantän|När du har visat meddelandehuvudet i karantänen kan du också kopiera och klistra in rubriktexten i [Meddelandehuvudanalysatorn](https://mha.azurewebsites.net/) för att ta reda på vad som hände med meddelandet.|
|**Skydd mot skadlig kod**||
|Flera motor anti-malware skydd|Flera motorer mot skadlig kod hjälper till att automatiskt skydda våra kunder hela tiden.|
|Möjligheten att inaktivera filtrering av skadlig kod|Du kan inte inaktivera filtrering av skadlig kod. Vi anser att det är en viktig del av den strategi som krävs för att skydda din e-postmiljö att bidra till att ge en konsekvent och rigorös skyddsnivå för alla våra kunder. Därför aktiveras filtrering av skadlig kod automatiskt för alla kunder.|
|Malware inspektion av meddelandet kroppen och bilagor|Tjänsten kontrollerar den aktiva nyttolasten i meddelandetexten och alla meddelandebilagor för skadlig kod.|
|Varningsmeddelanden för standard eller anpassad skadlig kod|Du kan skicka ett meddelande till avsändare eller administratörer. Mer information finns i [Konfigurera principer mot skadlig kod](configure-anti-malware-policies.md).|
|Meddelanden om mottagare|Tyst karantän meddelandet eller karantän meddelandet och även leverera den med alla bilagor ersättas med en enda textfil som innehåller standard eller anpassad text. Mer information finns i [Konfigurera principer mot skadlig kod](configure-anti-malware-policies.md).|
|Vanlig filtrering av bifogade filer|Du kan aktivera och anpassa en lista över filtyper som alltid antas vara skadlig kod. Mer information finns [i Skydd mot skadlig kod i EOP](anti-malware-protection.md).|
|Skydd mot spionprogram|Skydd mot skadlig kod omfattar skydd mot virus och skydd mot spionprogram.|
|Skapa anpassade filterprinciper för skadlig kod|För större granularitet kan du skapa anpassade filterprinciper för skadlig kod och tillämpa dem på angivna användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (det vill säga den löpande ordningen) för dina anpassade principer. Mer information finns i [Konfigurera principer mot skadlig kod](configure-anti-malware-policies.md).|
|**E-postroutning och kopplingar**||
|Routning av villkorlig e-post|Mer information finns i [Scenario: Villkorad e-postroutning i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistiska eller påtvingade TLS|Opportunistiska eller påtvingade TLS finns med kontakter. Opportunistisk TLS försöker en TLS-anslutning men använder en SMTP-anslutning om TLS-anslutningen misslyckas. Tvinga TLS tvingar TLS-anslutningar, vilket innebär att meddelandet avvisas om TLS-anslutningen misslyckas. Mer information om TLS, säkerhet och kopplingar finns i [Konfigurera kopplingar för säkert e-postflöde med en partnerorganisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regional routing (begränsning av e-postflödet till en viss region)|Mer information finns i avsnittet "EOP-datacenter" i [översikten För Exchange Online Protection](exchange-online-protection-overview.md).|
|SmTP-anslutningskontrollverktyget|Mer information om hur du använder det här verktyget för att testa e-postflödet finns i [Testa e-postflödet genom att validera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).|
|Matcha underdomäner|Mer information om hur du aktiverar e-postflöde till och från underdomäner till dina accepterade domäner finns [i E-postflödet i EOP](mail-flow-in-eop.md).|
|**Regler för e-postflöde**||
|Principbaserad filtrering och åtgärder|Anpassade principer baseras på Exchange-regler för e-postflöde (kallas även transportregler). Du kan filtrera efter domän, nyckelord, filnamn, filtyp, ämnesrad, meddelandetext, avsändare, mottagare, sidhuvud och IP-adress. Mer information finns i [Regler för e-postflöde (transportregler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Filtrera efter textmönster|Regler för e-postflöde kan använda en matris eller reguljära uttryck för att matcha text. Du kan också använda en sträng eller en matris med strängar för att matcha många meddelandeegenskaper, till exempel adress-, ämnes-, brödtext- eller bifogade namn. Mer information finns i [Regler för e-postflöde (transportregler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Egna ordlistor|Regler för e-postflöde kan innehålla långa listor med text och nyckelord, vilket ger samma funktioner som en egen ordlista.|
|Policyregler per domän|Omfattningen av en regel för e-postflöde kan anpassas för att matcha avsändar- eller mottagardomännamn, IP-adressintervall, adressnyckelord eller mönster, gruppmedlemskap och andra villkor.|
|Skanning av bifogade filer|Regler kan skapas för att skanna filnamn, tillägg och innehåll i den bifogade filen.|
|Skicka principregelmeddelanden till avsändaren|Du kan avvisa meddelanden och skicka en rapport om utebliven leverans (kallas även NDR eller avvisningsmeddelande) till avsändaren via **meddelandet Avvisa meddelandet med förklaringen** eller Avvisa meddelandet med åtgärden förbättrad **statuskod.** Mer information finns [i Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Omdirigera eller kopiera meddelanden|Regler för e-postflöde kan omdirigeras, lägga till mottagare efter Kopia eller Hemlig kopia, helt enkelt lägga till mottagare och andra alternativ. Mer information finns [i Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Justera regelprioriteten för flera regler|Använd administrationscentret för Exchange om du vill ändra i vilken ordning regler bearbetas.|
|Filtrera meddelanden och ändra sedan routning eller attribut för ett meddelande|Du kan filtrera meddelanden baserat på en mängd olika villkor och sedan tillämpa en serie åtgärder på varje meddelande. Mer information finns i [Regler för e-postflöde (transportregler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Ändra spam förtroendenivå (SCL) för ett meddelande efter regel.|Du kan granska ett meddelande under överföringen och tilldela ett skräppostförtroendenivå till det baserat på kriterier som du väljer. Mer information finns i [Använda regler för e-postflöde för att ange scl (Spam Confidence Level) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Granska bifogade filer i meddelanden|Du kan undersöka innehållet i en bifogad fil eller egenskaperna hos en bifogad fil och definiera en åtgärd som ska vidtas baserat på vad som hittas. Mer information finns i [Använda regler för e-postflöde för att granska bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Administration**||
|Webbaserad administration|Administratörer kan hantera tjänsten i Administrationscenter för Exchange (EAC), som stöds på 60 språk. Mer information finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).|
|Katalogsynkronisering|Katalogsynkronisering är tillgängligt via Azure Active Directory Sync-verktyget. Mer information finns i avsnittet "Använd katalogsynkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).|
|Katalogbaserad kantblockering (DBEB)|Med DBEB-funktionen kan du avvisa meddelanden för ogiltiga mottagare vid tjänstens nätverksper perimeter. MED DBEB kan administratörer lägga till e-postaktiverade mottagare i Microsoft 365 och blockera alla meddelanden som skickas till e-postadresser som inte finns i Microsoft 365. Mer information om hur du konfigurerar DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|Powershell|Fullständig EOP-funktionalitet finns i fristående EOP PowerShell. Mer information finns i [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).|
|**Rapportering och loggning**||
|Meddelandespårning|Administratörer kan följa e-postmeddelanden när de passerar genom tjänsten. Du kan avgöra om ett riktat e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten. På så sätt kan du effektivt svara på användarnas frågor, felsöka problem med e-postflödet, validera principändringar och minska behovet av att kontakta teknisk support för att få hjälp. Mer information finns [i Meddelandespårning i Säkerhets- & Compliance Center](message-trace-scc.md).|
|Webbaserade rapporter|E-postskyddsrapporterna i Security & Compliance Center tillhandahåller meddelandedata. Du kan till exempel övervaka hur mycket skräppost och skadlig kod som upptäcks eller hur ofta reglerna för e-postflödet matchas. Med dessa interaktiva rapporter kan du snabbt få en visuell rapport med sammanfattningsdata och öka detaljnivån i information om enskilda meddelanden, så långt tillbaka som 90 dagar. Mer information finns i [Använda e-postskyddsrapporter för att visa data om skadlig kod, skräppost och regelidentifieringar](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Granskningsloggning|Rapporten för administratörsrollgrupp och administratörsgranskningsloggen är tillgängliga för EOP-administratörer. Mer information finns [i Granskningsrapporter i EOP](auditing-reports-in-eop.md).|
|**Servicenivåavtal (SLA) och support**||
|Spam effektivitet SLA|\>99%|
|Falskt positivt förhållande SLA|\<1:250,000|
|Virusdetektering och blockering av SLA|100% av kända virus|
|Månatliga drifttid SLA|99.999%|
|Telefon- och webbteknisk support 24 timmar om dygnet, sju dagar i veckan|Mer information om EOP:s hjälp- och supportalternativ finns i [Hjälp och support för EOP](help-and-support-for-eop.md).|
|**Andra funktioner**||
|Ett geouppsagt globalt nätverk av servrar|EOP körs på ett världsomspännande nätverk av datacenter som är utformade för att ge bästa möjliga tillgänglighet. Mer information finns i avsnittet "EOP-datacenter" i [översikten över Exchange Online Protection](exchange-online-protection-overview.md).|
|Meddelandeköer när den lokala servern inte kan ta emot e-post|Meddelanden i uppskov kvar i våra köer för en dag. Försök att skicka meddelanden baseras på felet vi får tillbaka från mottagarens e-postsystem. I genomsnitt görs ett nytt försök var femte minut. Mer information finns i Vanliga frågor och [svar om EOP i kö, uppskjutna och studsade meddelanden](eop-queued-deferred-and-bounced-messages-faq.md).|
|Office 365-meddelandekryptering tillgänglig som tilläggstjänst|Mer information finns [i Kryptering i Office 365](../../compliance/encryption.md).|
