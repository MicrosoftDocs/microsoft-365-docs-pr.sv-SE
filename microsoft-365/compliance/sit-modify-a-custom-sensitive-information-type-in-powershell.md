---
title: Ändra en anpassad typ av känslig information med PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du ändrar en anpassad känslig information med hjälp av PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322957"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Ändra en anpassad typ av känslig information med PowerShell

För att ändra en anpassad typ av känslig information i Compliance Center PowerShell måste du:

1. Exportera det befintliga regelpaketet som innehåller den anpassade typen av känslig information till en XML-fil (eller använda en befintlig XML-fil om du har en sådan).

2. Ändra den anpassade typen av känslig information i den exporterade XML-filen.

3. Importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet.

Information om hur du ansluter till Compliance Center PowerShell finns i [Ansluta till Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Steg 1: Exportera det befintliga regelpaketet till en XML-fil

> [!NOTE]
> Om du har en kopia av XML-filen (till exempel om du just har skapat och importerat den) kan du gå vidare till nästa steg och ändra XML-filen.

1. Om du inte redan visste det kan du köra cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att hitta namnet på det anpassade regelpaketet:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > Det inbyggda regelpaketet som innehåller de inbyggda typerna av känslig information heter Regelpaket för Microsoft. Det regelpaket som innehåller anpassade typer av känslig information som du skapade i gränssnittet i efterlevnadscentret heter Microsoft.SCCManaged.CustomRulePack.

2. Använd cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) för att spara det anpassade regelpaketet i en variabel:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Om namnet på regelpaketet till exempel är "Employee ID Custom Rule Pack" kör du följande cmdlet:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Exportera det anpassade regelpaketet till en XML-fil med hjälp av cmdleten [Set-Content](/powershell/module/microsoft.powershell.management/set-content):

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   I det här exemplet exporterar du regelpaketet till filen ExportedRulePackage.xml i mappen C:\My Documents.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Steg 2: Ändra typen av känslig information i den exporterade XML-filen

Typer av känslig information i XML-filen och andra element i filen beskrivs tidigare i det här avsnittet.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Steg 3: Importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet

Använd cmdleten [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) för att importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet:

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Se [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) för detaljerad information om syntax och parametrar.


## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)

- [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md)
