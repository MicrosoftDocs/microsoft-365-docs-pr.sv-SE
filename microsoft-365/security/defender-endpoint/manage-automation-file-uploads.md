---
title: Hantera uppladdningar av automatiseringsfiler
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076913"
---
# <a name="manage-automation-file-uploads"></a>Hantera uppladdningar av automatiseringsfiler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Aktivera funktionen för innehållsanalys så att vissa filer och e-postbilagor automatiskt kan laddas upp till molnet för ytterligare kontroll i Automatiserad undersökning.

Identifiera filerna och e-postbilagor genom att ange filnamnstillägget och filnamnstillägget för e-post. 

Om du till exempel lägger till *exe* och *bat* som filnamnstillägg för filer eller bifogade filer, skickas alla filer eller bifogade filer med dessa tillägg automatiskt till molnet för ytterligare kontroll under Automatisk undersökning. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Lägg till filnamnstillägg och filnamn för bifogade filer.

1. Välj Inställningar Automation **filuppladdningar**  >  **i navigeringsfönstret.** 

2. Ändra inställningen för innehållsanalys mellan **På** och **Av.**

3. Konfigurera följande tilläggsnamn och separata tilläggsnamn med kommatecken:
   - **Filnamnstillägg** – Misstänkta filer utom e-postbilagor skickas för ytterligare kontroll
  

## <a name="related-topics"></a>Relaterade ämnen
- [Hantera undantag för automatiseringsmappar](manage-automation-folder-exclusions.md)
