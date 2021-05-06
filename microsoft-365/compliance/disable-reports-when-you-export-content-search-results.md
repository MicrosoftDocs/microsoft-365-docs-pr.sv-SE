---
title: Inaktivera rapporter när du exporterar innehållssökningsresultat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Redigera Windows-registret på den lokala datorn om du vill inaktivera rapporter när du exporterar resultatet av en innehållssökning från säkerhets- & kompatibilitetscentret.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161579"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Inaktivera rapporter när du exporterar innehållssökningsresultat

När du använder verktyget för eDiscovery-export för att exportera resultatet av en innehållssökning i säkerhets- och efterlevnadscentret för & skapar och exporterar verktyget automatiskt två rapporter som innehåller ytterligare information om det exporterade innehållet. De här rapporterna Results.csv filen och Manifest.xml (se avsnittet Vanliga frågor och svar om hur du inaktiverar [exportrapporter](#frequently-asked-questions-about-disabling-export-reports) i det här avsnittet för detaljerade beskrivningar av rapporterna). Eftersom dessa filer kan vara mycket stora kan du snabba upp nedladdningstiden och spara diskutrymme genom att förhindra att filerna exporteras. Det kan du göra genom att Windows i registret på datorn som du använder för att exportera sökresultatet. Om du vill ta med rapporterna vid ett senare tillfälle kan du redigera registerinställningen. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Skapa registerinställningar för att inaktivera exportrapporterna

Gör följande på den dator som du använder för att exportera resultatet en innehållssökning.
  
1. Stäng verktyget eDiscovery Export om det är öppet.
    
2. Utför en eller båda av följande steg, beroende på vilken exportrapport du vill inaktivera.
    
    - **Results.csv**
    
      Spara följande text i en Windows med hjälp av filnamnssuffixet REG. till exempel DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Spara följande text i en Windows med hjälp av filnamnssuffixet REG. till exempel DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. I Windows i Utforskaren klickar eller dubbelklickar du på REG-filen som du skapade i föregående steg.
    
4. I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen. 
    
5. När du uppmanas att fortsätta klickar du på **Ja.**
    
    Registereditorn visar ett meddelande om att inställningen har lagts till i registret.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Redigera registerinställningar för att återaktivera exportrapporterna

Om du inaktiverade Results.csv- och Manifest.xml-rapporterna genom att skapa REG-filerna i föregående procedur kan du redigera filerna och återaktivera rapporten så att den exporteras med sökresultatet. Gör på nytt följande på den dator som du använder för att exportera resultatet en innehållssökning.
  
1. Stäng verktyget eDiscovery Export om det är öppet.
    
2. Redigera en eller båda .reg-redigeringsfilerna som du skapade i föregående procedur.
    
    - **Results.csv**
    
        Öppna filen DisableResultsCsv.reg Anteckningar, ändra värdet till `False` `True` och spara sedan filen. När du har redigerat filen ser den till exempel ut så här:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Öppna filen DisableManifestXml.reg i Anteckningar, ändra värdet till `False` `True` och spara sedan filen. När du har redigerat filen ser den till exempel ut så här:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. I Windows i Utforskaren klickar eller dubbelklickar du på en REG-fil som du redigerade i föregående steg.
    
4. I fönstret User Access Control klickar du på **Ja** så att Registereditorn kan göra ändringen. 
    
5. När du uppmanas att fortsätta klickar du på **Ja.**
    
    Registereditorn visar ett meddelande om att inställningen har lagts till i registret.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Vanliga frågor och svar om hur du inaktiverar exportrapporter

 **Vilka är Results.csv och Manifest.xml rapporter?**
  
Filen Results.csv och Manifest.xml innehåller ytterligare information om det innehåll som exporterades.
  
- **Results.csv** Ett Excel som innehåller information om varje objekt som hämtas som sökresultat. För e-post innehåller resultatloggen information om varje meddelande, inklusive: 
    
  - Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).
    
  - Datumet då meddelandet skickades eller togs emot.
    
  - Ämnesraden från meddelandet.
    
  - Meddelandets avsändare och mottagare.
    
  - Om meddelandet är ett duplicerat meddelande om du har aktiverat avduplicering när du exporterar sökresultatet. Dubblettmeddelanden har ett värde i den överordnade **ItemId-kolumnen** som identifierar meddelandet som en dubblett. Värdet i kolumnen **Överordnat ItemId** är detsamma som värdet i kolumnen **Item DocumentId** för meddelandet som exporterades. 
    
    För dokument SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:
    
  - URL-adressen för dokumentet.
    
  - URL-adressen för webbplatssamlingen där dokumentet finns.
    
  - Datumet då dokumentet senast ändrades.
    
  - Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).
    
- **Manifest.xml** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet. Informationen i den här rapporten är densamma som Results.csv, men den är i det format som anges av EDRM (Electronic Discovery Reference Model). Mer information om EDRM finns i [https://www.edrm.net](https://www.edrm.net) .
    
 **När bör jag inaktivera exporten av rapporterna?**
  
Det beror på dina specifika behov. Många organisationer behöver ingen ytterligare information om sökresultat och dessa rapporter behövs inte.
  
 **Vilken dator måste jag göra detta på?**
  
 Du måste ändra registerinställningen på alla lokala datorer där du kör verktyget för eDiscovery-export. 
  
 **Måste jag starta om datorn när jag har ändrat den här inställningen?**
  
Nej, du behöver inte starta om datorn. Men om verktyget för eDiscovery-export körs måste du stänga det och starta om det när du har ändrat registerinställningen.
  
 **Redigeras en befintlig registernyckel, eller skapas en ny nyckel?**
  
En ny registernyckel skapas första gången du kör REG-filen som du skapade i proceduren i det här avsnittet. Sedan redigeras inställningen varje gång du ändrar och kör .reg-redigeringsfilen på ny gång.
