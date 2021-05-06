---
title: Visa nyckelordsstatistik för resultat i innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Lär dig hur du använder funktionen Sökstatistik för att visa och jämföra statistik för flera innehållssökningar i säkerhets- & kompatibilitetscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12c51c47045996e450772c081bd26ef4a520b5f
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161845"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Visa nyckelordsstatistik för resultat i innehållssökning

När du har skapat och kört en innehållssökning kan du visa statistik om det uppskattade sökresultatet. Det inkluderar en sammanfattning av sökresultaten (ungefär som sammanfattningen av det uppskattade sökresultatet som visas i informationsfönstret), frågestatistik som antalet innehållsplatser med objekt som matchar sökfrågan och namnet på de innehållsplatser som har de mest matchande objekten. Du kan visa statistik för en eller flera innehållssökningar. På så sätt kan du snabbt jämföra resultat för flera sökningar och fatta beslut om hur effektivt dina sökfrågor är.
  
Du kan dessutom konfigurera nya och befintliga sökningar för att returnera statistik för varje nyckelord i en sökfråga. Då kan du jämföra antalet resultat för varje nyckelord i en fråga och jämföra nyckelordsstatistik från flera sökningar.
  
Du kan också ladda ned sökstatistik och nyckelordsstatistik till en CSV-fil. På så sätt kan du använda funktionerna för filtrering och sortering Excel att jämföra resultat och förbereda rapporter för sökresultaten.
  
## <a name="get-statistics-for-content-searches"></a>Hämta statistik för innehållssökningar

Så här visar du statistik för innehållssökningar:
  
1. I Microsoft 365 kompatibilitetscenter går du till **Visa all**  >  **innehållssökning**.

2. Markera två eller fler sökningar i listan med sökningar och klicka sedan på **Sök statistik** på sidan **Massåtgärder.**
    
    ![Markera flera sökningar och klicka sedan på Sökstatistik](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. På sidan **Sök statistik** klickar du på någon av följande länkar för att visa statistik om de markerade sökningarna. 
    
    **Sammanfattning**
    
    På den här sidan visas statistik som liknar den som visas i informationsfönstret på **sidan Innehållssökning.** Statistik för alla valda sökningar visas. Observera att du även kan köra de markerade sökningarna från den här sidan om du vill uppdatera statistiken. 
    
    ![Sammanfattning av statistik för de markerade sökningarna](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Namnet på innehållssökningen. Som tidigare nämnts kan du visa och jämföra statistik för flera sökningar.
    
    b. Den typ av innehållsplats som har sökts igenom. Varje rad visar statistik för postlådor, webbplatser och gemensamma mappar från den angivna sökningen.
    
    c. Antalet innehållsplatser som innehåller objekt som matchar sökfrågan. För postlådor innehåller den här statistiken även antalet arkivpostlådor som innehåller objekt som matchar sökfrågan.
    
    d. Det totala antalet objekt för alla angivna innehållsplatser som matchar sökfrågan. Exempel på objekttyper är e-postmeddelanden, kalenderobjekt och dokument. Om ett objekt innehåller flera förekomster av ett nyckelord som genomsöks räknas det bara en gång i det totala antalet objekt. Om du till exempel söker efter orden "aktie" eller "bedrägeri" och ett e-postmeddelande innehåller tre förekomster av ordet "aktie" räknas det bara en gång i kolumnen **Objekt.** 
    
    e. Den totala storleken på alla objekt som hittades på den angivna innehållsplatsen som matchar sökfrågan. 
    
    **Frågor**
    
    På den här sidan visas statistik om sökfrågan.
    
    ![Sökfrågestatistik för de markerade sökningarna](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Namnet på den innehållssökning som raden innehåller frågestatistik för.
    
    b. Den typ av innehållsplats som frågestatistiken gäller för.
    
    c. Den här kolumnen anger vilken del av sökfrågan som statistiken ska tillämpas på. **Primär** anger hela sökfrågan. Om du använder en nyckelordslista när du skapar eller redigerar en sökfråga inkluderas statistik för varje komponent i frågan i den här tabellen. Mer information [finns i avsnittet Hämta nyckelordsstatistik](#get-keyword-statistics-for-content-searches) för innehållssökningar i den här artikeln. 
    
    d. Den här kolumnen innehåller den faktiska sökfrågan som körs av verktyget Innehållssökning. Observera att verktyget automatiskt lägger till några ytterligare komponenter i frågan som du skapar. 

    - När du söker efter allt innehåll i postlådor (genom att inte ange några nyckelord) är den faktiska nyckelordsfrågan så  `size>=0` att alla objekt returneras. 
    
     - När du söker SharePoint Online OneDrive för företag webbplatser läggs de två följande komponenterna till:
    
          **NOT IsExternalContent:1** – Exkluderar allt innehåll från en lokal SharePoint organisation. 
    
          **NOT IsOneNotePage:1** – Undantar alla OneNote eftersom det skulle vara dubbletter av alla dokument som matchar sökfrågan. 

    
    e. Numret på innehållsplatserna (som anges av ** Platstyp ** kolumnen) som innehåller objekt som matchar sökfrågan som visas i **frågekolumnen.** 
    
    f. Det antal objekt (från den angivna innehållsplatsen) som matchar sökfrågan som visas i **kolumnen** Fråga. Som tidigare förklarats räknas ett objekt bara en gång i den här kolumnen om det innehåller flera förekomster av ett nyckelord som söks igenom. 
    
    g. Den totala storleken på alla objekt som hittades (på den angivna innehållsplatsen) som matchar sökfrågan i **frågekolumnen.** 
    
    **Mest populära platserna**
    
    På den här sidan visas statistik för antalet objekt som matchar sökfrågan på varje innehållsplats som har sökts. De 1 000 översta platserna visas. Om du visar statistik för flera sökningar visas de 1 000 bästa platserna för varje sökning. Observera att en innehållsplats inte finns på den här sidan om den inte innehåller några objekt som matchar sökfrågan.
    
    ![Statistik om antalet objekt som hittades på innehållsplatserna som genomsökdes](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Namnet på innehållsplatsen.
    
    b. Den typ av innehållsplats som platsstatistiken gäller för.
    
    c. Det finns kolumner för varje sökning som du visar statistik för. I den här kolumnen visas antalet (och den totala storleken) för objekt som matchar sökfrågan på varje innehållsplats. Observera att när du visar statistik för flera sökningar anger "-" i den här kolumnen att innehållsplatsen inte inkluderades i sökningen. 

## <a name="get-keyword-statistics-for-content-searches"></a>Hämta nyckelordsstatistik för innehållssökningar

Som tidigare **förklarats visar sidan** Frågor sökfrågan och antalet (och storleken) objekt som matchar frågan. Om du använder en nyckelordslista när du skapar eller redigerar en sökfråga kan du få utökad statistik som visar hur många objekt som matchar varje nyckelord eller nyckelordsfras. Det kan hjälpa dig att snabbt identifiera vilka delar av frågan som är mest (och minst) effektiva. Om ett nyckelord till exempel returnerar ett stort antal objekt kan du välja att förfina nyckelordsfrågan för att begränsa sökresultatet. Du kan konfigurera en nyckelordslista när du skapar eller redigerar en innehållssökning. 

Så här skapar du en nyckelordslista och visar nyckelordsstatistik för en innehållssökning:
  
1. I Microsoft 365 kompatibilitetscenter går du till **Visa all**  >  **innehållssökning**.
    
2. Klicka och en sökning i listan med innehållssökningar och klicka sedan på redigera  ![ redigeringsikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
3. Klicka **på** Fråga och gör sedan följande: 
    
    ![Klicka på kryssrutan Visa nyckelordslista och skriv ett nyckelord på varje rad](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Klicka på **kryssrutan Visa nyckelordslista.** 
    
    b. Skriv ett nyckelord eller en nyckelordsfas på en rad i tabellen nyckelord. Skriv till exempel **budget på** den första raden och skriv sedan **säkerhet** på den andra raden. 
    
4. När du har lagt till de nyckelord som du vill söka efter och få statistik för klickar du **på Sök** för att köra den ändrade sökningen. 
    
5. När sökningen är klar markerar du den i listan med sökningar och klickar sedan på knappen **Sök statistik.** ![ ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) Du kan också visa och jämföra nyckelordsstatistik för flera sökningar.
    
6. På sidan **Sök statistik** klickar du på **Fråga för** att visa nyckelordsstatistik för de markerade sökningarna. 
    
    ![Statistiken för varje nyckelord för de valda sökningarna visas](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Som du ser i föregående skärmbild visas statistiken för varje nyckelord. detta omfattar: 
    
    - Nyckelordsstatistik för varje typ av innehållsplats som ingår i sökningen.
    
    - Den faktiska sökfrågan för varje nyckelord, som innehåller alla villkor från sökfrågan. 
    
    - Den fullständiga sökfrågan (identifieras **som primär** i **kolumnen Del)** och statistik för hela frågan. Observera att detta är samma statistik som visas på **sidan** Sammanfattning. 

> [!NOTE]
> För att minska problemen som orsakas av stora nyckelordslistor är du nu begränsad till högst 20 rader i nyckelordslistan för en sökfråga.
