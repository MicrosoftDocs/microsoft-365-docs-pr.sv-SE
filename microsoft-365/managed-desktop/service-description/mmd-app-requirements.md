---
title: Microsofts appkrav för hanterade skrivbord
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: bd775e201f5fec556941ae0e8e7b025744da0419
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529439"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="927ae-103">Microsofts appkrav för hanterade skrivbord</span><span class="sxs-lookup"><span data-stu-id="927ae-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="927ae-104">Microsoft Managed Desktop kräver att vi hanterar enheter med en specifik metod för att garantera enheters prestanda, tillförlitlighet och service.</span><span class="sxs-lookup"><span data-stu-id="927ae-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="927ae-105">Om du är säker på att den metod som Används av Microsoft Managed Desktop för områdena nedan inte fungerar för dig, kan du begära ett [undantag från serviceplanen](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="927ae-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="927ae-106">Ledningsområde</span><span class="sxs-lookup"><span data-stu-id="927ae-106">Management area</span></span>  |<span data-ttu-id="927ae-107">Microsoft-metod för hanterade skrivbord</span><span class="sxs-lookup"><span data-stu-id="927ae-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="927ae-108">Enhetskonfiguration eller principhantering</span><span class="sxs-lookup"><span data-stu-id="927ae-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="927ae-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="927ae-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="927ae-110">Hantering av program</span><span class="sxs-lookup"><span data-stu-id="927ae-110">Application management</span></span>     | <span data-ttu-id="927ae-111">Microsoft Intune och företagsportal</span><span class="sxs-lookup"><span data-stu-id="927ae-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="927ae-112">Drivrutinsdistribution</span><span class="sxs-lookup"><span data-stu-id="927ae-112">Driver deployment</span></span>     |  <span data-ttu-id="927ae-113">Drivrutiner som ingår i enheten, Windows Update eller Intune</span><span class="sxs-lookup"><span data-stu-id="927ae-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="927ae-114">Enhetssäkerhet</span><span class="sxs-lookup"><span data-stu-id="927ae-114">Device security</span></span>     | <span data-ttu-id="927ae-115">Se [Enhetssäkerhet](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="927ae-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="927ae-116">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="927ae-116">Identity and access management</span></span>     | <span data-ttu-id="927ae-117">Se [Hantering av identitet och åtkomst](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="927ae-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="927ae-118">Nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="927ae-118">Network security</span></span>     | <span data-ttu-id="927ae-119">Se [Nätverkssäkerhet](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="927ae-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="927ae-120">Informationssäkerhet</span><span class="sxs-lookup"><span data-stu-id="927ae-120">Information security</span></span>     |  <span data-ttu-id="927ae-121">Se [Informationssäkerhet](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="927ae-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="927ae-122">Dataräddning</span><span class="sxs-lookup"><span data-stu-id="927ae-122">Data recovery</span></span>     | <span data-ttu-id="927ae-123">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="927ae-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="927ae-124">Kärnproduktivitet</span><span class="sxs-lookup"><span data-stu-id="927ae-124">Core productivity</span></span>     | <span data-ttu-id="927ae-125">Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="927ae-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="927ae-126">Webbläsare</span><span class="sxs-lookup"><span data-stu-id="927ae-126">Browser</span></span>     | <span data-ttu-id="927ae-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="927ae-127">Microsoft Edge</span></span>        |




<span data-ttu-id="927ae-128">Microsoft Managed Desktop kan övervaka annan programvara som körs på hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="927ae-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="927ae-129">Om det påverkar systemets säkerhet, prestanda eller tillförlitlighet negativt kan du behöva begära ett undantag från serviceplanen.</span><span class="sxs-lookup"><span data-stu-id="927ae-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


