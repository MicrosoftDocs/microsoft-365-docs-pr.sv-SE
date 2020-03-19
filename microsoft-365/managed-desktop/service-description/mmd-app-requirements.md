---
title: Appkrav för Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42811812"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="71bf2-103">Appkrav för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="71bf2-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="71bf2-104">För att garantera prestanda, tillförlitlighet och serviceför tjänster får en kunds bransch inte allvarligt påverka slutanvändarens upplevelse eller ändra säkerhetsinriktningen.</span><span class="sxs-lookup"><span data-stu-id="71bf2-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="71bf2-105">Därför måste affärsprogram som du vill distribuera till Microsoft Managed Desktop-enheter uppfylla kraven i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="71bf2-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="71bf2-106">Ansökan villkor</span><span class="sxs-lookup"><span data-stu-id="71bf2-106">Application condition</span></span>

<span data-ttu-id="71bf2-107">Det är viktigt att program inte påverkar Microsoft Managed Desktop negativt.</span><span class="sxs-lookup"><span data-stu-id="71bf2-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="71bf2-108">Följande är de krav som ett program måste uppfylla för att ett program ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="71bf2-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="71bf2-109">För ett visst program eller en viss drivrutin får Microsoft avstå från alla krav som anges häri.</span><span class="sxs-lookup"><span data-stu-id="71bf2-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="71bf2-110">Microsoft kan besluta att ta bort alla program eller drivrutiner som påverkar prestanda och tillförlitlighet på Microsoft Managed Desktop-enheter negativt.</span><span class="sxs-lookup"><span data-stu-id="71bf2-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="71bf2-111">Centralt hanterade appar</span><span class="sxs-lookup"><span data-stu-id="71bf2-111">Centrally managed apps</span></span>

<span data-ttu-id="71bf2-112">Alla program och drivrutiner som är installerade på Microsoft Managed Devices måste distribueras via Microsoft Intune, Microsoft Store eller Microsoft Store for Business. Om det är tillgängligt distribueras även drivrutiner via Windows Update-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="71bf2-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="71bf2-113">Förbjudna appklasser</span><span class="sxs-lookup"><span data-stu-id="71bf2-113">Prohibited app classes</span></span>

<span data-ttu-id="71bf2-114">Vissa programtyper är inte tillåtna på Microsoft Managed Desktop-enheter:</span><span class="sxs-lookup"><span data-stu-id="71bf2-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="71bf2-115">Tredjepartsantivirusprogram, säkerhets- eller granskningsprogram för tredje part</span><span class="sxs-lookup"><span data-stu-id="71bf2-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="71bf2-116">Versioner av Microsoft Office före Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="71bf2-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="71bf2-117">Program som installerar eller paketerar annan programvara från tredje part</span><span class="sxs-lookup"><span data-stu-id="71bf2-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="71bf2-118">Begränsade appbeteenden</span><span class="sxs-lookup"><span data-stu-id="71bf2-118">Restricted app behaviors</span></span>

<span data-ttu-id="71bf2-119">Vissa appbeteenden kan påverka användarupplevelsen negativt eller utgöra en säkerhetsrisk för Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="71bf2-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="71bf2-120">Appar med följande beteenden får inte köras i Microsoft Managed Desktop-miljön utan en specifik från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71bf2-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="71bf2-121">Användarupplevelse:</span><span class="sxs-lookup"><span data-stu-id="71bf2-121">User Experience:</span></span>
- <span data-ttu-id="71bf2-122">Installera bakgrundstjänster</span><span class="sxs-lookup"><span data-stu-id="71bf2-122">Install background services</span></span>
- <span data-ttu-id="71bf2-123">Lägga till sig själv i startsökvägen för Windows</span><span class="sxs-lookup"><span data-stu-id="71bf2-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="71bf2-124">Program som är beroende av drivrutiner</span><span class="sxs-lookup"><span data-stu-id="71bf2-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="71bf2-125">Webbläsare i tredje part</span><span class="sxs-lookup"><span data-stu-id="71bf2-125">3rd party web browsers</span></span>

<span data-ttu-id="71bf2-126">Säkerhet:</span><span class="sxs-lookup"><span data-stu-id="71bf2-126">Security:</span></span>
- <span data-ttu-id="71bf2-127">Höj slutanvändarens privilegier</span><span class="sxs-lookup"><span data-stu-id="71bf2-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="71bf2-128">Fungera som en appbutik eller ha en inbyggd förlängningshanterare</span><span class="sxs-lookup"><span data-stu-id="71bf2-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="71bf2-129">Ha kända säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="71bf2-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="71bf2-130">Kryptera eller begränsa åtkomsten till slutanvändardata</span><span class="sxs-lookup"><span data-stu-id="71bf2-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="71bf2-131">Är osignerad eller signerad med ett certifikat som inte summeras till en betrodd rot</span><span class="sxs-lookup"><span data-stu-id="71bf2-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="71bf2-132">Drivrutinsdistribution</span><span class="sxs-lookup"><span data-stu-id="71bf2-132">Driver deployment</span></span>

<span data-ttu-id="71bf2-133">Microsoft Managed Desktop stöder endast drivrutiner som är tillgängliga via Windows Update eller installeras inkorg med Microsoft Managed Device.</span><span class="sxs-lookup"><span data-stu-id="71bf2-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="71bf2-134">Om ett program kräver att en viss drivrutin/ett eller de körs betraktas det som ett begränsat program och kräver ett undantag innan det distribueras till Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="71bf2-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exception before being deployed to Microsoft Managed Desktop.</span></span> 

