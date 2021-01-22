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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar Google-filer till Microsoft 365 för företag med hjälp av Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928204"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="4abef-103">Migrera Google-filer till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4abef-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="4abef-104">När du flyttar över till Microsoft 365 för företag bör du migrera dina filer från Google Drive.</span><span class="sxs-lookup"><span data-stu-id="4abef-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="4abef-105">Du kan använda appen Mover för att flytta filer från personliga och delade enheter.</span><span class="sxs-lookup"><span data-stu-id="4abef-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="4abef-106">Mer information finns i [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="4abef-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="4abef-107">Mover gör en kopia av filerna och flyttar kopiorna till Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="4abef-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="4abef-108">De ursprungliga filerna finns också kvar i Google Drives.</span><span class="sxs-lookup"><span data-stu-id="4abef-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4abef-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="4abef-109">Before you start</span></span>

<span data-ttu-id="4abef-110">Alla användare bör ha loggat in på Microsoft 365 för företag och konfigurera onedrive för företag.</span><span class="sxs-lookup"><span data-stu-id="4abef-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="4abef-111">Det gör du genom att [gå till office.com,](https://office.com)logga in med microsft 365 för företag-autentiseringsuppgifter och sedan välja OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4abef-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="4abef-112">Prova!</span><span class="sxs-lookup"><span data-stu-id="4abef-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="4abef-113">Installera Mover</span><span class="sxs-lookup"><span data-stu-id="4abef-113">Install Mover</span></span>

1. <span data-ttu-id="4abef-114">Logga in på administratörskonsolen för Google Workspace [på admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="4abef-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="4abef-115">Välj **Appar,** **Google Workspace Marketplace-appar** och lägg sedan till app i listan **Domäninstallation.**</span><span class="sxs-lookup"><span data-stu-id="4abef-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="4abef-116">Sök efter Mover och markera den.</span><span class="sxs-lookup"><span data-stu-id="4abef-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="4abef-117">Välj **Domäninstallation** och sedan **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="4abef-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="4abef-118">Granska behörigheterna, markera kryssrutan för att godkänna villkoren och välj **sedan** Tillåt, välj **Nästa** och sedan **Klar.**</span><span class="sxs-lookup"><span data-stu-id="4abef-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="4abef-119">Skapa kopplingar och köra migreringen</span><span class="sxs-lookup"><span data-stu-id="4abef-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="4abef-120">Återgå till **Google Workspace Marketplace-appar.**</span><span class="sxs-lookup"><span data-stu-id="4abef-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="4abef-121">Uppdatera webbläsaren och välj **appen Mover.**</span><span class="sxs-lookup"><span data-stu-id="4abef-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="4abef-122">Rulla nedåt och välj den universella navigeringslänken.</span><span class="sxs-lookup"><span data-stu-id="4abef-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="4abef-123">Välj **Auktorisera ny** koppling, **leta upp G Suite (administratör)** och välj **Auktorisera.**</span><span class="sxs-lookup"><span data-stu-id="4abef-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="4abef-124">Ändra **visningsnamnet om** du vill och välj sedan **Godkänn.**</span><span class="sxs-lookup"><span data-stu-id="4abef-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="4abef-125">Välj ett administratörskonto för Google, granska behörigheterna och välj **sedan Tillåt.**</span><span class="sxs-lookup"><span data-stu-id="4abef-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="4abef-126">Mover visar antalet teamenheter och användarenheter som identifierats.</span><span class="sxs-lookup"><span data-stu-id="4abef-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="4abef-127">Under **Välj mål** väljer du Godkänn ny **koppling,** letar reda på Office **365** och väljer **Auktorisera.**</span><span class="sxs-lookup"><span data-stu-id="4abef-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="4abef-128">Om du vill ge behörigheter till Mover-appen i Azure Active Directory går du till [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="4abef-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="4abef-129">Välj **Office 365 Mover,** **Behörigheter,** **Bevilja administratörsmedgivande för ditt företag.**</span><span class="sxs-lookup"><span data-stu-id="4abef-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="4abef-130">Välj ditt konto, granska behörigheterna och välj **Acceptera.**</span><span class="sxs-lookup"><span data-stu-id="4abef-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="4abef-131">Välj **Egenskaper** och kontrollera att **användartilldelning krävs?** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="4abef-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="4abef-132">Gå tillbaka till appen Mover, ändra visningsnamn **,** välj **Godkänn** om du vill och välj sedan ett Microsoft-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="4abef-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="4abef-133">Mover informerar dig om antalet SharePoint Online-webbplatser (eller SPO-webbplatser) och användare som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="4abef-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="4abef-134">Välj **Fortsätt migrering, välj** Lägg till **användare** och sedan Identifiera automatiskt och Lägg **till användare.**</span><span class="sxs-lookup"><span data-stu-id="4abef-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="4abef-135">Appen Mover försöker mappa enheter från källsökvägen i Google till målsökvägen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4abef-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="4abef-136">Om en enhet inte mappas automatiskt lägger du till målsökvägen till en CSV-fil som vi senare använder för att migrera den delade enheten till ett SharePoint-dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="4abef-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="4abef-137">I det här fallet har vi lagt till en SharePoint-webbplats som heter Migrerade filer och antecknat URL-adressen för dokumentsidan.</span><span class="sxs-lookup"><span data-stu-id="4abef-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="4abef-138">Sedan skapade vi en CSV-fil med formatet Källsökväg, Målsökväg och Taggar.</span><span class="sxs-lookup"><span data-stu-id="4abef-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="4abef-139">Mer information finns [i aka.ms/movercsv.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="4abef-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="4abef-140">När du lägger till URL:en för målsökvägen tar du bort allt efter Delade dokument, till exempel fungerar inte den här fullständiga URL:en: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="4abef-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="4abef-141">Ändra den till: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="4abef-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="4abef-142">När CSV-filen är klar väljer **du** Migreringsåtgärder, Lägg till **i migrering,** Välj **en fil att ladda upp.**</span><span class="sxs-lookup"><span data-stu-id="4abef-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="4abef-143">Gå till CSV-filen, markera den och välj sedan **Öppna.**</span><span class="sxs-lookup"><span data-stu-id="4abef-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="4abef-144">Välj den användare som kör de filer du vill migrera och välj sedan **Starta migrering av användare.**</span><span class="sxs-lookup"><span data-stu-id="4abef-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="4abef-145">Granska migreringsinformationen, välj när migreringen ska starta, godkänn **villkoren** och välj sedan **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="4abef-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="4abef-146">Appen Mover meddelar dig när migreringen är klar.</span><span class="sxs-lookup"><span data-stu-id="4abef-146">The Mover app will inform you when the migration process is complete.</span></span>