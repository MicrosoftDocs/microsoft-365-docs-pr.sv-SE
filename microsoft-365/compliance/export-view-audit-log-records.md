---
title: Exportera, konfigurera och visa granskningsloggposter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du exporterar, konfigurerar och visar Microsoft 365 i granskningsloggposterna.
ms.openlocfilehash: 4cea867b46d3bda7d3b3a8cd38f3d01938da8764
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161930"
---
# <a name="export-configure-and-view-audit-log-records"></a>Exportera, konfigurera och visa granskningsloggposter

När du har sökt i granskningsloggen och laddat ned sökresultatet till en CSV-fil innehåller filen en kolumn med namnet **Information,** som innehåller ytterligare information om varje händelse. Data i den här kolumnen formateras som ett JSON-objekt, som innehåller flera egenskaper som är konfigurerade som *property:value-par* avgränsade med kommatecken. Du kan använda funktionen JSON-transformering i Power Query-redigeraren i Excel för att dela upp varje egenskap i JSON-objektet i kolumnen **Information** i flera kolumner så att varje egenskap har en egen kolumn. Då kan du sortera och filtrera efter en eller flera av dessa egenskaper, vilket kan hjälpa dig att snabbt hitta de granskningsdata du letar efter.

## <a name="step-1-export-audit-log-search-results"></a>Steg 1: Exportera granskningsloggsökningsresultat

Det första steget är att söka i granskningsloggen och sedan exportera resultatet i en fil med kommaavgränsade värden (CSV) till den lokala datorn.
  
1. Kör en [granskningsloggsökning](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) och ändra sökvillkoren om det behövs tills du fått önskat resultat.

2. Klicka **på Exportera resultat** och välj Ladda ned alla **resultat.** 

   ![Klicka på Ladda ned alla resultat](../media/ExportAuditSearchResults.png)

   Det här alternativet exporterar alla granskningsposter från granskningsloggsökningen du körde i steg 1 och laddar ned rådata från granskningsloggen till en CSV-fil. 

   Ett meddelande visas längst ned i fönstret som uppmanar dig att öppna eller spara CSV-filen. 

3. Klicka **på > spara som** och spara CSV-filen på den lokala datorn. Det tar en stund att ladda ned många sökresultat. Så är det vanligtvis när du söker efter alla aktiviteter eller ett brett datumintervall. Ett meddelande längst ned i fönstret visas när CSV-filen har laddats ned.

   ![Meddelande som visas när CSV-filen har laddats ned](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > Du kan ladda ned högst 50 000 poster till en CSV-fil från en enstaka granskningsloggsökning. Om 50 000 poster laddas ned till CSV-filen kan du antagligen förutsätta att det finns fler än 50 000 händelser som uppfyller sökkriterierna. Om du vill exportera fler poster än så kan du prova att använda ett datumintervall för att minska antalet granskningsloggposter. Du kan behöva köra flera sökningar med mindre datumintervall för att exportera mer än 50 000 poster.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>Steg 2: Formatera den exporterade granskningsloggen med Power Query-redigeraren

Nästa steg är att använda transformeringsfunktionen JSON i Power Query-redigeraren i Excel för att dela upp varje egenskap i JSON-objektet i kolumnen **Information** i en egen kolumn. Sedan filtrerar du kolumner för att visa poster baserat på värdena för specifika egenskaper. Det kan hjälpa dig att snabbt hitta de granskningsdata du letar efter.

1. Öppna en tom arbetsbok i Excel för Office 365, Excel 2019 eller Excel 2016.

2. Klicka på Från **text/CSV** **i &** Hämta och omvandla data på fliken **Data.**

    ![Klicka på Från text/CSV på fliken Data](../media/JSONTransformOpenCSVFile.png)

3. Öppna CSV-filen som du laddade ned i steg 1.

4. I fönstret som visas klickar du på **Omvandla data.**

   ![Klicka på Omvandla data](../media/JSONOpenPowerQuery.png)

   CSV-filen öppnas i **Frågeredigeraren**. Det finns fyra kolumner: **CreationDate,** **UserIds**, **Operations** och **AuditData.** Kolumnen **Information är** ett JSON-objekt som innehåller flera egenskaper. Nästa steg är att skapa en kolumn för varje egenskap i JSON-objektet.

5. Högerklicka på rubriken i kolumnen **Information,** klicka på **Omvandla och** sedan på **JSON.** 

   ![Högerklicka på kolumnen Information, klicka på Omvandla och välj sedan JSON](../media/JSONTransform.png)

6. I det övre högra hörnet i **kolumnen Information klickar** du på expanderingsikonen.

   ![Klicka på expanderingsikonen i kolumnen Information](../media/JSONTransformExpandIcon.png)

   En delvis lista över egenskaperna i JSON-objekten i kolumnen **Information** visas.

7. Klicka **på Läs in** fler för att visa alla egenskaper i JSON-objekten i kolumnen **Information.**

   ![Klicka på Läs in fler för att visa alla egenskaper i JSON-objekt](../media/JSONTransformLoadJSONProperties.png)

   Du kan avmarkera kryssrutan bredvid en egenskap som du inte vill ska ingå. Att ta bort kolumner som inte är användbara för din undersökning är ett bra sätt att minska mängden data som visas i granskningsloggen. 

   > [!NOTE]
   > De JSON-egenskaper som visas i föregående skärmbild (när du klickar på Läs in **mer)** baseras på egenskaperna i kolumnen **Information** från de första 1 000 raderna i CSV-filen. Om det finns olika JSON-egenskaper i poster efter de första 1 000 raderna inkluderas inte de här egenskaperna (och en motsvarande kolumn) när **kolumnen Information** är uppdelad i flera kolumner. För att förhindra detta kan du köra granskningsloggsökningen igen och begränsa sökvillkoren så att färre poster returneras. En annan lösning är  att filtrera objekt i kolumnen Åtgärder för att minska antalet rader (innan du utför steg 5 ovan) innan du omvandlar JSON-objektet i **kolumnen Information.**

   > [!TIP]
   > Om du vill visa ett attribut i en lista,  till exempel AuditData.AffectedItems, klickar du på ikonen Expandera i det övre högra hörnet i kolumnen som du vill hämta ett attribut från och väljer sedan Utöka till ny **rad.**  Därifrån finns det en post och  du kan klicka på ikonen Expandera i det övre högra hörnet i kolumnen, visa attributen och välja det du vill visa eller extrahera.

8. Gör något av följande om du vill formatera rubriken för kolumnerna som läggs till för varje vald JSON-egenskap.

    - Avmarkera kryssrutan **Använd det ursprungliga kolumnnamnet som prefix** om du vill använda namnet på egenskapen JSON som kolumnnamn. Till exempel **RecordType eller** **SourceFileName**.

    - Låt kryssrutan **Använd det ursprungliga kolumnnamnet som prefix** vara markerad för att lägga till prefixet Information i kolumnnamnen. Till exempel **AuditData.RecordType eller** **AuditData.SourceFileName**.

9. Klicka på **OK**.

    Kolumnen **Information är** uppdelad i flera kolumner. Varje ny kolumn motsvarar en egenskap i objektet AuditData JSON. Varje rad i kolumnen innehåller värdet för egenskapen. Om egenskapen inte innehåller något värde  visas null-värdet. I Excel är celler med null-värden tomma.
  
10. På fliken **Start klickar** du på Stäng & läs in **för** att stänga Power Query-redigeraren och öppna den transformerade CSV-filen i en Excel arbetsbok.

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>Använda PowerShell för att söka efter och exportera granskningsloggposter

I stället för att använda verktyget för granskningsloggsökning i Säkerhets- & och efterlevnadscenter kan du använda cmdleten [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) i Exchange Online PowerShell för att exportera resultatet av en granskningsloggsökning till en CSV-fil. Sedan kan du följa samma procedur som beskrivs i steg 2 för att formatera granskningsloggen med Power Query-redigeraren. En fördel med att använda PowerShell-cmdleten är att du kan söka efter händelser från en viss tjänst med hjälp av *parametern RecordType.* Här är några exempel på hur du använder PowerShell för att exportera granskningsposter till en CSV-fil så att du kan använda Power Query-redigeraren för att transformera JSON-objektet i **kolumnen AuditData** enligt beskrivningen i steg 2.

I det här exemplet kör du följande kommandon för att returnera alla poster som är SharePoint delningsåtgärder.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

Sökresultaten exporteras till en CSV-fil med namnet *PowerShellAuditlog* som innehåller fyra kolumner: CreationDate, UserIds, RecordType och AuditData).

Du kan också använda namn- eller uppräkningsvärdet för posttypen som värde för *parametern RecordType.* En lista med namn på posttyper och deras motsvarande uppräkningsvärden finns i tabellen *AuditLogRecordType* [i Office 365 Api-schema för hanteringsaktivitet.](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)

Du kan bara ta med ett enda värde för *RecordType-parametern.* Om du vill söka efter granskningsposter efter andra posttyper måste du köra de två föregående kommandona igen för att ange en annan posttyp och lägga till dessa resultat i den ursprungliga CSV-filen. Kör till exempel följande två kommandon för att lägga SharePoint filaktiviteter från samma datumintervall till den PowerShellAuditlog.csv filen.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>Tips för att exportera och visa granskningsloggen

Här är några tips och exempel på hur du exporterar och visar granskningsloggen före och efter att du använder funktionen JSON-transformering för att dela upp **kolumnen Information** i flera kolumner.

- Filtrera **kolumnen RecordType så** att endast poster från en viss tjänst eller ett visst funktionellt område visas. Om du till exempel vill visa händelser SharePoint delning markerar du **14** (uppräkningsvärdet för poster som utlöses av SharePoint delningsaktiviteter). En lista över tjänster som motsvarar uppräkningsvärdena som visas i **kolumnen RecordType** finns i [Detaljerade egenskaper i granskningsloggen.](detailed-properties-in-the-office-365-audit-log.md)

- Filtrera kolumnen **Åtgärder** för att visa poster för specifika aktiviteter. En lista över de flesta åtgärder som motsvarar en sökbar aktivitet i verktyget för granskningsloggsökning i Säkerhets- och efterlevnadscenter för & finns i avsnittet "Granskade aktiviteter" i Söka i granskningsloggen i säkerhets- och efterlevnadscentret för [&.](search-the-audit-log-in-security-and-compliance.md#audited-activities)