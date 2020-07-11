---
title: Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter
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
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Läs om hur du hittar och använder säkerhetsrapporter för e-post för din organisation. Säkerhetsrapporter för e-post finns i Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26dfa8ec046122dce28582fb3d7b395843572a88
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102926"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter

En mängd olika rapporter finns i [Security & Compliance Center](https://protection.office.com) för att hjälpa dig att se hur säkerhetsfunktioner för e-post, till exempel anti-spam, anti-malware och krypteringsfunktioner i Microsoft 365 skyddar din organisation. Om du har [de behörigheter som krävs](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i Security & Compliance Center genom att gå till **Reports** \> **Instrumentpanelen**för rapporter . Om du vill gå direkt till instrumentpanelen för rapporter öppnar du <https://protection.office.com/insightdashboard> .

![Rapporter instrumentpanel i Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Rapport över komprometterade användare

> [!NOTE]
> Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor. Den är inte tillgänglig i fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.

Rapporten **Komprometterade användare** visar antalet användarkonton som har markerats som **misstänkta** eller **begränsade** under de senaste 7 dagarna. Konton i någon av dessa stater är problematiska eller till och med komprometterade. Med frekvent användning kan du använda rapporten för att upptäcka toppar och till och med trender i misstänkta eller begränsade konton. Mer information om komprometterade användare finns i [Svara på ett komprometterat e-postkonto](responding-to-a-compromised-email-account.md).

![Komprometterade användare widget i instrumentpanelen Rapporter](../../media/compromised-users-report-widget.png)

Den samlade vyn visar data för de senaste 90 dagarna och detaljvyn visar data för de senaste 30 dagarna.

Om du vill visa rapporten öppnar du [Security & Compliance Center](https://protection.office.com), går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **Komprometterade användare**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=CompromisedUsers> .

Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filter** och välja ett eller flera av följande värden:

- **Startdatum** och **slutdatum**

- **Misstänkt**: Användarkontot har skickat misstänkt e-post och riskerar att begränsas från att skicka e-post.

- **Begränsad**: Användarkontot har begränsats från att skicka e-post på grund av mycket misstänkta mönster.

![Rapportvyn i rapporten Komprometterade användare](../../media/compromised-users-report-activity-view.png)

Om du klickar på **Visa informationstabell**kan du se följande information:

- **Skapa tid**
- **Användar-ID**
- **Åtgärder**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="encryption-report"></a>Krypteringsrapport

**Krypteringsrapporten** är tillgänglig i EOP (prenumerationer med postlådor i Exchange Online eller fristående EOP utan Exchange Online-postlådor). Organisationens säkerhetsteam kan använda information i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden. Till exempel:

- Om du ser ett stort antal e-postmeddelanden krypterade av användare kanske du vill lägga till en krypteringsprincip för att automatisera kryptering för vissa användningsfall. Mer information finns i [Definiera regler för e-postflöde för att kryptera e-postmeddelanden i Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Om du har ett antal krypteringsmallar tillgängliga men ingen använder dem kan du undersöka om användarna behöver funktionsutbildning.

Den sammanlagda vyn tillåter filtrering för de senaste 90 dagarna, medan detaljvyn tillåter filtrering i 10 dagar.

Om du vill visa rapporten öppnar du [Security & Compliance Center](https://protection.office.com), går till **Instrumentpanelen rapporter** och väljer \> **Dashboard** **Krypteringsrapport**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=EncryptionReport> .

Mer information om kryptering finns [i E-postkryptering i Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Rapportvy för krypteringsrapporten

Du kan använda följande filter i diagrammet:

- **Visa data efter: Meddelandekrypteringsrapport** och **Bryt ned efter: Krypteringsmetod:** Följande krypteringsmetoder är tillgängliga:

  - **Kryptering per användare**
  - **Kryptering efter princip**

  Om du klickar på **Filter**kan du ändra diagrammet med följande filter:

  - **Startdatum** och **slutdatum**
  - Krypteringsmetod.
  - Krypteringsmall.

- **Visa data efter: Meddelandekrypteringsrapport** och **Bryt ned efter: Krypteringsmall:** Följande krypteringsmetoder är tillgängliga:

  - **Vidarebefordra inte**
  - **Endast kryptera**
  - **OME tidigare**
  - **Anpassade**

  Om du klickar på **Filter**kan du ändra diagrammet med följande filter:

  - **Startdatum** och **slutdatum**
  - Krypteringsmetod
  - Mall för kryptering

- **Visa data efter: Topp 5-mottagare:** I den här vyn visas ett cirkeldiagram med skickade meddelandeantal för de fem översta mottagardomänerna.

  Om du klickar på **Filter**kan du välja ett **startdatum** och **slutdatum**.

### <a name="details-table-view-for-the-encryption-report"></a>Tabellvy för information för krypteringsrapporten

Om du klickar på **Visa informationstabell**beror informationen som visas på vilket diagram du tittade på:

- **Bryt ned efter: Krypteringsmetod** eller **Bryt ned efter: Krypteringsmall**: Följande information visas:

  - **Datum**
  - **Avsändarens adress**
  - **Mall för kryptering**
  - **Krypteringsmetod**
  - **Mottagaradress**
  - **Ämne**

- **Visa data efter: Topp 5-mottagare:**

  - **Datum**
  - **Mottagardomän**
  - **Antal meddelanden**
  
Om du klickar på **Filter** i en detaljtabellvy kan du ändra resultaten med följande filter:

- **Startdatum** och **slutdatum**
- Krypteringsmetod
- Mall för kryptering

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="mailflow-status-report"></a>Statusrapport för e-postflöde

**Statusrapporten för Mailflow** innehåller information om meddelanden om skadlig kod, skräppost, nätfiske och kantblockerade meddelanden. Mer information finns i [Statusrapport för Mailflow](view-mail-flow-reports.md#mailflow-status-report).

## <a name="malware-detection-in-email-report"></a>Identifiering av skadlig kod i e-postrapport

Identifieringen **av skadlig kod i e-postrapporten** visar information om identifiering av skadlig kod i inkommande och utgående e-postmeddelanden (skadlig kod som upptäckts av Exchange Online Protection eller EOP). Mer information om skydd mot skadlig programvara i EOP finns [i Skydd mot skadlig kod i EOP](anti-malware-protection.md).

 Det sammanlagda vyfiltret tillåter 90 dagar, medan detaljtabellfiltret bara tillåter 10 dagar.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer Identifiering av skadlig kod i \> **Dashboard** **e-post**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=MalwareDetections> .

![Identifiering av skadlig kod i e-postwidget i instrumentpanelen Rapporter](../../media/malware-detections-widget.png)

Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filter** och välja:

- **Startdatum** och **slutdatum**
- **Inkommande**
- **Utgående**

![Rapportvyn i identifieringen av skadlig kod i e-postrapporten](../../media/malware-detections-report-view.png)

Om du klickar på **Visa informationstabell**kan du se följande information:

- **Datum**
- **Avsändarens adress**
- **Mottagaradress**
- **Meddelande-ID**
- **Ämne**
- **Filnamn**
- **Namn på skadlig kod**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="sent-and-received-email-report"></a>Skickad och mottagen e-postrapport

Rapporten **Skickat och mottaget e-post** innehåller information om skadlig kod, skräppost, regler för e-postflöde (kallas även transportregler) och avancerade identifieringar av skadlig kod när e-post kommer in i tjänsten. Mer information finns i [Skicka och mottagen e-postrapport](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Rapport om identifiering av skräppost

Rapporten **Skräppostidentifiering visar** skräppostmeddelanden som blockerades av EOP. Meddelanden räknas individuellt, inte per mottagare. Om till exempel samma skräppostmeddelande skickades till 100 mottagare i organisationen räknas det som ett meddelande.

Den sammanlagda vyn tillåter 90 dagars filtrering, medan informationstabellen tillåter 10 dagars filtrering.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **Skräppostidentifieringar**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=SpamDetections> .

![Widgeten Skräppostidentifieringar i instrumentpanelen Rapporter](../../media/spam-detections-report-widget.png)

Mer information om skydd mot skräppost finns [i Skydd mot skräppost i EOP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Rapportvy för rapporten Skräppostidentifiering

Följande diagram är tillgängliga i rapportvyn:

- **Bryt ned efter: Åtgärd:** Följande händelsetyper visas:

  - **Filtrerat spaminnehåll**
  - **Spam IP-block**
  - **Block av kuvert för skräppost**
  - **Spam DBEB filter:** Katalog baserad kant blockering (DBEB)

  När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många objekt som blockerades den dagen och hur dessa objekt kategoriseras.

  ![Åtgärdsvyn i rapporten Skräppostidentifiering](../../media/spam-detections-report-action-view.png)

- **Bryt ned efter:Riktning**: Följande anvisningar visas:

  - **Inkommande**
  - **Utgående**

  ![Riktningsvyn i rapporten Skräppostidentifiering](../../media/spam-detections-report-direction-view.png)

Om du klickar på **Filter** i en rapportvy kan du ändra resultaten med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Värden för händelsetyp

### <a name="details-table-view-for-the-spam-detections-report"></a>Informationstabellvy för rapporten Skräppostidentifiering

Om du klickar på **Visa informationstabell** i en rapportvy visas följande information:

- **Datum**
- **Avsändarens adress**
- **Mottagaradress**
- **Händelsetyp**
- **Åtgärder**
- **Ämne**

Om du klickar på **Filter** i en informationstabell kan du ändra resultaten med följande filter:

- **Startdatum** och **slutdatum**
- Riktningsvärden
- Värden för händelsetyp

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="spoof-detections-report"></a>Rapport över förfalskningar

Rapporten **Spoof detections** visar hur många falska e-postmeddelanden som upptäcktes och vilka som ansågs vara "bra" (falska e-postmeddelanden gjorda av legitima affärsmässiga skäl). För mer information om förfalskning, se [Anti-spoofing skydd i EOP](anti-spoofing-protection.md).

Den samlade vyn av rapporten tillåter 90 dagars filtrering, medan detaljvyn endast tillåter tio dagars filtrering.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **Spoof-identifieringar**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Spoof identifieringar widget i rapporterna instrumentpanelen](../../media/spoof-detections-widget.png)

När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många falska e-postmeddelanden som kom fram.

Du kan filtrera både diagrammet och informationstabellen genom att klicka på **Filter** och välja ett eller flera av följande värden:

- **Startdatum** och **slutdatum**

- **Bra post**

- **Fångad som skräppost**

![Rapportvy i rapporten Falska identifieringar](../../media/spoof-detections-report-view.png)

Om du klickar på **Visa informationstabell**kan du se följande information:

- **Datum**
- **Förfalskad avsändare**
- **Sann avsändare**
- **IP-adress för avsändare**
- **Åtgärder**
- **Antal meddelanden**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

**Statusrapporten för hotskydd** är tillgänglig i både EOP och Office 365 ATP. Rapporterna innehåller dock olika data. EOP-kunder kan till exempel visa information om skadlig kod som identifierats i e-post, men inte information om [skadliga filer som identifierats i SharePoint Online, OneDrive eller Microsoft Teams](atp-for-spo-odb-and-teams.md). Mer information om Office 365 ATP-rapporter finns i [Visa rapporter för avancerat skydd mot office 365](view-reports-for-atp.md).

Det här är en smart rapport som visar skadlig e-post som har identifierats och blockerats, och den gör det möjligt för säkerhetsadministratörer att identifiera trender eller avgöra om organisationsprinciper behöver justeras.

Om du vill visa rapporten öppnar du [Security & Compliance Center](https://protection.office.com), går till **Instrumentpanelen för rapporter** och väljer Status för skydd mot \> **Dashboard** **hot**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .

![Statuswidget för hotskydd i instrumentpanelen Rapporter](../../media/threat-protection-status-report-widget.png)

Som standard visar diagrammet data för de senaste 7 dagarna. Om du klickar på **Filter**kan du välja ett datumintervall på 90 dagar (utvärderingsprenumerationer kan vara begränsade till 30 dagar). I detaljtabellvyn kan filtrering filtreras i 30 dagar.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportvy för statusrapporten för hotskydd

Följande vyer är tillgängliga:

- **Visa data efter: Översikt**: Följande identifieringsinformation visas:

  - **Skadlig e-post**
  - **E-post phish**
  - **Skadlig kod för innehåll**

  ![Översiktsvy i statusrapporten för hotskydd](../../media/threat-protection-status-report-overview-view.png)

- **Visa data efter: Innehåll \> Skadlig kod**<sup>1</sup>: Följande information visas för Office 365 ATP-organisationer:

  - **Anti-malware motor**
  - **Fildetonation**

  ![Vyn Innehålls skadlig kod i statusrapporten för hotskydd](../../media/threat-protection-status-report-content-malware-view.png)

- **Bryt ner av: Detektionsteknik** och **Visa data efter: E-post \> Phish:** Följande information visas:

  - **ATP-genererat URL-rykte**<sup>1</sup>
  - **Avancerat phish-filter**
  - **Anti-parodi: DMARC misslyckande**
  - **Anti-parodi: Intra-org**
  - **Anti-parodi: extern domän**
  - **Varumärke personifiering**
  - **Domänpersonifiering**<sup>1</sup>
  - **EOP URL rykte**
  - **Allmänt phish-filter**
  - **Andra**
  - **Phish ZAP**<sup>2</sup>
  - **URL detonation**<sup>1</sup>
  - **Användarens personifiering**<sup>1</sup>

  ![Identifieringsteknikvyn för nätfiskemeddelande i statusrapporten för hotskydd](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Bryt ner av: Detektionsteknik** och **Visa data efter: E Malware: \> **Följande information visas:

  - **ATP-genererat filrykte**<sup>1</sup>
  - **Anti-malware motor**<sup>1</sup>
  - **Filtypsblock för skadlig kod**
  - **Fil detonation**<sup>1</sup>
  - **Rykte om skadliga filer**
  - **Malware ZAP**<sup>2</sup>
  - **Andra**

  ![Identifieringsteknikvy för skadlig kod i statusrapporten för hotskydd](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Bryt ned efter: Principtyp** och **Visa data efter: E-post \> Phish** eller **Visa data efter: E Malware: \> **Följande information visas:

  - **Anti-malware**
  - **Säker fastsättning**<sup>1</sup>
  - **Anti-phish (anti-phish)**
  - **Anti-spam**
  - **Regel för e-postflöde** (kallas även transportregel)
  - **Andra**

  ![Principtypsvy för nätfiskemeddelande i statusrapporten För hotskydd](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Bryt ner efter: Leveransstatus** och **Visa data efter: E-post \> Phish** eller **Visa data av: E Malware: \> **Följande information visas:

  - **Leveransen misslyckades**
  - **Tappade**
  - **Vidarebefordras**
  - **Värdpostlåda: Anpassad mapp**
  - **Värdpostlåda: Borttagna objekt**
  - **Värdpostlåda: Inkorg**
  - **Värdpostlåda: Skräppost**
  - **Lokal server: Levererad**
  - **Karantän**

  ![Leveransstatusvy för nätfiskemeddelande i statusrapporten för hotskydd](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>Endast 1</sup> Office 365 ATP

<sup>2</sup> Zero-hour auto purge (ZAP) är inte tillgängligt i fristående EOP (det fungerar bara i Exchange Online-postlådor).

Om du klickar på **Filter**kan du ändra rapporten med följande filter:

- **Startdatum** och **slutdatum**
- Identifieringsvärde
- **Skyddad av** (endast Office 365 ATP): **ATP** eller **EOP**. Observera att den här filterbara egenskapen inte är tillgänglig i **Visa data efter: Content \> Malware**.

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Informationstabellvy för statusrapporten för hotskydd

Om du klickar på **Visa informationstabell**beror informationen som visas på vilket diagram du tittade på:

- **Visa data efter: Innehåll \> Skadlig kod:**

  - **Datum**
  - **Plats**
  - **Regisserad av**
  - **Namn på skadlig kod**

- **Visa data efter: Översikt**: **Knappen Ingen visa information tabell** är tillgänglig.

- Alla andra diagram:

  - **Datum**
  - **Ämne**
  - **Avsändare**
  - **Mottagare**
  - **Detekteras av**
  - **Leveransstatus**
  - **Källa till kompromisser**

Om du klickar på **Filter**kan du ändra rapporten med följande filter:

- **Startdatum** och **slutdatum**
- Identifieringsvärde
- **Skyddad av** (endast Office 365 ATP): **ATP** eller **EOP**. Observera att den här filterbara egenskapen inte är tillgänglig i **Visa data efter: Content \> Malware**.

## <a name="top-malware-report"></a>Topprapport för skadlig kod

Top **malware** rapporten visar de olika typer av skadlig kod som upptäcktes av [anti-malware skydd i EOP](anti-malware-protection.md).

Om du vill visa rapporten öppnar du [Security & Compliance Center](https://protection.office.com), går till **Instrumentpanelen för rapporter** och väljer Topp skadlig \> **Dashboard** **kod**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=TopMalware> .

![Widgeten Bästa skadlig kod på instrumentpanelen Rapporter](../../media/top-malware-report-widget.png)

När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig kod och hur många meddelanden som har upptäckts ha den skadliga koden.

![Rapportvyn för skadlig kod](../../media/top-malware-report-view.png)

Om du klickar på **Visa informationstabell**kan du se följande information:

- **Bästa malware**
- **Räkna**

Om du klickar på **Filter** i rapportvyn eller detaljtabellvyn kan du ange ett datumintervall med **Startdatum** och **Slutdatum**.

## <a name="url-threat-protection-report"></a>Rapport om skydd av URL-hot

> [!NOTE]
> Den här rapporten är endast tillgänglig i Office 365 Advanced Threat Protection (ATP). Till exempel en Microsoft 365 E5-prenumeration eller ett ATP-plan 1- eller ATP-plan 2-tillägg.

**Rapporten för skydd av URL-hot** innehåller sammanfattnings- och trendvyer för upptäckta hot och åtgärder som vidtas på URL-klick som en del av [ATP Safe Links](atp-safe-links.md). Den här rapporten kommer inte att ha klickdata från användare där principen Säkra länkar tillämpas har alternativet **Spåra inte användarens klick** markerat.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **URL-skydd**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportvy för rapporten om skydd mot URL-hot

**Url-hotskyddsrapporten** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:

- **URL klicka skydd åtgärd**: Visar antalet URL klick av användare i organisationen och resultatet av klick:

  - **Blockerade**
  - **Blockerad och klickad igenom**
  - **Klickade igenom under genomsökningen**

  Ett klick anger att användaren har klickat sig igenom blocksidan till den skadliga webbplatsen (administratörer kan inaktivera klickning i principer för säkra länkar).

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - De tillgängliga klickskyddsåtgärderna, plus värdet **Tillåten** att se information för alla URL-klick (inte bara blockerade klick).

  ![URL-klickskyddsåtgärdsvyn i rapporten för skydd mot URL-hot](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL-klick för program**: Visar antalet URL-klick för program som stöder säkra länkar i Office 365 ATP:

  - **E-postklient**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Annat**

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Tillgängliga program.

### <a name="details-table-view-for-the-threat-protection-report"></a>Information om tabellvy för rapporten om hotskydd

Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid av alla klick som sker inom organisationen under de senaste sju dagarna med följande information:

- **Klicka på tid**
- **Användare**
- **Url**
- **Åtgärder**
- **Program**

Om du klickar på **Filter** i detaljtabellvyn kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="user-reported-messages-report"></a>Rapport över användarrapporterade meddelanden

Rapporten **Användares rapporterade meddelanden** visar information om e-postmeddelanden som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)med hjälp av tillägget Rapportera meddelande .

Information är tillgänglig för varje meddelande, inklusive leveransorsaken, ett sådant undantag för skräppostprinciper eller e-postflödesregel som konfigurerats för din organisation. Om du vill visa information markerar du ett objekt i listan med användarrapporter och visar sedan informationen på flikarna **Sammanfattning** och **Information.**

![Rapporten Användarrapporterade meddelanden visar meddelanden som användare som är märkta som skräppost, inte skräppost eller nätfiskeförsök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Så här visar du den här rapporten i [Security & Compliance Center:](https://protection.office.com)

- Gå **Threat management** till \> **Dashboard** \> **Användarrapporterade meddelanden**för hothanteringshantering .

- Gå till **Hothantering** \> **Granska** \> **användarrapporterade meddelanden**.

![I Security & Compliance Center väljer du \> Meddelanden om granskning av hothantering \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> För att rapporten Användarrapporterade meddelanden ska fungera korrekt **måste granskningsloggning vara aktiverat** för Office 365-miljön. Detta görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online. Mer information finns i [Aktivera eller inaktivera granskningsloggsökning för Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Vilka behörigheter behövs för att visa dessa rapporter?

Om du vill visa och använda rapporterna måste du vara medlem i den angivna rollgruppen i Security & Compliance Center **och** Exchange Online.

- I Security & Compliance Center måste du vara medlem i någon av följande rollgrupper:

  -Organisationshantering - Säkerhetsadministratör (du kan också göra detta i [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- I Exchange Online måste du vara medlem i någon av följande rollgrupper:

  -Organisationshantering -Endast visa organisationshantering -Visa-endast mottagare -efterlevnadshantering

Mer information finns [i Behörigheter i rollgrupper för Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och Hantera i Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i dina rapporter dubbelkollar du att dina principer är korrekt inställda. Mer information finns i [Skydda mot hot](protect-against-threats.md).

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot skräppost och skadlig kod i EOP](anti-spam-and-anti-malware-protection.md)

[Smarta rapporter och insikter i Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
