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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289465"
---
# <a name="work-with-app-control"></a><span data-ttu-id="5226a-103">Arbeta med appens kontroll</span><span class="sxs-lookup"><span data-stu-id="5226a-103">Work with app control</span></span>

<span data-ttu-id="5226a-104">När app-kontrollen har distribuerats i din miljö har både du och Microsoft hanterade Skriv bords operationer kontinuerlig ansvar.</span><span class="sxs-lookup"><span data-stu-id="5226a-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="5226a-105">Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare.</span><span class="sxs-lookup"><span data-stu-id="5226a-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="5226a-106">För att förbättra säkerheten bör alla appar vara kodade innan de släpps till användarna.</span><span class="sxs-lookup"><span data-stu-id="5226a-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="5226a-107">Ett programs publicerings information innehåller information om undertecknaren.</span><span class="sxs-lookup"><span data-stu-id="5226a-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="5226a-108">Lägga till ett nytt program</span><span class="sxs-lookup"><span data-stu-id="5226a-108">Add a new app</span></span>

<span data-ttu-id="5226a-109">Följ de här stegen om du vill lägga till ett nytt program:</span><span class="sxs-lookup"><span data-stu-id="5226a-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="5226a-110">Lägg till programmet i [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="5226a-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="5226a-111">Distribuera appen till valfri enhet i test ringen.</span><span class="sxs-lookup"><span data-stu-id="5226a-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="5226a-112">Testa programmet enligt dina vanliga affärs processer.</span><span class="sxs-lookup"><span data-stu-id="5226a-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="5226a-113">Kontrol lera logg boken under **program-och Logs\Microsoft\Windows\AppLocker**, och leta efter eventuella **8003** -eller **8006** -händelser.</span><span class="sxs-lookup"><span data-stu-id="5226a-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="5226a-114">De här händelserna indikerar att programmet blockerades.</span><span class="sxs-lookup"><span data-stu-id="5226a-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="5226a-115">Mer information om alla program lås händelser och deras betydelser finns i [använda logg boken med AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="5226a-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="5226a-116">Om du hittar några av de här händelserna kan du öppna en undertecknare med Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="5226a-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="5226a-117">Lägga till (eller ta bort) en betrodd undertecknare</span><span class="sxs-lookup"><span data-stu-id="5226a-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="5226a-118">När du öppnar en undertecknare måste du ange viktig information om utgivaren först.</span><span class="sxs-lookup"><span data-stu-id="5226a-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="5226a-119">Gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="5226a-119">Then follow these steps:</span></span>

1. <span data-ttu-id="5226a-120">[Samla in information om utgivaren](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="5226a-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="5226a-121">Öppna en biljett med Microsoft Managed Station ära datorer för att begära undertecknarens regel och ange följande information:</span><span class="sxs-lookup"><span data-stu-id="5226a-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="5226a-122">Program namn</span><span class="sxs-lookup"><span data-stu-id="5226a-122">Application name</span></span> 
    - <span data-ttu-id="5226a-123">Program version</span><span class="sxs-lookup"><span data-stu-id="5226a-123">Application version</span></span> 
    - <span data-ttu-id="5226a-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5226a-124">Description</span></span> 
    - <span data-ttu-id="5226a-125">Ändra typ ("Lägg till" eller "ta bort")</span><span class="sxs-lookup"><span data-stu-id="5226a-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="5226a-126">Information om utgivaren (till exempel: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="5226a-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="5226a-127">Om du vill ta bort förtroendet för ett program följer du samma steg, men ange **ändra typ** för att *ta bort*.</span><span class="sxs-lookup"><span data-stu-id="5226a-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="5226a-128">Operationer distribuerar automatiskt principer till distributions grupper enligt det här schemat:</span><span class="sxs-lookup"><span data-stu-id="5226a-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="5226a-129">Distributions grupp</span><span class="sxs-lookup"><span data-stu-id="5226a-129">Deployment group</span></span>  |<span data-ttu-id="5226a-130">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="5226a-130">Policy type</span></span>  |<span data-ttu-id="5226a-131">Avseende</span><span class="sxs-lookup"><span data-stu-id="5226a-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5226a-132">Tävlingar</span><span class="sxs-lookup"><span data-stu-id="5226a-132">Test</span></span>     |  <span data-ttu-id="5226a-133">Revisions</span><span class="sxs-lookup"><span data-stu-id="5226a-133">Audit</span></span>       |  <span data-ttu-id="5226a-134">Dag 0</span><span class="sxs-lookup"><span data-stu-id="5226a-134">Day 0</span></span>       |
|<span data-ttu-id="5226a-135">Skapas</span><span class="sxs-lookup"><span data-stu-id="5226a-135">First</span></span>     | <span data-ttu-id="5226a-136">Tvingande</span><span class="sxs-lookup"><span data-stu-id="5226a-136">Enforced</span></span>        | <span data-ttu-id="5226a-137">Dag 1</span><span class="sxs-lookup"><span data-stu-id="5226a-137">Day 1</span></span>        |
|<span data-ttu-id="5226a-138">Snabbspola</span><span class="sxs-lookup"><span data-stu-id="5226a-138">Fast</span></span>     | <span data-ttu-id="5226a-139">Tvingande</span><span class="sxs-lookup"><span data-stu-id="5226a-139">Enforced</span></span>        |  <span data-ttu-id="5226a-140">Dag 2</span><span class="sxs-lookup"><span data-stu-id="5226a-140">Day 2</span></span>       |
|<span data-ttu-id="5226a-141">Personer</span><span class="sxs-lookup"><span data-stu-id="5226a-141">Broad</span></span>     | <span data-ttu-id="5226a-142">Tvingande</span><span class="sxs-lookup"><span data-stu-id="5226a-142">Enforced</span></span>        |  <span data-ttu-id="5226a-143">Dag 3</span><span class="sxs-lookup"><span data-stu-id="5226a-143">Day 3</span></span>       |


<span data-ttu-id="5226a-144">Du kan pausa eller återställa distributionen när som helst under installationen.</span><span class="sxs-lookup"><span data-stu-id="5226a-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="5226a-145">Det gör du genom att öppna en annan tjänstbegäran med operationer.</span><span class="sxs-lookup"><span data-stu-id="5226a-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="5226a-146">Om du pausar utgivningen av en signerings regel måste den regeln antingen ångras eller slutföras innan en ny installation kan startas.</span><span class="sxs-lookup"><span data-stu-id="5226a-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="5226a-147">Samla in information om utgivare</span><span class="sxs-lookup"><span data-stu-id="5226a-147">Gather publisher details</span></span>

<span data-ttu-id="5226a-148">Följ de här stegen om du vill få åtkomst till Publisher-data för en app:</span><span class="sxs-lookup"><span data-stu-id="5226a-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="5226a-149">Hitta en Microsoft-hanterad stationär enhet i test ringen som har en policy för gransknings läge installerad.</span><span class="sxs-lookup"><span data-stu-id="5226a-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="5226a-150">Försök att installera appen på enheten.</span><span class="sxs-lookup"><span data-stu-id="5226a-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="5226a-151">Öppna logg boken på enheten.</span><span class="sxs-lookup"><span data-stu-id="5226a-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="5226a-152">I logg boken navigerar du till **program-och Logs\Microsoft\Windows**och väljer sedan **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="5226a-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="5226a-153">Hitta en **8003** -eller **8006** -händelse och kopiera sedan information från händelsen:</span><span class="sxs-lookup"><span data-stu-id="5226a-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="5226a-154">Program namn</span><span class="sxs-lookup"><span data-stu-id="5226a-154">Application name</span></span> 
    - <span data-ttu-id="5226a-155">Program version</span><span class="sxs-lookup"><span data-stu-id="5226a-155">Application version</span></span> 
    - <span data-ttu-id="5226a-156">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5226a-156">Description</span></span> 
    - <span data-ttu-id="5226a-157">Information om utgivaren (till exempel: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="5226a-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
