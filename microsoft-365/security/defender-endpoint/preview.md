---
title: Förhandsversionsfunktioner i Microsoft Defender ATP
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
ms.openlocfilehash: 370048586c5ddfa6fa9ea265e929608357adf5df
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186887"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="76daf-104">Förhandsversionsfunktioner i Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="76daf-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="76daf-105">Förhandsversionerna tillhandahålls utan ett servicenivåavtal och det rekommenderas inte för produktionsarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="76daf-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="76daf-106">Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.</span><span class="sxs-lookup"><span data-stu-id="76daf-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="76daf-107">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="76daf-107">**Applies to:**</span></span>
- [<span data-ttu-id="76daf-108">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="76daf-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76daf-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76daf-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76daf-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="76daf-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76daf-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="76daf-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="76daf-112">Defender för Endpoint-tjänsten uppdateras hela tiden med nya funktionsförbättringar och funktioner.</span><span class="sxs-lookup"><span data-stu-id="76daf-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="76daf-113">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="76daf-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="76daf-114">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="76daf-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="76daf-115">Lär dig mer om nya funktioner i förhandsversionen av Defender för slutpunkt och bli bland de första som kan prova kommande funktioner genom att aktivera förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="76daf-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="76daf-116">Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="76daf-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="76daf-117">Mer information om nya funktioner som är allmänt tillgängliga finns i [Vad är nytt i Defender för slutpunkt.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="76daf-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="76daf-118">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="76daf-118">Turn on preview features</span></span>

<span data-ttu-id="76daf-119">Du har tillgång till kommande funktioner som du kan lämna feedback på för att förbättra den övergripande upplevelsen innan funktionerna blir tillgängliga i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="76daf-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="76daf-120">Aktivera inställningen för förhandsversionen och var bland de första att prova kommande funktioner.</span><span class="sxs-lookup"><span data-stu-id="76daf-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="76daf-121">I navigeringsfönstret väljer du Inställningar **Avancerade**  >  **funktioner**  >  **Förhandsgranskningsfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="76daf-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="76daf-122">Ändra inställningen mellan På **och** **Av och** välj **Spara inställningar**.</span><span class="sxs-lookup"><span data-stu-id="76daf-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="76daf-123">Förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="76daf-123">Preview features</span></span>

<span data-ttu-id="76daf-124">Följande funktioner ingår i förhandsversionen:</span><span class="sxs-lookup"><span data-stu-id="76daf-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="76daf-125">Webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="76daf-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="76daf-126">Webbinnehållsfiltrering är en del av webbskyddsfunktionerna i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="76daf-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="76daf-127">Det gör att din organisation kan spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.</span><span class="sxs-lookup"><span data-stu-id="76daf-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="76daf-128">Många av dessa webbplatser, även om de inte är skadliga, kan vara problematiska på grund av regelefterlevnad, bandbreddsanvändning eller andra problem.</span><span class="sxs-lookup"><span data-stu-id="76daf-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="76daf-129">Rapport om enhetshälsa och efterlevnad</span><span class="sxs-lookup"><span data-stu-id="76daf-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="76daf-130">Rapporten om enhetens hälsa och efterlevnad ger detaljerad information om enheterna i din organisation.</span><span class="sxs-lookup"><span data-stu-id="76daf-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="76daf-131">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="76daf-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="76daf-132">Informationsskydd är en integrerad del av Microsoft 365 Enterprise Suite, vilket ger intelligent skydd för att skydda känsliga data samtidigt som produktivitet på arbetsplatsen möjliggörs.</span><span class="sxs-lookup"><span data-stu-id="76daf-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="76daf-133">Microsoft Defender för Endpoint är sömlöst integrerat i Microsoft Threat Protection för att tillhandahålla en fullständig och omfattande DLP-lösning (Data Loss Prevention) för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="76daf-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="76daf-134">Delvis tillgängligt från Windows 10, version 1809.</span><span class="sxs-lookup"><span data-stu-id="76daf-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="76daf-135">Onboard Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="76daf-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="76daf-136">Microsoft Defender för Endpoint lägger nu till stöd för Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="76daf-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="76daf-137">Du kan hantera Windows Server 2019 på samma sätt som för Windows 10-klientenheter.</span><span class="sxs-lookup"><span data-stu-id="76daf-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="76daf-138">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="76daf-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76daf-139">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="76daf-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
