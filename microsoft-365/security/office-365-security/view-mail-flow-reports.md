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
description: Administratörer kan läsa mer om de e-postflödesrapporter som är tillgängliga på instrumentpanelen Rapporter i säkerhets- & efterlevnadscenter.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029483"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Visa e-postflödesrapporter på instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De flesta rapporter som beskrivs i det här avsnittet är tillgängliga i administrationscentret för Exchange (EAC). Mer information finns i [E-postflödesrapporter i det nya administrationscentret för Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports) [Exchange-transportregelrapporten](view-email-security-reports.md#exchange-transport-rule-report) är tillgänglig på Microsoft 365 Defender-portalen.

Utöver de e-postflödesrapporter som [](mail-flow-insights-v2.md) finns tillgängliga på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & finns det en mängd andra e-postflödesrapporter på instrumentpanelen Rapporter som hjälper dig att övervaka din Microsoft 365-organisation.

Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-these-reports)du visa de här rapporterna i Säkerhets- [& efterlevnadscenter genom](https://protection.office.com) att gå till **Instrumentpanelen** \> **rapporter.** Gå direkt till instrumentpanelen Rapporter genom att öppna <https://protection.office.com/insightdashboard> .

![Instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Kopplingsrapport

Rapporten **Koppling visar** e-postflödesaktivitet för [inkommande och utgående anslutningar](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) som är konfigurerade för organisationen.

Om du vill visa rapporten öppnar du [säkerhets- & kompatibilitetscenter](https://protection.office.com), går till **instrumentpanelen** \> **rapporter** och väljer **Kopplingsrapport**. Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget för kopplingsrapport på instrumentpanelen Rapporter](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Rapportvyn för kopplingsrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data efter: E-postflöde:** I det här diagrammet visas antalet inkommande och utgående meddelanden ordnade efter:

  - **Totalt**
  - **Från Internet utan anslutning**
  - **Till Internet utan anslutning**
  - En specifik koppling som du har konfigurerat.

  Om du vill isolera data i diagrammet använder du visa data för kontroll **och** väljer ett av dessa alternativ eller All **e-postflöde**.

  ![Visa data via e-postflöde i kopplingsrapporten](../../media/connector-report-view-data-by-mail-flow.png)

- **Visa data efter: TLS-användning:** I det här diagrammet visas procentandelen användning av TLS (Transport Layer Security) för e-postflöde.

  Om du vill isolera data i diagrammet använder du **visa data för kontroll** och väljer något av följande alternativ:

  - **Allt e-postflöde**
  - **Från Internet utan anslutning**
  - **Till Internet utan anslutning**
  - En specifik koppling som du har konfigurerat.

  ![Visa data efter TLS-användning i kopplingsrapporten](../../media/connector-report-view-data-by-tls-usage.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

### <a name="details-table-view-for-the-connector-report"></a>Detaljtabellvyn för kopplingsrapporten

Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:

- **Datum**
- **Kopplingsriktning och -namn**
- **Kopplingstyp**
- **Tvingad TLS?**: Värdet **Sant** eller **Falskt.**
- **Ingen TLS** (procent)
- **TLS 1,0** (procent)
- **TLS 1,1** (procent)
- **TLS 1,2** (procent)
- **Volym**: Antalet meddelanden.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="exchange-transport-rule-report"></a>Rapport över Exchange-transportregel

I **rapporten Exchange-transportregel** visas effekten av e-postflödesregler (kallas även transportregler) på inkommande och utgående meddelanden i organisationen.

Om du vill visa rapporten öppnar du [säkerhets- &,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer **Exchange-transportregel**. Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget för Exchange-transportregel på instrumentpanelen Rapporter](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Rapportvy för Exchange-transportregelrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data efter: Exchange-transportregler** \> **Dela upp efter: Riktning**: I det här diagrammet visas antalet **inkommande** och **utgående** meddelanden som påverkades av transportreglerna.

- **Visa data efter: Exchange-transportregler** \> **Dela upp efter: Allvarlighetsgrad**:  I det här diagrammet visas antalet meddelanden med hög allvarlighetsgrad och medel allvarlighetsgrad samt låg **allvarlighetsgrad.** Du anger allvarlighetsnivån som en åtgärd i regeln **(Granska** denna regel med allvarlighetsnivå eller _AngeGranskningSalla_). Mer information finns i Åtgärder för [e-postflödesregel i Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Visa data efter: DLP Exchange-transportregler** \> **Dela upp efter: Riktning**: I det  här diagrammet visas antalet **inkommande** och utgående meddelanden som påverkades av DLP-transportregler (Data Loss Prevention). Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:

  - **Visa data för: Alla DLP-transportregler**
  - **Visa data för: Komprometterade användare**
  - **Visa data för: Låg mängd innehåll som identifierats av U.S. Act**

- **Visa data efter: DLP Exchange-transportregler** \> **Dela upp efter: Riktning**: I  den här vyn visas  antalet meddelanden med hög allvarlighetsgrad och medel allvarlighetsgrad och meddelanden med låg allvarlighetsgrad som påverkades av DLP-transportregler.  Du kan förfina diagrammet ytterligare genom att välja bland följande alternativ:

  - **Visa data för: Alla DLP-transportregler**
  - **Visa data för: Komprometterade användare**
  - **Visa data för: Låg mängd innehåll som identifierats av U.S. Act**

Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:

- **Startdatum och** **slutdatum**
- Riktningsvärden
- Värden för allvarlighetsgrad

![Rapportvyn i rapporten Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detaljtabellvyn för Exchange-transportregelrapporten

Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:

- **Visa data efter: Exchange-transportregler:**

  - **Datum**
  - **Transportregel**
  - **Ämne**
  - **Avsändarens adress**
  - **Mottagaradress**
  - **Allvarlighetsgrad**
  - **Riktning**

- **Visa data efter: DLP-transportregler i Exchange:**

  - **Datum**
  - **DLP-princip**
  - **Transportregel**
  - **Ämne**
  - **Avsändarens adress**
  - **Mottagaradress**
  - **Allvarlighetsgrad**
  - **Riktning**

Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:

- **Startdatum och** **slutdatum**
- Riktningsvärden
- Värden för allvarlighetsgrad

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="forwarding-report"></a>Vidarebefordransrapport

I **vidarebefordransrapporten** visas organisationens automatiskt vidarebefordrade meddelanden till externa domäner från Exchange Online postlådor. Vidarebefordrade meddelanden kan vara en säkerhets- eller efterlevnadsrisk och kan ange ett komprometterat konto.

Om du vill visa rapporten öppnar du [säkerhets- & Kompatibilitetscenter](https://protection.office.com), går till  \> **instrumentpanelen rapporter** och väljer **Vidarebefordransrapport.** Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget för vidarebefordransrapport på instrumentpanelen Rapporter](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Rapportvy för vidarebefordransrapporten

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Metoder för vidarebefordran:** Följande metoder visas:

  - **Transportregel:** Kallas även [e-postflödesregler.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postlåderegel:** Kallas även [inkorgsregler.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Vy över vidarebefordransmetoder i rapporten om vidarebefordran](../../media/forwarding-report-forwarding-methods.png)

- **Visa data för: Domäner för vidarebefordran:** I den här vyn visas de mottagardomäner som är destinationer för vidarebefordran.

  ![Vy för vidarebefordran av domäner i rapporten Om vidarebefordran](../../media/forwarding-report-forwarding-domains.png)

- **Visa data för: Vidarebefordrare:** Följande vidarebefordrare visas:

  - **Transportregel**
  - Postlådan som innehåller regeln för vidarebefordran av inkorg.

  ![Vyn Vidarebefordrare i rapporten Vidarebefordran](../../media/forwarding-report-forwarders.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

### <a name="details-table-view-for-the-forwarding-report"></a>Detaljtabellvyn för vidarebefordransrapporten

Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:

- **Vidarebefordrare:** **Värdetransportregeln eller** postlådan som innehåller vidare vidarebefordrans inkorgsregeln.
- **Vidarebefordranstyp:** **Värdepostlåderegel** eller **Transportregel.**
- **Mottagarens namn**
- **Mottagardomän**
- **Information:** Det här är GUID-värdet för e-postflödesregeln eller RuleIdentity-värdet för inkorgsregeln.
- **Antal**
- **Första forwardsdatumet**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.

## <a name="mailflow-status-report"></a>Statusrapport för e-postflöde

Statusrapporten **E-postflöde** liknar rapporten [Skickad](#sent-and-received-email-report)och mottagen e-post, med ytterligare information om tillåtna eller blockerade e-postmeddelanden i kanten. Det här är den enda rapporten som innehåller information om gränsskydd och som visar hur mycket e-post som blockeras innan den tillåts till tjänsten för utvärdering av Exchange Online Protection (EOP). Det är viktigt att vara säker på att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.
Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter](https://protection.office.com), går till  \> **instrumentpanelen Rapporter** och väljer **Statusrapport för e-postflöde.** Gå direkt till statusrapporten **E-postflöde genom att** öppna <https://protection.office.com/mailflowStatusReport> .

![Widget för statusrapport för e-postflöde på instrumentpanelen Rapporter](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typvy för statusrapporten E-postflöde

När du öppnar rapporten är **fliken Typ** markerad som standard. Som standard innehåller den här vyn ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.
- **Riktning**:

  - **Inkommande**
  - **Utgående**
  - **Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs. sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från **inkommande** **och utgående**)

- **Typ:**

  - **Bra e-post**
  - **Skadlig programvara**
  - **Skräppost**
  - **Edge-skydd**
  - **Regelmeddelanden**
  - **Nätfiske-e-post**

Diagrammet ordnas efter **typvärdena.**

Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen.

Datatabellen innehåller följande information:

- **Riktning**
- **Typ**
- **24 timmar**
- **3 dagar**
- **7 dagar**
- **15 dagar**
- **30 dagar**

Om du klickar **på Välj en kategori för mer** information kan du välja bland följande värden:

- **Nätfiskemeddelande:** Det här valet tar dig till [rapporten status för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)
- **Skadlig programvara i** e-post: Det här valet tar dig till [statusrapporten Skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)
- **Identifiering av skräppost:** Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)
- **Edge blockerad skräppost:** Det här valet tar dig till rapporten [Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)

**Exportera:**

I detaljvyn kan du bara exportera data under en dag. Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.

Varje exporterad .csv är begränsad till 150 000 rader. Om dagens data innehåller mer än 150 000 rader skapas .csv filer.

![Typvy i statusrapporten För e-postflöde](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Riktningsvyn för statusrapporten E-postflöde

Om du klickar **på** fliken Riktning används samma standardfilter **från** vyn Typ.

Diagrammet är ordnat efter **riktningsvärden.**

Du kan ändra dessa filter genom att klicka **på Filter** eller genom att klicka på ett värde i diagramförklaringen. Samma filter från **vyn** Typ används.

Datatabellen innehåller samma information från **vyn** Typ.

Vyn **Välj en kategori för mer information** om tillgängliga val och beteenden är samma som **vyn** Typ.

**Exportera:**

I detaljvyn kan du bara exportera data under en dag. Om du vill exportera data i 7 dagar måste du utföra 7 olika exportåtgärder.

Varje exporterad .csv är begränsad till 150 000 rader. Om dagens data innehåller mer än 150 000 rader skapas .csv filer.

![Riktningsvyn i statusrapporten E-postflöde](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trattvyn för statusrapporten E-postflöde

I **vyn Tratt** kan du se hur Microsofts skyddsfunktioner för e-posthot filtrerar inkommande och utgående e-post i organisationen. Här finns information om totalt antal e-postmeddelanden och hur de konfigurerade funktionerna för skydd mot hot, inklusive gränsskydd, skydd mot skadlig programvara, skydd mot nätfiske, skräppost och förfalskning, påverkar antalet.

Om du klickar **på fliken Tratt** innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.

- **Riktning**:

  - **Inkommande**
  - **Utgående**
  - **Årsorganisation:** Antalet är för meddelanden som skickas inom en klientorganisation. det vill säga att avsändaren abc@domain.com till mottagarens xyz@domain.com (räknas separat från inkommande och utgående).

För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.

Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.

I det här diagrammet visas antalet e-postmeddelanden ordnade efter:

- **Totalt antal e-postmeddelanden**
- **E-post efter gränsskydd**
- **E-post efter skadlig programvara, rykte, filtypsblockering**
- **E-post efter hot, URL-rykte, varumärkespersonifiering, skydd mot förfalskning**
- **E-post efter skräppost, massfiltrering**
- **E-post efter personifiering av användare och domän**<sup>1</sup>
- **E-post efter fil och URL detonation**<sup>1</sup>
- **E-post identifierades som därefter skydd efter leverans (URL klicka på tidsskydd)**

<sup>1</sup> Defender för Office 365 endast

Om du vill visa e-post som filtrerats efter EOP eller Defender Office 365 separat klickar du på värdet i diagramförklaringen.

Datatabellen innehåller följande information, visad i fallande datumordning:

- **Datum**
- **Totalt antal e-postmeddelanden**
- **Edge-skydd**
- **Skydd mot skadlig programvara, rykte för filen, filtypsblockering:**
  - **Rykte:** Meddelanden filtrerade på grund av identifiering av en bifogad fil av andra Microsoft-kunder.
  - **Filtypsblock:** Meddelanden filtreras på grund av vilken typ av skadlig fil som identifieras i meddelandet.
- **Antifras, URL-rykte, varumärkespersonifiering, skydd mot förfalskning:**
  - **URL-rykte:** Meddelanden filtreras på grund av identifiering av URL-adressen av andra Microsoft-kunder.
  - **Profilering:** Meddelanden filtrerade på grund av meddelanden från välkända varumärkespersonifieringsavsändare.
  - **Skydd mot förfalskning:** Meddelanden filtreras på grund av ett meddelande som försöker kapa en domän som mottagaren tillhör eller en domän som meddelandets avsändare inte äger.
- **Skräppostskydd, massfiltrering:**
  - **Massfiltrering:** Meddelanden filtreras på grund av ett försök att leverera massutskick till mottagarna.
- **Användar- och domänpersonifiering (Defender för Office 365)**:
  - **Personifiering för användare:** Filtrerade meddelanden på grund av ett försök att utge sig för att vara en användare (meddelandeavsändare) som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.
  - **Domänpersonifiering:** Meddelanden filtrerade på grund av ett försök att utge sig för att vara en domän som definierats i inställningarna för personifieringsskydd i en princip mot nätfiske.
- **Detonation av fil och URL (Defender för Office 365)**:
  - **Detonation för filer:** Meddelanden filtrerade efter Valv princip för bifogade filer.
  - **URL-detonation**: Meddelande filtrerat av Valv princip för länkar.
- **Post-delivery protection and ZAP (ATP) or ZAP (EOP)**: ZAP indicates zero hour auto-purge.

Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.

**Exportera:**

När du har **klickat** **på Exportera** under Alternativ kan du välja något av följande värden:

- **Sammanfattning (med data för de senaste 90 dagarna som mest)**
- **Information (med data för de senaste 30 dagarna som mest)**

Välj **ett** område under Datum och klicka sedan på **Använd**. Data för de aktuella filtren exporteras till en .csv fil.

Varje exporterad .csv är begränsad till 150 000 rader. Om informationen innehåller mer än 150 000 rader skapas .csv filer.

 ![Trattvyn i statusrapporten För e-postflöde](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Tech view for the Mailflow status report

**Tech-vyn** liknar vyn **Tratt, med** mer detaljerad information om de konfigurerade funktionerna för skydd mot hot. Från diagrammet kan du se hur meddelanden kategoriseras i olika faser av skydd mot hot.

Om du klickar **på fliken Teknisk** vy innehåller den här vyn som standard ett diagram och en datatabell som är konfigurerad med följande filter:

- **Datum:** De senaste sju dagarna.

- **Riktning**:

  - **Inkommande**
  - **Utgående**
  - **Årsorganisation**: det här antalet gäller meddelanden inom en klientorganisation, dvs. sender abc@domain.com skickar till mottagarens xyz@domain.com (räknas separat från inkommande och utgående)

För aggregerad vy och datatabellvy kan du filtrera i 90 dagar.

Om du klickar **på** Filter kan du filtrera både diagrammet och datatabellen.

Det här diagrammet visar meddelanden ordnade i följande kategorier:

- **Totalt antal e-postmeddelanden**
- **Tillåt i Edge** **och Filtrerad Edge**
- **Inte skadlig programvara**, **Valv identifiering av bifogade filer,** identifiering av skadlig <sup>\*</sup> **programvara** och **regelmeddelanden**
- **Inte phish**, **DMARC-fel,** **personidentifiering,** **förfalskning och** **phish-identifiering**
- **Ingen identifiering med URL-detonation och** **URL-detonation**<sup>\*</sup>
- **Inte** skräppost 
- **Icke-skadlig e-post** **, Valv identifiering av länkar** och <sup>\*</sup> **ZAP**

<sup>\*</sup>Defender för Office 365

När du hovrar över en kategori i diagrammet visas antalet meddelanden i den kategorin.

Datatabellen innehåller följande information, visad i fallande datumordning:

- **Datum**
- **Totalt antal e-postmeddelanden**
- **Edge filtrerad**
- **Motor mot skadlig programvara, Valv bifogade filer, regel filtrerad:**
  - **Regel filtrerad:** Meddelanden filtrerade på grund av e-postflödesregler (kallas även transportregler).
- **DMARC, personifiering, förfalskning, nätfiske filtrerat:**
  - **DMARC:** Meddelanden filtreras på grund av att meddelandet inte klarar sin DMARC-autentiseringskontroll.
- **Identifiering av URL-adresser**
- **Skräppostskydd filtreras**
- **ZAP har tagits bort**
- **Identifiering av Valv länkar**

Om du markerar en rad i datatabellen visas ytterligare en uppdelning av antalet e-postmeddelanden i den utfällklienten.

**Exportera:**

När du **klickar** på Exportera **kan** du välja något av följande värden under Alternativ:

- **Sammanfattning (med data för de senaste 90 dagarna som mest)**
- **Information (med data för de senaste 30 dagarna som mest)**

Välj **ett** område under Datum och klicka sedan på **Använd**. Data för de aktuella filtren exporteras till en .csv fil.

Varje exporterad .csv är begränsad till 150 000 rader. Om informationen innehåller mer än 150 000 rader skapas .csv filer.

 ![Tech view in the Mailflow status report](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Rapport om skickad och mottagen e-post

Rapporten **Skickad och mottagen** e-post är en smart rapport som visar information om inkommande och utgående e-post, inklusive identifiering av skräppost, skadlig programvara och e-post som identifieras som "bra". Skillnaden mellan den här rapporten och [statusrapporten](#mailflow-status-report) E-postflöde är: den här rapporten innehåller inga data om meddelanden som blockeras av edge-skydd.

**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som ett meddelande.

Mängdvyn och detaljvyn för rapporten tillåter 90 dagars filtrering.

Om du vill visa rapporten öppnar du [säkerhets- &,](https://protection.office.com)går till **instrumentpanelen** rapporter \> **och** väljer Skickad och **mottagen e-post.** Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget för skickad och mottagen e-post i instrumentpanelen Rapporter](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Rapportvy för rapporten Skickad och mottagen e-post

Följande diagram är tillgängliga i rapportvyn:

- **Dela upp efter: Typ:** Diagrammet visar alla tillgängliga kategorier:

  - **Totalt**
  - **Bra e-post**
  - **Skadlig programvara (skydd mot skadlig programvara)** (EOP)
  - **Identifiering av skräppost**
  - **Regelmeddelanden**
  - **Avancerad skadlig programvara** (Microsoft Defender för Office 365)

  När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.

  ![Skriv i rapporten Skickad och mottagen e-post](../../media/sent-and-received-email-report-type-view.png)

- **Dela upp efter: Riktning:** Diagrammet visar **data för Totalt,** **Inkommande** **och Utgående.** När du hovrar över en dag (datapunkt) i diagrammet kan du se information om den dagen.

  ![Riktningsvyn i rapporten Skickat och mottaget e-postmeddelande](../../media/sent-and-received-email-report-direction-view.png)

- **Öka detalj detalj detalj för** \> **Skadlig programvara (skadlig programvara)**: Det här valet tar dig till rapporten [om identifiering av skadlig programvara.](view-email-security-reports.md#malware-detections-report)

- **Öka detalj detalj detalj för** \> **Identifiering av skräppost)**: Det här valet tar dig till [rapporten Identifiering av skräppost.](view-email-security-reports.md#spam-detections-report)

Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:

- **Startdatum och** **slutdatum**
- Riktningsvärden
- Ange värden

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Tabellvyn Information för rapporten Skickad och mottagen e-post

Om du **klickar på Visa informationstabell** i Brytning ned **efter: Riktning** eller Dela upp **efter:** Riktningsvy, visas följande information:

- **Datum (UTC)**
- **Typ**
- **Riktning**
- **Antal meddelanden**

Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:

- **Startdatum och** **slutdatum**
- Riktningsvärden
- Ange värden

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="top-senders-and-recipients-report"></a>Rapport om de största avsändarna och mottagarna

Rapporten **De bästa avsändarna och mottagarna** är ett cirkeldiagram som visar dina främsta e-postavsändare och mottagare.

Om du vill visa rapporten öppnar [du säkerhets- & Efterlevnadscenter](https://protection.office.com), går till **instrumentpanelen** \> **Rapporter** och **väljer De främsta avsändarna och mottagarna.** Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget för de främsta avsändarna och mottagarna på instrumentpanelen Rapporter](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Rapportvy för rapporten Betrodda avsändare och mottagare

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för \> de viktigaste e-postavsändarna**
- **Visa data för de \> viktigaste e-postmottagarna**
- **Visa data för \> de mest populära skräppostmottagarna**
- **Visa data för \> Populära mottagare av skadlig programvara** (EOP)
- **Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**

Sammansättning av cirkeldiagrammet ändras baserat på dessa val.

När du hovrar över en kil i cirkeldiagrammet visas antalet meddelanden som skickats eller tagits emot.

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

![Cirkeldiagram i rapportvyn i rapporten Betrodda avsändare och mottagare](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Tabellvyn Information för rapporten Betrodda avsändare och mottagare

Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:

- **Visa data för \> de viktigaste e-postavsändarna**

  - **De mest populära e-postavsändarna**
  - **Antal**

- **Visa data för de \> viktigaste e-postmottagarna**

  - **De populäraste e-postmottagarna**
  - **Antal**

- **Visa data för \> de mest populära skräppostmottagarna**

  - **Mest populära skräppostmottagare**
  - **Antal**

- **Visa data för \> Populära mottagare av skadlig programvara** (EOP)

  - **Populära mottagare av skadlig programvara**
  - **Antal**

- **Visa data för \> de viktigaste mottagarna av skadlig programvara (Defender för Office 365)**

  - **Populära mottagare av skadlig programvara (Defender för Office 365)**
  - **Antal**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Vilka behörigheter krävs för att visa rapporterna?

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

[Insikter om e-postflöde i Säkerhets- & Efterlevnadscenter](mail-flow-insights-v2.md)

[Visa e-postsäkerhetsrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter](view-email-security-reports.md)

[Visa rapporter för Microsoft Defender för Office 365](view-reports-for-mdo.md)
