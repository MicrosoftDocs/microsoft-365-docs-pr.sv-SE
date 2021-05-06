---
title: Sökstatistik i Advance eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Validera dina sökresultat genom att visa den statistik som skapas efter att du har kört en sökning i en Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161712"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Sökstatistik i Advanced eDiscovery

Ett sätt att verifiera sökresultaten är att titta på statistiken runt resultaten och se till att de stämmer överens med dina förväntningar. När sökningen är klar visas statistik på hög nivå på den utfällbaserade sökinformationen:

- Antal objekt och antal objekt som hämtats i sökningen

- Antal och volym för delvis indexerade eller icke indexerade objekt som hittades på sökplatserna

- Antalet postlådor och platser som sökts.
Om du vill se mer detaljerad statistik klickar du på "Statistik" i den utfällade menyn med sökdetaljer.

## <a name="summary-view"></a>Sammanfattningsvy

I sammanfattningsvyn kan du se sökresultaten uppdelade efter platstyp (t.ex. Exchange). För varje platstyp visas:

- Antal platser som hade objekt som matchade sökvillkoren

- Antal objekt från dessa platser som matchade sökvillkoren

- Den totala mängden objekt som matchade sökvillkoren.

## <a name="top-locations-view"></a>Vyn Populära platser

I vyn Toppplatser ser du de enskilda platser som överensstämmer mest. För varje plats visas:

- Platsnamn (t.ex. SharePoint URL)

- Platstyp

- Antal objekt som matchade sökvillkoren

- Den totala mängden objekt som matchade sökvillkoren.

## <a name="queries-view"></a>Frågevyn

Om du har använt (c:s) nyckelord eller nyckelordsrader i frågan kan du se detaljerad information om frågan i vyn Frågor per platstyp. För varje platstyp visas:

- Del: Den här kolumnen innehåller antingen ordet "Primär" eller "Nyckelord". "Primär" innebär att raden presenterar statistik för hela frågan, medan "Nyckelord" betyder en av frågekomponenterna.

- Fråga: den faktiska frågekomponenten raden refererar till. Om del är "Primär" kommer detta att vara hela frågan. Om delen var "Nyckelord" visas en av frågekomponenterna här.
  
  - När du söker i allt innehåll i postlådor (genom att inte ange några nyckelord) är den faktiska frågan (storlek >= 0) så att alla objekt returneras
  
  - När du söker SharePoint Online OneDrive för företag webbplatser läggs de två följande komponenterna till:
    
    - NOT IsExternalContent:1 – undantar allt innehåll från en lokal SharePoint organisation
    
    - NOT isOneNotePage: 1 - undantar alla OneNote filer eftersom det skulle vara dubbletter av alla dokument som matchar sökfrågan.

- Antal platser som hade objekt som matchade sökvillkoren.

- Antalet objekt från dessa platser som matchade sökvillkoren.

- Den totala mängden objekt som matchade sökvillkoren.
