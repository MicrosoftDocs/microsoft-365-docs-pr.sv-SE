---
title: Steg 4. Migrering för din Microsoft 365 för företagsklienter
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migrera dina Windows-enheter, Office-klientprogram och Office-servrarna för Microsoft 365-klientorganisationen.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929150"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="06a88-104">Steg 4.</span><span class="sxs-lookup"><span data-stu-id="06a88-104">Step 4.</span></span> <span data-ttu-id="06a88-105">Migrering för din Microsoft 365 för företagsklienter</span><span class="sxs-lookup"><span data-stu-id="06a88-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="06a88-106">De flesta företag har en heterisk miljö som innehåller flera versioner av operativsystem, klientprogramvara och serverprogramvara.</span><span class="sxs-lookup"><span data-stu-id="06a88-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="06a88-107">Microsoft 365 för företag innehåller de säkraste versionerna av de viktigaste komponenterna i IT-infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="06a88-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="06a88-108">Dessutom finns produktivitetsfunktioner som är utformade för att dra nytta av molntekniker.</span><span class="sxs-lookup"><span data-stu-id="06a88-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="06a88-109">För att maximera affärsvärdet för företagets Microsoft 365 för en företagsintegrerad produktsvit kan du börja planera och implementera en strategi för att migrera dessa versioner:</span><span class="sxs-lookup"><span data-stu-id="06a88-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="06a88-110">Från</span><span class="sxs-lookup"><span data-stu-id="06a88-110">From</span></span> | <span data-ttu-id="06a88-111">Till</span><span class="sxs-lookup"><span data-stu-id="06a88-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="06a88-112">Windows 7 och Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="06a88-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="06a88-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="06a88-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="06a88-114">Office klientprodukter installerade på användarens enheter</span><span class="sxs-lookup"><span data-stu-id="06a88-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="06a88-115"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="06a88-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="06a88-116">Office serverprodukter installerade på lokala servrar</span><span class="sxs-lookup"><span data-stu-id="06a88-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="06a88-117">Motsvarande molnbaserade tjänster i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06a88-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="06a88-118">Migrera till Windows 10</span><span class="sxs-lookup"><span data-stu-id="06a88-118">Migrating to Windows 10</span></span>

<span data-ttu-id="06a88-119">Varje Microsoft 365 för företag innehåller en licens för Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="06a88-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="06a88-120">Om du vill migrera dina enheter Windows 7 eller Windows 8.1 kan du göra en på plats-uppgradering.</span><span class="sxs-lookup"><span data-stu-id="06a88-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="06a88-121">Supporten upphörde Windows 7 *januari 2020.*</span><span class="sxs-lookup"><span data-stu-id="06a88-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="06a88-122">Fler metoder för att installera Windows 10 Enterprise utöver en på plats-uppgradering finns i Windows 10 [distributionsscenarier.](/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="06a88-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="06a88-123">Du kan också [planera för distribution av Windows 10](/windows/deployment/planning/) på egen hand.</span><span class="sxs-lookup"><span data-stu-id="06a88-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="06a88-124">Migrera till Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="06a88-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="06a88-125">Microsoft 365 för företag inkluderar Microsoft 365-appar för företag, en version av Office-klientprodukterna (Word, PowerPoint, Excel och Outlook) som installeras och uppdateras från Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="06a88-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="06a88-126">Mer information finns i [Om Microsoft 365-appar för företag](/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="06a88-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="06a88-127">I stället för att hålla datorerna Office 2019 eller äldre versioner gör du följande:</span><span class="sxs-lookup"><span data-stu-id="06a88-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="06a88-128">Hämta och tilldela en Microsoft 365 licens för dina användare.</span><span class="sxs-lookup"><span data-stu-id="06a88-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="06a88-129">Avinstallera Office 2013 eller Office 2016 på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="06a88-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="06a88-130">Installera Microsoft 365-appar för företag, antingen enskilt eller under en IT-utrullning.</span><span class="sxs-lookup"><span data-stu-id="06a88-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="06a88-131">Mer information finns i [Distributionsguide för Microsoft 365 Program.](/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="06a88-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="06a88-132">Microsoft 365-appar för företag installerar både säkerhetsuppdateringar och nya funktionsuppdateringar automatiskt och kan dra nytta av molnbaserade tjänster i Microsoft 365 för bättre säkerhet och produktivitet.</span><span class="sxs-lookup"><span data-stu-id="06a88-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="06a88-133">Migrera lokala servrar och data till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06a88-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="06a88-134">Microsoft 365 för företag innehåller molnbaserade versioner av Office servertjänster som använder samma verktyg som lokala versioner av Office-serverprogramvaran, till exempel webbläsare och Outlook klienten.</span><span class="sxs-lookup"><span data-stu-id="06a88-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="06a88-135">Dessa molnbaserade tjänster uppdateras automatiskt för säkerhet och nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="06a88-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="06a88-136">Efter migreringen kan IT-avdelningen spara den tid det tar att underhålla och uppdatera lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="06a88-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="06a88-137">Använd följande resurser för information om hur du migrerar användare och data för specifika Microsoft 365 arbetsbelastningar:</span><span class="sxs-lookup"><span data-stu-id="06a88-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="06a88-138">Flytta postlådor från lokala Exchange Server till Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06a88-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="06a88-139">Migrera SharePoint data från SharePoint Server till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06a88-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="06a88-140">Migrera Skype för företag Online till Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06a88-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="06a88-141">En övergång för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="06a88-141">Transition your entire organization</span></span>

<span data-ttu-id="06a88-142">Ladda ned den här övergångsaffischen för att få en bättre bild av hur du kan flytta hela organisationen till produkter och tjänster i Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="06a88-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="06a88-143">[![Bild som visar affischen Övergång Microsoft 365 ny.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="06a88-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="06a88-144">Med den här affischen på två sidor kan du snabbt inventera din befintliga infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="06a88-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="06a88-145">Använd den för att få vägledning för att flytta över till en produkt eller tjänst i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="06a88-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="06a88-146">Den visar Windows hur Office-produkter samt andra infrastruktur- och säkerhetselement, till exempel enhetshantering, identitets- och hotskydd samt informationsskydd och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="06a88-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="06a88-147">Resultat i steg 4</span><span class="sxs-lookup"><span data-stu-id="06a88-147">Results of Step 4</span></span>

<span data-ttu-id="06a88-148">För migrering för din Microsoft 365 har du fastställt:</span><span class="sxs-lookup"><span data-stu-id="06a88-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="06a88-149">Vilka enheter som kör Windows 7 eller Windows 8.1 och planerar att uppdatera dem till Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="06a88-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="06a88-150">Vilka enheter som kör Office och planerar att uppdatera dem till Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="06a88-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="06a88-151">Vilka lokala servertjänster Office ska migreras till motsvarande Microsoft 365 och planera för att migrera dem och deras data.</span><span class="sxs-lookup"><span data-stu-id="06a88-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="06a88-152">Här är ett exempel på en klientorganisation med slutförd migrering av lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="06a88-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Exempel på en klientorganisation med slutförd migrering av lokala servrar](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="06a88-154">I den här illustrationen har organisationen:</span><span class="sxs-lookup"><span data-stu-id="06a88-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="06a88-155">Migrerade postlådorna Exchange Server till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="06a88-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="06a88-156">Migrerade dess lokala serverwebbplatser SharePoint data till e-SharePoint i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06a88-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="06a88-157">Löpande underhåll för migrering</span><span class="sxs-lookup"><span data-stu-id="06a88-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="06a88-158">Du kan behöva:</span><span class="sxs-lookup"><span data-stu-id="06a88-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="06a88-159">Beroende på statusen för Exchange postlådemigrering fortsätter du övergången för att Exchange Online till organisationen.</span><span class="sxs-lookup"><span data-stu-id="06a88-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="06a88-160">Beroende på statusen för din lokala SharePoint-webbplatsmigrering fortsätter du övergången till att SharePoint komma Microsoft 365 ut till organisationen.</span><span class="sxs-lookup"><span data-stu-id="06a88-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="06a88-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="06a88-161">Next step</span></span>

<span data-ttu-id="06a88-162">[![Steg 5. Distribuera hantering av enheter och program](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="06a88-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="06a88-163">Fortsätt med [enhetshantering och programhantering för](tenant-management-device-management.md) att distribuera enhet- och programhantering.</span><span class="sxs-lookup"><span data-stu-id="06a88-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>