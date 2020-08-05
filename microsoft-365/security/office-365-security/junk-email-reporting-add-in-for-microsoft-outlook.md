---
title: Installera och använda tillägget Skräppostrapportering för Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Lär dig hur du installerar och använder tillägget Microsoft Junk Email Reporting för att rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft.
ms.openlocfilehash: 54b0fb634333ccb180870ab1fcc6160fd133f81e
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560527"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installera och använda tillägget Skräppostrapportering för Microsoft Outlook

> [!NOTE]
> Om du inte använder tillägget Skräppostrapportering rekommenderar vi tillägget [Rapportmeddelande i](enable-the-report-message-add-in.md) stället. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Add-in-tillägget för skräppostrapportering för Microsoft Outlook gör det möjligt för användare att skicka falska positiva identifieringar (bra e-post markerat som skräppost), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft. Om din organisation inte använder Exchange Online Protection (till exempel lokala Exchange- eller e-posttjänster än Exchange Online) påverkar inte överföringen av skräppostrapporten skräppostfiltreringen.

I det här avsnittet beskrivs hur du installerar och använder tillägget Rapportering av skräppost.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill installera tillägget Skräppostrapportering läser du [avsnittet Installera tillägget Rapportering av skräppost](#install-the-junk-email-reporting-add-in) senare i det här avsnittet.

- Tillägget Skräppostrapportering fungerar med följande versioner av Outlook:

  - Outlook 2013 eller senare
  - Outlook ingår i Microsoft 365 Apps for Enterprise

- Mer information om hur du anmäler meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Använda tillägget Skräppostrapportering för att rapportera skräppost och nätfiskemeddelanden

1. För meddelanden i Inkorgen eller någon annan e-postmapp utom skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiskemeddelanden:

   - Markera meddelandet eller öppna meddelandet. Klicka på **Skräppost**på fliken **Start** eller **Meddelande** i menyfliksområdet och välj sedan **Rapportera som skräppost** eller Rapport som **nätfiske**.

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - Högerklicka på meddelandet, välj **Skräppost**och välj sedan **Rapportera som skräppost** eller Rapport som **nätfiske**.

     ![Rapportera skräppost eller nätfiskemeddelande från högerklicka](../../media/junk-email-reporting-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan **Rapportera som skräppost** eller Rapport som **nätfiske**.

     ![Rapportera flera skräppostmeddelanden eller nätfiskemeddelanden från högerklicka](../../media/junk-email-reporting-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapportera**. Om du ändrar dig klickar du på **Rapportera inte**.

   ![Rapport som skräppostdialogruta](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttade till mappen Skräppost om den rapporterades som skräppost.
   - Borttagen om det rapporterades som nätfiske.
   
   Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Använda tillägget Skräppostrapportering för att rapportera meddelanden som inte är skräppost och nätfiske från mappen Skräppost

1. I mappen Skräppost använder du någon av följande metoder för att rapportera falska positiva skräppost eller nätfiskemeddelanden:

   - Markera meddelandet eller öppna meddelandet. Klicka på **Inte skräppost**på fliken **Start** eller **Meddelande** och välj sedan Rapportera som **Inte skräppost** eller Rapport **som nätfiske**.

     ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Högerklicka på meddelandet, klicka på **Skräppost**och välj sedan **Rapportera som Inte skräppost** eller Rapport som **nätfiske**.

     ![Rapportera inte skräppost eller nätfiskemeddelande från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan **Rapportera som Inte skräppost** eller Rapport som **nätfiske**.

     ![Rapportera flera inte skräppost eller nätfiskemeddelanden från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapportera**. Om du ändrar dig klickar du på **Rapportera inte**.

   ![Rapportera som inte skräppostdialogruta](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttade till mappen Skräppost om den rapporterades som skräppost.
   - Borttagen om det rapporterades som nätfiske.

   Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.

## <a name="install-the-junk-email-reporting-add-in"></a>Installera tillägget Rapportering av skräppost

- Du måste ha administratörsbehörighet på datorn där du installerar tillägget.

- Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och hämta lämplig MSI-fil för din version av Office till en plats som är lätt att hitta:

  - **32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- För Outlook 2013 eller senare är den enda förutsättningen Microsoft .NET Framework 2.0. I Windows 10 installerar du inte .NET Framework 2.0 från en nedladdning.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installera tillägget Skräppostrapportering med installationsguiden

1. Stäng Outlook på datorn.

2. I Windows 10 kontrollerar du att .NET Framework 2.0 är aktiverat. Instruktioner finns [i Aktivera .NET Framework 3.5 på Kontrollpanelen](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).

3. Leta reda på MSI-filen du hämtade och dubbelklicka på den.

4. Klicka på **Nästa**på sidan **Välkommen till Microsofts skräppostrapporteringsrapportering.**

5. Granska licensavtalet, klicka på **Jag godkänner villkoren i licensavtalet** om du godkänner villkoren och sedan på **Nästa**.

6. När guiden är klar klickar du på **Slutför**.

Starta Outlook.

Leta efter **skräppostknappen** i menyfliksområdet i Outlook. Nu kan du rapportera skräppostmeddelanden till Microsoft genom att markera skräppostmeddelandena i Inkorgen och klicka på knappen **Rapportera skräppost.**

Välj nedpilen **bredvid Skräppost** för fler alternativ, till exempel **Rapportera som Nätfiske** om du vill rapportera skräppost med nätfiske till Microsoft. I skräppostmappen kan du också välja **Rapportera inte skräppost** om ett e-postmeddelande har identifierats felaktigt som skräppost.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installera tillägget Rapportering av skräppost med tyst läge

1. Stäng Outlook på datorn.

2. Installera .NET Framework 2.0 i Windows 10 genom att köra följande kommando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Om du vill installera tillägget utan någon användarinteraktion öppnar du en kommandotolk och använder följande syntax:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection`anger det maximala antalet meddelanden som du kan välja för en enda inlämning. Giltiga värden är från 1 till 50. Standardvärdet är 15.

   - `BccEmailAddress`anger ytterligare mottagare av hemlig kopia som ska få en kopia av alla användarinlämningar. Standardvärdet är tomt (inga ytterligare mottagare av hemlig kopia).

   I det här exemplet installeras 64-bitarsversionen av tillägget från den angivna sökvägen med standardinställningarna.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   I det här exemplet installeras 32-bitarsversionen av tillägget från den angivna sökvägen med följande ytterligare inställningar:

   - Upp till 20 meddelanden kan väljas i en enda inlämning.
   - junkreports@contoso.com och hollyd@treyresearch.net ta emot hemlig kopia av alla inlagor.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har installerat tillägget Rapportering av skräppost gör du något av följande steg i Outlook:

- Markera meddelandet eller öppna meddelandet. Klicka på **Skräppost**på fliken **Start** eller **Meddelande** i menyfliksområdet och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräprapportering**
  - **Rapportera hjälp om skräp online**

  ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- Högerklicka på meddelandet, välj **Skräppost**och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräprapportering**
  - **Rapportera hjälp om skräp online**

  ![Rapportera skräppost eller nätfiskemeddelande från högerklicka](../../media/junk-email-reporting-right-click.png)

- Markera flera meddelanden, högerklicka och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**

  ![Rapportera flera skräppostmeddelanden eller nätfiskemeddelanden från högerklicka](../../media/junk-email-reporting-right-click-multiple.png)

- Gör tidigare åtgärder i mappen **Skräppost** och verifiera de tidigare alternativen **för skräprapportering** är nu **inte skräppost**.

  ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräppost eller nätfiskemeddelande från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera inte skräppost eller nätfiskemeddelanden från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Avinstallera tillägget Rapportering av skräppost

När du har stängt Outlook använder du någon av följande procedurer för att avinstallera tillägget Rapportering av skräppost:

- **Kontrollpanelen:** Tryck på Windows-tangenten + R. Ange dialogrutan **Kör** som öppnas `control appwiz.cpl` och klicka sedan på **OK**.

  Leta reda på och välj **Microsofts tillägg för skräppostrapportering i** listan och klicka sedan på **Avinstallera**.

- **Windows Installer-paketet**: Hitta eller hämta lämplig MSI-fil och dubbelklicka på den.

  - **32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  I dialogrutan som visas väljer du **Ta bort Microsofts tillägg för rapportering av skräppost för Outlook** och klickar sedan på **Nästa**.

- **Tyst läge:** Hitta eller ladda ner lämplig MSI-fil. Ersätt med platsen för MSI-filen i ett kommandotolksfönster \<PathToFile\> och kör något av följande kommandon:

  - **32-bitars:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bitars:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

När du öppnar Outlook efter avinstallationen bör alternativen för skräppost, inte skräppost och nätfiskerapportering vara borta.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Felsöka tillägget Rapportering av skräppost

Ibland kan det uppstå problem med Outlook när du har lagt till tillägget Skräppostrapportering. I det här avsnittet beskrivs problem som kan uppstå, tillsammans med tips för att lösa dessa problem.

### <a name="troubleshooting-for-users"></a>Felsökning för användare

Du upplever ett eller flera av följande problem:

- Ingenting händer när du klickar på **Rapportera skräppost**
- Outlook slutar svara när du har valt ett e-postmeddelande
- Rapporterad skräppost kan inte levereras på grund av ett "ej utlevererbart" svar

Så här löser du problemet:

1. Stäng och starta om Outlook.
2. Skapa och skicka ett testmeddelande och kontrollera att mottagaren har tagit emot meddelandet.
3. Om problemet kvarstår kontaktar du administratören.

Andra metoder som du kan använda för att skicka meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

### <a name="troubleshooting-for-admins"></a>Felsökning för administratörer

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problem: Ett felmeddelande visas kontinuerligt som uppmanar användare att kontakta systemadministratören

1. Verifiera eller ange `LoggingLevel` registernyckeln till värdet "Utföros":

   - **32-bitars Outlook i 32-bitars Windows:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32-bitars Outlook i 64-bitars Windows:**

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

2. Starta om Outlook och be användarna att rapportera tillbaka när de ser felmeddelandet.

3. Samla in logginformation som finns på följande plats:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontakta Exchange Online Protection Teknisk support och förse dem med logginformation.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problem: Användare som har valt att inte få en bekräftelsefråga när de rapporterar meddelanden, och nu vill de ha snabben tillbaka

1. Skapa `ConfirmReportJunk` registernyckeln med värdet "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Starta om Outlook.
