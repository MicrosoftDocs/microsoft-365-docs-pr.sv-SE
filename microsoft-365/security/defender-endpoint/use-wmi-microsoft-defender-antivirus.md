---
title: Konfigurera Microsoft Defender Antivirus med WMI
description: Lär dig hur du konfigurerar och Microsoft Defender Antivirus med hjälp av WMI-skript för att hämta, ändra och uppdatera inställningar i Microsoft Defender för Slutpunkt.
keywords: wmi, skript, instrument för Windows-hantering, konfiguration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764069"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Använda Windows Management Instrumentation (WMI) för att konfigurera och hantera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Windows WMI (Management Instrumentation) är ett skriptgränssnitt där du kan hämta, ändra och uppdatera inställningar.

Läs mer om WMI på [Microsoft Developer Network System Administration-biblioteket.](/windows/win32/wmisdk/wmi-start-page)

Microsoft Defender Antivirus har ett antal specifika WMI-klasser som kan användas för att utföra de flesta av funktionerna som Grupprincip och andra hanteringsverktyg. Många av klasserna kan jämföras med [Defender PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).

I [REFERENSbiblioteket för MSDN Windows Defender WMIv2-providern](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) visas tillgängliga WMI-klasser för Microsoft Defender Antivirus, och exempelskript.

Ändringar som görs med WMI påverkar lokala inställningar i slutpunkten där ändringarna distribueras eller görs. Det innebär att distributioner av principen med grupprinciper, Microsoft Endpoint Configuration Manager och Microsoft Intune kan skriva över ändringar som gjorts med WMI. 

Du kan [konfigurera vilka inställningar som kan åsidosättas lokalt med åsidosättningar av lokala policyer.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)