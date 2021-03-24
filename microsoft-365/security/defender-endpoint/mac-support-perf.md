---
title: Felsöka prestandaproblem för Microsoft Defender ATP för Mac
description: Felsöka prestandaproblem i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070258"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="26b4c-104">Felsöka prestandaproblem för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="26b4c-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="26b4c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="26b4c-105">**Applies to:**</span></span>

- [<span data-ttu-id="26b4c-106">Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="26b4c-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="26b4c-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="26b4c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="26b4c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26b4c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="26b4c-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="26b4c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="26b4c-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="26b4c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="26b4c-111">Det här avsnittet innehåller några allmänna steg som kan användas för att begränsa prestandaproblem som rör Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="26b4c-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="26b4c-112">Realtidsskydd (RTP) är en funktion i Microsoft Defender för Endpoint för Mac som kontinuerligt övervakar och skyddar din enhet mot hot.</span><span class="sxs-lookup"><span data-stu-id="26b4c-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="26b4c-113">Den består av fil- och processövervakning och annan heuristics.</span><span class="sxs-lookup"><span data-stu-id="26b4c-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="26b4c-114">Beroende på vilka program du kör och enhetens egenskaper kan du uppleva underoptimal prestanda när du kör Microsoft Defender för Endpoint för Mac.</span><span class="sxs-lookup"><span data-stu-id="26b4c-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="26b4c-115">Särskilt program eller systemprocesser som har åtkomst till många resurser under ett kort tidspann kan leda till prestandaproblem i Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="26b4c-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="26b4c-116">Följande steg kan användas för att felsöka och minimera dessa problem:</span><span class="sxs-lookup"><span data-stu-id="26b4c-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="26b4c-117">Inaktivera realtidsskyddet med någon av följande metoder och se om prestandan förbättras.</span><span class="sxs-lookup"><span data-stu-id="26b4c-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="26b4c-118">Den här metoden begränsar om Microsoft Defender för Endpoint för Mac bidrar till prestandaproblemen.</span><span class="sxs-lookup"><span data-stu-id="26b4c-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="26b4c-119">Om din enhet inte hanteras av din organisation kan realtidsskydd inaktiveras med något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="26b4c-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="26b4c-120">Från användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="26b4c-120">From the user interface.</span></span> <span data-ttu-id="26b4c-121">Öppna Microsoft Defender för Slutpunkt för Mac och gå till **Hantera inställningar.**</span><span class="sxs-lookup"><span data-stu-id="26b4c-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Skärmbild på Hantera realtidsskydd](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="26b4c-123">Från terminalen.</span><span class="sxs-lookup"><span data-stu-id="26b4c-123">From the Terminal.</span></span> <span data-ttu-id="26b4c-124">Av säkerhetsskäl kräver den här åtgärden höjd.</span><span class="sxs-lookup"><span data-stu-id="26b4c-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="26b4c-125">Om enheten hanteras av din organisation kan realtidsskydd inaktiveras av administratören genom att följa anvisningarna i Ange inställningar för Microsoft Defender för [Slutpunkt för Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="26b4c-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="26b4c-126">Öppna Finder och gå **till**  >  **Programverktyg.**</span><span class="sxs-lookup"><span data-stu-id="26b4c-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="26b4c-127">Öppna **Aktivitetsrapporter** och analysera vilka program som använder resurserna på ditt system.</span><span class="sxs-lookup"><span data-stu-id="26b4c-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="26b4c-128">Vanliga exempel är programuppdateringsprogram och kompilatorer.</span><span class="sxs-lookup"><span data-stu-id="26b4c-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="26b4c-129">Konfigurera Microsoft Defender för slutpunkt för Mac med undantag för de processer eller diskutrymmen som bidrar till prestandaproblemen och återaktivera realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="26b4c-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="26b4c-130">Mer [information finns i Konfigurera och validera undantag för Microsoft Defender för Slutpunkt](mac-exclusions.md) för Mac.</span><span class="sxs-lookup"><span data-stu-id="26b4c-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
