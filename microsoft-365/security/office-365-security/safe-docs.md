---
title: Säkra dokument i Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Lär dig mer om Safe-dokument i Microsoft 365 E5 eller Microsoft 365 E5 Security.
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949460"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Säkra dokument i Microsoft 365 E5

Säkra dokument är en funktion i Microsoft 365 E5-eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att söka igenom dokument och filer som öppnas i [skyddad vy](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Säkra dokument är nu i allmänhet tillgängliga för användare med Office version 2004 (12730. x) eller senare. Den här funktionen är inaktive rad som standard och måste aktive ras av säkerhets administratören.

- Den här funktionen är endast tillgänglig för användare med *microsoft 365 E5* -eller *Microsoft 365 E5-säkerhets* licens (ingår inte i Office 365 ATP-abonnemang).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om 

- Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet. För att aktivera och konfigurera säkra dokument måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** . Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

För att skydda dig skickar säkra dokument filer till [Microsoft Defender Avancerat skydd för hotet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.

- Information om hur Microsoft Defender Avancerat skydd hanterar dina data finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).
- Utöver rikt linjerna ovan behålls inte filer som skickats av säkra dokument i Defender efter den tid som krävs för analys, vilket normalt är mindre än 24 timmar.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använda säkerhets & Compliance Center för att konfigurera betrodda dokument

1. Öppna säkerhets & Compliance Center på <https://protection.office.com> .

2. Gå till policyn för **Threat Management** - \> **Policy** \> **säkerhets**meddelanden.

3. Konfigurera någon av följande inställningar i avsnittet **Hjälp personer att skydda utanför skyddad vy i Office-program** .

   - **Aktivera säkra dokument för Office-klienter**

   - **Tillåt att personer klickar via skyddad vy även om säkra dokument identifierar filen som skadlig**: Vi rekommenderar att du inte aktiverar det här alternativet.

4. Klicka på **Spara** när du är klar.

![Sida med säkra filer för ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera betrodda dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Med parametern _EnableSafeDocs_ aktive ras eller inaktive ras säkra dokument för hela organisationen.

- Med _AllowSafeDocsOpen_ -parametern kan du hindra användare från att lämna skyddad vy (det innebär att dokumentet öppnas) om dokumentet har identifierats som skadligt.

Det här exemplet aktiverar säkra dokument för hela organisationen och hindrar användarna från att öppna dokument som har identifierats som skadliga från skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det här fungerade?

Gör något av följande om du vill kontrol lera att du har aktiverat och konfigurerat säkra dokument:

- I säkerhets & Compliance Center går du till **Threat Management** \> **policys** för inkommande \> **bifogade filer**och verifierar att de val du **gör för att skydda en fil som öppnas utanför skyddad vy i Office-program** .

- Kör följande kommando i Exchange Online PowerShell och kontrol lera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
