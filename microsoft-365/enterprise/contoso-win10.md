---
title: Windows 10 Enterprise-driftsättning för Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Endpoint Configuration Manager för att distribuera på plats-uppgraderingar av Windows 10 Enterprise.
ms.openlocfilehash: 5dc58a9090dd6976d7c521f7552181a10f22f5b2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810374"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="fec96-103">Windows 10 Enterprise-driftsättning för Contoso</span><span class="sxs-lookup"><span data-stu-id="fec96-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="fec96-104">Före lanseringen av Microsoft 365 Enterprise hade Contoso Windows-kompatibla datorer och enheter med en blandning av Windows 7 (10 %), Windows 8.1 (65 %) och Windows 10 (25 %).</span><span class="sxs-lookup"><span data-stu-id="fec96-104">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="fec96-105">Contoso ville uppgradera datorerna för Windows 10 Enterprise för att dra nytta av avancerad säkerhet och lägre IT-kostnader jämfört med automatiska distributioner av uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="fec96-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="fec96-106">Efter att ha uppskattat deras infrastruktur- och företagsbehov identifierade Contoso de viktigaste kraven för distributionen:</span><span class="sxs-lookup"><span data-stu-id="fec96-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="fec96-107">Så många datorer och enheter som möjligt skulle köra Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fec96-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="fec96-108">Lanseringen av på plats-uppgraderingar utnyttjar befintlig Configuration Manager-infrastruktur</span><span class="sxs-lookup"><span data-stu-id="fec96-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="fec96-109">Styr vilka versioner av Windows 10 Enterprise som ska distribueras och vilka uppdateringar som görs via ringar</span><span class="sxs-lookup"><span data-stu-id="fec96-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="fec96-110">Datorerna och enheterna ska vara uppdaterade med minimala IT-administrativa kostnader och minsta möjliga påverkan på slutanvändarna</span><span class="sxs-lookup"><span data-stu-id="fec96-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="fec96-111">Uppdaterat definieras som den version av Windows 10 Enterprise som stöds och som uppfyller organisationens affärsbehov, och det kan skilja sig från att ha alla Windows-kompatibla datorer med den senaste versionen av Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fec96-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="fec96-112">Distributionsverktyg</span><span class="sxs-lookup"><span data-stu-id="fec96-112">Deployment tools</span></span>

<span data-ttu-id="fec96-113">Före och under på plats-uppgraderingar av Windows 10 Enterprise använde Contoso följande lösningar i Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="fec96-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="fec96-114">Uppgraderingsberedskap</span><span class="sxs-lookup"><span data-stu-id="fec96-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="fec96-115">Samlar in system-, program- och drivrutinsdata för analys och identifierar kompatibilitetsproblem som kan blockera en uppgradering och förslag på problem som är kända för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec96-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="fec96-116">Uppdateringsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fec96-116">Update Compliance</span></span>  

  <span data-ttu-id="fec96-117">Visar status för dina enheter med hänsyn till Windows-uppdateringarna, så att du kan se till att de är uppdaterade med de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="fec96-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="fec96-118">Enhetshälsotillstånd</span><span class="sxs-lookup"><span data-stu-id="fec96-118">Device Health</span></span>  

  <span data-ttu-id="fec96-119">Identifierar enheter som kraschar ofta och därför kan behöva återskapas eller ersättas samt drivrutiner som orsakar att enheten kraschar, med förslag på alternativa versioner av drivrutiner som kan minska antalet krascher.</span><span class="sxs-lookup"><span data-stu-id="fec96-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="fec96-120">Skickar meddelanden om informativa Windows-felkonfigurationer som skickar uppmaningar till slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="fec96-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="fec96-121">Contoso har en befintlig infrastruktur för Configuration Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="fec96-121">Contoso has an existing Configuration Manager (Current Branch) infrastructure.</span></span> <span data-ttu-id="fec96-122">Configuration Manager kan skalas för stora miljöer och tillhandahåller omfattande kontroll över installation, uppdateringar och inställningar.</span><span class="sxs-lookup"><span data-stu-id="fec96-122">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="fec96-123">Den har också inbyggda funktioner som gör det enklare och mer effektivt att distribuera och hantera Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fec96-123">It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="fec96-124">Planeringsprocessen</span><span class="sxs-lookup"><span data-stu-id="fec96-124">Planning process</span></span>

<span data-ttu-id="fec96-125">Före distributionen definierade Contoso följande ringar:</span><span class="sxs-lookup"><span data-stu-id="fec96-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="fec96-126">Tre ringar för mellanlagring av verifiering och distribution</span><span class="sxs-lookup"><span data-stu-id="fec96-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="fec96-127">En för förhandsversioner</span><span class="sxs-lookup"><span data-stu-id="fec96-127">One for preview builds</span></span> 
  - <span data-ttu-id="fec96-128">En för nya versioner</span><span class="sxs-lookup"><span data-stu-id="fec96-128">One for new release builds</span></span>
  - <span data-ttu-id="fec96-129">En för tidigare versioner</span><span class="sxs-lookup"><span data-stu-id="fec96-129">One for a previous build</span></span> 
- <span data-ttu-id="fec96-130">En enda ring för bred distribution av Windows 10 Enterprise baserat på data från verifieringsringarna</span><span class="sxs-lookup"><span data-stu-id="fec96-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="fec96-131">Contoso använde även uppgraderingsberedskap för Windows Analytics för att avgöra vilka appar som är installerade och deras kompatibilitet med Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fec96-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="fec96-132">Distributionsprocess</span><span class="sxs-lookup"><span data-stu-id="fec96-132">Deployment process</span></span>

<span data-ttu-id="fec96-133">För att slutföra distributionen av på plats-uppgradering av Windows 10 Enterprise genomför Contoso följande process, som innehåller rekommendationer från Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fec96-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="fec96-134">Aktiverad peer-cachelagring för Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fec96-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="fec96-135">Anpassade Windows-paket som skapats utifrån avbildningarna från Volume Licensing Service Center.</span><span class="sxs-lookup"><span data-stu-id="fec96-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="fec96-136">Använde Configuration Manager för distribution av Windows-paket till distributionsplatser via nätverket och distribuerade versioner till de tre ringar för mellanlagring av verifiering och distribution.</span><span class="sxs-lookup"><span data-stu-id="fec96-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="fec96-137">Genomförde bedömning av framgång för datorer och enheter i de tre ringarna för mellanlagring av verifiering och distribution med hjälp av enhetshälsotillstånd och lösningar för uppdateringsefterlevnad för Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="fec96-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="fec96-138">Baserat på Windows Analytics-information fastställde Contoso versionen av Windows 10 Enterprise för distribution till den breda distributionsringen.</span><span class="sxs-lookup"><span data-stu-id="fec96-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="fec96-139">Körde Configuration Manager-aktivitetssekvenser för distribution för att distribuera det valda Windows-paketet till den breda distributionsringen.</span><span class="sxs-lookup"><span data-stu-id="fec96-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="fec96-140">Övervakade datorer och enheter i den breda distributionsringen som använder lösningar för enhetens hälsotillstånd och uppdateringsefterlevnad för att lösa problem.</span><span class="sxs-lookup"><span data-stu-id="fec96-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="fec96-141">Det här är Contosos på plats-uppgradering och pågående uppdateringars distributionsarkitektur.</span><span class="sxs-lookup"><span data-stu-id="fec96-141">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contosos distributrionsinfrastruktur för Windows 10 Enterprise](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="fec96-143">Infrastrukturen består av:</span><span class="sxs-lookup"><span data-stu-id="fec96-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="fec96-144">Configuration Manager, som:</span><span class="sxs-lookup"><span data-stu-id="fec96-144">Configuration Manager, which:</span></span>
  - <span data-ttu-id="fec96-145">Hämtar avbildningar av Windows 10 Enterprise-paket från Microsoft Volume Licensing Center i Microsoft-nätverket.</span><span class="sxs-lookup"><span data-stu-id="fec96-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="fec96-146">Är den centrala administrationsplatsen för distributionspaket.</span><span class="sxs-lookup"><span data-stu-id="fec96-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="fec96-147">Regionala distributionsplatser som vanligtvis finns i Contosos regionala navkontor.</span><span class="sxs-lookup"><span data-stu-id="fec96-147">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="fec96-148">Windows-datorer och -enheter på olika platser som tar emot och installerar distributionspaket för på plats-uppgraderingar eller pågående uppdateringar baserat på ringtillhörighet.</span><span class="sxs-lookup"><span data-stu-id="fec96-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="fec96-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fec96-149">Next step</span></span>

<span data-ttu-id="fec96-150">[Ta reda på mer](contoso-o365pp.md) om hur Contoso använder sin Configuration Manager-infrastruktur för att distribuera och hålla Office 365 ProPlus uppdaterat i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fec96-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="fec96-151">Se även</span><span class="sxs-lookup"><span data-stu-id="fec96-151">See also</span></span>

[<span data-ttu-id="fec96-152">Windows 10 Enterprise för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fec96-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="fec96-153">Distributionsguide</span><span class="sxs-lookup"><span data-stu-id="fec96-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fec96-154">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="fec96-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
