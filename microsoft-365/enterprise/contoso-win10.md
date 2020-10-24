---
title: Windows 10 Enterprise-driftsättning för Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Endpoint Configuration Manager för att distribuera på plats-uppgraderingar av Windows 10 Enterprise.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754257"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="682a6-103">Windows 10 Enterprise-driftsättning för Contoso</span><span class="sxs-lookup"><span data-stu-id="682a6-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="682a6-104">Från och med den breda lanseringen av Microsoft 365 för företag, hade contoso Windows-kompatibla datorer och enheter som använder en blandning av Windows 7 (10%), Windows 8,1 (65%) och Windows 10 (25%).</span><span class="sxs-lookup"><span data-stu-id="682a6-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="682a6-105">Contoso ville uppgradera datorerna för Windows 10 Enterprise för att dra nytta av avancerad säkerhet och lägre IT-kostnader jämfört med automatiska distributioner av uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="682a6-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="682a6-106">Efter att ha uppskattat deras infrastruktur- och företagsbehov identifierade Contoso de viktigaste kraven för distributionen:</span><span class="sxs-lookup"><span data-stu-id="682a6-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="682a6-107">Så många datorer och enheter som möjligt skulle köra Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="682a6-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="682a6-108">Lanseringen av på plats-uppgraderingar utnyttjar befintlig Configuration Manager-infrastruktur</span><span class="sxs-lookup"><span data-stu-id="682a6-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="682a6-109">Styr vilka versioner av Windows 10 Enterprise som ska distribueras och vilka uppdateringar som görs via ringar</span><span class="sxs-lookup"><span data-stu-id="682a6-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="682a6-110">Datorerna och enheterna ska vara uppdaterade med minimala IT-administrativa kostnader och minsta möjliga påverkan på slutanvändarna</span><span class="sxs-lookup"><span data-stu-id="682a6-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="682a6-111">Uppdaterat definieras som den version av Windows 10 Enterprise som stöds och som uppfyller organisationens affärsbehov, och det kan skilja sig från att ha alla Windows-kompatibla datorer med den senaste versionen av Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="682a6-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="682a6-112">Distributionsverktyg</span><span class="sxs-lookup"><span data-stu-id="682a6-112">Deployment tools</span></span>

<span data-ttu-id="682a6-113">Före och under på plats-uppgraderingar av Windows 10 Enterprise använde Contoso följande lösningar i Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="682a6-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="682a6-114">Uppgraderingsberedskap</span><span class="sxs-lookup"><span data-stu-id="682a6-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="682a6-115">Samlar in system-, program- och drivrutinsdata för analys och identifierar kompatibilitetsproblem som kan blockera en uppgradering och förslag på problem som är kända för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="682a6-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="682a6-116">Uppdateringsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="682a6-116">Update Compliance</span></span>  

  <span data-ttu-id="682a6-117">Visar status för dina enheter med hänsyn till Windows-uppdateringarna, så att du kan se till att de är uppdaterade med de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="682a6-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="682a6-118">Enhetshälsotillstånd</span><span class="sxs-lookup"><span data-stu-id="682a6-118">Device Health</span></span>  

  <span data-ttu-id="682a6-119">Identifierar enheter som kraschar ofta och därför kan behöva återskapas eller ersättas samt drivrutiner som orsakar att enheten kraschar, med förslag på alternativa versioner av drivrutiner som kan minska antalet krascher.</span><span class="sxs-lookup"><span data-stu-id="682a6-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="682a6-120">Skickar meddelanden om informativa Windows-felkonfigurationer som skickar uppmaningar till slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="682a6-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="682a6-121">Contoso har en befintlig infrastruktur för Configuration Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="682a6-121">Contoso has an existing Configuration Manager (Current Branch) infrastructure.</span></span> <span data-ttu-id="682a6-122">Configuration Manager kan skalas för stora miljöer och tillhandahåller omfattande kontroll över installation, uppdateringar och inställningar.</span><span class="sxs-lookup"><span data-stu-id="682a6-122">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="682a6-123">Den har också inbyggda funktioner som gör det enklare och mer effektivt att distribuera och hantera Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="682a6-123">It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="682a6-124">Planeringsprocessen</span><span class="sxs-lookup"><span data-stu-id="682a6-124">Planning process</span></span>

<span data-ttu-id="682a6-125">Contoso använde uppgraderings beredskap i Windows Analytics för att fastställa uppsättningen installerade appar och deras kompatibilitet med Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="682a6-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="682a6-126">Distributionsprocess</span><span class="sxs-lookup"><span data-stu-id="682a6-126">Deployment process</span></span>

<span data-ttu-id="682a6-127">För att slutföra distributionen av på plats-uppgradering av Windows 10 Enterprise genomför Contoso följande process, som innehåller rekommendationer från Microsoft:</span><span class="sxs-lookup"><span data-stu-id="682a6-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="682a6-128">Aktiverad peer-cachelagring för Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="682a6-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="682a6-129">Anpassade Windows-paket som skapats utifrån avbildningarna från Volume Licensing Service Center.</span><span class="sxs-lookup"><span data-stu-id="682a6-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="682a6-130">Använde Configuration Manager för att distribuera Windows-paketen till distributions platser via nätverket och distribuerade versioner till de tre mellanliggande validerings-och distributions grupperna.</span><span class="sxs-lookup"><span data-stu-id="682a6-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="682a6-131">Genomförde bedömning av framgång för datorer och enheter i de tre ringarna för mellanlagring av verifiering och distribution med hjälp av enhetshälsotillstånd och lösningar för uppdateringsefterlevnad för Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="682a6-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="682a6-132">Baserat på Windows Analytics-informationen fastställde contoso vilken version av Windows 10 Enterprise som ska distribueras till hela distributions gruppen.</span><span class="sxs-lookup"><span data-stu-id="682a6-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="682a6-133">Körde Configuration Manager-aktivitetssekvensdistributioner för distribution av det valda Windows-paketet till den breda distributions gruppen.</span><span class="sxs-lookup"><span data-stu-id="682a6-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="682a6-134">Övervakade datorer och enheter i gruppen omfattande distributioner med hjälp av enhetens hälso-och uppdaterings lösningar för att åtgärda problem.</span><span class="sxs-lookup"><span data-stu-id="682a6-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="682a6-135">Det här är Contosos på plats-uppgradering och pågående uppdateringars distributionsarkitektur.</span><span class="sxs-lookup"><span data-stu-id="682a6-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contosos distributrionsinfrastruktur för Windows 10 Enterprise](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="682a6-137">Infrastrukturen består av:</span><span class="sxs-lookup"><span data-stu-id="682a6-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="682a6-138">Configuration Manager, som:</span><span class="sxs-lookup"><span data-stu-id="682a6-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="682a6-139">Hämtar avbildningar av Windows 10 Enterprise-paket från Microsoft Volume Licensing Center i Microsoft-nätverket.</span><span class="sxs-lookup"><span data-stu-id="682a6-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="682a6-140">Är den centrala administrationsplatsen för distributionspaket.</span><span class="sxs-lookup"><span data-stu-id="682a6-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="682a6-141">Regionala distributionsplatser som vanligtvis finns i Contosos regionala navkontor.</span><span class="sxs-lookup"><span data-stu-id="682a6-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="682a6-142">Windows-datorer och enheter på olika platser som tar emot och installerar distributions paket för uppgradering på plats eller fort löp ande uppdateringar baserat på grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="682a6-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="682a6-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="682a6-143">Next step</span></span>

<span data-ttu-id="682a6-144">Lär dig hur contoso utnyttjar sin Configuration Manager-infrastruktur för att [distribuera och hålla nuvarande Microsoft 365-appar för företag](contoso-o365pp.md) i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="682a6-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="682a6-145">Se även</span><span class="sxs-lookup"><span data-stu-id="682a6-145">See also</span></span>

[<span data-ttu-id="682a6-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="682a6-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="682a6-147">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="682a6-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="682a6-148">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="682a6-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
