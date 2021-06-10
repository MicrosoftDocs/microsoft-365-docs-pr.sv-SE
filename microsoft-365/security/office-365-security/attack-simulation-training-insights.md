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
description: Administratörer kan lära sig hur attack simuleringsutbildning i Microsoft 365 säkerhetscenter påverkar anställda och kan få insikter från simulering och utbildningsresultat.
ms.technology: mdo
ms.openlocfilehash: 0fcb88406558f73b587d8452375c33dbbec1c78b
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51600013"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="990fb-103">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="990fb-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="990fb-104">I simuleringen av attacker ger Microsoft dig insikter baserade på resultat av simuleringar och utbildningar som anställda gick igenom.</span><span class="sxs-lookup"><span data-stu-id="990fb-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="990fb-105">De här insikterna hjälper dig att hålla dig informerad om dina anställdas beredskapsstatus och rekommenderar nästa steg för att bättre förbereda de anställda och din miljö för attacker.</span><span class="sxs-lookup"><span data-stu-id="990fb-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="990fb-106">Vi arbetar kontinuerligt med att expandera de insikter som är tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="990fb-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="990fb-107">Funktionens påverkan och rekommenderade åtgärder är tillgängliga för närvarande.</span><span class="sxs-lookup"><span data-stu-id="990fb-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="990fb-108">Börja med att gå till [simuleringsutbildning för attack i Microsoft 365 säkerhetscenter](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="990fb-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="990fb-109">Påverkan på kompromettränta</span><span class="sxs-lookup"><span data-stu-id="990fb-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="990fb-110">På fliken **Översikt** över attack simuleringsutbildning ser du hur beteendet **påverkar komprometteringsräntan.**</span><span class="sxs-lookup"><span data-stu-id="990fb-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="990fb-111">Det här kortet visar hur anställda tagit itu med de simuleringar du körde i motsats till den **förutsagda komprometteringen**.</span><span class="sxs-lookup"><span data-stu-id="990fb-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="990fb-112">Du kan använda de här insikterna för att följa utvecklingen av medarbetarnas hotberedskap genom att köra flera simuleringar mot samma grupper av anställda.</span><span class="sxs-lookup"><span data-stu-id="990fb-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="990fb-113">I diagrammet kan du se:</span><span class="sxs-lookup"><span data-stu-id="990fb-113">In the graph you can see:</span></span>

- <span data-ttu-id="990fb-114">**Förutsagd komprometteringshastighet** som återspeglar den genomsnittliga komprometteringen för simuleringar som använder samma typ av nyttolast i andra Microsoft 365-klientorganisationen som använder utbildning av attack simulering.</span><span class="sxs-lookup"><span data-stu-id="990fb-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="990fb-115">**Den faktiska komprometteringen** återspeglar procentandelen anställda som avar sig för simuleringen.</span><span class="sxs-lookup"><span data-stu-id="990fb-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="990fb-116">Återspeglar dessutom `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som komprometterats av attacken och den förutsagda komprometterats.</span><span class="sxs-lookup"><span data-stu-id="990fb-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="990fb-117">Antalet anställda är mindre sannolikt att bli komprometterade av liknande attacker i framtiden, samtidigt som det visar hur anställda gjorde generellt i motsats till `<percent%> better than predicted rate` den förutsagda komprometterat lönen.</span><span class="sxs-lookup"><span data-stu-id="990fb-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="990fb-118">![Kort som påverkar beteendet på översikt över attack simuleringsutbildning](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="990fb-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="990fb-119">Om du vill se en mer detaljerad rapport klickar du **på Visa simuleringar och effektivhetsrapport för utbildning**.</span><span class="sxs-lookup"><span data-stu-id="990fb-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="990fb-120">Den här rapporten innehåller samma information med ytterligare kontext från själva simuleringen (till exempel simuleringsteknik och den totala användarens riktade).</span><span class="sxs-lookup"><span data-stu-id="990fb-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="990fb-121">Rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="990fb-121">Recommended actions</span></span>

<span data-ttu-id="990fb-122">På fliken Simuleringar väljer du en simulering för att gå till [ **simuleringsinformationen,**](https://security.microsoft.com/attacksimulator?viewid=simulations)där du hittar **avsnittet Rekommenderade** åtgärder.</span><span class="sxs-lookup"><span data-stu-id="990fb-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="990fb-123">Avsnittet med rekommenderade åtgärder innehåller information om rekommendationer som finns [i Microsoft Secure Score.](../defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="990fb-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="990fb-124">De här rekommendationerna baseras på den nyttolast som användes i simuleringen och hjälper dig att skydda dina anställda och din miljö.</span><span class="sxs-lookup"><span data-stu-id="990fb-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="990fb-125">Om du klickar på varje förbättringsåtgärd visas information om den.</span><span class="sxs-lookup"><span data-stu-id="990fb-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="990fb-126">![Avsnittet Rekommendationsåtgärder på simulering av attack](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="990fb-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="990fb-127">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="990fb-127">Related Links</span></span>

[<span data-ttu-id="990fb-128">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="990fb-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="990fb-129">Skapa en simulering av nätfiskeattacker</span><span class="sxs-lookup"><span data-stu-id="990fb-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="990fb-130">skapa en nyttolast för utbildning av dina användare</span><span class="sxs-lookup"><span data-stu-id="990fb-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
