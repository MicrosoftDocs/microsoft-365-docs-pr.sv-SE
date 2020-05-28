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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Lär dig att anpassa rapporter i webbläsaren och Power BI Desktop.
ms.openlocfilehash: 121a9be4a83570b7fcf358c48bf558d3bc7c1131
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402936"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Anpassa rapporter i Microsoft 365 användningsanalyser

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365-användningsanalys innehåller en instrumentpanel i Power BI som ger insikter om hur användare använder och använder Microsoft 365. Instrumentpanelen är bara en utgångspunkt för att interagera med användningsdata. Rapporterna kan anpassas för att ge en mer specialiserad insyn.
  
Du kan också använda Power BI Desktop för att anpassa rapporterna ytterligare genom att koppla dem till andra datakällor i syfte att få bättre insyn i verksamheten.
  
## <a name="customizing-reports-in-the-browser"></a>Anpassa rapporter i webbläsaren

I följande två exemplen får du se hur du kan ändra en befintlig visualisering och skapa en ny visualisering.
  
### <a name="modify-an-existing-visual"></a>Ändra en befintlig visualisering

I det här exemplet visas hur du ändrar fliken **Aktivering** i **aktiverings-/licensieringsrapporten.** 
  
1. Klicka på fliken Aktivering i **aktiverings-/licensieringsrapporten.** **Activation**
    
2. Ange redigeringsläget genom att klicka på knappen **Redigera** högst upp via ![ knappen Fler sidor i Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI-knappen. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Klicka på **Duplicera**den här sidan längst upp till höger .
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. Längst ner till höger, klicka på någon av stapeldiagrammen som visar antalet användare som aktiverar baserat på OS som Android, iOS, Mac, etc.
    
5. I området **Visualiseringar** till höger, för att ta bort **Mac Count** från det visuella, klicka på **X** bredvid den.

    ![Ta bort antal mac-datorer](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Skapa en ny visualisering

Följande exempel visar hur du skapar en ny visualisering för att spåra nya Yammer-användare på månadsbasis.
  
1. Gå till rapporten **Produktanvändning** med den vänstra navigeringsfliken och klicka på fliken **Yammer.**
    
2. Växla till redigeringsläge genom att klicka på ![ Knappen Mer sida i Power BI och ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Redigera**. 
    
3. Längst ned på sidan klickar du på ![Knappen Lägg till sida i Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) för att skapa en ny sida.
  
4. Klicka på **stapeldiagrammet Staplat stapel (översta** raden, först från vänster) i området **Visualiseringar** till höger.

    ![Markera stapeldiagram](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Klicka längst ned till höger i den visualiseringen och dra för att göra den större.

6. Expandera tabellen **Kalender** i området **Fält** till höger.

7. Dra **MonthName** till fältområdet direkt nedanför rubriken **Axel** i området **Visualiseringar**.
 
    ![Dra månadsnamn](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. In the **Fields** area to the right, expand the **TenantProductUsage** table.

9. Dra **FirstTimeUsers** till området för fält direkt nedanför rubriken **Värde**.

10. Dra **Produkt** till området **Filter** direkt nedanför rubriken **Visuella nivåfilter**.

11. I området **Filtertyp** som visas markerar du kryssrutan **Yammer**.

    ![Markera kryssrutan Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Precis under listan över visualiseringar klickar du på ikonen **Formatformat** ![ i Power BI Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .

13. Expandera rubriken och ändra värdet för **Rubriktext** till **First-Time Yammer Users by Month** (Förstagångsanvändare av Yammer per månad).
    
14. Ändra värdet för **textstorlek** till **12**.
    
15. Ändra rubriken på den nya sidan genom att redigera namnet på sidan längst ned till höger.

16.  Spara rapporten genom att klicka på **Läsvyn** överst och sedan **spara**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Anpassa rapporterna i Power BI Desktop

För de flesta kunder räcker det att ändra rapporterna och diagramvisualiseringarna i Power BI Web. En del kan emellertid behöva koppla dessa data till andra datakällor för att få bättre insyn, beroende på vissa egenheter i den egna verksamheten. Om så är fallet kan de anpassa och skapa ytterligare rapporter med hjälp av Power BI Desktop. Du kan ladda ned [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostnadsfritt. 
  
### <a name="use-the-reporting-apis"></a>Använda rapport-API:erna

Du kan börja med att ansluta direkt till ODATA-rapporterings-API:erna från Microsoft 365 som driver dessa rapporter.
  
1. Gå till **Hämta data** \> **Andra** \> **ODATA-feed** \> **Anslut**.
    
2. I URL-fönstret anger du "https:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "
    
    **OBS:** De rapporterande API:erna är i förhandsversion och kan komma att ändras tills de tas i produktion. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Ange dina administratörsautentiseringsuppgifter för Microsoft 365 (organisation eller skola) som du vill autentisera till Microsoft 365 när du uppmanas att göra det.
    
    Mer information om vem som får åtkomst till apprapporterna för Microsoft 365 Adoption-mallen finns i [vanliga frågor](usage-analytics.md#faq) och svar. 
    
4. När anslutningen har autentiserats visas navigatörsfönstret med de datauppsättningar som är tillgängliga för anslutning.
    
    Markera alla och klicka på **Ladda**.
    
    Då hämtas data till din Power BI Desktop. Spara filen. Sedan kan du börja skapa rapporterna som du behöver.
    
    ![ODATA-värden som är tillgängliga i rapporterings-API:et](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Använda Microsoft 365 mall för användningsanalys

Du kan även använda mallfilen för Power BI som motsvarar Microsoft 365 användningsanalysrapporter som utgångspunkt när du ansluter till dessa data. Fördelen med att använda pbit-filen är att den redan har anslutningssträngen. Du kan också dra nytta av alla de anpassade åtgärder som skapas, utöver de data som det grundläggande schemat returnerar och bygga på dem ytterligare.
  
Du kan hämta Power BI-mallfilen från Microsofts nedladdningscenter från [Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). När du har hämtat Power BI-mallfilen följer du de här anvisningarna för att komma igång:
  
1. Öppna pbit-filen.
    
2. Ange ditt klientorganisations-ID i dialogrutan.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Ange dina administratörsuppgifter som ska autentiseras till Microsoft 365 när du uppmanas att göra det.
    
     om du vill ha mer information om vem som har åtkomst till Microsoft 365-rapporterna för användningsanalys. 
    
    Så snart auktoriseringen är klar uppdateras alla data i Power BI-filen.
    
    Datainläsningen kan ta lite tid, men när den är klar kan du spara filen som en pbix-fil och fortsätta att anpassa rapporterna eller hämta in ytterligare en datakälla till den här rapporten.
    
4. Följ anvisningarna i dokumentationen för att [komma igång med Power BI](https://go.microsoft.com/fwlink/?linkid=849802) så att du förstår hur du kan skapa rapporter, publicera dem i Power BI-tjänsten och dela med din organisation. Eventuellt krävs det ytterligare Power BI-licenser för att du ska kunna anpassa och dela. Mer detaljerad information finns i [vägledningen för licenser](https://go.microsoft.com/fwlink/p/?linkid=849803) för Power BI. 
    

