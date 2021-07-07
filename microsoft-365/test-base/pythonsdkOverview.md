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
# <a name="test-base-sdk-for-python"></a>Test Base SDK för Python

## <a name="overview"></a>Översikt
Test Base SDK kan användas för att interagera med Azure-testbasresursen. (t.ex. hantera ditt programpaket, inkludera skapa paket, redigera paket och ta bort paket)

I SDK ingår testsammanfattningen och Analysis Result som kan fås med: scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.

Med Test Base SDK kan du integrera testbas i din CI/CD-pipeline.

## <a name="client-library"></a>Klientbibliotek

Installera testbaspaketet med pip.

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>Exempel
