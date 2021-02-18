---
title: Visa e-postflödesrapporter på instrumentpanelen Rapporter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om e-postflödesrapporterna som är tillgängliga i instrumentpanelen Rapporter i säkerhets- & Efterlevnadscenter.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286723"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Visa e-postflödesrapporter i instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Förutom e-postflödesrapporterna som är [](mail-flow-insights-v2.md) tillgängliga på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & finns det flera olika e-postflödesrapporter på instrumentpanelen Rapporter som hjälper dig att övervaka Din Microsoft 365-organisation.

Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-these-reports)du visa de här rapporterna i Säkerhets- och [& genom](https://protection.office.com) att gå till  \> **instrumentpanelen Rapporter.** Om du vill gå direkt till instrumentpanelen Rapporter öppnar du <https://protection.office.com/insightdashboard> .

![Instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Kopplingsrapport

Kopplingsrapporten **visar** e-postflödesaktivitet [för inkommande och](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) utgående anslutningar som är konfigurerade för din organisation.

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går **till** instrumentpanelen \> **Rapporter** och väljer **Kopplingsrapport.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget för kopplingsrapport på instrumentpanelen Rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Rapportvy för kopplingsrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data efter: E-postflöde:** I det här diagrammet visas antalet inkommande och utgående meddelanden ordnade efter:

  - **Totalt**
  - **Från Internet utan anslutning**
  - **Till Internet utan anslutning**
  - En specifik koppling som du har konfigurerat.

  Om du vill isolera data i diagrammet använder du Visa data för kontroll **och** väljer ett av de här alternativen eller **Allt e-postflöde.**

  ![Visa data efter e-postflöde i kopplingsrapporten](../../media/connector-report-view-data-by-mail-flow.png)

- **Visa data efter: TLS-användning:** Det här diagrammet visar procentandelen TLS-versionsanvändning (Transport Layer Security) för e-postflöde.

  Om du vill isolera data i diagrammet använder du **Visa data för kontroll** och väljer ett av följande alternativ:

  - **Allt e-postflöde**
  - **Från Internet utan anslutning**
  - **Till Internet utan anslutning**
  - En specifik koppling som du har konfigurerat.

  ![Visa data efter TLS-användning i kopplingsrapporten](../../media/connector-report-view-data-by-tls-usage.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

### <a name="details-table-view-for-the-connector-report"></a>Detaljtabellvy för kopplingsrapporten

Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:

- **Datum**
- **Kopplingsriktning och namn**
- **Kopplingstyp**
- **Tvingad TLS?**: Värdet **Sant** eller **Falskt.**
- **Ingen TLS** (procent)
- **TLS 1,0** (procent)
- **TLS 1,1** (procent)
- **TLS 1,2** (procent)
- **Volym:** Antalet meddelanden.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="exchange-transport-rule-report"></a>Regelrapport för Exchange-transport

I **regelrapporten för Exchange-transport** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går **till** instrumentpanelen \> **Rapporter** och väljer **Exchange-transportregel.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget för Exchange-transportregel på instrumentpanelen Rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Rapportvy för Exchange-transportregelrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data efter: Exchange-transportregler** \> **Radbryt för: Riktning:** Det här diagrammet visar antalet **ingående** och **utgående** meddelanden som påverkades av transportreglerna.

- **Visa data efter: Exchange-transportregler** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages. Du anger allvarlighetsnivån som en åtgärd i regeln (Granska den här regeln med **allvarlighetsnivå** eller _AngeAuditSeverity_). Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Visa data efter: DLP Exchange-transportregler** \> **Åtser sig: Riktning:** I det här  diagrammet visas antalet **ingående** och utgående meddelanden som påverkades av DLP-transportregler (Data Loss Prevention). Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:

  - **Visa data för: Alla DLP-transportregler**
  - **Visa data för: Komprometterade användare**
  - **Visa data för: Låg mängd innehåll upptäckt av U.S. Act**

- **Visa data efter: DLP Exchange-transportregler** \> **Break down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules. Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:

  - **Visa data för: Alla DLP-transportregler**
  - **Visa data för: Komprometterade användare**
  - **Visa data för: Låg mängd innehåll upptäckt av U.S. Act**

Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Allvarlighetsvärden

![Rapportvy i exchange-transportregelrapporten](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detaljtabellvy för rapporten Exchange-transportregel

Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:

- **Visa data efter: Exchange-transportregler:**

  - **Datum**
  - **Transportregel**
  - **Ämne**
  - **Avsändarens adress**
  - **Mottagaradress**
  - **Allvarlighetsgrad**
  - **Riktning**

- **Visa data efter: DLP Exchange-transportregler:**

  - **Datum**
  - **DLP-princip**
  - **Transportregel**
  - **Ämne**
  - **Avsändarens adress**
  - **Mottagaradress**
  - **Allvarlighetsgrad**
  - **Riktning**

Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Allvarlighetsvärden

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="forwarding-report"></a>Vidarebefordransrapport

I **vidarebefordransrapporten** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online-postlådor. Vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan ange ett komprometterat konto.

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer **Vidarebefordransrapport.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget för vidarebefordransrapport på instrumentpanelen Rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Rapportvy för vidarebefordransrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Vidarebefordransmetoder:** Följande metoder visas:

  - **Transportregel:** Kallas även [e-postflödesregler.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postlåderegel:** Kallas även [inkorgsregler.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Vyn Vidarebefordransmetoder i rapporten om vidarebefordran](../../media/forwarding-report-forwarding-methods.png)

- **Visa data för: Domäner för vidarebefordran:** I den här vyn visas de mottagardomäner som är destinationer för vidarebefordran.

  ![Vyn Vidarebefordra domäner i rapporten Om vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- **Visa data för: Vidarebefordrare:** Följande vidarebefordrare visas:

  - **Transportregel**
  - Postlådan som innehåller vidare vidarebefordrans inkorgsregeln.

  ![Vyn Vidarebefordrare i rapporten Vidarebefordran](../../media/forwarding-report-forwarders.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

### <a name="details-table-view-for-the-forwarding-report"></a>Tabellvyn Information för vidarebefordransrapporten

Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:

- **Vidarebefordrare:** Värdet **Transport-regeln eller** postlådan som innehåller vidare vidarebefordrans inkorgsregeln.
- **Vidarebefordranstyp:** **Värdepostlåderegel** eller **transportregel.**
- **Mottagarens namn**
- **Mottagardomän**
- **Information:** Det här är GUID-värdet för e-postflödesregeln eller RuleIdentity-värdet för inkorgsregeln.
- **Antal**
- **Första vidarebefordransdatum**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="mailflow-status-report"></a>Statusrapport för e-postflöde

Statusrapporten **e-postflöde** liknar [](#sent-and-received-email-report)rapporten Skickad och mottagen e-post, med ytterligare information om tillåtna eller blockerade e-postmeddelanden i edge. Det här är den enda rapporten som innehåller information om gränsskydd och visar hur mycket e-post som blockeras innan de tillåts i tjänsten för utvärdering av Exchange Online Protection (EOP). Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.
Om du vill visa rapporten öppnar du [Säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** \> **Rapporter** och väljer **Statusrapport för e-postflöde.** Gå direkt till statusrapporten **för e-postflödet** genom att <https://protection.office.com/mailflowStatusReport> öppna.

![Widget för statusrapport i e-postflöde på instrumentpanelen Rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typvy för statusrapporten För e-postflöde

När du öppnar rapporten är **fliken** Typ markerad som standard. Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.
- **Riktning:**

  - **Inkommande**
  - **Utgående**
  - **Årsantal:** antalet är för meddelanden inom en klientorganisation, dvs. avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från **Inkommande** och **Utgående)**

- **Typ:**

  - **Bra e-post**
  - **Skadlig programvara**
  - **Skräppost**
  - **Edge-skydd**
  - **Regelmeddelanden**
  - **Nätfiske-e-post**

Diagrammet är ordnat efter **typvärdena.**

Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.

Datatabellen innehåller följande information:

- **Riktning**
- **Typ**
- **24 timmar**
- **3 dagar**
- **7 dagar**
- **15 dagar**
- **30 dagar**

Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:

- **Nätfiskemeddelande:** Det här valet tar dig till [statusrapporten om skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)
- **Skadlig programvara i** e-postmeddelanden: Det här valet tar dig [till statusrapporten om skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)
- **Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)
- **Blockerad skräppost i Edge:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)

**Exportera:**

I detaljvyn kan du bara exportera data för en dag. Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.

Varje exporterad CSV-fil är begränsad till 150 000 rader. Om dagens data innehåller fler än 150 000 rader skapas flera CSV-filer.

![Typvy i statusrapporten för E-postflöde ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Vyn Riktning för statusrapporten E-postflöde

Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.

Diagrammet är ordnat efter **riktningsvärden.**

Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen. Samma filter används **i** vyn Typ.

Datatabellen innehåller samma information från **vyn** Typ.

Välj **en kategori om du vill ha mer** information om tillgängliga val och beteenden är samma som **vyn** Typ.

**Exportera:**

I detaljvyn kan du bara exportera data för en dag. Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.

Varje exporterad CSV-fil är begränsad till 150 000 rader. Om dagens data innehåller fler än 150 000 rader skapas flera CSV-filer.

![Vyn Riktning i statusrapporten för e-postflöde ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trattvy för statusrapporten för e-postflöde

I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i din organisation. Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade skyddsfunktionerna för hot, inklusive gränsskydd, skadlig programvara, skydd mot nätfiske, skräppostskydd och förfalskning påverkar antalet.

Om du klickar **på fliken** Tratt innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.

- **Riktning:**

  - **Inkommande**
  - **Utgående**
  - **Årsantal:** Antalet är för meddelanden som skickas inom en klientorganisation. Det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).

Mängdvyn och datatabellvyn tillåter 90 dagars filtrering.

Om du klickar **på Filter** kan du filtrera både diagrammet och datatabellen.

I det här diagrammet visas antalet e-postmeddelanden ordnade efter:

- **Totalt antal e-postmeddelanden**
- **E-post efter gränsskydd**
- **E-post efter skadlig programvara, rykte, filtypsblock**
- **E-post efter anfing, URL-rykte, varumärkespersonifiering, förfalskning**
- **E-post efter skräppostskydd, massfiltrering**
- **E-post efter användare och domänpersonifiering**<sup>1</sup>
- **E-post efter fil och URL-detonation**<sup>1</sup>
- **E-post identifieras som hotad efter leveransskydd (URL-klicktidsskydd)**

<sup>1</sup> Endast Defender för Office 365

Om du vill visa e-post som filtreras separat med EOP eller Defender för Office 365 klickar du på värdet i diagramförklaringen.

Datatabellen innehåller följande information, som visas i fallande datumordning:

- **Datum**
- **Totalt antal e-postmeddelanden**
- **Edge-skydd**
- **Skydd mot skadlig programvara, rykte, filtypsblock:**
  - **Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.
  - **Filtypsblock:** Meddelanden filtrerade på grund av den typ av skadlig fil som identifieras i meddelandet.
- **Skydd mot phish, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**
  - **Rykte:** Meddelanden filtrerade på grund av identifiering av WEBBADRESSen av andra Microsoft-kunder.
  - **Profilering:** Meddelanden filtrerade på grund av meddelandet från välkända avsändare som utger sig för att vara avsändare.
  - Skydd mot **förfalskning:** Meddelanden filtrerade på grund av meddelandet som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.
- **Skydd mot skräppost och massfiltrering:**
  - **Massfiltrering:** Filtrerade meddelanden på grund av ett försök att leverera massutskick till mottagarna.
- **Personifiering av användare och domän (Defender för Office 365)**:
  - **Användarpersonifiering:** Filtrerade meddelanden på grund av ett försök att personifiera en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.
  - **Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att personifiera en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.
- **Detonation för fil och URL (Defender för Office 365)**:
  - **Detonation för filer:** Meddelanden filtrerade med en princip för säkra bifogade filer.
  - **URL-detonation:** Meddelande filtrerat med en princip för säkra länkar.
- **Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.

Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällna listan.

**Exportera:**

När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:

- **Sammanfattning (med data för de senaste 90 dagarna som mest)**
- **Information (med data för de senaste 30 dagarna som mest)**

Välj **ett** område under Datum och klicka sedan på **Använd.** Data för de aktuella filtren exporteras till en CSV-fil.

Varje exporterad CSV-fil är begränsad till 150 000 rader. Om informationen innehåller fler än 150 000 rader skapas flera CSV-filer.

 ![Trattvyn i statusrapporten för e-postflöde ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Tech view for the Mailflow status report

**Tech-vyn** liknar vyn **Tratt,** med mer detaljerad information om funktionerna för konfigurerade skydd mot hot. I diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.

Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.

- **Riktning:**

  - **Inkommande**
  - **Utgående**
  - **Årsantal:** antalet är för meddelanden inom en klientorganisation, dvs. avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)

Mängdvyn och datatabellvyn tillåter 90 dagars filtrering.

Om du klickar **på Filter** kan du filtrera både diagrammet och datatabellen.

I det här diagrammet visas meddelanden ordnade i följande kategorier:

- **Totalt antal e-postmeddelanden**
- **Tillåtna Edge** **och Filtrerad Edge**
- **Inte skadlig programvara,** **identifiering av säkra bifogade** <sup>\*</sup> **filer, identifiering av skadlig programvara** och **regelmeddelanden**
- **Inte phish,** **DMARC-fel,** identifiering **av personifiering,** identifiering **av förfalskning** och **phish**
- **Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup>
- **Inte** skräppost 
- **Icke-skadlig e-post,** **identifiering av säkra** länkar och <sup>\*</sup> **ZAP**

<sup>\*</sup> Defender för Office 365

När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.

Datatabellen innehåller följande information, som visas i fallande datumordning:

- **Datum**
- **Totalt antal e-postmeddelanden**
- **Filtrerad Edge**
- **Motor mot skadlig programvara, säkra bifogade filer, regel filtrerad:**
  - **Regel filtrerad:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).
- **DMARC, personifiering, förfalskning, nätfiske filtrerat:**
  - **DMARC:** Meddelanden filtrerade på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.
- **Identifiering av URL-detonation**
- **Skräppostskydd filtreras**
- **ZAP har tagits bort**
- **Identifiering av säkra länkar**

Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällna listan.

**Exportera:**

När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:

- **Sammanfattning (med data för de senaste 90 dagarna som mest)**
- **Information (med data för de senaste 30 dagarna som mest)**

Välj **ett** område under Datum och klicka sedan på **Använd.** Data för de aktuella filtren exporteras till en CSV-fil.

Varje exporterad CSV-fil är begränsad till 150 000 rader. Om informationen innehåller fler än 150 000 rader skapas flera CSV-filer.

 ![Teknisk vy i statusrapporten för E-postflöde ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Rapport om skickad och mottagen e-post

Rapporten **skickad och mottagen** e-post är en smart rapport som visar information om inkommande och utgående e-post, inklusive identifiering av skräppost, skadlig programvara och e-post som identifieras som "bra". Skillnaden mellan den här rapporten och [statusrapporten](#mailflow-status-report) för E-postflöde är: den här rapporten innehåller inte data om meddelanden som blockeras av Edge Protection. Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.

Mängdvyn och detaljvyn för rapporten tillåter 90 dagars filtrering.

Om du vill visa rapporten öppnar du [säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till instrumentpanelen Rapporter och väljer  \>  **Skickad och mottagen e-post.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget för skickad och mottagen e-post på instrumentpanelen Rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Rapportvy för rapporten Skickat och mottaget e-postmeddelande

Följande diagram är tillgängliga i rapportvyn:

- **Dela upp efter: Typ:** I diagrammet visas alla tillgängliga kategorier:

  - **Totalt**
  - **Bra e-post**
  - **Skadlig programvara (anti-malware)** (EOP)
  - **Identifiering av skräppost**
  - **Regelmeddelanden**
  - **Avancerad skadlig programvara** (Microsoft Defender för Office 365)

  När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.

  ![Vyn Typ i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-type-view.png)

- **Dela upp efter: Riktning:** Diagrammet visar **data för summa,** **inkommande** **och utgående** trafik. När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.

  ![Vyn Riktning i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-direction-view.png)

- **Öka detalj detalj för** \> **Skadlig programvara (skadlig kod)**: Med det här valet kommer du till identifieringar av skadlig programvara [i e-postrapporten.](view-email-security-reports.md#malware-detections-in-email-report)

- **Öka detalj detalj för** \> **Identifiering av skräppost)**: Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)

Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Typvärden

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Tabellvyn Information för rapporten skickat och mottaget e-postmeddelande

Om du **klickar på tabellen Visa** information i tabellen Dela upp **efter:** Riktning eller Dela upp **efter:** Riktningsvy visas följande information:

- **Datum (UTC)**
- **Typ**
- **Riktning**
- **Antal meddelanden**

Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Typvärden

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="top-senders-and-recipients-report"></a>Rapport om de viktigaste avsändarna och mottagarna

Rapporten **De bästa avsändarna och mottagarna** är ett cirkeldiagram som visar dina mest populära e-postavsändare och mottagare.

Om du vill visa rapporten öppnar [du säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** Rapporter \>  och väljer De **främsta avsändarna och mottagarna.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget för de bästa avsändarna och mottagarna på instrumentpanelen Rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Rapportvy för rapporten Mest om avsändare och mottagare

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för \> de viktigaste e-postavsändarna**
- **Visa data för de \> viktigaste e-postmottagarna**
- **Visa data för \> de viktigaste skräppostmottagarna**
- **Visa data för \> Populära mottagare av skadlig programvara** (EOP)
- **Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**

Sammansättning av cirkeldiagrammet ändras baserat på dessa val.

När du hovrar över en kil i cirkeldiagrammet visas antalet meddelanden som skickats eller tagits emot.

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

![Cirkeldiagram i rapportvyn i rapporten De största avsändarna och mottagarna](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Tabellvyn Information för rapporten om de viktigaste avsändarna och mottagaren

Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:

- **Visa data för \> de viktigaste e-postavsändarna**

  - **Mest populära e-postavsändare**
  - **Antal**

- **Visa data för de \> viktigaste e-postmottagarna**

  - **De viktigaste e-postmottagarna**
  - **Antal**

- **Visa data för \> de viktigaste skräppostmottagarna**

  - **Populära mottagare av skräppost**
  - **Antal**

- **Visa data för \> Populära mottagare av skadlig** programvara (EOP)

  - **De viktigaste mottagarna av skadlig programvara**
  - **Antal**

- **Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**

  - **De viktigaste mottagarna av skadlig programvara (Defender för Office 365)**
  - **Antal**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Vilka behörigheter krävs för att visa de här rapporterna?

För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Säkerhets- och & Efterlevnadscenter:

- **Organisationshantering**
- **Säkerhetsadministratör**
- **Säkerhetsläsare**
- **Global Reader**

Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Relaterade ämnen

[Smarta rapporter och insikter i Säkerhets- & Efterlevnadscenter](reports-and-insights-in-security-and-compliance.md)

[Insikter i e-postflöde i Säkerhets- & Efterlevnadscenter](mail-flow-insights-v2.md)

[Visa e-postsäkerhetsrapporter i Säkerhets- & Efterlevnadscenter](view-email-security-reports.md)

[Visa rapporter för Microsoft Defender för Office 365](view-reports-for-atp.md)
