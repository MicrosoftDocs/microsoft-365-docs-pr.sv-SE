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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="c2a18-103">Ändra en anpassad typ av känslig information med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2a18-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="c2a18-104">För att ändra en anpassad typ av känslig information i Compliance Center PowerShell måste du:</span><span class="sxs-lookup"><span data-stu-id="c2a18-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="c2a18-105">Exportera det befintliga regelpaketet som innehåller den anpassade typen av känslig information till en XML-fil (eller använda en befintlig XML-fil om du har en sådan).</span><span class="sxs-lookup"><span data-stu-id="c2a18-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="c2a18-106">Ändra den anpassade typen av känslig information i den exporterade XML-filen.</span><span class="sxs-lookup"><span data-stu-id="c2a18-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="c2a18-107">Importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet.</span><span class="sxs-lookup"><span data-stu-id="c2a18-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="c2a18-108">Information om hur du ansluter till Compliance Center PowerShell finns i [Ansluta till Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2a18-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="c2a18-109">Steg 1: Exportera det befintliga regelpaketet till en XML-fil</span><span class="sxs-lookup"><span data-stu-id="c2a18-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="c2a18-110">Om du har en kopia av XML-filen (till exempel om du just har skapat och importerat den) kan du gå vidare till nästa steg och ändra XML-filen.</span><span class="sxs-lookup"><span data-stu-id="c2a18-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="c2a18-111">Om du inte redan visste det kan du köra cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att hitta namnet på det anpassade regelpaketet:</span><span class="sxs-lookup"><span data-stu-id="c2a18-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="c2a18-112">Det inbyggda regelpaketet som innehåller de inbyggda typerna av känslig information heter Regelpaket för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2a18-112">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package.</span></span> <span data-ttu-id="c2a18-113">Det regelpaket som innehåller anpassade typer av känslig information som du skapade i gränssnittet i efterlevnadscentret heter Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="c2a18-113">The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="c2a18-114">Använd cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) för att spara det anpassade regelpaketet i en variabel:</span><span class="sxs-lookup"><span data-stu-id="c2a18-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="c2a18-115">Om namnet på regelpaketet till exempel är "Employee ID Custom Rule Pack" kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c2a18-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="c2a18-116">Exportera det anpassade regelpaketet till en XML-fil med hjälp av cmdleten [Set-Content](/powershell/module/microsoft.powershell.management/set-content):</span><span class="sxs-lookup"><span data-stu-id="c2a18-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="c2a18-117">I det här exemplet exporterar du regelpaketet till filen ExportedRulePackage.xml i mappen C:\My Documents.</span><span class="sxs-lookup"><span data-stu-id="c2a18-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="c2a18-118">Steg 2: Ändra typen av känslig information i den exporterade XML-filen</span><span class="sxs-lookup"><span data-stu-id="c2a18-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="c2a18-119">Typer av känslig information i XML-filen och andra element i filen beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c2a18-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="c2a18-120">Steg 3: Importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet</span><span class="sxs-lookup"><span data-stu-id="c2a18-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="c2a18-121">Använd cmdleten [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) för att importera den uppdaterade XML-filen tillbaka till det befintliga regelpaketet:</span><span class="sxs-lookup"><span data-stu-id="c2a18-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="c2a18-122">Se [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="c2a18-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="c2a18-123">Mer information</span><span class="sxs-lookup"><span data-stu-id="c2a18-123">More information</span></span>

- [<span data-ttu-id="c2a18-124">Mer information om skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="c2a18-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="c2a18-125">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c2a18-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="c2a18-126">Vad DLP-funktionerna letar efter</span><span class="sxs-lookup"><span data-stu-id="c2a18-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
