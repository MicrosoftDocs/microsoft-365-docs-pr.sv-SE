---
title: Förhandsversionsfunktioner i Microsoft Defender för slutpunkt
description: Lär dig hur du kommer åt förhandsversionsfunktioner för Microsoft Defender för slutpunkt.
keywords: förhandsgranska, förhandsversion, Microsoft Defender för Slutpunkt, funktioner, uppdateringar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339496"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="0811c-104">Förhandsversionsfunktioner i Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="0811c-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0811c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0811c-105">**Applies to:**</span></span>
- [<span data-ttu-id="0811c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0811c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0811c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0811c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0811c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0811c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0811c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0811c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0811c-110">Defender för Endpoint-tjänsten uppdateras hela tiden med nya funktionsförbättringar och funktioner.</span><span class="sxs-lookup"><span data-stu-id="0811c-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="0811c-111">Lär dig mer om nya funktioner i förhandsversionen av Defender för slutpunkt och bli bland de första som kan prova kommande funktioner genom att aktivera förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="0811c-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="0811c-112">Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="0811c-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="0811c-113">Mer information om nya funktioner som är allmänt tillgängliga finns i [Vad är nytt i Defender för slutpunkt.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="0811c-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="0811c-114">Det här behöver du veta</span><span class="sxs-lookup"><span data-stu-id="0811c-114">What you need to know</span></span>

<span data-ttu-id="0811c-115">När du arbetar med funktioner i offentlig förhandsversion kan dessa funktioner:</span><span class="sxs-lookup"><span data-stu-id="0811c-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="0811c-116">Kan ha begränsade eller begränsade funktioner.</span><span class="sxs-lookup"><span data-stu-id="0811c-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="0811c-117">Funktionen kan till exempel bara användas på en plattform.</span><span class="sxs-lookup"><span data-stu-id="0811c-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="0811c-118">Vanligtvis går vi igenom funktionsändringar innan de blir allmänt tillgängliga (GA).</span><span class="sxs-lookup"><span data-stu-id="0811c-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="0811c-119">Microsoft har fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="0811c-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="0811c-120">Kan bara vara tillgängligt i vissa geografiska regioner eller molnmiljöer.</span><span class="sxs-lookup"><span data-stu-id="0811c-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="0811c-121">Funktionen kanske till exempel inte finns i myndighetsmoln.</span><span class="sxs-lookup"><span data-stu-id="0811c-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="0811c-122">Enskilda funktioner i förhandsversionen kan ha fler begränsningar för användning och support.</span><span class="sxs-lookup"><span data-stu-id="0811c-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="0811c-123">I så fall antecknas informationen vanligtvis i funktionsdokumentationen.</span><span class="sxs-lookup"><span data-stu-id="0811c-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="0811c-124">Förhandsversionerna tillhandahålls med en standardsupportnivå och kan användas för produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="0811c-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="0811c-125">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="0811c-125">Turn on preview features</span></span>

<span data-ttu-id="0811c-126">Du har tillgång till kommande funktioner som du kan lämna feedback på för att förbättra den övergripande upplevelsen innan funktionerna blir tillgängliga i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="0811c-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="0811c-127">Aktivera inställningen för förhandsversionen och var bland de första att prova kommande funktioner.</span><span class="sxs-lookup"><span data-stu-id="0811c-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="0811c-128">I navigeringsfönstret väljer du Knappen **Inställningar**  >  **avancerade funktioner för**  >  **förhandsgranskning.**</span><span class="sxs-lookup"><span data-stu-id="0811c-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="0811c-129">Ändra inställningen mellan På **och** **Av och** välj **Spara inställningar**.</span><span class="sxs-lookup"><span data-stu-id="0811c-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="0811c-130">Förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="0811c-130">Preview features</span></span>

<span data-ttu-id="0811c-131">Följande funktioner ingår i förhandsversionen:</span><span class="sxs-lookup"><span data-stu-id="0811c-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="0811c-132">Webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="0811c-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="0811c-133">Webbinnehållsfiltrering är en del av webbskyddsfunktionerna i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0811c-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0811c-134">Det gör att din organisation kan spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.</span><span class="sxs-lookup"><span data-stu-id="0811c-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="0811c-135">Många av dessa webbplatser, även om de inte är skadliga, kan vara problematiska på grund av regelefterlevnad, bandbreddsanvändning eller andra problem.</span><span class="sxs-lookup"><span data-stu-id="0811c-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="0811c-136">Rapport om enhetshälsa och efterlevnad</span><span class="sxs-lookup"><span data-stu-id="0811c-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="0811c-137">Rapporten om enhetens hälsa och efterlevnad ger detaljerad information om enheterna i din organisation.</span><span class="sxs-lookup"><span data-stu-id="0811c-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="0811c-138">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0811c-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0811c-139">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0811c-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
