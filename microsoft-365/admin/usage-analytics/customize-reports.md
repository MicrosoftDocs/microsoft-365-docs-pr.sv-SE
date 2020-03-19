---
title: Anpassa rapporter i Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Lär dig att anpassa rapporter i webbläsaren och Power BI Desktop.
ms.openlocfilehash: 6e4bb6cf977607ca6e3b3f57240ac89dbd530e4f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809421"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Anpassa rapporter i Microsoft 365 användningsanalyser

Microsoft 365-användningsanalys tillhandahåller en instrumentpanel i Power BI som ger insikter om hur användare använder och använder Microsoft 365. Instrumentpanelen är bara en utgångspunkt för att interagera med användningsdata. Rapporterna kan anpassas för att ge en mer specialiserad insyn.
  
Du kan också använda Power BI Desktop för att anpassa rapporterna ytterligare genom att koppla dem till andra datakällor i syfte att få bättre insyn i verksamheten.
  
## <a name="customizing-reports-in-the-browser"></a>Anpassa rapporter i webbläsaren

I följande två exemplen får du se hur du kan ändra en befintlig visualisering och skapa en ny visualisering.
  
### <a name="modify-an-existing-visual"></a>Ändra en befintlig visualisering

I det här exemplet visas hur du ändrar fliken **Aktivering** i rapporten **Aktivering/licensiering.** 
  
1. I rapporten **Aktivering/licensiering** klickar du på fliken **Aktivering.**
    
2. Ange redigeringsläget genom att klicka på **knappen** Redigera ![högst upp via](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) knappen Ju mer sidknappen i Power BI-knappen. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Klicka på **Duplicera den här sidan**längst upp till höger.
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. I nedre högra, klicka på någon av stapeldiagram som visar antalet användare aktivera baserat på OS som Android, iOS, Mac, etc.
    
5. Klicka på **X** **bredvid** det för att ta bort Mac Count från det visuella objektet för att ta bort **Mac Count** från det visuella objektet.

    ![Ta bort Antalet Mac-värden](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Skapa en ny visualisering

Följande exempel visar hur du skapar en ny visualisering för att spåra nya Yammer-användare på månadsbasis.
  
1. Gå till **rapporten Produktanvändning** med vänster navigator och klicka på fliken **Yammer.**
    
2. Växla till redigeringsläge genom ![att klicka på](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) Knappen Mer sida i Power BI och **Redigera**. 
    
3. Längst ned på sidan klickar du på ![Knappen Lägg till sida i Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) för att skapa en ny sida.
  
4. Klicka på **stapeldiagrammet Staplat stapeldiagram** i området **Visualiseringar** till höger (översta raden, först från vänster).

    ![Välj stapeldiagram](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Klicka längst ned till höger i den visualiseringen och dra för att göra den större.

6. Expandera **tabellen Kalender** i området **Fält** till höger.

7. Dra **MonthName** till fältområdet direkt nedanför rubriken **Axel** i området **Visualiseringar**.
 
    ![Dra månadsnamn](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. In the **Fields** area to the right, expand the **TenantProductUsage** table.

9. Dra **FirstTimeUsers** till området för fält direkt nedanför rubriken **Värde**.

10. Dra **Produkt** till området **Filter** direkt nedanför rubriken **Visuella nivåfilter**.

11. I området **Filtertyp** som visas markerar du kryssrutan **Yammer**.

    ![Markera Yammer-kryssrutan](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Precis under listan över visualiseringar **Format** klickar ![du på ikonen Format format](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)i Power BI Visualizaions .

13. Expandera rubriken och ändra värdet för **Rubriktext** till **First-Time Yammer Users by Month** (Förstagångsanvändare av Yammer per månad).
    
14. Ändra värdet för **textstorlek** till **12**.
    
15. Ändra rubriken på den nya sidan genom att redigera namnet på sidan längst ned till höger.

16.  Spara rapporten genom att klicka på **Läsvy** överst och **spara**sedan .
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Anpassa rapporterna i Power BI Desktop

För de flesta kunder räcker det att ändra rapporterna och diagramvisualiseringarna i Power BI Web. En del kan emellertid behöva koppla dessa data till andra datakällor för att få bättre insyn, beroende på vissa egenheter i den egna verksamheten. Om så är fallet kan de anpassa och skapa ytterligare rapporter med hjälp av Power BI Desktop. Du kan ladda ned [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostnadsfritt. 
  
### <a name="use-the-reporting-apis"></a>Använda rapport-API:erna

Du kan börja med att ansluta direkt till ODATA-rapporterings-API:erna från Microsoft 365 som driver dessa rapporter.
  
1. Gå till **Hämta data** \> **Andra** \> **ODATA-feed** \> **Anslut**.
    
2. I URL-fönstret anger<i></i>\<du "https:// reports.office.com/pbi/v1.0/ tenantid\>"
    
    **OBS:** Rapporterings-API:erna är i förhandsversion och kan komma att ändras tills de tas i produktion. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Ange dina Microsoft 365-administratörsautentiseringsuppgifter (organisation eller skola) för att autentisera till Microsoft 365 när du uppmanas att göra det.
    
    Mer [FAQ](usage-analytics.md#faq) information om vem som får komma åt apprapporterna för användningsmallen för antagande av microsoft 365. 
    
4. När anslutningen har autentiserats visas navigatörsfönstret med de datauppsättningar som är tillgängliga för anslutning.
    
    Markera alla och klicka på **Ladda**.
    
    Då hämtas data till din Power BI Desktop. Spara filen. Sedan kan du börja skapa rapporterna som du behöver.
    
    ![ODATA-värden som är tillgängliga i rapporterings-API](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Använda Microsoft 365 mall för användningsanalys

Du kan även använda mallfilen för Power BI som motsvarar Microsoft 365 användningsanalysrapporter som utgångspunkt när du ansluter till dessa data. Fördelen med att använda pbit-filen är att den redan har anslutningssträngen. Du kan också dra nytta av alla de anpassade åtgärder som skapas, utöver de data som det grundläggande schemat returnerar och bygga på dem ytterligare.
  
Du kan hämta Mallfilen för Power BI från Microsofts hämtningscenter från [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). När du har hämtat Power BI-mallfilen följer du de här anvisningarna för att komma igång:
  
1. Öppna pbit-filen.
    
2. Ange ditt klientorganisations-ID i dialogrutan.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Ange dina administratörsuppgifter för att autentisera till Microsoft 365 när du uppmanas att göra det.
    
     mer information om vem som får komma åt microsoft 365-användningsanalysrapporterna. 
    
    Så snart auktoriseringen är klar uppdateras alla data i Power BI-filen.
    
    Datainläsningen kan ta lite tid, men när den är klar kan du spara filen som en pbix-fil och fortsätta att anpassa rapporterna eller hämta in ytterligare en datakälla till den här rapporten.
    
4. Följ anvisningarna i dokumentationen för att [komma igång med Power BI](https://go.microsoft.com/fwlink/?linkid=849802) så att du förstår hur du kan skapa rapporter, publicera dem i Power BI-tjänsten och dela med din organisation. Eventuellt krävs det ytterligare Power BI-licenser för att du ska kunna anpassa och dela. Mer detaljerad information finns i [vägledningen för licenser](https://go.microsoft.com/fwlink/p/?linkid=849803) för Power BI. 
    

