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
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788313"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Rapportera skräppost och nätfiske i Outlook på webben i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller lokala postlådor med [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

> [!IMPORTANT]
> Vi rekommenderar tilläggen Rapportmeddelande eller Rapportera nätfiske för användarinskick. Mer information finns i [Aktivera rapportmeddelandet eller tilläggen för rapportfiske.](./enable-the-report-message-add-in.md) Vi rekommenderar inte den inbyggda rapporteringsupplevelsen i Outlook eftersom den inte kan använda principen för [användarinskicking.](./user-submission.md)

- Om du är administratör i en organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

- Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben. Mer information finns i [avsnittet Inaktivera eller aktivera skräppostrapportering i Outlook på webben längre](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) fram i den här artikeln.

- Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Inaktivera eller aktivera skräppostrapportering i Outlook på webben

Som standard kan användare rapportera falska positiva meddelanden som skräppost, falska negativa tal och nätfiskemeddelanden till Microsoft för analys Outlook på webben. Administratörer kan konfigurera Outlook på principer för webbpostlådor i Exchange Online PowerShell för att hindra användare från att rapportera skräppost som falska positiva identifieringar och falskt negativa identifieringar av skräppost till Microsoft. Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du **rollerna Mottagarprinciper** eller E-postmottagare, som tilldelas rollgrupperna **Organisationshantering** och **Mottagarhantering** som standard.  Mer information om rollgrupper i Exchange Online finns i [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo) och Ändra [rollgrupper i Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- Varje organisation har en standardprincip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer. Anpassade principer tillämpas på begränsade användare före standardprincipen. Mer information om Outlook webbpostlådeprinciper finns i Outlook på principer för [webbpostlådor i Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

- Om du inaktiverar skräppostrapporteringen inaktiveras inte möjligheten att markera ett meddelande som skräppost eller inte skräppost i Outlook på webben. Om du markerar ett meddelande i mappen Skräppost och **klickar på Inte** skräppost Flyttar du fortfarande tillbaka meddelandet till \>  Inkorgen. Om du markerar ett meddelande  i en annan e-postmapp och klickar på Skräppost \>  flyttas det fortfarande till mappen Skräppost. Vad som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben

1. Om du vill hitta Outlook information om postlådeprinciperna för webben och status för skräppostrapportering kör du följande kommando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Inaktivera eller aktivera skräppostrapportering i Outlook på webben med följande syntax:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   Det här exemplet inaktiverar skräppostrapportering i standardprincipen.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   I det här exemplet möjliggörs rapportering av skräppost i den anpassade principen contoso-hanterare.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) och [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben genom att göra något av följande:

- I Exchange Online PowerShell kör du följande kommando och verifierar värdet för egenskapen **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öppna en användares postlåda i Outlook på webben, markera ett meddelande  i Inkorgen, klicka på Skräppost och kontrollera att meddelandet inte visas eller \>  inte.<sup>\*</sup>

- Öppna en användares postlåda i Outlook på webben, markera ett meddelande i  mappen Skräppost, klicka på Skräppost och kontrollera att meddelandet visas eller \>  inte.<sup>\*</sup>

<sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet samtidigt som de rapporterar meddelandet. Så här kontrollerar du den Outlook på webben:

1. Klicka **Inställningar** ![ Outlook på ikonen för webbinställningar ](../../media/owa-settings-icon.png) \> **Visa Outlook alla inställningar** \> **Skräppost.**
2. Kontrollera värdet **i** avsnittet Rapportering: Fråga **innan du skickar en rapport**.

   ![Outlook för skräppostrapportering på webben](../../media/owa-junk-email-reporting-options.png)
