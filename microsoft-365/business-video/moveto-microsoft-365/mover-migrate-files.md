---
title: 'Migrera Google-filer till Microsoft 365 för företag '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med hjälp av Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913580"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="5a1fd-103">Migrera Google-filer till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5a1fd-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="5a1fd-104">När du flyttar över till Microsoft 365 för företag ska du migrera dina filer från Google Drive.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="5a1fd-105">Du kan använda appen Mover för att flytta filer från personliga och delade enheter.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="5a1fd-106">Mer information finns i [Mover Cloud Migration.](/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="5a1fd-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="5a1fd-107">Mover gör en kopia av filerna och flyttar kopiorna till Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="5a1fd-108">De ursprungliga filerna finns även kvar i Google Drives.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5a1fd-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="5a1fd-109">Before you start</span></span>

<span data-ttu-id="5a1fd-110">Alla användare bör ha loggat in på Microsoft 365 för företag och konfigurera onedrive för företag.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="5a1fd-111">Det gör du genom att [gå office.com](https://office.com), logga in med dina autentiseringsuppgifter för Microsoft 365 för företag och sedan välja OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="5a1fd-112">Prova!</span><span class="sxs-lookup"><span data-stu-id="5a1fd-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="5a1fd-113">Installera Mover</span><span class="sxs-lookup"><span data-stu-id="5a1fd-113">Install Mover</span></span>

1. <span data-ttu-id="5a1fd-114">Logga in på administratörskonsolen för Google Workspace [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="5a1fd-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="5a1fd-115">Välj **Appar Google** Workspace  >  **Marketplace-appar Lägg** till app i listan För installation av  >  **domän**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="5a1fd-116">Sök efter Mover och markera den.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="5a1fd-117">Välj **Domäninstallation** och sedan **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="5a1fd-118">Granska behörigheterna, markera kryssrutan för att godkänna villkoren och välj sedan **Tillåt**, välj **Nästa** och sedan **Klar**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="5a1fd-119">Skapa kopplingar och köra migreringen</span><span class="sxs-lookup"><span data-stu-id="5a1fd-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="5a1fd-120">Återgå till **Google Workspace Marketplace-appar**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="5a1fd-121">Uppdatera webbläsaren och välj **appen Mover.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="5a1fd-122">Rulla nedåt och välj den universella navigeringslänken.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="5a1fd-123">Välj **Auktorisera ny** anslutning , **leta reda på G Suite (administratör)** och välj **Auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="5a1fd-124">Om du **vill kan** du ändra visningsnamnet och sedan **välja Godkänn.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="5a1fd-125">Välj ett Google-administratörskonto, granska behörigheterna och välj sedan **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="5a1fd-126">Mover visar antalet teamenheter och användare kör den upptäckt.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="5a1fd-127">Välj **Auktorisera** ny **koppling under Välj** destination , leta reda på Office **365** och välj **Auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="5a1fd-128">Om du vill ge behörigheter till mover-appen i Azure Active Directory går du till [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="5a1fd-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="5a1fd-129">Välj **Office 365 Mover**, **Behörigheter**, **Bevilja administratörsmedgivande för ditt företag**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="5a1fd-130">Välj ditt konto, granska behörigheterna och välj **Acceptera**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="5a1fd-131">Välj **Egenskaper** och kontrollera att **Användartilldelning krävs?** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="5a1fd-132">Gå tillbaka till appen Mover, ändra **visningsnamnet**, om du vill, välj **Auktorisera** och välj sedan ett Microsoft-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="5a1fd-133">Mover informerar dig om antalet SharePoint Online-webbplatser (eller SPO-webbplatser) och användare som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="5a1fd-134">Välj **Fortsätt migreringskonfiguration**, välj **Lägg till användare** och sedan Upptäck och lägg till användare **automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="5a1fd-135">Appen Mover försöker mappa enheter från källsökvägen i Google till målsökvägen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="5a1fd-136">Om en enhet inte mappas automatiskt lägger du till dess målsökväg i en CSV-fil, som vi använder senare för att migrera den delade enheten till ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="5a1fd-137">I det här fallet har vi lagt till en SharePoint-webbplats som kallas Migrerade filer och antecknat URL-adressen för dokumentsidan.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="5a1fd-138">Sedan skapade vi en CSV-fil med formatet Källsökväg, Målsökväg och Taggar.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="5a1fd-139">Mer information finns [i aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="5a1fd-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="5a1fd-140">När du lägger till URL:en för målsökväg tar du bort allt efter Delade dokument.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="5a1fd-141">Den här fullständiga URL:en fungerar till exempel inte: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="5a1fd-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="5a1fd-142">Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="5a1fd-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="5a1fd-143">När CSV-filen är klar väljer du **Migreringsåtgärder , Lägg** **till i migrering**, Välj en fil att ladda **upp.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="5a1fd-144">Navigera till CSV-filen, markera den och välj **öppna**.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="5a1fd-145">Välj den användare som kör de filer du vill migrera och välj **sedan Starta migrering av användare.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="5a1fd-146">Granska migreringsinformationen, välj när migreringen ska starta, godkänn **villkoren och** välj sedan **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5a1fd-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="5a1fd-147">Du får ett meddelande i appen Mover när migreringsprocessen är klar.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-147">The Mover app will inform you when the migration process is complete.</span></span>