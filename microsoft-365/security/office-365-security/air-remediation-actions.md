---
title: Åtgärder för reparation i office 365-automatiska undersökningar och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Lär dig mer om reparationsåtgärder i automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955539"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Åtgärder för reparation efter en automatiserad undersökning i Office 365

## <a name="remediation-actions"></a>Åtgärder för reparation

[Automatiska undersöknings- och svarsfunktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) i [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 innehåller vissa åtgärder för reparation. När en automatisk undersökning körs eller har slutförts ser du vanligtvis en eller flera reparationsåtgärder som kräver godkännande av säkerhetsoperationsteamet för att fortsätta. 

I följande tabell sammanfattas de reparationsåtgärder som för närvarande är tillgängliga i Office 365 ATP. 

|Åtgärder | Beskrivning |
|-----|-----|
|Blockera URL (tid för klick) |Skyddar mot e-postmeddelanden och dokument som innehåller skadliga webbadresser. Detta gör det möjligt att blockera skadliga länkar och relaterade webbsidor via [Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) när användaren klickar på en länk i en befintlig Office-fil eller i ett äldre e-postmeddelande. |
|E-post med mjuk borttagning  |Ta bort vissa e-postmeddelanden från en användares postlåda. <br/>Ett mjukt borttaget meddelande flyttas till en användares mapp för återställningsbara objekt och behålls tills kvarhållningsperioden för borttaget objekt löper ut. |
|E-kluster för mjuk borttagning  |Ta bort skadliga e-postmeddelanden som matchar en fråga från alla användares postlådor. <br/>Meddelanden som tagits bort med mjuka objekt flyttas till användarnas mapp för återställningsbara objekt och behålls tills kvarhållningsperioden för borttaget objekt löper ut. |
|Inaktivera vidarebefordran av extern e-post |Tar bort en vidarebefordringsregel från en viss slutanvändarpostlåda.|

> [!NOTE]
> I Office 365 ATP vidtas inga åtgärder för reparation automatiskt. Reparationsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam. 

## <a name="next-steps"></a>Nästa steg

- [Visa väntande eller slutförda reparationsåtgärder efter en automatisk undersökning i Office 365](air-review-approve-pending-completed-actions.md)

- [Information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Automatiserad undersökning i Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsofts hotskydd](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)