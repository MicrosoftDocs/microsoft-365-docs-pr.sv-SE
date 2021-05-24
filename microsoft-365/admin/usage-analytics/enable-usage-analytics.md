---
title: Aktivera Microsoft 365 användningsanalyser
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du börjar samla in data för klientorganisationen med hjälp Microsoft 365 mallappen för användningsanalys i Power BI.
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635420"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="d4821-103">Aktivera Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="d4821-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="d4821-104">Microsoft 365 användningsanalys är ännu inte tillgängligt för Microsoft 365 Government Community i USA.</span><span class="sxs-lookup"><span data-stu-id="d4821-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d4821-105">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d4821-105">Before you begin</span></span>

<span data-ttu-id="d4821-106">För att komma Microsoft 365 användningsanalys måste du först göra data tillgängliga i administrationscentret för Microsoft 365 och sedan starta mallappen i Power BI.</span><span class="sxs-lookup"><span data-stu-id="d4821-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
## <a name="get-power-bi"></a><span data-ttu-id="d4821-107">Hämta Power BI</span><span class="sxs-lookup"><span data-stu-id="d4821-107">Get Power BI</span></span>

<span data-ttu-id="d4821-108">Om du inte redan har ett Power BI kan du [registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="d4821-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="d4821-109">Välj **Prova gratis** för att registrera dig för en utvärderingsversion, eller Köp **nu** för att få Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="d4821-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="d4821-110">Du kan också öppna **Produkter** och köpa en version av Power BI.</span><span class="sxs-lookup"><span data-stu-id="d4821-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="d4821-111">Du behöver en Power BI Pro för att installera, anpassa och distribuera en mallapp.</span><span class="sxs-lookup"><span data-stu-id="d4821-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="d4821-112">Mer information finns i [Krav](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d4821-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="d4821-113">Om du vill dela dina data måste både du och de personer som du delar data med, en Power BI Pro-licens eller innehållet vara på en arbetsyta i en [Power BI premium-tjänst.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="d4821-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
## <a name="enable-the-template-app"></a><span data-ttu-id="d4821-114">Aktivera mallappen</span><span class="sxs-lookup"><span data-stu-id="d4821-114">Enable the template app</span></span>

<span data-ttu-id="d4821-115">Du måste vara global administratör för att kunna aktivera **mallappen.**</span><span class="sxs-lookup"><span data-stu-id="d4821-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="d4821-116">Mer information [finns i om](../add-users/about-admin-roles.md) administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="d4821-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="d4821-117">I administrationscentret går du till fliken **Inställningar** \> **Tjänster för** \> **organisationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="d4821-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span> 
    
2. <span data-ttu-id="d4821-118">Välj **Rapporter** på fliken **Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="d4821-118">On the **Services** tab, select  **Reports**.</span></span>
    
3. <span data-ttu-id="d4821-119">I panelen Rapporter som öppnas ställer du in **Gör rapportdata tillgängliga för** användning Microsoft 365 användningsanalys för Power BI till **Spara.** \> </span><span class="sxs-lookup"><span data-stu-id="d4821-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="d4821-120">Datainsamlingsprocessen slutförs om två till 48 timmar beroende på klientorganisationens storlek.</span><span class="sxs-lookup"><span data-stu-id="d4821-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="d4821-121">Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar.</span><span class="sxs-lookup"><span data-stu-id="d4821-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
## <a name="start-the-template-app"></a><span data-ttu-id="d4821-122">Starta mallappen</span><span class="sxs-lookup"><span data-stu-id="d4821-122">Start the template app</span></span>

<span data-ttu-id="d4821-123">För att kunna starta mallappen måste du vara antingen **global** administratör , **rapportläsare,** **Exchange administratör**, **Skype för företag** administratör eller **SharePoint administratör**.</span><span class="sxs-lookup"><span data-stu-id="d4821-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="d4821-124">Kopiera klientorganisations-ID:t **och välj Gå till Power BI**.</span><span class="sxs-lookup"><span data-stu-id="d4821-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="d4821-125">När du kommer till Power BI loggar du in.</span><span class="sxs-lookup"><span data-stu-id="d4821-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="d4821-126">Välj **sedan Appar** Hämta -> **appar** från navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="d4821-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="d4821-127">I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.</span><span class="sxs-lookup"><span data-stu-id="d4821-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="d4821-128">[![Välj Skaffa nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="d4821-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="d4821-129">När appen är installerad.</span><span class="sxs-lookup"><span data-stu-id="d4821-129">Once the app is installed.</span></span> <span data-ttu-id="d4821-130">Välj panelen för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="d4821-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="d4821-131">Välj **Utforska app** för att visa appen med exempeldata.</span><span class="sxs-lookup"><span data-stu-id="d4821-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="d4821-132">Välj **Anslut** vill ansluta appen till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="d4821-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="d4821-133">Välj **Anslut** på skärmen **Anslut** för Microsoft 365 användningsanalys och skriv sedan det klientorganisations-ID (utan streck) som du kopierade i steg (1) och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d4821-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="d4821-134">På nästa skärm väljer du **OAuth2** som **inloggningsmetod för** \> **autentisering**.</span><span class="sxs-lookup"><span data-stu-id="d4821-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="d4821-135">Om du väljer någon annan autentiseringsmetod kommer anslutningen till mallappen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="d4821-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Välj Microsoft-konto som autentiseringsmetod](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="d4821-137">Efter att mallappen har instansierats Microsoft 365 instrumentpanel för användningsanalyser att bli tillgänglig Power BI på webben.</span><span class="sxs-lookup"><span data-stu-id="d4821-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="d4821-138">Första inläsningen av instrumentpanelen tar 2 till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="d4821-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="d4821-139">Sammanställningar på klientorganisationsnivå blir tillgängliga i alla rapporter efter att du har valt att delta.</span><span class="sxs-lookup"><span data-stu-id="d4821-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="d4821-140">**Information på användarnivå blir bara tillgänglig runt den 5:e i nästa kalendermånad efter att du har valt .**</span><span class="sxs-lookup"><span data-stu-id="d4821-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="d4821-141">Det här påverkar alla rapporter under Användaraktivitet (se Navigera och använd rapporter i [Microsoft 365 användningsanalys](navigate-and-utilize-reports.md) för tips om hur du visar och använder rapporterna).</span><span class="sxs-lookup"><span data-stu-id="d4821-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="d4821-142">Gör insamlade data anonyma</span><span class="sxs-lookup"><span data-stu-id="d4821-142">Make the collected data anonymous</span></span>

<span data-ttu-id="d4821-143">Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter.</span><span class="sxs-lookup"><span data-stu-id="d4821-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="d4821-144">Det här innebär att identifierbar information som användare, grupp och webbplatsnamn i rapporter och mallappen döljs.</span><span class="sxs-lookup"><span data-stu-id="d4821-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="d4821-145">I administrationscentret går du till fliken **Inställningar** \> **organisation Inställningar** och under fliken **Tjänster** väljer du **Rapporter**.</span><span class="sxs-lookup"><span data-stu-id="d4821-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="d4821-146">Välj **Rapporter** och välj sedan Visa **anonyma identifierare**.</span><span class="sxs-lookup"><span data-stu-id="d4821-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="d4821-147">Den här inställningen används både på användningsrapporterna och på mallappen.</span><span class="sxs-lookup"><span data-stu-id="d4821-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="d4821-148">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="d4821-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="d4821-149">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="d4821-149">Related content</span></span>

<span data-ttu-id="d4821-150">[Om användningsanalyser](usage-analytics.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d4821-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="d4821-151">[Hämta den senaste versionen av användningsanalys](get-the-latest-version-of-usage-analytics.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d4821-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="d4821-152">[Navigera och använda rapporter i Microsoft 365 användningsanalys](navigate-and-utilize-reports.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d4821-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>