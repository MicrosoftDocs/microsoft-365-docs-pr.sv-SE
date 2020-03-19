---
title: Felsökning och supportinformation
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
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: I det här avsnittet beskrivs felsökningssteg för slutanvändare och administratörer och information om hur du kontaktar teknisk support för hjälp.
ms.openlocfilehash: efb71aab852b76b2b898419444bfea4144728514
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811135"
---
# <a name="troubleshooting-and-support-information"></a>Felsökning och supportinformation

I det här avsnittet beskrivs felsökningssteg för slutanvändare och administratörer och information om hur du kontaktar teknisk support för hjälp.

## <a name="troubleshooting-for-users"></a>Felsökning för användare

Ibland kan det uppstå problem med Microsoft Outlook när du har lagt till tillägget Skräppostrapportering. Följande är problem som du kan stöta på, tillsammans med tips för att lösa dessa problem.

- Ingenting händer när du klickar på **Rapportera skräppost**

- Outlook slutar svara när du har valt ett e-postmeddelande

- Rapporterad skräppost kan inte levereras på grund av ett "obeställbart" svar

Lös problemet genom att göra följande:

1. Stäng och starta om Outlook.

2. Kontrollera att du kan skapa och skicka ett testmeddelande. För att göra detta kan du skicka ett testmeddelande till ett annat e-postkonto som du ansvarar för och sedan verifiera att e-postmeddelandet tas emot.

Om problemet kvarstår kontaktar du administratören.

> [!TIP]
> Du kan också skicka in skräppost meddelanden direkt till Microsoft med hjälp av [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e-postadress och falska positiva meddelanden med hjälp av [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) e-postadress. Mer information finns i [Skicka meddelanden om skräppost, icke-skräppost och nätfisketill Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Felsökning för administratörer

Som administratör kan det uppstå problem med användare som använder tillägget Skräppostrapportering för Outlook. Nedan följer några tips för att lösa problem som du kan stöta på.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Problem: Ett felmeddelande där användarna uppmanas att kontakta sin systemadministratör visas kontinuerligt

1. Ange följande registernyckelvärde till "Verbose":

   - **32 bitars Outlook installerat på ett 32-bitars operativsystem:**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 bitars Outlook installerat på ett 64-bitars operativsystem:**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 bitars Outlook (alltid installerat på ett 64-bitars operativsystem):**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Starta om Outlook och be användarna att rapportera tillbaka när de ser felmeddelandet.

3. Samla in logginformationen som finns på följande plats:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontakta Teknisk support för onlineskydd och förse dem med logginformationen.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Problem: Användare väljer att inte få en bekräftelse när de skickar ett e-postmeddelande som skräppost och nu vill de ha tillbaka alternativet

1. Ange följande registernyckelvärde till "Sant": `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`.

2. Starta om Outlook.

## <a name="support-information"></a>Supportinformation

Om du behöver hjälp med installationen, konfigurationen eller avinstallationen av tillägget kontaktar du teknisk support med hjälp av länken för den nya tjänstbegäran på supportsidan i administrationscentret för Microsoft 365. Mer information om alternativ, inklusive att skicka in en serviceförfrågan via telefon- och självsupportalternativen, se [Hjälp och support för EOP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Mer information

[Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

[Rapportera skräppost meddelanden till Microsoft](report-junk-email-messages-to-microsoft.md)
