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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Sammanfattning: Vägledning för planering och implementering för snabbrörliga organisationer som har en ökad hotprofil.'
ms.openlocfilehash: d20d9f28f987b64f349510806c0d5b672998a9ab
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587526"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="3cb00-103">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer</span><span class="sxs-lookup"><span data-stu-id="3cb00-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

 <span data-ttu-id="3cb00-104">**Sammanfattning:** Vägledning för planering och implementering för snabbrörliga organisationer som har en ökad hotprofil.</span><span class="sxs-lookup"><span data-stu-id="3cb00-104">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="3cb00-105">Om din organisation är snabbrörlig, har en liten IT-grupp och din hotprofil är större än genomsnittet är den här vägledningen utformad för dig.</span><span class="sxs-lookup"><span data-stu-id="3cb00-105">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you.</span></span> <span data-ttu-id="3cb00-106">I den här lösningen finns information om hur du snabbt skapar en miljö med viktiga molntjänster som innehåller säkra kontroller direkt från början.</span><span class="sxs-lookup"><span data-stu-id="3cb00-106">This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start.</span></span> <span data-ttu-id="3cb00-107">I den här vägledningen ingår säkerhetsrekommendationer för att skydda data, identiteter, e-post och åtkomst från mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="3cb00-107">This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="3cb00-108">Vägledning för säkerhetslösning</span><span class="sxs-lookup"><span data-stu-id="3cb00-108">Security solution guidance</span></span>

<span data-ttu-id="3cb00-109">I den här vägledningen beskrivs hur du implementerar en säker molnmiljö.</span><span class="sxs-lookup"><span data-stu-id="3cb00-109">This guidance describes how to implement a secure cloud environment.</span></span> <span data-ttu-id="3cb00-110">Vägledningen för lösningen kan användas av alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="3cb00-110">The solution guidance can be used by any organization.</span></span> <span data-ttu-id="3cb00-111">Den innehåller extra hjälp för snabbrörliga organisationer med BYOD-åtkomst och gästkonton.</span><span class="sxs-lookup"><span data-stu-id="3cb00-111">It includes extra help for agile organizations with BYOD access and guest accounts.</span></span> <span data-ttu-id="3cb00-112">Du kan använda den här vägledningen som en utgångspunkt för att utforma din egen miljö.</span><span class="sxs-lookup"><span data-stu-id="3cb00-112">You can use this guidance as a starting-point for designing your own environment.</span></span> <span data-ttu-id="3cb00-113">Ge oss gärna feedback på [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3cb00-113">We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3cb00-114">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="3cb00-114">**Item**</span></span>|<span data-ttu-id="3cb00-115">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="3cb00-115">**Description**</span></span>|
|<span data-ttu-id="3cb00-116">**Microsofts säkerhetsvägledning för politiska kampanjer**</span><span class="sxs-lookup"><span data-stu-id="3cb00-116">**Microsoft Security Guidance for Political Campaigns**</span></span> <br/> <span data-ttu-id="3cb00-117">[![Miniatyr för miniposteruppsättning.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="3cb00-117">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br/> <span data-ttu-id="3cb00-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3cb00-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="3cb00-119">I den här vägledningen används en organisation med en politisk kampanj som exempel.</span><span class="sxs-lookup"><span data-stu-id="3cb00-119">This guidance uses a political campaign organization as an example.</span></span> <span data-ttu-id="3cb00-120">Använd den här vägledningen som en utgångspunkt för valfri miljö.</span><span class="sxs-lookup"><span data-stu-id="3cb00-120">Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="3cb00-121">**Microsofts säkerhetsvägledning för ideella föreningar**</span><span class="sxs-lookup"><span data-stu-id="3cb00-121">**Microsoft Security Guidance for Nonprofits**</span></span> <br/> <span data-ttu-id="3cb00-122">[![Miniatyr för nedladdningsbar fil](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="3cb00-122">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br/> <span data-ttu-id="3cb00-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3cb00-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="3cb00-124">Den här guiden är något ändrad för ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="3cb00-124">This guide is slightly revised for nonprofit organizations.</span></span> <span data-ttu-id="3cb00-125">Till exempel hänvisas till Office 365-abonnemang för ideella föreningar.</span><span class="sxs-lookup"><span data-stu-id="3cb00-125">For example, it references Office 365 Nonprofit plans.</span></span> <span data-ttu-id="3cb00-126">Den tekniska vägledningen är densamma som lösningsguiden för en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="3cb00-126">The technical guidance is the same as the political campaign solution guide.</span></span>|

## <a name="test-lab-guides"></a><span data-ttu-id="3cb00-127">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="3cb00-127">Test Lab Guides</span></span>

<span data-ttu-id="3cb00-128">Använd följande testlabbguider för att skapa en utvecklings-/testmiljö för den här lösningen:</span><span class="sxs-lookup"><span data-stu-id="3cb00-128">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="3cb00-129">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="3cb00-129">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="3cb00-130">Skapa utvärderingsprenumerationer för Office 365 och EMS och skapa sedan grupper och användare för en representativ politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="3cb00-130">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="3cb00-131">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="3cb00-131">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="3cb00-132">Skapa fyra teamwebbplatser för SharePoint Online med säkerhetsnivåerna Intern, Privat, Känslig och Strikt konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="3cb00-132">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="3cb00-133">Fler säkerhetsfunktioner för demonstration eller koncepttest finns i [Testlabbguider för Office 365](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="3cb00-133">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cb00-134">Se även</span><span class="sxs-lookup"><span data-stu-id="3cb00-134">See Also</span></span>

[<span data-ttu-id="3cb00-135">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="3cb00-135">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="3cb00-136">IT-arkitekturresurser för Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="3cb00-136">Microsoft Cloud IT architecture resources</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources)
