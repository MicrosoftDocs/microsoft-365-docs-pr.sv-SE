---
title: Använda PowerShell-cmdlets för att konfigurera och köra Microsoft Defender AV
description: I Windows 10 kan du använda PowerShell-cmdlets för att köra genomsökningar, uppdatera säkerhetsintelligens och ändra inställningar i Microsoft Defender Antivirus.
keywords: skanna, kommandorad, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765305"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="161a2-104">Använda PowerShell-cmdlets för att konfigurera och hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="161a2-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="161a2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="161a2-105">**Applies to:**</span></span>

- [<span data-ttu-id="161a2-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="161a2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="161a2-107">Du kan använda PowerShell till att utföra olika funktioner i Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="161a2-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="161a2-108">PowerShell liknar kommandotolken eller kommandoraden och är ett aktivitetsbaserat kommandoradsgränssnitt och skriptspråk som utformats särskilt för systemadministration.</span><span class="sxs-lookup"><span data-stu-id="161a2-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="161a2-109">Du kan läsa mer på [PowerShell-hubben på MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="161a2-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="161a2-110">En lista med cmdlet:ar och deras funktioner och tillgängliga parametrar finns i [avsnittet Om Defender-cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="161a2-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="161a2-111">PowerShell-cmdlets är mest användbara i Windows Server-miljöer som inte förlitar sig på ett grafiskt användargränssnitt (GUI) för att konfigurera programvara.</span><span class="sxs-lookup"><span data-stu-id="161a2-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="161a2-112">PowerShell-cmdlets bör inte användas som en ersättning för en fullständig infrastruktur för hantering av nätverksprinciper, till exempel ADMX-mallarna [Microsoft Endpoint Configuration Manager,](/configmgr) [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))eller Microsoft Defender Antivirus Group [Policy ADMX.](https://www.microsoft.com/download/101445)</span><span class="sxs-lookup"><span data-stu-id="161a2-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="161a2-113">Ändringar som görs med PowerShell påverkar lokala inställningar på slutpunkten där ändringarna distribueras eller görs.</span><span class="sxs-lookup"><span data-stu-id="161a2-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="161a2-114">Det innebär att distributioner av principen med Grupprincip, Microsoft Endpoint Configuration Manager eller Microsoft Intune kan skriva över ändringar som gjorts med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="161a2-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="161a2-115">Du kan [konfigurera vilka inställningar som kan åsidosättas lokalt med åsidosättningar av lokala policyer.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="161a2-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="161a2-116">PowerShell installeras vanligtvis under mappen `%SystemRoot%\system32\WindowsPowerShell` .</span><span class="sxs-lookup"><span data-stu-id="161a2-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="161a2-117">Använda Microsoft Defender Antivirus PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="161a2-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="161a2-118">Skriv powershell i **Windows-sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="161a2-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="161a2-119">Välj **Windows PowerShell** i resultatet för att öppna gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="161a2-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="161a2-120">Ange PowerShell-kommandot och eventuella parametrar.</span><span class="sxs-lookup"><span data-stu-id="161a2-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="161a2-121">Du kan behöva öppna PowerShell i administratörsläge.</span><span class="sxs-lookup"><span data-stu-id="161a2-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="161a2-122">Högerklicka på objektet på Start-menyn, klicka på **Kör som administratör och** klicka på **Ja** när behörigheter efterfrågas.</span><span class="sxs-lookup"><span data-stu-id="161a2-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="161a2-123">Om du vill öppna onlinehjälpen för någon av cmdletarna skriver du följande:</span><span class="sxs-lookup"><span data-stu-id="161a2-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="161a2-124">Utelämna parametern `-online` för att få lokalt cachelagrad hjälp.</span><span class="sxs-lookup"><span data-stu-id="161a2-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="161a2-125">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="161a2-125">Related topics</span></span>

- [<span data-ttu-id="161a2-126">Referensavsnitt om hanterings- och konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="161a2-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="161a2-127">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="161a2-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="161a2-128">Microsoft Defender Antivirus-cmdlets</span><span class="sxs-lookup"><span data-stu-id="161a2-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)