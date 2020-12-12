---
title: Installera och använda tillägget skräp post rapportering för Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Lär dig hur du installerar och använder tillägget skräp post rapportering i Microsoft för att rapportera skräp post, icke skräp post-och nät fiske meddelanden till Microsoft.
ms.openlocfilehash: 4345066ec180b5d7fe5ff8b537a3cd057f60c31c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658875"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installera och använda tillägget skräp post rapportering för Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du inte använder tillägget skräp post rapportering rekommenderar vi att du i stället [lägga till tillägget rapportera meddelanden](enable-the-report-message-add-in.md) . Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Med tillägget skräp post rapportering för Microsoft Outlook kan användarna skicka falska positiva (god e-post), falsk negativ (dålig e-post) och nätfiske-meddelanden till Microsoft. Om din organisation inte använder Exchange Online Protection (till exempel lokala Exchange-eller e-posttjänster som inte är Exchange Online), påverkas inte din skräp post filtrering.

I det här avsnittet förklaras hur du installerar och använder tillägget skräp post rapportering.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du installerar tillägget skräp post rapportering finns i avsnittet [installera tillägget skräp post rapportering](#install-the-junk-email-reporting-add-in) längre ned i den här artikeln.

- Tillägget skräp post rapportering fungerar med följande versioner av Outlook:

  - Outlook 2013 eller senare
  - Outlook ingår i Microsoft 365-appar för företag

- Mer information om hur du rapporterar meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Använda tillägget skräp post rapportering för att rapportera skräp post och nät fiske meddelanden

1. Använd någon av följande metoder för att rapportera skräp post och nät fiske meddelanden, för meddelanden i Inkorgen eller annan mapp för e-post, utom spam.

   - Markera meddelandet eller öppna meddelandet. Klicka på **skräp post** på fliken **Start** eller **meddelande** i menyfliksområdet och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.

     ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - Högerklicka på meddelandet, Välj **skräp post** och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.

     ![Rapportera skräp post eller nätfiske-e-postadress från höger musknapp](../../media/junk-email-reporting-right-click.png)

   - Välj flera meddelanden, högerklicka och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.

     ![Rapportera flera skräp post-eller nätfiske-meddelanden från höger musknapp](../../media/junk-email-reporting-right-click-multiple.png)

2. Läs informationen i dialog rutan som visas och klicka på **rapportera**. Om du ändrar dig klickar du på **rapportera inte**.

   ![Dialog rutan rapportera som skräp post](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialog rutan rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttas till mappen skräp post om den rapporter ATS som skräp post.
   - Borttagen om den rapporterades som nätfiske.

   Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Använda tillägget skräp post rapportering för att rapportera icke-spam-och nät fiske meddelanden från mappen skräp post

1. I mappen skräp post kan du använda någon av följande metoder för att rapportera skräp post i falsk positiv eller nätfiske:

   - Markera meddelandet eller öppna meddelandet. På fliken **Start** eller **meddelande** i menyfliksområdet klickar du på **inte skräp post** och väljer **rapportera inte som skräp post** eller **rapportera som nätfiske**.

     ![Rapportera inte skräp post eller nätfiske via menyfliksområdet i mappen skräp post](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Högerklicka på meddelandet, klicka på **skräp post** och välj sedan **rapportera som inte skräp post** eller **rapportera som nätfiske**.

     ![Rapportera inte skräp post eller nätfiske-e-postadress Högerklicka i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Välj flera meddelanden, högerklicka och välj sedan **rapportera som inte skräp post** eller **rapportera som nätfiske**.

     ![Rapportera flera inte skräp post eller nätfiske-meddelanden från höger musknapp i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Läs informationen i dialog rutan som visas och klicka på **rapportera**. Om du ändrar dig klickar du på **rapportera inte**.

   ![Dialog rutan rapportera inte som skräp post](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialog rutan rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttas till mappen skräp post om den rapporter ATS som skräp post.
   - Borttagen om den rapporterades som nätfiske.

   Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.

## <a name="install-the-junk-email-reporting-add-in"></a>Installera tillägget skräp post rapportering

- Du måste ha administratörs behörighet på den dator där du installerar tillägget.

- Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och ladda ned lämplig MSI-fil för din version av Office till en plats som är lätt att hitta:

  - **32-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- För Outlook 2013 eller senare är det enda kravet för Microsoft .NET Framework 2,0. I Windows 10 kan du inte installera .NET Framework 2,0 från en nedladdning.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installera tillägget skräp post rapportering med installations guiden

1. Stäng Outlook på datorn.

2. I Windows 10 kontrollerar du att .NET Framework 2,0 är aktiverat. Anvisningar finns i [Aktivera .NET Framework 3,5 på kontroll panelen](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).

3. Leta reda på. msi-filen du laddade ner och dubbelklicka på den.

4. Klicka på **Nästa** på sidan **Välkommen till installations programmet för skräp post** .

5. Granska licens avtalet, klicka på **Jag godkänner villkoren i licens avtalet** om du godkänner villkoren och klicka sedan på **Nästa**.

6. När guiden är klar klickar du på **Slutför**.

Starta Outlook.

Leta efter knappen **skräp post** i menyfliksområdet i Outlook. Du kan nu Rapportera skräp post meddelanden till Microsoft genom att välja skräp post meddelanden i Inkorgen och klicka på knappen **Rapportera skräp** post.

Välj nedpilen bredvid **skräp post** för fler alternativ, till exempel **rapportera som nätfiske** om du vill rapportera nät fiske meddelanden till Microsoft. I mappen skräp post kan du också välja att **rapportera inte skräp** post om ett e-postmeddelande felaktigt identifierades som skräppost.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installera Add-In för skräp post rapportering i tyst läge

1. Stäng Outlook på datorn.

2. I Windows 10 installerar du .NET Framework 2,0 genom att köra följande kommando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Om du vill installera tillägget utan några åtgärder från användaren öppnar du kommando tolken och använder följande syntax:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` anger maximalt antal meddelanden som du kan välja för en enda överföring. Giltiga värden är mellan 1 och 50. Standardvärdet är 15.

   - `BccEmailAddress` anger ytterligare hemliga kopior som kommer att få en kopia av alla användar inlämningar. Standardvärdet är tomt (inga fler mottagare av hemlig kopia).

   I det här exemplet installeras 64-bitars versionen av tillägget från den angivna sökvägen med standardinställningarna.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   I det här exemplet installeras 32-bitars versionen av tillägget från den angivna sökvägen med följande inställningar:

   - Upp till 20 meddelanden kan väljas med en enda överföring.
   - junkreports@contoso.com och hollyd@treyresearch.net ta emot kopior av alla inlägg.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrol lera att du har installerat tillägget skräp post rapportering genom att göra något av följande i Outlook:

- Markera meddelandet eller öppna meddelandet. Klicka på **skräp post** på fliken **Start** eller **meddelande** i menyfliksområdet och kontrol lera att följande alternativ är tillgängliga:

  - **Rapportera som skräp post**
  - **Rapportera som nätfiske**
  - **Alternativ för skräp post**
  - **Rapportera skräppost-onlinehjälp**

  ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- Högerklicka på meddelandet, Välj **skräp post** och kontrol lera att följande alternativ är tillgängliga:

  - **Rapportera som skräp post**
  - **Rapportera som nätfiske**
  - **Alternativ för skräp post**
  - **Rapportera skräppost-onlinehjälp**

  ![Rapportera skräp post eller nätfiske-e-postadress från höger musknapp](../../media/junk-email-reporting-right-click.png)

- Välj flera meddelanden, högerklicka och kontrol lera att följande alternativ är tillgängliga:

  - **Rapportera som skräp post**
  - **Rapportera som nätfiske**

  ![Rapportera flera skräp post-eller nätfiske-meddelanden från höger musknapp](../../media/junk-email-reporting-right-click-multiple.png)

- Gör föregående åtgärder i mappen **skräp post** och kontrol lera att tidigare alternativ för **skräp** post rapportering **inte är skräp post**.

  ![Rapportera inte skräp post eller nätfiske via menyfliksområdet i mappen skräp post](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräp post eller nätfiske-e-postadress Högerklicka i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera inte skräp post eller nätfiske-meddelanden från höger musknapp i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Avinstallera tillägget skräp post rapportering

När du har stängt Outlook kan du använda någon av följande procedurer för att avinstallera tillägget skräp post rapportering:

- **Kontroll panelen**: Tryck på Windows-tangenten + R. I dialog rutan **Kör** som öppnas anger du `control appwiz.cpl` och klickar sedan på **OK**.

  Leta reda på och markera **tillägget skräp post rapportering** i listan och klicka sedan på **Avinstallera**.

- **Windows installations paket**: Sök eller ladda ned lämplig. msi-fil och dubbelklicka på den.

  - **32-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  I dialog rutan som visas väljer du **ta bort Microsoft skräppost-e-postrapportering för Outlook** och klicka sedan på **Nästa**.

- **Tyst läge**: hitta eller ladda ned lämplig. msi-fil. Ersätt \<PathToFile\> med platsen för MSI-filen i kommando tolken och kör något av följande kommandon:

  - **32-bitar**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bitar**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

När du öppnar Outlook när du har avinstallerat bör du inte gå vidare med alternativen för skräp post, inte skräp post och nätfiske.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Felsöka tillägget skräp post rapportering

Ibland kan du få problem med Outlook när du har lagt till tillägget skräp post rapportering. I det här avsnittet beskrivs problem som du kan stöta på, tillsammans med tips för att åtgärda problemen.

### <a name="troubleshooting-for-users"></a>Fel sökning för användare

Ett eller flera av följande problem uppstår:

- Inget händer när du klickar på **Rapportera skräp post**
- Outlook slutar svara när du har valt ett e-postmeddelande
- Rapporterade att skräp post inte kan levereras på grund av ett "unleveransable"-svar

Så här löser du problemet:

1. Stäng och starta om Outlook.
2. Skapa och skicka ett test meddelande och kontrol lera att mottagaren fått meddelandet.
3. Om problemet kvarstår kontaktar du din administratör.

Andra metoder som du kan använda för att skicka meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

### <a name="troubleshooting-for-admins"></a>Fel sökning för administratörer

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problem: ett fel meddelande visas hela tiden så att användarna kan kontakta sin system administratör

1. Verifiera eller ange `LoggingLevel` register nyckel för värdet "VERBOSE":

   - **32-bitars Outlook på 32-bitars versionen av Windows**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32-bitars Outlook på 64-bitars versionen av Windows**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64-bitars Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Starta om Outlook och be användare rapportera tillbaka när de ser fel meddelandet.

3. Samla in logg informationen som finns på följande plats:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontakta Exchange Online Protection Technical Support och ge dem logg information.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problem: användarna har markerat sig för att inte få en bekräftelse när de rapporterar meddelanden och nu vill att de ska uppmanas tillbaka

1. Skapa `ConfirmReportJunk` register nyckel med värdet "true":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Starta om Outlook.
