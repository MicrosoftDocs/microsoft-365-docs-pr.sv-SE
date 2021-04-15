---
title: Utvärdera Microsoft Defender Antivirus
description: Företag av alla storlekar kan använda den här guiden för att utvärdera och testa skyddet som erbjuds av Microsoft Defender Antivirus i Windows 10.
keywords: Microsoft Defender Antivirus, molnskydd, moln, program mot skadlig programvara, säkerhet, defender, utvärdera, testa, skydd, jämföra, realtidsskydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764837"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Utvärdera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Använd den här guiden för att avgöra hur väl Microsoft Defender Antivirus skyddar dig mot virus, skadlig programvara och potentiellt oönskade program.

>[!TIP]
>Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar och se hur de fungerar:
>- Moln levererat skydd
>- Fast learning (inklusive Block at first sight)
>- Potentiellt oönskad programblockering

Här förklaras viktiga nästa generations skyddsfunktioner i Microsoft Defender Antivirus som är tillgängliga för både små och stora företag, och hur de ökar skyddet mot skadlig programvara i nätverket.

Du kan välja att konfigurera och utvärdera varje inställning oberoende av varandra eller alla samtidigt. Vi har grupperat liknande inställningar baserat på vanliga utvärderingsscenarier och innehåller instruktioner för hur du använder PowerShell för att aktivera inställningarna.

Guiden är tillgänglig i PDF-format för offlinevisning:

- [Ladda ned guiden i PDF-format](https://www.microsoft.com/download/details.aspx?id=54795)

Du kan också ladda ned en PowerShell som automatiskt aktiverar alla inställningar som beskrivs i guiden. Du kan hämta skriptet tillsammans med PDF-nedladdningen ovan eller individuellt från PowerShell-galleriet:

- [Ladda ned PowerShell-skriptet för att automatiskt konfigurera inställningarna](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Guiden är för närvarande avsedd för en datorutvärdering av Microsoft Defender Antivirus. Det är inte lämpligt att aktivera alla inställningar i den här guiden för verkliga distributioner.
>
> De senaste rekommendationerna för distribution och övervakning av Microsoft Defender Antivirus i hela nätverket finns i [Distribuera Microsoft Defender Antivirus.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)