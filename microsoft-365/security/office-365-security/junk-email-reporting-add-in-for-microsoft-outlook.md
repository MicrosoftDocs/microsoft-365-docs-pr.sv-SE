---
title: Installera och använda tillägget Skräppostrapportering för Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Lär dig hur du installerar och använder tillägget Microsoft Skräppostrapportering för att rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 171bdc43e565a0890cddcd1e48208b49774a5315
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167353"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installera och använda tillägget Skräppostrapportering för Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> Om du inte använder tillägget Skräppostrapportering rekommenderar vi i stället [](enable-the-report-message-add-in.md) tilläggen [Rapportmeddelande](enable-the-report-phish-add-in.md) eller Rapport nätfiske. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Med tillägget Skräppostrapportering för Microsoft Outlook kan användare skicka falska positiva meddelanden (bra e-post som har markerats som skräppost), falska negativa meddelanden (felaktig e-post tillåts) och nätfiskemeddelanden till Microsoft. Om din organisation inte använder Exchange Online Protection (till exempel lokal Exchange eller andra e-posttjänster än Exchange Online) påverkar inte inskickingen av skräppostrapporten skräppostfiltreringen.

I det här avsnittet förklaras hur du installerar och använder tillägget Skräppostrapportering.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill installera tillägget Skräppostrapportering [](#install-the-junk-email-reporting-add-in) läser du avsnittet Installera tillägget Skräppostrapportering senare i den här artikeln.

- Tillägget Skräppostrapportering fungerar med följande versioner av Outlook:

  - Outlook 2013 eller senare
  - Outlook ingår i Microsoft 365-program för företag

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Använd tillägget Skräppostrapportering för att rapportera skräppost och nätfiskemeddelanden

1. För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiske:

   - Markera meddelandet eller öppna meddelandet. Klicka på **Skräppost** **på fliken** Start eller Meddelande i **menyfliksområdet** och välj sedan Rapportera **som skräppost** eller Rapportera **som nätfiske.**

     ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - Högerklicka på meddelandet, välj **Skräppost** och välj sedan **Rapportera som skräppost eller** Rapportera som **nätfiske.**

     ![Rapportera skräppost och nätfiske genom att högerklicka](../../media/junk-email-reporting-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan Rapportera **som skräppost** eller Rapportera **som nätfiske.**

     ![Rapportera flera skräppost- eller nätfiskemeddelanden från högerklickning](../../media/junk-email-reporting-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapport.** Om du ändrar dig klickar du **på Rapportera inte.**

   ![Dialogrutan Rapportera som skräppost](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttades till mappen Skräppost om den rapporterades som skräppost.
   - Borttagna om de rapporterats som nätfiske.

   Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Använd tillägget Skräppostrapportering för att rapportera icke skräppost- och nätfiskemeddelanden från mappen Skräppost

1. Använd någon av följande metoder i mappen Skräppost för att rapportera skräppost med falska positiva resultat eller nätfiskemeddelanden:

   - Markera meddelandet eller öppna meddelandet. Klicka på **Inte** skräppost **på** fliken Start eller Meddelande i menyfliksområdet och välj sedan Rapporten **som** Inte skräppost eller Rapportera **som nätfiske.**

     ![Rapportera inte skräppost eller nätfiskemeddelande från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Högerklicka på meddelandet, klicka på **Skräppost** och välj sedan **Rapportera som** Inte skräppost eller Rapportera **som nätfiske.**

     ![Rapportera inte skräppost eller nätfiskemeddelande från att högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan Rapportera som Inte **skräppost** eller **Rapportera som nätfiske.**

     ![Rapportera flera icke-skräppost- eller nätfiskemeddelanden från högerklick i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapport.** Om du ändrar dig klickar du **på Rapportera inte.**

   ![Dialogrutan Rapportera som inte skräppost](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttades till mappen Skräppost om den rapporterades som skräppost.
   - Borttagna om de rapporterats som nätfiske.

   Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="install-the-junk-email-reporting-add-in"></a>Installera tillägget Skräppostrapportering

- Du måste ha administratörsbehörighet på den dator där du installerar tillägget.

- Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och ladda ned lämplig MSI-fil för din version av Office till en plats som är lätt att hitta:

  - **32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- För Outlook 2013 eller senare är Microsoft .NET Framework 2.0 den enda förutsättningen. I Windows 10 kan du inte installera .NET Framework 2.0 från en nedladdning.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installera tillägget Skräppostrapportering med hjälp av installationsguiden

1. Stäng Outlook på datorn.

2. Kontrollera att .NET Framework 2.0 är aktiverat i Windows 10. Instruktioner finns i [Aktivera .NET Framework 3.5 på Kontrollpanelen.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. Leta upp .msi-filen som du laddade ned och dubbelklicka på den.

4. På sidan **Välkommen till installationsprogrammet för rapportering av** skräppost för Microsoft klickar du på **Nästa.**

5. Granska licensavtalet, klicka **på Jag accepterar villkoren i licensavtalet** om du godkänner villkoren och klicka sedan på **Nästa.**

6. Klicka på Slutför när guiden är **klar.**

Starta Outlook.

Leta efter knappen **Skräppost** i menyfliksområdet i Outlook. Nu kan du rapportera skräppost till Microsoft genom att markera skräppostmeddelanden i Inkorgen och klicka på **knappen Rapportera** skräppost.

Välj nedåtpilen bredvid skräppost för **fler** alternativ, till exempel Rapport som **nätfiske** om du vill rapportera nätfiskemeddelanden till Microsoft. I skräppostmappen kan du också markera **Rapportera** inte skräppost om ett e-postmeddelande felaktigt identifierats som skräppost.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installera rapportering av skräppost i Add-In tyst läge

1. Stäng Outlook på datorn.

2. Installera .NET Framework 2.0 i Windows 10 genom att köra följande kommando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Om du vill installera tillägget utan interaktion med användarna öppnar du kommandotolken och använder följande syntax:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` anger det maximala antalet meddelanden som du kan välja för en enskild inskickning. Giltiga värden är 1 till 50. Standardvärdet är 15.

   - `BccEmailAddress` ytterligare mottagare av hemlig kopia som ska få en kopia av alla användarinskickningar. Standardvärdet är tomt (inga ytterligare mottagare av Hemlig kopia).

   I det här exemplet installeras 64-bitarsversionen av tillägget från den angivna sökvägen med standardinställningarna.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   I det här exemplet installeras 32-bitarsversionen av tillägget från den angivna sökvägen med följande ytterligare inställningar:

   - Upp till 20 meddelanden kan väljas i en enda inskickning.
   - junkreports@contoso.com och hollyd@treyresearch.net ta emot hemlig kopia av alla bidrag.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har installerat tillägget Skräppostrapportering genom att göra något av följande i Outlook:

- Markera meddelandet eller öppna meddelandet. Klicka på **Skräppost** **på fliken** Start eller Meddelande **i** menyfliksområdet och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräppostrapportering**
  - **Rapportera hjälp för Skräppost online**

  ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- Högerklicka på meddelandet, välj **Skräppost** och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräppostrapportering**
  - **Rapportera hjälp för Skräppost online**

  ![Rapportera skräppost och nätfiske genom att högerklicka](../../media/junk-email-reporting-right-click.png)

- Markera flera meddelanden, högerklicka och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**

  ![Rapportera flera skräppost- eller nätfiskemeddelanden från högerklickning](../../media/junk-email-reporting-right-click-multiple.png)

- Gör de föregående åtgärderna i **mappen Skräppost** och kontrollera att de **tidigare** alternativen för skräppostrapportering nu är **Inte skräppost.**

  ![Rapportera inte skräppost eller nätfiskemeddelande från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräppost eller nätfiskemeddelande från att högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera icke-skräppost- eller nätfiskemeddelanden från högerklick i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Avinstallera tillägget Skräppostrapportering

När du stänger Outlook kan du använda någon av följande procedurer för att avinstallera tillägget Skräppostrapportering:

- **Kontrollpanelen:** Tryck på Windows-tangenten + R. I dialogrutan **Kör** som öppnas anger du och `control appwiz.cpl` klickar sedan på **OK.**

  Leta upp och **välj tillägget Microsoft Skräppostrapportering** i listan och klicka sedan på **Avinstallera.**

- **Windows Installer paket:** Hitta eller hämta lämplig .msi-fil och dubbelklicka på den.

  - **32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  I dialogrutan som visas väljer du **Ta bort microsoft-tillägget Skräppostrapportering för Outlook och** klickar sedan på **Nästa.**

- **Tyst läge:** Hitta eller hämta lämplig MSI-fil. I kommandotolken ersätter du med MSI-filens plats \<PathToFile\> och kör något av följande kommandon:

  - **32-bitars:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bitars:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

När du öppnar Outlook efter avinstallationen ska alternativen för skräppost, inte skräppost och nätfiskerapportering vara borta.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Felsöka tillägget Skräppostrapportering

Ibland kan du uppleva problem med Outlook när du har lagt till tillägget Skräppostrapportering. I det här avsnittet beskrivs problem som du kan stöta på samt tips för att lösa problemen.

### <a name="troubleshooting-for-users"></a>Felsökning för användare

Du får ett eller flera av följande problem:

- Inget händer när du klickar **på Rapportera skräppost**
- Outlook slutar svara när du har valt ett e-postmeddelande
- Rapporterad skräppost kan inte levereras på grund av ett "olevererbart" svar

Lös problemet genom att göra följande:

1. Stäng och starta om Outlook.
2. Skapa och skicka ett testmeddelande och kontrollera att mottagaren har fått meddelandet.
3. Kontakta administratören om problemet kvarstår.

Information om andra metoder som du kan använda för att skicka meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>Felsökning för administratörer

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problem: Ett felmeddelande visas kontinuerligt som ber användarna att kontakta sina systemadministratör

1. Verifiera eller ange `LoggingLevel` registernyckeln till värdet "Utförlig":

   - **32-bitars Outlook på 32-bitars Windows:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32-bitars Outlook på 64-bitars Windows:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64-bitars Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Starta om Outlook och be användarna att rapportera när de ser felmeddelandet.

3. Samla in logginformationen som finns på följande plats:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontakta den tekniska supporten för Exchange Online Protection och ge dem logginformationen.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problem: Användarna valde att inte få någon bekräftelsefråga när de rapporterar meddelanden, och nu vill de få tillbaka uppmaningen

1. Skapa `ConfirmReportJunk` registernyckeln med värdet "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Starta om Outlook.
