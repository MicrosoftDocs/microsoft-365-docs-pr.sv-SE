---
title: Administratörsinskickningar
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de använder portalen inskickade innehåll i Säkerhets- & och efterlevnadscenter för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och filer till Microsoft för genomsökning.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288795"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administrationsinskickning för att skicka misstänkt skräppost, nätt phish, URL:er och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)


I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen Inskickade i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.

När du skickar ett e-postmeddelande får du:

1. **Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.
2. **Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen åsidosätter våra tjänstefilterprinciper.
3. **Payload reputation/detonation**: En undersökning av alla URL:er och bifogade filer i meddelandet.
4. **Analys av** grader: Granska gjort av mänskliga graders för att bekräfta om meddelanden är skadliga.

> [!IMPORTANT]
> Analys av nyttolast och detonation och grader görs inte i alla klientorganisationen. Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationens gräns i efterlevnadssyfte.

Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan** För inskicking använder du <https://protection.office.com/reportsubmission> .

- Om du vill skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

  - **Organisationshantering** i [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

    Observera att medlemskap i den här rollgruppen krävs för att visa användarinskickningar till den anpassade [postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.

- Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. I Säkerhets- & Efterlevnadscenter går  du till Sändning av hothantering, kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan på \>  **Ny inskickad inskicking.** 

2. Använd **den utfälltext** för ny inskickning som ser ut att skicka meddelandet, URL:en eller den bifogade filen enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tveksamt e-postmeddelande till Microsoft

1. Välj **E-post i** avsnittet **Objekttyp.** Använd **något av följande alternativ** i avsnittet Överföringsformat:

   - **Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i rubriken **X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.

   - **Fil:** Klicka **på Välj fil.** Leta upp och markera .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna.**

   > [!NOTE]
   > Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden som är så gamla som 30 dagar. Andra administratörer kan bara gå tillbaka 7 dagar.

2. I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot. Principkontrollen avgör om genomsökning av e-post har kringgåts på grund av principer för användare eller organisation.

3. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Ska ha blockerats:** Välj **Skräppost,** **nätfiske** eller **skadlig kod.** Om du är osäker kan du använda ditt bästa omdöme.

4. Klicka på knappen Skicka när du **är** klar.

   ![Exempel på URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt URL till Microsoft

1. Välj URL i avsnittet **Objekttyp.**  I rutan som visas anger du den fullständiga WEBBADRESSen (till `https://www.fabrikam.com/marketing.html` exempel).

2. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Bör ha blockerats:** Välj **nätfiske eller** **skadlig kod.**

3. Klicka på knappen Skicka när du **är** klar.

   ![Exempel på e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

1. Välj **Bifogad fil i** avsnittet **Objekttyp.**

2. Klicka **på Välj fil.** Leta upp och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna.**

3. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Bör ha blockerats:** **Skadlig** programvara är det enda alternativet och väljs automatiskt.

4. Klicka på knappen Skicka när du **är** klar.

   ![Exempel på inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Visa administratörsinskickningar

I Säkerhets- & Efterlevnadscenter går  du till Sändning av hothantering, kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan på \>  **Ny inskickad inskicking.** 

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter inskicknings-ID (ett GUID-värde som tilldelas till varje inskickat värde) genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera. Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkor klickar du **på knappen** Överförings-ID och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/Filnamn**
- **Skickat av**
- **Typ av inskicking**
- **Status**

![Filteralternativ för administratörsinskickningar](../../media/admin-submission-email-filter-options.png)

Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

Under diagrammet finns det tre flikar: **E-post** (standard), **URL och** **bifogad fil.**

### <a name="view-admin-email-submissions"></a>Visa inskickade e-postinskick för administratörer

Klicka på **fliken E-post.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Inskickings-ID:** Ett GUID-värde som har tilldelats till varje sändning.
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskicking**
- **Leveransorsak**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.

#### <a name="admin-submission-rescan-details"></a>Information om administratörsinskickning

Meddelanden som skickas som inskickade administratörer genomsöks på ny sida och resultaten visas i den utfällna informationen:

- Om det var fel i avsändarens e-postautentisering vid leverans.
- Information om principträffar som kan ha påverkat eller åsidosättt ett meddelandes bedömning.
- Aktuella detonationsresultat för att se om URL:erna eller filerna som finns i meddelandet är skadliga eller inte.
- Feedback från graders.

Om en åsidosättning hittades ska det slutföras om några minuter. Om det inte uppstod något problem med e-postautentisering eller e-postleverans påverkades inte av en åsidosättning kan det ta upp till en dag för feedback från grader.

### <a name="view-admin-url-submissions"></a>Visa url-inskickade administratörs-URL

Klicka på **fliken URL.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Inskickings-ID**
- **Skickat av**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Typ av inskicking**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.

### <a name="view-admin-attachment-submissions"></a>Visa inskickade bifogade filer från administratörer

Klicka på **fliken Bifogade** filer.

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Inskickings-ID**
- **Skickat av**<sup>\*</sup>
- **Filnamn**<sup>\*</sup>
- **Typ av inskicking**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.

## <a name="view-user-submissions-to-microsoft"></a>Visa användarinskick till Microsoft

Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapport nätfiske eller använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben kan  du se vad användarna rapporterar på fliken Användarinsändning.

1. Gå till & för hantering av  hothantering i Säkerhets- \> **och efterlevnadscentret.**

2. Välj fliken **Användarinskickningar** och klicka sedan på **Ny inskicking.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Skickat**
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskicking**

<sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter avsändare genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera. Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkor klickar du **på knappen** Avsändare och väljer något av följande värden:

- **Avsändningsdomän**
- **Ämne**
- **Skickat av**
- **Typ av inskicking**
- **Sender IP**

![Filteralternativ för användarinskickningar](../../media/user-submissions-filter-options.png)

Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visa användarinskickningar till den anpassade postlådan

**Om** du har konfigurerat [en anpassad](user-submission.md) postlåda för att ta emot användarrapporterade meddelanden kan du visa och även skicka meddelanden som har levererats till den rapportpostlådan.

1. Gå till & för hantering av  hothantering i Säkerhets- \> **och efterlevnadscentret.**

2. Välj fliken **Anpassad** postlåda.

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Skickat**
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskicking**

Högst upp på sidan kan du ange ett startdatum, ett slutdatum  och filtrera efter Skickat genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera. Du kan ange flera värden avgränsade med kommatecken.

Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

## <a name="undo-user-submissions"></a>Ångra användarinskickningar

När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material. Om användaren vill återställa e-post är den tillgänglig för återställning i mapparna Borttagna objekt eller Skräppost.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade postlådan

Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys. Då flyttas en användarinskickning till en administratörsinskickning.

Markera ett **meddelande i** listan på fliken Anpassad  postlåda, klicka på åtgärdsknappen och gör något av följande:

- **Rapportrensning**
- **Rapportera nätfiske**
- **Rapportera skadlig programvara**
- **Rapportera skräppost**

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
