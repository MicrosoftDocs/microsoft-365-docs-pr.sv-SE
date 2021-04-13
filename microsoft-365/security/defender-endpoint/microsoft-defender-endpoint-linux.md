---
title: Microsoft Defender för Endpoint i Linux
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
ms.openlocfilehash: 0fea9d4dd46be2a77ea27728787a43b5273f92f5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687763"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="386ea-104">Microsoft Defender för Endpoint i Linux</span><span class="sxs-lookup"><span data-stu-id="386ea-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="386ea-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="386ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="386ea-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="386ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="386ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="386ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="386ea-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="386ea-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="386ea-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="386ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="386ea-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint på Linux.</span><span class="sxs-lookup"><span data-stu-id="386ea-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="386ea-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint på Linux kan sannolikt leda till prestandaproblem och oförutsägbara sidoeffekter.</span><span class="sxs-lookup"><span data-stu-id="386ea-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="386ea-112">Om skydd mot slutpunkter som inte är Microsoft är ett absolut krav i din miljö kan du fortfarande tryggt dra nytta av Defender för Endpoint för Linux EDR-funktioner när antivirusfunktionen har konfigurerats så att den körs i [passivt läge.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="386ea-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="386ea-113">Så här installerar du Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="386ea-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="386ea-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="386ea-114">Prerequisites</span></span>

- <span data-ttu-id="386ea-115">Åtkomst till Microsoft Defender Säkerhetscenter-portalen</span><span class="sxs-lookup"><span data-stu-id="386ea-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="386ea-116">Linux-distribution med [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="386ea-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="386ea-117">Nybörjarupplevelse i Linux och BASH-skript</span><span class="sxs-lookup"><span data-stu-id="386ea-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="386ea-118">Administratörsbehörigheter på enheten (vid manuell distribution)</span><span class="sxs-lookup"><span data-stu-id="386ea-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="386ea-119">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="386ea-119">Installation instructions</span></span>

<span data-ttu-id="386ea-120">Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint i Linux.</span><span class="sxs-lookup"><span data-stu-id="386ea-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="386ea-121">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="386ea-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="386ea-122">Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="386ea-123">Distribuera Microsoft Defender för Slutpunkt på Linux med någon av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="386ea-123">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="386ea-124">Kommandoradsverktyget:</span><span class="sxs-lookup"><span data-stu-id="386ea-124">The command-line tool:</span></span>
    - [<span data-ttu-id="386ea-125">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="386ea-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="386ea-126">Hanteringsverktyg från tredje part:</span><span class="sxs-lookup"><span data-stu-id="386ea-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="386ea-127">Distribuera med verktyget För konfigurationshantering av såsend</span><span class="sxs-lookup"><span data-stu-id="386ea-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="386ea-128">Distribuera med ett ansible-konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="386ea-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="386ea-129">Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt i Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="386ea-130">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="386ea-130">System requirements</span></span>

- <span data-ttu-id="386ea-131">Linux-serverdistributioner och -versioner som stöds:</span><span class="sxs-lookup"><span data-stu-id="386ea-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="386ea-132">Red Hat Enterprise Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="386ea-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="386ea-133">CentOS 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="386ea-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="386ea-134">Ubuntu 16.04 LTS eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="386ea-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="386ea-135">Hane 9 eller senare</span><span class="sxs-lookup"><span data-stu-id="386ea-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="386ea-136">SUSE Linux Enterprise Server 12 eller senare</span><span class="sxs-lookup"><span data-stu-id="386ea-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="386ea-137">Oracle Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="386ea-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="386ea-138">Minsta kernel-version 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="386ea-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="386ea-139">`fanotify`Kernel-alternativet måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="386ea-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="386ea-140">Det går inte att köra Defender för Slutpunkt för Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="386ea-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="386ea-141">Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.</span><span class="sxs-lookup"><span data-stu-id="386ea-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="386ea-142">Diskutrymme: 1 GB</span><span class="sxs-lookup"><span data-stu-id="386ea-142">Disk space: 1GB</span></span>
- <span data-ttu-id="386ea-143">/opt/microsoft/mdatp/sbin/wdavdaemon kräver körbar behörighet.</span><span class="sxs-lookup"><span data-stu-id="386ea-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="386ea-144">Mer information finns i "Se till att daemon har körbar behörighet" i Felsöka [installationsproblem för Microsoft Defender ATP för Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="386ea-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="386ea-145">Minne: 1 GB</span><span class="sxs-lookup"><span data-stu-id="386ea-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="386ea-146">Kontrollera att du har ledigt diskutrymme i /varians.</span><span class="sxs-lookup"><span data-stu-id="386ea-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="386ea-147">Lösningen tillhandahåller för närvarande realtidsskydd för följande filsystemtyper:</span><span class="sxs-lookup"><span data-stu-id="386ea-147">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="386ea-148">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="386ea-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="386ea-149">Granskningsramverket `auditd` () måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="386ea-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="386ea-150">Systemhändelser som fångas av regler som lagts till i läggs till `/etc/audit/rules.d/` `audit.log` i (s) och kan påverka värdgranskning och överordnad samling.</span><span class="sxs-lookup"><span data-stu-id="386ea-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="386ea-151">Händelser som läggs till av Microsoft Defender för Endpoint i Linux kommer att taggas med `mdatp` en nyckel.</span><span class="sxs-lookup"><span data-stu-id="386ea-151">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="386ea-152">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="386ea-152">Network connections</span></span>

<span data-ttu-id="386ea-153">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="386ea-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="386ea-154">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er.</span><span class="sxs-lookup"><span data-stu-id="386ea-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="386ea-155">Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="386ea-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="386ea-156">**Kalkylblad med domänlista**</span><span class="sxs-lookup"><span data-stu-id="386ea-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="386ea-157">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="386ea-157">**Description**</span></span>|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="386ea-159">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="386ea-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="386ea-160">Ladda ned kalkylbladet här.</span><span class="sxs-lookup"><span data-stu-id="386ea-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="386ea-161">En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="386ea-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="386ea-162">Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="386ea-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="386ea-163">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="386ea-163">Transparent proxy</span></span>
- <span data-ttu-id="386ea-164">Manuell statisk proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="386ea-164">Manual static proxy configuration</span></span>

<span data-ttu-id="386ea-165">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="386ea-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="386ea-166">För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="386ea-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="386ea-167">För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="386ea-168">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="386ea-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="386ea-169">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="386ea-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="386ea-170">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="386ea-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="386ea-171">Konfigurera ett undantag för SSL-kontrollen och proxyservern för att direkt överföra data från Defender för Slutpunkt i Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="386ea-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="386ea-172">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="386ea-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="386ea-173">Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Slutpunkt på Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="386ea-174">Uppdatera Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="386ea-174">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="386ea-175">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="386ea-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="386ea-176">Om du vill uppdatera Microsoft Defender för Slutpunkt på Linux går du till [Distribuera uppdateringar för Microsoft Defender för Slutpunkt i Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-176">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="386ea-177">Konfigurera Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="386ea-177">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="386ea-178">Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för slutpunkt i Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="386ea-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="386ea-179">Resurser</span><span class="sxs-lookup"><span data-stu-id="386ea-179">Resources</span></span>

- <span data-ttu-id="386ea-180">Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="386ea-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
