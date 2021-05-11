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
description: Använd en CSV-fil från en befintlig innehållssökning om du vill skapa en sökning i en ID-lista som returnerar specifika e-postobjekt.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311558"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Förbereda en CSV-fil för en ID-lista Innehållssökning

Du kan söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista Exchange-ID. Om du vill skapa en sökning med en ID-lista skickar du en fil med kommaavgränsade värden (CSV) som identifierar de specifika postlådeobjekt som du vill söka efter. För den här CSV-filen använder du **Results.csv-filen** eller icke indexerade **Items.csv-filen** som tas med när du exporterar sökresultatet för innehåll eller exporterar en innehållssökningsrapport från en befintlig innehållssökning. Sedan redigerar du en av dessa filer för att ange specifika objekt att söka efter, skapa en ny sökning i ID-listan och skicka CSV-filen.

**Varför skapa en sökning i en ID-lista?** Om du inte kan avgöra om ett objekt svarar på en eDiscovery-begäran baserat på metadata i **Results.csv-** eller **Oindexerade Items.csv-filer** kan du använda en ID-lista för att söka efter, förhandsgranska och exportera objektet för att avgöra om det svarar på det ärende som du undersöker. Sökningar i ID-listor används oftast för att söka efter och returnera en viss uppsättning icke indexerade objekt.

Här är en snabb överblick över processen för att skapa en sökning i en ID-lista.

1. Skapa och kör en ny sökning i Microsoft 365 kompatibilitetscenter.

2. Exportera sökresultaten eller rapporten för innehållssökning. Mer information finns i:

    - [Exportera resultat av innehållssökning](export-search-results.md)

    - [Exportera en innehållssökningsrapport](export-a-content-search-report.md)

3. Redigera filen **Results.csv** icke **indexerade eItems.csvpostlådor** och identifiera de specifika postlådeobjekt som ska ingå i sökningen i ID-listan. Läs [anvisningarna för](#prepare-the-csv-file-for-an-id-list-search) att förbereda en CSV-fil för sökning i EN ID-lista.

4. Skapa en ny sökning i ID-listan (se [instruktionerna](#create-an-id-list-search)) och skicka CSV-filen som du förberett. Sökningen som skapas söker bara efter de objekt som har markerats i CSV-filen.

> [!NOTE]
> Sökningar i ID-listor stöds endast för postlådeobjekt. Det går inte att söka efter SharePoint och OneDrive dokument i en sökning i en ID-lista.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Förbereda CSV-filen för sökning i ID-lista

När du exporterat sökresultatet eller rapporten för en sökning utför du följande steg för att förbereda CSV-filen för en sökning i ID-listan. Den här CSV-filen identifierar alla objekt i sökningen i ID-listan.

Du kan använda en CSV-fil från en sökning som inkluderade SharePoint-webbplatser och OneDrive-konton, men du kan bara välja postlådeobjekt för sökning i en ID-lista. Om du väljer ett dokument i SharePoint eller OneDrive misslyckas CSV-filen när du skapar en sökning i ID-listan.

1. Öppna **Results.csv** eller **icke indexerade Items.csv** i Excel.

2. I kolumnen **Markerad** skriver du **Ja** i cellen som motsvarar objektet du vill söka efter. Upprepa det här steget för alla objekt som du vill söka efter.

    > [!IMPORTANT]
    > När du öppnar CSV-filen i Excel kan dataformatet för kolumnen **Dokument-ID** ha ändrats till **Allmänt.** Det leder till att dokument-ID:t för ett objekt visas i vetenskaplig notation. Dokument-ID för "481037338205" visas till exempel som "4,81037E+11". Om det händer måste du utföra nästa steg för att ändra  dataformatet i kolumnen **Dokument-ID** till Tal för att återställa rätt format för dokument-ID. Om du inte gör det kommer sökningen i ID-listan som använder CSV-filen att misslyckas.

3. Högerklicka på hela kolumnen **Dokument-ID** och välj **Formatera celler.**

4. Klicka på **Tal** i rutan **Kategori.**

5. Ändra antalet decimaler till **0** och klicka sedan på **OK för** att spara ändringarna. Observera att värdena i kolumnen Dokument-ID ändras till tal.

    Här är ett exempel på en CSV-fil som kan skickas för innehållssökning med ID-listor.

    ![Exempel på en CSV-fil för en sökning med riktat innehåll](../media/SearchIDListCSVFile.png)

6. Spara CSV-filen eller **använd Spara som** för att spara filen med ett annat filnamn. Se till att spara filen i CSV-format i båda fallen.

## <a name="create-an-id-list-search"></a>Skapa en sökning i en ID-lista

Nästa steg är att skapa en ny sökning i ID-listan och skicka CSV-filen som du förberett i föregående steg.

> [!IMPORTANT]
> Du bör skapa en sökning i ID-listan högst 2 dagar efter att du exporterat sökresultatet eller rapporten. Om sökresultatet eller rapporten som exporterades för mer än två dagar sedan bör du exportera om sökresultatet eller rapporten för att generera uppdaterade CSV-filer. Sedan kan du förbereda en av de uppdaterade CSV-filerna och använda den för att skapa en sökning i ID-listan.

1. Gå till <https://compliance.microsoft.com> och logga in.

2. I det vänstra navigeringsfönstret i Microsoft 365 Efterlevnadscenter klickar du på **Visa alla** och sedan på **Innehållssökning**.

3. Klicka på **Sök efter** ID-lista på **sidan Innehållssökning.**

4. På den **utfällbara** menyn Sök efter ID ger du sökningen  ett namn (och beskriver den om det). Klicka sedan på Bläddra och välj CSV-filen som du förberedde i föregående steg.

    Microsoft 365 försöker verifiera CSV-filen. Om verifieringen inte lyckas visas ett felmeddelande som kan hjälpa dig att felsöka verifieringsfelen. CSV-filen måste valideras för att du ska kunna skapa en sökning i ID-listan.

5. När CSV-filen har verifierats klickar du på **Sök för** att skapa sökningen i ID-listan.

    Här är ett exempel på den utfällade sidan från en sökning i ID-listan som visar den fråga som genereras och det uppskattade antalet sökresultat.

    ![Sökfråga för sökning i ID-lista](../media/SearchIDListFlyout.png)

    Det uppskattade antalet objekt som visas i statistik för ID-sökningen ska matcha antalet objekt som du valde i CSV-filen.

6. Förhandsgranska eller exportera de objekt som returneras av sökningen i ID-listan.

## <a name="more-information"></a>Mer information

Om du flyttar en postlåda efter att ha skapat en sökning i ID-listan returnerar frågan för sökningen inte de angivna objekten. Det beror på att egenskapen **DocumentId** för postlådeobjekt ändras när en postlåda flyttas. I den sällsynta instansen när en postlåda flyttas när du har skapat en sökning i en ID-lista bör du skapa en ny innehållssökning (eller uppdatera sökresultatet för en befintlig sökning) och sedan exportera sökresultatet eller rapporten för att generera uppdaterade CSV-filer som kan användas för att skapa en ny ID-lista.
