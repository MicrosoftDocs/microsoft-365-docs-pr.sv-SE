---
title: Felsöka tjänstproblem i Microsoft 365 Defender
description: Hitta lösningar och lösningar på kända problem med Microsoft 365 Defender
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925724"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Felsöka tjänstproblem i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Det här avsnittet tar upp problem som kan uppstå när du använder Tjänsten Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Jag ser inte Microsoft 365 Defender-innehåll

Om du inte ser funktioner i navigeringsfönstret, som Incidenter, Åtgärdscenter eller Sök i portalen, måste du kontrollera att klientorganisationen har rätt licenser.

Mer information finns i [Förutsättningarna.](prerequisites.md)

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender för identitetsaviseringar visas inte i Microsoft 365 Defender-incidenterna

Om du har Distribuerat Microsoft Defender för identitet i din miljö men inte ser Defender för identitetsaviseringar som en del av Microsoft 365 Defender-incidenter måste du se till att Microsoft Cloud App Security och Defender för identitetsintegrering är aktiverade.

Mer information finns i [Microsoft Defender för identitetsintegrering.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var finns inställningssidan för att aktivera tjänsten?

Om du vill aktivera Microsoft 365 Defender öppnar du Inställningar från navigeringsfönstret i Säkerhetscenter för Microsoft 365.  Det här navigeringsobjektet visas bara om du har nödvändiga [behörigheter och licenser.](mtp-enable.md#check-license-eligibility-and-required-permissions)
