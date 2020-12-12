---
title: Program krav för Microsoft Managed Desktop
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659720"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="1eea3-103">Program krav för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1eea3-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="1eea3-104">Microsoft Managed Desktop kräver att vi hanterar enheter med en särskild metod för att garantera prestanda, tillförlitlighet och service möjligheter.</span><span class="sxs-lookup"><span data-stu-id="1eea3-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="1eea3-105">Hanterings område</span><span class="sxs-lookup"><span data-stu-id="1eea3-105">Management area</span></span>  |<span data-ttu-id="1eea3-106">Microsoft Managed Desktop-teknik</span><span class="sxs-lookup"><span data-stu-id="1eea3-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="1eea3-107">Enhets konfiguration eller princip hantering</span><span class="sxs-lookup"><span data-stu-id="1eea3-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="1eea3-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1eea3-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="1eea3-109">Program hantering</span><span class="sxs-lookup"><span data-stu-id="1eea3-109">Application management</span></span>     | <span data-ttu-id="1eea3-110">Microsoft Intune-och företags Portal</span><span class="sxs-lookup"><span data-stu-id="1eea3-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="1eea3-111">Driv rutins distribution</span><span class="sxs-lookup"><span data-stu-id="1eea3-111">Driver deployment</span></span>     |  <span data-ttu-id="1eea3-112">Driv rutiner som ingår i enheten, Windows Update eller Intune</span><span class="sxs-lookup"><span data-stu-id="1eea3-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="1eea3-113">Enhets säkerhet</span><span class="sxs-lookup"><span data-stu-id="1eea3-113">Device security</span></span>     | <span data-ttu-id="1eea3-114">Se [enhetens säkerhet](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="1eea3-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="1eea3-115">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="1eea3-115">Identity and access management</span></span>     | <span data-ttu-id="1eea3-116">Se [identitets-och åtkomst hantering](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="1eea3-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="1eea3-117">Nätverks säkerhet</span><span class="sxs-lookup"><span data-stu-id="1eea3-117">Network security</span></span>     | <span data-ttu-id="1eea3-118">Se [nätverks säkerhet](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="1eea3-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="1eea3-119">Informations säkerhet</span><span class="sxs-lookup"><span data-stu-id="1eea3-119">Information security</span></span>     |  <span data-ttu-id="1eea3-120">Se [informations säkerhet](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="1eea3-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="1eea3-121">Återställning av data</span><span class="sxs-lookup"><span data-stu-id="1eea3-121">Data recovery</span></span>     | <span data-ttu-id="1eea3-122">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="1eea3-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="1eea3-123">Grundläggande produktivitet</span><span class="sxs-lookup"><span data-stu-id="1eea3-123">Core productivity</span></span>     | <span data-ttu-id="1eea3-124"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="1eea3-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="1eea3-125">Läsa</span><span class="sxs-lookup"><span data-stu-id="1eea3-125">Browser</span></span>     | <span data-ttu-id="1eea3-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1eea3-126">Microsoft Edge</span></span>        |




<span data-ttu-id="1eea3-127">Microsoft Managed Desktop kan övervaka andra program som körs på hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="1eea3-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="1eea3-128">Om det påverkar enhets hantering, enhetens säkerhet, prestanda eller pålitlighet negativt kan du behöva begära ett [undantag för tjänste abonnemanget](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="1eea3-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
