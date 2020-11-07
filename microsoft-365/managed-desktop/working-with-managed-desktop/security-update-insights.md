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
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941447"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="3620f-103">Insikter om Windows-säkerhetsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="3620f-103">Windows security update insights</span></span>
<span data-ttu-id="3620f-104">Den här vyn innehåller en översikt över status för säkerhets uppdateringar för Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="3620f-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="3620f-105">Om du vill visa användnings data väljer du fliken <strong>Windows säkerhets uppdateringar</strong> .</span><span class="sxs-lookup"><span data-stu-id="3620f-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows säkerhets uppdaterings fönster: stapel-grafer med enhets status och uppdatera version i vänster kolumn, uppdatera distributions förloppet över tid i mitten och procent av aktiva enheter efter distributions grupp, samt antalet dagar för att nå distributions mål för 95% i höger kolumn.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="3620f-107">Enhets status</span><span class="sxs-lookup"><span data-stu-id="3620f-107">Device status</span></span>

<span data-ttu-id="3620f-108">För att enheter ska uppdateras av Windows Update måste de vara anslutna till Internet och inte försätts i vilo läge i minst sex timmar, två av dessa måste vara löpande.</span><span class="sxs-lookup"><span data-stu-id="3620f-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="3620f-109">Även om det är möjligt att en enhet som inte uppfyller dessa krav kommer att uppdateras, att enheter som uppfyller dem har högsta sannolikhet för att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="3620f-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="3620f-110">Vi kategoriserar enhets aktivitet i Windows Update med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="3620f-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="3620f-111"><strong>Aktivt:</strong> Enheter som har uppnått de lägsta aktivitets villkoren (sex timmar, två löpande) för den senaste säkerhets uppdateringen och har checkat in med Microsoft Intune minst var femte dag</span><span class="sxs-lookup"><span data-stu-id="3620f-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="3620f-112"><strong>Synkroniserat:</strong> Enheter som har checkat in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="3620f-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="3620f-113">Inte <strong>synkroniserat:</strong> Enheter som <i>inte</i> har checkats in med Intune under de senaste 28 dagarna</span><span class="sxs-lookup"><span data-stu-id="3620f-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="3620f-114">Uppdatera versions status</span><span class="sxs-lookup"><span data-stu-id="3620f-114">Update version status</span></span>

<span data-ttu-id="3620f-115">Microsoft publicerar säkerhets uppdateringar varannan tisdag i månaden.</span><span class="sxs-lookup"><span data-stu-id="3620f-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="3620f-116">Varje utgåva innehåller viktiga uppdateringar för kända säkerhets problem.</span><span class="sxs-lookup"><span data-stu-id="3620f-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="3620f-117">Microsoft Managed Desktop säkerställer att 95% av dess hanterade enheter uppdateras med de senaste tillgängliga säkerhets uppdateringarna varje månad.</span><span class="sxs-lookup"><span data-stu-id="3620f-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="3620f-118">Säkerhets uppdateringar släpps ibland vid andra tillfällen för att snarast adressera nya hot.</span><span class="sxs-lookup"><span data-stu-id="3620f-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="3620f-119">Microsoft Managed Desktop distribuerar dessa uppdateringar på liknande sätt.</span><span class="sxs-lookup"><span data-stu-id="3620f-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="3620f-120">Vi kategoriserar statusen för säkerhets uppdaterings versioner med dessa villkor:</span><span class="sxs-lookup"><span data-stu-id="3620f-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="3620f-121"><strong>Nuvarande:</strong> Enheter som kör uppdateringen släpptes under den aktuella månaden</span><span class="sxs-lookup"><span data-stu-id="3620f-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="3620f-122"><strong>Föregående:</strong> Enheter som kör uppdateringen som släpptes under den föregående månaden</span><span class="sxs-lookup"><span data-stu-id="3620f-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="3620f-123"><strong>Äldre:</strong> Enheter med säkerhets uppdateringar som släpps före den föregående månaden</span><span class="sxs-lookup"><span data-stu-id="3620f-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="3620f-124">Du bör se få enheter i den <strong>äldre</strong> kategorin – en stor eller växande population indikerar antagligen ett systemfel som du bör rapportera till Microsoft Managed Desktop så att vi kan undersöka det.</span><span class="sxs-lookup"><span data-stu-id="3620f-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="3620f-125">Distributions förlopp</span><span class="sxs-lookup"><span data-stu-id="3620f-125">Deployment progress</span></span>

<span data-ttu-id="3620f-126">I början av varje version för säkerhets uppdatering tar Microsoft Managed Desktop en ögonblicks bild av enhets populationen och anger dess drift sättnings mål till 95% av populationen.</span><span class="sxs-lookup"><span data-stu-id="3620f-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="3620f-127">I området <strong>distributions förlopp</strong> visas en historisk trend, uppdaterad varje dag, och här följer en genom gång av hur nära uppdaterings distributionen uppfyller detta mål för varje utgåva.</span><span class="sxs-lookup"><span data-stu-id="3620f-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="3620f-128">I det här diagrammet visas endast enheter med aktiv status.</span><span class="sxs-lookup"><span data-stu-id="3620f-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="3620f-129">Du kan visa dessa data för föregående uppdaterings cykler genom att använda den nedrullningsbara menyn i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="3620f-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="3620f-130">Den period som du väljer i den här menyn gäller för all information på hela sidan.</span><span class="sxs-lookup"><span data-stu-id="3620f-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="3620f-131">I området för <strong>uppdaterade aktiva enheter efter distributions grupp</strong> kan du se hur uppdateringen fortskrider för var och en av de olika distributions grupperna för Microsoft Managed Station.</span><span class="sxs-lookup"><span data-stu-id="3620f-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="3620f-132">I <strong>mål</strong> området visas hur lång tid det tog för 95% av totalt antal enheter att uppdateras med den aktuella säkerhets uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="3620f-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="3620f-133">När distributionen pågår visas det <strong>fortfarande</strong> i det här området tills 95%-målet nås för den valda uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="3620f-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="3620f-134">Området enhets information</span><span class="sxs-lookup"><span data-stu-id="3620f-134">Device details area</span></span>

<span data-ttu-id="3620f-135">Instrument panelens nederkant är en tabell med detaljerad information för dina enheter, inklusive [enhets status](#device-status) och status för [uppdaterings version](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="3620f-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="3620f-136">Du kan söka i den här listan eller filtrera den med något av de angivna värdena.</span><span class="sxs-lookup"><span data-stu-id="3620f-136">You can search this list or filter it by any listed value.</span></span>


![Enhets informations tabell med kolumner för enhets namn, tilldelad användare, enhets status, uppdatering version, operativ system version och datum då enheten senast synkroniserades.](../../media/security-update-insights-device-table-sterile.png)
