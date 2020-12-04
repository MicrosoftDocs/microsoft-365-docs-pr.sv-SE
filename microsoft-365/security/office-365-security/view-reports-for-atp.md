---
title: Visa Defender för Office 365-rapporter i instrument panelen rapporter
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Hitta och använda rapporter för Microsoft Defender för Office 365 i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a237049c9ebbccf1c01feeb21129496e16d437b2
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572495"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Visa Defender för Office 365-rapporter i rapport instrument panelen i säkerhets & efterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365 abonnemang 1 eller Microsoft Defender för Office 365 abonnemang 2 tillägg) innehåller flera olika säkerhets relaterade rapporter. Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till **Reports** \> **instrument panelen** för rapporter. Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .

![Instrument panelen för rapporter i säkerhets & efterlevnad](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Rapport om fil typer i Defender för Office 365

I rapporten **Defender för Office 365-filtyper** visas en typ av filer som identifieras i skadlig kod för [bifogade](atp-safe-attachments.md)filer.

 I den sammanställda vyn i rapporten kan du använda 90 dagar för att filtrera den, men i detaljvyn kan du bara tillåta 10 dagars filtrering.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Defender för Office 365-filtyper**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget för Office 365-filtyper i rapport instrument panelen](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Informationen i den här rapporten är också tillgänglig i [meddelande dispositions rapporten för Defender för Office 365](#defender-for-office-365-message-disposition-report).

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Rapportvy för rapporten fil typer i Defender för Office 365

Följande vyer är tillgängliga:

- **Visa data genom: fil**: diagrammet innehåller följande information:

  - **Skadliga Excel-bilagor**
  - **Skadliga Flash-filer**
  - **Skadliga PDF-filer**
  - **Skadliga PowerPoint-bilagor**
  - **Illasinnade URL: er**
  - **Skadliga Word-bilagor**
  - **Skadliga körbara filer**
  - **Gemensamma**

  När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma fil typs värden som visas i diagrammet.

- **Visa data via: meddelande**: diagrammet innehåller följande information:

  - **Blockera åtkomst**
  - **Meddelanden ersatta**
  - **Meddelanden som övervakas**
  - **Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Vyn detaljerad tabell för fil typer i Defender för Office 365

Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna. Informationen som visas beror på diagrammet du tittade på:

- **Visa data per: fil**:

  - **Datum**
  - **Mottagarens adress**
  - **Avsändarens adress**
  - **Meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt. Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).
  - **Fil**

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma fil typs värden som visas i diagrammet.

- **Visa data via: meddelande**:

  - **Datum**
  - **Mottagarens adress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **Fil**
  - **Ämne**

  Om du klickar på **filter** kan du ändra resultatet med följande filter:

  - **Start datum** och **slutdatum**
  - Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="defender-for-office-365-message-disposition-report"></a>Meddelande disposition för Defender för Office 365

I rapporten för att visa **ATP** visas de åtgärder som vidtogs för e-postmeddelanden som identifierats som skadligt innehåll.

Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Defender för Office 365 meddelande disposition**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget för Defender för Office 365 meddelande dispositioner i instrument panelen rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Informationen i den här rapporten är också tillgänglig i [rapporten fil typer i Defender för Office 365](#defender-for-office-365-file-types-report).

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Rapportvy för meddelande dispositions rapport för Defender för Office 365

Följande vyer är tillgängliga:

- **Visa data via: meddelande**: diagrammet innehåller följande information:

  - **Blockera åtkomst**
  - **Meddelanden ersatta**
  - **Meddelanden som övervakas**
  - **Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .

- **Visa data genom: fil**: diagrammet innehåller följande information:

  - **Skadliga Excel-bilagor**
  - **Skadliga Flash-filer**
  - **Skadliga PDF-filer**
  - **Skadliga PowerPoint-bilagor**
  - **Illasinnade URL: er**
  - **Skadliga Word-bilagor**
  - **Skadliga körbara filer**
  - **Gemensamma**

  När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma fil typs värden som visas i diagrammet.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Vyn detaljerad tabell för meddelande dispositionen för Defender för Office 365

Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna. Informationen som visas beror på diagrammet du tittade på:

- **Visa data via: meddelande**:

  - **Datum**
  - **Mottagarens adress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **Fil**
  - **Ämne**

  Om du klickar på **filter** kan du ändra resultatet med följande filter:

  - **Start datum** och **slutdatum**
  - Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .

- **Visa data per: fil**:

  - **Datum**
  - **Mottagarens adress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **Fil**

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Samma fil typs värden som visas i diagrammet.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="mail-latency-report"></a>E-postrapport

I **rapporten e-postsvars tid** visas en sammanslagen för leverans-och spräng tiden i din organisation. Leverans tiden för e-post påverkas av många faktorer och den absoluta leverans tiden i sekunder är ofta inte en bra indikation på framgång eller ett problem. En långsam leverans tid på en dag kan betraktas som en genomsnittlig leverans tid på en annan dag, eller tvärtom. I **rapporten e-postsvars tid** görs ett försök att kvalificera meddelande leverans baserat på statistik om den observerade leverans tiden för andra meddelanden:

- **femtio percentil**: det här är mitten för leverans tider för meddelanden. Du kan betrakta detta värde som en genomsnittlig leverans tid.
- **nittionde percentil**: Detta indikerar en hög latens för meddelande leverans. Det tog längre tid än 10 procent av meddelandena att leverera.
- **99th percentil**: här visas den högsta svars tiden för meddelande leverans.

Klient sidan och nätverks fördröjningen ingår inte.

Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **rapport om e-postsvar**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget för tids rapport för e-post i instrument panelen rapporter](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Rapportvy för rapport om e-postsvar

När du öppnar rapporten är fliken **femtio percentil** markerad som standard.

Som standard innehåller den här vyn ett diagram som är konfigurerat med följande filter:

- **Datum**: de senaste 7 dagarna
- **Meddelande vy**:
  - Översprängta meddelanden

I det här diagrammet visas meddelanden ordnade i följande kategorier:

- **Leverans svars tid för e-post**
- **Fördröjning för sprängning**

När du hovrar över en kategori i diagrammet kan du se en uppdelning av svars tiden i varje kategori.

![E-postrapport](../../media/mail-latency-report.png)

Om du klickar på **filter** i rapportvyn kan du ändra resultatet med följande filter:

- Alla meddelanden
- Meddelanden som innehåller bilagor eller URL: er

Om du klickar på fliken **nittionde percentiler** eller på fliken **99th percentiler** används samma standard filter från vyn **50 percentiler** .

### <a name="details-table-view-for-the-mail-latency-report"></a>Vyn detaljerad tabell för rapporten e-postsvar

Följande information visas i vyn detaljerad tabell:

- **Datum**
- **Värden**
- **Antal meddelanden**
- **Total svars tid**

![Rapport information om e-postsvar](../../media/mail-latency-report-details.png)

Ovanstående visar att genomsnittlig tids åtgång den 14 november för alla meddelanden som levererats och sprängat sig **108,033** sekunder.

Tabellen information innehåller samma information på varje flik.

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

Status rapporten för **hotets skydd** är en enkel vy som innehåller information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365. För mer information, se [status rapport för hot skydd](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Rapport om skydd mot URL-hotet

**Rapporten skydd mot URL-hotet** innehåller översikts-och trend lägen för hot som upptäcks och åtgärder som vidtas på URL-adresser till vissa [säkra länkar](atp-safe-links.md). Den här rapporten kommer inte att behöva klicka på data från användare där **principen för Safe** Links har Aktiver ATS.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **URL-skydd**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widgeten rapport om URL-skydd i instrument panelen rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> Det här är en *skydds trend rapport* som visar trender i en större data mängd. Därför är data i den aggregerade vyn inte tillgängliga i real tid, men data i vyn detaljerad tabell är så att du kan se en liten avvikelse mellan de två vyerna.

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportvy för rapport om URL-Threat

Rapporten **skydd mot URL-hotet** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:

- **Webb adress klicka på skydds åtgärd**: visar antalet URL-musklick efter användare i organisationen och resultatet av klickning:

  - **Blockerad** (användaren hindrades från att gå till URL-adressen)
  - **Blockerad och klickat genom**
  - **Klickning genom under genomsökning**

  Ett klick visar att användaren har klickat via block sidan till webbplatsen för illasinnade webbplatser (administratörer kan inaktivera Klicka genom i principer för säkra länkar).

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - De tillgängliga Klicka på skydds åtgärder plus värdet som **tillåts** (användaren kunde navigera till URL: en).

  ![URL-adress klicka på skydds åtgärd i rapporten URL-skydd](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL-adress klicka** här: visar antalet URL-musklick med program som stöder säkra länkar:

  - **E-postklient**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Annat**

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - Tillgängliga program.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Vyn detaljerad tabell för rapportering av URL-hotet

Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 7 dagarna med följande information:

- **Klicka på tid**
- **Användare**
- **:**
- **Fattning**
- **Program**

Om du klickar på **filter** i vyn detaljerad tabell kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="additional-reports-to-view"></a>Ytterligare rapporter att Visa

Utöver de rapporter som beskrivs i det här avsnittet är flera andra rapporter tillgängliga, enligt följande tabell:

****

|Rapport|Ämnes|
|---|---|
|**Explorer** (Microsoft Defender för Office 365 abonnemang 2) eller **real tids identifiering** (microsoft Defender för Office 365 abonnemang 1)|[Hotutforskaren (och realtidsidentifieringar)](threat-explorer.md)|
|**Säkerhets rapporter för e-post**, till exempel rapporten Top avsändare och mottagare, rapporten Spoof meddelanden och rapporten skräp identifiering.|[Visa säkerhets rapporter för e-post i säkerhets & efterlevnad](view-email-security-reports.md)|
|**E-postflödes rapporter**, till exempel vidarebefordran, rapporten flödes schema och rapport om avsändare och mottagare.|[Visa rapporter om e-postflöden i säkerhets & Compliance Center](view-mail-flow-reports.md)|
|**URL-spårning för säkra länkar** (endast PowerShell). Utdata från denna cmdlet visar resultaten av åtgärder för säkra länkar under de senaste sju dagarna.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Resultat för e-posttrafik för EOP och Microsoft Defender för Office 365** (endast PowerShell). Utdata från den här cmdleten innehåller information om domäner, datum, händelse typ, riktning, åtgärd och antal meddelanden.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-postdetaljerade rapporter för EOP och Defender för Office 365-identifiering** (endast PowerShell). Utdata från den här cmdleten innehåller information om skadliga filer och URL-adresser, nät fiske försök, personifiering och andra potentiella hot i e-post och filer.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Vilka behörigheter behövs för att Visa Defender för Office 365-rapporterna?

För att kunna visa och använda de rapporter som beskrivs i det här avsnittet måste du vara medlem i någon av följande roll grupper i säkerhets & Compliance Center:

- **Organisationshantering**
- **Säkerhets administratör**
- **Säkerhets läsare**
- **Global läsare**

Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

**Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i din Defender för Office 365-rapporter kontrollerar du att dina principer är korrekt konfigurerade. Din organisation måste ha principer för [säkert](set-up-atp-safe-links-policies.md) och [bifogade filer](set-up-atp-safe-attachments-policies.md) definierade för att Defender för Office 365-skydd ska vara installerat. Se även [antiskräppost-och skydd mot skadlig program vara](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Relaterade ämnen

[Smarta rapporter och insikter i säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md)
  
[Roll behörigheter (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
