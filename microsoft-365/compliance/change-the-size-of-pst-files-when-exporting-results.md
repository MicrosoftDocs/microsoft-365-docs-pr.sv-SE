---
title: Ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Du kan ändra standardstorleken för PST-filer som laddas ned till datorn när du exporterar eDiscovery-sökresultat.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "52161513"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat

När du använder verktyget för eDiscovery-export för att exportera e-postresultaten från en eDiscovery-sökning från de olika Microsoft eDiscovery-verktygen är standardstorleken för en PST-fil som kan exporteras 10 GB. Om du vill ändra den här standardstorleken kan du redigera Windows-registret på den dator som du använder för att exportera sökresultatet. En orsak till det är att en PST-fil får plats på ett flyttbart medium, en DVD-skiva, en cd-skiva eller en USB-enhet. 
  
> [!NOTE]
> Verktyget för eDiscovery-export används för att exportera sökresultaten när de använder verktyget Innehållssökning i säkerhets- och efterlevnadscentret för &, In-Place eDiscovery i Exchange Online och eDiscovery Center i SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Skapa en registerinställning för att ändra storlek på PST-filer när du exporterar eDiscovery-sökresultat

Utför följande procedur på den dator som du använder för att exportera resultatet av en eDiscovery-sökning.
  
1. Stäng verktyget eDiscovery Export om det är öppet. 
    
2. Spara följande text i en Window-registerfil med filnamnssuffixet .reg. till exempel PstExportera.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    I exemplet ovan är värdet inställt på  `PstSizeLimitInBytes` 1 073 741 824 byte eller ungefär 1 GB. Här är några andra exempelvärden för  `PstSizeLimitInBytes` inställningen. 
    
    |**Storlek i GB (ca.)**|**Storlek i byte**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Ändra `PstSizeLimitInBytes` värdet till önskad maxstorlek för en PST-fil när du exporterar sökresultatet och spara sedan filen. 
    
4. I Windows i Utforskaren klickar eller dubbelklickar du på REG-filen som du skapade i föregående steg.
    
5. I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen. 
    
6. När du uppmanas att fortsätta klickar du på **Ja.**
    
    Registereditorn visar ett meddelande om att inställningen har lagts till i registret.
    
7. Du kan upprepa steg 3–6 om du vill ändra värdet för  `PstSizeLimitInBytes` registerinställningen. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Vanliga frågor och svar om hur du ändrar standardstorleken för PST-filer när du exporterar eDiscovery-sökresultat

 **Varför är standardstorleken 10 GB?**
  
Standardstorleken på 10 GB baseras på feedback från kunder. 10 GB är en bra balans mellan den optimala mängden innehåll i en enda PST-fil och med minsta risk för skadade filer.
  
 **Ska jag öka eller minska standardstorleken på PST-filer?**
  
Kunder tenderar att minska storleksgränsen så att sökresultaten får plats på ett flyttbart medium som de fysiskt kan skicka till andra platser inom organisationen. Vi rekommenderar inte att du ökar standardstorleken eftersom problem med skadade PST-filer som är större än 10 GB kan ha problem med skadade filer.
  
 **Vilken dator måste jag göra detta på?**
  
Du måste ändra registerinställningen på alla lokala datorer där du kör verktyget för eDiscovery-export.
  
 **Måste jag starta om datorn när jag har ändrat den här inställningen?**
  
Nej, du behöver inte starta om datorn. Men om verktyget för eDiscovery-export körs måste du stänga det och starta om det när du har ändrat den här inställningen.
  
 **Redigeras en befintlig registernyckel, eller skapas en ny nyckel?**
  
En ny registernyckel skapas första gången du kör REG-filen som du skapade i den här proceduren. Sedan redigeras inställningen varje gång du ändrar och kör REG-redigeringsfilen igen.
