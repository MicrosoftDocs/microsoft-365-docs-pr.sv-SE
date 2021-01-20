---
title: Steg 4. Migrering för Microsoft 365 för företags innehavare
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
ms.custom:
- Ent_Solutions
description: Migrera dina Windows-enheter, Office-klientprogram och Office-servrar för dina Microsoft 365-klient organisationer.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908754"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="9908f-104">Steg 4.</span><span class="sxs-lookup"><span data-stu-id="9908f-104">Step 4.</span></span> <span data-ttu-id="9908f-105">Migrering för Microsoft 365 för företags innehavare</span><span class="sxs-lookup"><span data-stu-id="9908f-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="9908f-106">De flesta företags organisationer har en heterogen miljö som inkluderar flera versioner av operativ system, klient program vara och serverprogram vara.</span><span class="sxs-lookup"><span data-stu-id="9908f-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="9908f-107">Microsoft 365 för Enterprise innehåller de säkraste versionerna av huvud komponenterna i din IT-infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="9908f-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="9908f-108">Det inkluderar också produktivitets funktioner som är avsedda att utnyttja moln teknologier.</span><span class="sxs-lookup"><span data-stu-id="9908f-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="9908f-109">Om du vill maximera företags värdet för Microsoft 365 för Enterprise-integrerad produkt serie kan du börja planera och implementera en strategi för att migrera dessa utgåvor:</span><span class="sxs-lookup"><span data-stu-id="9908f-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="9908f-110">Från</span><span class="sxs-lookup"><span data-stu-id="9908f-110">From</span></span> | <span data-ttu-id="9908f-111">Till</span><span class="sxs-lookup"><span data-stu-id="9908f-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="9908f-112">Windows 7 och Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="9908f-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="9908f-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9908f-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="9908f-114">Office-klientprodukter installerade på din arbets tagares enheter</span><span class="sxs-lookup"><span data-stu-id="9908f-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="9908f-115"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="9908f-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="9908f-116">Office Server-produkter installerade på lokala servrar</span><span class="sxs-lookup"><span data-stu-id="9908f-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="9908f-117">Deras motsvarande molnbaserade tjänster i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9908f-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="9908f-118">Migrera till Windows 10</span><span class="sxs-lookup"><span data-stu-id="9908f-118">Migrating to Windows 10</span></span>

<span data-ttu-id="9908f-119">Alla Microsoft 365 för företags licenser inkluderar en licens för Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9908f-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="9908f-120">Om du vill migrera dina enheter som kör Windows 7 eller Windows 8,1 kan du göra en uppgradering på plats.</span><span class="sxs-lookup"><span data-stu-id="9908f-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="9908f-121">Support upphörde för Windows 7 den *14 januari 2020*.</span><span class="sxs-lookup"><span data-stu-id="9908f-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="9908f-122">Ytterligare metoder för att installera Windows 10 Enterprise efter en uppgradering på plats finns i [Windows 10: distributions scenarier](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="9908f-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="9908f-123">Du kan också [planera för distribution av Windows 10](https://aka.ms/planforwin10deployment) på egen hand.</span><span class="sxs-lookup"><span data-stu-id="9908f-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="9908f-124">Migrera till Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="9908f-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="9908f-125">Microsoft 365 för Enterprise innehåller Microsoft 365-appar för företag, en version av Office-klientprodukter (Word, PowerPoint, Excel och Outlook) som installeras och uppdateras från Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="9908f-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="9908f-126">Mer information finns i [om Microsoft 365-appar för företag](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="9908f-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="9908f-127">I stället för att hålla datorerna aktuella för Office 2019 eller äldre versioner gör du så här:</span><span class="sxs-lookup"><span data-stu-id="9908f-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="9908f-128">Skaffa och tilldela en Microsoft 365-licens för dina användare.</span><span class="sxs-lookup"><span data-stu-id="9908f-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="9908f-129">Avinstallera Office 2013 eller Office 2016 på sina datorer.</span><span class="sxs-lookup"><span data-stu-id="9908f-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="9908f-130">Installera Microsoft 365-appar för företag, antingen individuellt eller under en IT-installation.</span><span class="sxs-lookup"><span data-stu-id="9908f-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="9908f-131">Mer information finns i [distributions guide för Microsoft 365-appar](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="9908f-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="9908f-132">Microsoft 365-appar för Enterprise installerar både säkerhets uppdateringar och nya funktioner uppdateringar automatiskt och kan utnyttja molnbaserade tjänster i Microsoft 365 för ökad säkerhet och produktivitet.</span><span class="sxs-lookup"><span data-stu-id="9908f-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="9908f-133">Migrera lokala servrar och data till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9908f-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="9908f-134">Microsoft 365 för Enterprise innehåller molnbaserade versioner av Office Server-tjänster som använder vissa av de verktyg som lokala versioner av Office Server-program, till exempel webbläsare och Outlook-klienten.</span><span class="sxs-lookup"><span data-stu-id="9908f-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="9908f-135">Dessa molnbaserade tjänster uppdateras automatiskt för säkerhets-och nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="9908f-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="9908f-136">Efter migrering kan din IT-avdelning Spara den tid det tar att underhålla och uppdatera lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="9908f-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="9908f-137">Använd följande resurser för information om hur du migrerar användare och data för specifika Microsoft 365-arbets belastningar:</span><span class="sxs-lookup"><span data-stu-id="9908f-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="9908f-138">Flytta post lådor från lokal Exchange-Server till Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9908f-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="9908f-139">Migrera SharePoint-data från SharePoint Server till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9908f-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="9908f-140">Migrera Skype för företag – Online till Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9908f-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="9908f-141">En övergång för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="9908f-141">Transition your entire organization</span></span>

<span data-ttu-id="9908f-142">För att få en bättre bild av hur du flyttar hela organisationen till produkterna och tjänsterna i Microsoft 365 för företag kan du hämta denna över gångs affisch:</span><span class="sxs-lookup"><span data-stu-id="9908f-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="9908f-143">[![Bild som visar över gången till Microsoft 365-affisch.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="9908f-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="9908f-144">Med den här affischen på två sidor kan du snabbt inventera din befintliga infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="9908f-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="9908f-145">Använd den för att få vägledning för att flytta till en produkt eller tjänst i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="9908f-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="9908f-146">Det visar Windows-och Office-produkter och andra infrastruktur-och säkerhets element som enhets hantering, identitets-och hot skydd samt informations skydd och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="9908f-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="9908f-147">Resultat i steg 4</span><span class="sxs-lookup"><span data-stu-id="9908f-147">Results of Step 4</span></span>

<span data-ttu-id="9908f-148">Om du vill migrera din Microsoft 365-klient kan du bestämma:</span><span class="sxs-lookup"><span data-stu-id="9908f-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="9908f-149">Vilka enheter som kör Windows 7 eller Windows 8,1 och abonnemanget för att uppdatera dem till Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9908f-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="9908f-150">Vilka enheter som kör Office-klientprogram och abonnemanget för att uppdatera dem till Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="9908f-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="9908f-151">Vilka lokala Office Server-tjänster som bör migreras till deras Microsoft 365-motsvarighet och för att migrera dem och deras data.</span><span class="sxs-lookup"><span data-stu-id="9908f-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="9908f-152">Här är ett exempel på en klient organisation med en slutförd migrering av lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="9908f-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Exempel på en klient organisation med fullständig migrering av lokala servrar](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="9908f-154">I den här bilden har organisationen:</span><span class="sxs-lookup"><span data-stu-id="9908f-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="9908f-155">Migrerade sina lokala Exchange Server-postlådor till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9908f-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="9908f-156">Migrerade dess lokala SharePoint Server-webbplatser och data till SharePoint i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9908f-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="9908f-157">Löpande underhåll för migrering</span><span class="sxs-lookup"><span data-stu-id="9908f-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="9908f-158">Kontinuerligt måste du kanske:</span><span class="sxs-lookup"><span data-stu-id="9908f-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="9908f-159">Beroende på tillståndet för din Exchange-postmigrering fortsätter du att rulla över gången till Exchange Online till din organisation.</span><span class="sxs-lookup"><span data-stu-id="9908f-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="9908f-160">Beroende på tillståndet för den lokala SharePoint-webbplatsens migrering fortsätter du att rulla över gången till SharePoint i Microsoft 365 till din organisation.</span><span class="sxs-lookup"><span data-stu-id="9908f-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="9908f-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9908f-161">Next step</span></span>

<span data-ttu-id="9908f-162">[![Steg 5. Distribuera enhets-och program hantering](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="9908f-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="9908f-163">Fortsätt med [enhet och program hantering](tenant-management-device-management.md) för att distribuera enheter och program hantering.</span><span class="sxs-lookup"><span data-stu-id="9908f-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
