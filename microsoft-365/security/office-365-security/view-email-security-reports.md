---
title: Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Lär dig hur du hittar och använder e-postsäkerhetsrapporter för din organisation. E-postsäkerhetsrapporter finns tillgängliga i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290805"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Ett antal olika rapporter finns tillgängliga i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) för att hjälpa dig se hur säkerhetsfunktioner för e-post, till exempel skydd mot skräppost, skadlig programvara och kryptering i Microsoft 365 skyddar organisationen. Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-these-reports)du visa de här rapporterna i Säkerhets- och & genom att gå till  \> **instrumentpanelen Rapporter.** Om du vill gå direkt till instrumentpanelen Rapporter öppnar du <https://protection.office.com/insightdashboard> .

![Instrumentpanelen Rapporter i Säkerhets- & Efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Rapport om komprometterade användare

> [!NOTE]
> Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor. Det är inte tillgängligt i fristående Exchange Online Protection-organisationer (EOP).

I **rapporten Komprometterade** användare visas antalet användarkonton som har markerats som **misstänkta** eller **begränsade under** de senaste 7 dagarna. Konton i båda dessa delstater är problematiska eller till och med komprometterade. Med regelbunden användning kan du använda rapporten för att upptäcka insamlingar och även trender i misstänkta eller begränsade konton. Mer information om komprometterade användare finns i [Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)

![Widget för komprometterade användare på instrumentpanelen Rapporter](../../media/compromised-users-report-widget.png)

I mängdvyn visas data för de senaste 90 dagarna och i detaljvyn visas data för de senaste 30 dagarna.

Om du vill visa rapporten öppnar du [Säkerhets- &,](https://protection.office.com)går till instrumentpanelen  \> **Rapporter och** väljer **Komprometterade användare.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=CompromisedUsers> .

Du kan filtrera både diagrammet och detaljtabellen genom att klicka **på Filter** och välja ett eller flera av följande värden:

- **Startdatum** och **slutdatum**

- **Misstänkt:** Användarkontot har skickat misstänkt e-postmeddelande och riskerar att bli begränsat från att skicka e-post.

- **Begränsad:** Användarkontot har begränsats från att skicka e-post på grund av mycket misstänkta mönster.

![Rapportvyn i rapporten Komprometterade användare](../../media/compromised-users-report-activity-view.png)

Om du **klickar på Visa informationstabell** visas följande information:

- **Tid för skapande**
- **Användar-ID**
- **Åtgärd**

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="encryption-report"></a>Krypteringsrapport

Krypteringsrapporten **är** tillgänglig i EOP (prenumerationer med postlådor i Exchange Online eller fristående EOP utan Exchange Online-postlådor). Organisationens säkerhetsteam kan använda informationen i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden. Till exempel:

- Om du ser ett stort antal e-postmeddelanden som krypteras av användare kanske du vill lägga till en krypteringsprincip för att automatisera kryptering för vissa användningsfall. Mer information finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden i Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

- Om du har ett antal tillgängliga krypteringsmallar men ingen använder dem kan du undersöka om användarna behöver funktionsutbildning.

I mängdvyn kan du filtrera de senaste 90 dagarna, medan detaljvyn tillåter filtrering i 10 dagar.

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer **Krypteringsrapport.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=EncryptionReport> .

Mer information om kryptering finns i [E-postkryptering i Microsoft 365.](../../compliance/email-encryption.md)

### <a name="report-view-for-the-encryption-report"></a>Rapportvy för rapporten Kryptering

Du kan använda följande filter i diagrammet:

- **Visa data efter: Meddelandekrypteringsrapport** **och Dela upp efter: Krypteringsmetod:** Följande krypteringsmetoder är tillgängliga:

  - **Kryptering efter användare**
  - **Kryptering efter princip**

  Om du **klickar på** Filter kan du ändra diagrammet med följande filter:

  - **Startdatum** och **slutdatum**
  - Krypteringsmetod.
  - Krypteringsmall.

- **Visa data efter: Meddelandekrypteringsrapport** **och Dela upp efter: Krypteringsmall:** Följande krypteringsmetoder är tillgängliga:

  - **Vidarebefordra inte**
  - **Endast kryptera**
  - **OME föregående**
  - **Anpassad**

  Om du **klickar på** Filter kan du ändra diagrammet med följande filter:

  - **Startdatum** och **slutdatum**
  - Krypteringsmetod
  - Krypteringsmall

- **Visa data efter: De 5 översta mottagardomänerna:** I den här vyn visas ett cirkeldiagram med antal skickade meddelanden för de fem översta mottagardomänerna.

  Om du klickar **på** Filter kan du **välja startdatum** **och slutdatum.**

### <a name="details-table-view-for-the-encryption-report"></a>Detaljtabellvyn för krypteringsrapporten

Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:

- **Dela upp dig med: Krypteringsmetod** **eller Dela upp dig efter: Krypteringsmall:** Följande information visas:

  - **Datum**
  - **Avsändarens adress**
  - **Krypteringsmall**
  - **Krypteringsmetod**
  - **Mottagaradress**
  - **Ämne**

- **Visa data efter: De 5 främsta mottagardomänerna:**

  - **Datum**
  - **Mottagardomän**
  - **Antal meddelanden**

Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Krypteringsmetod
- Krypteringsmall

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="mailflow-status-report"></a>Statusrapport för e-postflöde

Statusrapporten **för e-postflöde** innehåller information om skadlig programvara, skräppost, nätfiske och blockerade meddelanden i Edge. Mer information finns i [statusrapporten för E-postflöde.](view-mail-flow-reports.md#mailflow-status-report)

## <a name="malware-detections-in-email-report"></a>Identifiering av skadlig kod i e-postrapport

Identifieringar av skadlig programvara i e-postrapporten visar information om identifiering av skadlig programvara i inkommande och utgående e-postmeddelanden (skadlig kod som **upptäckts** av Exchange Online Protection eller EOP). Mer information om skydd mot skadlig programvara i EOP finns i [Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)

 Mängdvyfiltret tillåter i 90 dagar, medan tabellfiltret i detalj bara tillåter i 10 dagar.

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till instrumentpanelen Rapporter och väljer Identifiering av skadlig programvara  \>  **i e-post.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MalwareDetections> .

![Identifiering av skadlig kod i e-postwidgeten på instrumentpanelen Rapporter](../../media/malware-detections-widget.png)

Du kan filtrera både diagrammet och detaljtabellen genom att klicka **på Filter** och välja:

- **Startdatum** och **slutdatum**
- **Inkommande**
- **Utgående**

![Rapportvy i identifiering av skadlig programvara i e-postrapport](../../media/malware-detections-report-view.png)

Om du **klickar på Visa informationstabell** visas följande information:

- **Datum**
- **Avsändarens adress**
- **Mottagaradress**
- **Meddelande-ID:** Tillgängligt i **meddelande-ID-sidhuvudet** i meddelandehuvudet och ska vara unikt. Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).
- **Ämne**
- **Filnamn**
- **Namn på skadlig programvara**

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="mail-latency-report"></a>E-postsvarstid – rapport

Rapporten **om e-postsvarstid** innehåller information om den e-postleverans och detonationsfördröjning som har upplevts i din organisation. Mer information finns i [e-postsvarstidsrapporten.](view-reports-for-atp.md#mail-latency-report)

## <a name="sent-and-received-email-report"></a>Rapport om skickad och mottagen e-post

Rapporten **skickat och mottaget** e-postmeddelande innehåller information om skadlig programvara, skräppost, e-postflödesregler (kallas även transportregler) och avancerad identifiering av skadlig programvara när e-post har kommit in i tjänsten. Mer information finns i rapporten [Skickad och mottagen e-post.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Rapport om identifiering av skräppost

Rapporten **om identifiering av skräppost** visar e-postmeddelanden som har blockerats av EOP. Meddelanden räknas individuellt, inte per mottagare. Om till exempel samma skräppostmeddelande skickades till 100 mottagare i organisationen räknas det som ett meddelande.

I mängdvyn kan du filtrera i 90 dagar, medan detaljtabellen tillåter 10 dagars filtrering.

Om du vill visa rapporten öppnar du [Säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** \> **Rapporter** och väljer **Identifiering av skräppost.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget för identifiering av skräppost på instrumentpanelen Rapporter](../../media/spam-detections-report-widget.png)

Mer information om skydd mot skräppost finns i [Skydd mot skräppost i EOP.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>Rapportvy för rapporten om identifiering av skräppost

Följande diagram är tillgängliga i rapportvyn:

- **Dela upp efter: Åtgärd:** Följande händelsetyper visas:

  - **Filtrerat skräppostinnehåll**
  - **IP-blockering för skräppost**
  - **Skräppostkuvertblock**
  - **DBEB-skräppostfilter:** Katalogbaserad kantblockering (DBEB)

  När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många objekt som blockerades den dagen och hur de objekten kategoriserats.

  ![Åtgärdsvyn i rapporten Om identifiering av skräppost](../../media/spam-detections-report-action-view.png)

- **Break down by: Direction:** The following directions are shown:

  - **Inkommande**
  - **Utgående**

  ![Vyn Riktning i rapporten om identifiering av skräppost](../../media/spam-detections-report-direction-view.png)

Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Händelsetypsvärden

### <a name="details-table-view-for-the-spam-detections-report"></a>Tabellvyn Information för rapporten om identifiering av skräppost

Om du **klickar på tabellen Visa** information i en rapportvy visas följande information:

- **Datum**
- **Avsändarens adress**
- **Mottagaradress**
- **Händelsetyp**
- **Åtgärd**
- **Ämne**

Om du klickar **på** Filter i en detaljtabell kan du ändra resultatet med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Händelsetypsvärden

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="spoof-detections-report"></a>Rapporten Identifieringar av förfalskning

I rapporten Identifieringar av förfalskning visas hur många **förfalskningsmeddelanden** som påträffades och av de som anses vara "bra" (förfalskning av e-post av legitima skäl). Mer information om förfalskning finns i Skydd mot [förfalskning i EOP.](anti-spoofing-protection.md)

I mängdvyn för rapporten kan du filtrera i 90 dagar, medan detaljvyn bara tillåter tio dagars filtrering.

Om du vill visa rapporten öppnar [du Säkerhets- &](https://protection.office.com)Efterlevnadscenter, går till **instrumentpanelen** Rapporter \>  och väljer **Identifieringar av förfalskning.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget för identifiering av förfalskning på instrumentpanelen Rapporter](../../media/spoof-detections-widget.png)

När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många förfalskningsmeddelanden som kom fram.

Du kan filtrera både diagrammet och detaljtabellen genom att klicka **på Filter** och välja ett eller flera av följande värden:

- **Startdatum** och **slutdatum**

- **Bra e-post**

- **Fångas som skräppost**

![Rapportvyn i rapporten Identifieringar av förfalskning](../../media/spoof-detections-report-view.png)

Om du **klickar på Visa informationstabell** visas följande information:

- **Datum**
- **Förfalskningsavsändare**
- **Verklig avsändare**
- **Sender IP**
- **Åtgärd**
- **Antal meddelanden**

Klicka på Visa rapport om du vill gå tillbaka **till rapportvyn.**

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

Statusrapporten **för skydd** mot hot är tillgänglig i både EOP och Microsoft Defender för Office 365. Rapporterna innehåller däremot olika data. Till exempel kan EOP-kunder visa information om skadlig programvara som upptäckts i e-post, men inte information om skadliga filer som upptäckts av säkra bifogade filer för [SharePoint, OneDrive och Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Rapporten innehåller antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (URL:er) som har blockerats av antivirusmotorn, nolltimmars automatisk rensning [(ZAP)](zero-hour-auto-purge.md)och Defender för Office 365-funktioner som säkra [länkar,](atp-safe-links.md)säkra bifogade filer och nätfiske. [](atp-safe-attachments.md) [](set-up-anti-phishing-policies.md) Du kan använda den här informationen för att identifiera trender eller avgöra om organisationens principer behöver justeras.

**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.

Om du vill visa rapporten öppnar du [säkerhets- & Efterlevnadscenter,](https://protection.office.com)går till **instrumentpanelen** \> **Rapporter** och väljer Status för **skydd mot hot.** Öppna någon av följande URL:er för att gå direkt till rapporten:

- Microsoft Defender för Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget för hotskyddsstatus på instrumentpanelen Rapporter](../../media/threat-protection-status-report-widget.png)

Som standard visas data för de senaste 7 dagarna i diagrammet. Om du klickar **på Filter** kan du välja ett datumintervall på 90 dagar (utvärderingsprenumerationer kan vara begränsade till 30 dagar). I detaljtabellvyn kan du filtrera i 30 dagar.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportvy för statusrapporten för skydd mot hot

Följande vyer är tillgängliga:

- **Visa data efter: Översikt:** Följande identifieringsinformation visas:

  - **Skadlig e-post**
  - **E-post phish**
  - **Innehålls skadlig programvara**

  ![Översiktsvy i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-overview-view.png)

- **Visa data efter: Innehåll \> Skadlig**<sup>programvara 1:</sup>Följande information visas för Microsoft Defender för Office 365-organisationer:

  - **Motor mot skadlig programvara:** Skadliga filer som upptäckts i Sharepoint, OneDrive och Microsoft Teams av [den inbyggda virusidentifieringen i Microsoft 365.](virus-detection-in-spo.md)
  - **Fildeonation:** Skadliga filer som upptäckts av [säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](atp-for-spo-odb-and-teams.md)

  ![Vyn Innehålls skadlig programvara i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-content-malware-view.png)

- **Visa data efter: Åsidosättning av meddelande:** Följande orsak visas:

  - **Lokal skip**
  - **TILLÅT IP**
  - **E-postflödesregel**
  - **Sender allow**
  - **Tillåt domän**
  - **ZAP har inte aktiverats**
  - **Mappen Skräppost är inte aktiverad**
  - **Betrodd avsändare för användare**
  - **User Safe Domain**

  ![Vyn Åsidosättning av meddelande i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-message-override-view.png)

- **Dela upp dig med: Identifieringsteknik** **och Visa data efter: E-post, \> Phish:** Följande information visas:

  - **ATP-genererat URL-rykte**<sup>1</sup>: Skadligt URL-rykte genererat av Defender för Office 365-detonationer i andra Microsoft 365-kunder.
  - **Avancerat nätfiskefilter:** Nätfiskesignaler baserade på maskininlärning.
  - **Anti-spoof - DMARC-fel:** DMARC-autentiseringsfel på meddelanden.
  - **Skydd mot förfalskning – års org:** Avsändaren försöker kapa mottagardomänen.
  - **Skydd mot förfalskning – extern domän:** Avsändaren försöker kapa någon annan domän.
  - **Personifiering av varumärken:** Personifiering av välkända varumärken baserat på avsändare.
  - **Domänpersonifiering**<sup>1:</sup>Personifiering av domäner som kunden äger eller definierar.
  - **EOP URL-rykte:** Skadligt URL-rykte.
  - **Allmänt nätfiskefilter:** Nätfiskesignaler baserade på analysregler.
  - **Andra**
  - **Phish ZAP**<sup>2</sup>: Ingen timmes automatisk rensning av nätfiskemeddelanden.
  - **URL-detonation**<sup>1</sup>
  - **Användarpersonifiering**<sup>1:</sup>Personifiering av användare som definierats av administratör eller lärt sig via postlådeinformation.

  ![Identifieringsteknikvy för nätfiskemeddelande i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Dela upp dig med: Identifieringsteknik** och **Visa data efter: Skadlig e-post: \>** Följande information visas:

  - **ATP-genererat filrykte**<sup>1</sup>: Hela ryktet för skadlig fil genererad av Defender för Office 365-detonationer.
  - **Anti-malware engine**<sup>1:</sup>Detection from anti-malware engines.
  - **Blockering av filtyper mot skadlig programvara:** Det här är e-postmeddelanden som filtrerats bort på grund av den typ av skadlig fil som identifieras i meddelandet.
  - **Detonation**<sup>1: Identifiering</sup>av säkra bifogade filer.
  - **Skadligt rykte**
  - **Malware ZAP**<sup>2</sup>
  - **Andra**

  ![Vy för identifieringsteknik för skadlig programvara i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Dela upp dig efter: Principtyp** och visa data efter: E-post, **\> Phish** eller Visa data: Skadlig e-post: Följande information visas: **\>**

  - **Skydd mot skadlig programvara**
  - **Säkra bifogade filer**<sup>1</sup>
  - **Anti-phish**
  - **Skräppostskydd**
  - **E-postflödesregel** (kallas även transportregel)
  - **Andra**

  ![Principtypsvy för nätfiskemeddelande i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Dela upp dig efter: Leveransstatus** och visa data efter: E-post, **\> Phish** eller Visa data: E-post skadlig programvara: Följande information visas: **\>**

  - **Leveransen misslyckades**
  - **Nedsnad**
  - **Vidarebefordrad**
  - **Värdpostlåda: Anpassad mapp**
  - **Värdpostlåda: Borttagna objekt**
  - **Värdinkorg: Inkorgen**
  - **Värdpostlåda: Skräppost**
  - **Lokal server: Levererat**
  - **Karantän**

  ![Vyn Leveransstatus för nätfiskemeddelande i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Endast Defender för Office 365

<sup>Zap</sup> (Zero-hour auto purge) är inte tillgängligt i fristående EOP (det fungerar bara i Exchange Online-postlådor).

Om du klickar **på** Filter beror de tillgängliga filtren på det diagram du tittar på:

- När **du vill visa data \> efter:** Skadlig innehåll kan du ändra rapporten efter **startdatum** **och slutdatum** samt värdet **identifiering.**

- Om **du vill visa data efter: Åsidosättning** av meddelande kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - **Åsidosätt orsak**
  - **Tagg:** Filtrera resultaten efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton). Mer information om användartaggar finns i [Användartaggar.](user-tags.md)
  - **Domain**

- För alla andra vyer kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - **Identifiering**
  - **Skyddat av:** **ATP** eller **EOP**
  - **Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton). Mer information om användartaggar finns i [Användartaggar.](user-tags.md)
  - **Domain**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Detaljtabellvy för statusrapporten för skydd mot hot

Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:

- **Visa data efter: Översikt:** **Tabellknappen Ingen tabellinformationsknapp** för Visa är tillgänglig.

- **Visa data efter: Innehåll \> Skadlig programvara:**

  - **Datum**
  - **Plats**
  - **Riktad av**
  - **Namn på skadlig programvara**

  Om du **klickar på** Filter i den här vyn kan du ändra rapporten efter **startdatum** **och slutdatum** och **värdet Identifiering.**

- **Visa data efter: Åsidosättning av meddelande:**

  - **Datum**
  - **Ämne**
  - **Avsändare**
  - **Mottagare**
  - **Upptäckt av**
  - **Åsidosätt orsak**
  - **Källan till kompromett**
  - **Taggar**

  Om du **klickar på** Filter i den här vyn kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - **Åsidosätt orsak**
  - **Tagg:** Filtrera resultaten efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton). Mer information om användartaggar finns i [Användartaggar.](user-tags.md)
  - **Domain**
  - **Mottagare** (Observera att den här filtrerbara egenskapen endast är tillgänglig i detaljtabellvyn)

- Alla andra diagram:

  - **Datum**
  - **Ämne**
  - **Avsändare**
  - **Mottagare**
  - **Upptäckt av**
  - **Leveransstatus**
  - **Källan till kompromett**
  - **Taggar**

  Om du **klickar på** Filter kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - **Identifiering**
  - **Skyddad av:** **Defender för Office 365** eller **EOP**
  - **Tagg:** Filtrera resultaten efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton). Mer information om användartaggar finns i [Användartaggar.](user-tags.md)
  - **Domain**
  - **Mottagare** (Observera att den här filtrerbara egenskapen endast är tillgänglig i detaljtabellvyn)

## <a name="top-malware-report"></a>Bästa rapporten om skadlig programvara

Den **viktigaste rapporten om** skadlig programvara visar de olika typer av skadlig programvara som identifierats av skydd mot skadlig programvara i [EOP.](anti-malware-protection.md)

Om du vill visa rapporten öppnar du [Säkerhets- & Efterlevnadscenter,](https://protection.office.com)går **till** instrumentpanelen \> **Rapporter och** väljer Den **viktigaste skadlig programvara.** Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopMalware> .

![Widget för skadlig programvara på instrumentpanelen Rapporter](../../media/top-malware-report-widget.png)

När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig programvara och hur många meddelanden som identifierats som har den skadlig programvara.

![Den översta vyn i rapporten om skadlig programvara](../../media/top-malware-report-view.png)

Om du **klickar på Visa informationstabell** visas följande information:

- **Populära skadlig programvara**
- **Antal**

Om du klickar **på** Filter i rapportvyn eller i detaljtabellvyn kan du ange ett datumintervall **med startdatum** **och slutdatum.**

## <a name="url-threat-protection-report"></a>Rapport om URL-skydd

Rapporten **om skydd mot URL-hot** är tillgänglig i Microsoft Defender för Office 365. Mer information finns i rapporten [om skydd mot URL-hot.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Rapport om användarrapporterade meddelanden

I **rapporten över** användarrapporter visas information om e-postmeddelanden som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](enable-the-report-message-add-in.md) med hjälp av tilläggen Rapportmeddelande eller Tillägg för [nätfiske.](enable-the-report-phish-add-in.md)

Information är tillgänglig för varje meddelande, inklusive leveransorsaken, ett sådant undantag från skräppostprincipen eller en e-postflödesregel som konfigurerats för din organisation. Om du vill visa information markerar du ett objekt i listan med användarrapporter och visar informationen på flikarna **Sammanfattning** **och** Information.

![I User-Reported i meddelanderapporten visas meddelanden som användare har märkt som skräppost, inte skräppost eller nätfiskeförsök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Om du vill visa den här [rapporten gör & säkerhets-](https://protection.office.com)och efterlevnadscentret på något av följande sätt:

- Gå till **användarrapporterade** \> **meddelanden från** \> **instrumentpanelen för hantering av hot.**

- Gå till **Hothanteringsgranskning** \>  \> **av användarrapporterade meddelanden.**

![I Säkerhets- & Center väljer du Användarrapporter för \> hantering av \> hothantering](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> För att den användarrapporterade meddelanderapporten ska fungera korrekt **måste** granskningsloggning vara aktiverad för Office 365-miljön. Det görs vanligtvis av någon som har tilldelats rollen Granskningsloggar i Exchange Online. Mer information finns i Aktivera eller inaktivera granskningsloggsökning [i Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Vilka behörigheter krävs för att visa de här rapporterna?

För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Säkerhets- och & Efterlevnadscenter:

- **Organisationshantering**
- **Säkerhetsadministratör**
- **Säkerhetsläsare**
- **Global Reader**

Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

**Obs!** Om du lägger till användare till motsvarande Azure Active Directory-roll i administrationscentret för Microsoft  365 får användarna de behörigheter som krävs i säkerhets- och efterlevnadscentret för & och behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i rapporterna kontrollerar du att principerna är korrekt konfigurerade. Mer information finns i [Skydda mot hot.](protect-against-threats.md)

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot skräppost och skadlig programvara i EOP](anti-spam-and-anti-malware-protection.md)

[Smarta rapporter och insikter i Säkerhets- & Efterlevnadscenter](reports-and-insights-in-security-and-compliance.md)

[Visa e-postflödesrapporter i Säkerhets- & Efterlevnadscenter](view-mail-flow-reports.md)

[Visa rapporter för Defender för Office 365](view-reports-for-atp.md)
