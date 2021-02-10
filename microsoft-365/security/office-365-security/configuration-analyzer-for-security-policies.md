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
description: Administratörer kan lära sig att använda konfigurationsanalys för att hitta och åtgärda säkerhetsprinciper som finns under de förinställda säkerhetsprinciperna Standardskydd och Strikt skydd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a78452cb3a7e4cb65c72d98b9322f217309a6d6f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165913"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurationsanalys för skyddsprinciper i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Konfigurationsanalys i säkerhets- och efterlevnadscentret för & tillhandahåller en central plats för att hitta och åtgärda säkerhetsprinciper där inställningarna finns under profilinställningarna Standardskydd och Strikt skydd i [förinställda säkerhetsprinciper.](preset-security-policies.md)

Följande typer av principer analyseras av konfigurationsanalysatorn:

- **Principer för Exchange Online Protection (EOP):** Detta omfattar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:

  - [Principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)
  - [Principer för skydd mot skadlig programvara.](configure-anti-malware-policies.md)
  - [Principer för skydd mot nätfiske i EOP.](set-up-anti-phishing-policies.md#spoof-settings)

- **Principer för Microsoft Defender för Office 365:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för Office 365-tilläggsprenumerationer:

  - Principer mot nätfiske i Microsoft Defender för Office 365, som omfattar:

    - Samma inställningar [för förfalskning som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade tröskelvärden för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Principer för säkra länkar.](set-up-atp-safe-links-policies.md)

  - [Principer för säkra bifogade filer.](set-up-atp-safe-attachments-policies.md)

Principinställningsvärdena **Standard** och Strikt som används som baslinjer beskrivs i Rekommenderade inställningar för EOP och Microsoft Defender för [Office 365-säkerhet.](recommended-settings-for-eop-and-office365-atp.md) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan Konfigurationsanalys** använder du <https://protection.office.com/configurationAnalyzer> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill använda **konfigurationsanalysatorn** och uppdatera säkerhetsprinciper måste du vara medlem i rollgrupperna Organisationshantering **eller** **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till konfigurationsanalys behöver du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >  
  > - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  > 
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Använda konfigurationsanalysatorn i Säkerhets- & Efterlevnadscenter

Gå till Konfigurationsanalys för & för **hothanteringspolicy** i \>  \> **Säkerhets- och efterlevnadscenter.**

![Widget för konfigurationsanalys på sidan Policy för \> hothantering](../../media/configuration-analyzer-widget.png)

Konfigurationsanalysatorn har två huvudflikar:

- **Inställningar och rekommendationer:** Du väljer Standard eller Strikt och jämför dessa inställningar med dina befintliga säkerhetsprinciper. I resultatet kan du justera värdena i inställningarna så att de hamnar på samma nivå som Standard eller Strikt.

- **Konfigurationsanalys och historik:** I den här vyn kan du spåra principändringar över tid.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Fliken Inställningar och rekommendationer i konfigurationsanalys

Som standard öppnas fliken med jämförelsen med profilen för standardskydd. Du kan växla till jämförelsen av profilen för strikt skydd genom att klicka på **Visa strikt rekommendationer.** Om du vill växla tillbaka väljer du **Visa standardrekommendationer.**

![Vyn Inställningar och rekommendationer i Konfigurationsanalys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Som standard innehåller **namnkolumnen Principgrupp/inställning** en komprimerad vy av de olika typerna av säkerhetsprinciper och antalet inställningar som behöver förbättras (om det finns några). Olika typer av principer är:

- **Skräppostskydd**
- **Skydd mot nätfiske**
- **Skydd mot skadlig programvara**
- **ATP – säkra bifogade** filer (om prenumerationen omfattar Microsoft Defender för Office 365)
- **ATP – säkra länkar** (om prenumerationen omfattar Microsoft Defender för Office 365)

I standardvyn döljs allt. Bredvid varje princip finns en sammanfattning av jämförelseresultaten från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard- eller striktskyddsprofilerna (som du inte kan ändra). Följande information visas för den skyddsprofil som du jämför med:

- **Grön:** Alla inställningar i alla befintliga principer är minst lika säkra som skyddsprofilen.
- **Gult:** Ett litet antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen.
- **Röd**: Ett stort antal inställningar i de befintliga principerna är inte lika säkra som skyddsprofilen. Det kan vara några inställningar i många principer eller många inställningar i en princip.

För bra jämförelser ser du texten: Alla inställningar **följer** \<**Standard** or **Strict**\> **rekommendationer.** Annars visas antalet rekommenderade inställningar som ska ändras.

Om du **expanderar principens grupp-/inställningsnamn** visas alla principer och tillhörande inställningar i varje specifik princip som kräver uppmärksamhet. Du kan också expandera en viss typ av princip (till exempel **Skräppostskydd)** om du bara vill visa inställningarna i de typer av principer som kräver din uppmärksamhet.

Om jämförelsen inte har några rekommendationer för förbättring (grön) visar expandering av principen ingenting. Om det finns något antal rekommendationer för förbättring (gult eller rött) visas de inställningar som kräver uppmärksamhet och motsvarande information visas i följande kolumner:

- Namnet på den inställning som kräver din uppmärksamhet. I den föregående skärmbilden är till exempel tröskelvärdet för massutskick **av** e-post i en princip mot skräppost.

- **Princip:** Namnet på den princip som påverkas som innehåller inställningen.

- **Tillämpas på:** Antalet användare som de påverkade principerna tillämpas på.

- **Aktuell konfiguration:** Det aktuella värdet för inställningen.

- **Senast ändrad:** Det datum då principen senast ändrades.

- **Rekommendationer:** Värdet för inställningen i profilen för standard- eller strikt skydd. Om du vill ändra värdet för inställningen i principen så att den matchar det rekommenderade värdet i skyddsprofilen klickar du på **Införa.** Om ändringen lyckas visas meddelandet: Rekommendationerna **har godkänts.** Klicka **på** Uppdatera om du vill se det minskade antalet rekommendationer och borttagningen av den specifika inställningen/principraden från resultatet.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Konfigurationsanalys och historikflik i konfigurationsanalys

Med den här fliken kan du spåra de ändringar som du har gjort i dina anpassade säkerhetsprinciper. Som standard visas följande information:

- **Senast ändrad**
- **Ändrad av**
- **Inställningsnamn**
- **Princip**
- **Typ**

Om du vill filtrera resultaten klickar du på **Filter**. I  den utfällna listan Filter som visas kan du välja bland följande filter:

- **Starttid** **och sluttid** (datum)
- **Standardskydd** eller **Strikt skydd**

Om du vill exportera resultaten till en CSV-fil klickar du på **Exportera.**

![Konfigurationsanalys och historikvy i Konfigurationsanalys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
