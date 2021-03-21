---
title: Konfigurationsanalys för säkerhetsprinciper
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda konfigurationsanalysatorn för att hitta och åtgärda säkerhetsprinciper som finns under de förinställda säkerhetsprinciperna Standardskydd och Strikt skydd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 49c54fa93d5ed95c6c3e0aa948646dd544ea4a5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924450"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Konfigurationsanalys i Säkerhets- och efterlevnadscenter för & tillhandahåller en central plats för att hitta och åtgärda säkerhetsprinciper där inställningarna finns under profilinställningarna Standardskydd och Strikt skydd i [förinställda säkerhetsprinciper.](preset-security-policies.md)

Följande typer av principer analyseras av konfigurationsanalysatorn:

- **Principer för Exchange Online Protection (EOP):** Det här omfattar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:

  - [Principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)
  - [Principer för skydd mot skadlig programvara.](configure-anti-malware-policies.md)
  - [Principer för skydd mot nätfiske i EOP.](set-up-anti-phishing-policies.md#spoof-settings)

- **Principer för Microsoft Defender för Office 365:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för tilläggsprenumerationer för Office 365:

  - Principer mot nätfiske i Microsoft Defender för Office 365, som omfattar:

    - Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade tröskelvärden för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Principer för säkra länkar.](set-up-atp-safe-links-policies.md)

  - [Principer för säkra bifogade filer.](set-up-atp-safe-attachments-policies.md)

**Standard-** och **Strikt-principinställningsvärdena** som används som baslinjer beskrivs i Rekommenderade inställningar för EOP och Microsoft Defender för Office [365-säkerhet.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd för att gå **direkt till sidan Configuration analyzer** <https://protection.office.com/configurationAnalyzer> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill använda konfigurationsanalysatorn och uppdatera säkerhetsprinciper måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** 
  - För skrivskyddade åtkomst till konfigurationsanalys behöver du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >  
  > - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Använda konfigurationsanalysen i Säkerhets- & Säkerhets- och efterlevnadscenter

I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Analysverktyg** för \> **hantering av** \> **hotprinciper.**

![Widget för konfigurationsanalys på sidan \> Hothanteringspolicy](../../media/configuration-analyzer-widget.png)

Konfigurationsanalysen har två huvudflikar:

- **Inställningar och rekommendationer:** Du väljer Standard eller Strikt och jämför inställningarna med dina befintliga säkerhetsprinciper. I resultatet kan du justera värdena i inställningarna så att de hamnar på samma nivå som Standard eller Strikt.

- **Konfigurationsanalys och historik:** I den här vyn kan du spåra principändringar över tid.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Fliken Inställningar och rekommendationer i konfigurationsanalys

Som standard öppnas fliken med jämförelsen av profilen för standardskydd. Du kan växla till jämförelsen av profilen för strikt skydd genom att klicka på **Visa strikt rekommendationer.** Om du vill växla tillbaka väljer du **Visa standardrekommendationer**.

![Vyn Inställningar och rekommendationer i Konfigurationsanalys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Som standard innehåller **namnkolumnen Principgrupp/inställning** en komprimerad vy av de olika typerna av säkerhetsprinciper och antalet inställningar som behöver förbättras (om sådana finns). Här är typerna av principer:

- **Skräppostskydd**
- **Skydd mot nätfiske**
- **Skydd mot skadlig programvara**
- **ATP – säkra bifogade** filer (om prenumerationen omfattar Microsoft Defender för Office 365)
- **ATP – säkra** länkar (om microsoft Defender för Office 365 ingår i prenumerationen)

I standardvyn döljs allt. Bredvid varje princip finns en sammanfattning av jämförelseresultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard- eller striktskyddsprofilerna (som du inte kan ändra). Följande information visas för den skyddsprofil som du jämför med:

- **Grön**: Alla inställningar i alla befintliga principer är minst lika säkra som skyddsprofilen.
- **Gult** antal: Ett litet antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.
- **Röd**: Ett stort antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen. Det kan vara några inställningar i många principer eller många inställningar i en princip.

För bra jämförelser ser du texten: Alla inställningar **följer** \<**Standard** or **Strict**\> **rekommendationer**. I annat fall visas antalet rekommenderade inställningar som ska ändras.

Om du **expanderar grupp-/inställningsnamn** för princip visas alla principer och de associerade inställningarna i varje specifik princip som kräver uppmärksamhet. Du kan också expandera en viss typ av princip (till exempel Skräppostskydd) om du bara vill visa de inställningarna i de policytyper som kräver din uppmärksamhet.

Om jämförelsen inte har några rekommendationer för förbättring (grön) visar expanderande princip ingenting. Om det finns något antal rekommendationer för förbättring (gult eller rött) visas de inställningar som kräver uppmärksamhet och motsvarande information visas i följande kolumner:

- Namnet på den inställning som kräver din uppmärksamhet. I den föregående skärmbilden är till exempel tröskelvärdet för **massutskick** av e-post i en princip mot skräppost.

- **Princip:** Namnet på den princip som påverkas som innehåller inställningen.

- **Tillämpas på:** Antalet användare som de aktuella principerna tillämpas på.

- **Aktuell konfiguration:** Det aktuella värdet för inställningen.

- **Senast ändrad:** Datumet då principen senast ändrades.

- **Rekommendationer:** Värdet på inställningen i profilen standard eller strikt skydd. Om du vill ändra värdet för inställningen i principen så att den matchar det rekommenderade värdet i skyddsprofilen klickar du på **Adopt**. Om ändringen lyckas visas meddelandet: Rekommendationer **har godkänts**. Klicka **på** Uppdatera om du vill se det minskade antalet rekommendationer och borttagningen av den specifika inställnings-/principraden från resultatet.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Konfigurationsanalys och historikfliken i konfigurationsanalys

På den här fliken kan du spåra de ändringar som du har gjort av dina anpassade säkerhetsprinciper. Som standard visas följande information:

- **Senast ändrad**
- **Ändrad av**
- **Inställningsnamn**
- **Princip**
- **Typ**

Om du vill filtrera resultaten klickar du på **Filter**. I  den utfällna listan Filter som visas kan du välja bland följande filter:

- **Starttid** **och Sluttid** (datum)
- **Standardskydd** eller **Strikt skydd**

Om du vill exportera resultaten till en CSV-fil klickar du på **Exportera**.

![Konfigurationsanalys och historikvy i Konfigurationsanalys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)