---
title: Upload ditt paket
description: Så här överför du programlicering, binärfiler och beroenden till testbasen
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323097"
---
# <a name="step-2-uploading-a-package"></a>Steg 2: Ladda upp ett paket

På sidan Test Base-portalen går du till alternativet för Upload nytt paket i det vänstra navigeringsfältet enligt nedan: Upload ![ ett nytt paket](Media/Upload-New-Package.png)

När du är där följer du stegen nedan för att ladda upp ett nytt paket.

## <a name="enter-details-for-your-package"></a>Ange information om ditt paket

På fliken Testinformation skriver du in paketets namn, version och annan information som efterfrågas. 

**Du kan testa de färdiga funktionerna** via **den** här instrumentpanelen.

Stegen nedan ger en guide om hur du fyller i paketinformationen:

1.  **Ange det namn som ska anges för paketet i ```“Package name``` fältet.**

> [!Note]  
> Den paketnamns- och versionskombination som har angetts måste vara unik inom din organisation. Detta valideras av bockmarkeringen enligt nedan.
  
  - Om du väljer att använda paketets namn på nytt måste versionsnumret vara unikt (d.v.s. aldrig ha använts med ett paket som kan innehålla det specifika namnet).
  - Om kombinationen av paketnamnet + versionen inte klarar unikhetskontrollen visas ett felmeddelande med meddelandet "Paketera med den här paketversionen *finns redan".* 

![Bild för uppladdning av paketinstruktioner](Media/Instructions.png)

2. **Ange en version i fältet Paketversion.**

![Paketversion](Media/ApplicationVersion.png)

3.  **Välj vilken typ av test du vill köra på paketet**

    Ett **OOB-test (Out-of-Box)** utför en *installation*, *start,* *stängning* och *avinstallation* av paketet. Efter installationen upprepas stängningsrutin för start 30 gånger innan en enskild avinstallation körs. 
    
    Detta OOB-test förser dig med standardiserad telemetri på ditt paket för att jämföra Windows olika byggen.

    Ett **funktionstest** skulle köra dina uppladdade testskript på paketet. Skripten körs i överföringssekvens och ett fel i ett visst skript stoppar efterföljande skript att köras.

> [!Note]
> **Alla** skript körs högst i 80 minuter. 
    
4.  **Välj typ av OS-uppdatering**

   - Med säkerhetsuppdateringarna kan paketet testas mot stegvisa fallande Windows månads säkerhetsuppdateringar. 
   - Funktionsuppdateringarna gör att ditt paket kan testas mot Windows versioner av funktionsuppdateringar per år från Windows Insider Program.
<!---
Change to the correct picture
-->
![TYP av OS-uppdatering](Media/OSUpdateType.png)

5.  **Välj OS-versionerna för säkerhetsuppdateringstester.**

I listrutan för flerval väljer du operativsystemets versioner Windows ditt paket ska installeras på. 

  - Om du vill testa paketet Windows endast klient-OSes väljer du de Windows 11 OS-versionerna i menylistan.
  - Om du vill testa paketet Windows endast server-OSes väljer du de Windows Server OS-versionerna i menylistan.
  - Om du vill testa paketet Windows server- och klient-OSes markerar du alla tillämpliga OSes i menylistan. 

> [!Note]
> Om du väljer att testa paketet mot både server- och klient-OSes kontrollerar du att paketet är kompatibelt och kan köras på båda OSes


![Välja en OS-version](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  **Välja alternativ för funktionsuppdateringstester:**

  - När du väljer "Välj Insider-kanal" väljer du ```Windows Insider Program Channel``` den version som paketen ska testas mot.
  
    Vi använder för närvarande versionerna i Insider Beta-kanalen.

  - På alternativet för att "Välj OS-baslinje för Insikt" väljer du den Windows OS-version som ska användas som baslinje när du jämför testresultaten. 

> [!Note]
> Vi stöder INTE funktionsuppdateringstestning för server-OSes för stunden
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![Testa funktionsuppdatering](Media/FeatureUpdate.png)

7.  En färdig sida med testinformation ska se ut så här: 

![Visa testinformation](Media/TestDetails.png)
## <a name="next-steps"></a>Nästa steg

Vår nästa artikel handlar om att ladda upp binärfiler till vårt serivce.
> [!div class="nextstepaction"]
> [Nästa steg](binaries.md)

<!---
Add button for next page
-->

