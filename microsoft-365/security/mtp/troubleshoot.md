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
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918672"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Felsöka tjänstproblem i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

I det här avsnittet behandlas problem som kan uppstå när du använder Microsoft 365 Defender-tjänsten.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Jag ser inte Microsoft 365 Defender-innehåll

Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Sök i portalen, måste du kontrollera att klientorganisationen har rätt licenser.

Mer information finns i [Krav](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender för identitetsaviseringar visas inte i Microsoft 365 Defender-incidenter

Om du har Microsoft Defender för identitet distribuerat i din miljö men du inte ser Defender för identitetsaviseringar som en del av Microsoft 365 Defender-incidenter måste du se till att Microsoft Cloud App-säkerhet och Defender för identitetsintegrering är aktiverat.

Mer information finns i [Microsoft Defender för identitetsintegrering.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var finns inställningssidan för att aktivera tjänsten?

Om du vill aktivera Microsoft 365 Defender öppnar du **Inställningar** från navigeringsfönstret i Säkerhetscenter för Microsoft 365. Det här navigeringsobjektet visas bara om du har nödvändiga [behörigheter och licenser.](mtp-enable.md#check-license-eligibility-and-required-permissions)