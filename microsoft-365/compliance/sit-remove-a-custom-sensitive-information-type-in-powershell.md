---
title: Ta bort en anpassad typ av känslig information med PowerShell
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
description: Lär dig hur du tar bort en anpassad typ av känslig information med PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322956"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Ta bort en anpassad typ av känslig information med PowerShell



Det finns två sätt att ta bort anpassade typer av känslig information i Compliance Center PowerShell:

- **Ta bort anpassade anpassade typer av känslig information:** Använd den metod som beskrivs i [Ändra en anpassad typ av känslig information med Hjälp av PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell) Du kan exportera det anpassade regelpaketet som innehåller den anpassade typen av känslig information, ta bort typen av känslig information från XML-filen och importera den uppdaterade XML-filen tillbaka till det befintliga anpassade regelpaketet.

- **Ta bort ett anpassat regelpaket och alla anpassade typer av känslig information som det innehåller**: Den här metoden beskrivs i det här avsnittet.

> [!NOTE]
> Innan du tar bort en anpassad typ av känslig information ska du kontrollera att inga DLP-principer eller e-postflödesregler i Exchange (kallas även transportregler) fortfarande refererar till den typ av känslig information som finns.

1. [Ansluta till Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell)

2. Om du vill ta bort ett anpassat regelpaket använder du cmdleten [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Du kan använda namnvärdet (för vilket språk som helst) eller `RulePack id`-värdet (GUID) för att identifiera regelpaketet.

   Det här exemplet tar bort regelpaketet med namnet ”Employee ID Custom Rule Pack”.

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Se [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) för detaljerad information om syntax och parametrar.

3. Gör något av följande för att kontrollera att du har tagit bort en anpassad typ av känslig information:

   - Kör cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) och kontrollera att regelpaketet inte längre visas:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att kontrollera att typerna av känslig information som ingick i det borttagna regelpaketet inte längre visas:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     För anpassade typer av känslig information är egenskapsvärdet för utgivare något annat än Microsoft Corporation.

   - Ersätt \<Name\> med namnvärdet för typen av känslig information (till exempel Employee ID (medarbetar-ID)) och kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att kontrollera att typen av känslig information inte längre visas:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)

- [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md)
