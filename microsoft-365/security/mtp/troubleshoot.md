---
title: Felsöka problem med Microsoft Threat Protection-tjänsten
description: Hitta lösningar och Undvik kända problem med Microsoft Threat Protection
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, sidan Inställningar
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
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201297"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Felsöka problem med Microsoft Threat Protection-tjänsten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

I det här avsnittet åtgärdas problem som kan uppstå när du använder tjänsten Microsoft Threat Protection.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Jag ser inte innehåll från Microsoft Threat Protection
Om du inte ser funktionerna i navigerings fönstret, till exempel händelser, åtgärds Center eller jakt på din portal, måste du verifiera att klient organisationen har rätt licenser. 

För mer information, se [förutsättningar](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP-meddelanden visas inte i Microsofts skydds händelser för hotet
Om du har distribuerat Azure ATP i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du kontrol lera att Microsoft Cloud App Security och Azure ATP-integreringen är aktive rad. 

Mer information finns i [integreringen av Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var är inställnings sidan för att aktivera tjänsten?
Aktivera åtkomst **Inställningar** för Microsoft Threat från navigerings fönstret i Microsoft 365 säkerhets Center. Det här navigerings objektet visas bara om du har [behörighet och licenser för nödvändig](mtp-enable.md#check-license-eligibility-and-required-permissions)installation.
 

