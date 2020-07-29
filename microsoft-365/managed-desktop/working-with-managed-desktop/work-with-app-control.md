---
title: Arbeta med appens kontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430453"
---
# <a name="work-with-app-control"></a><span data-ttu-id="96288-103">Arbeta med appens kontroll</span><span class="sxs-lookup"><span data-stu-id="96288-103">Work with app control</span></span>

<span data-ttu-id="96288-104">När appkontrollen har distribuerats i din miljö har både du och Microsoft Managed Desktop Operations kontinuerligt ansvar.</span><span class="sxs-lookup"><span data-stu-id="96288-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="96288-105">Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare.</span><span class="sxs-lookup"><span data-stu-id="96288-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="96288-106">För att förbättra säkerheten bör alla appar vara kodsignerade innan du släpper dem till slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="96288-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="96288-107">En apps utgivarinformation innehåller information om undertecknaren.</span><span class="sxs-lookup"><span data-stu-id="96288-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="96288-108">Lägga till en ny app</span><span class="sxs-lookup"><span data-stu-id="96288-108">Add a new app</span></span>

<span data-ttu-id="96288-109">Så här lägger du till en ny app:</span><span class="sxs-lookup"><span data-stu-id="96288-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="96288-110">Lägg till appen [i Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="96288-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="96288-111">Distribuera appen till valfri enhet i testringen.</span><span class="sxs-lookup"><span data-stu-id="96288-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="96288-112">Testa din app enligt dina vanliga affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="96288-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="96288-113">Kontrollera Loggboken under **Program- och tjänstloggar\Microsoft\Windows\AppLocker**och leta efter eventuella **8003-** eller **8006-händelser.**</span><span class="sxs-lookup"><span data-stu-id="96288-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="96288-114">Dessa händelser indikerar att appen skulle blockeras.</span><span class="sxs-lookup"><span data-stu-id="96288-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="96288-115">Mer information om alla App Locker-händelser och deras betydelser finns i [Använda Loggboken med AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="96288-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="96288-116">Om du hittar någon av dessa händelser öppnar du en undertecknarbegäran med Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="96288-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="96288-117">Lägga till (eller ta bort) en betrodd undertecknare</span><span class="sxs-lookup"><span data-stu-id="96288-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="96288-118">När du öppnar en undertecknarbegäran måste du ange viktig information om utgivaren först.</span><span class="sxs-lookup"><span data-stu-id="96288-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="96288-119">Följ sedan dessa steg:</span><span class="sxs-lookup"><span data-stu-id="96288-119">Then follow these steps:</span></span>

1. <span data-ttu-id="96288-120">[Samla in information om utgivare](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="96288-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="96288-121">Öppna en biljett med Microsoft Managed Desktop Operations för att begära undertecknarregeln och inkludera följande information:</span><span class="sxs-lookup"><span data-stu-id="96288-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="96288-122">Programnamn</span><span class="sxs-lookup"><span data-stu-id="96288-122">Application name</span></span> 
    - <span data-ttu-id="96288-123">Programversion</span><span class="sxs-lookup"><span data-stu-id="96288-123">Application version</span></span> 
    - <span data-ttu-id="96288-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96288-124">Description</span></span> 
    - <span data-ttu-id="96288-125">Ändra typ ("lägg till" eller "ta bort")</span><span class="sxs-lookup"><span data-stu-id="96288-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="96288-126">Information om utgivare (till exempel : "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="96288-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="96288-127">Om du vill ta bort förtroendet för en app följer du samma steg, men anger **Ändra typ** för att *ta bort*.</span><span class="sxs-lookup"><span data-stu-id="96288-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="96288-128">Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:</span><span class="sxs-lookup"><span data-stu-id="96288-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="96288-129">Distributions grupp</span><span class="sxs-lookup"><span data-stu-id="96288-129">Deployment group</span></span>  |<span data-ttu-id="96288-130">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="96288-130">Policy type</span></span>  |<span data-ttu-id="96288-131">Timing</span><span class="sxs-lookup"><span data-stu-id="96288-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="96288-132">Test</span><span class="sxs-lookup"><span data-stu-id="96288-132">Test</span></span>     |  <span data-ttu-id="96288-133">Revision</span><span class="sxs-lookup"><span data-stu-id="96288-133">Audit</span></span>       |  <span data-ttu-id="96288-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="96288-134">Day 0</span></span>       |
|<span data-ttu-id="96288-135">Första</span><span class="sxs-lookup"><span data-stu-id="96288-135">First</span></span>     | <span data-ttu-id="96288-136">Verkställas</span><span class="sxs-lookup"><span data-stu-id="96288-136">Enforced</span></span>        | <span data-ttu-id="96288-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="96288-137">Day 1</span></span>        |
|<span data-ttu-id="96288-138">Snabb</span><span class="sxs-lookup"><span data-stu-id="96288-138">Fast</span></span>     | <span data-ttu-id="96288-139">Verkställas</span><span class="sxs-lookup"><span data-stu-id="96288-139">Enforced</span></span>        |  <span data-ttu-id="96288-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="96288-140">Day 2</span></span>       |
|<span data-ttu-id="96288-141">Bred</span><span class="sxs-lookup"><span data-stu-id="96288-141">Broad</span></span>     | <span data-ttu-id="96288-142">Verkställas</span><span class="sxs-lookup"><span data-stu-id="96288-142">Enforced</span></span>        |  <span data-ttu-id="96288-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="96288-143">Day 3</span></span>       |


<span data-ttu-id="96288-144">Du kan pausa eller återställa distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="96288-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="96288-145">Det gör du genom att öppna en annan tjänstbegäran med åtgärder.</span><span class="sxs-lookup"><span data-stu-id="96288-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="96288-146">Om du pausar frisättningen av en undertecknarregel måste den regeln antingen återställas eller slutföras innan en annan distribution kan starta.</span><span class="sxs-lookup"><span data-stu-id="96288-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="96288-147">Samla in information om utgivare</span><span class="sxs-lookup"><span data-stu-id="96288-147">Gather publisher details</span></span>

<span data-ttu-id="96288-148">Så här kommer du åt utgivardata för en app:</span><span class="sxs-lookup"><span data-stu-id="96288-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="96288-149">Hitta en Microsoft-hanterad skrivbordsenhet i testringen som har en princip för granskningsläge tillämpad.</span><span class="sxs-lookup"><span data-stu-id="96288-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="96288-150">Försök att installera appen på enheten.</span><span class="sxs-lookup"><span data-stu-id="96288-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="96288-151">Öppna Loggboken på den enheten.</span><span class="sxs-lookup"><span data-stu-id="96288-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="96288-152">I Loggboken navigerar du till **program- och tjänstloggar\Microsoft\Windows**och väljer sedan **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="96288-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="96288-153">Hitta en händelse på **8003** eller **8006** och kopiera sedan information från evenemanget:</span><span class="sxs-lookup"><span data-stu-id="96288-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="96288-154">Programnamn</span><span class="sxs-lookup"><span data-stu-id="96288-154">Application name</span></span> 
    - <span data-ttu-id="96288-155">Programversion</span><span class="sxs-lookup"><span data-stu-id="96288-155">Application version</span></span> 
    - <span data-ttu-id="96288-156">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96288-156">Description</span></span> 
    - <span data-ttu-id="96288-157">Information om utgivare (till exempel: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="96288-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
