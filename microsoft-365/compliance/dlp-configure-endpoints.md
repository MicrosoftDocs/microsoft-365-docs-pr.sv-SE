---
title: Onboarding-metoder och -verktyg för Windows 10 enheter
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Introducera Windows 10 enheter så att de kan skicka sensordata till Microsoft 365 efterlevnadslösningar
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341706"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Registreringsverktyg och -metoder för Windows 10-enheter

**Gäller för:**
- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](./endpoint-dlp-learn-about.md)

Enheter i organisationen måste vara konfigurerade så att Microsoft 365 dataförlustskydd för slutpunkten kan få sensordata från dem. Det finns olika metoder och distributionsverktyg som du kan använda för att konfigurera enheter i din organisation.

Följande distributionsverktyg och -metoder stöds:

- grupprincip
- Microsoft Endpoint Configuration Manager
- Hantering av mobila enheter (inklusive Microsoft Intune)
- lokalt skript

## <a name="in-this-section"></a>I det här avsnittet
Ämne | Beskrivning
:---|:---
[Introducera Windows 10 enheter med grupprincip](dlp-configure-endpoints-gp.md) | Använd Grupprincip för att distribuera konfigurationspaketet på enheter.
[Introducera Windows enheter med hjälp av Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Du kan använda antingen Microsoft Endpoint Configuration Manager (current branch) version 1606 eller Microsoft Endpoint Configuration Manager (current branch) version 1602 eller tidigare för att distribuera konfigurationspaket på enheter.
[Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](dlp-configure-endpoints-mdm.md) | Använd verktyg för hantering av mobila enheter eller Microsoft Intune till att distribuera konfigurationspaketet på enheten.
[Registrera Windows 10-enheter med ett lokalt skript](dlp-configure-endpoints-script.md) | Lär dig hur du använder det lokala skriptet för att distribuera konfigurationspaketet på slutpunkter.
[Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md) | Lär dig hur du använder konfigurationspaketet för att konfigurera VDI-enheter.