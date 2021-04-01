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
ms.openlocfilehash: d36e07a19b0ebda0d154b11723630e38b746eb8d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471095"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Anpassa rapporter i Microsoft 365 användningsanalyser

Microsoft 365 användningsanalyser tillhandahåller en instrumentpanel i Power BI som ger insyn i hur användarna inför och använder Microsoft 365. Instrumentpanelen är bara en utgångspunkt för att interagera med användningsdata. Rapporterna kan anpassas för att ge en mer specialiserad insyn.
  
Du kan också använda Power BI Desktop för att anpassa rapporterna ytterligare genom att koppla dem till andra datakällor i syfte att få bättre insyn i verksamheten.
  
## <a name="customizing-reports-in-the-browser"></a>Anpassa rapporter i webbläsaren

I följande två exemplen får du se hur du kan ändra en befintlig visualisering och skapa en ny visualisering.
  
### <a name="modify-an-existing-visual"></a>Ändra en befintlig visualisering

Det här exemplet visar hur du ändrar **fliken** Aktivering i **rapporten om aktivering/licensiering.** 
  
1. I rapporten **om aktivering/licensiering** väljer du **fliken** Aktivering.
    
2. Öppna redigeringsläget genom att välja **knappen** Redigera längst upp på ![ knappen Mer sida i Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Välj Duplicera den här **sidan längst upp till höger.**
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. Längst ned till höger väljer du något av de stapeldiagram som visar antalet användare som aktiverar baserat på operativsystemet, till exempel Android, iOS, Mac osv.
    
5. I området **Visualiseringar** till höger, för att ta bort **Mac Count** från det visuella objektet, väljer du **X** bredvid det.

    ![Ta bort Mac Count](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Skapa en ny visualisering

Följande exempel visar hur du skapar en ny visualisering för att spåra nya Yammer-användare på månadsbasis.
  
1. Gå till rapporten **Produktanvändning** i det vänstra navigeringsfältet och välj **fliken Yammer.**
    
2. Växla till redigeringsläge genom att ![ välja knappen Mer sida i Power BI och ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Redigera**. 
    
3. Längst ned på sidan väljer du ![Knappen Lägg till sida i Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) för att skapa en ny sida.
  
4. I området **Visualiseringar** till höger väljer du det staplade **liggande stapeldiagrammet** (översta raden, först från vänster).

    ![Välj Stapeldiagram](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Markera den nedre högra delen av visualiseringen och dra för att göra den större.

6. I **området Fält** till höger expanderar du **tabellen** Kalender.

7. Dra **MonthName** till fältområdet direkt nedanför rubriken **Axel** i området **Visualiseringar**.
 
    ![Dra Månadsnamn](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. In the **Fields** area to the right, expand the **TenantProductUsage** table.

9. Dra **FirstTimeUsers** till området för fält direkt nedanför rubriken **Värde**.

10. Dra **Produkt** till området **Filter** direkt nedanför rubriken **Visuella nivåfilter**.

11. I området **Filtertyp** som visas markerar du kryssrutan **Yammer**.

    ![Markera kryssrutan Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Precis under listan med visualiseringar väljer du **ikonen Format** ikon för Format ![ i Visualiseringar i Power ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) BI.

13. Expandera rubriken och ändra värdet för **Rubriktext** till **First-Time Yammer Users by Month** (Förstagångsanvändare av Yammer per månad).
    
14. Ändra värdet för **textstorlek** till **12**.
    
15. Ändra rubriken på den nya sidan genom att redigera namnet på sidan längst ned till höger.

16.  Spara rapporten genom att klicka på **Läsvy** överst och sedan på **Spara**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Anpassa rapporterna i Power BI Desktop

För de flesta kunder räcker det att ändra rapporterna och diagramvisualiseringarna i Power BI Web. En del kan emellertid behöva koppla dessa data till andra datakällor för att få bättre insyn, beroende på vissa egenheter i den egna verksamheten. Om så är fallet kan de anpassa och skapa ytterligare rapporter med hjälp av Power BI Desktop. Du kan ladda ned [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostnadsfritt. 
  
### <a name="use-the-reporting-apis"></a>Använda rapport-API:erna

Du kan börja genom att ansluta direkt till ODATA-rapport-API:erna från Microsoft 365 som driver rapporterna.
  
1. Gå till **Hämta data** \> **Andra** \> **ODATA-feed** \> **Anslut**.
    
2. I URL-fönstret skriver du "https:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "
    
    **OBS!** Rapport-API:erna är förhandsversioner och kan komma att ändras tills de går till produktion. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Ange dina autentiseringsuppgifter som administratör för Microsoft 365 (organisation eller skola) för att autentisera dig för Microsoft 365 när du uppmanas att göra det.
    
    Mer information [om vem](usage-analytics.md#faq) som har behörighet att komma åt apprapporterna för införande av Microsoft 365 finns i Vanliga frågor och svar. 
    
4. När anslutningen har autentiserats visas navigatörsfönstret med de datauppsättningar som är tillgängliga för anslutning.
    
    Markera alla och välj **Läs in**.
    
    Då laddas data ned till din Power BI Desktop. Spara den här filen och börja sedan skapa de rapporter du behöver.
    
    ![ODATA-värden som är tillgängliga i rapport-API:t](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Använda Microsoft 365 mall för användningsanalys

Du kan även använda mallfilen för Power BI som motsvarar Microsoft 365 användningsanalysrapporter som utgångspunkt när du ansluter till dessa data. Fördelen med att använda pbit-filen är att den redan har anslutningssträngen. Du kan också dra nytta av alla de anpassade åtgärder som skapas, utöver de data som det grundläggande schemat returnerar och bygga på dem ytterligare.
  
Du kan ladda ned Power BI-mallfilen från [Microsoft Download Center.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) När du har laddat ned Power BI-mallfilen följer du de här anvisningarna för att komma igång:
  
1. Öppna pbit-filen.
    
2. Ange ditt klientorganisations-ID i dialogrutan.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Ange dina autentiseringsuppgifter som administratör för att autentisera dig för Microsoft 365 när du uppmanas att göra det.
    
     om du vill ha mer information om vem som har åtkomst till användningsanalysrapporterna för Microsoft 365. 
    
    Så snart auktoriseringen är klar uppdateras alla data i Power BI-filen.
    
    Datainläsningen kan ta lite tid, men när den är klar kan du spara filen som en pbix-fil och fortsätta att anpassa rapporterna eller hämta in ytterligare en datakälla till den här rapporten.
    
4. Följ anvisningarna i dokumentationen för att [komma igång med Power BI](/power-bi/fundamentals/desktop-getting-started) så att du förstår hur du kan skapa rapporter, publicera dem i Power BI-tjänsten och dela med din organisation. Eventuellt krävs det ytterligare Power BI-licenser för att du ska kunna anpassa och dela. Mer detaljerad information finns i [vägledningen för licenser](https://go.microsoft.com/fwlink/p/?linkid=849803) för Power BI. 
