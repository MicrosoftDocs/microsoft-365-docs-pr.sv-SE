---
title: Rapportera skräppost och nätfiske i Outlook på webben
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om de inbyggda alternativen för skräppost, inte skräppost och nätfiske i Outlook på webben (Outlook Web App) i Exchange Online, och hur de inaktiverar rapporteringsalternativen för användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289227"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Rapportera skräppost och nätfiske i Outlook på webben i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online kan du använda de inbyggda rapporteringsalternativen i Outlook på webben (tidigare Outlook Web App) för att skicka falska positiva identifieringar (bra e-post som markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

- Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben. Mer information finns i avsnittet [Inaktivera eller aktivera skräppostrapportering i Outlook på webben senare](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) i den här artikeln.

- Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Rapportera skräppost och nätfiskemeddelanden i Outlook på webben

1. För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiske:

   - Markera meddelandet, klicka **på Skräppost** i verktygsfältet och välj sedan **Skräppost** eller **nätfiske.**

     ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/owa-report-junk.png)

   - Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som skräppost.**

2. Klicka på Rapport i dialogrutan **som visas.** Om du ändrar dig klickar du **på Rapportera inte.**

   |Skräppost|Fiske|
   |:---:|:---:|
   |![Dialogrutan Rapportera som skräppost](../../media/owa-report-as-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. De valda meddelandena skickas till Microsoft för analys. Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Rapportera icke-skräppost och nätfiskemeddelanden från mappen Skräppost i Outlook på webben

1. Använd någon av följande metoder i mappen Skräppost för att rapportera skräppost med falska positiva resultat eller nätfiskemeddelanden:

   - Markera meddelandet, klicka **på Inte skräppost** i verktygsfältet och välj sedan Inte **skräppost** eller **nätfiske.**

     ![Rapportera inte skräppost eller inte nätfiskemeddelande från menyfliksområdet](../../media/owa-report-not-junk.png)

   - Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som inte skräppost.**

2. Läs informationen i dialogrutan som visas och klicka på **Rapport.** Om du ändrar dig klickar du **på Rapportera inte.**

   |Inte skräppost|Fiske|
   |:---:|:---:|
   |![Dialogrutan Rapportera som inte skräppost](../../media/owa-report-as-not-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. De valda meddelandena skickas till Microsoft för analys. Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Inaktivera eller aktivera skräppostrapportering i Outlook på webben

Standardinställningen är att användare kan rapportera skräppost med falska positiva meddelanden, falska negativa meddelanden och nätfiskemeddelanden till Microsoft för analys i Outlook på webben. Administratörer kan konfigurera principer för postlådor i Outlook på webben i Exchange Online PowerShell för att hindra användare från att rapportera skräppost som falska positiva identifieringar och skräppost till Microsoft. Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du **rollerna Mottagarprinciper** och E-postmottagare, som är tilldelade **rollgrupperna** Organisationshantering **och Mottagarhantering** som standard.  Mer information om rollgrupper i Exchange Online finns i Behörigheter [i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) och Ändra [rollgrupper i Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)

- Varje organisation har en standardprincip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer. Anpassade principer tillämpas på begränsade användare före standardprincipen. Mer information om postlådeprinciper för Outlook på webben finns i [postlådeprinciperna för Outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)på webben i Exchange Online.

- Om du inaktiverar skräppostrapportering tas inte möjligheten att markera ett meddelande som skräppost eller inte som skräppost i Outlook på webben. Om du markerar ett meddelande i mappen Skräppost och klickar **på Inte** skräppost flyttas meddelandet tillbaka \>  till Inkorgen. Om du markerar ett meddelande  i en annan e-postmapp och klickar på Skräppost \>  flyttas meddelandet fortfarande till mappen Skräppost. Det som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben

1. Om du vill hitta dina befintliga postlådeprinciper för Outlook på webben och status för skräppostrapportering kör du följande kommando:

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

   I det här exemplet möjliggörs rapportering av skräppost i den anpassade principen contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) [och Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben genom att göra något av följande:

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdet **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öppna en användares postlåda i Outlook på webben, markera ett  meddelande i Inkorgen, klicka på Skräppost och kontrollera att meddelandet inte visas eller \>  inte.<sup>\*</sup>

- Öppna en användares postlåda i Outlook på webben, markera ett meddelande  i mappen Skräppost, klicka på Skräppost och kontrollera att meddelandet visas eller \>  inte.<sup>\*</sup>

<sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet medan du fortfarande rapporterar meddelandet. Så här kontrollerar du den här inställningen i Outlook på webben:

1. Klicka **på Inställningar** i Outlook på ![ webbinställningsikonen ](../../media/owa-settings-icon.png) \> **Visa alla Outlook-inställningar** för \> **skräppost.**
2. Kontrollera värdet **i** avsnittet Rapportering: Fråga **innan du skickar en rapport.**

   ![Inställningar för rapportering av skräppost i Outlook på webben](../../media/owa-junk-email-reporting-options.png)
