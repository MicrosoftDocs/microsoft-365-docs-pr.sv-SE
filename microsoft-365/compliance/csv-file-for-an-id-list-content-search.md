---
title: Förbereda en CSV-fil för en ID-lista Innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Använd CSV-filer från en befintlig innehållssökning för att skapa en sökning i en ID-lista som returnerar specifika e-postmeddelanden.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161581"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Förbereda en CSV-fil för en ID-lista Innehållssökning

Du kan söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista Exchange-ID. Om du vill skapa en sökning med ID-listor (som kallas för riktad sökning) skickar du en CSV-fil (kommaavgränsade värden) som identifierar de specifika postlådeobjekten att söka efter. För den här CSV-filen använder du **Results.csv-filen** eller **Oindexerade Items.csv-filen** som tas med när du exporterar sökresultatet eller exporterar en innehållsökningsrapport från och befintlig innehållssökning. Sedan redigerar du en av dessa filer för att ange de specifika objekten som ska sökas efter, och skapar sedan en ny sökning i ID-listan och skickar CSV-filen.

Här är en snabb överblick över processen för att skapa en sökning i en ID-lista.

1. Skapa och kör en ny eller guidad innehållssökning i Säkerhets- & efterlevnadscenter.

2. Exportera innehållssökningsresultaten eller exportera rapporten för innehållssökning. Mer information finns i:

    - [Exportera resultat för innehållssökning](export-search-results.md)

    - [Exportera en rapport för innehållssökning](export-a-content-search-report.md)

3. Redigera **Results.csv** eller Icke indexerade objekt **Items.csv** och identifiera de specifika postlådeobjekt som du vill ska ingå i sökningen i ID-listan. Läs [anvisningarna för](#prepare-the-csv-file-for-an-id-list-search) att förbereda en CSV-fil för sökning i EN ID-lista.

4. Skapa en ny sökning i ID-listan (se [instruktionerna](#create-an-id-list-search)) och skicka CSV-filen som du förberett. Sökningen som skapas söker bara efter de objekt som har markerats i CSV-filen.

> [!NOTE]
> Sökningar i ID-listor stöds endast för postlådeobjekt. Det går inte att söka efter SharePoint och OneDrive dokument i en sökning i en ID-lista.

 **Varför skapa en sökning i en ID-lista?** Om du inte kan avgöra om ett objekt svarar på en eDiscovery-begäran baserat på metadata i **Results.csv-** eller **Oindexerade Items.csv-filer** kan du använda en ID-lista för att söka efter, förhandsgranska och exportera objektet för att avgöra om det svarar på det ärende som du undersöker. Sökningar i ID-listor används oftast för att söka efter och returnera en viss uppsättning icke indexerade objekt.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Förbereda CSV-filen för sökning i ID-lista

När du exporterat sökresultatet eller rapporten för en innehållssökning kan du utföra följande steg för att förbereda CSV-filen för sökning i en ID-lista. Den här CSV-filen identifierar alla objekt i sökningen i ID-listan.

Observera att du kan använda en CSV-fil från en sökning som inkluderade SharePoint webbplatser  och OneDrive-konton, men du kan bara välja postlådeobjekt för sökning med en ID-lista. Om du väljer ett dokument i SharePoint eller OneDrive misslyckas CSV-filen när du skapar en sökning i ID-listan.

1. Öppna **Results.csv** eller **icke indexerade Items.csv** i Excel.

2. I kolumnen **Markerad** skriver du **Ja** i cellen som motsvarar objektet du vill söka efter. Upprepa det här steget för alla objekt som du vill söka efter.

    > [!IMPORTANT]
    > När du öppnar CSV-filen i Excel ändras dataformatet för kolumnen **Dokument-ID** till **Allmänt.** Det leder till att dokument-ID:t för ett objekt visas i vetenskaplig notation. Exempel: Dokument-ID för "481037338205" visas som "4,81037E+11" Du måste utföra nästa steg för att  ändra dataformatet i kolumnen **Dokument-ID** till Tal för att återställa rätt format för dokument-ID. Om du inte gör det kommer sökningen i ID-listan som använder CSV-filen att misslyckas.

3. Högerklicka på hela kolumnen **Dokument-ID** och välj **Formatera celler.**

4. Klicka på **Tal** i rutan **Kategori.**

5. Ändra antalet decimaler till **0** och klicka sedan på **OK för** att spara ändringarna. Observera att värdena i kolumnen Dokument-ID ändras till tal.

    Här är ett exempel på en CSV-fil som kan skickas för innehållssökning i ID-listan.

    ![Exempel på en CSV-fil för en sökning med riktat innehåll](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Spara CSV-filen eller **använd Spara som** för att spara filen med ett annat filnamn. Se till att spara filen i CSV-format i båda fallen.

## <a name="create-an-id-list-search"></a>Skapa en sökning i en ID-lista

Nästa steg är att skapa en ny ID-lista Innehållssökning och skicka CSV-filen som du förberett i föregående steg.

> [!IMPORTANT]
> Du bör skapa en sökning i ID-listan högst 2 dagar efter att du exporterat resultatet eller rapporten från en innehållssökning. Om sökresultatet eller rapporten som exporterades för mer än två dagar sedan bör du exportera om sökresultatet eller rapporten för att generera uppdaterade CSV-filer. Sedan kan du förbereda en av de uppdaterade CSV-filerna och använda den för att skapa en sökning i ID-listan.

1. Gå till Sök & i **Säkerhets- och** \> **efterlevnadscenter.**

2. På sidan **Sök** klickar du på pilen bredvid Lägg ![ till-ikonen ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Ny sökning** och klickar sedan på Sök efter **ID-lista**.

    ![Klicka på Sök efter ID-lista i listrutan Ny sökning](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. På den **utfällbara** menyn Sök efter ID ger du sökningen  ett namn (och beskriver den om det). Klicka sedan på Bläddra och välj CSV-filen som du förberedde i föregående steg.

    Microsoft 365 försöker verifiera CSV-filen. Om verifieringen inte lyckas visas ett felmeddelande som kan hjälpa dig att felsöka verifieringsfelen. CSV-filen måste valideras för att du ska kunna skapa en sökning i ID-listan.

4. När CSV-filen har verifierats klickar du på **Sök för** att skapa sökningen i ID-listan.

    Här är ett exempel på det uppskattade sökresultatet och frågan som genereras för sökning med ID-listor.

    ![Sökfråga för en riktad innehållssökning i informationsfönstret](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Observera att det uppskattade antalet objekt som visas i statistik för ID-sökningen ska matcha antalet objekt som du valde i CSV-filen.

5. Förhandsgranska eller exportera de objekt som returneras av sökningen i ID-listan.

> [!NOTE]
> Om du flyttar en postlåda efter att ha skapat en sökning i ID-listan returnerar frågan för sökningen inte de angivna objekten. Det beror på att egenskapen **DocumentId** för postlådeobjekt ändras när en postlåda flyttas. I den sällsynta instansen när en postlåda flyttas när du har skapat en sökning i en ID-lista ska du skapa en ny innehållssökning (eller uppdatera sökresultaten för den befintliga innehållssökningen) och sedan exportera sökresultatet eller rapporten för att generera uppdaterade CSV-filer som kan användas för att skapa en ny ID-lista.
