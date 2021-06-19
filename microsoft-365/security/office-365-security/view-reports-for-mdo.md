---
title: Visa rapporter för Defender för Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan läsa mer om hur de hittar och använder Defender Office 365-rapporter som finns tillgängliga i Microsoft 365 Defender portalen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9279614571c123ad92f1684f86175b410c6c5c
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022862"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Visa Defender för Office 365 i Microsoft 365 Defender portalen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365 abonnemang 1 eller Microsoft Defender för tillägg för Office 365 Abonnemang 2) innehåller en mängd olika säkerhetsrelaterade rapporter. Om du har [nödvändiga](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)behörigheter kan du visa de här rapporterna  i Microsoft 365 Defender-portalen genom att gå till Rapporterar e-& för samarbete \>  \> **E& och samarbetsrapporter.** Om du vill gå direkt **till sidan & e-post och** samarbetsrapporter öppnar du <https://security.microsoft.com/emailandcollabreport> .

![Skicka & via e-post och samarbetsrapporter i Microsoft 365 Defender portalen](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> Säkerhetsrapporter för e-post som inte kräver Defender för Office 365 beskrivs i Visa [e-postsäkerhetsrapporter i Microsoft 365 Defender portalen.](view-email-security-reports.md)
>
> Rapporter som är relaterade till e-postflödet finns nu Exchange administrationscenter (EAC). Mer information om rapporterna finns i [E-postflödesrapporter i det nya Exchange administrationscentret.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

## <a name="safe-attachments-file-types-report"></a>Valv Rapport över bifogade filer

> [!NOTE]
> Rapporten **Valv bifogade filer försvinner** så småningom. Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)

## <a name="safe-attachments-message-disposition-report"></a>Valv Dispositionsrapport för bifogade filer

> [!NOTE]
> Dispositionen **Valv bifogade filer försvinner** så småningom. Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)

## <a name="mail-latency-report"></a>E-postsvarstid – rapport

I **rapporten E-postsvarstid** visas en samlad vy av den e-postleverans och detonationstid som har varit lång inom organisationen. Leveranstiderna för e-post i tjänsten påverkas av ett antal faktorer och den absoluta leveranstiden i sekunder är ofta inte en bra indikator på ett lyckat resultat eller ett problem. En långsam leveranstid på en dag kan ses som en genomsnittlig leveranstid på en annan dag eller tvärtom. Meddelandet levereras som kvalificerar sig baserat på statistiska data om observerade leveranstider för andra meddelanden.

Klientsidan och nätverksfördröjning ingår inte.

Om du vill visa rapporten öppnar du [Microsoft 365 Defender portalen](https://security.microsoft.com)och går till **Rapporterar** \> **e-& samarbete** \> **E& samarbetsrapporter**. På sidan **E& över samarbetsrapporter hittar** du Svarstidsrapport för **e-post** och klickar sedan **på Visa information.** Gå direkt till rapporten genom att öppna <https://security.microsoft.com/mailLatencyReport> .

![Rapportwidget för e-postfördröjning på sidan & för e-postsamarbete](../../media/mail-latency-report-widget.png)

På sidan **E-postfördröjningsrapport** är följande flikar tillgängliga på **sidan Med svarstid för e-post:**

- **50:e percentilen**: Det här är mitten för leveranstid för meddelanden. Du kan betrakta det här värdet som en genomsnittlig leveranstid. Den här fliken är markerad som standard.
- **90:e percentilen**: Det här anger en lång svarstid för meddelandeleveransen. Det tog bara 10 % längre tid än det här värdet att leverera.
- **99:e percentilen**: Det här anger den högsta svarstiden för meddelandeleveransen.

Oavsett vilken flik du väljer visas meddelanden ordnade i följande kategorier i diagrammet:

- **Svarstid för e-postleverans**
- **Detonationer**

När du hovrar över en kategori i diagrammet kan du se en uppdelning av svarstiden i varje kategori.

![50:e percentilvyn i rapporten E-postsvarstid](../../media/mail-latency-report-50th-percentile-view.png)

Om du klickar **på Filter** kan du filtrera både diagrammet och informationstabellen med hjälp av följande värden:

- **Datum (UTC)**: **Startdatum** **och slutdatum**
- **Meddelandevy:** Något av följande värden:
  - **Alla meddelanden**
  - **Meddelanden som innehåller bifogade filer eller URL-adresser**
  - **Detonerade meddelanden**

När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**

I informationstabellen under diagrammet finns följande information tillgänglig:

- **Datum (UTC)**
- **Percentiler:** **50,** **90** eller **99**
- **Antal meddelanden**
- **Total svarstid**

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

Statusrapporten **För skydd** mot hot är en vy som samlar information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365. Mer information finns i [Statusrapport för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)

## <a name="url-threat-protection-report"></a>Rapport om skydd mot URL-hot

Rapporten **om skydd mot URL-hot** ger sammanfattnings- och trendvyer för identifierade hot och åtgärder som vidtas på URL-klick som en del av Valv [Länkar.](safe-links.md) Du kan inte klicka på data från användare i Valv länkprincipen som har markerats med alternativet Spåra inte **användarklick.**

Om du vill visa rapporten öppnar du [Microsoft 365 Defender portalen](https://security.microsoft.com)och går till **Rapporterar** \> **e-& samarbete** \> **E& samarbetsrapporter**. På sidan **E& och samarbetsrapporter** hittar du **sidan URL-skydd** och klickar sedan **på Visa information.** Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/URLProtectionActionReport> .

![Widget för URL-skyddsrapport på sidan & för e-postsamarbete](../../media/url-protection-report-widget.png)

De tillgängliga vyerna på **sidan för skydd mot URL-hot** beskrivs i följande avsnitt.

> [!NOTE]
> Det här är en *rapport om skyddtrender,* vilket innebär att data representerar trender i en större datauppsättning. Därför är data i diagrammen inte tillgängliga i realtid här, men data i detaljtabellen är det, så du kan se en liten avvikelse mellan dem. Diagrammen uppdateras en gång var fjärde timme och innehåller data för de senaste 90 dagarna.

### <a name="view-data-by-url-click-protection-action"></a>Visa data via URL,klickskyddsåtgärd

![Vy för URL-klickskyddsåtgärd i rapporten om skydd mot URL-hot](../../media/url-threat-protection-report-url-click-protection-action-view.png)

I **åtgärdsvyn Visa data via URL** klickar du på Skydd visas antalet URL-klick som användare i organisationen har klickat på och resultatet av klicket:

- **Tillåtet:** Användaren har tillåtits att navigera till URL-adressen.
- **Blockerad:** Användaren blockerades från att navigera till URL-adressen.
- **Blockeras och klickas igenom:** Användaren har valt att fortsätta navigera till URL-adressen.
- **Klickade igenom under genomsökningen:** Användaren har klickat på länken innan genomsökningen var klar.

Ett klick anger att användaren har klickat igenom blockeringssidan till den skadliga webbplatsen (administratörer kan inaktivera klicka i Valv-länkar).

Om du klickar **på** Filter kan du ändra rapporten och detaljtabellen genom att välja ett eller flera av följande värden i den utfällade menyn som visas:

- **Datum (UTC)**: **Startdatum** **och slutdatum**
- **Identifiering:**
  - **Tillåts**
  - **Blockeras**
  - **Blockeras och klickas igenom**
  - **Klickade igenom under genomsökning**
- **Domäner**: URL-domänerna som visas i rapportresultaten.
- **Mottagare**

När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**

I detaljtabellen under diagrammet visas följande närtidsvy över alla klick som har hänt inom organisationen de senaste 7 dagarna:

- **Klicktid**
- **Användare**
- **URL**
- **Åtgärd**
- **Program**

### <a name="view-data-by-url-click-by-application"></a>Visa data per URL, klicka på efter program

![URL-klick på efter programvy i rapporten om skydd mot URL-hot](../../media/url-threat-protection-report-url-click-by-application-view.png)

I **vyn Visa data per URL som klickas** på efter programvy visas antalet URL-klickningar från appar som stöder Valv Länkar:

- **E-postklient**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **Andra**

Om du klickar **på** Filter kan du ändra rapporten och detaljtabellen genom att välja ett eller flera av följande värden i den utfällade menyn som visas:

- **Datum (UTC)**: **Startdatum** **och slutdatum**
- **Identifiering:** Tillgängliga appar från diagrammet.
- **Domäner**: URL-domänerna som visas i rapportresultaten.
- **Mottagare**

När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**

I detaljtabellen under diagrammet visas följande närtidsvy över alla klick som har hänt inom organisationen de senaste 7 dagarna:

- **Klicktid**
- **Användare**
- **URL**
- **Åtgärd**
- **Program**

## <a name="additional-reports-to-view"></a>Ytterligare rapporter att visa

Utöver rapporterna som beskrivs i den här artikeln finns det flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:

<br>

****

|Rapport|Ämne|
|---|---|
|**Utforskaren** (Microsoft Defender Office 365 abonnemang 2) eller identifieringar i realtid **(Microsoft** Defender för Office 365 abonnemang 1)|[Hotutforskaren (och realtidsidentifieringar)](threat-explorer.md)|
|**Säkerhetsrapporter för** e-post, till exempel rapporten De största avsändarna och mottagarna, förfalskningsrapporten och rapporten Om identifiering av skräppost.|[Visa e-postsäkerhetsrapporter på Microsoft 365 Defender portalen](view-email-security-reports.md)|
|**E-postflödesrapporter,** till exempel vidarebefordransrapporten, statusrapporten E-postflöde och rapporten Betrodda avsändare och mottagare.|[E-postflödesrapporter i det Exchange administrationscentret](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|**URL-spårning för Valv länkar** (endast PowerShell). I utdata för den här cmdleten visas resultatet Valv åtgärder under de senaste sju dagarna.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**E-posttrafikresultat för EOP och Microsoft Defender för Office 365** (endast PowerShell). Utdata för denna cmdlet innehåller information om Domän, Datum, Händelsetyp, Riktning, Åtgärd och Antal meddelanden.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-postdetaljrapporter för EOP och Defender Office 365 identifieringar** (endast PowerShell). Utdata från denna cmdlet innehåller information om skadliga filer eller URL:er, nätfiskeförsök, personifiering och andra potentiella hot i e-postmeddelanden och filer.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?

För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Microsoft 365 Defender portalen:

- **Organisationshantering**
- **Säkerhetsadministratör**
- **Säkerhetsläsare**
- **Global Reader**

Mer information finns i [Behörigheter i Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).

**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll i Administrationscenter för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i Defender för Office 365 kontrollerar du att dina principer är korrekt konfigurerade. Organisationen måste ha [principer Valv länkar](set-up-safe-links-policies.md) och principer [Valv](set-up-safe-attachments-policies.md) för att Defender Office 365 ska finnas på plats. Se även [Skydd mot skräppost och skadlig programvara.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Relaterade ämnen

[Smarta rapporter och insikter i Microsoft 365 Defender portalen](reports-and-insights-in-security-and-compliance.md)

[Rollbehörigheter (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
