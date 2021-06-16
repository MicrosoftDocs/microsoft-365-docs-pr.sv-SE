---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lär dig Exchange Online Protection (EOP) kan skydda din lokala e-postorganisation i fristående och hybridmiljöer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a925b251ff79aec5acaa0b2c1da2aee3f5a6d70d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930169"
---
# <a name="exchange-online-protection-overview"></a>Översikt över Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) är den molnbaserade filtreringstjänsten som skyddar organisationen mot skräppost, skadlig programvara och andra e-posthot. EOP ingår i alla Microsoft 365 med Exchange Online postlådor.

> [!NOTE]
> EOP är också tillgängligt för sig själv för att skydda lokala postlådor och i hybridmiljöer för att skydda lokala Exchange postlådor. Mer information finns i [Fristående Exchange Online Protection](/exchange/standalone-eop/standalone-eop).

Anvisningarna för att konfigurera säkerhetsfunktionerna i EOP och en jämförelse med den extra säkerhet du får i Microsoft Defender för Office 365, [se skydda mot hot.](protect-against-threats.md) De rekommenderade inställningarna för EOP-funktioner finns i [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md)

Resten av den här artikeln förklarar hur EOP fungerar och de funktioner som är tillgängliga i EOP.

## <a name="how-eop-works"></a>Så här fungerar EOP

För att förstå hur EOP fungerar hjälper det dig att se hur det bearbetar inkommande e-post:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Bild av e-post från Internet eller kundfeedback som passerar till EOP och via Anslutning, Skadlig programvara, Filtrering av e-postflödesregler och innehållsfiltrering, innan bedömning av antingen skräppost eller karantän, eller slutanvändarens e-postleverans.":::

1. När ett inkommande meddelande kommer in i EOP passerar det först genom anslutningsfiltrering, som kontrollerar avsändarens rykte. Majoriteten av skräpposten stoppas nu och avvisas av EOP. Mer information finns i [konfigurera anslutningsfilter](configure-the-connection-filter-policy.md).

2. Sedan kontrolleras meddelandet om det finns skadlig programvara. Om skadlig programvara finns i meddelandet eller i de bifogade filer, dirigeras meddelandet till en administratörs enda lagringslager i karantän. Mer information om skydd mot skadlig programvara finns [i Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)

3. Meddelandet fortsätter med principfiltrering, där det utvärderas mot alla e-postflödesregler (kallas även transportregler) som du har skapat. En regel kan till exempel skicka ett meddelande till en chef när ett meddelande tas emot från en viss avsändare.

   I en lokal organisation med Exchange Enterprise CAL med tjänstelicenser utförs [även DLP-kontroller (Data Loss Prevention)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) i EOP i det här läget.

4. Meddelandet passerar genom innehållsfiltrering (skydd mot skräppost och skydd mot förfalskning) där skadliga meddelanden identifieras som skräppost, skräppost med högt förtroende, nätfiske, nätfiske och massutskick (principer för skräppostskydd) eller förfalskning (förfalskningsinställningar i principer för skydd mot nätfiske). Du kan konfigurera vilken åtgärd som ska vidtas på meddelandet baserat på filtreringen av bedömning (karantän, flytta till mappen Skräppost osv.). Mer information finns i Konfigurera [principer för skydd mot skräppost och](configure-your-spam-filter-policies.md) Konfigurera principer för skydd mot [nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

Ett meddelande som klarar alla de här skyddslageren levereras till mottagarna.

Mer information finns i [Ordning och prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)

### <a name="eop-datacenters"></a>EOP-datacenter

EOP körs i ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Om till exempel ett datacenter blir otillgängligt, dirigeras e-postmeddelanden automatiskt till ett annat datacenter utan avbrott i tjänsten. Servrar i varje datacenter tar emot meddelanden åt dig, vilket innebär en åtskillnad mellan organisationen och Internet, vilket minskar belastningen på servrarna. Genom detta tillgängliga nätverk kan Microsoft se till att e-post når din organisation i tid.

EOP utför belastningsutjämning mellan datacenter men bara i en region. Om du har etablerat dig i en region bearbetas alla meddelanden med e-postdirigeringen för den regionen. I följande lista visas hur regional e-postdirigering fungerar för EOP-datacenter:

- I Europa, Mellanöstern och Afrika (EMEA) finns alla Exchange Online-postlådor i EMEA-datacenter och alla meddelanden dirigeras via EMEA-datacenter för EOP-filtrering.
- I Asia-Pacific (APAC) finns alla Exchange Online-postlådor i APAC-datacenter och meddelandena dirigeras just nu via APAC-datacenter för EOP-filtrering.
- I Amerika distribueras tjänster på följande platser:
  - Sydamerika: Exchange Online finns i datacenter i Brasilien och Chile. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
  - Kanada: Exchange Online finns i datacenter i Kanada. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
  - USA: Exchange Online postlådor finns i datacenter i USA. Alla meddelanden dirigeras genom lokala datacenter för EOP-filtrering. Meddelanden i karantän lagras i det datacenter där klientorganisationen finns.
- För Government Community Cloud (GCC) finns alla Exchange Online-postlådor i USA:s datacenter och alla meddelanden dirigeras via usa-datacenter för EOP-filtrering.

### <a name="eop-features"></a>Funktioner i EOP

Det här avsnittet innehåller en översikt över de huvudfunktioner som är tillgängliga i EOP.

Mer information om krav, viktiga begränsningar och funktionstillgänglighet för alla EOP-abonnemang finns [i Exchange Online Protection tjänstbeskrivning.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**Anmärkningar**:

- EOP använder flera URL-blockeringslistor som hjälper till att identifiera kända skadliga länkar i meddelanden.
- EOP använder en omfattande lista med domäner som är kända för att skicka skräppost.
- EOP använder flera sökmotorer mot skadlig programvara för att alltid skydda våra kunder.
- EOP kontrollerar den aktiva nyttolasten i meddelandets brödtext och alla bifogade filer för meddelanden kontrollerar skadlig kod.
- Rekommenderade värden för skyddsprinciper finns i [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md)
- Du kan läsa snabbt om hur du konfigurerar [skyddsprinciper i Skydda mot hot.](protect-against-threats.md)

<br>

****
|Funktion|Kommentarer|
|---|---|
|**Skydd**||
|Skydd mot skadlig programvara|[Skydd mot skadlig programvara i EOP](anti-malware-protection.md) <p> [Vanliga frågor och svar om skydd mot skadlig kod](anti-malware-protection-faq-eop.yml) <p> [Konfigurera principer för skydd mot skadlig programvara i EOP](configure-anti-malware-policies.md)|
|Inkommande skräppostskydd|[Skydd mot skräppost i EOP](anti-spam-protection.md) <p> [Vanliga frågor och svar om skydd mot skräppost](anti-spam-protection-faq.yml) <p> [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
|Utgående skräppostskydd|[Skydd mot utgående skräppost i EOP](outbound-spam-controls.md) <p> [Konfigurera utgående skräppostfiltrering i EOP](configure-the-outbound-spam-policy.md) <p> [Kontrollera automatisk vidarebefordran av extern e-post i Microsoft 365](external-email-forwarding.md)|
|Anslutningsfiltrering|[Konfigurera anslutningsfiltrering](configure-the-connection-filter-policy.md)|
|Skydd mot nätfiske|[Principer mot nätfiske i Microsoft 365](set-up-anti-phishing-policies.md) <p> [Konfigurera principer för skydd mot nätfiske i EOP](configure-anti-phishing-policies-eop.md)|
|Skydd mot förfalskning|[Falska intelligensinsikter i EOP](learn-about-spoof-intelligence.md) <p> [Hantera Klientorganisationens Tillåt/blockera listan](tenant-allow-block-list.md)|
|ZAP (Zero-hour auto purge) för levererad skadlig programvara, skräppost och nätfiskemeddelanden|[ZAP i Exchange Online](zero-hour-auto-purge.md)|
|Förvalda säkerhetsprinciper|[Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365](preset-security-policies.md) <p> [Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365](configuration-analyzer-for-security-policies.md)|
|Klientorganisationslistan över tillåtna/blockerade|[Hantera Klientorganisationens Tillåt/blockera listan](tenant-allow-block-list.md)|
|Spärra listor för meddelandeavsändare|[Skapa spärrade avsändarlistor i EOP](create-block-sender-lists-in-office-365.md)|
|Tillåta listor för meddelandeavsändare|[Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md)|
|Katalogbaserat gränsblockering (DBEB)|[Använda katalogbaserad Edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Karantän och insändning**||
|Administratörsinskick|[Använd administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft](admin-submission.md)|
|Användarinskickade användare (anpassad postlåda)|[Princip för användarinskick](user-submission.md)|
|Karantän – administratörer|[Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md) <p> [Vanliga frågor och svar om meddelanden i karantän](quarantine-faq.yml) <p> [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Meddelandehuvuden för antiskräppost i Microsoft 365](anti-spam-message-headers.md) <p> Du kan analysera meddelanderubrikerna i meddelanden i karantän med hjälp av [Analysverktyg för meddelanderubrik på](https://mha.azurewebsites.net/).|
|Karantän – slutanvändare|[Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Använda skräppost-aviseringar för användare för att släppa och rapportera meddelanden i karantän](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**E-postflöde**||
|E-postflödesregler|[E-postflödesregler (transportregler) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Villkor och undantag för e-postflödesregel (predikat) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Åtgärder för e-postflödesregel i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Hantera e-postflödesregler i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Procedurer för e-postflödesregel i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Godkända domäner|[Hantera godkända domäner i Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Kopplingar|[Konfigurera e-postflödet med kopplingar i Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Förbättrad filtrering för kopplingar|[Förbättrad filtrering för kopplingar i Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Övervakning**||
|Meddelandespårning|[Meddelandespårning](message-trace-scc.md) <p> [Meddelandespårning i Exchange administrationscenter](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Skicka e& och samarbetsrapporter|[Visa säkerhetsrapporter för e-post](view-email-security-reports.md)|
|E-postflödesrapporter|[Visa flödesrapporter för e-post](view-mail-flow-reports.md) <p> [E-postflödesrapporter Exchange administrationscenter](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Insikter i e-postflöde|[Insikter i e-postflöde](mail-flow-insights-v2.md) <p> [Insikter om e-postflöde Exchange administrationscentret](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Granskningsrapporter|[Granskningsrapporter i Exchange administrationscenter](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Aviseringsprinciper|[Aviseringsprinciper](../../compliance/alert-policies.md)|
|**Servicenivåavtal (SLAs) och support**||
|SLA (effektiv skräppost)|\> 99%|
|False positive ratio SLA|\< 1:250,000|
|Virusidentifiering och blockering av SLA|100 % av kända virus|
|SLA för månatlig drifttid|99.999%|
|Telefon support och webb teknisk support dygnet runt sju dagar i veckan|[Hjälp och support för EOP.](help-and-support-for-eop.md)|
|**Andra funktioner**||
|Ett geo-redundant globalt nätverk av servrar|EOP körs i ett globalt nätverk av datacenter som är utformade för att ge bästa tillgänglighet. Mer information finns i avsnittet [om EOP-datacenter](#eop-datacenters) tidigare i den här artikeln.|
|Köer när den lokala servern inte kan ta emot e-post|Meddelanden med uppsegen post finns kvar i våra köer en dag. Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem. I genomsnitt tas meddelanden om var femte minut. Mer information finns i Vanliga frågor och [svar om EOP i kö, uppskjuten eller oaktiverad e-post.](eop-queued-deferred-and-bounced-messages-faq.yml)|
|Meddelandekryptering i Office 365 tillgänglig som ett tillägg|Mer information finns i [Kryptering i Office 365](../../compliance/encryption.md).|
|||
