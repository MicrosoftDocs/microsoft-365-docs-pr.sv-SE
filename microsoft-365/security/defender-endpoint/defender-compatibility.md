---
title: Kompatibilitet med antivirusprogram med Defender för Slutpunkt
description: Läs mer om Windows Defender fungerar med Microsoft Defender för Endpoint och hur den fungerar när en tredjepartsklient mot skadlig programvara används.
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
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782891"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Kompatibilitet med antivirusprogram med Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Agenten Microsoft Defender för slutpunkt är beroende Microsoft Defender Antivirus vissa funktioner, till exempel genomsökning av filer.

>[!IMPORTANT]
>Defender för Endpoint följer inte inställningarna för Microsoft Defender Antivirus undantag. 

Du måste konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett Microsoft Defender Antivirus är aktiv program mot skadlig programvara eller inte. Mer information finns i Hantera [uppdateringar Microsoft Defender Antivirus använda baslinjer.](manage-updates-baselines-microsoft-defender-antivirus.md)

Om en enhet som finns ombord är skyddad av en tredjepartsklient mot skadlig programvara Microsoft Defender Antivirus den slutpunkten gå in i passivt läge.

Microsoft Defender Antivirus fortsätter att ta emot uppdateringar och *mspeng.exe-processen* anges som en tjänst som körs, men genomsökningar utförs inte och ersätter inte den datorprogram mot skadlig programvara från tredje part som körs.

Gränssnittet Microsoft Defender Antivirus inaktiveras och användare på enheten kommer inte att kunna använda det Microsoft Defender Antivirus att utföra genomsökningar på begäran eller konfigurera de flesta alternativ.

Mer information finns i avsnittet [om Microsoft Defender Antivirus Och Defender för Slutpunktskompatibilitet.](microsoft-defender-antivirus-compatibility.md)
