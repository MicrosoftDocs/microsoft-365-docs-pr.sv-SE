---
title: Konfiguration av Microsoft 365 Multi-Geo-klientorganisation
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
description: I den här artikeln lär du dig hur du lägger till satellitplatser och konfigurerar klientorganisationen för Microsoft 365 Multi-Geo.
ms.openlocfilehash: fb907c02a4714c5a2d8e47245321252e7186a8a7
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040574"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="d613e-103">Konfiguration av Microsoft 365 Multi-Geo-klientorganisation</span><span class="sxs-lookup"><span data-stu-id="d613e-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="d613e-104">Innan du konfigurerar klientorganisationen för Microsoft 365 Multi-Geo bör du läsa Abonnemang för [Microsoft 365 Multi-Geo.](plan-for-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="d613e-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="d613e-105">Om du vill följa stegen i den här artikeln behöver du en lista över de geoplatser som du vill aktivera som satellitplatser och testanvändarna som du vill etablera för dessa platser.</span><span class="sxs-lookup"><span data-stu-id="d613e-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="d613e-106">Lägg till Multi-Geo Capabilities i Microsoft 365-abonnemanget i din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="d613e-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="d613e-107">Om du vill använda Microsoft 365 Multi-Geo behöver du _Multi-Geo Capabilities i Microsoft 365-abonnemanget._</span><span class="sxs-lookup"><span data-stu-id="d613e-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="d613e-108">Arbeta med ditt kontoteam för att lägga till den här planen i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d613e-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="d613e-109">Ditt kontoteam kommer att ansluta dig till rätt licensieringsspecialist och få din klientorganisation konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="d613e-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="d613e-110">Observera att _Multi-Geo Capabilities i Microsoft 365-abonnemanget_ är ett serviceabonnemang på användarnivå.</span><span class="sxs-lookup"><span data-stu-id="d613e-110">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan.</span></span> <span data-ttu-id="d613e-111">Du behöver en licens för varje användare som du vill vara värd för på en satellitplats.</span><span class="sxs-lookup"><span data-stu-id="d613e-111">You need a license for each user that you want to host in a satellite location.</span></span> <span data-ttu-id="d613e-112">Du kan lägga till fler licenser med tiden när du lägger till användare i satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="d613e-112">You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="d613e-113">När klientorganisationen har etablerats med  _Multi-Geo Capabilities i Microsoft 365-abonnemanget_ blir fliken **Geoplatser** tillgänglig i administrationscentret för OneDrive och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d613e-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="d613e-114">Lägga till satellitplatser i klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="d613e-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="d613e-115">Du måste lägga till en satellitplats för varje geoplats där du vill lagra data.</span><span class="sxs-lookup"><span data-stu-id="d613e-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="d613e-116">Tillgängliga geografiska platser visas i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="d613e-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Skärmbild av sidan geoplatser i administrationscentret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="d613e-118">Lägga till en satellitplats</span><span class="sxs-lookup"><span data-stu-id="d613e-118">To add a satellite location</span></span>

1. <span data-ttu-id="d613e-119">Öppna SharePoint Online Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="d613e-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="d613e-120">Gå till **fliken Geoplatser.**</span><span class="sxs-lookup"><span data-stu-id="d613e-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="d613e-121">Klicka **på Lägg till plats.**</span><span class="sxs-lookup"><span data-stu-id="d613e-121">Click **Add location**.</span></span>

4. <span data-ttu-id="d613e-122">Välj den plats du vill lägga till och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d613e-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="d613e-123">Ange den domän som du vill använda med geoplatsen och klicka sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="d613e-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="d613e-124">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d613e-124">Click **Close**.</span></span>

<span data-ttu-id="d613e-125">Etableringen kan ta från ett par timmar upp till 72 timmar, beroende på storleken på klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d613e-125">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant.</span></span> <span data-ttu-id="d613e-126">När etableringen av en satellitplats har slutförts får du en e-postbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="d613e-126">Once provisioning of a satellite location has completed, you will receive an email confirmation.</span></span> <span data-ttu-id="d613e-127">När den nya geoplatsen visas i blått på kartan på fliken Geoplatser i administrationscentret för OneDrive kan du fortsätta och ange **användarnas** önskade dataplats till den geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="d613e-127">When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d613e-128">Din nya satellitplats konfigureras med standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="d613e-128">Your new satellite location will be set up with default settings.</span></span> <span data-ttu-id="d613e-129">Det här gör att du kan konfigurera den satellitplatsen efter dina lokala efterlevnadsbehov.</span><span class="sxs-lookup"><span data-stu-id="d613e-129">This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="d613e-130">Ange användarnas föredragna dataplats</span><span class="sxs-lookup"><span data-stu-id="d613e-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="d613e-131">När du har aktiverar de satellitplatser som behövs kan du uppdatera användarkontona så att de använder rätt önskad dataplats.</span><span class="sxs-lookup"><span data-stu-id="d613e-131">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location.</span></span> <span data-ttu-id="d613e-132">Vi rekommenderar att du anger en önskad dataplats för varje användare, även om användaren finns kvar på den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="d613e-132">We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d613e-133">Om en användares önskade dataplats anges till en plats som inte har konfigurerats som en satellitplats eller den centrala platsen får systemet som standard den centrala platsen när OneDrive- och SharePoint-webbplatser och grupppostlådor etableras.</span><span class="sxs-lookup"><span data-stu-id="d613e-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="d613e-134">Vi rekommenderar att du börjar validera med en testanvändare eller en liten grupp användare innan du distribuerar multi-geo till din bredare organisation.</span><span class="sxs-lookup"><span data-stu-id="d613e-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="d613e-135">Det finns två typer av användarobjekt i Azure Active Directory (Azure AD): endast molnanvändare och synkroniserade användare.</span><span class="sxs-lookup"><span data-stu-id="d613e-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="d613e-136">Följ anvisningarna för din typ av användare.</span><span class="sxs-lookup"><span data-stu-id="d613e-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="d613e-137">Synkronisera användarens föredragna dataplats med hjälp av Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="d613e-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="d613e-138">Om användarna i ditt företag synkroniseras från ett lokalt Active Directory-system till Azure AD måste deras PreferredDataLocation fyllas i i AD och synkroniseras med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d613e-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="d613e-139">Följ processen i [Azure Active Directory Connect-synkronisering:](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) Konfigurera önskad dataplats för Microsoft 365-resurser för att konfigurera synkronisering av önskad dataplats från din lokala Active Directory DS (AD DS) till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d613e-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="d613e-140">Vi rekommenderar att du anger användarens föredragna dataplats som en del av ditt vanliga arbetsflöde för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="d613e-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d613e-141">För nya användare som inte har någon OneDrive-etablering bör du vänta i minst 24 timmar efter att en användares PDF-fil har synkroniserats med Azure AD för att ändringarna ska spridas innan användarna loggar in i OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="d613e-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="d613e-142">(Genom att ange önskad dataplats innan användaren loggar in för att etablera sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)</span><span class="sxs-lookup"><span data-stu-id="d613e-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="d613e-143">Ange önskad dataplats för användare endast i molnet</span><span class="sxs-lookup"><span data-stu-id="d613e-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="d613e-144">Om användarna i ditt företag inte synkroniseras från ett lokalt Active Directory-system till Azure AD, vilket innebär att de skapas i Microsoft 365 eller Azure AD, måste PDF-operativsystemet ställas in med Hjälp av Microsoft Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d613e-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="d613e-145">För procedurerna i det här avsnittet [krävs Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen.](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0)</span><span class="sxs-lookup"><span data-stu-id="d613e-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="d613e-146">Om du redan har den här modulen installerad bör du uppdatera till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="d613e-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="d613e-147">[Anslut och logga in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) med en uppsättning autentiseringsuppgifter som global administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d613e-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="d613e-148">Använd [cmdleten Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) för att ange önskad dataplats för var och en av användarna.</span><span class="sxs-lookup"><span data-stu-id="d613e-148">Use the [Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users.</span></span> <span data-ttu-id="d613e-149">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d613e-149">For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="d613e-150">Du kan kontrollera om den rekommenderade dataplatsen har uppdaterats korrekt med hjälp av cmdleten Get-MsolUser.</span><span class="sxs-lookup"><span data-stu-id="d613e-150">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet.</span></span> <span data-ttu-id="d613e-151">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d613e-151">For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Skärmbild av PowerShell-fönstret med Set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="d613e-153">Vi rekommenderar att du anger användarens föredragna dataplats som en del av ditt vanliga arbetsflöde för att skapa användare.</span><span class="sxs-lookup"><span data-stu-id="d613e-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d613e-154">För nya användare som inte har någon OneDrive-etablering bör du vänta i minst 24 timmar efter att en användares PDF-fil har angetts för att ändringarna ska spridas innan användaren loggar in på OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d613e-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="d613e-155">(Genom att ange önskad dataplats innan användaren loggar in för att etablera sin OneDrive för företag säkerställer du att användarens nya OneDrive etableras på rätt plats.)</span><span class="sxs-lookup"><span data-stu-id="d613e-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="d613e-156">OneDrive-etablering och effekten av PDL</span><span class="sxs-lookup"><span data-stu-id="d613e-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="d613e-157">Om användaren redan har en OneDrive-webbplats skapad i klientorganisationen flyttas inte deras befintliga OneDrive automatiskt när du anger deras PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="d613e-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="d613e-158">Information om hur du flyttar en användares OneDrive finns i [Geoflyttning i OneDrive för företag.](move-onedrive-between-geo-locations.md)</span><span class="sxs-lookup"><span data-stu-id="d613e-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d613e-159">Exchange Online flyttar automatiskt användarens postlåda om PLD-ändringarna och postlåderegion inte längre stämmer överens med geoplatskoden för postlådedatabasen.</span><span class="sxs-lookup"><span data-stu-id="d613e-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="d613e-160">Mer information finns i Administrera [Exchange Online-postlådor i en miljö med flera geografiska miljöer.](https://docs.microsoft.com/microsoft-365/enterprise/administering-exchange-online-multi-geo)</span><span class="sxs-lookup"><span data-stu-id="d613e-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](https://docs.microsoft.com/microsoft-365/enterprise/administering-exchange-online-multi-geo).</span></span>

<span data-ttu-id="d613e-161">Om användaren inte har en OneDrive-webbplats i klientorganisationen etableras OneDrive åt dem i enlighet med deras PDL-värde, förutsatt att PDF-talet för användaren matchar en av företagets satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="d613e-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="d613e-162">Konfigurera multi geosökning</span><span class="sxs-lookup"><span data-stu-id="d613e-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="d613e-163">Din multigeobaserade klientorganisation har samlade sökfunktioner som gör att en sökfråga kan returnera resultat från valfri plats i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d613e-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="d613e-164">Som standard returnerar sökningar från dessa startpunkter aggregerade resultat, även om varje sökindex finns inom dess relevanta geoplats:</span><span class="sxs-lookup"><span data-stu-id="d613e-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="d613e-165">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="d613e-165">OneDrive for Business</span></span>

- <span data-ttu-id="d613e-166">Delve</span><span class="sxs-lookup"><span data-stu-id="d613e-166">Delve</span></span>

- <span data-ttu-id="d613e-167">Start för SharePoint</span><span class="sxs-lookup"><span data-stu-id="d613e-167">SharePoint Home</span></span>

- <span data-ttu-id="d613e-168">Sökcenter</span><span class="sxs-lookup"><span data-stu-id="d613e-168">Search Center</span></span>

<span data-ttu-id="d613e-169">Dessutom kan funktioner för flera geosökning konfigureras för anpassade sökprogram som använder SharePoints sök-API.</span><span class="sxs-lookup"><span data-stu-id="d613e-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="d613e-170">I Konfigurera [sökning efter OneDrive för företag – Multi-Geo](configure-search-for-multi-geo.md) finns instruktioner, inklusive eventuella begränsningar och skillnader.</span><span class="sxs-lookup"><span data-stu-id="d613e-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="d613e-171">Validera Microsoft 365 Multi-Geo-konfigurationen</span><span class="sxs-lookup"><span data-stu-id="d613e-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="d613e-172">Nedan följer några grundläggande användningsfall som du kanske vill inkludera i din valideringsplan innan du allmänt distribuerar Microsoft 365 Multi-Geo till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d613e-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="d613e-173">När du har slutfört dessa tester och eventuella ytterligare användningsfall som är relevanta för ditt företag kan du välja att gå vidare och lägga till användare i den första pilotgruppen.</span><span class="sxs-lookup"><span data-stu-id="d613e-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="d613e-174">**OneDrive för företag**</span><span class="sxs-lookup"><span data-stu-id="d613e-174">**OneDrive for Business**</span></span>

<span data-ttu-id="d613e-175">Välj OneDrive från appstartaren för Microsoft 365 och bekräfta att du automatiskt dirigeras till rätt geoplats för användaren, baserat på användarens PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="d613e-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="d613e-176">OneDrive för företag bör nu börja etableras på den platsen.</span><span class="sxs-lookup"><span data-stu-id="d613e-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="d613e-177">När de har etablerats kan du försöka ladda upp och ladda ned vissa dokument.</span><span class="sxs-lookup"><span data-stu-id="d613e-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="d613e-178">**OneDrive-mobilappen**</span><span class="sxs-lookup"><span data-stu-id="d613e-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="d613e-179">Logga in på OneDrive-mobilappen med dina autentiseringsuppgifter för testkontot.</span><span class="sxs-lookup"><span data-stu-id="d613e-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="d613e-180">Bekräfta att du kan se dina OneDrive för företag-filer och kan interagera med dem från din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="d613e-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="d613e-181">**OneDrive-synkroniseringsklient**</span><span class="sxs-lookup"><span data-stu-id="d613e-181">**OneDrive sync client**</span></span>

<span data-ttu-id="d613e-182">Kontrollera att OneDrive-synkroniseringsklienten automatiskt identifierar din geoplats i OneDrive för företag vid inloggning.</span><span class="sxs-lookup"><span data-stu-id="d613e-182">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login.</span></span> <span data-ttu-id="d613e-183">Om du behöver ladda ned synkroniseringsklienten kan du klicka **på Synkronisera** i OneDrive-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="d613e-183">If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="d613e-184">**Office-program**</span><span class="sxs-lookup"><span data-stu-id="d613e-184">**Office applications**</span></span>

<span data-ttu-id="d613e-185">Bekräfta att du kan komma åt OneDrive för företag genom att logga in från ett Office-program, till exempel Word.</span><span class="sxs-lookup"><span data-stu-id="d613e-185">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word.</span></span> <span data-ttu-id="d613e-186">Öppna Office-programmet och välj "OneDrive – <TenantName> ".</span><span class="sxs-lookup"><span data-stu-id="d613e-186">Open the Office application and select "OneDrive – <TenantName>".</span></span> <span data-ttu-id="d613e-187">Office identifierar din OneDrive-plats och visar de filer som du kan öppna.</span><span class="sxs-lookup"><span data-stu-id="d613e-187">Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="d613e-188">**Delning**</span><span class="sxs-lookup"><span data-stu-id="d613e-188">**Sharing**</span></span>

<span data-ttu-id="d613e-189">Prova att dela OneDrive-filer.</span><span class="sxs-lookup"><span data-stu-id="d613e-189">Try sharing OneDrive files.</span></span> <span data-ttu-id="d613e-190">Bekräfta att alla dina SharePoint Online-användare visas i väljaren, oavsett deras geografiska position.</span><span class="sxs-lookup"><span data-stu-id="d613e-190">Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>
