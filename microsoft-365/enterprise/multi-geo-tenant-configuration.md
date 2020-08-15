---
title: Microsoft 365 multi-geo-klient konfiguration
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: I den här artikeln lär du dig hur du lägger till satellit platser och konfigurerar klient organisationen för Microsoft 365 multi-geo.
ms.openlocfilehash: 4276d8ff70fed99e74f2cbab29386c81da06d17b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694480"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="897db-103">Microsoft 365 multi-geo-klient konfiguration</span><span class="sxs-lookup"><span data-stu-id="897db-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="897db-104">Innan du konfigurerar klient organisationen för Microsoft 365 multi-geo bör du se till att du har Läs [plan för microsoft 365 multi-geo](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="897db-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="897db-105">För att följa anvisningarna i den här artikeln behöver du en lista över de geo-platser som du vill aktivera som satellit platser och vilka test användare som du vill etablera för dessa platser.</span><span class="sxs-lookup"><span data-stu-id="897db-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="897db-106">Lägga till multi-geo-funktioner i ditt Microsoft 365-abonnemang till klient organisationen</span><span class="sxs-lookup"><span data-stu-id="897db-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="897db-107">För att använda Microsoft 365 multi-geo måste du ha _flera geo-funktioner i Microsoft 365_ -abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="897db-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="897db-108">Arbeta med ditt konto team för att lägga till det här abonnemanget i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="897db-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="897db-109">Ditt konto team ansluter dig med rätt licensierings specialist och får din klient organisation konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="897db-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="897db-110">Observera att _multi-geo-funktionerna i Microsoft 365_ -abonnemanget är en tjänst plan på användar nivå.</span><span class="sxs-lookup"><span data-stu-id="897db-110">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan.</span></span> <span data-ttu-id="897db-111">Du behöver en licens för varje användare som du vill ha på en satellit plats.</span><span class="sxs-lookup"><span data-stu-id="897db-111">You need a license for each user that you want to host in a satellite location.</span></span> <span data-ttu-id="897db-112">Du kan lägga till fler licenser under tiden när du lägger till användare på satellit platser.</span><span class="sxs-lookup"><span data-stu-id="897db-112">You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="897db-113">När din klient organisation har etablerats med  _flera geo-funktioner i Microsoft 365_ -abonnemang blir fliken **geo platser** tillgängliga i administrations centret för OneDrive och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="897db-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="897db-114">Lägga till satellit platser till din klient organisation</span><span class="sxs-lookup"><span data-stu-id="897db-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="897db-115">Du måste lägga till en satellit plats för varje Geo-plats där du vill lagra data.</span><span class="sxs-lookup"><span data-stu-id="897db-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="897db-116">Tillgängliga geo-platser visas i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="897db-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Skärm bild av sidan geo locations i administrations centret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="897db-118">Lägga till en satellit plats</span><span class="sxs-lookup"><span data-stu-id="897db-118">To add a satellite location</span></span>

1. <span data-ttu-id="897db-119">Öppna SharePoint Online Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="897db-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="897db-120">Gå till fliken **geo platser** .</span><span class="sxs-lookup"><span data-stu-id="897db-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="897db-121">Klicka på **Lägg till plats**.</span><span class="sxs-lookup"><span data-stu-id="897db-121">Click **Add location**.</span></span>

4. <span data-ttu-id="897db-122">Välj den plats du vill lägga till och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="897db-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="897db-123">Skriv den domän som du vill använda med geo platsen och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="897db-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="897db-124">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="897db-124">Click **Close**.</span></span>

<span data-ttu-id="897db-125">Etableringen kan ta från några timmar upp till 72 timmar, beroende på innehavarens storlek.</span><span class="sxs-lookup"><span data-stu-id="897db-125">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant.</span></span> <span data-ttu-id="897db-126">När etableringen av en satellit plats har genomförts får du ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="897db-126">Once provisioning of a satellite location has completed, you will receive an email confirmation.</span></span> <span data-ttu-id="897db-127">När den nya geo-platsen visas i blått på kartan på fliken **geo locations** i administrations centret för OneDrive kan du fortsätta med att ange användarens önskade data plats till den geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="897db-127">When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="897db-128">Din nya satellit plats konfigureras med standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="897db-128">Your new satellite location will be set up with default settings.</span></span> <span data-ttu-id="897db-129">Detta gör att du kan konfigurera den satellit platsen efter behov.</span><span class="sxs-lookup"><span data-stu-id="897db-129">This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="897db-130">Ange användarens förvalda plats</span><span class="sxs-lookup"><span data-stu-id="897db-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="897db-131">När du aktiverar de satellitiska platserna kan du uppdatera dina användar konton så att de använder lämplig data plats.</span><span class="sxs-lookup"><span data-stu-id="897db-131">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location.</span></span> <span data-ttu-id="897db-132">Vi rekommenderar att du anger en vald plats för varje användare, även om användaren befinner sig på Central platsen.</span><span class="sxs-lookup"><span data-stu-id="897db-132">We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="897db-133">Om en användares önskade data plats är inställt på en plats som inte har kon figurer ATS som en satellit plats eller central plats kommer systemet att standardiseras till den centrala platsen när du konfigurerar OneDrive-och SharePoint-webbplatser och grupp post lådor.</span><span class="sxs-lookup"><span data-stu-id="897db-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="897db-134">Vi rekommenderar att du påbörjar verifiering med en test användare eller en liten grupp användare innan du rullar ut multi-geo till din bredare organisation.</span><span class="sxs-lookup"><span data-stu-id="897db-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="897db-135">I Azure Active Directory (Azure AD) finns det två typer av användar objekt: endast molnbaserade användare och synkroniserade användare.</span><span class="sxs-lookup"><span data-stu-id="897db-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="897db-136">Följ instruktionerna för din typ av användare.</span><span class="sxs-lookup"><span data-stu-id="897db-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="897db-137">Synkronisera användarens önskade data plats med Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="897db-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="897db-138">Om företagets användare synkroniseras från ett lokalt Active Directory-system till Azure AD måste deras PreferredDataLocation vara ifyllda i AD och synkroniseras till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="897db-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="897db-139">Följ processen i [Azure Active Directory Connect-synkronisering: konfigurera önskad data plats för Microsoft 365-resurser](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) för att konfigurera den önskade synkroniseringen av data platsen från din lokala Active Directory Domain Services (AD DS) till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="897db-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="897db-140">Vi rekommenderar att du anger användarens önskade data plats som en del av standard arbets flödet för skapande av användare.</span><span class="sxs-lookup"><span data-stu-id="897db-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="897db-141">För nya användare som inte har OneDrive etablerad kan du vänta minst 24 timmar efter att en användares PDL synkroniserats till Azure AD för att ändringarna ska spridas innan användaren loggar in på OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="897db-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="897db-142">(Om du anger önskad data plats innan användaren loggar in för att etablera sin OneDrive för företag säkerställs att användarens nya OneDrive etableras på rätt plats.)</span><span class="sxs-lookup"><span data-stu-id="897db-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="897db-143">Ange önskad data plats för endast molnet</span><span class="sxs-lookup"><span data-stu-id="897db-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="897db-144">Om företagets användare inte synkroniseras från ett lokalt Active Directory-system till Azure AD, vilket innebär att de skapas i Microsoft 365 eller Azure AD, måste PDL ställas in med Microsoft Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="897db-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="897db-145">Procedurerna i det här avsnittet kräver [Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span><span class="sxs-lookup"><span data-stu-id="897db-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="897db-146">Om du redan har den här modulen installerad, se till att uppdatera till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="897db-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="897db-147">[Anslut och logga](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) in med en uppsättning globala administratörs uppgifter för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="897db-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="897db-148">Använd cmdleten [set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) för att ange den önskade data platsen för varje användare.</span><span class="sxs-lookup"><span data-stu-id="897db-148">Use the [Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users.</span></span> <span data-ttu-id="897db-149">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="897db-149">For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="897db-150">Du kan kontrol lera att den önskade data platsen har uppdaterats korrekt med cmdleten Get-MsolUser.</span><span class="sxs-lookup"><span data-stu-id="897db-150">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet.</span></span> <span data-ttu-id="897db-151">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="897db-151">For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Skärm bild av PowerShell-fönstret med set-MsolUser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="897db-153">Vi rekommenderar att du anger användarens önskade data plats som en del av standard arbets flödet för skapande av användare.</span><span class="sxs-lookup"><span data-stu-id="897db-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="897db-154">För nya användare som inte har OneDrive etablerad väntar du minst 24 timmar efter att en användares PDL har ställts in för att ändringarna ska spridas innan användaren loggar in på OneDrive.</span><span class="sxs-lookup"><span data-stu-id="897db-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="897db-155">(Om du anger önskad data plats innan användaren loggar in för att etablera sin OneDrive för företag säkerställs att användarens nya OneDrive etableras på rätt plats.)</span><span class="sxs-lookup"><span data-stu-id="897db-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="897db-156">OneDrive-etablering och effekten av PDL</span><span class="sxs-lookup"><span data-stu-id="897db-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="897db-157">Om användaren redan har en OneDrive-webbplats skapad i klient organisationen, flyttas inte deras befintliga OneDrive automatiskt.</span><span class="sxs-lookup"><span data-stu-id="897db-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="897db-158">Information om hur du flyttar en användares OneDrive finns i [för OneDrive för företag – för flytt](move-onedrive-between-geo-locations.md) Följ instruktionerna i flytta OneDrive mellan geo platser.</span><span class="sxs-lookup"><span data-stu-id="897db-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md) please follow the instructions in Moving OneDrive between geo locations.</span></span> <span data-ttu-id="897db-159">(Observera att användarens Exchange-postlåda flyttas automatiskt när du ställer in användarens PDL.)</span><span class="sxs-lookup"><span data-stu-id="897db-159">(Note that the user's Exchange mailbox does move automatically when you set the user's PDL.)</span></span>

<span data-ttu-id="897db-160">Om användaren inte har en OneDrive-webbplats i klient organisationen tillhandahålls OneDrive för dem i enlighet med deras PDL-värde, under antagandet att användaren matchar ett av företagets satellit platser.</span><span class="sxs-lookup"><span data-stu-id="897db-160">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="897db-161">Konfigurera multi-geo-sökning</span><span class="sxs-lookup"><span data-stu-id="897db-161">Configuring Multi-Geo search</span></span>

<span data-ttu-id="897db-162">Din multi-geo-klient har aggregerade Sök funktioner som gör att Sök frågor kan returnera resultat från valfri plats inom innehavaren.</span><span class="sxs-lookup"><span data-stu-id="897db-162">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="897db-163">Som standard returnerar sökningar från dessa start punkter sammansatta resultat, även om varje Sök index finns inom dess relevanta Geo-plats:</span><span class="sxs-lookup"><span data-stu-id="897db-163">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="897db-164">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="897db-164">OneDrive for Business</span></span>

- <span data-ttu-id="897db-165">Delve</span><span class="sxs-lookup"><span data-stu-id="897db-165">Delve</span></span>

- <span data-ttu-id="897db-166">Start sidan för SharePoint</span><span class="sxs-lookup"><span data-stu-id="897db-166">SharePoint Home</span></span>

- <span data-ttu-id="897db-167">Sök Center</span><span class="sxs-lookup"><span data-stu-id="897db-167">Search Center</span></span>

<span data-ttu-id="897db-168">Dessutom kan flera geo-Sök funktioner konfigureras för dina anpassade Sök program som använder SharePoint Search API.</span><span class="sxs-lookup"><span data-stu-id="897db-168">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="897db-169">Läs igenom [Konfigurera Sök efter OneDrive för företag multi-geo](configure-search-for-multi-geo.md) för instruktioner, inklusive begränsningar och skillnader.</span><span class="sxs-lookup"><span data-stu-id="897db-169">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="897db-170">Verifiera Microsoft 365 multi-geo-konfigurationen</span><span class="sxs-lookup"><span data-stu-id="897db-170">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="897db-171">Nedan följer några grundläggande användnings fall som du kanske vill ta med i verifierings planen innan du kan lansera Microsoft 365 multi-geo för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="897db-171">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="897db-172">När du har slutfört de här testerna och eventuella andra användnings fall som är relevanta för ditt företag kan du välja att gå vidare till att lägga till användarna i den första pilot gruppen.</span><span class="sxs-lookup"><span data-stu-id="897db-172">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="897db-173">**OneDrive för företag**</span><span class="sxs-lookup"><span data-stu-id="897db-173">**OneDrive for Business**</span></span>

<span data-ttu-id="897db-174">Välj OneDrive från Microsoft 365-Start programmet och bekräfta att du dirigeras automatiskt till rätt Geo-plats för användaren, baserat på användarens PDL.</span><span class="sxs-lookup"><span data-stu-id="897db-174">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="897db-175">OneDrive för företag ska nu börja etablera på den platsen.</span><span class="sxs-lookup"><span data-stu-id="897db-175">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="897db-176">När du har etablerat det kan du försöka ladda upp och ladda ned vissa dokument.</span><span class="sxs-lookup"><span data-stu-id="897db-176">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="897db-177">**OneDrive-mobilapp**</span><span class="sxs-lookup"><span data-stu-id="897db-177">**OneDrive Mobile App**</span></span>

<span data-ttu-id="897db-178">Logga in på din OneDrive-mobilapp med autentiseringsuppgifterna för ditt testkonto.</span><span class="sxs-lookup"><span data-stu-id="897db-178">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="897db-179">Kontrol lera att du kan se dina OneDrive för företag-filer och kan interagera med dem från din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="897db-179">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="897db-180">**OneDrive-synkroniseringsklient**</span><span class="sxs-lookup"><span data-stu-id="897db-180">**OneDrive sync client**</span></span>

<span data-ttu-id="897db-181">Bekräfta att OneDrive-synkroniseringsklienten automatiskt identifierar din OneDrive för företag-Geo plats när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="897db-181">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login.</span></span> <span data-ttu-id="897db-182">Om du behöver hämta synkroniseringsklienten kan du klicka på **Synkronisera** i OneDrive-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="897db-182">If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="897db-183">**Office-program**</span><span class="sxs-lookup"><span data-stu-id="897db-183">**Office applications**</span></span>

<span data-ttu-id="897db-184">Kontrol lera att du kan komma åt OneDrive för företag genom att logga in från ett Office-program, till exempel Word.</span><span class="sxs-lookup"><span data-stu-id="897db-184">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word.</span></span> <span data-ttu-id="897db-185">Öppna Office-programmet och välj "OneDrive – <TenantName> ".</span><span class="sxs-lookup"><span data-stu-id="897db-185">Open the Office application and select "OneDrive – <TenantName>".</span></span> <span data-ttu-id="897db-186">Office identifierar din OneDrive-plats och visar de filer som du kan öppna.</span><span class="sxs-lookup"><span data-stu-id="897db-186">Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="897db-187">**Delning**</span><span class="sxs-lookup"><span data-stu-id="897db-187">**Sharing**</span></span>

<span data-ttu-id="897db-188">Försök dela OneDrive-filer.</span><span class="sxs-lookup"><span data-stu-id="897db-188">Try sharing OneDrive files.</span></span> <span data-ttu-id="897db-189">Kontrol lera att person väljaren visar alla dina SharePoint Online-användare oavsett deras Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="897db-189">Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>
