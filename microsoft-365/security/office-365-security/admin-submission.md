---
title: Administrativa inlämningar
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur du använder portalen Inlämningar i Security & Compliance Center för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer till Microsoft för skanning.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726845"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft

I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen Inlämningar i Security & Compliance Center för att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft för skanning.

När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av webbadresser och bilagor med posten. Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer för klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).

Andra sätt att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Inlämning** använder du <https://protection.office.com/reportsubmission> .

- Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:

  - Om du vill skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad åtkomst till portalen inlämningar måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.

2. Klicka på knappen **Ny inlämning** på sidan **Inlämningar** som visas.

3. Använd **Nytt överföringsutfällbart** överföringsutfällbart som visas för att skicka meddelandet, WEBBADRESSEN eller bilagan enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tvivelaktigt e-postmeddelande till Microsoft

1. Välj **E-post**i avsnittet **Objekttyp** . I avsnittet **Inlämningsformat** använder du något av följande alternativ:

   - **Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i **x-MS-Exchange-Organization-Network-Message-Id-huvudet** i meddelandet.

   - **Arkiv**: Klicka på **Välj fil**. Leta reda på och markera FILEN .eml eller .msg i dialogrutan som öppnas och klicka sedan på **Öppna**.

2. I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot. Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av användar- eller organisationsprinciper.

3. I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:

   - **Borde inte ha blockerats**

   - **Borde ha blockerats:** Välj **Skräppost,** **Nätfiske**eller **skadlig kod**. Om du är osäker, använd ditt bästa omdöme.

4. Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.

   Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter. Du ser ytterligare information om inlämningen genom att klicka på statuslänken. Detta inkluderar resultaten av policykontrollen och återscan domen. Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell omsökning baserat på vissa attribut för e-post, URL eller fil.

5. När du är klar klickar du på knappen **Skicka.**

![Exempel på inskickad webbadress](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt WEBBADRESS till Microsoft

1. Välj **URL**i avsnittet **Objekttyp** . I rutan som visas anger du den fullständiga webbadressen (till exempel <https://www.fabrikam.com/marketing.html> ).

2. I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:

   - **Borde inte ha blockerats**

   - **Borde ha blockerats:** Välj **Nätfiske** eller **skadlig kod**.

3. När du är klar klickar du på knappen **Skicka.**

![Exempel på inlämning av e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

1. Välj **Bifogad fil**i avsnittet **Objekttyp** .

2. Klicka på **Välj fil**. Leta reda på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.

3. I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:

   - **Borde inte ha blockerats**

   - **Borde ha blockerats:** **Malware** är det enda valet, och väljs automatiskt..

4. När du är klar klickar du på knappen **Skicka.**

![Exempel på inlämning av bifogad fil](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Visa administratörsinlämningar

1. Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.

2. Kontrollera att fliken **Administratörsöverföringar** är markerad på sidan **Inlämningar** som visas.

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) kan du filtrera efter **inlämnings-ID** genom att ange ett värde i rutan och klicka på Uppdatera.Up of the top of the page, you can enter a start date, an end date, and (by default) you can filter by Submission ID by entering a value in the box and ![ clicking Refresh button ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkoren klickar du på knappen **Inlämnings-ID** och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/Filnamn**
- **Insänt av**
- **Typ av inlämning**
- **Status**

![Filteralternativ för administratörsinlämningar](../../media/admin-submission-email-filter-options.png)

Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**. Spara CSV-filen i dialogrutan som visas.

Under diagrammet finns tre flikar: **E-post** (standard), **URL**och **Bifogad fil**.

### <a name="view-admin-email-submissions"></a>Visa e-postinlämningar för administratörer

Klicka på fliken **E-post.**

Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:

- **Datum**
- **Inlämnings-ID**
- **Insänt av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **IP-adress för avsändare**<sup>\*</sup>
- **Typ av inlämning**
- **Leveransorsak**
- **Status**<sup>\*</sup>
- **Kontrolltyp**
- **Kontrollkälla**

  <sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.

### <a name="view-admin-url-submissions"></a>Visa inlämning av administratörs-URL

Klicka på fliken **URL.**

Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:

- **Datum**
- **Inlämnings-ID**
- **Insänt av**<sup>\*</sup>
- **Url**<sup>\*</sup>
- **Typ av inlämning**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.

### <a name="view-admin-attachment-submissions"></a>Visa inlämningar av administratörsbelämning

Klicka på fliken **Bifogade filer.**

Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:

- **Datum**
- **Inlämnings-ID**
- **Insänt av**<sup>\*</sup>
- **Filnamn**<sup>\*</sup>
- **Typ av inlämning**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.

## <a name="view-user-submissions-to-microsoft"></a>Visa användarinlämningar till Microsoft

Om du har distribuerat [tillägget Rapportmeddelande](enable-the-report-message-add-in.md)eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **Användares inlämningar.**

1. Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.

2. Klicka på fliken **Användare inlämningar** på sidan **Inlämningar** som visas.

Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:

- **Insänt den**
- **Insänt av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **IP-adress för avsändare**<sup>\*</sup>
- **Typ av inlämning**

<sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på Uppdatera.Up the top of the page, you can enter a start date, an end date, and (as default) you can filter by Sender by entering a value in the box and clicking ![ Refresh button ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filtervillkoren klickar du på knappen **Avsändare** och väljer något av följande värden:

- **Avsändningsdomän**
- **Ämne**
- **Insänt av**
- **Typ av inlämning**
- **IP-adress för avsändare**

![Filteralternativ för användarinlämningar](../../media/user-submissions-filter-options.png)

Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**. Spara CSV-filen i dialogrutan som visas.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visa användaröverföringar till den anpassade postlådan

Om du har [konfigurerat en anpassad postlåda](user-submission.md) för att ta emot användarrapporterade meddelanden kan du visa och även skicka meddelanden som levererades till rapportpostlådan.

1. Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.

2. Klicka på fliken **Anpassad postlåda** på sidan **Inlämningar** som visas.

Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:

- **Insänt den**
- **Insänt av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **IP-adress för avsändare**<sup>\*</sup>
- **Typ av inlämning**

Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter **Skickad** genom att ange ett värde i rutan och klicka på ![ Uppdatera-knappen ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**. Spara CSV-filen i dialogrutan som visas.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade postlådan

Om du har konfigurerat den anpassade postlådan för att avlyssna användarrapporterade meddelanden utan att skicka meddelandena till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys. Detta flyttar effektivt en användare inlämning till en administratör inlämning.

Markera ett meddelande i listan på fliken **Anpassad postlåda,** klicka på **knappen Åtgärd** och gör något av följande val:

- **Rapporten är ren**
- **Rapportera nätfiske**
- **Rapportera skadlig kod**
- **Rapportera skräppost**

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
