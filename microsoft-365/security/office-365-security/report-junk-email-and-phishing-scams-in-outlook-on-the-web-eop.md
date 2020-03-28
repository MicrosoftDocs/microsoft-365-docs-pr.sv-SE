---
title: 'Rapportera skräppost och nätfiskebedrägerier i Outlook på webben '
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365-användare med Exchange Online-postlådor kan använda Outlook på webben (Outlook Web App) för att skicka skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft för analys.
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033710"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a>Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Office 365

Om du är Office 365-kund med Exchange Online-postlådor kan du använda de inbyggda rapporteringsalternativen i Outlook på webben (tidigare kallat Outlook Web App) för att skicka in falska positiva identifieringar (bra e-post markerat som skräppost), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du är administratör i en Office 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Office 365 Security & Compliance Center. Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).

- Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben. Mer information finns i [avsnittet Inaktivera eller aktivera skräppostrapportering i Outlook på webben](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) senare i det här avsnittet.

- Mer information om hur du anmäler meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft i Office 365](report-junk-email-messages-to-microsoft.md).

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Rapportera skräppost och nätfiskemeddelanden i Outlook på webben

1. För meddelanden i Inkorgen eller någon annan e-postmapp utom skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiskemeddelanden:

   - Markera meddelandet, klicka på **Skräppost** i verktygsfältet och välj sedan **Skräppost** eller **Nätfiske**.

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/owa-report-junk.png)

   - Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som skräppost**.

2. Klicka på **Rapportera**i dialogrutan som visas. Om du ändrar dig klickar du på **Rapportera inte**.

   ![Rapport som skräppostdialogruta](../../media/owa-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys. Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Rapportera meddelanden som inte är skräppost och nätfiske från mappen Skräppost i Outlook på webben

1. I mappen Skräppost använder du någon av följande metoder för att rapportera falska positiva skräppost eller nätfiskemeddelanden:

   - Markera meddelandet, klicka på **Inte skräppost** i verktygsfältet och välj sedan **Inte skräppost** eller **nätfiske**.

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/owa-report-not-junk.png)

   - Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som inte skräppost**.

2. Läs informationen i dialogrutan som visas och klicka på **Rapportera**. Om du ändrar dig klickar du på **Rapportera inte**.

   ![Rapportera som inte skräppostdialogruta](../../media/owa-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)

3. De valda meddelandena skickas till Microsoft för analys. Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Inaktivera eller aktivera skräppostrapportering i Outlook på webben

Som standard kan användare rapportera falska positiva skräpposter, falska negativ och nätfiskemeddelanden till Microsoft för analys i Outlook på webben. Administratörer kan använda Outlook på webbpostlådeprinciperna i Exchange Online för att inaktivera eller aktivera den här möjligheten, men bara i Exchange Online PowerShell.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du behöver som standard rollerna **Mottagare eller** **E-postmottagare** i Exchange Online, som tilldelas rollgrupperna **Organisationshantering** och **Mottagarhantering** som standard. Mer information om rollgrupper i Exchange Online finns [i Ändra rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).

- Varje organisation har en standardprincip med namnet OwaMailboxPolicy-Default, men du kan skapa anpassade principer. Anpassade principer tillämpas på begränsade användare före standardprincipen. Mer information om Outlook i principerna för webbpostlåda finns i Outlook i principerna för [webbpostlådan i Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

1. Om du vill hitta dina befintliga Outlook på webbpostlådeprinciperna och statusen för skräppostrapportering kör du följande kommando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Om du vill inaktivera eller aktivera skräppostrapportering i Outlook på webben använder du följande syntax:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   I det här exemplet inaktiveras skräppostrapportering i standardprincipen.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   Det här exemplet aktiverade skräppostrapportering i den anpassade principen Contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Detaljerad syntax- och parameterinformation finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) och [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben använder du något av följande:

- I Exchange Online PowerShell kör du följande kommando och verifierar egenskapsvärdet **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öppna en berörd användares postlåda i Outlook på webben och kontrollera alternativen för att rapportera skräppost, inte skräppost och nätfiskemeddelanden är tillgängliga eller inte tillgängliga. Observera att användaren fortfarande kan markera meddelanden som skräppost, nätfiske och inte skräppost, men användaren kan inte rapportera dem till Microsoft.
