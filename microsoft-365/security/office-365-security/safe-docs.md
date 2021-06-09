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
description: Läs mer Valv dokument i Microsoft 365 E5 eller Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644758"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Säkra dokument i Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Valv Dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5 Security som använder [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Slutpunkt för att söka igenom dokument och filer som öppnas i [Skyddad](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) vy eller Application Guard [för Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Valv Dokument är endast tillgängligt för användare med *Microsoft 365 E5* eller *Microsoft 365 E5 Security* licenser. Dessa licenser ingår inte i Microsoft Defender för Office 365 abonnemang.

- Valv Dokument stöds i Microsoft 365-appar för företag (tidigare kallad Office 365 ProPlus) version 2004 eller senare.

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>. Gå direkt till **ATP-sidan Valv bifogade filer** genom att öppna <https://protection.office.com/safeattachmentv2> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du Valv för dokumentinställningar måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst Valv i dokumentinställningarna måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

### <a name="how-does-microsoft-handle-your-data"></a>Hur hanterar Microsoft dina data?

Om du vill skydda dig Valv Dokument filer till [Microsoft Defender för Endpoint-molnet](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys. Information om hur Microsoft Defender för Endpoint hanterar dina data finns här: Microsoft Defender för [endpoint-datalagring och sekretess](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Filer som Valv sparas inte i Defender utöver den tid som krävs för analys (normalt mindre än 24 timmar).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Använd Säkerhets- och & för att konfigurera Valv dokument

1. I Säkerhets- & säkerhets- och  efterlevnadscenter går du till ATP för hothanteringspolicy Valv bifogade filer \>  \> och klickar sedan **på Globala inställningar.**

2. I den **globala inställningsfällan** som visas konfigurerar du följande inställningar:

   - **Aktivera Valv dokument för Office**: Flytta reglaget åt höger för att aktivera funktionen: Aktivera ![ ](../../media/scc-toggle-on.png) .

   - Tillåt att andra klickar i Skyddad vy även om Valv-dokument identifierar filen som skadlig: Vi rekommenderar att du låter det här alternativet vara inaktiverat (låt **växlingsknappen** vara till vänster: inaktivera ![ ](../../media/scc-toggle-off.png) ).

   Klicka på **Spara** när du är klar.

   ![Valv Dokumentinställningarna när du har valt Globala inställningar Valv bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Använda Exchange Online PowerShell för att konfigurera Valv-dokument

Använd följande syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Parametern _EnableSafeDocs_ aktiverar eller inaktiverar Valv Dokument för hela organisationen.
- Parametern _AllowSafeDocsOpen_ tillåter eller hindrar användare från att lämna Skyddad vy (dvs. öppna dokumentet) om dokumentet har identifierats som skadligt.

Det här exemplet Valv dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från Skyddad vy.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Gå till Microsoft Defender för slutpunktstjänsten för att aktivera granskningsfunktioner

Om du vill distribuera Microsoft Defender för Endpoint måste du gå igenom de olika faserna i distributionen. Efter introduktionen kan du konfigurera granskningsfunktionerna i Säkerhets- & efterlevnadscenter.

Mer information finns i [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding). Om du behöver mer hjälp går du till Felsöka problem med [Microsoft Defender för slutpunkts onboarding.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>Hur vet jag att det fungerade?

Verifiera att du har aktiverat och konfigurerat Valv genom att göra något av följande:

- I Säkerhets- &  och efterlevnadscenter går du till ATP för hothanteringspolicy Valv Bifogade filer , klickar på Globala inställningar och verifierar Aktivera Valv-dokument för Office-klienter och Tillåt användare att klicka igenom Skyddad vy även om filen identifieras som skadlig i \>  \>    **Valv-dokument.**

- Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Följande filer är tillgängliga för att testa Valv Dokumentskydd. Dessa dokument liknar den EICAR.TXT filen för att testa skadlig programvara och antivirusprogram. Filerna är inte skadliga, men de utlöser Valv dokumentskydd.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
