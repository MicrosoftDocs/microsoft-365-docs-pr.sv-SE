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
description: Lär dig hur du börjar samla in data för klientorganisationen med hjälp av mallappen Microsoft 365 Användningsanalys i Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114243"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="8417b-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="8417b-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8417b-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8417b-104">The admin center is changing.</span></span> <span data-ttu-id="8417b-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8417b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="8417b-106">Microsoft 365 användningsanalyser är ännu inte tillgängliga för Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="8417b-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="8417b-107">Steg för att aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="8417b-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="8417b-108">För att komma igång med Microsoft 365 användningsanalyser måste du först göra data tillgängliga i administrationscentret för Microsoft 365 och sedan starta mallappen i Power BI.</span><span class="sxs-lookup"><span data-stu-id="8417b-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="8417b-109">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="8417b-109">Get Power BI</span></span>

<span data-ttu-id="8417b-110">Om du inte redan har Power BI kan du [registrera dig för Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="8417b-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="8417b-111">Välj **Prova gratis** för att registrera dig för en utvärderingsversion eller Köp **nu** för att skaffa Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="8417b-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="8417b-112">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="8417b-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="8417b-113">Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp.</span><span class="sxs-lookup"><span data-stu-id="8417b-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="8417b-114">Mer information finns i [Förutsättningarna.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="8417b-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="8417b-115">Om du vill dela dina data måste både du och de personer som du delar data med ha en Power BI Pro-licens, eller så måste innehållet finnas på en arbetsyta i en [Power BI Premium-tjänst.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="8417b-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="8417b-116">Aktivera mallappen</span><span class="sxs-lookup"><span data-stu-id="8417b-116">Enable the template app</span></span>

<span data-ttu-id="8417b-117">Du måste vara global administratör för att kunna aktivera **mallappen.**</span><span class="sxs-lookup"><span data-stu-id="8417b-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="8417b-118">Mer information [finns i artikeln om](../add-users/about-admin-roles.md) administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="8417b-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="8417b-119">I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.</span><span class="sxs-lookup"><span data-stu-id="8417b-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="8417b-120">Leta upp **Microsoft** **365** användningsanalyskortet på sidan Användning och välj **Kom igång.**</span><span class="sxs-lookup"><span data-stu-id="8417b-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="8417b-121">På panelen Rapporter som öppnas ställer du in **Gör data tillgängliga för Microsoft 365 användningsanalyser för Power BI** till **Spara.** \> </span><span class="sxs-lookup"><span data-stu-id="8417b-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="8417b-122">Datainsamlingsprocessen slutförs om två till 48 timmar beroende på klientorganisationens storlek.</span><span class="sxs-lookup"><span data-stu-id="8417b-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="8417b-123">Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="8417b-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="8417b-124">Starta mallappen</span><span class="sxs-lookup"><span data-stu-id="8417b-124">Start the template app</span></span>

<span data-ttu-id="8417b-125">För att kunna starta mallappen måste du vara global **administratör,** **rapportläsare,** **Exchange-administratör,** Skype för företag-administratör eller **SharePoint-administratör.** </span><span class="sxs-lookup"><span data-stu-id="8417b-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="8417b-126">Kopiera klientorganisations-ID:t **och välj Gå till Power BI.**</span><span class="sxs-lookup"><span data-stu-id="8417b-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="8417b-127">Logga in när du kommer till Power BI.</span><span class="sxs-lookup"><span data-stu-id="8417b-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="8417b-128">Välj **sedan** -> **Appar– hämta appar** från navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="8417b-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="8417b-129">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="8417b-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="8417b-130">[![Välj Skaffa nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="8417b-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="8417b-131">När appen har installerats.</span><span class="sxs-lookup"><span data-stu-id="8417b-131">Once the app is installed.</span></span> <span data-ttu-id="8417b-132">Välj panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="8417b-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="8417b-133">Välj **Utforska app** för att visa appen med exempeldata.</span><span class="sxs-lookup"><span data-stu-id="8417b-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="8417b-134">Välj **Anslut** för att ansluta appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="8417b-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="8417b-135">Välj **Anslut** på skärmen Anslut till **Microsoft 365** användningsanalyser, skriv sedan in klientorganisations-ID:t (utan streck) som du kopierade i steg (1) och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="8417b-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="8417b-136">På nästa skärm väljer du **OAuth2** som **inloggningsmetod för** \> **autentisering.**</span><span class="sxs-lookup"><span data-stu-id="8417b-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="8417b-137">Om du väljer någon annan autentiseringsmetod kommer anslutningen till mallappen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="8417b-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Välj Microsoft-konto som autentiseringsmetod](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="8417b-139">Efter att mallappen instansierats blir instrumentpanelen för Microsoft 365 användningsanalyser tillgänglig i Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="8417b-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="8417b-140">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="8417b-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="8417b-141">Sammanställningar på klientorganisationsnivå blir tillgängliga i alla rapporter efter att du har valt att delta.</span><span class="sxs-lookup"><span data-stu-id="8417b-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="8417b-142">**Information på användarnivå blir bara tillgänglig runt den 5:e i nästa kalendermånad efter att du har anmäla dig.**</span><span class="sxs-lookup"><span data-stu-id="8417b-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="8417b-143">Det här påverkar alla rapporter under Användaraktivitet (se Navigera och använd rapporterna i [Microsoft 365](navigate-and-utilize-reports.md) användningsanalyser för tips om hur du visar och använder rapporterna).</span><span class="sxs-lookup"><span data-stu-id="8417b-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="8417b-144">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="8417b-144">Make the collected data anonymous</span></span>

<span data-ttu-id="8417b-145">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="8417b-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="8417b-146">Det här innebär att identifierbar information som användare, grupp och webbplatsnamn i rapporter och mallappen döljs.</span><span class="sxs-lookup"><span data-stu-id="8417b-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="8417b-147">Gå till inställningar för organisationens **inställningar** i \> **administrationscentret** och välj Rapporter under fliken **Tjänster.** </span><span class="sxs-lookup"><span data-stu-id="8417b-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="8417b-148">Välj **Rapporter** och välj sedan att visa **anonyma identifierare.**</span><span class="sxs-lookup"><span data-stu-id="8417b-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="8417b-149">Den här inställningen tillämpas både på användningsrapporterna och på mallappen.</span><span class="sxs-lookup"><span data-stu-id="8417b-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="8417b-150">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="8417b-150">Select **Save changes**.</span></span>
