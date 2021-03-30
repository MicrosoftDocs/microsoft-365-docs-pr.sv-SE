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
ms.openlocfilehash: 08bb4c73cb9df429c4b07194f1c7615f44d745d8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408343"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bd4a8-104">Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="bd4a8-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd4a8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bd4a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd4a8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd4a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd4a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd4a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bd4a8-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bd4a8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd4a8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bd4a8-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="bd4a8-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint för Linux kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bd4a8-112">Så här installerar du Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="bd4a8-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="bd4a8-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="bd4a8-113">Prerequisites</span></span>

- <span data-ttu-id="bd4a8-114">Åtkomst till Microsoft Defender Säkerhetscenter-portalen</span><span class="sxs-lookup"><span data-stu-id="bd4a8-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="bd4a8-115">Linux-distribution med [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="bd4a8-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="bd4a8-116">Nybörjarupplevelse i Linux och BASH-skript</span><span class="sxs-lookup"><span data-stu-id="bd4a8-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="bd4a8-117">Administratörsbehörigheter på enheten (vid manuell distribution)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="bd4a8-118">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="bd4a8-118">Installation instructions</span></span>

<span data-ttu-id="bd4a8-119">Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="bd4a8-120">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="bd4a8-121">Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="bd4a8-122">Distribuera Microsoft Defender för Endpoint för Linux med någon av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="bd4a8-123">Kommandoradsverktyget:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-123">The command-line tool:</span></span>
    - [<span data-ttu-id="bd4a8-124">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="bd4a8-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="bd4a8-125">Hanteringsverktyg från tredje part:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="bd4a8-126">Distribuera med verktyget För konfigurationshantering av såsend</span><span class="sxs-lookup"><span data-stu-id="bd4a8-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="bd4a8-127">Distribuera med ett ansible-konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="bd4a8-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="bd4a8-128">Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt för Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="bd4a8-129">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="bd4a8-129">System requirements</span></span>

- <span data-ttu-id="bd4a8-130">Linux-serverdistributioner och -versioner som stöds:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="bd4a8-131">Red Hat Enterprise Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="bd4a8-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="bd4a8-132">CentOS 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="bd4a8-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="bd4a8-133">Ubuntu 16.04 LTS eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="bd4a8-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="bd4a8-134">Hane 9 eller senare</span><span class="sxs-lookup"><span data-stu-id="bd4a8-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="bd4a8-135">SUSE Linux Enterprise Server 12 eller senare</span><span class="sxs-lookup"><span data-stu-id="bd4a8-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="bd4a8-136">Oracle Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="bd4a8-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="bd4a8-137">Minsta kernel-version 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="bd4a8-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="bd4a8-138">`fanotify`Kernel-alternativet måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="bd4a8-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="bd4a8-139">Det går inte att köra Defender för Slutpunkt för Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="bd4a8-140">Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="bd4a8-141">Diskutrymme: 1 GB</span><span class="sxs-lookup"><span data-stu-id="bd4a8-141">Disk space: 1GB</span></span>
- <span data-ttu-id="bd4a8-142">/opt/microsoft/mdatp/sbin/wdavdaemon kräver körbar behörighet.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-142">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="bd4a8-143">Mer information finns i "Se till att daemon har körbar behörighet" i Felsöka [installationsproblem för Microsoft Defender ATP för Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-143">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="bd4a8-144">Minne: 1 GB</span><span class="sxs-lookup"><span data-stu-id="bd4a8-144">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="bd4a8-145">Kontrollera att du har ledigt diskutrymme i /varians.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-145">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="bd4a8-146">Lösningen tillhandahåller för närvarande realtidsskydd för följande filsystemtyper:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-146">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="bd4a8-147">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-147">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="bd4a8-148">Granskningsramverket `auditd` () måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-148">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="bd4a8-149">Systemhändelser som fångas av regler som lagts till `audit.logs` i läggs till i granskningsloggar och kan påverka värdgranskning och överordnad samling.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-149">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="bd4a8-150">Händelser som läggs till av Microsoft Defender för Endopoint för Linux kommer att märkas med `mdatp` tangenten.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-150">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="bd4a8-151">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="bd4a8-151">Network connections</span></span>

<span data-ttu-id="bd4a8-152">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="bd4a8-153">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="bd4a8-154">Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-154">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="bd4a8-155">**Kalkylblad med domänlista**</span><span class="sxs-lookup"><span data-stu-id="bd4a8-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="bd4a8-156">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="bd4a8-156">**Description**</span></span>|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="bd4a8-158">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="bd4a8-159">Ladda ned kalkylbladet här.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="bd4a8-160">En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-160">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="bd4a8-161">Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="bd4a8-161">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="bd4a8-162">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="bd4a8-162">Transparent proxy</span></span>
- <span data-ttu-id="bd4a8-163">Manuell statisk proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="bd4a8-163">Manual static proxy configuration</span></span>

<span data-ttu-id="bd4a8-164">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-164">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="bd4a8-165">För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-165">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="bd4a8-166">För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-166">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="bd4a8-167">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-167">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="bd4a8-168">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-168">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="bd4a8-169">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-169">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="bd4a8-170">Konfigurera ett undantag för SSL-kontroll och din proxyserver för att direkt överföra data från Defender för Endpoint för Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-170">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="bd4a8-171">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-171">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="bd4a8-172">Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Endpoint för Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-172">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bd4a8-173">Uppdatera Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="bd4a8-173">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="bd4a8-174">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="bd4a8-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="bd4a8-175">Om du vill uppdatera Microsoft Defender för Endpoint för Linux går du till [Distribuera uppdateringar för Microsoft Defender för Endpoint för Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-175">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bd4a8-176">Konfigurera Microsoft Defender för Slutpunkt för Linux</span><span class="sxs-lookup"><span data-stu-id="bd4a8-176">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="bd4a8-177">Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för Slutpunkt för Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="bd4a8-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="bd4a8-178">Resurser</span><span class="sxs-lookup"><span data-stu-id="bd4a8-178">Resources</span></span>

- <span data-ttu-id="bd4a8-179">Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bd4a8-179">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
