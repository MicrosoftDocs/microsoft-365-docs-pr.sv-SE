---
title: Nästan dubblettidentifiering – eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd nästan dubblettidentifiering om du vill gruppera dokument som liknar varandra när du analyserar ärendedata i Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161625"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Nästan dubblettidentifiering i Advanced eDiscovery

Överväg att granska en uppsättning dokument där en delmängd baseras på samma mall och oftast har samma exempelspråk, med några skillnader här och där. Om granskare skulle kunna identifiera den här deluppsättningen granskar du en av dem noggrant och granskar skillnaderna för resten. Då hade de inte missat någon unik information medan det tog endast en del tid som skulle ha tagit dem att läsa alla dokument omslag. Med en text som liknar varandra i närheten av dubblettidentifieringsgrupper blir granskningsprocessen effektivare.

## <a name="how-does-it-work"></a>Hur fungerar det?

När identifiering av nästan dubbletter körs parsar systemet alla dokument med text. Sedan jämförs alla dokument med varandra för att avgöra om deras likhet är större än det inställt tröskelvärdet. Om den är det grupperas dokumenten tillsammans. När alla dokument har jämförts och grupperats markeras ett dokument från varje grupp som "pivot". När du granskar dina dokument kan du granska en pivot först och granska de andra dokumenten i samma nästan dubblettuppsättning, med fokus på skillnaden mellan pivot och det dokument som granskas.
