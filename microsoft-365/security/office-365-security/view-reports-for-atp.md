---
title: Visa rapporter för avancerat hotskydd
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Hitta och använda rapporter för avancerat skydd mot office 365 i &amp; Säkerhetsefterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4210ea30457215f9adc2984f24f161dc94985873
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434131"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visa rapporter för avancerat hotskydd för Office 365

Office 365 Atp-organisationer (Advanced Threat Protection) (till exempel Microsoft 365 E5-prenumerationer eller ATP-abonnemang 1 eller ATP-abonnemang 2) innehåller en mängd säkerhetsrelaterade rapporter. Om du har [de behörigheter som krävs](#what-permissions-are-needed-to-view-the-atp-reports)kan du visa dessa rapporter i Security & Compliance Center genom att gå till **Reports** \> **Instrumentpanelen**för rapporter . Om du vill gå direkt till instrumentpanelen för rapporter öppnar du <https://protection.office.com/insightdashboard> .

![Instrumentpanelen Rapporter i security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Rapport över avancerade filtyper för hotskydd

Rapporten **Avancerat skydd mot hotfiltyper** visar vilken typ av filer som har identifierats som skadliga av [ATP Safe Attachments](atp-safe-attachments.md).

 Den sammanlagda vyn av rapporten tillåter 90 dagars filtrering, medan detaljvyn endast tillåter 10 dagars filtrering.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för Rapporter** och väljer Office \> **Dashboard** **ATP-filtyper**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widgeten Office ATP-filtyper i instrumentpanelen Rapporter](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Informationen i den här rapporten finns också i [rapporten Disposition för avancerat skydd mot skydd.](#advanced-threat-protection-message-disposition-report)

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Rapportvy för rapporten Avancerad skyddsskydd

Följande vyer är tillgängliga:

- **Visa data efter: Fil:** Diagrammet innehåller följande information:

  - **Skadliga Excel-bilagor**
  - **Skadliga Flash-bilagor**
  - **Skadliga PDF-bilagor**
  - **Skadliga PowerPoint-bilagor**
  - **Skadliga webbadresser**
  - **Bifogade filer med skadliga Word**
  - **Skadliga körbara bilagor**
  - **Andra**

  När du hovrar över en viss dag (datapunkt) kan du se fördelningen av typer av skadliga filer som upptäcktes av [ATP Safe Attachments](atp-safe-attachments.md) och [skydd mot skadlig kod i EOP](anti-malware-protection.md).

  ![Filvy i ATP-filtyperrapporten](../../media/atp-file-types-report-file-view.png)

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma filtypsvärden som visas i diagrammet.

- **Visa data efter: Meddelande**: Diagrammet innehåller följande information:

  - **Blockera åtkomst**
  - **Meddelanden ersatta**
  - **Meddelanden som övervakas**
  - **Ersatt av dynamisk e-postleverans:** Mer information finns i [Dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md).

  ![Meddelandevy i ATP-filtyperrapporten](../../media/atp-file-types-report-message-view.png)

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>Informationstabellvy för rapporten Avancerad skyddsskydd

Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid över alla klick som inträffar inom organisationen under de senaste 10 dagarna. Vilken information som visas beror på diagrammet du tittade på:

- **Visa data efter: Arkiv:**

  - **Datum**
  - **Mottagaradress**
  - **Avsändarens adress**
  - **Meddelande-ID:** Tillgängligt i fältet **Meddelande-ID-huvud** i meddelandehuvudet och ska vara unikt. Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (notera vinkelparenteserna).
  - **ﬁlen**

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma filtypsvärden som visas i diagrammet.

- **Visa data efter: Meddelande:**

  - **Datum**
  - **Mottagaradress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **ﬁlen**
  - **Ämne**

  Om du klickar på **Filter**kan du ändra resultaten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="advanced-threat-protection-message-disposition-report"></a>Dispositionsrapport för avancerat skydd mot skydd

**Atp-meddelandedispositionsrapporten** visar de åtgärder som har vidtagits för e-postmeddelanden som har identifierats som skadliga innehåll.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer Office \> **Dashboard** **ATP-meddelandedisposition**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Office 365 ATP-meddelandedispositionswidget i instrumentpanelen Rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Informationen i den här rapporten finns också i [rapporten Avancerade typer av hotskydd](#advanced-threat-protection-file-types-report).

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Rapportvy för meddelandedispositionsrapporten för avancerat skydd

Följande vyer är tillgängliga:

- **Visa data efter: Meddelande**: Diagrammet innehåller följande information:

  - **Blockera åtkomst**
  - **Meddelanden ersatta**
  - **Meddelanden som övervakas**
  - **Ersatt av dynamisk e-postleverans:** Mer information finns i [Dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md).

  ![Meddelandevy i ATP-filtyperrapporten](../../media/atp-file-types-report-message-view.png)

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.

- **Visa data efter: Fil:** Diagrammet innehåller följande information:

  - **Skadliga Excel-bilagor**
  - **Skadliga Flash-bilagor**
  - **Skadliga PDF-bilagor**
  - **Skadliga PowerPoint-bilagor**
  - **Skadliga webbadresser**
  - **Bifogade filer med skadliga Word**
  - **Skadliga körbara bilagor**
  - **Andra**

  När du hovrar över en viss dag (datapunkt) kan du se fördelningen av typer av skadliga filer som upptäcktes av [ATP Safe Attachments](atp-safe-attachments.md) och [skydd mot skadlig kod i EOP](anti-malware-protection.md).

  ![Filvy i ATP-filtyperrapporten](../../media/atp-file-types-report-file-view.png)

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma filtypsvärden som visas i diagrammet.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Informationstabellvy för meddelandedispositionsrapporten för avancerat skydd

Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid över alla klick som inträffar inom organisationen under de senaste 10 dagarna. Vilken information som visas beror på diagrammet du tittade på:

- **Visa data efter: Meddelande:**

  - **Datum**
  - **Mottagaradress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **ﬁlen**
  - **Ämne**

  Om du klickar på **Filter**kan du ändra resultaten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.

- **Visa data efter: Arkiv:**

  - **Datum**
  - **Mottagaradress**
  - **Avsändarens adress**
  - **Meddelande-ID**
  - **ﬁlen**

  Om du klickar på **Filter**kan du ändra rapporten med följande filter:

  - **Startdatum** och **slutdatum**
  - Samma filtypsvärden som visas i diagrammet.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

**Statusrapporten för hotskydd** är en enda vy som samlar information om skadligt innehåll och skadlig e-post som upptäckts och blockerats av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Office 365 ATP. Mer information finns i [statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Rapport om skydd av URL-hot

**Rapporten för skydd av URL-hot** innehåller sammanfattnings- och trendvyer för upptäckta hot och åtgärder som vidtas på URL-klick som en del av [ATP Safe Links](atp-safe-links.md). Den här rapporten kommer inte att ha klickdata från användare där principen Säkra länkar tillämpas har alternativet **Spåra inte användarens klick** markerat.

Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **URL-skyddsrapport**. Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widgeten URL-skyddsrapport på instrumentpanelen Rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> Det här är en *trendrapport*för skydd , vilket innebär att data representerar trender i en större datauppsättning. Därför är data i den aggregerade vyn inte tillgängliga i realtid här, men data i detaljtabellvyn är, så du kan se en liten diskrepans mellan de två vyerna.

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

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Informationstabellvy för rapporten om skydd mot URL-hot

Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid av alla klick som sker inom organisationen under de senaste sju dagarna med följande information:

- **Klicka på tid**
- **Användare**
- **Url**
- **Åtgärder**
- **Program**

Om du klickar på **Filter** i detaljtabellvyn kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="additional-reports-to-view"></a>Ytterligare rapporter att visa

Förutom de ATP-rapporter som beskrivs i det här avsnittet finns flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:

|Rapport|Ämne|
|---|---|
|**Explorer** (ATP Plan 2) eller **realtidsidentifieringar** (ATP-plan 1)|[Hotutforskaren (och realtidsidentifieringar)](threat-explorer.md)|
|**Säkerhetsrapporter för e-post**, till exempel rapporten Toppavsändare och mottagare, rapporten Spoof-e-post och rapporten Skräppostidentifieringar.|[Visa säkerhetsrapporter för e-post i Säkerhets- & Compliance Center](view-email-security-reports.md)|
|**E-postflödesrapporter**, till exempel rapporten Vidarebefordran, statusrapporten för e-postflödet och rapporten Toppavsändare och mottagare.|[Visa e-postflödesrapporter i Säkerhets- & Compliance Center](view-mail-flow-reports.md)|
|**URL-spårning för ATP-säkra länkar** (endast PowerShell). Utdata från den här cmdleten visar resultatet av ATP Safe Links-åtgärder under de senaste sju dagarna.|[Få-urltrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**E-posttrafikresultat för EOP och ATP** (endast PowerShell). Utdata för den här cmdleten innehåller information om domän, datum, händelsetyp, riktning, åtgärd och meddelanderäkning.|[Hämta-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport) <br/><br/> |
|**E-postinformationsrapporter för EOP- och ATP-identifieringar** (endast PowerShell). Utdata från den här cmdleten innehåller information om skadliga filer eller webbadresser, nätfiskeförsök, personifiering och andra potentiella hot i e-post eller filer.|[Hämta-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Vilka behörigheter behövs för att visa ATP-rapporterna?

Om du vill visa och använda de rapporter som beskrivs i det här avsnittet **måste du ha en lämplig roll tilldelad för både Security Compliance Center och &amp; Administrationscenter för Exchange**.

- För Security & Compliance Center måste du ha tilldelats någon av följande roller:

  - Organisationshantering
  - Säkerhetsadministratör (detta kan tilldelas i Administrationscentret för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Säkerhetsoperatör (detta kan tilldelas i Administrationscentret för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Säkerhetsläsare

- För Exchange Online måste du ha någon av följande roller tilldelad i administrationscentret för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) eller med PowerShell-cmdletar (se [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Organisationshantering
  - Organisationshantering endast med enbart vy
  - Rollen Endast visa mottagare
  - Hantering av efterlevnad

Mer information finns i följande resurser:

- [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)

- [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i ATP-rapporterna dubbelkollar du att dina principer är korrekt konfigurerade. Din organisation måste ha [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) och [ATP-principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) definierade för att ATP-skydd ska vara på plats. Se även [skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Relaterade ämnen

[Smarta rapporter och insikter i Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Rollbehörigheter (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
