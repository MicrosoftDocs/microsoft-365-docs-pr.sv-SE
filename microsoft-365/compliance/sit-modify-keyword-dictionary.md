---
title: Ändra en nyckelordsordlista
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du ändrar en nyckelordsordlista i Microsoft 365 Kompatibilitetscenter.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685227"
---
# <a name="modify-a-keyword-dictionary"></a>Ändra en nyckelordsordlista

Du kan behöva ändra nyckelord i någon av dina nyckelordsordlistor eller ändra någon av de inbyggda ordlistorna. Du kan göra det via PowerShell eller via efterlevnadscentret.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Ändra en nyckelordsordlista i Efterlevnadscenter

Nyckelordsordlistor kan användas som `Primary elements` `Supporting elements` eller i känslig informationstyp (SIT). Du kan redigera en nyckelordsordlista när du skapar en SIT eller i en befintlig SIT. Så här redigerar du till exempel en befintlig nyckelordsordlista:

1. Öppna mönstret som har nyckelordsordlistan som du vill uppdatera.
2. Leta upp nyckelordsordlistan som du vill uppdatera och välj redigera. 
3.  Gör dina ändringar med hjälp av ett nyckelord per rad.

![skärmbild, redigera nyckelord](../media/edit-keyword-dictionary.png)

4. Välj `Done` .

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Ändra en nyckelordsordlista med hjälp av PowerShell 

Vi kommer till exempel att ändra vissa termer i PowerShell, spara termerna lokalt där du kan ändra dem i ett redigeringsprogram och sedan uppdatera de tidigare termerna. 

Hämta först ordlisteobjektet:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Om du skriver ut `$dict` visas de olika variablerna. Nyckelorden lagras i ett objekt i serverdelen, men `$dict.KeywordDictionary` innehåller en strängrepresentation av dem som du använder när du ändrar ordlistan. 

Innan du ändrar ordlistan måste du omvandla strängen med termer till en matris med hjälp av `.split(',')`-metoden. Sedan rensar du bort de oönskade blankstegen mellan nyckelorden med `.trim()`-metoden, så att bara nyckelorden finns kvar. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Nu kan du ta bort vissa termer från ordlistan. Eftersom exempelordlistan bara innehåller några få nyckelord kan du i stället gå vidare till att exportera ordlistan och redigera den i Anteckningar, men ordlistor innehåller vanligtvis en stor mängd text så du får först lära dig det här sättet att redigera dem enkelt i PowerShell.
  
I det sista steget sparade du nyckelorden i en matris. Det finns flera sätt att [ta bort objekt från en matris](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), men ett enkelt sätt är att skapa en matris med de termer som du vill ta bort från ordlistan och sedan endast kopiera ordlistetermerna som inte finns i listan med termer att ta bort.
  
Kör kommandot `$terms` för att visa den aktuella listan med termer. Kommandots utdata ser ut så här: 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

Kör kommandot för att ange de termer som du vill ta bort:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Kör kommandot för att ta bort termerna från listan:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Kör kommandot `$updatedTerms` för att visa den uppdaterade listan med termer. Kommandots utdata ser ut så här (de angivna termerna har tagits bort): 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Öppna filen, lägg till dina andra termer och spara med Unicode-kodning (UTF-16). Nu ska du ladda upp de uppdaterade termerna och uppdatera ordlistan på plats.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Nu har ordlistan uppdaterats. Fältet `Identity` hämtar namnet på ordlistan. Om du även vill ändra namnet på ordlistan med cmdleten `set-`, behöver du bara lägga till parametern `-Name` i det som visas ovan med det nya ordlistenamnet. 

Se även
- [Skapa en nyckelordsordlista](create-a-keyword-dictionary.md)
- [Skapa en anpassad känslig informationstyp](create-a-custom-sensitive-information-type.md)
