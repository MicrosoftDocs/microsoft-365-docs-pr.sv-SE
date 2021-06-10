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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917646"
---
# <a name="work-with-app-control"></a><span data-ttu-id="5024b-103">Arbeta med appens kontroll</span><span class="sxs-lookup"><span data-stu-id="5024b-103">Work with app control</span></span>

<span data-ttu-id="5024b-104">När appkontrollen har distribuerats i din miljö har både du och Microsoft Hanterat skrivbord Har löpande ansvar.</span><span class="sxs-lookup"><span data-stu-id="5024b-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="5024b-105">Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare.</span><span class="sxs-lookup"><span data-stu-id="5024b-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="5024b-106">För att förbättra säkerheten bör alla appar vara kod signerade innan du släpper dem till användarna.</span><span class="sxs-lookup"><span data-stu-id="5024b-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="5024b-107">Utgivarens information innehåller information om undertecknaren.</span><span class="sxs-lookup"><span data-stu-id="5024b-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="5024b-108">Lägga till ett nytt program</span><span class="sxs-lookup"><span data-stu-id="5024b-108">Add a new app</span></span>

<span data-ttu-id="5024b-109">Följ de här anvisningarna om du vill lägga till en ny app:</span><span class="sxs-lookup"><span data-stu-id="5024b-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="5024b-110">Lägg till appen i [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="5024b-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="5024b-111">Distribuera programmet till valfri enhet i testringen.</span><span class="sxs-lookup"><span data-stu-id="5024b-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="5024b-112">Testa programmet enligt dina vanliga affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="5024b-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="5024b-113">Kontrollera Loggboken under **Application and Services Logs\Microsoft\Windows\AppLocker**, leta efter eventuella **8003-** eller **8006-händelser.**</span><span class="sxs-lookup"><span data-stu-id="5024b-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="5024b-114">Dessa händelser anger att appen blockeras.</span><span class="sxs-lookup"><span data-stu-id="5024b-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="5024b-115">Mer information om alla applåsningshändelser och deras innebörd finns i [Använda loggboken med AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="5024b-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="5024b-116">Om du hittar något av dessa händelser öppnar du en begäran om att signera med Microsoft Hanterat skrivbord Operations.</span><span class="sxs-lookup"><span data-stu-id="5024b-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="5024b-117">Lägga till (eller ta bort) en betrodd undertecknare</span><span class="sxs-lookup"><span data-stu-id="5024b-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="5024b-118">När du öppnar en begäran om undertecknaren måste du ange viktig information för utgivaren först.</span><span class="sxs-lookup"><span data-stu-id="5024b-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="5024b-119">Följ sedan de här anvisningarna:</span><span class="sxs-lookup"><span data-stu-id="5024b-119">Then follow these steps:</span></span>

1. <span data-ttu-id="5024b-120">[Samla information om utgivare](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="5024b-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="5024b-121">Öppna en biljett med Microsoft Hanterat skrivbord Åtgärder för att begära undertecknarregeln och ange följande information:</span><span class="sxs-lookup"><span data-stu-id="5024b-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="5024b-122">Programnamn</span><span class="sxs-lookup"><span data-stu-id="5024b-122">Application name</span></span> 
    - <span data-ttu-id="5024b-123">Programversion</span><span class="sxs-lookup"><span data-stu-id="5024b-123">Application version</span></span> 
    - <span data-ttu-id="5024b-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5024b-124">Description</span></span> 
    - <span data-ttu-id="5024b-125">Ändra typ ("lägg till" eller "ta bort")</span><span class="sxs-lookup"><span data-stu-id="5024b-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="5024b-126">Publisher information (till exempel: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="5024b-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="5024b-127">Följ samma steg om du vill ta bort förtroende för en app, men ange ändra **typ för att** ta *bort*.</span><span class="sxs-lookup"><span data-stu-id="5024b-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="5024b-128">Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:</span><span class="sxs-lookup"><span data-stu-id="5024b-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="5024b-129">Distributions grupp</span><span class="sxs-lookup"><span data-stu-id="5024b-129">Deployment group</span></span>  |<span data-ttu-id="5024b-130">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="5024b-130">Policy type</span></span>  |<span data-ttu-id="5024b-131">Tidsinställning</span><span class="sxs-lookup"><span data-stu-id="5024b-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5024b-132">Test</span><span class="sxs-lookup"><span data-stu-id="5024b-132">Test</span></span>     |  <span data-ttu-id="5024b-133">Granskning</span><span class="sxs-lookup"><span data-stu-id="5024b-133">Audit</span></span>       |  <span data-ttu-id="5024b-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="5024b-134">Day 0</span></span>       |
|<span data-ttu-id="5024b-135">Första</span><span class="sxs-lookup"><span data-stu-id="5024b-135">First</span></span>     | <span data-ttu-id="5024b-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="5024b-136">Enforced</span></span>        | <span data-ttu-id="5024b-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="5024b-137">Day 1</span></span>        |
|<span data-ttu-id="5024b-138">Snabbt</span><span class="sxs-lookup"><span data-stu-id="5024b-138">Fast</span></span>     | <span data-ttu-id="5024b-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="5024b-139">Enforced</span></span>        |  <span data-ttu-id="5024b-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="5024b-140">Day 2</span></span>       |
|<span data-ttu-id="5024b-141">Bred</span><span class="sxs-lookup"><span data-stu-id="5024b-141">Broad</span></span>     | <span data-ttu-id="5024b-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="5024b-142">Enforced</span></span>        |  <span data-ttu-id="5024b-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="5024b-143">Day 3</span></span>       |


<span data-ttu-id="5024b-144">Du kan pausa eller återställa distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="5024b-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="5024b-145">Det gör du genom att öppna en annan tjänstförfrågan med Drift.</span><span class="sxs-lookup"><span data-stu-id="5024b-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="5024b-146">Om du pausar lanseringen av en signeringsregel måste regeln antingen återställas eller slutföras innan en annan utrullning kan starta.</span><span class="sxs-lookup"><span data-stu-id="5024b-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="5024b-147">Samla information om utgivaren</span><span class="sxs-lookup"><span data-stu-id="5024b-147">Gather publisher details</span></span>

<span data-ttu-id="5024b-148">Gör så här för att få tillgång till publisher-data för ett program:</span><span class="sxs-lookup"><span data-stu-id="5024b-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="5024b-149">Hitta en Microsoft Hanterat skrivbord i testringen som har en princip för granskningsläge tillämpad.</span><span class="sxs-lookup"><span data-stu-id="5024b-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="5024b-150">Försök att installera appen på enheten.</span><span class="sxs-lookup"><span data-stu-id="5024b-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="5024b-151">Öppna Loggboken på enheten.</span><span class="sxs-lookup"><span data-stu-id="5024b-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="5024b-152">I Loggboken går du **till Application and Services Logs\Microsoft\Windows** och väljer sedan **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="5024b-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="5024b-153">Hitta en **8003-** eller **8006-händelse** och kopiera sedan information från händelsen:</span><span class="sxs-lookup"><span data-stu-id="5024b-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="5024b-154">Programnamn</span><span class="sxs-lookup"><span data-stu-id="5024b-154">Application name</span></span> 
    - <span data-ttu-id="5024b-155">Programversion</span><span class="sxs-lookup"><span data-stu-id="5024b-155">Application version</span></span> 
    - <span data-ttu-id="5024b-156">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5024b-156">Description</span></span> 
    - <span data-ttu-id="5024b-157">Publisher information (till exempel: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="5024b-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>