---
title: Microsofts säkerhetsvägledning för politiska kampanjer och ideella föreningar
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Sammanfattning: Vägledning för planering och implementering för snabbrörliga organisationer som har en ökad hotprofil.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ed01d2c41529782c5c714bfe66096b97300712
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287407"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="f77b6-103">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer</span><span class="sxs-lookup"><span data-stu-id="f77b6-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f77b6-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f77b6-104">**Applies to**</span></span>
- [<span data-ttu-id="f77b6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f77b6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f77b6-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f77b6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="f77b6-107">**Sammanfattning:** Vägledning för planering och implementering för snabbrörliga organisationer som har en ökad hotprofil.</span><span class="sxs-lookup"><span data-stu-id="f77b6-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="f77b6-108">Om din organisation är snabbrörlig, har en liten IT-grupp och din hotprofil är större än genomsnittet är den här vägledningen utformad för dig.</span><span class="sxs-lookup"><span data-stu-id="f77b6-108">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you.</span></span> <span data-ttu-id="f77b6-109">I den här lösningen finns information om hur du snabbt skapar en miljö med viktiga molntjänster som innehåller säkra kontroller direkt från början.</span><span class="sxs-lookup"><span data-stu-id="f77b6-109">This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start.</span></span> <span data-ttu-id="f77b6-110">I den här vägledningen ingår säkerhetsrekommendationer för att skydda data, identiteter, e-post och åtkomst från mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="f77b6-110">This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="f77b6-111">Vägledning för säkerhetslösning</span><span class="sxs-lookup"><span data-stu-id="f77b6-111">Security solution guidance</span></span>

<span data-ttu-id="f77b6-112">I den här vägledningen beskrivs hur du implementerar en säker molnmiljö.</span><span class="sxs-lookup"><span data-stu-id="f77b6-112">This guidance describes how to implement a secure cloud environment.</span></span> <span data-ttu-id="f77b6-113">Vägledningen för lösningen kan användas av alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="f77b6-113">The solution guidance can be used by any organization.</span></span> <span data-ttu-id="f77b6-114">Den innehåller extra hjälp för snabbrörliga organisationer med BYOD-åtkomst och gästkonton.</span><span class="sxs-lookup"><span data-stu-id="f77b6-114">It includes extra help for agile organizations with BYOD access and guest accounts.</span></span> <span data-ttu-id="f77b6-115">Du kan använda den här vägledningen som en utgångspunkt för att utforma din egen miljö.</span><span class="sxs-lookup"><span data-stu-id="f77b6-115">You can use this guidance as a starting-point for designing your own environment.</span></span> <span data-ttu-id="f77b6-116">Ge oss gärna feedback på [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f77b6-116">We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="f77b6-117">Objekt</span><span class="sxs-lookup"><span data-stu-id="f77b6-117">Item</span></span>|<span data-ttu-id="f77b6-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f77b6-118">Description</span></span>|
|---|---|
|<span data-ttu-id="f77b6-119">**Microsofts säkerhetsvägledning för politiska kampanjer**</span><span class="sxs-lookup"><span data-stu-id="f77b6-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="f77b6-120">[![Miniatyr för miniposteruppsättning.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="f77b6-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="f77b6-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="f77b6-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="f77b6-122">I den här vägledningen används en organisation med en politisk kampanj som exempel.</span><span class="sxs-lookup"><span data-stu-id="f77b6-122">This guidance uses a political campaign organization as an example.</span></span> <span data-ttu-id="f77b6-123">Använd den här vägledningen som en utgångspunkt för valfri miljö.</span><span class="sxs-lookup"><span data-stu-id="f77b6-123">Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="f77b6-124">**Microsofts säkerhetsvägledning för ideella föreningar**</span><span class="sxs-lookup"><span data-stu-id="f77b6-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="f77b6-125">[![Miniatyr för nedladdningsbar fil](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="f77b6-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="f77b6-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="f77b6-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="f77b6-127">Den här guiden är något ändrad för ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="f77b6-127">This guide is slightly revised for nonprofit organizations.</span></span> <span data-ttu-id="f77b6-128">Till exempel hänvisas till Office 365-abonnemang för ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="f77b6-128">For example, it references Office 365 Nonprofit plans.</span></span> <span data-ttu-id="f77b6-129">Den tekniska vägledningen är densamma som lösningsguiden för en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="f77b6-129">The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="f77b6-130">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="f77b6-130">Test Lab Guides</span></span>

<span data-ttu-id="f77b6-131">Använd följande testlabbguider för att skapa en utvecklings-/testmiljö för den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="f77b6-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="f77b6-132">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="f77b6-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="f77b6-133">Skapa utvärderingsprenumerationer för Office 365 och EMS och skapa sedan grupper och användare för en representativ politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="f77b6-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="f77b6-134">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="f77b6-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="f77b6-135">Skapa fyra teamwebbplatser för SharePoint Online med säkerhetsnivåerna Intern, Privat, Känslig och Strikt konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="f77b6-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="f77b6-136">Fler säkerhetsfunktioner för demonstration eller koncepttest finns i [Testlabbguider för Office 365](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="f77b6-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="f77b6-137">Se även</span><span class="sxs-lookup"><span data-stu-id="f77b6-137">See Also</span></span>

[<span data-ttu-id="f77b6-138">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="f77b6-138">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="f77b6-139">IT-arkitekturresurser för Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="f77b6-139">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
