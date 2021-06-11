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
description: Administratörer kan ta reda på hur de använder portalen för sändning i säkerhetscentret i Microsoft 365 för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och e-postbilagor till Microsoft för att återsöka.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878694"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)


I Microsoft 365 organisationer med postlådor i Exchange Online kan administratörer använda portalen för inskickade meddelanden i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.

När du skickar ett e-postmeddelande får du:

1. **Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.
2. **Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen, åsidosätter våra tjänstfilters bedömningar.
3. **Payload reputation/detonation**: Eng över alla URL:er och bifogade filer i meddelandet.
4. **Gradersanalys:** Granska utförts av grader för att bekräfta om meddelanden är skadliga.

> [!IMPORTANT]
> Analys av berytning och gradering av nyttolast görs inte i alla klientorganisationen. Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationsgränsen i efterlevnadssyfte.

Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar säkerhetscentret Microsoft 365 på <https://security.microsoft.com/> . Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.

- För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:

  - **Organisationshantering** eller **Säkerhetsläsare** i [Microsoft 365 Säkerhetscenter](permissions-microsoft-365-security-center.md).

  - **Organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Observera att medlemskap i den här rollgruppen krävs för att [visa användarinskick till den anpassade postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.

- Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. Gå till Microsoft 365 [i](../defender/overview-security-center.md)säkerhetscentret  och kontrollera att du är  på fliken Skickat för analys och klicka sedan på Skicka till **Microsoft för granskning.**

2. Använd den **utfäll plats för Skicka** till Microsoft för granskning som ser ut att skicka en bifogad fil med meddelande, URL eller e-post enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tveksamt e-postmeddelande till Microsoft

1. Välj **E-post i** avsnittet Välj **överföringstyp.** Använd **något av följande alternativ i avsnittet Lägg till** nätverksmeddelande-ID eller ladda upp e-postfilen:

   - Lägg till **meddelande-ID** för e-postnätverket: Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i rubriken **X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.

   - **Upload e-postfilen:** Klicka på **Bläddra bland filer**. Leta rätt på och välj .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna**.

   > [!NOTE]
   > Möjligheten att skicka meddelanden som gamla som 30 dagar har tillfälligt stängts av för Defender för Office 365 kunder. Administratörer kan bara gå tillbaka 7 dagar.

2. I avsnittet **Välj en mottagare som har ett problem** anger du den mottagare som du vill köra en principkontroll mot. Principkontrollen avgör om förbikoppling av e-post beror på användar- eller organisationsprinciper.

3. Välj **något av följande alternativ i avsnittet Välj** en orsak för att skicka till Microsoft:

   - **Borde inte ha blockerats**

   - **Ska ha blockerats:** Välj **Skräppost,** **Nätfiske** eller **Skadlig kod.** Om du är osäker kan du använda ditt bästa omdöme.

4. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på ny URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt URL till Microsoft

1. I avsnittet **Välj överföringstyp** väljer du **URL**. I rutan som visas anger du den fullständiga webbadressen (till exempel `https://www.fabrikam.com/marketing.html` ).

2. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Ska ha blockerats:** Välj **Nätfiske** eller **skadlig kod.**

3. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på ny e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Skicka en misstänkt e-postbilaga till Microsoft

1. I avsnittet **Välj typ av inskickning väljer** du Bifogad fil i **e-post**.

2. Klicka **på Välj fil**. Leta rätt på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.

3. Välj **något av följande** alternativ i avsnittet Orsak till inskickning:

   - **Borde inte ha blockerats**

   - **Borde ha blockerats:** **Skadlig programvara** är det enda alternativet och väljs automatiskt.

4. När du är klar klickar du på **skicka-knappen.**

   ![Exempel på ny inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Visa objekt som skickats för analys

I säkerhetscentret Microsoft 365 du till **Inlämningar** och kontrollerar att du är på fliken **Skickat för** analys

I kommandofältet i mitten av sidan kan du ange ett startdatum, ett slutdatum och (som standard) kan du filtrera efter **Sändnings-ID** (ett GUID-värde som är kopplat till varje inskickat värde) genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera. Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkoren klickar **du på knappen** Filter och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/Filnamn**
- **Skickat av**
- **Typ av inskickat material**
- **Status**

![Nya filteralternativ för administratörsinskick](../../media/admin-submission-email-filter-options.png)

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** I dialogrutan som visas sparar du den .csv filen.

Under diagrammet finns tre flikar: **E-post** (standard), URL och E-postbilaga .  

### <a name="view-admin-email-submissions"></a>Visa e-postinskick från administratör

Du kan lägga till **eller ta bort** kolumner från vyn genom att klicka på knappen Anpassa kolumner nästan längst ned på sidan:

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

Meddelanden som skickas i administrationsinskick genomsöks på annat sätt och resultaten visas i den utfällkommning som visas i inskickade uppgifter:

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

### <a name="view-email-attachment-submissions"></a>Visa inskickade e-postbilalar

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

Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapportfiske eller om användarna använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben kan  du se vad användarna rapporterar på fliken Användarinsändning.

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

![Nya filteralternativ för användarinskick](../../media/user-submissions-filter-options.png)

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** I dialogrutan som visas sparar du den .csv filen.

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

Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.** I dialogrutan som visas sparar du den .csv filen.

> [!NOTE]
> Om organisationer är konfigurerade att endast skicka till en anpassad postlåda skickas inte rapporterade meddelanden för sökning och resultat i portalen för användarrapporter är alltid tomma.

## <a name="undo-user-submissions"></a>Ångra användarinskick

När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material. Om användaren vill återställa e-posten kan den återställas i mapparna Borttagna objekt eller Skräppost.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade postlådan

Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys. Då flyttas en användarinskickning till en administratörsinskickning.

På fliken **Användarrapporterade** meddelanden väljer du ett  meddelande i listan, klickar på knappen Åtgärd och gör ett av följande val:

- **Rapportrensning**
- **Rapportera nätfiske**
- **Rapportera skadlig programvara**
- **Rapportera skräppost**

![Nya alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
