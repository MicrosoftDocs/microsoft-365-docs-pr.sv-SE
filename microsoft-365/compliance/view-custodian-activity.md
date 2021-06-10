---
title: Visa visningsaktiviteter för granskare
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
ms.assetid: ''
description: Använd verktyget Advanced eDiscovery för att enkelt komma åt och söka i aktiviteten efter biblioteks anärende i ditt ärende.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "52161587"
---
# <a name="view-custodian-audit-activity"></a>Visa visningsaktiviteter för granskare

Behöver du ta reda på om en användare har visat ett visst dokument eller tagit bort ett objekt från postlådan? Advanced eDiscovery nu integrerats med det befintliga sökverktyget i granskningsloggen i Säkerhets- & Säkerhets- och efterlevnadscenter. Med hjälp av den här inbäddade upplevelsen kan du använda verktyget Advanced eDiscovery Uppsåtande hantering för att underlätta din undersökning genom att enkelt komma åt och söka i aktiviteten för biblioteks uppringare i ditt ärende.

## <a name="get-permissions"></a>Få behörigheter

Du måste ha tilldelats rollen Skrivskyddade granskningsloggar eller Granskningsloggar i Exchange Online för att söka i granskningsloggen. Som standard tilldelas de här rollerna till rollgrupperna Efterlevnadshantering och Organisationshantering på sidan Behörigheter i administrationscentret för Exchange. Om du vill ge en användare möjlighet att söka i Advanced eDiscovery-granskningsloggen med den lägsta behörighetsnivån kan du skapa en anpassad rollgrupp i Exchange Online, lägga till rollen View-Only-granskningsloggar eller granskningsloggar och sedan lägga till användaren som medlem i den nya rollgruppen. Mer information finns i Hantera rollgrupper i Exchange Online.

> [!IMPORTANT]
> Om du tilldelar en användare rollen View-Only granskningsloggar eller granskningsloggar på sidan Behörigheter i säkerhets- och efterlevnadscentret för & kan de inte söka i granskningsloggen. Du måste tilldela behörigheterna i Exchange Online. Det beror på att den underliggande cmdleten som används för att söka i granskningsloggen är en Exchange Online-cmdlet.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Steg 1: Sök i granskningsloggen efter aktiviteter som utförts av en vårdnadshavare

1. Gå till **eDiscovery > Advanced eDiscovery** och öppna ärendet.
  
2. Klicka på **fliken** Källor.
  
3. På sidan **The Förserer** väljer du en vårdnadshavare i listan och klickar sedan på **Visa** läsaktiviteter på den utfällade sidan.

    Söksidan Förskanningsaktiviteter visas. Observera att den vårdnadshavare du valde i föregående steg visas **i** listrutan Förn eller inte. Du kan välja olika språk i listrutan, men du kan bara söka efter aktiviteter åt gången för att hitta en vårdnadshavare.

    ![Söksidan för inskanningsaktiviteter](../media/AeDCustodianActivities1.png)
   
4. Konfigurera följande sökvillkor:
      
   1. **Aktiviteter** – Klicka på listrutan för att visa de aktiviteter som du kan söka efter. När du har kört sökningen visas bara granskningsposterna för de markerade aktiviteterna. Om **du markerar Visa resultat för alla** aktiviteter visas resultat för alla aktiviteter som utförts av den som är den som matchar de andra sökvillkoren.

      ![Lista över aktiviteter](../media/CustodianActivityAudit.PNG)
      
   1. **Startdatum och Slutdatum – Välj** ett datum- och tidsintervall för att visa händelser som inträffat under perioden. De senaste sju dagarna är valda som standard. Datum och tid presenteras i UTC-format (Coordinated Universal Time). Det maximala datumintervall som du kan ange är ett år.
      
   1. **Torer** – Klicka i den här rutan och välj sedan en specifik objekt att visa sökresultat för. Granskningsposter för den valda aktiviteten som utförts av de användare du väljer i den här rutan visas i resultatlistan.
      
5. Klicka på ![Knappen Sök](../media/SearchButton.PNG)  om du vill köra sökningen enligt dina sökvillkor. Sökresultaten läses in och efter en liten stund visas de under Resultat på söksidan Förnärendeaktiviteter. 

## <a name="step-2-view-the-audit-log-search-results"></a>Steg 2: Visa granskningsloggens sökresultat

Resultatet av en granskningslogg visas under Resultat på sidan Kontroll av granskningslogg. Maximalt 5 000 (senaste) händelser visas i steg om 150 händelser. Om du vill visa fler händelser kan du använda rullningslisten i fönstret Resultat eller så kan du trycka på Skift + End för att visa de nästa 150 händelserna.

Resultatet innehåller följande information om varje händelse som returneras av sökningen.
- **Datum:** Datum och tid (i UTC-format) när händelsen inträffade.

- **IP-adress**: IP-adressen för den enhet som användes när aktiviteten loggades. IP-adressen visas i IPv4- eller IPv6-adressformat.

- **Användare**: Användaren (eller tjänstkontot) som utförde åtgärden som utlöste händelsen.

- **Aktivitet**: Den aktivitet som användaren utförde. Det här värdet motsvarar de aktiviteter som du valde i listrutan Aktiviteter. För en händelse från granskningsloggen för Exchange-administratören är värdet i den här kolumnen en Exchange-cmdlet.

- **Objekt**: Objektet som skapades eller ändrades som ett resultat av motsvarande aktivitet. Exempelvis den fil som visades eller ändrades eller det användarkonto som uppdaterades. Alla aktiviteter har inte ett värde i den här kolumnen.

- **Information:** Ytterligare information om en aktivitet. Inte heller här har alla aktiviteter ett värde.

## <a name="step-3-filter-the-search-results"></a>Steg 3: Filtrera sökresultatet

Förutom att sortera kan du också filtrera resultatet av en granskningsloggsökning. Det kan hjälpa dig att snabbt filtrera resultatet för en viss användare eller aktivitet. 

Så här filtrerar du resultatet:

 1. Skapa och kör en granskningsloggsökning.
  
2. När resultatet visas klickar du på **Filtrera resultat**.
 
3. Nyckelordsrutor visas under varje kolumnrubrik.
  
4. Klicka på någon av rutorna under en kolumnrubrik och skriv ett ord eller en fras, beroende på vilken kolumn du filtrerar på. Resultatet justeras dynamiskt och visar händelser som matchar filtret.
  
5. Om du vill ta bort ett filter klickar **du på X** i filterrutan eller så klickar du bara på Dölj **filtrering**.

## <a name="export-the-search-results-to-a-file"></a>Exportera sökresultatet till en fil

Du kan exportera resultatet av en granskningsloggsökning till en fil med kommaavgränsade värden (CSV) på den lokala datorn. Du kan öppna den här filen i Microsoft Excel och använda funktioner som att söka, sortera, filtrera och dela en enstaka kolumn (som innehåller celler med flera värden) i flera kolumner.

1. Kör en granskningsloggsökning och ändra sedan sökvillkoren tills du fått önskat resultat.
  
2. Klicka på Exportera resultat och välj något av följande alternativ:

    - **Spara inlästa resultat:** Välj det här alternativet om du bara vill exportera de poster som visas under **Resultat** på sidan **Datagranskningsloggsökning.** CSV-filen som laddas ned innehåller samma kolumner (och data) som visas på sidan (Datum, Användare, Aktivitet, Objekt och Information). En extra kolumn (mer **som heter**) ingår i CSV-filen som innehåller mer information från granskningsloggposten. Eftersom du exporterar samma resultat som är inlästa (och går att visa) på sidan Sökning i granskningslogg exporteras högst 5 000 poster.
        
    - **Ladda ned alla resultat:** Välj det här alternativet om du vill exportera alla poster från granskningsloggen som uppfyller sökvillkoren. Om du har en stor uppsättning sökresultat väljer du det här alternativet om du vill ladda ned alla poster  från granskningsloggen utöver de 5 000 resultat som kan visas på sidan Kontrollboksloggsökning. Det här alternativet laddar ned rådata från granskningsloggen till en CSV-fil och innehåller ytterligare information från granskningsloggposten i en kolumn med namnet Information. Det kan ta längre tid att ladda ned filen om du väljer det här exportalternativet eftersom filen kan vara mycket större än den som laddas ned om du väljer det andra alternativet.
    
      > [!IMPORTANT]
      > Du kan ladda ned högst 50 000 poster till en CSV-fil från en enstaka granskningsloggsökning. Om 50 000 poster laddas ned till CSV-filen kan du antagligen förutsätta att det finns fler än 50 000 händelser som uppfyller sökkriterierna. Om du vill exportera fler poster än så kan du prova att använda ett datumintervall för att minska antalet granskningsloggposter. Du kan behöva köra flera sökningar med mindre datumintervall för att exportera mer än 50 000 poster.
        

3. När du har valt exportalternativ visas ett meddelande längst ned i fönstret som uppmanar dig att öppna CSV-filen, spara den i mappen Hämtade filer eller spara den i en särskild mapp

Mer information om hur du visar, filtrerar eller exporterar granskningsloggsökningsresultat finns i Söka i granskningsloggen i [& Säkerhets- och efterlevnadscenter.](search-the-audit-log-in-security-and-compliance.md)
