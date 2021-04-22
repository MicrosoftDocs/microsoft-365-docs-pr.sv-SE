---
title: Microsoft Defender för slutpunktsflödeskoppling
ms.reviewer: ''
description: Använd Microsoft Defender för Slutpunktsflödeskoppling för att automatisera säkerhet och skapa ett flöde som utlöses varje gång en ny avisering inträffar i klientorganisationen.
keywords: flöde, apis som stöds, api, Microsoft flow, fråga, automation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929305"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="80c38-104">Microsoft Power Automate (tidigare Microsoft Flow) och Azure-funktioner</span><span class="sxs-lookup"><span data-stu-id="80c38-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80c38-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="80c38-105">**Applies to:**</span></span>
- [<span data-ttu-id="80c38-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="80c38-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80c38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80c38-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="80c38-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="80c38-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80c38-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="80c38-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="80c38-110">Att automatisera säkerhetsprocedurer är ett standardkrav för alla moderna säkerhetsoperationscenter.</span><span class="sxs-lookup"><span data-stu-id="80c38-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="80c38-111">Brist på professionella cyberbrott tvingar SOC att arbeta på det mest effektiva sättet och automatisering är ett måste.</span><span class="sxs-lookup"><span data-stu-id="80c38-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="80c38-112">Microsoft Power Automate har stöd för olika kopplingar som skapats exakt för detta.</span><span class="sxs-lookup"><span data-stu-id="80c38-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="80c38-113">Du kan skapa en end-to-end-procedurautomatisering inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="80c38-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="80c38-114">Microsoft Defender API har en officiell Flow Connector med många funktioner.</span><span class="sxs-lookup"><span data-stu-id="80c38-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Bild av autentiseringsuppgifter för redigera1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="80c38-116">Mer information om licenskrav för Premium Connectors finns i [Licensiering för premium-anslutningappar.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="80c38-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="80c38-117">Användningsexempel</span><span class="sxs-lookup"><span data-stu-id="80c38-117">Usage example</span></span>

<span data-ttu-id="80c38-118">I följande exempel visas hur du skapar ett flöde som utlöses när en ny avisering inträffar för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="80c38-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="80c38-119">Logga in på [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="80c38-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="80c38-120">Gå till **My flows**  >  **New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="80c38-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Bild av autentiseringsuppgifter för redigera2](images/api-flow-1.png)

3. <span data-ttu-id="80c38-122">Välj ett namn för ditt Flow, sök efter "Microsoft Defender ATP-utlösare" som utlösare och välj sedan den nya aviseringsutlösaren.</span><span class="sxs-lookup"><span data-stu-id="80c38-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Bild av autentiseringsuppgifter för redigering3](images/api-flow-2.png)

<span data-ttu-id="80c38-124">Nu har du ett Flöde som utlöses varje gång en ny avisering inträffar.</span><span class="sxs-lookup"><span data-stu-id="80c38-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Bild av autentiseringsuppgifter för redigera4](images/api-flow-3.png)

<span data-ttu-id="80c38-126">Allt du behöver göra nu är att välja nästa steg.</span><span class="sxs-lookup"><span data-stu-id="80c38-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="80c38-127">Du kan till exempel isolera enheten om aviseringens allvarlighetsgrad är Hög och skicka ett e-postmeddelande om den.</span><span class="sxs-lookup"><span data-stu-id="80c38-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="80c38-128">Aviseringsutlösaren anger endast aviserings-ID och maskin-ID.</span><span class="sxs-lookup"><span data-stu-id="80c38-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="80c38-129">Du kan använda kopplingen för att expandera dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="80c38-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="80c38-130">Hämta aviseringsentitet med hjälp av kopplingen</span><span class="sxs-lookup"><span data-stu-id="80c38-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="80c38-131">Välj **Microsoft Defender ATP** för det nya steget.</span><span class="sxs-lookup"><span data-stu-id="80c38-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="80c38-132">Välj **Aviseringar – Få API för enkel avisering.**</span><span class="sxs-lookup"><span data-stu-id="80c38-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="80c38-133">Ställ in **aviserings-ID** från det sista steget som **indata**.</span><span class="sxs-lookup"><span data-stu-id="80c38-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Bild av autentiseringsuppgifter för redigera5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="80c38-135">Isolera enheten om aviseringens allvarlighetsgrad är hög</span><span class="sxs-lookup"><span data-stu-id="80c38-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="80c38-136">Lägg **till** villkor som ett nytt steg.</span><span class="sxs-lookup"><span data-stu-id="80c38-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="80c38-137">Kontrollera om allvarlighetsgraden för avisering **är lika med** Hög.</span><span class="sxs-lookup"><span data-stu-id="80c38-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="80c38-138">Om ja lägger du till **åtgärden Microsoft Defender ATP - Isolera** maskin med maskin-ID och en kommentar.</span><span class="sxs-lookup"><span data-stu-id="80c38-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Bild av autentiseringsuppgifter för redigera6](images/api-flow-5.png)

3. <span data-ttu-id="80c38-140">Lägg till ett nytt steg för att skicka e-post om aviseringen och isoleringen.</span><span class="sxs-lookup"><span data-stu-id="80c38-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="80c38-141">Det finns flera e-postanslutningar som är mycket enkla att använda, till exempel Outlook eller Gmail.</span><span class="sxs-lookup"><span data-stu-id="80c38-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="80c38-142">Spara flödet.</span><span class="sxs-lookup"><span data-stu-id="80c38-142">Save your flow.</span></span>

<span data-ttu-id="80c38-143">Du kan också skapa ett **schemalagt** flöde som kör Avancerad sökning och mycket mer!</span><span class="sxs-lookup"><span data-stu-id="80c38-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="80c38-144">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="80c38-144">Related topic</span></span>
- [<span data-ttu-id="80c38-145">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="80c38-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
