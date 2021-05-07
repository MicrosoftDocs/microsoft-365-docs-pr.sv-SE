---
title: Exportera en rapport för innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: I stället för att exportera de faktiska resultaten av en innehållssökning i säkerhets- & kompatibilitetscentret i Office 365 kan du exportera en sökresultatrapport. Rapporten innehåller en sammanfattning av sökresultaten och ett dokument med detaljerad information om varje objekt som ska exporteras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162659"
---
# <a name="export-a-content-search-report"></a>Exportera en rapport för innehållssökning

I stället för att exportera hela uppsättningen sökresultat från en innehållssökning i efterlevnadscentret för säkerhet i & (och från en innehållssökning som är kopplad till ett eDiscovery-ärende) kan du exportera samma rapporter som genereras när du exporterar sökresultat.
  
När du exporterar en rapport laddas den ned till en mapp med samma namn som Innehållssökning, men som läggs till i *_ReportsOnly*. Om innehållssökningen till exempel heter  *ContosoCase0815* laddas rapporten ned till en mapp med namnet *ContosoCase0815_ReportsOnly*. En lista över dokument som ingår i rapporten finns i [Vad ingår i rapporten.](#whats-included-in-the-report)

## <a name="assign-roles-and-check-system-requirements"></a>Tilldela roller och kontrollera systemkrav

- Om du vill exportera en rapport för innehållssökning måste du ha tilldelats rollen Efterlevnadssökning i säkerhets- & efterlevnadscenter. Den här rollen tilldelas som standard till de inbyggda rollgrupperna eDiscovery Manager och Organisationshantering. Mer information finns i Tilldela [eDiscovery-behörigheter.](assign-ediscovery-permissions.md)

- När du exporterar en rapport lagras data tillfälligt i ett unikt Azure Storage i Microsoft-molnet innan de laddas ned till din lokala dator. Se till att din organisation kan ansluta till slutpunkten i Azure, som är **\* .blob.core.windows.net** (jokertecknet representerar en unik identifierare för exporten). Sökresultatdata tas bort från området Azure Storage två veckor efter att den har skapats.

- Datorn du använder för att exportera sökresultaten måste uppfylla följande systemkrav:

  - Senaste versionen av Windows (32-bitars eller 64-bitars)

  - Microsoft .NET Framework 4.7

- Du måste använda någon av följande webbläsare som stöds för att köra eDiscovery Export Tool<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>

    ELLER

  - Microsoft Internet Explorer 10 och senare versioner

  > [!NOTE]
  > <sup>1</sup> Microsoft tillverkar inte tillägg eller tillägg från tredje part för ClickOnce tilläggsprogram. Export av sökresultat med en webbläsare som inte stöds med tillägg eller tillägg från tredje part stöds inte.<br/>
  > <sup>2</sup> På grund av de senaste ändringarna Microsoft Edge är ClickOnce inte längre aktiverat som standard. Anvisningar om hur du aktiverar ClickOnce i Edge finns i [Använda verktyget för eDiscovery-export i Microsoft Edge.](configure-edge-to-export-search-results.md)

- Om den uppskattade totala storleken på resultatet som returneras av en innehållssökning överskrider 2 TB misslyckas exporten av rapporten. Om du vill exportera rapporten försöker du begränsa omfattningen och köra sökningen igen så att den uppskattade storleken på resultatet är mindre än 2 TB.

- När du exporterar innehållsökningsrapporter räknas antalet exporter som körs samtidigt och det maximala antalet exporter som en enskild användare kan köra. Mer information om exportgränser finns i [Exportera resultat för innehållssökning.](export-search-results.md#export-limits)

## <a name="generate-and-download-a-content-search-report"></a>Generera och ladda ned en rapport för innehållssökning

Stegen för att skapa och ladda ned en rapport för innehållssökning liknar att faktiskt exportera sökresultat.
  
## <a name="step-1-generate-the-report-for-export"></a>Steg 1: Generera rapporten för export

Det första steget är att förbereda rapporten för nedladdning till datorn som exporteras. När du rapporten överförs rapportdokumenten till ett Azure Storage i Microsoft-molnet.
  
1. Gå till [https://protection.office.com](https://protection.office.com).
    
2. Logga in med ditt arbets- eller skolkonto.
    
3. I den vänstra rutan i säkerhets- & Säkerhets- och efterlevnadscenter klickar du **på Sök** \> **efter innehållsökning**.
    
4. Välj **en sökning på** sidan Innehållssökning. 
    
5. Klicka på Generera rapport under **Exportera rapport till en dator** i **informationsfönstret.**
    
    > [!NOTE]
    > Om resultatet för en sökning är äldre än 7 dagar uppmanas du att uppdatera sökresultatet. Om det händer avbryter du  exporten, klickar på Uppdatera sökresultat i informationsfönstret för den valda sökningen och startar rapportexporten igen när resultatet har uppdaterats. 
  
6. Välj **något av följande** alternativ under **Inkludera följande objekt från sökningen** på sidan Exportera en rapport:
    
    - Exportera endast indexerade objekt
    
    - Exportera indexerade och icke indexerade objekt
    
    - Exportera endast icke indexerade objekt
    
    Mer information om icke indexerade objekt finns i [Delvis indexerade objekt i Innehållssökning](partially-indexed-items-in-content-search.md).
    
7. Välj att ta med sökstatistik för alla versioner SharePoint dokument. Det här alternativet visas bara om innehållskällorna för sökningen omfattar SharePoint eller OneDrive för företag webbplatser.
    
8. Klicka **på Generera rapport**.
    
    Sökresultatrapporten förbereds för nedladdning, vilket innebär att rapportdokumenten laddas upp till Azure Storage i Microsoft-molnet. När rapporten är klar för nedladdning visas **länken Ladda** ned rapport under Exportera rapport till **en dator** i informationsfönstret. 
    
> [!NOTE]
> Du kan också exportera en rapport för en innehållssökning som är kopplad till ett e-dataidentifieringsfall. Det gör du genom att gå **till eDiscovery** \> **eDiscovery**, markera ett ärende och klicka på **Redigera** ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) . På sidan **Sökningar** väljer du en sökning och klickar sedan på **exportera** ![ sökresultatikonen ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Exportera en rapport.** 
  
## <a name="step-2-download-the-report"></a>Steg 2: Ladda ned rapporten

Nästa steg är att ladda ned rapporten från Azure Storage området till din lokala dator.
  
1. Klicka på Ladda ned rapport under Exportera rapport till en dator **i** informationsfönstret för sökningen som du genererade **rapporten för.**
    
    Sidan **Ladda** ned rapport visas och innehåller följande information om den rapport som laddas ned till datorn. 
    
    - Antalet objekt som kommer att laddas ned.
    
    - Den uppskattade totala storleken på de objekt som kommer att laddas ned.
    
    - Om indexerade eller icke indexerade produkter exporteras. Icke indexerade objekt är objekt som har ett känt format, är krypterade eller inte indexeras av andra orsaker.
    
    - Om versioner SharePoint dokument hämtas.
    
    - Status för rapportexportprocessen. Du kan börja ladda ned rapporten även om förberedelsen av rapporten inte är slutförd.
    
2. Klicka på Kopiera till **Urklipp under Exportnyckel.**  Du använder den här nyckeln i steg 5 för att ladda ned rapporten.
    
    > [!IMPORTANT]
    > Eftersom vem som helst kan installera och starta verktyget för eDiscovery-export och sedan använda den här nyckeln för att ladda ned sökrapporten, bör du vidta vissa försiktighetsåtgärder för att skydda den här nyckeln på samma sätt som du skyddar lösenord eller annan säkerhetsrelaterad information. 
  
3. Klicka **på Ladda ned rapport.**
    
4. Om du uppmanas att installera **eDiscovery-exportverktyget klickar** du på **Installera**.
    
5. I **eDiscovery-exportverktyget** klistrar du in exportnyckeln som du kopierade i steg 2 i lämplig ruta.
    
6. Klicka **på** Bläddra för att ange den plats där du vill ladda ned rapporten. 
    
7. Klicka **på Start** för att ladda ned sökresultatet till datorn. 
    
    I **verktyget eDiscovery Export** visas statusinformation om exporten, inklusive en uppskattning av antalet (och storleken) av de återstående objekten som ska laddas ned. När exporten är klar kan du komma åt filerna på den plats där de laddades ned. 
    
> [!NOTE]
> Du kan ladda ned rapporten för en innehållssökning som är kopplad till ett e-dataidentifieringsfall. Det gör du genom att gå **till eDiscovery** \> **eDiscovery**, markera ett ärende och klicka på **Redigera** ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) . På sidan **Exporter** väljer du en rapportexport och klickar sedan **på Ladda ned** rapport i informationsfönstret. 
  
## <a name="whats-included-in-the-report"></a>Vad som ingår i rapporten

När du skapar och exporterar en rapport om resultatet av en innehållssökning laddas följande dokument ned:
  
- **Sammanfattning av export:** Ett Excel som innehåller en sammanfattning av exporten. Det omfattar information som antal innehållskällor som har sökts, antalet sökresultat från varje innehållsplats, det uppskattade antalet objekt, det faktiska antalet objekt som skulle exporteras och den uppskattade och faktiska storleken på de objekt som skulle exporteras. 
    
    > [!NOTE]
    > Om du tar med icke indexerade objekt när du exporterar rapporten inkluderas antalet icke indexerade objekt i det totala antalet uppskattade sökresultat och det totala antalet nedladdade sökresultat (om du skulle exportera sökresultaten) som visas i rapporten Exportsammanfattning. Med andra ord är det totala antalet objekt som hämtas lika med det totala antalet uppskattade resultat och det totala antalet icke indexerade objekt. 
  
- **Manifest:** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet. 
    
- **Resultat:** Ett Excel som innehåller en rad med information om varje indexerat objekt som skulle exporteras med sökresultatet. För e-post innehåller resultatloggen information om varje meddelande, inklusive: 
    
  - Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).
    
  - Datumet då meddelandet skickades eller togs emot.
    
  - Ämnesraden från meddelandet.
    
  - Meddelandets avsändare och mottagare.
    
    För dokument från SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:
    
  - URL-adressen för dokumentet.
    
  - URL-adressen för webbplatssamlingen där dokumentet finns.
    
  - Datumet då dokumentet senast ändrades.
    
  - Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).
    
    > [!NOTE]
    > Antalet rader i  resultatrapporten ska vara lika med det totala antalet sökresultat minus det totala antalet objekt som visas i rapporten Icke **indexerade** objekt. 
  
- **Icke indexerade objekt:** Ett Excel dokument som innehåller information om icke indexerade objekt som ingår i sökresultatet. Om du inte tar med icke indexerade objekt när du skapar sökresultatrapporten kommer den här rapporten fortfarande att laddas ned, men den är tom.
