---
title: Riktlinjer för testpaket
description: Läs riktlinjerna för testpaket
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323049"
---
# <a name="test-package-guidelines"></a>Riktlinjer för testpaket

## <a name="1---script-referencing"></a>1. Skript som refererar

När du överför .zip en fil till portalen packas allt innehåll i filen upp i en rotmapp. Du behöver inte skriva någon kod för att göra den här första packa upp åtgärden. Du kan också referera till alla filer .zip filen genom att använda sökvägen i förhållande till zip-filen som laddats upp.

I exemplet nedan visar vi hur du kan referera till binärvärden/skript från inmatningsfältet på fliken Uppgifter. Texten i blått ska skrivas in i **fältet Skriptsökväg** **utan citattecken.**

Det är viktigt att du är medveten om innehållet i ZIP-filen innan du laddar upp den. När du zippar en mapp skapar din lokala dator ofta en huvudmapp under ZIP-filen. I det här fallet visas referensen i fetstil **nedan:**

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/mapp1/script.ps1"**

Ibland kan zip-filen ha filer eller innehåll direkt under det, det vill säga ingen mapp på andra nivån:

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **"ScriptX.ps1"**
  - Script.ps1 – **"mapp1/script.ps1"**
  
## <a name="2---script-execution"></a>2. Körning av skript

**In-box-tester:** Programpaketet måste innehålla minst tre PowerShell-skript som kör oövervakad installation, start och stängning av programmet och dess beroenden. Varje skript ska hantera kontroll av egna krav, verifiera att det har lyckats och rensa efter sig själv (om det behövs).

**Funktionstester:** Programpaketet måste innehålla minst ett PowerShell-skript. Där mer än ett skript tillhandahålls körs skripten i överföringssekvens och ett fel i ett visst skript stoppar efterföljande skript från att köras.

### <a name="script-requirements"></a>Skriptkrav

• PowerShell version 5.1+     

• Ej uppövervakad körning    

• Felreturkod               

• Validera framgången            

• Loggning för skriptspecifik loggmapp

Varje skript måste köras helt oövervakat för att köras i testpipelinet.

> [!Note]
> Skripten bör returnera "0" när de har slutförts och en felkod som inte är noll om det uppstår fel vid körning.

Varje skript bör verifiera att det har körts. T.ex. Installationsskriptet bör kontrollera om det finns vissa binärfiler och/eller registernycklar i systemet, efter att binär installationsprogrammet har avslutats, för att säkerställa att installationen lyckades. 

Detta är nödvändigt för att korrekt diagnostisera var fel uppstår under en testkörning, t.ex. det går inte att installera programmet jämfört med att starta det.

> [!Important]
> **Undvik följande:** Skript bör inte starta om datorn. Om det behövs en omstart anger du detta under uppladdningen av dina skript.

## <a name="3---log-collection"></a>3. Loggsamling

Varje skript bör mata ut alla loggar som genereras i en mapp med namnet ```logs``` . Alla mappar i katalogen ```logs``` kopieras och presenteras för nedladdning på ```Test Results``` sidan.

Installationsskriptet (som kan finnas i **app-/skript/installationskatalogen)** kan till exempel mata ut sina loggar till: **loggar/install.log,** så att den slutliga loggen blir på: **Apps/scripts/install/logs/install.log**

Systemet hämtar filen tillsammans med ```install.log``` andra filer i andra mappar och ```logs``` sorterar den för nedladdning.


## <a name="4---application-binaries"></a>4. Binärfiler för program

Eventuella binärfiler och beroenden bör inkluderas i den enda zip-filen. 

De bör omfatta allt som behövs för installationen av programmet (t.ex. programinstallationsprogrammet). Om programmet är beroende av något ramverk, till exempel .NET Core/Standard eller .NET Framework, bör dessa inkluderas i filen och refereras till korrekt i de angivna skripten.


> [!Note]
> Den uppladdade ZIP-filen får inte ha några blanksteg eller specialtecken i namnet

## <a name="next-steps"></a>Nästa steg

Gå till nästa artikel för att visa några **vanliga frågor och svar**
> [!div class="nextstepaction"]
> [Nästa steg](faq.md)
