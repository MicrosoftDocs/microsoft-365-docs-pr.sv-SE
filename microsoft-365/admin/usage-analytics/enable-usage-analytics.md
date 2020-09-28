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
ms.openlocfilehash: 1e59811d6812c6a9d68878f6766181e85efb668b
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295339"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="5555c-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="5555c-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5555c-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="5555c-104">The admin center is changing.</span></span> <span data-ttu-id="5555c-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="5555c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5555c-106">Microsoft 365 användnings analys är ännu inte tillgänglig för Microsoft 365 USA community.</span><span class="sxs-lookup"><span data-stu-id="5555c-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="5555c-107">Steg för att aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="5555c-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="5555c-108">För att komma igång med Microsoft 365 användnings analys måste du först göra data tillgängliga i administrations centret för Microsoft 365 och sedan starta programmet i Power BI.</span><span class="sxs-lookup"><span data-stu-id="5555c-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="5555c-109">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="5555c-109">Get Power BI</span></span>

<span data-ttu-id="5555c-110">Om du inte redan har Power BI kan du [Registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="5555c-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="5555c-111">Välj **prova gratis** för att registrera dig för en utvärderings version eller **Köp nu** för att få Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="5555c-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="5555c-112">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="5555c-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="5555c-113">Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mall.</span><span class="sxs-lookup"><span data-stu-id="5555c-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="5555c-114">För mer information, se [förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="5555c-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="5555c-115">Du behöver en Power BI Pro-licens för att dela innehåll och de personer som du delar det med, eller så måste innehållet vara på en arbets yta i en [Premium-kapacitet](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="5555c-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="5555c-116">Aktivera programmet mall</span><span class="sxs-lookup"><span data-stu-id="5555c-116">Enable the template app</span></span>

<span data-ttu-id="5555c-117">Om du vill aktivera programmet mall måste du vara antingen **Global administratör**, **rapport läsare**, Exchange- **administratör**, **Skype för företag-administratör**eller **SharePoint-administratör**.</span><span class="sxs-lookup"><span data-stu-id="5555c-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="5555c-118">Mer information finns i [om administratörs roller](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="5555c-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="5555c-119">I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.</span><span class="sxs-lookup"><span data-stu-id="5555c-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="5555c-120">På sidan **användning** letar du upp **Microsoft 365 användnings analys** kort och väljer **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="5555c-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="5555c-121">På panelen rapporter som öppnas ställer du in **data som är tillgängliga för Microsoft 365 användnings analys för Power BI** **på** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5555c-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="5555c-p104">Det här initierar datainsamlingsprocessen och tar mellan 2 och 48 timmar att slutföra beroende på storleken på din klientorganisation. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="5555c-p104">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="5555c-124">Starta programmet mall</span><span class="sxs-lookup"><span data-stu-id="5555c-124">Initiate the template app</span></span>

<span data-ttu-id="5555c-125">För att kunna starta programmet mall måste du vara antingen **Global administratör**, **rapport läsare**, Exchange- **administratör**, **Skype för företag-administratör**eller **SharePoint-administratör**.</span><span class="sxs-lookup"><span data-stu-id="5555c-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="5555c-126">Kopiera klient-ID och välj **gå till Power BI**.</span><span class="sxs-lookup"><span data-stu-id="5555c-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="5555c-127">När du kommer till Power BI loggar du in.</span><span class="sxs-lookup"><span data-stu-id="5555c-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="5555c-128">Välj appar->skaffa appar från navigerings menyn.</span><span class="sxs-lookup"><span data-stu-id="5555c-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="5555c-129">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="5555c-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="5555c-130">[![Välj Skaffa det nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="5555c-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="5555c-131">När programmet är installerat.</span><span class="sxs-lookup"><span data-stu-id="5555c-131">Once the app is installed.</span></span> <span data-ttu-id="5555c-132">Klicka på panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="5555c-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="5555c-133">Klicka på **utforska app** för att Visa appen med exempel data.</span><span class="sxs-lookup"><span data-stu-id="5555c-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="5555c-134">Klicka på **Anslut** för att koppla appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="5555c-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="5555c-135">När du har klickat **365** på **Anslut**skriver du in klient-ID (utan tank streck) som du kopierade i steg (1) och väljer **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5555c-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="5555c-136">På nästa skärm väljer du **OAuth2** som **autentiseringsmetod** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="5555c-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="5555c-137">Om du väljer någon annan autentiseringsmetod kommer anslutningen till programmet att Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="5555c-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Välj Microsoft-konto som autentiseringsmetod](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="5555c-139">När mallgalleriet har instansierats blir Microsoft 365 användnings analys instrument panelen tillgängliga i Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="5555c-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="5555c-140">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="5555c-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="5555c-141">Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="5555c-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="5555c-142">**Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**.</span><span class="sxs-lookup"><span data-stu-id="5555c-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="5555c-143">Detta påverkar alla rapporter under användar aktivitet (se [navigera och använda rapporterna i Microsoft 365 användnings analyser](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter).</span><span class="sxs-lookup"><span data-stu-id="5555c-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="5555c-144">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="5555c-144">Make the collected data anonymous</span></span>

<span data-ttu-id="5555c-145">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="5555c-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="5555c-146">Då döljs identifierbar information som användare, grupp och webbplats namn i rapporter och i mallfilen.</span><span class="sxs-lookup"><span data-stu-id="5555c-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="5555c-147">Gå till **Inställningar** i administrations centret \> **Org Settings**och välj **rapporter**på fliken **tjänster** .</span><span class="sxs-lookup"><span data-stu-id="5555c-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="5555c-148">Välj **rapporter**och välj sedan om du vill **Visa anonyma identifierare**.</span><span class="sxs-lookup"><span data-stu-id="5555c-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="5555c-149">Denna inställning tillämpas både på användnings rapporterna och i programmet.</span><span class="sxs-lookup"><span data-stu-id="5555c-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="5555c-150">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="5555c-150">Select **Save changes**.</span></span>
