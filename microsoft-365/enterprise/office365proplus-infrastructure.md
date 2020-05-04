---
title: 'Fas 4: Microsoft 365-applikationer för företag'
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
description: Steg för att distribuera infrastrukturen för Microsoft 365-applikationer för företag för Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011953"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c922c-103">Fas 4: Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="c922c-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![Fas 4: Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="c922c-105">*Det här steget gäller både E3- och E5-versionerna av Microsoft 365 Enterprise och Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="c922c-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="c922c-106">Microsoft 365 Enterprise innehåller Microsoft 365-applikationer för företag, prenumerationsversionen av Office.</span><span class="sxs-lookup"><span data-stu-id="c922c-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="c922c-107">Precis som Office 2019 innehåller Microsoft 365-applikationer för företag alla Office-programmen, och programmen installeras direkt på klientenheterna.</span><span class="sxs-lookup"><span data-stu-id="c922c-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="c922c-108">Till skillnad från Office 2019 uppdateras Microsoft 365-applikationer för företag regelbundet med nya funktioner och har en användarbaserad licensieringsmodell som gör det möjligt för användare att installera Office på flera enheter.</span><span class="sxs-lookup"><span data-stu-id="c922c-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="c922c-109">Mer information finns i [Om Microsoft 365-applikationer för företag](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="c922c-109">For more details, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="c922c-110">I den här fasen distribuerar du Microsoft 365-applikationer för företag till klientenheter som en del av Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c922c-110">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="c922c-111">Utöver den här vägledningen rekommenderar vi att du använder [Microsoft FastTrack](https://fasttrack.microsoft.com/office) för att underlätta distributionen.</span><span class="sxs-lookup"><span data-stu-id="c922c-111">In addition to this guidance, we recommend you use [Microsoft FastTrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="c922c-112">Om du redan har distribuerat Microsoft 365-applikationer för företag kan du läsa [avslutsvillkoren](office365proplus-exit-criteria.md) i den här fasen för att kontrollera att den uppfyller de obligatoriska villkoren för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c922c-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="c922c-113">Om du vill distribuera både Windows 10 Enterprise och Microsoft 365-applikationer för företag tillsammans hittar du mer information i [Center för skrivbordsdistribution](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="c922c-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="c922c-114">Steg 1: Utvärdera miljön</span><span class="sxs-lookup"><span data-stu-id="c922c-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="c922c-115">Innan du distribuerar Microsoft 365-applikationer för företag följer du anvisningarna i artikeln om att [Utvärdera miljön och kraven för distribution av Microsoft 365-applikationer](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="c922c-115">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps).</span></span> <span data-ttu-id="c922c-116">I den här utvärderingen ingår systemkrav, information om dina klientenheter (till exempel arkitekturer och språk som krävs), licensieringskrav, nätverkskapacitet och programkompatibilitet.</span><span class="sxs-lookup"><span data-stu-id="c922c-116">This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility.</span></span> <span data-ttu-id="c922c-117">Utvärderingen hjälper dig att fatta viktiga beslut som en del av planeringen inför distributionen.</span><span class="sxs-lookup"><span data-stu-id="c922c-117">Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="c922c-118">Steg 2: Planera distributionen</span><span class="sxs-lookup"><span data-stu-id="c922c-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="c922c-119">När du har utvärderat miljön följer du stegen i artikeln om att [planera distributionen av Microsoft 365-applikationer](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) för att skapa en distributionsplan.</span><span class="sxs-lookup"><span data-stu-id="c922c-119">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) to create a deployment plan.</span></span> <span data-ttu-id="c922c-120">I planen ingår följande beslut:</span><span class="sxs-lookup"><span data-stu-id="c922c-120">This plan includes the following decisions:</span></span> 

- <span data-ttu-id="c922c-121">Hur du distribuerar Office, till exempel vilket verktyg du ska använda (till exempel Microsoft Endpoint Configuration Manager eller Office-distributionsverktyget) och var Office ska installeras från</span><span class="sxs-lookup"><span data-stu-id="c922c-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="c922c-122">Hantera uppdateringar av Office</span><span class="sxs-lookup"><span data-stu-id="c922c-122">How to manage updates to Office</span></span>
- <span data-ttu-id="c922c-123">Vilka uppdateringskanaler du ska använda (uppdateringskanaler för Office styr hur ofta användarna får funktionsuppdateringar för Office-program)</span><span class="sxs-lookup"><span data-stu-id="c922c-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="c922c-124">De Office-installationspaket och distributionsgrupper som du vill använda, inklusive vilka Office-program och språk som ska installeras för vilka användare</span><span class="sxs-lookup"><span data-stu-id="c922c-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="c922c-125">I [planeringsartikeln](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) finns metodtips för alla dessa alternativ, t. ex. hur du hanterar distribution och uppdateringar, definierar installationspaket och skapar distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c922c-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="c922c-126">Steg 3: Distribuera</span><span class="sxs-lookup"><span data-stu-id="c922c-126">Step 3: Deploy</span></span>

<span data-ttu-id="c922c-127">Välj hur du vill distribuera baserat på din distributionsplan:</span><span class="sxs-lookup"><span data-stu-id="c922c-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="c922c-128">**[Distribuera Microsoft 365-applikationer med Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Hantera din distribution med Configuration Manager, och ladda ned och distribuera Office från distributionsplatser i nätverket</span><span class="sxs-lookup"><span data-stu-id="c922c-128">**[Deploy Microsoft 365 Apps with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="c922c-129">**[Distribuera Microsoft 365-applikationer från molnet](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Hantera din distribution med ODT och installera Office på klientenheter direkt från Office CDN</span><span class="sxs-lookup"><span data-stu-id="c922c-129">**[Deploy Microsoft 365 Apps from the cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="c922c-130">**[Självinstallation av Microsoft 365-applikationer för företag från Office-portalen](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Hantera din distribution från Office-portalen och låt användarna installera Office på sina klientenheter direkt från portalen</span><span class="sxs-lookup"><span data-stu-id="c922c-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="c922c-131">Många organisationer kommer att använda en kombination av de här alternativen för olika användare.</span><span class="sxs-lookup"><span data-stu-id="c922c-131">Many organizations will use a combination of these options for different users.</span></span> <span data-ttu-id="c922c-132">En organisation kan till exempel använda konfigurationshanteraren för att distribuera Office till merparten av sina användare, men erbjuda självinstallation för en mindre grupp medarbetare som inte ansluter till det interna nätverket så ofta.</span><span class="sxs-lookup"><span data-stu-id="c922c-132">For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="c922c-133">Om din organisation använder konfigurationshanteraren rekommenderar vi att du uppgraderar till Current Branch och uppdaterar till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="c922c-133">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release.</span></span> <span data-ttu-id="c922c-134">Mer information finns i [Vilken gren av konfigurationshanteraren ska jag använda?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="c922c-134">For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c922c-135">Hur Microsoft använder Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c922c-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c922c-136">Ta reda på hur experter på Microsoft [distribuerar och hanterar uppdateringar för Microsoft 365-applikationer för företag](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="c922c-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c922c-137">Så här använder Contoso Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c922c-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c922c-138">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade Microsoft 365-applikationer för företag](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="c922c-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c922c-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c922c-140">Next step</span></span>

[<span data-ttu-id="c922c-141">Avslutsvillkor för infrastrukturen för Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="c922c-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
