---
title: Använda PowerShell-cmdlets för att konfigurera och köra Microsoft Defender AV
description: I Windows 10 kan du använda PowerShell-cmdlets för att köra genomsökningar, uppdatera säkerhetsintelligens och ändra inställningar i Microsoft Defender Antivirus.
keywords: skanna, kommandorad, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 0fd1e6b2eec1be722af58e0753e158c050b56c6b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749884"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Använda PowerShell-cmdlets för att konfigurera och hantera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda PowerShell till att utföra olika funktioner i Windows Defender. PowerShell liknar kommandotolken eller kommandoraden och är ett aktivitetsbaserat kommandoradsgränssnitt och skriptspråk som utformats särskilt för systemadministration. Du kan läsa mer på [PowerShell-hubben på MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))

En lista med cmdlet:ar och deras funktioner och tillgängliga parametrar finns i [avsnittet Om Defender-cmdlets.](/powershell/module/defender)

PowerShell-cmdlets är mest användbara i Windows Server-miljöer som inte förlitar sig på ett grafiskt användargränssnitt (GUI) för att konfigurera programvara.

> [!NOTE]
> PowerShell-cmdlets bör inte användas som en ersättning för en fullständig infrastruktur för hantering av nätverksprinciper, till exempel ADMX-mallarna [Microsoft Endpoint Configuration Manager,](/configmgr) [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))eller Microsoft Defender Antivirus Group [Policy ADMX.](https://www.microsoft.com/download/101445)

Ändringar som görs med PowerShell påverkar lokala inställningar på slutpunkten där ändringarna distribueras eller görs. Det innebär att distributioner av principen med Grupprincip, Microsoft Endpoint Configuration Manager eller Microsoft Intune kan skriva över ändringar som gjorts med PowerShell.

Du kan [konfigurera vilka inställningar som kan åsidosättas lokalt med åsidosättningar av lokala policyer.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell installeras vanligtvis under mappen `%SystemRoot%\system32\WindowsPowerShell` .

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Använda Microsoft Defender Antivirus PowerShell-cmdlets

1. Skriv powershell i **Windows-sökfältet.**
2. Välj **Windows PowerShell** i resultatet för att öppna gränssnittet.
3. Ange PowerShell-kommandot och eventuella parametrar.

> [!NOTE]
> Du kan behöva öppna PowerShell i administratörsläge. Högerklicka på objektet på Start-menyn, klicka på **Kör som administratör och** klicka på **Ja** när behörigheter efterfrågas.

Om du vill öppna onlinehjälpen för någon av cmdletarna skriver du följande:

```PowerShell
Get-Help <cmdlet> -Online
```

Utelämna parametern `-online` för att få lokalt cachelagrad hjälp.

## <a name="related-topics"></a>Relaterade ämnen

- [Referensavsnitt om hanterings- och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus-cmdlets](/powershell/module/defender)