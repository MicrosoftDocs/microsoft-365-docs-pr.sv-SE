---
title: Få insikter genom att träna på attacksimulering
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Lär dig hur utbildning för att simulera attacker i Microsoft 365 Security Center påverkar anställda och får insikter från simulering och utbildning.
ms.openlocfilehash: 80b8c275d1d64dd3dbd6509309fb88cd641734e3
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950989"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="dba2f-103">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="dba2f-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="dba2f-104">Med utbildning för att simulera attacker tillhandahåller Microsoft dig insikter baserade på resultat från simuleringar och utbildning som anställda gick igenom.</span><span class="sxs-lookup"><span data-stu-id="dba2f-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="dba2f-105">Dessa insikter hjälper dig med att informera dina anställda om hot och att rekommendera nästa steg för att bättre förbereda dina anställda och din miljö för attacker.</span><span class="sxs-lookup"><span data-stu-id="dba2f-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="dba2f-106">Vi arbetar ständigt med att utöka alla insikter som är tillgängliga för dig, med beteende effekter och rekommenderade åtgärder tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="dba2f-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="dba2f-107">För att komma igång kan du [gå vidare med utbildning för utleverans simulering i Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="dba2f-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="dba2f-108">Beteendet påverkar kompromissen</span><span class="sxs-lookup"><span data-stu-id="dba2f-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="dba2f-109">På fliken **Översikt** för angrepps simulering visas **beteendet för kompromiss** kortet.</span><span class="sxs-lookup"><span data-stu-id="dba2f-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="dba2f-110">Det här kortet visar hur medarbetare kan hantera simuleringen som du har använt i motsats till det **förutsagda kompromissade priset**.</span><span class="sxs-lookup"><span data-stu-id="dba2f-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="dba2f-111">Du kan använda dessa insikter för att spåra framsteg i de anställdas hot genom att köra flera simuleringar mot samma grupper av anställda.</span><span class="sxs-lookup"><span data-stu-id="dba2f-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="dba2f-112">I diagrammet kan du se:</span><span class="sxs-lookup"><span data-stu-id="dba2f-112">In the graph you can see:</span></span>

- <span data-ttu-id="dba2f-113">**Förväntad kompromiss nivå** som återspeglar den genomsnittliga kompromiss frekvensen för simuleringar med samma typ av nytto Last mellan klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="dba2f-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="dba2f-114">**Faktisk kompromiss hastighet** visar den andel av anställda som sjönk för simuleringen.</span><span class="sxs-lookup"><span data-stu-id="dba2f-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="dba2f-115">Dessutom visas `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som äventyras av angreppet och det uppskattade kompromiss priset.</span><span class="sxs-lookup"><span data-stu-id="dba2f-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="dba2f-116">Det här antalet anställda är mindre troligt att det äventyras genom liknande attacker i framtiden, samtidigt som `<percent%> better than predicted rate` det visar hur de anställda hade stor till gång till den förväntade kompromissen.</span><span class="sxs-lookup"><span data-stu-id="dba2f-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dba2f-117">![Kurs kort i Översikt över hantering av angrepp](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="dba2f-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="dba2f-118">Om du vill se en mer detaljerad rapport klickar du på **Visa simuleringar och kurs effektivitets rapport** som ger samma information om ytterligare kontext från själva simuleringen, som simulerings teknik och totalt antal användare riktade till sig.</span><span class="sxs-lookup"><span data-stu-id="dba2f-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="dba2f-119">Rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="dba2f-119">Recommended actions</span></span>

<span data-ttu-id="dba2f-120">På fliken [ **simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations)kommer du till simulerings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dba2f-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="dba2f-121">Här hittar du avsnittet **rekommenderade åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="dba2f-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="dba2f-122">Rekommendationer för rekommenderade åtgärder som är tillgängliga i [Microsofts säkra Poäng](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="dba2f-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="dba2f-123">Dessa rekommendationer är baserade på den nytto last som används i simuleringen och hjälper dig att skydda dina anställda och din miljö.</span><span class="sxs-lookup"><span data-stu-id="dba2f-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="dba2f-124">Om du klickar på varje åtgärd för förbättring kommer du till dess uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dba2f-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dba2f-125">![Avsnittet rekommendations åtgärder i utbildning för simulering av attacker](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="dba2f-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="dba2f-126">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="dba2f-126">Related Links</span></span>

<span data-ttu-id="dba2f-127">**Angrepps Simulator** [skapa en simulering av nätfiske-attack](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training?view=o365-worldwide) och [skapa en nytto last för utbildning av dina kontakter](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="dba2f-127">**Attack Simulator** [Create a phishing attack simulation](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training?view=o365-worldwide) and [create a payload for training your people](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads?view=o365-worldwide)</span></span>
