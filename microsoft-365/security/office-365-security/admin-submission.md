---
title: Administratörs inskickade material
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
description: Administratörer kan ta reda på hur de använder portalen för inskickade innehåll i Säkerhets- och efterlevnadscenter för & för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och filer till Microsoft för genomsökning.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0975d5b6c2d29c94a30f7bbc703221b80217761
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599881"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)


I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen för inskickade meddelanden i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.

När du skickar ett e-postmeddelande får du:

1. **Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.
2. **Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen, åsidosätter våra tjänstfilters bedömningar.
3. **Payload reputation/detonation**: Eng över alla URL:er och bifogade filer i meddelandet.
4. **Gradersanalys:** Granska utförts av grader för att bekräfta om meddelanden är skadliga.

> [!IMPORTANT]
> Analys av berytning och gradering av nyttolast görs inte i alla klientorganisationen. Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationsgränsen i efterlevnadssyfte.

Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd för att gå direkt **till sidan** Inskickat. <https://protection.office.com/reportsubmission>

- För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:

  - **Organisationshantering** eller **Säkerhetsläsare** i [Säkerhets- & Säkerhets- och efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

  - **Organisationshantering** i [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

    Observera att medlemskap i den här rollgruppen krävs för att [visa användarinskick till den anpassade postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.

- Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. I Säkerhets- & efterlevnadscenter går  du till Inskickade hothantering , kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan \> på **Ny inskickad inskickad information.** 

2. Använd den utfällingstext för ny inskickning som ser ut att skicka meddelandet, **URL:en** eller den bifogade filen enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tveksamt e-postmeddelande till Microsoft

1. Välj **E-post** i avsnittet **Objekttyp.** Använd **något av följande** alternativ i avsnittet Överföringsformat:

   - **Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i **rubriken X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.

   - **Fil:** Klicka på **Välj fil**. Leta rätt på och välj .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna**.

   > [!NOTE]
   > Möjligheten att skicka meddelanden som gamla som 30 dagar har tillfälligt stängts av för Defender för Office 365-kunder. Administratörer kan bara gå tillbaka 7 dagar.

2. I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot. Principkontrollen avgör om förbikoppling av e-post beror på användar- eller organisationsprinciper.

3. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Ska ha blockerats:** Välj **Skräppost,** **Nätfiske** eller **Skadlig kod.** Om du är osäker kan du använda ditt bästa omdöme.

4. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt URL till Microsoft

1. Välj URL **i avsnittet** **Objekttyp.** I rutan som visas anger du den fullständiga webbadressen (till exempel `https://www.fabrikam.com/marketing.html` ).

2. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Ska ha blockerats:** Välj **Nätfiske** eller **skadlig kod.**

3. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

1. Välj **Bifogad fil** i avsnittet **Objekttyp.**

2. Klicka **på Välj fil**. Leta rätt på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.

3. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Borde ha blockerats:** **Skadlig programvara** är det enda alternativet, och väljs automatiskt.

4. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Visa objekt som skickats för analys

I säkerhets- & säkerhets- och  \> **efterlevnadscenter** går du till Sändning av hothantering , kontrollerar att du är på **fliken Skickat för** analys

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter sändnings-ID (ett GUID-värde som är tilldelat till varje inskickat värde) genom att ange ett värde i rutan och klicka på Uppdatera knapp ![ ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkor klickar du på knappen Inskickat **ID** och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/Filnamn**
- **Skickat av**
- **Typ av inskickat material**
- **Status**

![Filteralternativ för administratörsinskick](../../media/admin-submission-email-filter-options.png)

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

Under diagrammet finns tre **flikar:** E-post (standard), **URL och** **Bifogad fil**.

### <a name="view-admin-email-submissions"></a>Visa e-postinskick från administratör

Klicka på fliken **E-post.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Överförings-ID:** Ett GUID-värde som tilldelas till varje sändning.
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskickat material**
- **Leveransorsak**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.

#### <a name="admin-submission-rescan-details"></a>Information om administratörsinskickning igen

Meddelanden som skickas i administratörsinskick genomsöks på ny plats och resultaten visas i den utfällade informationen:

- Om avsändarens e-postautentisering misslyckades vid leveransen.
- Information om politiska träffar som kan ha påverkat eller åsidosatt bedömningen av ett meddelande.
- Aktuella detonationsresultat för att se om webbadresserna eller filerna i meddelandet var skadliga eller inte.
- Feedback från grader.

Om en åsidosättning hittades bör omskanningen slutföras på några minuter. Om det inte uppstod något problem i e-postautentisering eller -leverans påverkades inte av en åsidosättning, kan feedback från grader ta upp till en dag.

### <a name="view-admin-url-submissions"></a>Visa url-inskickade administratörs-URL

Klicka på **fliken URL.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Sändnings-ID**
- **Skickat av**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Typ av inskickat material**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.

### <a name="view-admin-attachment-submissions"></a>Visa inskickade bifogade filer från administratörer

Klicka på **fliken Bifogade** filer.

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Sändnings-ID**
- **Skickat av**<sup>\*</sup>
- **Filnamn**<sup>\*</sup>
- **Typ av inskickat material**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.

## <a name="view-user-submissions-to-microsoft"></a>Visa användarinskick till Microsoft

Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapportfiske eller om användarna använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben, kan du se vad användarna rapporterar på fliken Användarinsändning. 

1. I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**

2. Välj fliken **Användarinskickningar** och klicka sedan på **Ny inskicking.**

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Skickat**
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskickat material**

<sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter avsändare genom att ange ett värde i rutan och klicka på ![ Uppdatera ](../../media/scc-quarantine-refresh.png) knapp. Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkor klickar du **på knappen** Avsändare och väljer något av följande värden:

- **Avsändningsdomän**
- **Ämne**
- **Skickat av**
- **Typ av inskickat material**
- **Sender IP**

![Filteralternativ för användarinskick](../../media/user-submissions-filter-options.png)

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visa användarinskick till den anpassade postlådan

**Om** du har konfigurerat [en anpassad postlåda för](user-submission.md) att ta emot användarrapporterade meddelanden kan du visa och skicka meddelanden som har levererats till den rapportpostlådan.

1. I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**

2. Välj fliken **Anpassad** postlåda.

Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:

- **Skickat**
- **Skickat av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Sender IP**<sup>\*</sup>
- **Typ av inskickat material**

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter **Skickat** genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera. Du kan ange flera värden avgränsade med kommatecken.

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** Spara CSV-filen i dialogrutan som visas.

> [!NOTE]
> Om organisationer är konfigurerade att endast skicka till en anpassad postlåda skickas inte rapporterade meddelanden för sökning och resultat i portalen för användarrapporter är alltid tomma.

## <a name="undo-user-submissions"></a>Ångra användarinskick

När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material. Om användaren vill återställa e-posten kan den återställas i mapparna Borttagna objekt eller Skräppost.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade postlådan

Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys. Då flyttas en användarinskickning till en administratörsinskickning.

Markera **ett meddelande i** listan på fliken Anpassad postlåda, klicka **på** knappen Åtgärd och gör något av följande:

- **Rapportrensning**
- **Rapportera nätfiske**
- **Rapportera skadlig programvara**
- **Rapportera skräppost**

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
