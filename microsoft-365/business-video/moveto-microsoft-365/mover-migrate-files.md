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
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med flytt firman.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794701"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="af55b-103">Migrera Google-filer till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="af55b-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="af55b-104">När du flyttar till Microsoft 365 för företag ska du migrera dina filer från Google Drive.</span><span class="sxs-lookup"><span data-stu-id="af55b-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="af55b-105">Du kan använda appen kraft för att flytta filer från personliga och delade enheter.</span><span class="sxs-lookup"><span data-stu-id="af55b-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="af55b-106">Mer information finns i [migrera moln migrering](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="af55b-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="af55b-107">En kopia av filerna kopieras och kopiorna flyttas till Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="af55b-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="af55b-108">Originalfilerna sparas också i Google Drives.</span><span class="sxs-lookup"><span data-stu-id="af55b-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="af55b-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="af55b-109">Before you start</span></span>

<span data-ttu-id="af55b-110">Alla användare ska ha loggat in på Microsoft 365 för företag och ställa in sin OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="af55b-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="af55b-111">Det gör du genom att gå till [Office.com](https://office.com), logga in med ditt Microsft 365 för företag-autentiseringsuppgifter och sedan välja OneDrive.</span><span class="sxs-lookup"><span data-stu-id="af55b-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="af55b-112">Prova!</span><span class="sxs-lookup"><span data-stu-id="af55b-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="af55b-113">Installera flyttat</span><span class="sxs-lookup"><span data-stu-id="af55b-113">Install Mover</span></span>

1. <span data-ttu-id="af55b-114">Logga in på din Google Workspace-administratörskonsolen på [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="af55b-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="af55b-115">Välj **appar**, **Google Workspace Marketplace-appar** och **Lägg sedan till program i domän installations listan**.</span><span class="sxs-lookup"><span data-stu-id="af55b-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="af55b-116">Leta efter flytt firman och välj den.</span><span class="sxs-lookup"><span data-stu-id="af55b-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="af55b-117">Välj **Domain install** och sedan **Continue**.</span><span class="sxs-lookup"><span data-stu-id="af55b-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="af55b-118">Granska behörigheterna, markera kryss rutan för att godkänna villkoren och välj sedan **Tillåt**, Välj **Nästa** och sedan **färdig**.</span><span class="sxs-lookup"><span data-stu-id="af55b-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="af55b-119">Skapa kopplingar och kör migreringen</span><span class="sxs-lookup"><span data-stu-id="af55b-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="af55b-120">Återvänd till **Google Workspace Marketplace-appar**.</span><span class="sxs-lookup"><span data-stu-id="af55b-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="af55b-121">Uppdatera webbläsaren och välj programmet **Flytta** .</span><span class="sxs-lookup"><span data-stu-id="af55b-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="af55b-122">Bläddra nedåt och välj den universella navigerings länken.</span><span class="sxs-lookup"><span data-stu-id="af55b-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="af55b-123">Välj **Godkänn ny koppling**, leta reda på **G Suite (administratör)** och välj **auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="af55b-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="af55b-124">Ändra **visnings namnet**, om du vill och välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="af55b-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="af55b-125">Välj ett Google admin-konto, granska behörigheterna och välj sedan **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="af55b-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="af55b-126">Kraft Drive visar antalet grupp enheter och användar enheter som identifieras.</span><span class="sxs-lookup"><span data-stu-id="af55b-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="af55b-127">Under **Välj mål** väljer du **Godkänn ny koppling**, letar reda på **Office 365** och väljer **auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="af55b-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="af55b-128">Om du vill ge behörighet till programmet flytta i din Azure Active Directory navigerar du till [aka.MS/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="af55b-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="af55b-129">Välj **Office 365 flytt firma**, **behörigheter**, **bevilja administratörs medgivande för ditt företag**.</span><span class="sxs-lookup"><span data-stu-id="af55b-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="af55b-130">Välj ditt konto, granska behörigheterna och välj **acceptera**.</span><span class="sxs-lookup"><span data-stu-id="af55b-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="af55b-131">Välj **Egenskaper** och kontrol lera att **användar tilldelning krävs?** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="af55b-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="af55b-132">Gå tillbaka till programmet kraft, ändra **visnings namnet** om du vill, Välj **Godkänn** och välj sedan ett Microsoft administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="af55b-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="af55b-133">Med den här funktionen får du information om antalet SharePoint Online-webbplatser (eller SPO) och användare som identifieras.</span><span class="sxs-lookup"><span data-stu-id="af55b-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="af55b-134">Välj **Fortsätt migreringen**, Välj **Lägg till användare** och **Upptäck och Lägg sedan till användare automatiskt**.</span><span class="sxs-lookup"><span data-stu-id="af55b-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="af55b-135">Programmet kör automatiskt försöker mappa enheter från käll Sök vägen i Google till mål Sök vägen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af55b-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="af55b-136">Om en enhet inte mappas automatiskt lägger du till mål Sök vägen till en CSV-fil som du senare kommer att använda för att migrera den delade enheten till ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="af55b-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="af55b-137">I det här fallet har vi lagt till en SharePoint-webbplats som heter migrerade filer och noterat URL-adressen till sidan dokument.</span><span class="sxs-lookup"><span data-stu-id="af55b-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="af55b-138">En CSV-fil skapas sedan med käll Sök vägens format, mål Sök väg och taggar.</span><span class="sxs-lookup"><span data-stu-id="af55b-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="af55b-139">Mer information finns i [aka.MS/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="af55b-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="af55b-140">När du lägger till URL-adressen för mål Sök vägen tar du bort allt efter delade dokument, till exempel att denna fullständiga URL inte fungerar: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="af55b-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="af55b-141">Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="af55b-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="af55b-142">När CSV-filen är klar väljer du **migreringsåtgärder**, **lägger till i migrering**, **väljer en fil som ska laddas upp**.</span><span class="sxs-lookup"><span data-stu-id="af55b-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="af55b-143">Gå till CSV-filen, markera den och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="af55b-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="af55b-144">Markera de användar enheter vars filer du vill migrera och välj sedan **Starta migrering av användare**.</span><span class="sxs-lookup"><span data-stu-id="af55b-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="af55b-145">Granska migrations informationen, Välj när du vill starta migreringen, Godkänn **villkoren och** Välj sedan **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="af55b-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="af55b-146">Programmet flytta över dig när migreringen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="af55b-146">The Mover app will inform you when the migration process is complete.</span></span>