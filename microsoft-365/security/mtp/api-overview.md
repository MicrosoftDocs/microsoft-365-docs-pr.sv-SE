---
title: 'Översikt över Microsoft 365 Defender API: er'
description: 'Läs mer om tillgängliga API: er i Microsoft 365 Defender'
keywords: 'API, API: er, översikt, problem, incidenter, hot om hotet'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845022"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="4296c-104">Översikt över Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="4296c-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4296c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4296c-105">**Applies to:**</span></span>
- <span data-ttu-id="4296c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4296c-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="4296c-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="4296c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4296c-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="4296c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4296c-109">Microsoft 365 Defender-lösningen är byggd ovanpå en integrerad integrerings plattform.</span><span class="sxs-lookup"><span data-stu-id="4296c-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="4296c-110">Med Lop-nivå API för Microsoft 365 Defender kan du automatisera arbets flöden utifrån de delade incidenterna och de avancerade jakt tabellerna.</span><span class="sxs-lookup"><span data-stu-id="4296c-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="4296c-111">**Kö** för sammanslagna olyckor – hjälper säkerhetsutövarna att fokusera på vad som är viktigt.</span><span class="sxs-lookup"><span data-stu-id="4296c-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="4296c-112">Gör det lättare att se till att fullständig attack-och stötande till gångar grupperas tillsammans och lagras i rätt tid under API: t.</span><span class="sxs-lookup"><span data-stu-id="4296c-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="4296c-113">Stöldskydd med olika **produkter** -säkerhets team kan utnyttja sin unika organisations kunskap för att hitta tecken på kompromisser genom att skapa egna anpassade frågor via API: er över rå data som samlas in av de olika skydds produkterna.</span><span class="sxs-lookup"><span data-stu-id="4296c-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="4296c-114">Utöver dessa API-uppsättningar visar de olika skydds produkterna ytterligare API: er som hjälper dig att förnya baserat på varje produkt kapacitet.</span><span class="sxs-lookup"><span data-stu-id="4296c-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4296c-115">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4296c-115">Related topics</span></span>
- [<span data-ttu-id="4296c-116">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="4296c-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="4296c-117">Andra API-resurser</span><span class="sxs-lookup"><span data-stu-id="4296c-117">Other API resources</span></span>](api-articles.md)
