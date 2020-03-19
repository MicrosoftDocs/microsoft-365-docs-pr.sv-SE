---
title: Insikter om Windows-säkerhetsuppdateringar
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42809457"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="f96f2-103">Insikter om Windows-säkerhetsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f96f2-103">Windows security update insights</span></span>
<span data-ttu-id="f96f2-104">Den här vyn innehåller en översikt över statusen för säkerhetsuppdateringar för dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="f96f2-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="f96f2-105">Om du vill visa användningsdata väljer du fliken Säkerhetsuppdateringar i <strong>Windows.</strong></span><span class="sxs-lookup"><span data-stu-id="f96f2-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Fönstret Windows säkerhetsuppdateringar: stapeldiagram över enhetsstatus och uppdateringsversion i vänster kolumn, uppdatera distributionsförloppet över tid i mittkolumnen och procentandel av aktiva enheter efter distributionsgrupp, samt antalet dagar som har gjorts för att nå 95%-distributionen mål i höger kolumn.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="f96f2-107">Enhetsstatus</span><span class="sxs-lookup"><span data-stu-id="f96f2-107">Device status</span></span>

<span data-ttu-id="f96f2-108">För att enheter ska kunna uppdateras av Windows Update måste de vara anslutna till Internet och inte vara i viloläge i minst sex timmar, varav två måste vara kontinuerliga.</span><span class="sxs-lookup"><span data-stu-id="f96f2-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="f96f2-109">Så länge en enhet är ansluten och inte övervintrar, anses den vara "i bruk".</span><span class="sxs-lookup"><span data-stu-id="f96f2-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="f96f2-110">Även om det är möjligt att en enhet som inte uppfyller dessa krav kommer att uppdateras, har enheter som uppfyller dem den största sannolikheten för att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f96f2-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="f96f2-111">Vi kategoriserar enhetsaktivitet i samband med Windows Update med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f96f2-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="f96f2-112"><strong>Aktiv:</strong> Enheter som har uppfyllt minimianvändningskriterierna (sex timmar, två kontinuerliga) för den senaste säkerhetsuppdateringsversionen och har checkat in med Microsoft Intune minst var femte dag</span><span class="sxs-lookup"><span data-stu-id="f96f2-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="f96f2-113"><strong>Synkroniserad:</strong> Enheter som har checkat in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="f96f2-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="f96f2-114"><strong>Osynkroniserad:</strong> Enheter som <i>inte</i> har checkat in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="f96f2-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="f96f2-115">Status för uppdateringsversionen</span><span class="sxs-lookup"><span data-stu-id="f96f2-115">Update version status</span></span>

<span data-ttu-id="f96f2-116">Microsoft släpper säkerhetsuppdateringar varannan tisdag i månaden.</span><span class="sxs-lookup"><span data-stu-id="f96f2-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="f96f2-117">Varje utgåva lägger till viktiga uppdateringar för kända säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="f96f2-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="f96f2-118">Microsoft Managed Desktop säkerställer att 95 % av dess hanterade enheter uppdateras med den senaste tillgängliga säkerhetsuppdateringen varje månad.</span><span class="sxs-lookup"><span data-stu-id="f96f2-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="f96f2-119">Säkerhetsuppdateringar släpps ibland vid andra tillfällen för att snabbt ta itu med nya hot.</span><span class="sxs-lookup"><span data-stu-id="f96f2-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="f96f2-120">Microsoft Managed Desktop distribuerar dessa uppdateringar på ett liknande sätt.</span><span class="sxs-lookup"><span data-stu-id="f96f2-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="f96f2-121">Vi kategoriserar status för säkerhetsuppdateringsversioner med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="f96f2-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="f96f2-122"><strong>Aktuell:</strong> Enheter som kör uppdateringen som släpps under den aktuella månaden</span><span class="sxs-lookup"><span data-stu-id="f96f2-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="f96f2-123"><strong>Föregående:</strong> Enheter som kör uppdateringen som släpptes föregående månad</span><span class="sxs-lookup"><span data-stu-id="f96f2-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="f96f2-124"><strong>Äldre:</strong> Enheter som kör någon säkerhetsuppdatering som släpptes före föregående månad</span><span class="sxs-lookup"><span data-stu-id="f96f2-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="f96f2-125">Du bör se få enheter i kategorin <strong>Äldre</strong> – en stor eller växande population indikerar förmodligen ett systemproblem som du bör rapportera till Microsoft Managed Desktop så att vi kan undersöka.</span><span class="sxs-lookup"><span data-stu-id="f96f2-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="f96f2-126">Förloppet för distribution</span><span class="sxs-lookup"><span data-stu-id="f96f2-126">Deployment progress</span></span>

<span data-ttu-id="f96f2-127">I början av varje startcykel för säkerhetsuppdateringar tar Microsoft Managed Desktop en ögonblicksbild av enhetspopulationen och anger sitt distributionsmål till 95 % av den populationen.</span><span class="sxs-lookup"><span data-stu-id="f96f2-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="f96f2-128"><strong>Området Förlopp för distribution</strong> visar en historisk trend, uppdaterad dagligen, som spårar hur nära uppdateringsdistributionen uppfyller det här målet för varje version.</span><span class="sxs-lookup"><span data-stu-id="f96f2-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="f96f2-129">Det här diagrammet visar bara enheter med aktiv status.</span><span class="sxs-lookup"><span data-stu-id="f96f2-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="f96f2-130">Du kan visa dessa data för tidigare uppdateringscykler med hjälp av rullgardinsmenyn längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="f96f2-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="f96f2-131">Den period du väljer i den här menyn gäller för all information på hela sidan.</span><span class="sxs-lookup"><span data-stu-id="f96f2-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="f96f2-132">Det <strong>uppdaterade aktiva enheterna efter distributionsgruppsområdet</strong> ger en annan vy genom att visa förloppet för uppdateringsinstallationen för var och en av distributionsgrupperna för Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f96f2-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="f96f2-133">Området <strong>Dagar för att nå mål</strong> visar hur lång tid det tog för 95 % av det totala antalet enheter som ska uppdateras med den aktuella säkerhetsuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="f96f2-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="f96f2-134">När distributionen pågår visas <strong>stilluppdatering</strong> fortfarande tills 95% målet har uppnåtts för den valda uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="f96f2-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="f96f2-135">Området för enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="f96f2-135">Device details area</span></span>

<span data-ttu-id="f96f2-136">Längst ned på instrumentpanelen finns en tabell som visar detaljerad information för dina enheter, inklusive [enhetsstatus](#device-status) och status för [uppdateringsversionen](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="f96f2-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="f96f2-137">Du kan söka i den här listan eller filtrera den efter valfritt värde i listan.</span><span class="sxs-lookup"><span data-stu-id="f96f2-137">You can search this list or filter it by any listed value.</span></span>


![Enhetsinformationstabell som visar kolumner för enhetsnamn, tilldelad användare, enhetsstatus, uppdateringsversion, operativsystemversion och det datum då enheten senast synkroniserades.](../../media/security-update-insights-device-table-sterile.png)
