---
title: Få insikter genom att träna på attacksimulering
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur attackersutbildning i Säkerhetscenter i Microsoft 365 påverkar anställda och kan få insikter från simulering och utbildningsresultat.
ms.technology: mdo
ms.openlocfilehash: b7fd414cc355e768077198eb5215720c4d4a9444
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933072"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="1414d-103">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="1414d-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="1414d-104">I utbildning av attacksimulering ger Microsoft dig insikter baserade på resultat av simuleringar och utbildningar som anställda har gått igenom.</span><span class="sxs-lookup"><span data-stu-id="1414d-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="1414d-105">De här insikterna hjälper dig att hålla dig informerad om dina anställdas beredskapsnivå och rekommenderar nästa steg för att bättre förbereda anställda och din miljö för attacker.</span><span class="sxs-lookup"><span data-stu-id="1414d-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="1414d-106">Vi arbetar kontinuerligt med att utöka de insikter som är tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="1414d-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="1414d-107">Funktionens påverkan och rekommenderade åtgärder är tillgängliga för närvarande.</span><span class="sxs-lookup"><span data-stu-id="1414d-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="1414d-108">Börja med att gå till [attackutbildningen i Säkerhetscenter i Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="1414d-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="1414d-109">Påverkan på kompromettens</span><span class="sxs-lookup"><span data-stu-id="1414d-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="1414d-110">På fliken **Översikt** över attacksimuleringsutbildning ser du hur **beteendet påverkar komprometteringskortet.**</span><span class="sxs-lookup"><span data-stu-id="1414d-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="1414d-111">Det här kortet visar hur anställda har hanterat de simuleringar du körde i motsats till **den förutsagda komprometteringen.**</span><span class="sxs-lookup"><span data-stu-id="1414d-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="1414d-112">Du kan använda de här insikterna för att följa utvecklingen av medarbetarnas hotberedskap genom att köra flera simuleringar mot samma grupper av anställda.</span><span class="sxs-lookup"><span data-stu-id="1414d-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="1414d-113">I diagrammet kan du se:</span><span class="sxs-lookup"><span data-stu-id="1414d-113">In the graph you can see:</span></span>

- <span data-ttu-id="1414d-114">**Förutsagd** komprometteringshastighet som återspeglar den genomsnittliga komprometteringen för simuleringar som använder samma typ av nyttolast i andra Microsoft 365-klientorganisationen som använder utbildning i attacksimulering.</span><span class="sxs-lookup"><span data-stu-id="1414d-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="1414d-115">**Den faktiska komprometteringen** återspeglar procentandelen anställda som var med i simuleringen.</span><span class="sxs-lookup"><span data-stu-id="1414d-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="1414d-116">Återspeglar dessutom `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som komprometterats av attacken och den förutsagda komprometteras.</span><span class="sxs-lookup"><span data-stu-id="1414d-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="1414d-117">Antalet anställda är mindre sannolikt att bli komprometterade av liknande angrepp i framtiden, samtidigt som det visar hur anställda gjorde generellt i motsats till den `<percent%> better than predicted rate` förutsagda komprometterande hastigheten.</span><span class="sxs-lookup"><span data-stu-id="1414d-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1414d-118">![Kortet Påverkar beteendet på översikt över attacksimulering](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="1414d-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="1414d-119">Om du vill se en mer detaljerad rapport klickar du **på Visa simuleringar och övningsresultat.**</span><span class="sxs-lookup"><span data-stu-id="1414d-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="1414d-120">Den här rapporten innehåller samma information med ytterligare kontext från själva simuleringen (till exempel simuleringsteknik och totalt antal användare som är riktade).</span><span class="sxs-lookup"><span data-stu-id="1414d-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="1414d-121">Rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="1414d-121">Recommended actions</span></span>

<span data-ttu-id="1414d-122">På [ **fliken Simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations)kommer du till simuleringsinformationen där du hittar avsnittet Rekommenderade **åtgärder** när du väljer en simulering.</span><span class="sxs-lookup"><span data-stu-id="1414d-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="1414d-123">Avsnitten med rekommenderade åtgärder innehåller information om rekommendationer som finns [i Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="1414d-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="1414d-124">De här rekommendationerna baseras på den nyttolast som användes i simuleringen och hjälper dig att skydda dina anställda och din miljö.</span><span class="sxs-lookup"><span data-stu-id="1414d-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="1414d-125">Om du klickar på varje förbättringsåtgärd visas information om den.</span><span class="sxs-lookup"><span data-stu-id="1414d-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1414d-126">![Avsnittet Rekommendationsåtgärder på attacksimuleringsutbildning](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="1414d-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="1414d-127">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="1414d-127">Related Links</span></span>

[<span data-ttu-id="1414d-128">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="1414d-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="1414d-129">Skapa en nätfiskeattack som kan simuleras</span><span class="sxs-lookup"><span data-stu-id="1414d-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="1414d-130">skapa ett nyttolast för att utbilda dina användare</span><span class="sxs-lookup"><span data-stu-id="1414d-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
