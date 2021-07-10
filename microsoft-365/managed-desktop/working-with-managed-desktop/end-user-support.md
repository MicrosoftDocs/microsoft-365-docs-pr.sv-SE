---
title: Få användarsupport för Microsoft Hanterat skrivbord
description: Hur användare kan få hjälp med tjänsten och enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362623"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="08dd9-104">Få hjälp för användare</span><span class="sxs-lookup"><span data-stu-id="08dd9-104">Getting help for users</span></span>

<span data-ttu-id="08dd9-105">Om du har kommit till [](../service-description/user-support.md) den punkt i arbetsflödet där du behöver begära utökad enhetsåtkomst eller eskalering till Microsoft gör du så här:</span><span class="sxs-lookup"><span data-stu-id="08dd9-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="08dd9-106">De här supportalternativen är inte tillgängliga för enheter i testgruppen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="08dd9-107">Höjdbegäranden</span><span class="sxs-lookup"><span data-stu-id="08dd9-107">Elevation requests</span></span>

<span data-ttu-id="08dd9-108">Innan du begär utökad åtkomst till en enhet bör du kontrollera vilka åtgärder som passar bäst.</span><span class="sxs-lookup"><span data-stu-id="08dd9-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="08dd9-109">**Vanliga åtgärder** är vad den här processen är avsedd för och som utförs regelbundet medan problem med e-Microsoft Hanterat skrivbord felsöks.</span><span class="sxs-lookup"><span data-stu-id="08dd9-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="08dd9-110">Några exempel:</span><span class="sxs-lookup"><span data-stu-id="08dd9-110">Examples include:</span></span>
    - <span data-ttu-id="08dd9-111">Höja upp inbyggda systemfelsökare, kommandotolken eller Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08dd9-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="08dd9-112">Felsöka verksamhetsbaserade program</span><span class="sxs-lookup"><span data-stu-id="08dd9-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="08dd9-113">Använda en lösning för att korrigera något som ska fungera enligt design (t.ex. BitLocker-aktivering eller systemtid som inte uppdateras)</span><span class="sxs-lookup"><span data-stu-id="08dd9-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="08dd9-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span><span class="sxs-lookup"><span data-stu-id="08dd9-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="08dd9-115">**Åtgärder som inte rekommenderas** är bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="08dd9-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="08dd9-116">Installera programvara eller webbläsare</span><span class="sxs-lookup"><span data-stu-id="08dd9-116">Installing software or browsers</span></span>
    - <span data-ttu-id="08dd9-117">Installera drivrutiner utanför Windows, inklusive för kringutrustning</span><span class="sxs-lookup"><span data-stu-id="08dd9-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="08dd9-118">Installera .msi eller .exe filer</span><span class="sxs-lookup"><span data-stu-id="08dd9-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="08dd9-119">Installera Windows funktioner</span><span class="sxs-lookup"><span data-stu-id="08dd9-119">Installing Windows features</span></span>

- <span data-ttu-id="08dd9-120">**Åtgärder som inte stöds** är bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="08dd9-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="08dd9-121">Installera programvara eller funktioner som står i konflikt Microsoft Hanterat skrivbord säkerhets- eller hanteringsfunktioner eller -åtgärder</span><span class="sxs-lookup"><span data-stu-id="08dd9-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="08dd9-122">Inaktivera en Windows som krävs för Microsoft Hanterat skrivbord, till exempel BitLocker</span><span class="sxs-lookup"><span data-stu-id="08dd9-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="08dd9-123">Ändra inställningar som hanteras av din organisation</span><span class="sxs-lookup"><span data-stu-id="08dd9-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="08dd9-124">Begära höjd</span><span class="sxs-lookup"><span data-stu-id="08dd9-124">To request elevation</span></span>

1. <span data-ttu-id="08dd9-125">Gå till portalen och [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) logga in med dina inloggningsuppgifter Azure Active Directory autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="08dd9-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="08dd9-126">Välj **Ny begäran om höjd**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="08dd9-127">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="08dd9-127">Provide these details:</span></span>
    - <span data-ttu-id="08dd9-128">**Support ticket ID** from your own support ticketing system.</span><span class="sxs-lookup"><span data-stu-id="08dd9-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="08dd9-129">**Enhetsnamn**: ange enhetens serienummer och välj sedan enheten på menyn.</span><span class="sxs-lookup"><span data-stu-id="08dd9-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="08dd9-130">**Kategori:** Välj den kategori som bäst passar ditt problem.</span><span class="sxs-lookup"><span data-stu-id="08dd9-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="08dd9-131">Om inget alternativ verkar vara nära väljer du **Annat** och ger mer information i **fälten** Rubrik och Plan **för** åtgärder.</span><span class="sxs-lookup"><span data-stu-id="08dd9-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="08dd9-132">Det är bäst att välja en kategori om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="08dd9-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="08dd9-133">**Underkategori:** Välj den som passar bäst för problemet.</span><span class="sxs-lookup"><span data-stu-id="08dd9-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="08dd9-134">Om inget alternativ verkar vara nära väljer du **Annat** och ger en kort beskrivning i **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="08dd9-135">Ange **de felsökningssteg** du planerar att vidta när höjd beviljas i Planera för åtgärd.</span><span class="sxs-lookup"><span data-stu-id="08dd9-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="08dd9-136">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="08dd9-137">Eskaleringsförfrågningar</span><span class="sxs-lookup"><span data-stu-id="08dd9-137">Escalation requests</span></span>


<span data-ttu-id="08dd9-138">Om du behöver [eskalera ett](../service-description/user-support.md#escalation-portal) problem till Microsoft gör du så här:</span><span class="sxs-lookup"><span data-stu-id="08dd9-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="08dd9-139">Gå till portalen och [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) logga in med dina inloggningsuppgifter Azure Active Directory autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="08dd9-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="08dd9-140">Välj **Eskaleringsförfrågningar** och välj sedan **Ny eskaleringsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="08dd9-141">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="08dd9-141">Provide these details:</span></span>
    - <span data-ttu-id="08dd9-142">**Kategori:** Välj den kategori som bäst passar ditt problem.</span><span class="sxs-lookup"><span data-stu-id="08dd9-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="08dd9-143">**Rubrik**: Ge en mycket kort beskrivning.</span><span class="sxs-lookup"><span data-stu-id="08dd9-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="08dd9-144">**Beskrivning**: Lägg till ytterligare information som kan hjälpa vårt team att förstå problemet.</span><span class="sxs-lookup"><span data-stu-id="08dd9-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="08dd9-145">Om du behöver bifoga filer kan du göra det genom att komma tillbaka till begäran efter att du skickat den.</span><span class="sxs-lookup"><span data-stu-id="08dd9-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="08dd9-146">**Primär kontaktinformation:** Ange information om hur du kontaktar huvudpersonen som ansvarar för att arbeta med vårt team.</span><span class="sxs-lookup"><span data-stu-id="08dd9-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="08dd9-147">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-147">Select **Submit**.</span></span>
5. <span data-ttu-id="08dd9-148">Gå tillbaka till biljetten i samma portal för att interagera med vårt team.</span><span class="sxs-lookup"><span data-stu-id="08dd9-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="08dd9-149">Endast problem med allvarlighetsgrad C kan eskaleras genom den här vägen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="08dd9-150">Om det är andra problem kontaktar du IT-administratören och arkiverar begäran via administratörsportalen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>