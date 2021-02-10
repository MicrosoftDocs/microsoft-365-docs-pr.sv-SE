---
title: Säkra dokument i Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs mer om säkra dokument i Microsoft 365 E5 eller Microsoft 365 E5 Säkerhet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47bb6c66d51575c91b829e9688a074aaf9a18ab5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166657"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Säkra dokument i Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Säkra dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Slutpunkt för att söka igenom dokument och filer som öppnas i [Skyddad vy.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Säkra dokument är endast tillgängliga för användare med Säkerhetslicenser för *Microsoft 365 E5* eller *Microsoft 365 E5.* Licenserna ingår inte i Microsoft Defender för Office 365-abonnemang.

- Säkra dokument stöds i Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus) version 2004 eller senare.

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com>. Gå direkt till **atp-sidan för säkra bifogade** filer genom att <https://protection.office.com/safeattachmentv2> öppna.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill konfigurera inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Global Reader** **eller** Säkerhetsläsare.

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  > 
  > - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

### <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

Om du vill skydda dig skickas filer till Microsoft [Defender för slutpunktsmoln](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys. Information om hur Microsoft Defender för Endpoint hanterar dina data finns här: Microsoft Defender för [slutpunktens datalagring och sekretess.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Filer som skickas av säkra dokument sparas inte i Defender utöver den tid som krävs för analys (vanligtvis mindre än 24 timmar).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använd Säkerhets- & center för att konfigurera säkra dokument

1. Gå till  ATP & för hanteringspolicy för säkerhet och säkerhet i Säkerhets- och efterlevnadscenter och klicka sedan \>  \> på **Globala inställningar.**

2. I den **globala inställningsfällan** som visas konfigurerar du följande inställningar:

   - **Aktivera Säkra dokument för Office-klienter:** Flytta reglaget till höger för att aktivera funktionen: ![ ](../../media/scc-toggle-on.png) Aktivera.

   - Tillåt att andra klickar i Skyddad vy även om filen identifieras som skadlig i Säkra dokument: Vi rekommenderar att du låter det här alternativet vara inaktiverat (låt **växlingsknappen** vara ![ inaktiverad ](../../media/scc-toggle-off.png) till vänster).

   Klicka på **Spara** när du är klar.

   ![Inställningar för säkra dokument när du har valt Globala inställningar på sidan Säkra bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell för att konfigurera säkra dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Parametern _EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.
- Parametern _AllowSafeDocsOpen_ tillåter eller förhindrar användare från att lämna Skyddad vy (dvs. öppna dokumentet) om dokumentet har identifierats som skadligt.

Det här exemplet aktiverar Säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från Skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad information om syntax och parametrar finns [i Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det fungerade?

Kontrollera att du har aktiverat och konfigurerat Säkra dokument genom att göra något av följande:

- I Säkerhets- &  \>  \> **Efterlevnadscenter** går du till **ATP** för hanteringspolicy för säkra bifogade filer, klickar på Globala inställningar och kontrollerar aktivera Säkra dokument för **Office-klienter** och tillåter att andra klickar genom Skyddad vy även om säkra dokument identifierar filen som skadlig kod.

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Följande filer är tillgängliga för att testa skyddet mot säkra dokument. Dessa dokument liknar filen EICAR.TXT för att testa antivirus- och antiviruslösningar. Filerna är inte skadliga, men de utlöser skydd för säkra dokument.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
