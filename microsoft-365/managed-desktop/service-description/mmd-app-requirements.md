---
title: Microsoft Hanterat skrivbord för appar
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
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="defc6-103">Microsoft Hanterat skrivbord för appar</span><span class="sxs-lookup"><span data-stu-id="defc6-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="defc6-104">Microsoft Hanterat skrivbord kräver att vi hanterar enheter med en viss metod för att garantera enheternas prestanda, tillförlitlighet och servicebarhet.</span><span class="sxs-lookup"><span data-stu-id="defc6-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="defc6-105">Hanteringsområde</span><span class="sxs-lookup"><span data-stu-id="defc6-105">Management area</span></span>  |<span data-ttu-id="defc6-106">Microsoft Hanterat skrivbord metod</span><span class="sxs-lookup"><span data-stu-id="defc6-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="defc6-107">Enhetskonfiguration eller principhantering</span><span class="sxs-lookup"><span data-stu-id="defc6-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="defc6-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="defc6-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="defc6-109">Programhantering</span><span class="sxs-lookup"><span data-stu-id="defc6-109">Application management</span></span>     | <span data-ttu-id="defc6-110">Microsoft Intune och Företagsportal</span><span class="sxs-lookup"><span data-stu-id="defc6-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="defc6-111">Drivrutinsdistribution</span><span class="sxs-lookup"><span data-stu-id="defc6-111">Driver deployment</span></span>     |  <span data-ttu-id="defc6-112">Drivrutiner som ingår i enheten, Windows Update eller Intune</span><span class="sxs-lookup"><span data-stu-id="defc6-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="defc6-113">Enhetssäkerhet</span><span class="sxs-lookup"><span data-stu-id="defc6-113">Device security</span></span>     | <span data-ttu-id="defc6-114">Se [Enhetssäkerhet](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="defc6-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="defc6-115">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="defc6-115">Identity and access management</span></span>     | <span data-ttu-id="defc6-116">Se [Identitets- och åtkomsthantering](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="defc6-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="defc6-117">Nätverkssäkerhet</span><span class="sxs-lookup"><span data-stu-id="defc6-117">Network security</span></span>     | <span data-ttu-id="defc6-118">Se [Nätverkssäkerhet](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="defc6-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="defc6-119">Informationssäkerhet</span><span class="sxs-lookup"><span data-stu-id="defc6-119">Information security</span></span>     |  <span data-ttu-id="defc6-120">Se [Informationssäkerhet](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="defc6-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="defc6-121">Dataåterställning</span><span class="sxs-lookup"><span data-stu-id="defc6-121">Data recovery</span></span>     | <span data-ttu-id="defc6-122">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="defc6-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="defc6-123">Kärnproduktivitet</span><span class="sxs-lookup"><span data-stu-id="defc6-123">Core productivity</span></span>     | <span data-ttu-id="defc6-124"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="defc6-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="defc6-125">Webbläsare</span><span class="sxs-lookup"><span data-stu-id="defc6-125">Browser</span></span>     | <span data-ttu-id="defc6-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="defc6-126">Microsoft Edge</span></span>        |




<span data-ttu-id="defc6-127">Microsoft Hanterat skrivbord övervaka annan programvara som körs på hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="defc6-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="defc6-128">Om den påverkar enhetshantering, enhetssäkerhet, prestanda och tillförlitlighet negativt kan du behöva begära ett [undantag från tjänstplanen.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="defc6-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
