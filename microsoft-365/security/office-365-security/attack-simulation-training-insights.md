---
title: Få insikter genom att träna på attacksimulering
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan lära sig hur utbildning för attack simulering i Microsoft 365 Security Center påverkar anställda och kan få insikter från simulering och utbildning.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667609"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="9d982-103">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="9d982-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="9d982-104">Med utbildning för att simulera attacker tillhandahåller Microsoft dig insikter baserade på resultat från simuleringar och utbildningar som de anställda gick igenom.</span><span class="sxs-lookup"><span data-stu-id="9d982-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="9d982-105">Dessa insikter hjälper dig att hålla dig informerad om hur hotet utvecklas för dina anställda, samt att rekommendera nästa steg för att bättre förbereda dina anställda och din miljö för attacker.</span><span class="sxs-lookup"><span data-stu-id="9d982-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9d982-106">Vi arbetar ständigt med att utöka de insikter som är tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="9d982-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="9d982-107">Beteende effekter och rekommenderade åtgärder är för tillfället tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="9d982-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="9d982-108">För att börja, gå över till en [utbildning för angrepps simulering i Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="9d982-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="9d982-109">Beteendet påverkar kompromissen</span><span class="sxs-lookup"><span data-stu-id="9d982-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="9d982-110">På fliken **Översikt** under utbildning för ansöknings simulering visas **beteendet för kompromiss** kortet.</span><span class="sxs-lookup"><span data-stu-id="9d982-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="9d982-111">Det här kortet visar hur anställda som samtycker till simuleringarna du körde i motsats till det **förutsagda kompromissade priset**.</span><span class="sxs-lookup"><span data-stu-id="9d982-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="9d982-112">Du kan använda dessa insikter för att spåra framsteg i de anställdas hot genom att köra flera simuleringar mot samma grupper av anställda.</span><span class="sxs-lookup"><span data-stu-id="9d982-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="9d982-113">I diagrammet kan du se:</span><span class="sxs-lookup"><span data-stu-id="9d982-113">In the graph you can see:</span></span>

- <span data-ttu-id="9d982-114">**Förväntad kompromiss nivå** som återspeglar den genomsnittliga kompromiss frekvensen för simuleringar med samma typ av nytto last för andra Microsoft 365-klient organisationer som använder samtals simulerings utbildning.</span><span class="sxs-lookup"><span data-stu-id="9d982-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="9d982-115">**Faktisk kompromiss hastighet** visar den andel av anställda som sjönk för simuleringen.</span><span class="sxs-lookup"><span data-stu-id="9d982-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="9d982-116">Dessutom visas `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som äventyras av angreppet och det uppskattade kompromiss priset.</span><span class="sxs-lookup"><span data-stu-id="9d982-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="9d982-117">Det här antalet anställda är mindre troligt att det äventyras genom liknande attacker i framtiden, samtidigt som `<percent%> better than predicted rate` det visar hur de anställda hade stor till gång till den förväntade kompromissen.</span><span class="sxs-lookup"><span data-stu-id="9d982-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d982-118">![Kurs kort i Översikt över hantering av angrepp](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="9d982-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="9d982-119">Om du vill se en mer detaljerad rapport klickar du på **Visa simuleringar och rapport om kurs utveckling**.</span><span class="sxs-lookup"><span data-stu-id="9d982-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="9d982-120">Den här rapporten ger samma information som du kan använda för att simulera själva simuleringen (till exempel simulerings teknik och totalt antal användare).</span><span class="sxs-lookup"><span data-stu-id="9d982-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="9d982-121">Rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="9d982-121">Recommended actions</span></span>

<span data-ttu-id="9d982-122">På fliken [ **simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations)kommer du till simulerings uppgifter där du hittar avsnittet **rekommenderade åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="9d982-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="9d982-123">Rekommendationer för rekommenderade åtgärder som är tillgängliga i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="9d982-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="9d982-124">Dessa rekommendationer är baserade på den nytto last som används i simuleringen och hjälper dig att skydda dina anställda och din miljö.</span><span class="sxs-lookup"><span data-stu-id="9d982-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="9d982-125">Om du klickar på varje åtgärd för förbättring kommer du till dess uppgifter.</span><span class="sxs-lookup"><span data-stu-id="9d982-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d982-126">![Avsnittet rekommendations åtgärder i utbildning för simulering av attacker](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="9d982-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="9d982-127">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="9d982-127">Related Links</span></span>

<span data-ttu-id="9d982-128">**Angrepps Simulator** [skapa en simulering av nätfiske-attack](attack-simulation-training.md) och [skapa en nytto last för utbildning av dina kontakter](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="9d982-128">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
