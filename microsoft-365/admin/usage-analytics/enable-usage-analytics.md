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
description: Lär dig hur du börjar samla in data för din klientorganisation med hjälp av mallappen Microsoft 365 Usage Analytics i Power BI.
ms.openlocfilehash: 386b64b1db15ba9f00450ac037a74bfc702e95ea
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140689"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="d4a11-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="d4a11-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d4a11-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="d4a11-104">The admin center is changing.</span></span> <span data-ttu-id="d4a11-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d4a11-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d4a11-106">Microsoft 365-användningsanalys är också tillgängligt för Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="d4a11-106">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="d4a11-107">Steg för att aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="d4a11-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="d4a11-108">För att komma igång med Microsoft 365-användningsanalys måste du först göra data tillgängliga i Microsoft 365-administrationscentret och sedan starta mallappen i Power BI.</span><span class="sxs-lookup"><span data-stu-id="d4a11-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="d4a11-109">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="d4a11-109">Get Power BI</span></span>

<span data-ttu-id="d4a11-110">Om du inte redan har Power BI kan du [registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="d4a11-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="d4a11-111">Välj **Prova gratis** för att registrera dig för en utvärderingsversion eller Köp **nu** för att få Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="d4a11-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="d4a11-112">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="d4a11-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="d4a11-113">Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp.</span><span class="sxs-lookup"><span data-stu-id="d4a11-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="d4a11-114">Mer information finns i [Förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d4a11-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="d4a11-115">Du behöver en Power BI Pro-licens för att dela ditt innehåll, och de personer du delar det med gör det också, eller så måste innehållet finnas på en arbetsyta med [en Premium-kapacitet.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="d4a11-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="d4a11-116">Aktivera mallappen</span><span class="sxs-lookup"><span data-stu-id="d4a11-116">Enable the template app</span></span>

<span data-ttu-id="d4a11-117">Om du vill aktivera mallappen måste du antingen vara global **administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="d4a11-118">Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4a11-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="d4a11-119">I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.</span><span class="sxs-lookup"><span data-stu-id="d4a11-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="d4a11-120">Leta reda på Microsoft **365-användningsanalyskortet** på sidan **Användning** och välj **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="d4a11-121">På panelen Rapporter som öppnas anger du **Gör data tillgängliga för Microsoft 365-användningsanalys för Power BI** till **På** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="d4a11-p104">Det här initierar datainsamlingsprocessen och tar mellan 2 och 48 timmar att slutföra beroende på storleken på din klientorganisation. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="d4a11-p104">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="d4a11-124">Initiera mallappen</span><span class="sxs-lookup"><span data-stu-id="d4a11-124">Initiate the template app</span></span>

<span data-ttu-id="d4a11-125">Om du vill starta mallappen måste du antingen vara global **administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="d4a11-126">Kopiera klient-ID:et och välj **Gå till Power BI**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="d4a11-127">Logga in när du kommer till Power BI.</span><span class="sxs-lookup"><span data-stu-id="d4a11-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="d4a11-128">Välj Appar->Hämta appar på navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="d4a11-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="d4a11-129">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="d4a11-130">[![Välj Hämta det nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="d4a11-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="d4a11-131">När appen är installerad.</span><span class="sxs-lookup"><span data-stu-id="d4a11-131">Once the app is installed.</span></span> <span data-ttu-id="d4a11-132">Klicka på panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="d4a11-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="d4a11-133">Klicka på **Utforska app** om du vill visa appen med exempeldata.</span><span class="sxs-lookup"><span data-stu-id="d4a11-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="d4a11-134">Klicka på **Anslut** om du vill ansluta appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="d4a11-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="d4a11-135">När du har klickat på **Anslut**skriver du i det klient-ID som du kopierade \> i steg (1) **Nästa**på skärmen **Anslut till Microsoft 365 användningsanalys** .</span><span class="sxs-lookup"><span data-stu-id="d4a11-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="d4a11-136">På nästa skärm väljer du **oAuth2** som **autentiseringsmetod** \> **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="d4a11-137">Om du väljer någon annan autentiseringsmetod misslyckas anslutningen till mallappen.</span><span class="sxs-lookup"><span data-stu-id="d4a11-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="d4a11-139">När mallappen har instansierats är instrumentpanelen för användningsanalys i Microsoft 365 tillgänglig i Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="d4a11-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="d4a11-140">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="d4a11-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="d4a11-141">Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="d4a11-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="d4a11-142">**Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="d4a11-143">Detta påverkar alla rapporter under Användaraktivitet (Se [Navigera och använda rapporterna i Microsoft 365-användningsanalys](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter).</span><span class="sxs-lookup"><span data-stu-id="d4a11-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="d4a11-144">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="d4a11-144">Make the collected data anonymous</span></span>

<span data-ttu-id="d4a11-145">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="d4a11-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="d4a11-146">Detta döljer identifierbar information som användar-, grupp- och webbplatsnamn i rapporter och i mallappen .</span><span class="sxs-lookup"><span data-stu-id="d4a11-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="d4a11-147">Gå till **inställningar** \> **Settings**för inställningar i administrationscentret och välj **Rapporter**under **Fliken Tjänster** .</span><span class="sxs-lookup"><span data-stu-id="d4a11-147">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="d4a11-148">Välj **Rapporter**och välj sedan att **visa anonyma identifierare**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="d4a11-149">Den här inställningen tillämpas både på användningsrapporterna och på mallappen.</span><span class="sxs-lookup"><span data-stu-id="d4a11-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="d4a11-150">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="d4a11-150">Select **Save changes**.</span></span>
