---
title: Test Base SDK för Python
description: Information om hur du förstår Test Bases SDK för Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323122"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="52bd2-103">Test Base SDK för Python</span><span class="sxs-lookup"><span data-stu-id="52bd2-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="52bd2-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="52bd2-104">Overview</span></span>
<span data-ttu-id="52bd2-105">Test Base SDK kan användas för att interagera med Azure-testbasresursen.</span><span class="sxs-lookup"><span data-stu-id="52bd2-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="52bd2-106">(t.ex. hantera ditt programpaket, inkludera skapa paket, redigera paket och ta bort paket)</span><span class="sxs-lookup"><span data-stu-id="52bd2-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="52bd2-107">I SDK ingår testsammanfattningen och Analysis Result som kan fås med: scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="52bd2-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="52bd2-108">Med Test Base SDK kan du integrera testbas i din CI/CD-pipeline.</span><span class="sxs-lookup"><span data-stu-id="52bd2-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="52bd2-109">Klientbibliotek</span><span class="sxs-lookup"><span data-stu-id="52bd2-109">Client Library</span></span>

<span data-ttu-id="52bd2-110">Installera testbaspaketet med pip.</span><span class="sxs-lookup"><span data-stu-id="52bd2-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="52bd2-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="52bd2-111">Example</span></span>
