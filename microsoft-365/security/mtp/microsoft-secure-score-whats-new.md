---
title: Nyheter i Microsofts säkra Poäng
description: Här beskrivs vilka nya ändringar som har hänt för säkert Poäng i Microsoft 365 säkerhets Center.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, Microsoft-säkerhet, Microsoft 365 säkerhets Center
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367121"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="5b02c-104">Nyheter i Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="5b02c-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5b02c-105">Vi har gjort några ändringar för att göra Microsoft säkert poäng en bättre representant för dina säkerhets Posture.</span><span class="sxs-lookup"><span data-stu-id="5b02c-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="5b02c-106">Om du vill veta mer om planerade ändringar kan du läsa [vad som kommer i Microsofts säkra Poäng?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="5b02c-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="5b02c-107">November 2020</span><span class="sxs-lookup"><span data-stu-id="5b02c-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="5b02c-108">3 tjänster-relaterade förbättrings åtgärder för Microsoft Defender för slut punkten (tidigare Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="5b02c-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="5b02c-109">Åtgärda den icke-citerade tjänst Sök vägen för Windows-tjänster</span><span class="sxs-lookup"><span data-stu-id="5b02c-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="5b02c-110">Ändra sökvägen till den körbara filen till en gemensam skyddad plats</span><span class="sxs-lookup"><span data-stu-id="5b02c-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="5b02c-111">Ändra tjänst konto för att undvika cachelagrat lösen ord i Windows-registret</span><span class="sxs-lookup"><span data-stu-id="5b02c-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="5b02c-112">Oktober 2020</span><span class="sxs-lookup"><span data-stu-id="5b02c-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="5b02c-113">Ta bort förbättrings åtgärd relaterad till Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="5b02c-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="5b02c-114">Ange webb innehålls kontroll för Windows Store-appen för Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="5b02c-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="5b02c-115">Augusti 2020</span><span class="sxs-lookup"><span data-stu-id="5b02c-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="5b02c-116">Uppdaterad förbättrings åtgärd för Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5b02c-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="5b02c-117">Aktivera princip för blockering av bakåtkompatibel-verifikation</span><span class="sxs-lookup"><span data-stu-id="5b02c-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="5b02c-118">Inkompatibilitet med identitets säkra poäng-och diagram-API</span><span class="sxs-lookup"><span data-stu-id="5b02c-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="5b02c-119">I den senaste versionen av Microsofts säkra poäng är en förbättrad Poäng modell släppt.</span><span class="sxs-lookup"><span data-stu-id="5b02c-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="5b02c-120">Dessa ändringar ger en mer flexibel och korrekt översikt av dina säkerhets Posture.</span><span class="sxs-lookup"><span data-stu-id="5b02c-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="5b02c-121">Men de här uppdateringarna har gjort Microsoft säker Poäng tillfälligt inkompatibelt med identitets säkra poäng och diagram-API.</span><span class="sxs-lookup"><span data-stu-id="5b02c-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="5b02c-122">I tid kommer identitets säkra poäng och Graph API att anta den nya bedömnings modellen.</span><span class="sxs-lookup"><span data-stu-id="5b02c-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="5b02c-123">Till dess kommer kunderna att se skillnaderna i resultaten som rapporter ATS av säkra poäng, identitets säkra poäng och diagram-API.</span><span class="sxs-lookup"><span data-stu-id="5b02c-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="5b02c-124">Vi ber om ursäkt för eventuella besvär som det här orsakar och arbetar för att säkerställa att dessa upplevelser är mer kompatibla i framtiden.</span><span class="sxs-lookup"><span data-stu-id="5b02c-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="5b02c-125">Uppdaterade förbättrings åtgärder</span><span class="sxs-lookup"><span data-stu-id="5b02c-125">Updated improvement actions</span></span>

- <span data-ttu-id="5b02c-126">Åtgärder för Azure Active Directory-förbättring har lagts till</span><span class="sxs-lookup"><span data-stu-id="5b02c-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="5b02c-127">Microsoft Defender för förbättrings åtgärder har lagts till</span><span class="sxs-lookup"><span data-stu-id="5b02c-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="5b02c-128">Stöd för Microsoft Defender för att skydda slut punkter [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) säkerhets rekommendationer</span><span class="sxs-lookup"><span data-stu-id="5b02c-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="5b02c-129">Alla publicerade säkerhets rekommendationer från TVM är nu tillgängliga</span><span class="sxs-lookup"><span data-stu-id="5b02c-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="5b02c-130">Uppdaterat gränssnitt och funktioner</span><span class="sxs-lookup"><span data-stu-id="5b02c-130">Updated interface and functionality</span></span>

* <span data-ttu-id="5b02c-131">Alla nya mått och trender för diskussioner på CISO och lead-nivå</span><span class="sxs-lookup"><span data-stu-id="5b02c-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="5b02c-132">Nya sätt att spåra och mäta Poäng</span><span class="sxs-lookup"><span data-stu-id="5b02c-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="5b02c-133">Bättre spårning och förståelse för resultat regressioner</span><span class="sxs-lookup"><span data-stu-id="5b02c-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="5b02c-134">Filtrera, tagga, söka och gruppera dina förbättrings åtgärder</span><span class="sxs-lookup"><span data-stu-id="5b02c-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="5b02c-135">Hantera dina framtida mål med Poäng prognoser och planerade åtgärder</span><span class="sxs-lookup"><span data-stu-id="5b02c-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="5b02c-136">Och mer!</span><span class="sxs-lookup"><span data-stu-id="5b02c-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5b02c-137">Vi vill höra från dig</span><span class="sxs-lookup"><span data-stu-id="5b02c-137">We want to hear from you</span></span>

<span data-ttu-id="5b02c-138">Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span><span class="sxs-lookup"><span data-stu-id="5b02c-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5b02c-139">Vi övervakar communityn och ger hjälp.</span><span class="sxs-lookup"><span data-stu-id="5b02c-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5b02c-140">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="5b02c-140">Related resources</span></span>

- [<span data-ttu-id="5b02c-141">Utvärdera säkerhets genom övergå molnet</span><span class="sxs-lookup"><span data-stu-id="5b02c-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="5b02c-142">Spåra din Microsoft säkra Poäng historik och uppfylla målen</span><span class="sxs-lookup"><span data-stu-id="5b02c-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5b02c-143">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="5b02c-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
