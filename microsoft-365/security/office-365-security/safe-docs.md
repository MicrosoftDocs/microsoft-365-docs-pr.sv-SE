---
title: Säkra dokument i Microsoft Defender för Office 365
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
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845486"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Säkra dokument i Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Säkra dokument är en funktion i Microsoft 365 E5-eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att söka igenom dokument och filer som öppnas i [skyddad vy](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Säkra dokument är endast tillgängligt för användare med *microsoft 365 E5* -eller *Microsoft 365 E5-säkerhets* licenser. Dessa licenser är inte inkluderade i Microsoft Defender för Office 365-abonnemang.

- Säkra dokument stöds i Microsoft 365-appar för företag (tidigare Office 365 ProPlus) version 2004 eller senare.

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>. Om du vill gå direkt till sidan **betrodda säkerhets** meddelanden via ATP öppnar du <https://protection.office.com/safeattachmentv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet. För att aktivera och konfigurera säkra dokument måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** . Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

### <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

För att skydda dig skickar säkra dokument filer till [Microsoft Defender för slut punkts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) moln för analys. Information om hur Microsoft Defender för slut punkter hanterar dina data finns här: [Microsoft Defender för slut punkts data lagring och integritet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Filer som skickas av säkra dokument behålls inte i Defender utöver den tid som krävs för analys (vanligt vis mindre än 24 timmar).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använda säkerhets & Compliance Center för att konfigurera betrodda dokument

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** , \> **mottagna** och sedan klicka på **globala inställningar**.

2. I de **globala inställningarna** som visas konfigurerar du följande inställningar:

   - **Aktivera säkra dokument för Office-klienter** : flytta växlings knappen till höger för att aktivera funktionen: ![ slå på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Tillåt att personer klickar via skyddad vy även om säkra dokument identifierar filen som skadlig** : Vi rekommenderar att du låter det här alternativet vara avstängt (Stäng av växlings knappen till vänster: ![ Växla av ](../../media/scc-toggle-off.png) ).

   Klicka på **Spara** när du är klar.

   ![Inställningar för säkra dokument när du har valt globala inställningar på sidan betrodda bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell för att konfigurera betrodda dokument

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

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** för inkommande \> **bifogade filer** , klickar på **globala inställningar** och verifierar alternativet **Aktivera säkra dokument för Office-klienter** och **tillåter att personer klickar via skyddad vy även om säkra dokument identifierar filen som skadlig** inställningar.

- Kör följande kommando i Exchange Online PowerShell och kontrol lera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Följande filer är tillgängliga för att testa skyddet för skyddat dokument. Dessa dokument liknar EICAR.TXT fil för testning av skadlig program vara och antivirus lösning. Filerna är inte säkra, men de kommer att utlösa skydd mot säkra dokument.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
