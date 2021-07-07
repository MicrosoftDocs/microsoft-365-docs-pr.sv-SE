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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="c9452-103">Ta bort en anpassad typ av känslig information med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9452-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="c9452-104">Det finns två sätt att ta bort anpassade typer av känslig information i Compliance Center PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9452-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="c9452-105">**Ta bort anpassade anpassade typer av känslig information:** Använd den metod som beskrivs i [Ändra en anpassad typ av känslig information med Hjälp av PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="c9452-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="c9452-106">Du kan exportera det anpassade regelpaketet som innehåller den anpassade typen av känslig information, ta bort typen av känslig information från XML-filen och importera den uppdaterade XML-filen tillbaka till det befintliga anpassade regelpaketet.</span><span class="sxs-lookup"><span data-stu-id="c9452-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="c9452-107">**Ta bort ett anpassat regelpaket och alla anpassade typer av känslig information som det innehåller**: Den här metoden beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c9452-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="c9452-108">Innan du tar bort en anpassad typ av känslig information ska du kontrollera att inga DLP-principer eller e-postflödesregler i Exchange (kallas även transportregler) fortfarande refererar till den typ av känslig information som finns.</span><span class="sxs-lookup"><span data-stu-id="c9452-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="c9452-109">Ansluta till Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9452-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="c9452-110">Om du vill ta bort ett anpassat regelpaket använder du cmdleten [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="c9452-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="c9452-111">Du kan använda namnvärdet (för vilket språk som helst) eller `RulePack id`-värdet (GUID) för att identifiera regelpaketet.</span><span class="sxs-lookup"><span data-stu-id="c9452-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="c9452-112">Det här exemplet tar bort regelpaketet med namnet ”Employee ID Custom Rule Pack”.</span><span class="sxs-lookup"><span data-stu-id="c9452-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="c9452-113">Se [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="c9452-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="c9452-114">Gör något av följande för att kontrollera att du har tagit bort en anpassad typ av känslig information:</span><span class="sxs-lookup"><span data-stu-id="c9452-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="c9452-115">Kör cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) och kontrollera att regelpaketet inte längre visas:</span><span class="sxs-lookup"><span data-stu-id="c9452-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="c9452-116">Kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att kontrollera att typerna av känslig information som ingick i det borttagna regelpaketet inte längre visas:</span><span class="sxs-lookup"><span data-stu-id="c9452-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="c9452-117">För anpassade typer av känslig information är egenskapsvärdet för utgivare något annat än Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="c9452-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="c9452-118">Ersätt \<Name\> med namnvärdet för typen av känslig information (till exempel Employee ID (medarbetar-ID)) och kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) för att kontrollera att typen av känslig information inte längre visas:</span><span class="sxs-lookup"><span data-stu-id="c9452-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="c9452-119">Mer information</span><span class="sxs-lookup"><span data-stu-id="c9452-119">More information</span></span>

- [<span data-ttu-id="c9452-120">Mer information om skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="c9452-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="c9452-121">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c9452-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="c9452-122">Vad DLP-funktionerna letar efter</span><span class="sxs-lookup"><span data-stu-id="c9452-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
