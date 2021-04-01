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
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="13fe3-103">Anpassa rapporter i Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="13fe3-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="13fe3-104">Microsoft 365 användningsanalyser tillhandahåller en instrumentpanel i Power BI som ger insyn i hur användarna inför och använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13fe3-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="13fe3-105">Instrumentpanelen är bara en utgångspunkt för att interagera med användningsdata.</span><span class="sxs-lookup"><span data-stu-id="13fe3-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="13fe3-106">Rapporterna kan anpassas för att ge en mer specialiserad insyn.</span><span class="sxs-lookup"><span data-stu-id="13fe3-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="13fe3-107">Du kan också använda Power BI Desktop för att anpassa rapporterna ytterligare genom att koppla dem till andra datakällor i syfte att få bättre insyn i verksamheten.</span><span class="sxs-lookup"><span data-stu-id="13fe3-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="13fe3-108">Anpassa rapporter i webbläsaren</span><span class="sxs-lookup"><span data-stu-id="13fe3-108">Customizing reports in the browser</span></span>

<span data-ttu-id="13fe3-109">I följande två exemplen får du se hur du kan ändra en befintlig visualisering och skapa en ny visualisering.</span><span class="sxs-lookup"><span data-stu-id="13fe3-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="13fe3-110">Ändra en befintlig visualisering</span><span class="sxs-lookup"><span data-stu-id="13fe3-110">Modify an existing visual</span></span>

<span data-ttu-id="13fe3-111">Det här exemplet visar hur du ändrar **fliken** Aktivering i **rapporten om aktivering/licensiering.**</span><span class="sxs-lookup"><span data-stu-id="13fe3-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="13fe3-112">I rapporten **om aktivering/licensiering** väljer du **fliken** Aktivering.</span><span class="sxs-lookup"><span data-stu-id="13fe3-112">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="13fe3-113">Öppna redigeringsläget genom att välja **knappen** Redigera längst upp på ![ knappen Mer sida i Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI.</span><span class="sxs-lookup"><span data-stu-id="13fe3-113">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="13fe3-115">Välj Duplicera den här **sidan längst upp till höger.**</span><span class="sxs-lookup"><span data-stu-id="13fe3-115">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="13fe3-117">Längst ned till höger väljer du något av de stapeldiagram som visar antalet användare som aktiverar baserat på operativsystemet, till exempel Android, iOS, Mac osv.</span><span class="sxs-lookup"><span data-stu-id="13fe3-117">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="13fe3-118">I området **Visualiseringar** till höger, för att ta bort **Mac Count** från det visuella objektet, väljer du **X** bredvid det.</span><span class="sxs-lookup"><span data-stu-id="13fe3-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Ta bort Mac Count](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="13fe3-120">Skapa en ny visualisering</span><span class="sxs-lookup"><span data-stu-id="13fe3-120">Create a new visual</span></span>

<span data-ttu-id="13fe3-121">Följande exempel visar hur du skapar en ny visualisering för att spåra nya Yammer-användare på månadsbasis.</span><span class="sxs-lookup"><span data-stu-id="13fe3-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="13fe3-122">Gå till rapporten **Produktanvändning** i det vänstra navigeringsfältet och välj **fliken Yammer.**</span><span class="sxs-lookup"><span data-stu-id="13fe3-122">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="13fe3-123">Växla till redigeringsläge genom att ![ välja knappen Mer sida i Power BI och ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-123">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="13fe3-124">Längst ned på sidan väljer du</span><span class="sxs-lookup"><span data-stu-id="13fe3-124">At the bottom of the page, select the</span></span> ![Knappen Lägg till sida i Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="13fe3-126">för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="13fe3-126">to create a new page.</span></span>
  
4. <span data-ttu-id="13fe3-127">I området **Visualiseringar** till höger väljer du det staplade **liggande stapeldiagrammet** (översta raden, först från vänster).</span><span class="sxs-lookup"><span data-stu-id="13fe3-127">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Välj Stapeldiagram](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="13fe3-129">Markera den nedre högra delen av visualiseringen och dra för att göra den större.</span><span class="sxs-lookup"><span data-stu-id="13fe3-129">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="13fe3-130">I **området Fält** till höger expanderar du **tabellen** Kalender.</span><span class="sxs-lookup"><span data-stu-id="13fe3-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="13fe3-131">Dra **MonthName** till fältområdet direkt nedanför rubriken **Axel** i området **Visualiseringar**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Dra Månadsnamn](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="13fe3-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span><span class="sxs-lookup"><span data-stu-id="13fe3-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="13fe3-134">Dra **FirstTimeUsers** till området för fält direkt nedanför rubriken **Värde**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="13fe3-135">Dra **Produkt** till området **Filter** direkt nedanför rubriken **Visuella nivåfilter**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="13fe3-136">I området **Filtertyp** som visas markerar du kryssrutan **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Markera kryssrutan Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="13fe3-138">Precis under listan med visualiseringar väljer du **ikonen Format** ikon för Format ![ i Visualiseringar i Power ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) BI.</span><span class="sxs-lookup"><span data-stu-id="13fe3-138">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="13fe3-139">Expandera rubriken och ändra värdet för **Rubriktext** till **First-Time Yammer Users by Month** (Förstagångsanvändare av Yammer per månad).</span><span class="sxs-lookup"><span data-stu-id="13fe3-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="13fe3-140">Ändra värdet för **textstorlek** till **12**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="13fe3-141">Ändra rubriken på den nya sidan genom att redigera namnet på sidan längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="13fe3-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="13fe3-142">Spara rapporten genom att klicka på **Läsvy** överst och sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="13fe3-143">Anpassa rapporterna i Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="13fe3-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="13fe3-p102">För de flesta kunder räcker det att ändra rapporterna och diagramvisualiseringarna i Power BI Web. En del kan emellertid behöva koppla dessa data till andra datakällor för att få bättre insyn, beroende på vissa egenheter i den egna verksamheten. Om så är fallet kan de anpassa och skapa ytterligare rapporter med hjälp av Power BI Desktop. Du kan ladda ned [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostnadsfritt.</span><span class="sxs-lookup"><span data-stu-id="13fe3-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="13fe3-147">Använda rapport-API:erna</span><span class="sxs-lookup"><span data-stu-id="13fe3-147">Use the reporting APIs</span></span>

<span data-ttu-id="13fe3-148">Du kan börja genom att ansluta direkt till ODATA-rapport-API:erna från Microsoft 365 som driver rapporterna.</span><span class="sxs-lookup"><span data-stu-id="13fe3-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="13fe3-149">Gå till **Hämta data** \> **Andra** \> **ODATA-feed** \> **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="13fe3-150">I URL-fönstret skriver du "https:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "</span><span class="sxs-lookup"><span data-stu-id="13fe3-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="13fe3-151">**OBS!** Rapport-API:erna är förhandsversioner och kan komma att ändras tills de går till produktion.</span><span class="sxs-lookup"><span data-stu-id="13fe3-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="13fe3-153">Ange dina autentiseringsuppgifter som administratör för Microsoft 365 (organisation eller skola) för att autentisera dig för Microsoft 365 när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="13fe3-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="13fe3-154">Mer information [om vem](usage-analytics.md#faq) som har behörighet att komma åt apprapporterna för införande av Microsoft 365 finns i Vanliga frågor och svar.</span><span class="sxs-lookup"><span data-stu-id="13fe3-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="13fe3-155">När anslutningen har autentiserats visas navigatörsfönstret med de datauppsättningar som är tillgängliga för anslutning.</span><span class="sxs-lookup"><span data-stu-id="13fe3-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="13fe3-156">Markera alla och välj **Läs in**.</span><span class="sxs-lookup"><span data-stu-id="13fe3-156">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="13fe3-157">Då laddas data ned till din Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="13fe3-157">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="13fe3-158">Spara den här filen och börja sedan skapa de rapporter du behöver.</span><span class="sxs-lookup"><span data-stu-id="13fe3-158">Save this file and then you can start creating the reports you need.</span></span>
    
    ![ODATA-värden som är tillgängliga i rapport-API:t](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="13fe3-160">Använda Microsoft 365 mall för användningsanalys</span><span class="sxs-lookup"><span data-stu-id="13fe3-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="13fe3-p104">Du kan även använda mallfilen för Power BI som motsvarar Microsoft 365 användningsanalysrapporter som utgångspunkt när du ansluter till dessa data. Fördelen med att använda pbit-filen är att den redan har anslutningssträngen. Du kan också dra nytta av alla de anpassade åtgärder som skapas, utöver de data som det grundläggande schemat returnerar och bygga på dem ytterligare.</span><span class="sxs-lookup"><span data-stu-id="13fe3-p104">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="13fe3-164">Du kan ladda ned Power BI-mallfilen från [Microsoft Download Center.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="13fe3-164">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="13fe3-165">När du har laddat ned Power BI-mallfilen följer du de här anvisningarna för att komma igång:</span><span class="sxs-lookup"><span data-stu-id="13fe3-165">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="13fe3-166">Öppna pbit-filen.</span><span class="sxs-lookup"><span data-stu-id="13fe3-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="13fe3-167">Ange ditt klientorganisations-ID i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="13fe3-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="13fe3-169">Ange dina autentiseringsuppgifter som administratör för att autentisera dig för Microsoft 365 när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="13fe3-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="13fe3-170">om du vill ha mer information om vem som har åtkomst till användningsanalysrapporterna för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13fe3-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="13fe3-171">Så snart auktoriseringen är klar uppdateras alla data i Power BI-filen.</span><span class="sxs-lookup"><span data-stu-id="13fe3-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="13fe3-172">Datainläsningen kan ta lite tid, men när den är klar kan du spara filen som en pbix-fil och fortsätta att anpassa rapporterna eller hämta in ytterligare en datakälla till den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="13fe3-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="13fe3-p106">Följ anvisningarna i dokumentationen för att [komma igång med Power BI](/power-bi/fundamentals/desktop-getting-started) så att du förstår hur du kan skapa rapporter, publicera dem i Power BI-tjänsten och dela med din organisation. Eventuellt krävs det ytterligare Power BI-licenser för att du ska kunna anpassa och dela. Mer detaljerad information finns i [vägledningen för licenser](https://go.microsoft.com/fwlink/p/?linkid=849803) för Power BI.</span><span class="sxs-lookup"><span data-stu-id="13fe3-p106">Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
