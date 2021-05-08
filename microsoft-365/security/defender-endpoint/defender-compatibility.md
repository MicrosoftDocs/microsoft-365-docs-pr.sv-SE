---
title: Kompatibilitet med antivirusprogram med Defender för Slutpunkt
description: Läs mer om hur Windows Defender fungerar med Microsoft Defender för Endpoint och hur det fungerar när en tredjepartsklient mot skadlig programvara används.
keywords: windows defender-kompatibilitet, defender, Microsoft Defender för slutpunkt, defender för slutpunkt, antivirus, mde
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
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274886"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Kompatibilitet med antivirusprogram med Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Agenten Microsoft Defender för slutpunkt är beroende av Microsoft Defender Antivirus för vissa funktioner, till exempel genomsökning av filer.

>[!IMPORTANT]
>Defender för Endpoint följer inte inställningarna för undantag från Microsoft Defender Antivirus. 

Du måste konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett om Microsoft Defender Antivirus är aktivt mot skadlig programvara eller inte. Mer information finns i Hantera [uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)

Om en onboarded-enhet skyddas av en tredjepartsklient för program mot skadlig programvara kommer Microsoft Defender Antivirus för den slutpunkten att gå in i passivt läge.

Microsoft Defender Antivirus fortsätter att ta emot uppdateringar och *mspeng.exe-processen* visas som en tjänst som körs, men genomsökningar utförs inte och ersätter inte den datorprogram mot skadlig programvara från tredje part som körs.

Microsoft Defender Antivirus-gränssnittet inaktiveras och användare på enheten kan inte använda Microsoft Defender Antivirus för att utföra genomsökningar på begäran eller konfigurera de flesta alternativ.

Mer information finns i avsnittet [Microsoft Defender Antivirus och Defender om slutpunktskompatibilitet.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
