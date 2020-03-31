---
title: 'Fas 4: Office 365 ProPlus'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Steg för att distribuera Office 365 ProPlus-infrastrukturen för Microsoft 365 Enterprise.
ms.openlocfilehash: 2b3ac311863249720a2dc1fba00ead9ebf6ac8e5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808095"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="a7771-103">Fas 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a7771-103">Phase 4: Office 365 ProPlus</span></span>

![Fas 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="a7771-105">*Det här steget gäller både E3- och E5-versionerna av Microsoft 365 Enterprise och Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="a7771-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="a7771-106">Microsoft 365 Enterprise innehåller Office 365 ProPlus, prenumerationsversionen av Office.</span><span class="sxs-lookup"><span data-stu-id="a7771-106">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office.</span></span> <span data-ttu-id="a7771-107">Precis som Office 2019 innehåller Office 365 ProPlus alla Office-programmen, och programmen installeras direkt på klientenheterna.</span><span class="sxs-lookup"><span data-stu-id="a7771-107">Like Office 2019, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="a7771-108">Till skillnad från Office 2019 uppdateras Office 365 ProPlus regelbundet med nya funktioner och har en användarbaserad licensieringsmodell som gör det möjligt för användare att installera Office på flera enheter.</span><span class="sxs-lookup"><span data-stu-id="a7771-108">Unlike Office 2019, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="a7771-109">Mer information finns i [Om Office 365 ProPlus i företaget](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="a7771-109">For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="a7771-110">I den här fasen distribuerar du Office 365 ProPlus till klientenheter som en del av Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a7771-110">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="a7771-111">Utöver den här vägledningen rekommenderar vi att du använder [Microsoft FasTrack](https://fasttrack.microsoft.com/office) för att underlätta distributionen.</span><span class="sxs-lookup"><span data-stu-id="a7771-111">In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="a7771-112">Om du redan har distribuerat Office 365 ProPlus kan du läsa [avslutsvillkoren](office365proplus-exit-criteria.md) i den här fasen för att kontrollera att den uppfyller de obligatoriska villkoren för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a7771-112">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="a7771-113">Om du vill distribuera både Windows 10 Enterprise och Office 365 ProPlus tillsammans hittar du mer information i [Desktop Deployment Center](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="a7771-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="a7771-114">Steg 1: Utvärdera miljön</span><span class="sxs-lookup"><span data-stu-id="a7771-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="a7771-115">Innan du distribuerar Office 365 ProPlus följer du anvisningarna i [Utvärdera miljön och kraven för distribution av Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus).</span><span class="sxs-lookup"><span data-stu-id="a7771-115">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus).</span></span> <span data-ttu-id="a7771-116">I den här utvärderingen ingår systemkrav, information om dina klientenheter (till exempel arkitekturer och språk som krävs), licensieringskrav, nätverkskapacitet och programkompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="a7771-116">This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility.</span></span> <span data-ttu-id="a7771-117">Utvärderingen hjälper dig att fatta viktiga beslut som en del av planeringen inför distributionen.</span><span class="sxs-lookup"><span data-stu-id="a7771-117">Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="a7771-118">Steg 2: Planera distributionen</span><span class="sxs-lookup"><span data-stu-id="a7771-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="a7771-119">När du har utvärderat miljön följer du stegen i [Planera distributionen av Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) för att skapa en distributionsplan.</span><span class="sxs-lookup"><span data-stu-id="a7771-119">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan.</span></span> <span data-ttu-id="a7771-120">I planen ingår följande beslut:</span><span class="sxs-lookup"><span data-stu-id="a7771-120">This plan includes the following decisions:</span></span> 

- <span data-ttu-id="a7771-121">Hur du distribuerar Office, till exempel vilket verktyg du ska använda (till exempel Microsoft Endpoint Configuration Manager eller Office-distributionsverktyget) och var Office ska installeras från</span><span class="sxs-lookup"><span data-stu-id="a7771-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="a7771-122">Hantera uppdateringar av Office</span><span class="sxs-lookup"><span data-stu-id="a7771-122">How to manage updates to Office</span></span>
- <span data-ttu-id="a7771-123">Vilka uppdateringskanaler du ska använda (uppdateringskanaler för Office styr hur ofta användarna får funktionsuppdateringar för Office-program)</span><span class="sxs-lookup"><span data-stu-id="a7771-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="a7771-124">De Office-installationspaket och distributionsgrupper som du vill använda, inklusive vilka Office-program och språk som ska installeras för vilka användare</span><span class="sxs-lookup"><span data-stu-id="a7771-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="a7771-125">I [planeringsartikeln](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) finns metodtips för alla dessa alternativ, t. ex. hur du hanterar distribution och uppdateringar, definierar installationspaket och skapar distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="a7771-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="a7771-126">Steg 3: Distribuera</span><span class="sxs-lookup"><span data-stu-id="a7771-126">Step 3: Deploy</span></span>

<span data-ttu-id="a7771-127">Välj hur du vill distribuera baserat på din distributionsplan:</span><span class="sxs-lookup"><span data-stu-id="a7771-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="a7771-128">**[Distribuera Office 365 ProPlus med konfigurationshanteraren](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Hantera din distribution med konfigurationshanteraren, och hämta och distribuera Office från distributionsplatser i nätverket</span><span class="sxs-lookup"><span data-stu-id="a7771-128">**[Deploy Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="a7771-129">**[Distribuera Office 365 ProPlus med ODT från molnet](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Hantera din distribution med ODT och installera Office på klientenheter direkt från Office CDN</span><span class="sxs-lookup"><span data-stu-id="a7771-129">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="a7771-130">**[Självinstallera Office 365 ProPlus från Office-portalen](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Hantera din distribution från Office-portalen och låt användarna installera Office på sina klientenheter direkt från portalen</span><span class="sxs-lookup"><span data-stu-id="a7771-130">**[Self-install Office 365 ProPlus from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="a7771-131">Många organisationer kommer att använda en kombination av de här alternativen för olika användare.</span><span class="sxs-lookup"><span data-stu-id="a7771-131">Many organizations will use a combination of these options for different users.</span></span> <span data-ttu-id="a7771-132">En organisation kan till exempel använda konfigurationshanteraren för att distribuera Office till merparten av sina användare, men erbjuda självinstallation för en mindre grupp medarbetare som inte ansluter till det interna nätverket så ofta.</span><span class="sxs-lookup"><span data-stu-id="a7771-132">For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="a7771-133">Om din organisation använder konfigurationshanteraren rekommenderar vi att du uppgraderar till Current Branch och uppdaterar till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="a7771-133">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release.</span></span> <span data-ttu-id="a7771-134">Mer information finns i [Vilken gren av konfigurationshanteraren ska jag använda?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="a7771-134">For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="a7771-135">Så här används Microsoft 365 Enterprise på Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7771-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a7771-136">Lär dig hur experter på Microsoft [distribuerar och hanterar uppdateringar för Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="a7771-136">Learn how the experts at Microsoft are [deploying and managing updates for Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="a7771-137">Så här använder Contoso Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a7771-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a7771-138">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade Office 365 ProPlus](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="a7771-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="a7771-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a7771-140">Next step</span></span>

[<span data-ttu-id="a7771-141">Avslutsvillkor för Office 365 ProPlus-infrastruktur</span><span class="sxs-lookup"><span data-stu-id="a7771-141">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
