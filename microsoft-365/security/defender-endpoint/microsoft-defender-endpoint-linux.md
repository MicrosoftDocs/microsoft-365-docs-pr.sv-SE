---
title: Microsoft Defender för Endpoint för Linux
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender för Endpoint på Linux.
keywords: microsoft, defender, Microsoft Defender för Endpoint, linux, installation, distribuera, avinstallation, installationse, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
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
ms.openlocfilehash: 4175d3bedff86dc7f8cdafc1ff2366ca1c9cffc4
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893746"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2316b-104">Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="2316b-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2316b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2316b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2316b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2316b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2316b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2316b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2316b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2316b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2316b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2316b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2316b-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint på Linux.</span><span class="sxs-lookup"><span data-stu-id="2316b-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="2316b-111">Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint på Linux kan sannolikt leda till prestandaproblem och oförutsägbara sidoeffekter.</span><span class="sxs-lookup"><span data-stu-id="2316b-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="2316b-112">Om skydd mot slutpunkter som inte är Microsoft är ett absolut krav i din miljö kan du fortfarande tryggt dra nytta av Defender för Endpoint på Linux Identifiering och åtgärd på slutpunkt-funktioner när du har konfigurerat antivirusfunktionerna så att de körs i [passivt läge.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="2316b-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2316b-113">Så här installerar du Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="2316b-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2316b-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2316b-114">Prerequisites</span></span>

- <span data-ttu-id="2316b-115">Åtkomst till Microsoft Defender Säkerhetscenter portalen</span><span class="sxs-lookup"><span data-stu-id="2316b-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="2316b-116">Linux-distribution med [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="2316b-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="2316b-117">Nybörjarupplevelse i Linux och BASH-skript</span><span class="sxs-lookup"><span data-stu-id="2316b-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="2316b-118">Administratörsbehörigheter på enheten (vid manuell distribution)</span><span class="sxs-lookup"><span data-stu-id="2316b-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="2316b-119">Microsoft Defender för Slutpunkt på Linux-agenten är fristående [från OMS-agenten.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="2316b-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="2316b-120">Microsoft Defender för Endpoint använder sig av en egen oberoende telemetripipeline.</span><span class="sxs-lookup"><span data-stu-id="2316b-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="2316b-121">Microsoft Defender för Endpoint på Linux är ännu inte integrerat i Azure Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="2316b-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="2316b-122">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="2316b-122">Installation instructions</span></span>

<span data-ttu-id="2316b-123">Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint i Linux.</span><span class="sxs-lookup"><span data-stu-id="2316b-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="2316b-124">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="2316b-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="2316b-125">Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="2316b-126">Distribuera Microsoft Defender för Slutpunkt på Linux med någon av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="2316b-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="2316b-127">Kommandoradsverktyget:</span><span class="sxs-lookup"><span data-stu-id="2316b-127">The command-line tool:</span></span>
    - [<span data-ttu-id="2316b-128">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="2316b-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="2316b-129">Hanteringsverktyg från tredje part:</span><span class="sxs-lookup"><span data-stu-id="2316b-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="2316b-130">Distribuera med verktyget För konfigurationshantering av såsend</span><span class="sxs-lookup"><span data-stu-id="2316b-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="2316b-131">Distribuera med ett ansible-konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="2316b-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="2316b-132">Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt i Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="2316b-133">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="2316b-133">System requirements</span></span>

- <span data-ttu-id="2316b-134">Linux-serverdistributioner och x64-versioner (AMD64/EM64T) stöds:</span><span class="sxs-lookup"><span data-stu-id="2316b-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="2316b-135">Red Hat Enterprise Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="2316b-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="2316b-136">CentOS 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="2316b-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="2316b-137">Ubuntu 16.04 LTS eller senare LTS</span><span class="sxs-lookup"><span data-stu-id="2316b-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="2316b-138">Hane 9 eller senare</span><span class="sxs-lookup"><span data-stu-id="2316b-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="2316b-139">SUSE Linux Enterprise Server 12 eller senare</span><span class="sxs-lookup"><span data-stu-id="2316b-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="2316b-140">Oracle Linux 7.2 eller senare</span><span class="sxs-lookup"><span data-stu-id="2316b-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="2316b-141">Distributions- och versionsnummer som inte uttryckligen anges stöds inte (även om de härleds från de officiellt angivna fördelningarna).</span><span class="sxs-lookup"><span data-stu-id="2316b-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="2316b-142">Minsta kernel-version 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="2316b-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="2316b-143">`fanotify`Kernel-alternativet måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="2316b-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="2316b-144">Det går inte att köra Defender för slutpunkt på Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="2316b-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="2316b-145">Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.</span><span class="sxs-lookup"><span data-stu-id="2316b-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="2316b-146">Diskutrymme: 1 GB</span><span class="sxs-lookup"><span data-stu-id="2316b-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="2316b-147">/opt/microsoft/mdatp/sbin/wdavdaemon kräver körbar behörighet.</span><span class="sxs-lookup"><span data-stu-id="2316b-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="2316b-148">Mer information finns i "Se till att daemon har körbar behörighet" i Felsöka installationsproblem för [Microsoft Defender för slutpunkt i Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="2316b-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="2316b-149">Kärnor: minst 2, 4 som prioriteras</span><span class="sxs-lookup"><span data-stu-id="2316b-149">Cores: 2 minimum, 4 preferred</span></span>

- <span data-ttu-id="2316b-150">Minne: minst 1 GB, 4 som rekommenderas</span><span class="sxs-lookup"><span data-stu-id="2316b-150">Memory: 1 GB minimum, 4 preferred</span></span>

    > [!NOTE]
    > <span data-ttu-id="2316b-151">Kontrollera att du har ledigt diskutrymme i /varians.</span><span class="sxs-lookup"><span data-stu-id="2316b-151">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="2316b-152">Lösningen tillhandahåller för närvarande realtidsskydd för följande filsystemtyper:</span><span class="sxs-lookup"><span data-stu-id="2316b-152">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="2316b-153">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="2316b-153">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="2316b-154">Granskningsramverket `auditd` () måste vara aktiverat.</span><span class="sxs-lookup"><span data-stu-id="2316b-154">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="2316b-155">Systemhändelser som fångas av regler som lagts till i läggs till `/etc/audit/rules.d/` `audit.log` i (s) och kan påverka värdgranskning och överordnad samling.</span><span class="sxs-lookup"><span data-stu-id="2316b-155">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="2316b-156">Händelser som läggs till av Microsoft Defender för Endpoint i Linux kommer att taggas med `mdatp` en nyckel.</span><span class="sxs-lookup"><span data-stu-id="2316b-156">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="2316b-157">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="2316b-157">Network connections</span></span>

<span data-ttu-id="2316b-158">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="2316b-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="2316b-159">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er.</span><span class="sxs-lookup"><span data-stu-id="2316b-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="2316b-160">Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="2316b-160">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="2316b-161">Kalkylblad med domänlista</span><span class="sxs-lookup"><span data-stu-id="2316b-161">Spreadsheet of domains list</span></span> | <span data-ttu-id="2316b-162">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2316b-162">Description</span></span> |
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="2316b-164">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="2316b-164">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="2316b-165">Ladda ned kalkylbladet här.</span><span class="sxs-lookup"><span data-stu-id="2316b-165">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="2316b-166">En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2316b-166">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="2316b-167">Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="2316b-167">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="2316b-168">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="2316b-168">Transparent proxy</span></span>
- <span data-ttu-id="2316b-169">Manuell statisk proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="2316b-169">Manual static proxy configuration</span></span>

<span data-ttu-id="2316b-170">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="2316b-170">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="2316b-171">För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2316b-171">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="2316b-172">För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-172">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="2316b-173">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="2316b-173">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="2316b-174">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="2316b-174">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="2316b-175">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="2316b-175">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="2316b-176">Konfigurera ett undantag för SSL-kontrollen och proxyservern för att direkt överföra data från Defender för Slutpunkt i Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="2316b-176">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="2316b-177">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="2316b-177">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="2316b-178">Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Slutpunkt på Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-178">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2316b-179">Uppdatera Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="2316b-179">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="2316b-180">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="2316b-180">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="2316b-181">Om du vill uppdatera Microsoft Defender för Slutpunkt på Linux går du till [Distribuera uppdateringar för Microsoft Defender för Slutpunkt i Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-181">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2316b-182">Konfigurera Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="2316b-182">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="2316b-183">Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för slutpunkt i Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="2316b-183">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2316b-184">Resurser</span><span class="sxs-lookup"><span data-stu-id="2316b-184">Resources</span></span>

- <span data-ttu-id="2316b-185">Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="2316b-185">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
