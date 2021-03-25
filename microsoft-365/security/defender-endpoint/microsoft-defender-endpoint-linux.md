---
title: Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, installation, distribuera, avinstallation, enkel, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 84d85b723d4dcbdfc07a074c40241242c57bc390
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185593"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="5e5ec-104">Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="5e5ec-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5e5ec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5e5ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="5e5ec-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5e5ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5e5ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e5ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5e5ec-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5e5ec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5e5ec-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5e5ec-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="5e5ec-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint för Linux kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="5e5ec-112">Så här installerar du Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="5e5ec-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5e5ec-113">Krav</span><span class="sxs-lookup"><span data-stu-id="5e5ec-113">Prerequisites</span></span>

- <span data-ttu-id="5e5ec-114">Åtkomst till Microsoft Defender Säkerhetscenter-portalen</span><span class="sxs-lookup"><span data-stu-id="5e5ec-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="5e5ec-115">Linux-distribution med [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="5e5ec-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="5e5ec-116">Nybörjarupplevelse i Linux och BASH-skript</span><span class="sxs-lookup"><span data-stu-id="5e5ec-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="5e5ec-117">Administratörsbehörigheter på enheten (vid manuell distribution)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="5e5ec-118">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="5e5ec-118">Installation instructions</span></span>

<span data-ttu-id="5e5ec-119">Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="5e5ec-120">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="5e5ec-121">Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="5e5ec-122">Distribuera Microsoft Defender för Endpoint för Linux med någon av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="5e5ec-123">Kommandoradsverktyget:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-123">The command-line tool:</span></span>
    - [<span data-ttu-id="5e5ec-124">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="5e5ec-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="5e5ec-125">Hanteringsverktyg från tredje part:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="5e5ec-126">Distribuera med verktyget För konfigurationshantering av såsend</span><span class="sxs-lookup"><span data-stu-id="5e5ec-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="5e5ec-127">Distribuera med ett ansible-konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="5e5ec-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="5e5ec-128">Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt för Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="5e5ec-129">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="5e5ec-129">System requirements</span></span>

- <span data-ttu-id="5e5ec-130">Linux-serverdistributioner och -versioner som stöds:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="5e5ec-131">Red Hat Enterprise Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="5e5ec-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="5e5ec-132">CentOS 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="5e5ec-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="5e5ec-133">Ubuntu 16.04 LTS eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="5e5ec-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="5e5ec-134">Hane 9 eller senare</span><span class="sxs-lookup"><span data-stu-id="5e5ec-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="5e5ec-135">SUSE Linux Enterprise Server 12 eller senare</span><span class="sxs-lookup"><span data-stu-id="5e5ec-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="5e5ec-136">Oracle Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="5e5ec-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="5e5ec-137">Minsta kernel-version 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="5e5ec-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="5e5ec-138">`fanotify`Kernel-alternativet måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="5e5ec-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="5e5ec-139">Det går inte att köra Defender för Slutpunkt för Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="5e5ec-140">Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="5e5ec-141">Diskutrymme: 1 GB</span><span class="sxs-lookup"><span data-stu-id="5e5ec-141">Disk space: 1GB</span></span>
- <span data-ttu-id="5e5ec-142">Lösningen tillhandahåller för närvarande realtidsskydd för följande filsystemtyper:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-142">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="5e5ec-143">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="5e5ec-144">Granskningsramverket `auditd` () måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="5e5ec-145">Systemhändelser som fångas av regler som lagts till `audit.logs` i läggs till i granskningsloggar och kan påverka värdgranskning och överordnad samling.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="5e5ec-146">Händelser som läggs till av Microsoft Defender för Endopoint för Linux kommer att märkas med `mdatp` tangenten.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="5e5ec-147">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="5e5ec-147">Network connections</span></span>

<span data-ttu-id="5e5ec-148">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="5e5ec-149">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="5e5ec-150">Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="5e5ec-151">**Kalkylblad med domänlista**</span><span class="sxs-lookup"><span data-stu-id="5e5ec-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="5e5ec-152">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="5e5ec-152">**Description**</span></span>|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="5e5ec-154">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="5e5ec-155">Ladda ned kalkylbladet här.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="5e5ec-156">En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="5e5ec-157">Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="5e5ec-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="5e5ec-158">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="5e5ec-158">Transparent proxy</span></span>
- <span data-ttu-id="5e5ec-159">Manuell statisk proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="5e5ec-159">Manual static proxy configuration</span></span>

<span data-ttu-id="5e5ec-160">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="5e5ec-161">För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="5e5ec-162">För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="5e5ec-163">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="5e5ec-164">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="5e5ec-165">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="5e5ec-166">Konfigurera ett undantag för SSL-kontroll och din proxyserver för att direkt överföra data från Defender för Endpoint för Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="5e5ec-167">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="5e5ec-168">Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Endpoint för Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="5e5ec-169">Uppdatera Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="5e5ec-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="5e5ec-170">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="5e5ec-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="5e5ec-171">Om du vill uppdatera Microsoft Defender för Endpoint för Linux går du till [Distribuera uppdateringar för Microsoft Defender för Endpoint för Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="5e5ec-172">Konfigurera Microsoft Defender för Slutpunkt för Linux</span><span class="sxs-lookup"><span data-stu-id="5e5ec-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="5e5ec-173">Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för Slutpunkt för Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="5e5ec-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="5e5ec-174">Resurser</span><span class="sxs-lookup"><span data-stu-id="5e5ec-174">Resources</span></span>

- <span data-ttu-id="5e5ec-175">Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="5e5ec-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
