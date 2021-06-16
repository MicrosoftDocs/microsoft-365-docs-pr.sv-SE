---
title: Utvärdera Microsoft Defender Antivirus
description: Företag av alla storlekar kan använda den här guiden till att utvärdera och testa skyddet som Microsoft Defender Antivirus i Windows 10.
keywords: Microsoft Defender Antivirus, molnskydd, moln, skydd mot skadlig programvara, säkerhet, defender, utvärdera, testa, skydda, jämföra, realtidsskydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c558a7799bff61a0ee80db31ee476ad611053c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926625"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Utvärdera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Använd den här guiden för att avgöra Microsoft Defender Antivirus skyddar datorn mot virus, skadlig programvara och potentiellt oönskade program.

>[!TIP]
>Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar och se hur de fungerar:
>- Molnbaserat skydd
>- Fast learning (inklusive Block at first sight)
>- Potentiellt oönskad programblockering

Här förklaras de viktiga nästa generations skyddsfunktioner i Microsoft Defender Antivirus tillgängligt för både små och stora företag, och hur de ökar identifieringen av skadlig programvara och skyddet över nätverket.

Du kan välja att konfigurera och utvärdera varje inställning oberoende av varandra eller alla samtidigt. Vi har grupperat liknande inställningar baserat på vanliga utvärderingsscenarier och innehåller instruktioner för hur du använder PowerShell för att aktivera inställningarna.

Guiden är tillgänglig i PDF-format för offlinevisning:

- [Ladda ned guiden i PDF-format](https://www.microsoft.com/download/details.aspx?id=54795)

Du kan också ladda ned en PowerShell som automatiskt aktiverar alla inställningar som beskrivs i guiden. Du kan hämta skriptet tillsammans med PDF-nedladdningen ovan eller individuellt från PowerShell-galleriet:

- [Ladda ned PowerShell-skriptet för att automatiskt konfigurera inställningarna](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Guiden är för närvarande avsedd för en datorutvärdering av Microsoft Defender Antivirus. Det är inte lämpligt att aktivera alla inställningar i den här guiden för verkliga distributioner.
>
> De senaste rekommendationerna för distribution i realtid och övervakning av Microsoft Defender Antivirus över ett nätverk finns i [Distribuera Microsoft Defender Antivirus.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)