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
description: Lär dig hur du anpassar rapporter i webbläsaren och Power BI Desktop.
ms.openlocfilehash: 3c662dfa91939c68f0aa0a85c19a1fab003064bf
ms.sourcegitcommit: d3c1b08b3a8af29ef19ffe77da063920f28fe290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50572656"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="f0279-103">Anpassa rapporter i Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="f0279-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f0279-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="f0279-104">The admin center is changing.</span></span> <span data-ttu-id="f0279-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f0279-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f0279-106">Microsoft 365 användningsanalyser tillhandahåller en instrumentpanel i Power BI som ger insyn i hur användarna inför och använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0279-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="f0279-107">Instrumentpanelen är bara en utgångspunkt för att interagera med användningsdata.</span><span class="sxs-lookup"><span data-stu-id="f0279-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="f0279-108">Rapporterna kan anpassas för att ge en mer specialiserad insyn.</span><span class="sxs-lookup"><span data-stu-id="f0279-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="f0279-109">Du kan också använda Power BI Desktop för att anpassa rapporterna ytterligare genom att koppla dem till andra datakällor i syfte att få bättre insyn i verksamheten.</span><span class="sxs-lookup"><span data-stu-id="f0279-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="f0279-110">Anpassa rapporter i webbläsaren</span><span class="sxs-lookup"><span data-stu-id="f0279-110">Customizing reports in the browser</span></span>

<span data-ttu-id="f0279-111">I följande två exemplen får du se hur du kan ändra en befintlig visualisering och skapa en ny visualisering.</span><span class="sxs-lookup"><span data-stu-id="f0279-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="f0279-112">Ändra en befintlig visualisering</span><span class="sxs-lookup"><span data-stu-id="f0279-112">Modify an existing visual</span></span>

<span data-ttu-id="f0279-113">Det här exemplet visar hur du ändrar **fliken** Aktivering i **rapporten Om aktivering/licensiering.**</span><span class="sxs-lookup"><span data-stu-id="f0279-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="f0279-114">Välj **fliken Aktivering i** rapporten om **aktivering/licensiering.**</span><span class="sxs-lookup"><span data-stu-id="f0279-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="f0279-115">Gå in i redigeringsläget genom **att välja knappen** Redigera högst upp via knappen Mer sida i Power ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI.</span><span class="sxs-lookup"><span data-stu-id="f0279-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="f0279-117">Välj Duplicera den **här sidan längst upp till höger.**</span><span class="sxs-lookup"><span data-stu-id="f0279-117">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="f0279-119">Längst ned till höger väljer du något av de stapeldiagram som visar antalet användare som aktiverar baserat på operativsystemet, till exempel Android, iOS, Mac osv.</span><span class="sxs-lookup"><span data-stu-id="f0279-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="f0279-120">I området **Visualiseringar** till höger väljer du X bredvid det för att ta bort **Mac Count** **från** det visuella objektet.</span><span class="sxs-lookup"><span data-stu-id="f0279-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Ta bort Mac Count](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="f0279-122">Skapa en ny visualisering</span><span class="sxs-lookup"><span data-stu-id="f0279-122">Create a new visual</span></span>

<span data-ttu-id="f0279-123">Följande exempel visar hur du skapar en ny visualisering för att spåra nya Yammer-användare på månadsbasis.</span><span class="sxs-lookup"><span data-stu-id="f0279-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="f0279-124">Gå till rapporten **Produktanvändning** i det vänstra navigeringsfältet och välj **Yammer** fliken.</span><span class="sxs-lookup"><span data-stu-id="f0279-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="f0279-125">Växla till redigeringsläge genom att ![ välja knappen Mer sida i Power BI och ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="f0279-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="f0279-126">Längst ned på sidan väljer du</span><span class="sxs-lookup"><span data-stu-id="f0279-126">At the bottom of the page, select the</span></span> ![Knappen Lägg till sida i Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="f0279-128">för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="f0279-128">to create a new page.</span></span>
  
4. <span data-ttu-id="f0279-129">I området **Visualiseringar** till höger väljer du det staplade **liggande stapeldiagrammet** (översta raden, först från vänster).</span><span class="sxs-lookup"><span data-stu-id="f0279-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Välj stapeldiagram](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="f0279-131">Markera den nedre högra delen av visualiseringen och dra för att göra den större.</span><span class="sxs-lookup"><span data-stu-id="f0279-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="f0279-132">Expandera **kalendertabellen** i området Fält **till** höger.</span><span class="sxs-lookup"><span data-stu-id="f0279-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="f0279-133">Dra **MonthName** till fältområdet direkt nedanför rubriken **Axel** i området **Visualiseringar**.</span><span class="sxs-lookup"><span data-stu-id="f0279-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Dra månadsnamn](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="f0279-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span><span class="sxs-lookup"><span data-stu-id="f0279-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="f0279-136">Dra **FirstTimeUsers** till området för fält direkt nedanför rubriken **Värde**.</span><span class="sxs-lookup"><span data-stu-id="f0279-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="f0279-137">Dra **Produkt** till området **Filter** direkt nedanför rubriken **Visuella nivåfilter**.</span><span class="sxs-lookup"><span data-stu-id="f0279-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="f0279-138">I området **Filtertyp** som visas markerar du kryssrutan **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="f0279-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Markera Yammer kryssrutan](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="f0279-140">Precis under listan med visualiseringar väljer du **formatikonen Format** i ![ visualiseringarna i Power ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) BI.</span><span class="sxs-lookup"><span data-stu-id="f0279-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="f0279-141">Expandera rubriken och ändra värdet för **Rubriktext** till **First-Time Yammer Users by Month** (Förstagångsanvändare av Yammer per månad).</span><span class="sxs-lookup"><span data-stu-id="f0279-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="f0279-142">Ändra värdet för **textstorlek** till **12**.</span><span class="sxs-lookup"><span data-stu-id="f0279-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="f0279-143">Ändra rubriken på den nya sidan genom att redigera sidans namn längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="f0279-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="f0279-144">Spara rapporten genom att klicka på **Läsvy** överst och sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="f0279-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="f0279-145">Anpassa rapporterna i Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="f0279-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="f0279-p103">För de flesta kunder räcker det att ändra rapporterna och diagramvisualiseringarna i Power BI Web. En del kan emellertid behöva koppla dessa data till andra datakällor för att få bättre insyn, beroende på vissa egenheter i den egna verksamheten. Om så är fallet kan de anpassa och skapa ytterligare rapporter med hjälp av Power BI Desktop. Du kan ladda ned [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) kostnadsfritt.</span><span class="sxs-lookup"><span data-stu-id="f0279-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="f0279-149">Använda rapport-API:erna</span><span class="sxs-lookup"><span data-stu-id="f0279-149">Use the reporting APIs</span></span>

<span data-ttu-id="f0279-150">Du kan börja genom att ansluta direkt till ODATA-rapport-API:erna från Microsoft 365 som driver rapporterna.</span><span class="sxs-lookup"><span data-stu-id="f0279-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="f0279-151">Gå till **Hämta data** \> **Andra** \> **ODATA-feed** \> **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="f0279-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="f0279-152">I URL-fönstret anger du "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"</span><span class="sxs-lookup"><span data-stu-id="f0279-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="f0279-153">**OBS!** Rapport-API:erna är förhandsversioner och kan komma att ändras tills de går till produktion.</span><span class="sxs-lookup"><span data-stu-id="f0279-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="f0279-155">Ange dina autentiseringsuppgifter som administratör för Microsoft 365 (organisation eller skola) för att autentisera dig för Microsoft 365 när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="f0279-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="f0279-156">Se vanliga [frågor och](usage-analytics.md#faq) svar om du vill ha mer information om vem som har behörighet att komma åt apprapporterna för mallen införande av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0279-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="f0279-157">När anslutningen har autentiserats visas navigatörsfönstret med de datauppsättningar som är tillgängliga för anslutning.</span><span class="sxs-lookup"><span data-stu-id="f0279-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="f0279-158">Markera alla och välj **Läs in.**</span><span class="sxs-lookup"><span data-stu-id="f0279-158">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="f0279-159">Då hämtas data till Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="f0279-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="f0279-160">Spara den här filen och sedan kan du börja skapa de rapporter du behöver.</span><span class="sxs-lookup"><span data-stu-id="f0279-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![ODATA-värden som är tillgängliga i rapport-API:t](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="f0279-162">Använda Microsoft 365 mall för användningsanalys</span><span class="sxs-lookup"><span data-stu-id="f0279-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="f0279-p105">Du kan även använda mallfilen för Power BI som motsvarar Microsoft 365 användningsanalysrapporter som utgångspunkt när du ansluter till dessa data. Fördelen med att använda pbit-filen är att den redan har anslutningssträngen. Du kan också dra nytta av alla de anpassade åtgärder som skapas, utöver de data som det grundläggande schemat returnerar och bygga på dem ytterligare.</span><span class="sxs-lookup"><span data-stu-id="f0279-p105">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="f0279-166">Du kan hämta Power BI-mallfilen från [Microsoft Download Center.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="f0279-166">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="f0279-167">När du har laddat ned Power BI-mallfilen följer du de här stegen för att komma igång:</span><span class="sxs-lookup"><span data-stu-id="f0279-167">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="f0279-168">Öppna pbit-filen.</span><span class="sxs-lookup"><span data-stu-id="f0279-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="f0279-169">Ange ditt klientorganisations-ID i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f0279-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="f0279-171">Ange dina autentiseringsuppgifter som administratör för att autentisera dig för Microsoft 365 när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="f0279-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="f0279-172">för mer information om vem som har åtkomst till Microsoft 365 användningsanalysrapporter.</span><span class="sxs-lookup"><span data-stu-id="f0279-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="f0279-173">Så snart auktoriseringen är klar uppdateras alla data i Power BI-filen.</span><span class="sxs-lookup"><span data-stu-id="f0279-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="f0279-174">Datainläsningen kan ta lite tid, men när den är klar kan du spara filen som en pbix-fil och fortsätta att anpassa rapporterna eller hämta in ytterligare en datakälla till den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="f0279-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="f0279-p107">Följ anvisningarna i dokumentationen för att [komma igång med Power BI](https://go.microsoft.com/fwlink/?linkid=849802) så att du förstår hur du kan skapa rapporter, publicera dem i Power BI-tjänsten och dela med din organisation. Eventuellt krävs det ytterligare Power BI-licenser för att du ska kunna anpassa och dela. Mer detaljerad information finns i [vägledningen för licenser](https://go.microsoft.com/fwlink/p/?linkid=849803) för Power BI.</span><span class="sxs-lookup"><span data-stu-id="f0279-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

