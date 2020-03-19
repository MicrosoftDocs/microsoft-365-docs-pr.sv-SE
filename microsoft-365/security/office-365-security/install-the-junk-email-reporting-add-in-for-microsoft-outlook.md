---
title: Installera tillägget Skräppostrapportering för Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: I den här artikeln Stöds språkInstallera tillägget skräppostrapportering SÃ¤tt du fÃ¶r skräppostrapportering
ms.openlocfilehash: 0f7a5a3cbaddf9aef5e518db38ffb36c397cd1f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811119"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installera tillägget Skräppostrapportering för Microsoft Outlook

I det här avsnittet beskrivs hur du installerar (och avinstallerar) tillägget Microsoft Skräppostrapportering för Outlook på klientdatorer i organisationen. Den aktuella versionen av tillägget (januari 2016) innehåller stöd för Outlook 2016, Outlook 2013 och Outlook 2010.

Tillägget (för alla språk som stöds) gör att du kan rapportera skräppost direkt från menyfliksområdet i Outlook. Den engelska versionen av tillägget innehåller ytterligare alternativ för att rapportera e-postproblem till Microsoft direkt från menyfliksområdet:

- Rapportera e-postmeddelanden om nätfiskebedrägerier som du får

- Rapportera e-post som felaktigt identifierats som skräppost.

## <a name="supported-languages"></a>Språk som stöds
<a name="sectionSection0"> </a>

Tillägget Skräppostrapportering stöder följande språk:

- Förenklad kinesiska

- Traditionella kinesiska

- Nederländska

- Engelska

- Franska

- Tyska

- Italienska

- Japanska

- Koreanska

- Portugisiska

- Portugisiska (Brasilien)

- Spanska

## <a name="install-the-junk-email-reporting-add-in"></a>Installera tillägget Skräppostrapportering

Du kan installera tillägget Skräppostrapportering:

- Genom att köra Windows Installer-paketet på samma sätt som alla andra MSI-filer. När du installerar tillägget öppnas ett GUI-gränssnitt och uppmanar dig via installationsskärmarna. Mer information finns i [Installera tillägget Skräppostrapportering med hjälp av installationsguiden](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).

ELLER

- Genom att köra en tyst installation som undertrycker installationsanvändargränssnittet. I stället anger du kommandoradsalternativ som kör ett installationsskript. När du installerar tillägget finns ytterligare konfigurationsalternativ som inte är tillgängliga via GRÄNSSNITTET för gränssnittet för gränssnittet för gränssnittet för gränssnittet för gränssnittet för gränssnittet. Mer information finns i [Installera tillägget Skräppostrapportering med tyst läge](#install-the-junk-email-reporting-add-in-using-silent-mode).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Se **systemkraven** för tillägget Skräppostrapportering på [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275).

> [!NOTE]
> Du måste ha administratörsbehörighet på den dator där du installerar tillägget.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installera tillägget Skräppostrapportering med guiden Konfigurera installationsprogrammet

1. Stäng Outlook på datorn.

2. I avsnittet **Information** på [Microsoft Junk E-post Reporting Add-In för Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)hämtar du lämplig MSI-fil för din version av Office.

3. Dubbelklicka på MSI-filen.

4. Klicka på **Nästa**på sidan Lägg till tillägg **för välkommen till Microsoft skräppostrapportering.**

5. Granska licensavtalet och klicka sedan på **Jag godkänner villkoren i licensavtalet** om du godkänner installationsvillkoren (krävs för att fortsätta installationen). Klicka på **Nästa** för att fortsätta.

6. När guiden är klar klickar du på **Slutför**.

7. Starta Outlook.

8. Leta efter knappen **Skräppost** i menyfliksområdet i Outlook. Du kan nu rapportera skräppost meddelanden till Microsoft genom att välja skräppost meddelanden i inkorgen och klicka på **knappen Rapportera skräppost.**

9. Välj nedpilen **bredvid Skräppost** för fler alternativ, till exempel **Rapportera som nätfiske** om du vill rapportera e-postmeddelanden om nätfiskebedrägerier till Microsoft. I skräppostmappen kan du också välja, **Rapportera inte skräppost** om ett e-postmeddelande har identifierats felaktigt som skräppost.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installera tillägget Skräppostrapportering med tyst läge

1. Stäng Outlook på datorn.

2. Öppna en kommandotolk.

3. Om du vill utföra en rak installation av tillägget, utan några valfria parametrar, anger du följande:

   - Datorer som kör x86 Outlook:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`

   - Datorer som kör x64 Outlook:`msiexec /qn /i JunkReportingAdd-in.x64-en.msi`

    Du kan också ange parametrarna MaxMessageSelection och BccEmailAddress som tillval:

   - MaxMessageSelection Tillåter administratörer att definiera det maximala antalet meddelanden som kan väljas av användare för inlämning med ett enda klick. Intervallet är 1 till 50 meddelanden och standardvärdet är 10 meddelanden.

     Exempel: Om du vill ange det maximala antalet meddelanden som kan väljas av användare för inlämning i ett enda klick till 16 använder du följande alternativ som en del av installationskommandot:`MaxMessageSelection=16`

   - BccEmailAddress Gör det möjligt för administratörer att konfigurera en postlåda för att ta emot en kopia av alla sina användarinlämningar genom att ange en Hemlig kopia-e-postadress. När postlådan har konfigurerats skickas en kopia av alla inskickade e-postmeddelanden till BccEmailAddress. Annars är standardinställningen ingen Hemlig kopia-e-postadress.

     Exempel: Om du vill använda junkReports@contoso.com som hemlig kopia-e-postadress för alla inlämningar använder du följande kommando:`BccEmailAddress="junkReports@contoso.com"`

     > [!NOTE]
     > Du kan ange flera EBCC-e-postadresser genom att ange dem med en semikolonavgränsare. Exempel:`BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`

     Om du vill lägga till båda dessa valfria parametrar baserat på tidigare exempel kör du följande kommando på en dator som kör x86 Outlook:

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. När installationen är klar startar du Outlook.

5. Leta efter knappen **Skräppost** i menyfliksområdet i Outlook. Du kan nu rapportera skräppost meddelanden till Microsoft genom att välja skräppost meddelanden i inkorgen och klicka på **knappen Rapportera skräppost.**

6. Välj nedpilen **bredvid Skräppost** för fler alternativ, till exempel **Rapportera som nätfiske** om du vill rapportera e-postmeddelanden om nätfiskebedrägerier till Microsoft. I skräppostmappen kan du också välja, **Rapportera inte skräppost** om ett e-postmeddelande har identifierats felaktigt som skräppost.

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Avinstallera tillägget Skräppostrapportering

Använd något av alternativen i detta för att avinstallera tillägget skräppostrapportering:

- Ta bort tillägget med Windows Kontrollpanelen.

- Kör Installationspaketet för Windows och välj alternativet Avinstallera.

- Kör en tyst installation med alternativet Avinstallation.

> [!NOTE]
> Du måste ha administratörsbehörighet på den dator där du avinstallerar tillägget.

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Avinstallera tillägget skräppostrapportering från Kontrollpanelen

1. Stäng Outlook på datorn.

2. Välj **Kontrollpanelen**på Start-menyn på datorn.

3. Välj **program och funktioner**.

4. Välj **Microsoft Skräppostrapporteringstillägg för Microsoft Office Outlook**.

5. Välj **Avinstallera**.

6. Starta Outlook igen för att bekräfta att tillägget inte längre visas i menyfliksområdet i Outlook.

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Avinstallera tillägget skräppostrapportering genom att köra Windows Installer-paketet

1. Stäng Outlook på datorn.

   > [!NOTE]
   > Om Outlook körs under avinstallationsprocessen måste det startas om för att tillägget ska kunna avinstalleras helt.

2. Kör filen MSI igen som du tidigare körde för att installera tillägget.

   (I avsnittet **Information** på [Microsoft Skräppostrapporteringstillägg för Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)laddar du ned lämplig MSI-fil för din version av Office och dubbelklickar sedan på MSI-filen.)

3. Följ anvisningarna för att avinstallera tillägget.

4. Starta Outlook igen för att bekräfta att tillägget inte längre visas i menyfliksområdet i Outlook.

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Avinstallera tillägget Skräppostrapportering i tyst läge

1. Stäng Outlook på datorn.

   > [!NOTE]
   > Om Outlook körs under avinstallationsprocessen måste det startas om för att tillägget ska kunna avinstalleras helt.

2. Öppna en kommandotolk.

3. Ange följande kommandoradsparameter:

   Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

   Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

4. Starta Outlook igen för att bekräfta att tillägget inte längre visas i menyfliksområdet i Outlook.

## <a name="for-more-information"></a>Mer information

[Rapportera skräppost meddelanden till Microsoft](report-junk-email-messages-to-microsoft.md)

[Felsökning och supportinformation](troubleshooting-and-support-information.md)
