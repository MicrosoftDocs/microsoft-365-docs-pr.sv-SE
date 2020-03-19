---
title: Felsöka problem med Tjänsten Microsoft Threat Protection
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "42808631"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Felsöka problem med Tjänsten Microsoft Threat Protection

**Gäller:**
- Microsofts hotskydd

I det här avsnittet beskrivs problem som kan uppstå när du använder Microsoft Threat Protection-tjänsten.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Jag ser inte Microsoft Threat Protection-innehåll
Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Jakt i portalen, måste du kontrollera att din klient har rätt licenser. 

Mer information finns i [Förutsättningar](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP-aviseringar visas inte i Microsoft Threat Protection-incidenterna
Om du har Azure ATP distribuerat i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du se till att Microsoft Cloud App Security och Azure ATP-integrering är aktiverad. 

Mer information finns i [Azure ATP-integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Är Microsoft Threat Protection tillgängligt för GCC (US Government Community Cloud) eller GCC High?
För närvarande är den inte tillgänglig.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var finns inställningssidan för att slå på tjänsten?
Om du vill aktivera Microsoft Threat Protection kommer du åt **Inställningar** från navigeringsfönstret i Microsoft 365-säkerhetscentret. Det här [navigeringsobjektet](mtp-enable.md#check-license-eligibility-and-required-permissions)visas bara om du har behörighet och licenser .

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>Kan jag använda ett tillägg i stället för de E5-licenser som krävs?
Det finns för närvarande inga tillägg för Microsoft Threat Protection. [Se licenskrav](prerequisites.md) 

