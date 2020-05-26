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
description: Lär dig mer om säkra dokument i Office 365 ATP.
ms.openlocfilehash: f792b1acbdacfd29db5bbbf377f41396c35e3f17
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350957"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Säkra dokument i Office 365 ATP

Säkra dokument är en funktion i Office 365 Advanced Threat Protection (Office 365 ATP) som använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att skanna dokument och filer som öppnas i [skyddad vy](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Den här funktionen är endast tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Security-licensen.

- Säkra dokument är för närvarande tillgängliga för offentlig förhandsversion, som är tillgängliga för användare som ingår i [Office Insider-programmet](https://insider.office.com/en-us/join) på månadskanalen (Targeted)' med Office Version 2002 (12527.20092) eller mer. Den här funktionen är inaktiverad som standard och måste aktiveras av säkerhetsadministratören.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet. Om du vill aktivera och konfigurera säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

För att skydda dig skickar säkra dokument filer till Microsoft [Defender Advanced Threat Protection-molnet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.

- Information om hur Microsoft Defender Advanced Thread Protection hanterar dina data finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Utöver riktlinjerna ovan, filer som skickas av säkra dokument inte behållas i Defender utöver den tid som behövs för analys, vilket vanligtvis är mindre än 24 timmar

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använda Security & Compliance Center för att konfigurera säkra dokument

1. Öppna Säkerhets- & Compliance Center på <https://protection.office.com> .

2. Gå **Threat management** till \> **Policy** \> **ATP-säkra bilagor för**hothanteringsprincip .

3. Konfigurera någon av följande inställningar när du litar på en fil för att öppna utanför skyddad vy i Office-program i hjälpen för personer som är säkra när de **litar på en fil för att öppna utanför skyddad vy i Office-program:**

   - **Aktivera säkra dokument för Office-klienter (Filer skickas också till Microsoft Cloud för djupgående analyser)**

   - **Tillåt personer att klicka sig igenom Skyddad vy även om säkra dokument identifierar filen som skadlig:** Vi rekommenderar att du inte aktiverar det här alternativet.

4. Klicka på **Spara** när du är klar.

![ATP Säkra bilagor sida](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera säkra dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- Parametern _EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.

- Parametern _AllowSafeDocsOpen_ gör det möjligt eller hindrar användare från att lämna skyddad vy (det vill än att öppna dokumentet) om dokumentet har identifierats som skadligt.

Det här exemplet aktiverar säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad syntax- och parameterinformation finns i [Ange-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det fungerade?

Så här kontrollerar du att du har aktiverat och konfigurerat säkra dokument:

- I Security & Compliance Center **Threat management** går du till \> **Policy** \> **ATP-betrodda bilagor**för hothanteringsprincip och verifierar valen i **hjälppersonerna att vara säkra när de litar på att en fil öppnas utanför skyddad vy i Office-program.**

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
