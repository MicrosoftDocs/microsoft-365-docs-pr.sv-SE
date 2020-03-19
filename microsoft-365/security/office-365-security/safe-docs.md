---
title: Säkra dokument i Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs mer om säkra dokument i Office 365 ATP.
ms.openlocfilehash: 3980746eb2f48e77c22f5139827bead5640dad61
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42809707"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Säkra dokument i Office 365 Avancerat hotskydd

Säkra dokument är en funktion i Office 365 Advanced Threat Protection (ATP) som använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att skanna dokument och filer som öppnas i skyddad [vy](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Den här funktionen är endast tillgänglig för användare med licensen Microsoft 365 E5 eller Microsoft 365 E5 Security.

- Säkra dokument är för närvarande tillgängligt för offentlig förhandsversion, tillgänglig för användare som ingår i [Office Insider Program](https://insider.office.com/en-us/join) på "Monthly Channel (Targeted)" med Office Version 2002 (12527.20092) eller högre. Den här funktionen är avstängd som standard och måste aktiveras av säkerhetsadministratören.

- Endast usa-region som för närvarande stöds för kompatibel filbearbetning (Alla filer kommer att resa till den amerikanska regionen för skanning). Stöd till storbritannien/EU-regionen planeras i en framtida uppdatering.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet. Om du vill aktivera och konfigurera säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **säkerhetsadministratör.** Mer information om rollgrupper i Security & Compliance Center finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Använda Office 365 Security & Compliance Center för att konfigurera säkra dokument

1. Öppna Office 365 Security & <https://protection.office.com>Compliance Center på .

2. Gå till policy **för hothantering** \> **Policy** \> **ATP-säkra bilagor**.

3. Konfigurera någon av följande inställningar i avsnittet Hjälp personer när de **litar på att en fil ska öppnas utanför skyddad vy i Office-program:**

   - **Aktivera betrodda dokument för Office-klienter (Filer skickas också till Microsoft Cloud för djupa analyser)**

   - **Tillåt personer att klicka sig igenom Skyddad vy även om säkra dokument identifierar filen som skadlig:** Vi rekommenderar att du inte aktiverar det här alternativet.

4. Klicka på **Spara** när du är klar.

![SIDAN ATP-säkra bilagor](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Använd Exchange Online PowerShell eller Exchange Online Protection PowerShell för att konfigurera säkra dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- _Parametern EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.

- _Parametern AllowSafeDocsOpen_ tillåter eller hindrar användare från att lämna Skyddad vy (det vill lägga dokumentet) om dokumentet har identifierats som skadligt.

I det här exemplet aktiveras Säkra dokument för hela organisationen och förhindrar användare från att öppna dokument som har identifierats som skadliga från skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad syntax- och parameterinformation finns [i Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det fungerade?

Så här kontrollerar du att du har aktiverat och konfigurerat säkra dokument:

- I Säkerhets-& Compliance Center gå till **policy för** \> **hothantering** \> **OCH**verifiera valen i **hjälpanvändarna när de litar på en fil för att öppna utanför skyddad vy i Office-program.**

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
