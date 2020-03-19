---
title: Reparationsåtgärder i Office 365 automatisk undersökning och svar
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
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836864"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Reparationsåtgärder efter en automatisk undersökning i Office 365

## <a name="remediation-actions"></a>Åtgärder för sanering

[Automatiska gransknings- och svarsfunktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) i [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 omfattar vissa reparationsåtgärder. När en automatisk undersökning körs eller har slutförts ser du vanligtvis en eller flera reparationsåtgärder som kräver godkännande av säkerhetsgruppen för att fortsätta. 

I följande tabell sammanfattas de reparationsåtgärder som för närvarande är tillgängliga i Office 365 ATP. 

|Åtgärder | Beskrivning |
|-----|-----|
|Blockera URL (tid-för-klick) |Skyddar mot e-postmeddelanden och dokument som innehåller skadliga webbadresser. Detta gör det möjligt att blockera skadliga länkar och eventuella relaterade webbsidor via [Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) när användaren klickar på en länk i en befintlig Office-fil eller i ett äldre e-postmeddelande. |
|Soft delete e-post  |Mjuka borttagning av specifika e-postmeddelanden från en användares postlåda. <br/>Ett meddelande som tagits bort med mjuka borttaget flyttas till en användares mappen Recoverable Items och behålls tills kvarhållningsperioden för borttaget av objektet upphör att gälla. |
|Mjuka borttagning s-postkluster  |Mjuka borttagning av skadliga e-postmeddelanden som matchar en fråga från alla användares postlådor. <br/>Mjuka borttagna meddelanden flyttas till mappen Recoverable Items och behålls tills den borttagna objektretentionsperioden upphör att gälla. |
|Inaktivera vidarebefordran av extern e-post |Tar bort en vidarebefordringsregel från en viss slutanvändares postlåda.|

> [!NOTE]
> I Office 365 ATP vidtas inga reparationsåtgärder automatiskt. Reparationsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam. 

## <a name="next-steps"></a>Nästa steg

- [Visa väntande eller slutförda reparationsåtgärder efter en automatisk undersökning i Office 365](air-review-approve-pending-completed-actions.md)

- [Information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)