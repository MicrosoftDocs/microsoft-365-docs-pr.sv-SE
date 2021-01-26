---
title: Administratörs inlämningar
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976609"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.

När du skickar ett e-postmeddelande får du:

1. **Kontrol lera e-postauktorisering**: information om huruvida e-postauktoriseringen lyckades eller misslyckades när den levererades.
2. **Princip träffar**: information om eventuella principer som kan ha tillåtit eller blockera inkommande e-post till din klient organisation och Åsidosätt vårt service filter verdicts.
3. **Nytto lastens rykte/spränghet**: undersökning av URL-adresser och bilagor i meddelandet.
4. **Kurs analys**: granska gjorda av de mänskliga betygen för att bekräfta att meddelanden är skadliga.

> [!IMPORTANT]
> Nytto lastens rykte/Spräng och betygs analyser utförs inte hos alla klient organisationer. Informationen blockeras från att gå utanför organisationen när data inte förväntas lämna klient organisationens gräns för efterlevnad.

Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .

- För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

  - **Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Observera att medlemskap i den här roll gruppen krävs för att [Visa användar överföringar till den anpassade post lådan](#view-user-submissions-to-the-custom-mailbox) enligt beskrivningen längre ned i den här artikeln.

- Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Rapportera misstänkt innehåll till Microsoft

1. I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.

2. Använd  utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tveksamt e-postmeddelande till Microsoft

1. Välj **e-post** under **objekt typ** . Använd något av följande alternativ i avsnittet **sändnings format** :

   - **ID för nätverks meddelande**: det här är ett GUID-värde som är tillgängligt i huvudet **x-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet, eller i **X-MS-Office365**

   - **Fil**: Klicka på **Välj fil**. I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.

   > [!NOTE]
   > Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden som gamla 30 dagar. Andra administratörer kan bara gå tillbaka sju dagar.

2. Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** . Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.

3. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Bör ha blockerats**: Välj **skräp post**, **nätfiske** eller **skadlig program vara**. Om du är osäker kan du använda ditt bästa omdöme.

4. När du är klar klickar du på **Skicka** .

   ![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt URL till Microsoft

1. Välj **URL** under **objekt typ** . I rutan som visas anger du den fullständiga URL: en (till exempel `https://www.fabrikam.com/marketing.html` ).

2. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Borde ha blockerats**: Välj **nätfiske** eller **malware**.

3. När du är klar klickar du på **Skicka** .

   ![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

1. Välj **bilaga** under **objekt typ** .

2. Klicka på **Välj fil**. Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.

3. Välj något av följande alternativ i avsnittet **orsak för inlämning** :

   - **Ska inte ha blockerats**

   - **Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...

4. När du är klar klickar du på **Skicka** .

   ![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Visa administratörs inlämningar

I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.

Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) . Du kan ange flera värden avgränsade med kommatecken.

Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:

- **Avsändare**
- **Ämne/URL/fil namn**
- **Skickades av**
- **Sändnings typ**
- **Status**

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**. Spara CSV-filen i dialog rutan som visas.

Under grafen finns det tre flikar: **e-post** (standard), **URL** och **bifogad fil**.

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

  <sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.

#### <a name="admin-submission-rescan-details"></a>Information om att söka efter administratörs uppgifter

Meddelanden som skickas i administratörs inlämningar skannas in och visas i den utfällbara informationen:

- Om det uppstod ett fel i avsändarens e-postautentisering vid leverans tillfället.
- Information om eventuella policy träffar som kan ha påverkat eller åsidosatt Verdict av ett meddelande.
- Aktuella Spräng resultat för att se om URL-adresserna eller filerna i meddelandet är skadliga eller inte.
- Feedback från betyg.

Om en åsidosättning hittas måste genomsökningen genomföras flera minuter. Om det inte fanns något problem med e-postauktorisering eller leveransen påverkas inte av en åsidosättning och feedback från betyg kan ta upp till en dag.

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

Om du har distribuerat [tillägget rapportera](enable-the-report-message-add-in.md)tillägget rapport- [nätfiske](enable-the-report-phish-add-in.md)eller personer som använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **användar överföringar** .

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

## <a name="undo-user-submissions"></a>Ångra användar inlägg

När en användare skickar ett misstänkt e-postmeddelande till den anpassade post lådan har användaren och administratören inget alternativ för att ångra sändningen. Om användaren vill återställa e-postmeddelandet kommer den att vara tillgänglig för återställning i mapparna Borttaget eller skräp post.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Skicka meddelanden till Microsoft från den anpassade post lådan

Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys. Detta flyttar en användares överföring till en administratör.

På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:

- **Rapport klar**
- **Rapportera nätfiske**
- **Rapportera skadlig program vara**
- **Rapportera skräp post**

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
