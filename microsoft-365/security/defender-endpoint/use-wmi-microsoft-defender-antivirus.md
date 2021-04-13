---
title: Konfigurera Microsoft Defender Antivirus med WMI
description: Lär dig hur du konfigurerar och hanterar Microsoft Defender Antivirus med hjälp av WMI-skript för att hämta, ändra och uppdatera inställningar i Microsoft Defender för Slutpunkt.
keywords: wmi, skript, instrument för Windows-hantering, konfiguration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691166"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Använda Windows Management Instrumentation (WMI) för att konfigurera och hantera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

WMI (Windows Management Instrumentation) är ett skriptgränssnitt där du kan hämta, ändra och uppdatera inställningar.

Läs mer om WMI på [Microsoft Developer Network System Administration-biblioteket.](/windows/win32/wmisdk/wmi-start-page)

Microsoft Defender Antivirus har ett antal specifika WMI-klasser som kan användas för att utföra de flesta av funktionerna som Grupprincip och andra hanteringsverktyg. Många av klasserna kan jämföras med [Defender PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).

Referensbiblioteket [för MSDN Windows Defender WMIv2-providern](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) innehåller tillgängliga WMI-klasser för Microsoft Defender Antivirus och innehåller exempelskript.

Ändringar som görs med WMI påverkar lokala inställningar i slutpunkten där ändringarna distribueras eller görs. Det innebär att distributioner av principen med Grupprincip, Microsoft Endpoint Configuration Manager eller Microsoft Intune kan skriva över ändringar som gjorts med WMI. 

Du kan [konfigurera vilka inställningar som kan åsidosättas lokalt med åsidosättningar av lokala policyer.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)