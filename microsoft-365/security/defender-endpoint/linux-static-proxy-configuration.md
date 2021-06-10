---
title: Microsoft Defender för slutpunkt på statisk proxyidentifiering i Linux
ms.reviewer: ''
description: Här beskrivs hur du konfigurerar Microsoft Defender för slutpunkt på Linux för statisk proxyidentifiering.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, installation, proxy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c5dc14c71c344bf508cda8d39f892d740781ac87
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933127"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="fd62f-104">Konfigurera Microsoft Defender för slutpunkt på Linux för statisk proxyidentifiering</span><span class="sxs-lookup"><span data-stu-id="fd62f-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fd62f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fd62f-105">**Applies to:**</span></span>
- [<span data-ttu-id="fd62f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fd62f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fd62f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd62f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fd62f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fd62f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fd62f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fd62f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fd62f-110">Microsoft Defender för Endpoint kan identifiera en proxyserver med ```HTTPS_PROXY``` miljövariabeln.</span><span class="sxs-lookup"><span data-stu-id="fd62f-110">Microsoft Defender for Endpoint can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="fd62f-111">Den här inställningen måste **konfigureras både** vid installationen och efter att produkten har installerats.</span><span class="sxs-lookup"><span data-stu-id="fd62f-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="fd62f-112">Konfiguration av installationstid</span><span class="sxs-lookup"><span data-stu-id="fd62f-112">Installation time configuration</span></span>

<span data-ttu-id="fd62f-113">Under installationen måste ```HTTPS_PROXY``` miljövariabeln skickas till pakethanteraren.</span><span class="sxs-lookup"><span data-stu-id="fd62f-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="fd62f-114">Pakethanteraren kan läsa den här variabeln på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="fd62f-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="fd62f-115">Variabeln ```HTTPS_PROXY``` definieras ```/etc/environment``` i med följande rad:</span><span class="sxs-lookup"><span data-stu-id="fd62f-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="fd62f-116">Variabeln `HTTPS_PROXY` definieras i den globala konfigurationen av package manager.</span><span class="sxs-lookup"><span data-stu-id="fd62f-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="fd62f-117">I Ubuntu 18.04 kan du till exempel lägga till följande rad för `/etc/apt/apt.conf.d/proxy.conf` att:</span><span class="sxs-lookup"><span data-stu-id="fd62f-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="fd62f-118">Observera att två metoder ovan kan definiera proxyn som ska användas för andra program i systemet.</span><span class="sxs-lookup"><span data-stu-id="fd62f-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="fd62f-119">Använd den här metoden med försiktighet eller bara om det är tänkt att vara en global konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd62f-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="fd62f-120">Variabeln `HTTPS_PROXY` förberedas för installations- eller avinstallationskommandona.</span><span class="sxs-lookup"><span data-stu-id="fd62f-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="fd62f-121">Med APT-pakethanteraren ska variabeln till exempel förberedas så här när du installerar Microsoft Defender för slutpunkt:</span><span class="sxs-lookup"><span data-stu-id="fd62f-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="fd62f-122">Lägg inte till sudo mellan miljövariabeldefinitionen och snabel, annars sprids inte variabeln.</span><span class="sxs-lookup"><span data-stu-id="fd62f-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="fd62f-123">`HTTPS_PROXY`Miljövariabeln kan på liknande sätt definieras vid avinstallation.</span><span class="sxs-lookup"><span data-stu-id="fd62f-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="fd62f-124">Observera att installationen och avinstallationen inte nödvändigtvis misslyckas om en proxy krävs men inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="fd62f-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="fd62f-125">Telemetri skickas dock inte och åtgärden kan ta mycket längre tid på grund av timeout för nätverk.</span><span class="sxs-lookup"><span data-stu-id="fd62f-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="fd62f-126">Efter installation</span><span class="sxs-lookup"><span data-stu-id="fd62f-126">Post installation configuration</span></span>
  
<span data-ttu-id="fd62f-127">Efter installationen måste `HTTPS_PROXY` miljövariabeln definieras i Defender för slutpunktstjänstfilen.</span><span class="sxs-lookup"><span data-stu-id="fd62f-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="fd62f-128">Det gör du genom att öppna `/lib/systemd/system/mdatp.service` den i en textredigerare medan du kör rotanvändaren.</span><span class="sxs-lookup"><span data-stu-id="fd62f-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="fd62f-129">Du kan sedan sprida variabeln till tjänsten på ett av två sätt:</span><span class="sxs-lookup"><span data-stu-id="fd62f-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="fd62f-130">Ta bort från raden och `#Environment="HTTPS_PROXY=http://address:port"` ange din statiska proxyadress.</span><span class="sxs-lookup"><span data-stu-id="fd62f-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="fd62f-131">Lägg till en linje `EnvironmentFile=/path/to/env/file` .</span><span class="sxs-lookup"><span data-stu-id="fd62f-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="fd62f-132">Den här sökvägen kan `/etc/environment` peka på eller en anpassad fil, som alla måste lägga till följande rad:</span><span class="sxs-lookup"><span data-stu-id="fd62f-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="fd62f-133">Spara och stäng `mdatp.service` filen när du har redigerat den.</span><span class="sxs-lookup"><span data-stu-id="fd62f-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="fd62f-134">Starta om tjänsten så att ändringarna kan tillämpas.</span><span class="sxs-lookup"><span data-stu-id="fd62f-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="fd62f-135">I Ubuntu innefattar detta två kommandon:</span><span class="sxs-lookup"><span data-stu-id="fd62f-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
