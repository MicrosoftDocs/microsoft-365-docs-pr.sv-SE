---
title: Insikter om Windows-säkerhetsuppdateringar
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739840"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="f6a8d-103">Insikter om Windows-säkerhetsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f6a8d-103">Windows security update insights</span></span>
<span data-ttu-id="f6a8d-104">Den här vyn ger en översikt över statusen för säkerhetsuppdateringar för dina Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="f6a8d-105">Om du vill visa användningsdata väljer <strong>Windows fliken Säkerhetsuppdateringar.</strong></span><span class="sxs-lookup"><span data-stu-id="f6a8d-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows fönstret för säkerhetsuppdateringar: stapeldiagram över enhetsstatus och uppdateringsversion i den vänstra kolumnen, uppdateringsdistributionsförloppet över tiden i kolumnen Mitt och procentandel av aktiva enheter efter distributionsgrupp, samt antalet dagar det tar att nå distributionsmålet på 95 % i den högra kolumnen.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="f6a8d-107">Enhetsstatus</span><span class="sxs-lookup"><span data-stu-id="f6a8d-107">Device status</span></span>

<span data-ttu-id="f6a8d-108">För att enheter ska uppdateras genom Windows Update måste de vara anslutna till Internet och inte gå in i viloläge i minst sex timmar, av vilka två måste vara kontinuerliga.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="f6a8d-109">Även om det är möjligt att en enhet som inte uppfyller dessa krav kommer att uppdateras, kommer enheter som uppfyller dem att ha störst sannolikhet för att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="f6a8d-110">Vi kategoriserar enhetsaktivitet i samband med Windows med följande termer:</span><span class="sxs-lookup"><span data-stu-id="f6a8d-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="f6a8d-111"><strong>Aktiv:</strong> Enheter som har uppfyllt minimikravet för aktivitet (sex timmar, två i kontinuerligt) för den senaste säkerhetsuppdateringen och som har checkat in med Microsoft Intune minst var femte dag</span><span class="sxs-lookup"><span data-stu-id="f6a8d-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="f6a8d-112"><strong>Synkroniserat:</strong> Enheter som har checkat in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="f6a8d-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="f6a8d-113"><strong>Inte synkroniserad:</strong> Enheter som inte <i>har checkat</i> in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="f6a8d-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="f6a8d-114">Uppdatera versionsstatus</span><span class="sxs-lookup"><span data-stu-id="f6a8d-114">Update version status</span></span>

<span data-ttu-id="f6a8d-115">Microsoft släpper säkerhetsuppdateringar varannan tisdag i månaden.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="f6a8d-116">Varje version lägger till viktiga uppdateringar för kända säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="f6a8d-117">Microsoft Hanterat skrivbord ser till att 95 % av alla hanterade enheter uppdateras med den senaste tillgängliga säkerhetsuppdateringen varje månad.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="f6a8d-118">Säkerhetsuppdateringar släpps ibland vid andra tillfällen för att brådskande hantera nya hot.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="f6a8d-119">Microsoft Hanterat skrivbord distribuerar uppdateringarna på ett liknande sätt.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="f6a8d-120">Vi kategoriserar statusen för versioner av säkerhetsuppdateringar med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f6a8d-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="f6a8d-121"><strong>Aktuell:</strong> Enheter som kör uppdateringen som släpptes under den aktuella månaden</span><span class="sxs-lookup"><span data-stu-id="f6a8d-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="f6a8d-122"><strong>Föregående:</strong> Enheter som kör uppdateringen som släpptes under föregående månad</span><span class="sxs-lookup"><span data-stu-id="f6a8d-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="f6a8d-123"><strong>Äldre:</strong> Enheter som kör en säkerhetsuppdatering som släppts före föregående månad</span><span class="sxs-lookup"><span data-stu-id="f6a8d-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="f6a8d-124">Du bör se några enheter i kategorin Äldre <strong>–</strong> en stor eller växande befolkning indikerar antagligen ett problem med att vara här och att du bör rapportera till Microsoft Hanterat skrivbord så att vi kan undersöka den.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="f6a8d-125">Distributionsstatus</span><span class="sxs-lookup"><span data-stu-id="f6a8d-125">Deployment progress</span></span>

<span data-ttu-id="f6a8d-126">I början av varje version av säkerhetsuppdateringen tar Microsoft Hanterat skrivbord en ögonblicksbild av enhetens population och anger dess distributionsmål till 95 % av populationen.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="f6a8d-127">I <strong>området Förlopp</strong> för distribution visas en historisk trend som uppdateras varje dag, med en uppföljning av hur nära uppdateringsdistributionen uppfyller detta mål för varje version.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="f6a8d-128">Det här diagrammet visar bara enheter med aktiv status.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="f6a8d-129">Du kan visa informationen för tidigare uppdateringscykler med hjälp av den nedrullningsbara menyn i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="f6a8d-130">Den period du väljer i den här menyn gäller för all information på hela sidan.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="f6a8d-131">Området <strong>Uppdaterade aktiva enheter efter</strong> distributionsgrupp erbjuder en annan vy genom att visa förloppet för uppdateringsinstallationen för var och en Microsoft Hanterat skrivbord distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="f6a8d-132">I <strong>området Dagar att nå</strong> mål visar hur lång tid det tog för 95 % av det totala antalet enheter att uppdateras med den aktuella säkerhetsuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="f6a8d-133">Medan distributionen pågår visas fortfarande uppdatering i det här <strong>området tills</strong> 95 % målet har nåtts för den valda uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="f6a8d-134">Området Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="f6a8d-134">Device details area</span></span>

<span data-ttu-id="f6a8d-135">Längst ned på instrumentpanelen finns en tabell med detaljerad information om dina enheter, till exempel [enhetsstatus](#device-status) och [uppdateringsversionsstatus.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="f6a8d-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="f6a8d-136">Du kan söka i listan eller filtrera den efter vilket värde som helst.</span><span class="sxs-lookup"><span data-stu-id="f6a8d-136">You can search this list or filter it by any listed value.</span></span>


![Enhetsinformationstabell med kolumner för enhetsnamn, tilldelad användare, enhetsstatus, uppdateringsversion, operativsystemsversion och det datum då enheten senast synkroniserades.](../../media/security-update-insights-device-table-sterile.png)
