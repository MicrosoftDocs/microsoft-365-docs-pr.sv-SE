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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: I följande tabell finns en lista med funktioner som är tillgängliga i e-postfiltret för Exchange Online Protection (EOP).
ms.openlocfilehash: 58893cd4a4d6c90c8d19de5a6b2f0d108ee797e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202933"
---
# <a name="eop-features"></a>Funktioner i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I följande tabell finns en lista med funktioner som är tillgängliga i e-postfiltret för Exchange Online Protection (EOP).

> [!TIP]
> [Microsoft 365 för Business-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) är en bra resurs för att få information om kommande nya funktioner. Mer information om vilka funktioner som är tillgängliga med de olika abonnemangen för EOP finns i [Beskrivning av Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Funktion|Beskrivning|
|---|---|
|**Skydd mot skräppost**||
|Inkommande spam för skräp post|Mer information finns i [skydd mot skräp post i Microsoft 365](anti-spam-protection.md). <br/><br/> I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Utgående skräp identifiering|Utgående skydd mot skräp post är alltid aktiverat om du använder tjänsten för att skicka utgående e-post. Mer information finns i [utgående skräp post skydd](outbound-spam-controls.md).|
|Skydd mot bakdett|Mer information finns i avsnittet om att läsa- [och EOP](backscatter-messages-and-eop.md).|
|Mass filtrering|EOP använder Mass avgränsaren för klagomål (BCL) för att markera Mass utskick av e-postmeddelanden. Mer information finns i följande avsnitt: <br/><br/> [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Bulk klagomål (BCL) i EOP](bulk-complaint-level-values.md) <br/> [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md)|
|Listor med skadlig URL-block|EOP använder flera URL-adressblock som hjälper dig att identifiera kända illasinnade länkar i meddelanden.|
|Skydd mot nätfiske|EOP innehåller 750 000-domäner för kända skräp post avsändare.|
|Skydd mot förfalskning|Mer information finns i [skydd mot förfalskning](anti-spoofing-protection.md).|
|**Hantering av skräp post**||
|Konfigurera betrodda avsändare och spärrade avsändare|Mer information finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md) och [skapa spärrade avsändare](create-block-sender-lists-in-office-365.md).|
|Skapa anpassade principer för skräp post|Om du vill ha större precision kan du skapa anpassade principer för skräp post och tillämpa dem på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid högre prioritet än standard principen, men du kan ändra prioriteten (d.v.s. den kör ande ordningen) på dina anpassade principer. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Konfigurera åtgärderna för skräp post – filtrerade meddelanden|Du kan till exempel ta bort innehåll – filtrerade meddelanden eller skicka dem till mappen skräp post eller karantänen. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Internationell skräp filtrering|Du kan konfigurera filtrering av skräp post för att filtrera meddelanden skrivna på ett visst språk eller skickas från specifika länder eller regioner. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).|
|Hantera skräp post via Outlook eller Outlook på webben (tidigare Outlook Web App)|Administratörer och slutanvändare kan skapa säkra avsändare och spärrade avsändare. Mer information finns i [om inställningar för skräp post i Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <br/><br/> Om du använder EOP för att skydda lokala post lådor bör du använda profilsynkronisering för att säkerställa att dessa inställningar synkroniseras med tjänsten. Mer information om hur du konfigurerar katalog synkronisering finns i "använda katalog synkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).|
|Rapportera falska positiva och falska negativa negativ till Microsoft.|Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).|
|Meddelanden om skräp post för slutanvändare|Mer information finns i [aviseringar](use-spam-notifications-to-release-and-report-quarantined-messages.md) om slutanvändare och [konfigurering av skräp post meddelanden](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Visa, hitta och hantera meddelanden i karantän portalen.|Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md) eller [hitta och släppa meddelanden i karantän som en användare](find-and-release-quarantined-messages-as-a-user.md).|
|Visa skräp post meddelanden – karantän rubriker|När du har granskat meddelande huvudet i karantänen kan du också kopiera och klistra in sidhuvudet i [meddelande rubrik analys](https://mha.azurewebsites.net/) för att ta reda på vad som hände med meddelandet.|
|**Skydd mot skadlig kod**||
|Skydd mot skadlig program vara med flera motorer|Flera motorer med skadlig program vara hjälper till att automatiskt skydda våra kunder.|
|Möjlighet att inaktivera filter mot skadlig kod|Du kan inte inaktivera filter mot skadlig kod. Vi tror att vi erbjuder en konsekvent och rigorös skydds nivå för alla våra kunder är en viktig del av strategin för djupgående försvar som behövs för att skydda din e-postmiljö. Därför aktive ras filtrering av skadlig kod automatiskt för alla kunder.|
|Kontroll av skadlig program vara i meddelandets brödtext och bifogade filer|Tjänsten kontrollerar den aktiva nytto lasten i meddelandets brödtext och alla bifogade filer för skadlig program vara.|
|Standard meddelanden och aviseringar om skadlig program vara|Du kan skicka ett meddelande till avsändare eller administratörer. Mer information finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).|
|Mottagar aviseringar|Placera meddelandet i karantän eller placera det i karantän och leverera det också med alla bilagor ersatta med en enda textfil som innehåller vanlig eller anpassad text. Mer information finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).|
|Filtrering av vanliga bilagor|Du kan aktivera och anpassa en lista med filtyper som alltid antas vara skadlig program vara. Mer information finns i [skydda mot skadlig program vara i EOP](anti-malware-protection.md).|
|Skydd mot spionprogram|Skydd mot skadlig program vara omfattar Antivirus skydd och skydd mot spionprogram.|
|Skapa anpassade filter principer för skadlig kod|För högre precision kan du skapa anpassade filter principer för skadlig kod och tillämpa dem på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid högre prioritet än standard principen, men du kan ändra prioriteten (d.v.s. den kör ande ordningen) på dina anpassade principer. Mer information finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).|
|**E-postdirigering och kopplingar**||
|Villkorsstyrd e-postdirigering|Mer information finns i [Scenario: villkorlig e-postdirigering i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistic eller påtvingad TLS|Opportunistic eller Användarkonfigurerad TLS är tillgängligt med kopplingar. Opportunistic TLS försöker ansluta till en TLS-anslutning men använder en SMTP-anslutning om TLS-anslutningen Miss lyckas. Tvinga fram TLS-anslutningar, vilket innebär att meddelandet nekas om anslutningen Miss lyckas. Mer information om TLS, säkerhet och anslutningar finns i [Konfigurera kopplingar för säkert e-postflöde med en partner organisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regional routing (begränsningen för e-postflöden till en viss region)|Mer information finns i avsnittet "EOP Data Center" i [Exchange Online Protection-översikten](exchange-online-protection-overview.md).|
|SMTP Connectivity Checker|Om du vill ha mer information om hur du använder verktyget för att testa e-postflödet läser du [Testa e-postflödet genom att verifiera dina Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)|
|Matcha under domäner|Mer information om hur du aktiverar e-postflöde till och från under domäner för godkända domäner finns i [e-postflöde i EOP](mail-flow-in-eop.md).|
|**Regler för e-postflöde**||
|Principbaserad filtrering och åtgärder|Anpassade principer baseras på regler för Exchange-flöden (kallas även transport regler). Du kan filtrera efter domän, nyckelord, fil namn, filtyp, ämne, ämnesrad, meddelande text, avsändare, mottagare, rubrik och IP-adress. Mer information finns i [regler för e-postflöde (transport regler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Filtrera efter text mönster|Regler för e-postflöde kan använda en matris eller vanliga uttryck för att matcha text. Du kan också använda en sträng eller en matris med strängar för att matcha många meddelande egenskaper, till exempel adress, ämne, brödtext eller namn på bifogade filer. Mer information finns i [regler för e-postflöde (transport regler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Egna ord listor|Regler för e-postflöde kan inkludera långa listor med text och nyckelord, vilket ger samma funktioner som en egen ord lista.|
|Princip regler per domän|Omfattningen av en regel för e-postflöde kan anpassas så att den matchar avsändare eller mottagares domän namn, IP-adressintervall, adress nyckelord eller-mönster, grupp medlemskap och andra villkor.|
|Bilage genomsökning|Du kan skapa regler för att söka igenom fil namnet, tillägget och innehållet i den bifogade filen.|
|Skicka policy regel meddelanden till avsändaren|Du kan avvisa meddelanden och skicka en rapport om utebliven leverans (kallas även för ett NDR-eller studs meddelande) till avsändaren genom att **avvisa meddelandet med förklaring** eller **avvisa meddelandet med den förbättrade status kods** åtgärden. Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Omdirigera eller kopiera meddelanden|Regler för e-postflöden kan omdirigera, lägga till mottagare via kopia eller Hemlig kopia, Lägg till mottagare och andra alternativ. Mer information finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Justera regel prioriteten för flera regler|Använd administrations centret för Exchange för att ändra i vilken ordning reglerna behandlas.|
|Filtrera meddelanden och sedan ändra routning eller attribut för ett meddelande|Du kan filtrera meddelanden baserat på en mängd olika villkor och sedan använda en serie åtgärder för varje meddelande. Mer information finns i [regler för e-postflöde (transport regler) i Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Ändra säkerhets nivån för skräp post (SCL) för ett meddelande enligt regel.|Du kan inspektera ett meddelande och tilldela en säkerhets nivå för skräp post baserat på de kriterier du väljer. Mer information finns i [använda regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Kontrol lera bifogade filer|Du kan granska innehållet i en bilaga eller egenskaperna för en bifogad fil och definiera en åtgärd som ska utföras baserat på vad som hittas. Mer information finns i [använda regler för e-postflöde för att kontrol lera bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Administration**||
|Webbaserad administration|Administratörer kan hantera tjänsten i administrations centret för Exchange (UK), som stöds i 60-språk. Mer information finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).|
|Katalogsynkronisering:|Directory-synkronisering är tillgänglig via Azure Active Directory Sync Tool. Mer information finns i avsnittet "använda katalog synkronisering för att hantera e-postanvändare" i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).|
|Mappbaserade Edge-blockering (DBEB)|Med funktionen DBEB kan du avvisa meddelanden om ogiltiga mottagare i tjänst nätverkets perimeter. DBEB låter administratörer lägga till e-postaktiverade mottagare i Microsoft 365 och blockera alla meddelanden som skickas till e-postadresser som inte finns i Microsoft 365. Mer information om hur du konfigurerar DBEB finns i [använda katalogbaserade kant spärr för att neka meddelanden skickade till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|PowerShell|Fullständiga funktioner för EOP är tillgängliga i fristående EOP PowerShell. Mer information finns i [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).|
|**Rapportering och loggning**||
|Meddelande spårning|Administratörer kan följa e-postmeddelanden när de passerar via tjänsten. Du kan bestämma om ett riktat e-postmeddelande har tagits emot, nekats, uppskjuts eller levererats av tjänsten. Detta gör att du kan besvara användarnas frågor effektivt, felsöka e-postflöden, validera princip ändringar och minska behovet av att kontakta teknisk support för att få hjälp. Mer information finns i [meddelande spårning i säkerhets & Compliance Center](message-trace-scc.md).|
|Webbaserade rapporter|Rapporterna för e-postskydd i säkerhets & Compliance tillhandahåller meddelande data. Du kan till exempel övervaka hur mycket skräp post och skadlig kod som identifieras eller hur ofta dina e-postflöden matchas. Med dessa interaktiva rapporter kan du snabbt få en visuell rapport om sammanfattnings data och öka detalj nivån till information om enskilda meddelanden, så långt tillbaka som 90 dagar. Mer information finns i [använda e-postskydds rapporter för att visa information om skadlig program vara, skräp post och identifiering av regler](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Gransknings loggning|Roll gruppen administratör och administratörs gransknings loggen är tillgängliga för EOP-administratörer. Mer information finns i [granska rapporter i EOP](auditing-reports-in-eop.md).|
|**Service nivå avtal (SLAs) och support**||
|Service nivå avtal för skräp post|\> 99%|
|Falskt positivt förhållande SLA|\< 1:250000|
|SLA för virus avkänning och blockering|100% kända virus|
|Månads vis drift tid SLA|99,999%|
|Teknisk telefon och webb support dygnet runt, sju dagar i veckan|Mer information om EOP hjälp-och support alternativ finns i [Hjälp och support för EOP](help-and-support-for-eop.md).|
|**Andra funktioner**||
|Ett Geo-redundant globalt nätverk av servrar|EOP körs i ett världs omfattande nätverk av data Center som är utformade för att ge bästa möjliga tillgänglighet. Mer information finns i avsnittet "EOP data centers" i [Exchange Online Protection Overview](exchange-online-protection-overview.md).|
|Meddelande köer när den lokala servern inte kan använda e-post|Meddelanden i tids försvaret kvarstår i våra köer under en dag. Försök att försöka igen baseras på det fel vi får tillbaka från mottagarens e-postsystem. I genomsnitt görs meddelanden om fem minuter. Mer information finns i avsnittet [om vanliga frågor och svar om EOP i kö](eop-queued-deferred-and-bounced-messages-faq.md).|
|Office 365 meddelande kryptering är tillgängligt som tilläggs tjänst|Mer information finns i [kryptering i Office 365](../../compliance/encryption.md).|
|
