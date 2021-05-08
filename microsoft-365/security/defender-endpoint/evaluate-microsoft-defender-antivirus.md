---
title: Utvärdera Microsoft Defender Antivirus
description: Företag av alla storlekar kan använda den här guiden till att utvärdera och testa skyddet som Microsoft Defender Antivirus i Windows 10.
keywords: Microsoft Defender Antivirus, molnskydd, moln, skydd mot skadlig programvara, säkerhet, defender, utvärdera, testa, skydda, jämföra, realtidsskydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274742"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="163c3-104">Utvärdera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="163c3-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="163c3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="163c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="163c3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="163c3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="163c3-107">Använd den här guiden för att avgöra Microsoft Defender Antivirus skyddar datorn mot virus, skadlig programvara och potentiellt oönskade program.</span><span class="sxs-lookup"><span data-stu-id="163c3-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="163c3-108">Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar och se hur de fungerar:</span><span class="sxs-lookup"><span data-stu-id="163c3-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="163c3-109">Molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="163c3-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="163c3-110">Fast learning (inklusive Block at first sight)</span><span class="sxs-lookup"><span data-stu-id="163c3-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="163c3-111">Potentiellt oönskad programblockering</span><span class="sxs-lookup"><span data-stu-id="163c3-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="163c3-112">Här förklaras de viktiga nästa generations skyddsfunktioner i Microsoft Defender Antivirus tillgängligt för både små och stora företag, och hur de ökar identifieringen av skadlig programvara och skyddet över nätverket.</span><span class="sxs-lookup"><span data-stu-id="163c3-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="163c3-113">Du kan välja att konfigurera och utvärdera varje inställning oberoende av varandra eller alla samtidigt.</span><span class="sxs-lookup"><span data-stu-id="163c3-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="163c3-114">Vi har grupperat liknande inställningar baserat på vanliga utvärderingsscenarier och innehåller instruktioner för hur du använder PowerShell för att aktivera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="163c3-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="163c3-115">Guiden är tillgänglig i PDF-format för offlinevisning:</span><span class="sxs-lookup"><span data-stu-id="163c3-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="163c3-116">Ladda ned guiden i PDF-format</span><span class="sxs-lookup"><span data-stu-id="163c3-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="163c3-117">Du kan också ladda ned en PowerShell som automatiskt aktiverar alla inställningar som beskrivs i guiden.</span><span class="sxs-lookup"><span data-stu-id="163c3-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="163c3-118">Du kan hämta skriptet tillsammans med PDF-nedladdningen ovan eller individuellt från PowerShell-galleriet:</span><span class="sxs-lookup"><span data-stu-id="163c3-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="163c3-119">Ladda ned PowerShell-skriptet för att automatiskt konfigurera inställningarna</span><span class="sxs-lookup"><span data-stu-id="163c3-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="163c3-120">Guiden är för närvarande avsedd för en datorutvärdering av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="163c3-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="163c3-121">Det är inte lämpligt att aktivera alla inställningar i den här guiden för verkliga distributioner.</span><span class="sxs-lookup"><span data-stu-id="163c3-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="163c3-122">De senaste rekommendationerna för distribution i realtid och övervakning av Microsoft Defender Antivirus över ett nätverk finns i [Distribuera Microsoft Defender Antivirus.](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="163c3-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="163c3-123">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="163c3-123">Related topics</span></span>

- [<span data-ttu-id="163c3-124">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="163c3-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="163c3-125">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="163c3-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)