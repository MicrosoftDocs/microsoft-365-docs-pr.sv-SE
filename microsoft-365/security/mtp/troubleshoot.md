---
title: Felsöka serviceproblem för Microsoft Threat Protection
description: Hitta lösningar och lösa information om kända problem med Microsoft Threat Protection
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844924"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Felsöka serviceproblem för Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

I det här avsnittet beskrivs problem som kan uppstå när du använder Microsoft Threat Protection-tjänsten.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Jag ser inte Microsoft Threat Protection-innehåll
Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Jakt i portalen, måste du kontrollera att din klient har rätt licenser. 

Mer information finns i [Förutsättningar](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP-aviseringar visas inte i Microsoft Threat Protection-incidenterna
Om du har Azure ATP distribuerat i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du se till att Microsoft Cloud App Security och Azure ATP-integrering är aktiverad. 

Mer information finns i [Azure ATP-integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var finns inställningssidan för att slå på tjänsten?
Om du vill aktivera Microsoft Threat Protection öppnar du **Inställningar** från navigeringsfönstret i Microsoft 365-säkerhetscentret. Det här [navigeringsobjektet](mtp-enable.md#check-license-eligibility-and-required-permissions)visas bara om du har behörighet och licenser .
 

