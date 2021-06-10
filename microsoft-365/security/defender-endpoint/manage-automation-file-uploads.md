---
title: Hantera uppladdningar av automationsfil
description: Aktivera innehållsanalys och konfigurera filnamnstillägg och e-posttillägg för bifogade filer som ska skickas för analys
keywords: automation, fil, uppladdningar, innehåll, analys, fil, anknytning, e-post, bifogad fil
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185855"
---
# <a name="manage-automation-file-uploads"></a>Hantera uppladdningar av automationsfil

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Aktivera funktionen för innehållsanalys så att vissa filer och e-postbilagor automatiskt kan laddas upp till molnet för ytterligare kontroll i Automatiserad undersökning.

Identifiera filerna och e-postbilagor genom att ange filnamnstillägget och filnamnstillägget för e-post. 

Om du till exempel lägger till *exe* och *bat* som filnamnstillägg för filer eller bifogade filer, skickas alla filer eller bifogade filer med dessa tillägg automatiskt till molnet för ytterligare kontroll under Automatisk undersökning. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Lägg till filnamnstillägg och filnamn för bifogade filer.

1. I navigeringsfönstret väljer du **Inställningar**  >  **automationsfiluppladdningar**. 

2. Ändra inställningen för innehållsanalys mellan **På** och **Av.**

3. Konfigurera följande tilläggsnamn och separata tilläggsnamn med kommatecken:
   - **Filnamnstillägg** – Misstänkta filer utom e-postbilagor skickas för ytterligare kontroll
  

## <a name="related-topics"></a>Relaterade ämnen
- [Hantera undantag från automationsmappar](manage-automation-folder-exclusions.md)
