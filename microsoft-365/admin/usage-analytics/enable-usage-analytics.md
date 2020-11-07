---
title: Aktivera Microsoft 365 användningsanalyser
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Lär dig hur du börjar samla in data för klient organisationen med hjälp av programmet Microsoft 365 användnings analys i Power BI.
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941337"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b06e7-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="b06e7-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b06e7-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="b06e7-104">The admin center is changing.</span></span> <span data-ttu-id="b06e7-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b06e7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b06e7-106">Microsoft 365 användnings analys är ännu inte tillgänglig för Microsoft 365 USA community.</span><span class="sxs-lookup"><span data-stu-id="b06e7-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b06e7-107">Steg för att aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="b06e7-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b06e7-108">För att komma igång med Microsoft 365 användnings analys måste du först göra data tillgängliga i administrations centret för Microsoft 365 och sedan starta programmet i Power BI.</span><span class="sxs-lookup"><span data-stu-id="b06e7-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="b06e7-109">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="b06e7-109">Get Power BI</span></span>

<span data-ttu-id="b06e7-110">Om du inte redan har Power BI kan du [Registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="b06e7-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="b06e7-111">Välj **prova gratis** för att registrera dig för en utvärderings version eller **Köp nu** för att få Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="b06e7-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="b06e7-112">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="b06e7-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="b06e7-113">Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mall.</span><span class="sxs-lookup"><span data-stu-id="b06e7-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="b06e7-114">För mer information, se [förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="b06e7-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="b06e7-115">Om du vill dela dina data måste både du och de personer som du delar data med, ha en Power BI Pro-licens eller innehållet måste finnas på en arbets yta i en [Power BI premium-tjänst](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="b06e7-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="b06e7-116">Aktivera programmet mall</span><span class="sxs-lookup"><span data-stu-id="b06e7-116">Enable the template app</span></span>

<span data-ttu-id="b06e7-117">Om du vill aktivera programmet mall måste du vara **Global administratör**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="b06e7-118">Mer information finns i [om administratörs roller](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="b06e7-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="b06e7-119">I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.</span><span class="sxs-lookup"><span data-stu-id="b06e7-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="b06e7-120">På sidan **användning** letar du upp **Microsoft 365 användnings analys** kort och väljer **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="b06e7-121">På panelen rapporter som öppnas ställer du in **data som är tillgängliga för Microsoft 365 användnings analys för Power BI** **på** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="b06e7-122">Data insamlings processen slutförs i två till 48 timmar beroende på innehavarens storlek.</span><span class="sxs-lookup"><span data-stu-id="b06e7-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="b06e7-123">Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="b06e7-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="b06e7-124">Starta programmet mall</span><span class="sxs-lookup"><span data-stu-id="b06e7-124">Start the template app</span></span>

<span data-ttu-id="b06e7-125">För att starta programmet mall måste du vara antingen **Global administratör** , **rapport läsare** , **Exchange-administratör** , **Skype för företag-administratör** eller SharePoint- **administratör**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-125">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="b06e7-126">Kopiera klient-ID och välj **gå till Power BI**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="b06e7-127">När du kommer till Power BI loggar du in.</span><span class="sxs-lookup"><span data-stu-id="b06e7-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="b06e7-128">**Välj sedan appar** -> **Get apps** från navigerings menyn.</span><span class="sxs-lookup"><span data-stu-id="b06e7-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="b06e7-129">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="b06e7-130">[![Välj Skaffa det nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="b06e7-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="b06e7-131">När programmet är installerat.</span><span class="sxs-lookup"><span data-stu-id="b06e7-131">Once the app is installed.</span></span> <span data-ttu-id="b06e7-132">Välj panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="b06e7-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="b06e7-133">Välj **utforska app** för att Visa appen med exempel data.</span><span class="sxs-lookup"><span data-stu-id="b06e7-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="b06e7-134">Välj **Anslut** för att koppla appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="b06e7-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="b06e7-135">Välj **Anslut** , på skärmen **anslut till Microsoft 365 användnings analys** och skriv sedan in klient-ID (utan tank streck) som du kopierade i steg (1) och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-135">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="b06e7-136">På nästa skärm väljer du **OAuth2** som **autentiseringsmetod** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="b06e7-137">Om du väljer någon annan autentiseringsmetod kommer anslutningen till programmet att Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="b06e7-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Välj Microsoft-konto som autentiseringsmetod](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="b06e7-139">När mallgalleriet har instansierats blir Microsoft 365 användnings analys instrument panelen tillgängliga i Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="b06e7-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="b06e7-140">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="b06e7-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="b06e7-141">Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="b06e7-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="b06e7-142">**Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="b06e7-143">Detta påverkar alla rapporter under användar aktivitet.</span><span class="sxs-lookup"><span data-stu-id="b06e7-143">This will impact all reports under User Activity.</span></span> <span data-ttu-id="b06e7-144">Se [navigera och utnyttja rapporterna i Microsoft 365 användnings analys](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter.</span><span class="sxs-lookup"><span data-stu-id="b06e7-144">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="b06e7-145">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="b06e7-145">Make the collected data anonymous</span></span>

<span data-ttu-id="b06e7-146">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="b06e7-146">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="b06e7-147">Då döljs identifierbar information som användare, grupp och webbplats namn i rapporter och i mallfilen.</span><span class="sxs-lookup"><span data-stu-id="b06e7-147">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="b06e7-148">Gå till **Inställningar** i administrations centret \> **Org Settings** och välj **rapporter** på fliken **tjänster** .</span><span class="sxs-lookup"><span data-stu-id="b06e7-148">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="b06e7-149">Välj **rapporter** och välj sedan om du vill **Visa anonyma identifierare**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-149">Select **Reports** , and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="b06e7-150">Denna inställning tillämpas både på användnings rapporterna och i programmet.</span><span class="sxs-lookup"><span data-stu-id="b06e7-150">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="b06e7-151">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b06e7-151">Select **Save changes**.</span></span>
