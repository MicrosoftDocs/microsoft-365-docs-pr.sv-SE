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
ms.openlocfilehash: 78ae99158e30046923d24897e7ab9b45adff31d0
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445402"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Säkra dokument i Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Säkra dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Endpoint för att söka igenom dokument och filer som öppnas i [Skyddad](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) vy eller Application Guard [för Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Säkra dokument är endast tillgängligt för användare med *Säkerhetslicenser för Microsoft 365 E5* eller *Microsoft 365 E5.* Dessa licenser ingår inte i Microsoft Defender för Office 365-abonnemang.

- Säkra dokument stöds i Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus) version 2004 eller senare.

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>. Gå direkt till sidan **ATP – säkra bifogade** filer genom att öppna <https://protection.office.com/safeattachmentv2> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - För att konfigurera inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

### <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

För att skydda dig skickar Säkra dokument filer till [Microsoft Defender för Endpoint-molnet](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys. Information om hur Microsoft Defender för Endpoint hanterar dina data finns här: Microsoft Defender för [endpoint-datalagring och sekretess](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Filer som skickas av säkra dokument sparas inte i Defender utöver den tid som krävs för analys (normalt mindre än 24 timmar).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använd Säkerhets- och & för att konfigurera säkra dokument

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för hothanteringspolicy för säkra \>  \> **bifogade** filer och klickar sedan **på Globala inställningar.**

2. I den **globala inställningsfällan** som visas konfigurerar du följande inställningar:

   - **Aktivera Säkra dokument för Office-klienter**: Flytta växlingsknappen åt höger för att aktivera funktionen: ![ Aktivera ](../../media/scc-toggle-on.png) .

   - Tillåt att andra klickar i Skyddad vy även om säkra dokument identifierar filen som skadlig: Vi rekommenderar att du låter det här alternativet vara inaktiverat (låt **växlingsknappen** vara till vänster: ![ ](../../media/scc-toggle-off.png) inaktivera).

   Klicka på **Spara** när du är klar.

   ![Inställningarna för Säkra dokument när du har valt Globala inställningar på sidan Säkra bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell för att konfigurera säkra dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Parametern _EnableSafeDocs_ aktiverar eller inaktiverar Säkra dokument för hela organisationen.
- Parametern _AllowSafeDocsOpen_ tillåter eller hindrar användare från att lämna Skyddad vy (dvs. öppna dokumentet) om dokumentet har identifierats som skadligt.

Det här exemplet aktiverar Säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från Skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Gå till Microsoft Defender för slutpunktstjänsten för att aktivera granskningsfunktioner

Om du vill distribuera Microsoft Defender för Endpoint måste du gå igenom de olika faserna i distributionen. Efter introduktionen kan du konfigurera granskningsfunktionerna i Säkerhets- & efterlevnadscenter.

Mer information finns i [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding). Om du behöver mer hjälp går du till Felsöka problem med [Microsoft Defender för slutpunkts onboarding.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det fungerade?

Verifiera att du har aktiverat och konfigurerat säkra dokument genom att göra något av följande:

- I Säkerhets- & och  \>  \> **efterlevnadscenter** går du till **ATP** för hothanteringspolicyn ATP – säkra bifogade filer , klickar på Globala inställningar och verifierar Aktivera säkra dokument för **Office-klienter** och Tillåt användare att klicka igenom Skyddad vy även om säkra dokument identifierar filen som skadlig.

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Följande filer är tillgängliga för att testa skydd mot säkra dokument. Dessa dokument liknar den EICAR.TXT filen för att testa skadlig programvara och antivirusprogram. Filerna är inte skadliga, men de utlöser skydd för säkra dokument.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
