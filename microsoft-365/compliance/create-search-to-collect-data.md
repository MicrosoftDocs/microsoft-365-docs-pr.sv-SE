---
title: Skapa en sökning
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
description: Lär dig hur du skapar, definierar och väljer biblioteksplatser för en sökning i ett Advanced eDiscovery fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "52161565"
---
# <a name="create-a-search"></a>Skapa en sökning

På fliken **Sökningar** i ditt ärende kan du skapa en ny sökning genom att klicka **på Ny sökning** och följa guiden.

![Sökguiden i ett Advanced eDiscovery ärende](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Namnge sökningen och ge den en beskrivning

Varje sökning med ett ärende ska ha ett unikt namn. Du kan också ange en beskrivning för sökningen. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Välj de andrekteriska och uppsövande platserna att söka på

Välj plats för det dokument du vill söka efter genom att ange att dokumentare som du har lagt till i ärendet. Om du väljer en vårdnadshavare körs sökningen mot alla datakällor som är mappade till den inskanssonen. Du kan också begränsa sökningen till valda datakällor för varje enskild person. Mer information om hur du lägger till och hanterar käll sereer och hanterar deras datakällor finns i [Arbeta med biblioteksvårdare.](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>Välja platser som inte är insövade

I vissa fall kan du vilja söka i datakällor som inte är associerade med en vårdnadshavare. I det här fallet kan du ange platser du vill söka på eller välja att söka efter alla innehållsplatser för en viss Microsoft-tjänst (till exempel söka i alla Exchange-postlådor eller alla SharePoint-webbplatser och OneDrive-konton).

## <a name="define-the-search-query-and-conditions"></a>Definiera sökfrågan och villkoren

Du kan definiera nyckelordsfrågan och eventuella villkor för sökningen med hjälp av de förbyggda villkorskorten eller med Hjälp av Keyword Query Language (KQL). Mer information finns i [Skapa sökfrågor.](building-search-queries.md)
