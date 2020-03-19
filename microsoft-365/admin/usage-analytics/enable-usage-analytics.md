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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Läs om hur du börjar samla in data för din klient genom att använda mallappen Microsoft 365 Usage Analytics i Power BI.
ms.openlocfilehash: 249fadce15ca2e4c979d6e1930ff0d14ccd9bc08
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808008"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="88264-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="88264-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="88264-104">Microsoft 365 användninganalytics är också tillgänglig för Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="88264-104">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="88264-105">Steg för att aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="88264-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="88264-106">Om du vill komma igång med Microsoft 365-användningsanalys måste du först göra data tillgängliga i administrationscentret för Microsoft 365 och sedan initiera mallappen i Power BI.</span><span class="sxs-lookup"><span data-stu-id="88264-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="88264-107">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="88264-107">Get Power BI</span></span>

<span data-ttu-id="88264-108">Om du inte redan har Power BI kan du [registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="88264-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="88264-109">Välj **Prova gratis** att registrera dig för en utvärderingsversion, eller Köp **nu** för att få Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="88264-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="88264-110">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="88264-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="88264-111">Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp.</span><span class="sxs-lookup"><span data-stu-id="88264-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="88264-112">Mer information finns i [Förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="88264-112">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="88264-113">Du behöver en Power BI Pro-licens för att dela ditt innehåll, och de personer du delar det med gör också, eller innehållet måste vara på en arbetsyta i [premiumkapacitet](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="88264-113">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="88264-114">Aktivera mallappen</span><span class="sxs-lookup"><span data-stu-id="88264-114">Enable the template app</span></span>

<span data-ttu-id="88264-115">Om du vill aktivera mallappen måste du vara antingen en **global administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör.**</span><span class="sxs-lookup"><span data-stu-id="88264-115">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="88264-116">Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="88264-116">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="88264-117">I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.</span><span class="sxs-lookup"><span data-stu-id="88264-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="88264-118">Leta reda på **Microsoft 365-användningsanalyskortet** på sidan **Användning** och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="88264-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="88264-119">På panelen Rapporter som öppnas anger **du Gör data tillgängliga för Microsoft 365-användningsanalys för Power BI** på **Spara** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="88264-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="88264-p103">Det här initierar datainsamlingsprocessen och tar mellan 2 och 48 timmar att slutföra beroende på storleken på din klientorganisation. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="88264-p103">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="88264-122">Starta mallappen</span><span class="sxs-lookup"><span data-stu-id="88264-122">Initiate the template app</span></span>

<span data-ttu-id="88264-123">Om du vill initiera mallappen måste du vara antingen en **global administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör.**</span><span class="sxs-lookup"><span data-stu-id="88264-123">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="88264-124">Kopiera klient-ID:t och välj **Gå till Power BI**.</span><span class="sxs-lookup"><span data-stu-id="88264-124">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="88264-125">Logga in när du kommer till Power BI.</span><span class="sxs-lookup"><span data-stu-id="88264-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="88264-126">Välj Appar >Hämta appar på navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="88264-126">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="88264-127">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="88264-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="88264-128">[![Välj Hämta den nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="88264-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="88264-129">När appen har installerats.</span><span class="sxs-lookup"><span data-stu-id="88264-129">Once the app is installed.</span></span> <span data-ttu-id="88264-130">Klicka på panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="88264-130">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="88264-131">Klicka på **Utforska app** om du vill visa appen med exempeldata.</span><span class="sxs-lookup"><span data-stu-id="88264-131">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="88264-132">Klicka på **Anslut** om du vill ansluta appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="88264-132">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="88264-133">När du har klickat på **Anslut**till **Microsoft 365 användninganalytics-** -skriver du i \> klient-ID:t som du kopierade i steg (1) **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="88264-133">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="88264-134">På nästa skärm väljer du **oAuth2** som **autentiseringsmetod** \> **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="88264-134">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="88264-135">Om du väljer någon annan autentiseringsmetod misslyckas anslutningen till mallappen.</span><span class="sxs-lookup"><span data-stu-id="88264-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="88264-137">När mallappen har instansierats kommer instrumentpanelen för användningsanalys för Microsoft 365 att vara tillgänglig i Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="88264-137">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="88264-138">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="88264-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="88264-139">Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="88264-139">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="88264-140">**Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**.</span><span class="sxs-lookup"><span data-stu-id="88264-140">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="88264-141">Detta påverkar alla rapporter under Användaraktivitet (Se [Navigera och använd rapporterna i Microsoft 365 användningsanalys](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter).</span><span class="sxs-lookup"><span data-stu-id="88264-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="88264-142">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="88264-142">Make the collected data anonymous</span></span>

<span data-ttu-id="88264-143">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="88264-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="88264-144">Detta döljer identifierbar information som användar-, grupp- och webbplatsnamn i rapporter och i mallappen .</span><span class="sxs-lookup"><span data-stu-id="88264-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="88264-145">I administrationscentret går **Settings** \> du till fliken **Inställningar**och väljer **Rapporter**under **Fliken Tjänster** .</span><span class="sxs-lookup"><span data-stu-id="88264-145">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="88264-146">Välj **Rapporter**och välj sedan **visa anonyma identifierare**.</span><span class="sxs-lookup"><span data-stu-id="88264-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="88264-147">Den här inställningen tillämpas både på användningsrapporterna och på mallappen.</span><span class="sxs-lookup"><span data-stu-id="88264-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="88264-148">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="88264-148">Select **Save changes**.</span></span>
