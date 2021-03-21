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
description: Lär dig hur du installerar och använder tillägget Microsoft Skräppostrapportering för att rapportera skräppost, icke-skräppost och nätfiske till Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a6386307b24d879cac9dd2390d9080cd2cb8b5b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920366"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installera och använda tillägget Skräppostrapportering för Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Om du för närvarande inte använder tillägget Skräppostrapportering rekommenderar vi [](enable-the-report-message-add-in.md) istället tillägget Rapportmeddelande eller Rapportera [nätfiske.](enable-the-report-phish-add-in.md) Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Med hjälp av tillägget Skräppostrapportering för Microsoft Outlook kan användare skicka falska positiva resultat (bra e-post som har markerats som skräppost), falska negativa e-postmeddelanden (felaktigt tillåtna e-postmeddelanden) och nätfiskemeddelanden till Microsoft. Om din organisation inte använder Exchange Online Protection (till exempel lokal Exchange eller andra e-posttjänster än Exchange Online) påverkar inte inskickingen av skräppostrapporten skräppostfiltreringen.

I det här avsnittet förklaras hur du installerar och använder tillägget Skräppostrapportering.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill installera tillägget Skräppostrapportering läser du avsnittet Installera tillägget Skräppostrapportering [längre fram](#install-the-junk-email-reporting-add-in) i den här artikeln.

- Tillägget Skräppostrapportering fungerar med följande versioner av Outlook:

  - Outlook 2013 eller senare
  - Outlook ingår i Microsoft 365-appar för företag

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Använd tillägget Skräppostrapportering för att rapportera skräppost och nätfiskemeddelanden

1. För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du något av följande metoder för att rapportera skräppost och nätfiske:

   - Markera meddelandet eller öppna meddelandet. Gå till **fliken** Start **eller** Meddelande i menyfliksområdet, klicka **på Skräppost** och välj sedan Rapportera som **skräppost eller** Rapportera **som nätfiske**.

     ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - Högerklicka på meddelandet, välj Skräppost **och** välj sedan Rapportera **som skräppost eller** Rapportera som **nätfiske.**

     ![Rapportera skräppost och nätfiske genom att högerklicka](../../media/junk-email-reporting-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan Rapportera **som skräppost eller** Rapportera som **nätfiske.**

     ![Rapportera flera skräppost- eller nätfiskemeddelanden från högerklickning](../../media/junk-email-reporting-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapport**. Om du ändrar dig klickar du **på Rapportera inte**.

   ![Dialogrutan Rapportera som skräppost](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttades till mappen Skräppost om den rapporterades som skräppost.
   - Borttagna om det har rapporterats som nätfiske.

   Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Använd tillägget Skräppostrapportering om du vill rapportera icke-skräppost och nätfiskemeddelanden från mappen Skräppost

1. Använd någon av följande metoder i mappen Skräppost för att rapportera skräppost med falska positiva resultat eller nätfiskemeddelanden:

   - Markera meddelandet eller öppna meddelandet. På fliken **Start** **eller Meddelande** i menyfliksområdet klickar du på **Inte** skräppost och väljer sedan Rapportera som **Inte skräppost** eller Rapportera **som nätfiske.**

     ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Högerklicka på meddelandet, klicka på **Skräppost och** välj sedan Rapportera som **Inte skräppost** eller Rapportera **som nätfiske.**

     ![Rapportera inte skräppost eller nätfiske från att högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Markera flera meddelanden, högerklicka och välj sedan Rapportera **som Inte skräppost** eller Rapportera som **nätfiske.**

     ![Rapportera flera meddelanden som inte är skräppost eller nätfiske från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Läs informationen i dialogrutan som visas och klicka på **Rapport**. Om du ändrar dig klickar du **på Rapportera inte**.

   ![Dialogrutan Rapportera som inte skräppost](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttades till mappen Skräppost om den rapporterades som skräppost.
   - Borttagna om det har rapporterats som nätfiske.

   Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="install-the-junk-email-reporting-add-in"></a>Installera tillägget Skräppostrapportering

- Du måste ha administratörsbehörighet på den dator där du installerar tillägget.

- Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och ladda ned lämplig .msi-fil för din version av Office till en plats som är lätt att hitta:

  - **32-bitars**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bitars**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- För Outlook 2013 eller senare krävs endast Microsoft .NET Framework 2.0. I Windows 10 kan du inte installera .NET Framework 2.0 från en nedladdning.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installera tillägget Skräppostrapportering med hjälp av installationsguiden

1. Stäng Outlook på datorn.

2. I Windows 10 kontrollerar du att .NET Framework 2.0 är aktiverat. Anvisningar finns i [Aktivera .NET Framework 3.5 på Kontrollpanelen.](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. Leta reda på .msi-filen som du laddade ned och dubbelklicka på den.

4. På sidan **Välkommen till tilläggsprogrammet För rapportering av skräppost klickar** du på **Nästa.**

5. Granska licensavtalet, klicka **på Jag accepterar villkoren i licensavtalet om** du godkänner villkoren och klicka sedan på **Nästa.**

6. När guiden är klar klickar du på **Slutför.**

Starta Outlook.

Leta efter knappen **Skräppost** i menyfliksområdet i Outlook. Nu kan du rapportera skräppost till Microsoft genom att markera skräppostmeddelandena i Inkorgen och klicka på **knappen Rapportera** skräppost.

Välj nedåtpilen bredvid Skräppost **för fler** alternativ, till exempel Rapport som **nätfiske** om du vill rapportera nätfiskemeddelanden till Microsoft. I skräppostmappen kan du också välja **Rapportera** inte skräppost om ett e-postmeddelande felaktigt identifierats som skräppost.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installera rapporteringsmeddelande för skräppost Add-In tyst läge

1. Stäng Outlook på datorn.

2. Installera .NET Framework 2.0 i Windows 10 genom att köra följande kommando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Om du vill installera tillägget utan interaktion med användarna öppnar du kommandotolken och använder följande syntax:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` anger det maximala antalet meddelanden som du kan välja för en enskild inskicking. Giltiga värden är 1 till 50. Standardvärdet är 15.

   - `BccEmailAddress` ytterligare mottagare av hemlig kopia som ska få en kopia av alla användarinskick. Standardvärdet är tomt (inga ytterligare mottagare av hemlig kopia).

   I det här exemplet installeras 64-bitarsversionen av tillägget från den angivna sökvägen med standardinställningarna.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   I det här exemplet installeras 32-bitarsversionen av tillägget från den angivna sökvägen med följande ytterligare inställningar:

   - Upp till 20 meddelanden kan väljas i en enda inskickning.
   - junkreports@contoso.com och hollyd@treyresearch.net får du kopior av alla inskickade filer.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har installerat tillägget Skräppostrapportering genom att göra något av följande i Outlook:

- Markera meddelandet eller öppna meddelandet. Klicka på **Skräppost** **på fliken** Start eller Meddelande **i** menyfliksområdet och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräppostrapportering**
  - **Rapportera hjälp om skräppost online**

  ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- Högerklicka på meddelandet, välj Skräppost **och** kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**
  - **Alternativ för skräppostrapportering**
  - **Rapportera hjälp om skräppost online**

  ![Rapportera skräppost och nätfiske genom att högerklicka](../../media/junk-email-reporting-right-click.png)

- Markera flera meddelanden, högerklicka och kontrollera att följande alternativ är tillgängliga:

  - **Rapportera som skräppost**
  - **Rapportera som nätfiske**

  ![Rapportera flera skräppost- eller nätfiskemeddelanden från högerklickning](../../media/junk-email-reporting-right-click-multiple.png)

- Gör de föregående åtgärderna i **mappen Skräppost** och kontrollera att de tidigare alternativen **för** skräppostrapportering nu är **Inte skräppost.**

  ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräppost eller nätfiske från att högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera meddelanden som inte är skräppost eller nätfiske från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Avinstallera tillägget Skräppostrapportering

När du stänger Outlook kan du använda någon av följande procedurer för att avinstallera tillägget Skräppostrapportering:

- **Kontrollpanelen:** Tryck på Windows-tangenten + R. I dialogrutan **Kör** som öppnas anger du och `control appwiz.cpl` klickar sedan på **OK.**

  Leta upp och **välj tillägget Microsoft Skräppostrapportering i** listan och klicka sedan på **Avinstallera**.

- **Windows** Installer-paket: Hitta eller hämta lämplig .msi-fil och dubbelklicka på den.

  - **32-bitars**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bitars**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  I dialogrutan som visas väljer du Ta **bort microsoft-tillägget Skräppostrapportering för Outlook och** klickar sedan på **Nästa.**

- **Tyst läge:** Hitta eller hämta lämplig MSI-fil. I kommandotolken ersätter \<PathToFile\> du med platsen för .msi-filen och kör något av följande kommandon:

  - **32-bitars**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bitars**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

När du öppnar Outlook efter avinstallationen ska alternativen för skräppost, inte skräppost och nätfiskerapportering vara borta.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Felsökning av tillägget Rapportering av skräppost

Ibland kan du uppleva problem med Outlook när du har lagt till tillägget Skräppostrapportering. I det här avsnittet beskrivs problem som du kan stöta på samt tips för att lösa problemen.

### <a name="troubleshooting-for-users"></a>Felsökning för användare

Ett eller flera av följande problem uppstår:

- Ingenting händer när du klickar **på Rapportera skräppost**
- Outlook slutar svara när du markerar ett e-postmeddelande
- Rapporterad skräppost kan inte levereras på grund av ett "olevererbart" svar

Lös problemet genom att göra följande:

1. Stäng och starta om Outlook.
2. Skapa och skicka ett testmeddelande samt kontrollera att mottagaren har fått meddelandet.
3. Kontakta administratören om problemet kvarstår.

För andra metoder som du kan använda för att skicka meddelanden till Microsoft, se [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>Felsökning för administratörer

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problem: Ett felmeddelande visas kontinuerligt som ber användarna att kontakta systemadministratören

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

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problem: Användarna valde att inte få en bekräftelsemeddelande när de rapporterar meddelanden, och nu vill de få tillbaka uppmaningen

1. Skapa `ConfirmReportJunk` registernyckeln med värdet "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Starta om Outlook.