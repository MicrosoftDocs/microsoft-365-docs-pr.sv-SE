---
title: Administratörs inlämningar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.openlocfilehash: ef401f34bb0bc7a9a9718443101924ad09bca8a0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947978"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft

I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.

När du skickar ett e-postmeddelande får du information om eventuella principer som kan ha tillåtit inkommande e-post till din klient organisation samt granskning av URL: er och bilagor i e-postmeddelandet. Principer som kan ha tillåtelse till ett e-postmeddelande inkluderar en enskild användares lista över betrodda avsändare och policy principer för Exchange-flöden (kallas även transport regler).

Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .

- För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

  - **Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Observera att medlemskap i den här roll gruppen krävs för att [Visa användar överföringar till den anpassade post lådan](#view-user-submissions-to-the-custom-mailbox) enligt beskrivningen längre fram i det här avsnittet.

- Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions**, kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.

2. Använd **New submission** utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tveksamt e-postmeddelande till Microsoft

1. Välj **e-post**under **objekt typ** . Använd något av följande alternativ i avsnittet **sändnings format** :

   - **Nätverks meddelande-ID**: det här är ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet.

   - **Fil**: Klicka på **Välj fil**. I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.

2. Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** . Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.

3. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Bör ha blockerats**: Välj **skräp post**, **nätfiske**eller **skadlig program vara**. Om du är osäker kan du använda ditt bästa omdöme.

4. Om filtret hoppades över på grund av principer vid överföring visas information om den policyn.

   Om filtret inte har hoppats över på grund av en eller flera principer slutförs genomsökningen flera minuter. Du får mer information om inlämningen genom att klicka på status länken. Här ingår resultaten av princip kontrollen och omsökning Verdict. OBS! detta kör inte e-postmeddelandet via Office 365 ATP-fullständig filtrerings stack igen men kör en delvis omsökning baserat på vissa av attributen för e-post, URL eller fil.

5. När du är klar klickar du på **Skicka** .

![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt URL till Microsoft

1. Välj **URL**under **objekt typ** . I rutan som visas anger du den fullständiga URL: en (till exempel `https://www.fabrikam.com/marketing.html` ).

2. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Borde ha blockerats**: Välj **nätfiske** eller **malware**.

3. När du är klar klickar du på **Skicka** .

![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

1. Välj **bilaga**under **objekt typ** .

2. Klicka på **Välj fil**. Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.

3. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...

4. När du är klar klickar du på **Skicka** .

![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Visa administratörs inlämningar

I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions**, kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.

Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/fil namn**
- **Skickades av**
- **Sändnings typ**
- **Status**

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**. Spara CSV-filen i dialog rutan som visas.

Under grafen finns det tre flikar: **e-post** (standard), **URL**och **bifogad fil**.

### <a name="view-admin-email-submissions"></a>Visa e-postinlägg för administratörer

Klicka på fliken **e-post** .

Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Sändnings-ID**: ett GUID-värde som tilldelats varje överföring.
- **Skickades av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Avsändarens IP**<sup>\*</sup>
- **Sändnings typ**
- **Leverans orsak**
- **Status**<sup>\*</sup>
- **Kontroll typ**
- **Kontroll källa**

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.

### <a name="view-admin-url-submissions"></a>Visa URL-överföringar för administratörer

Klicka på fliken **URL** .

Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Sändnings-ID**
- **Skickades av**<sup>\*</sup>
- **:**<sup>\*</sup>
- **Sändnings typ**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.

### <a name="view-admin-attachment-submissions"></a>Visa underlämning av administrativa bilagor

Klicka på fliken **bifogade filer** .

Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:

- **Datum**
- **Sändnings-ID**
- **Skickades av**<sup>\*</sup>
- **Fil namn**<sup>\*</sup>
- **Sändnings typ**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.

## <a name="view-user-submissions-to-microsoft"></a>Visa användar inlämningar till Microsoft

Om du har distribuerat [tillägget för rapport meddelanden](enable-the-report-message-add-in.md), eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kan du se vilka användare som rapporterar på fliken **användar överföringar** .

1. I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.

2. Välj fliken **användar överföringar** och klicka sedan på **ny överföring**.

Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:

- **Skickades**
- **Skickades av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Avsändarens IP**<sup>\*</sup>
- **Sändnings typ**

<sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.

Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:

- **Avsändningsdomän**
- **Ämne**
- **Skickades av**
- **Sändnings typ**
- **Avsändarens IP**

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**. Spara CSV-filen i dialog rutan som visas.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visa användar inlämningar till den anpassade post lådan

**Om** du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.

1. I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.

2. Välj fliken **egen post låda** .

Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:

- **Skickades**
- **Skickades av**<sup>\*</sup>
- **Ämne**<sup>\*</sup>
- **Avsändare**
- **Avsändarens IP**<sup>\*</sup>
- **Sändnings typ**

Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**. Spara CSV-filen i dialog rutan som visas.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade post lådan

Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys. Detta flyttar en användares överföring till en administratör.

På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:

- **Rapport klar**
- **Rapportera nätfiske**
- **Rapportera skadlig program vara**
- **Rapportera skräp post**

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
