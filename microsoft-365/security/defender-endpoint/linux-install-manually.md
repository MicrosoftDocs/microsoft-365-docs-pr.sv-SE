---
title: Distribuera Microsoft Defender för Slutpunkt i Linux manuellt
ms.reviewer: ''
description: Här beskrivs hur du distribuerar Microsoft Defender för slutpunkt i Linux manuellt från kommandoraden.
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8d7ac39baabca1496a5d2c22521874cfd60c6208
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105578"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="b8e60-104">Distribuera Microsoft Defender för Slutpunkt i Linux manuellt</span><span class="sxs-lookup"><span data-stu-id="b8e60-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8e60-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b8e60-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8e60-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8e60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8e60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8e60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b8e60-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b8e60-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b8e60-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b8e60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b8e60-110">I den här artikeln beskrivs hur du distribuerar Microsoft Defender för Endpoint på Linux manuellt.</span><span class="sxs-lookup"><span data-stu-id="b8e60-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="b8e60-111">För en lyckad distribution måste alla följande uppgifter slutföras:</span><span class="sxs-lookup"><span data-stu-id="b8e60-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="b8e60-112">Distribuera Microsoft Defender för Slutpunkt i Linux manuellt</span><span class="sxs-lookup"><span data-stu-id="b8e60-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="b8e60-113">Krav och systemkrav</span><span class="sxs-lookup"><span data-stu-id="b8e60-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="b8e60-114">Konfigurera linux-programvarans lagringsplats</span><span class="sxs-lookup"><span data-stu-id="b8e60-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="b8e60-115">RHEL och varianter (CentOS och Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="b8e60-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="b8e60-116">SLES och varianter</span><span class="sxs-lookup"><span data-stu-id="b8e60-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="b8e60-117">Ubuntu och Ubuntu systems</span><span class="sxs-lookup"><span data-stu-id="b8e60-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="b8e60-118">Programinstallation</span><span class="sxs-lookup"><span data-stu-id="b8e60-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="b8e60-119">Ladda ned onboarding-paketet</span><span class="sxs-lookup"><span data-stu-id="b8e60-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="b8e60-120">Klientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="b8e60-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="b8e60-121">Installationsskript</span><span class="sxs-lookup"><span data-stu-id="b8e60-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="b8e60-122">Logga installationsproblem</span><span class="sxs-lookup"><span data-stu-id="b8e60-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="b8e60-123">Uppgraderingar av operativsystem</span><span class="sxs-lookup"><span data-stu-id="b8e60-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="b8e60-124">Avinstallation</span><span class="sxs-lookup"><span data-stu-id="b8e60-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="b8e60-125">Krav och systemkrav</span><span class="sxs-lookup"><span data-stu-id="b8e60-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="b8e60-126">Innan du börjar kan du gå till [Microsoft Defender för Slutpunkt](microsoft-defender-endpoint-linux.md) på Linux för att få en beskrivning av krav och systemkrav för den aktuella programvaruversionen.</span><span class="sxs-lookup"><span data-stu-id="b8e60-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="b8e60-127">Konfigurera linux-programvarans lagringsplats</span><span class="sxs-lookup"><span data-stu-id="b8e60-127">Configure the Linux software repository</span></span>

<span data-ttu-id="b8e60-128">Defender för Slutpunkt i Linux kan distribueras från någon av följande kanaler (anges nedan som *[kanal]*): *insiders-fast,* *insiders-slow* eller *prod*. Var och en av dessa kanaler motsvarar en linux-programvarudatabas.</span><span class="sxs-lookup"><span data-stu-id="b8e60-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="b8e60-129">Anvisningar för hur du konfigurerar enheten för att använda någon av dessa lagringsningar finns nedan.</span><span class="sxs-lookup"><span data-stu-id="b8e60-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="b8e60-130">Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="b8e60-131">Enheter inom *insiders – snabbt* är de första som får uppdateringar och nya funktioner, följt senare av *insiders-slow* och slutligen *av prod*.</span><span class="sxs-lookup"><span data-stu-id="b8e60-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="b8e60-132">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget så att de använder *insiders snabbt* eller *insiders -långsamt.*</span><span class="sxs-lookup"><span data-stu-id="b8e60-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="b8e60-133">Om du byter kanal efter den första installationen måste produkten installeras om.</span><span class="sxs-lookup"><span data-stu-id="b8e60-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="b8e60-134">Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="b8e60-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="b8e60-135">RHEL och varianter (CentOS och Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="b8e60-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="b8e60-136">Installera `yum-utils` om det inte är installerat än:</span><span class="sxs-lookup"><span data-stu-id="b8e60-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="b8e60-137">Notera din distribution och version och identifiera den mest närmaste posten (efter huvudämne och sedan mindre) för den under `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="b8e60-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="b8e60-138">Till exempel är RHEL 7,9 närmare 7,4 än 8.</span><span class="sxs-lookup"><span data-stu-id="b8e60-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="b8e60-139">I kommandona nedan *ersätter du [distro]* *och [version]* med den information som du har identifierat:</span><span class="sxs-lookup"><span data-stu-id="b8e60-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8e60-140">Om du använder Oracle Linux *ersätter du [distro]* med "rhel".</span><span class="sxs-lookup"><span data-stu-id="b8e60-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="b8e60-141">Om du till exempel kör CentOS 7 och vill distribuera Defender för Endpoint på Linux från *prod-kanalen:*</span><span class="sxs-lookup"><span data-stu-id="b8e60-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="b8e60-142">Eller om du vill utforska nya funktioner på valda enheter kanske du vill distribuera MDE för Linux till *insiders-fast-kanal:*</span><span class="sxs-lookup"><span data-stu-id="b8e60-142">Or if you wish to explore new features on selected devices, you might want to deploy MDE for Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="b8e60-143">Installera den offentliga Microsoft GPG-nyckeln:</span><span class="sxs-lookup"><span data-stu-id="b8e60-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="b8e60-144">Ladda ned och gör att alla metadata för de för tillfället aktiverade lagringsplatsen för yum går att använda:</span><span class="sxs-lookup"><span data-stu-id="b8e60-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="b8e60-145">SLES och varianter</span><span class="sxs-lookup"><span data-stu-id="b8e60-145">SLES and variants</span></span>

- <span data-ttu-id="b8e60-146">Notera din distribution och version och identifiera den mest närmaste posten (efter huvudämne och sedan mindre) för den under `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="b8e60-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="b8e60-147">Ersätt [distro] och *[version]* med den information du har identifierat med följande kommandon: </span><span class="sxs-lookup"><span data-stu-id="b8e60-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="b8e60-148">Om du till exempel kör SLES 12 och vill distribuera MDE för Linux från *prod-kanalen:*</span><span class="sxs-lookup"><span data-stu-id="b8e60-148">For example, if you are running SLES 12 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="b8e60-149">Installera den offentliga Microsoft GPG-nyckeln:</span><span class="sxs-lookup"><span data-stu-id="b8e60-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="b8e60-150">Ubuntu och Ubuntu systems</span><span class="sxs-lookup"><span data-stu-id="b8e60-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="b8e60-151">Installera `curl` om det inte är installerat än:</span><span class="sxs-lookup"><span data-stu-id="b8e60-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="b8e60-152">Installera `libplist-utils` om det inte är installerat än:</span><span class="sxs-lookup"><span data-stu-id="b8e60-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="b8e60-153">Notera din distribution och version och identifiera den mest närmaste posten (efter huvudämne och sedan mindre) för den under `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="b8e60-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="b8e60-154">I kommandot nedan ersätter *du [distro]* och *[version]* med den information som du har identifierat:</span><span class="sxs-lookup"><span data-stu-id="b8e60-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="b8e60-155">Till exempel om du kör Ubuntu 18.04 och vill distribuera MDE för Linux från *prod-kanalen:*</span><span class="sxs-lookup"><span data-stu-id="b8e60-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="b8e60-156">Installera lagringsplatsens konfiguration:</span><span class="sxs-lookup"><span data-stu-id="b8e60-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="b8e60-157">Om du till exempel har *valt prod-kanal:*</span><span class="sxs-lookup"><span data-stu-id="b8e60-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="b8e60-158">Installera paketet `gpg` om det inte redan är installerat:</span><span class="sxs-lookup"><span data-stu-id="b8e60-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="b8e60-159">Installera `gpg` om inte är `gnupg` tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="b8e60-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="b8e60-160">Installera den offentliga Microsoft GPG-nyckeln:</span><span class="sxs-lookup"><span data-stu-id="b8e60-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="b8e60-161">Installera https-drivrutinen om den inte redan finns:</span><span class="sxs-lookup"><span data-stu-id="b8e60-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="b8e60-162">Uppdatera metadata för lagringsplatsen:</span><span class="sxs-lookup"><span data-stu-id="b8e60-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="b8e60-163">Programinstallation</span><span class="sxs-lookup"><span data-stu-id="b8e60-163">Application installation</span></span>

- <span data-ttu-id="b8e60-164">RHEL och varianter (CentOS och Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="b8e60-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="b8e60-165">Om du har flera Microsoft-lagringslager konfigurerade på enheten kan du vara specifik för vilken lagringsplats paketet ska installeras från.</span><span class="sxs-lookup"><span data-stu-id="b8e60-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b8e60-166">I följande exempel visas hur du installerar paketet från kanalen `production` om du även har `insiders-fast` databasens kanal konfigurerad på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="b8e60-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b8e60-167">Det här kan inträffa om du använder flera Microsoft-produkter på din enhet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="b8e60-168">Beroende på distributionen och versionen av servern kan lagringsplatsaliaset vara ett annat än det som visas i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="b8e60-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="b8e60-169">SLES och varianter:</span><span class="sxs-lookup"><span data-stu-id="b8e60-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="b8e60-170">Om du har flera Microsoft-lagringslager konfigurerade på enheten kan du vara specifik för vilken lagringsplats paketet ska installeras från.</span><span class="sxs-lookup"><span data-stu-id="b8e60-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b8e60-171">I följande exempel visas hur du installerar paketet från kanalen `production` om du även har `insiders-fast` databasens kanal konfigurerad på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="b8e60-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b8e60-172">Det här kan inträffa om du använder flera Microsoft-produkter på din enhet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="b8e60-173">Ubuntu och Ubuntu system:</span><span class="sxs-lookup"><span data-stu-id="b8e60-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="b8e60-174">Om du har flera Microsoft-lagringslager konfigurerade på enheten kan du vara specifik för vilken lagringsplats paketet ska installeras från.</span><span class="sxs-lookup"><span data-stu-id="b8e60-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b8e60-175">I följande exempel visas hur du installerar paketet från kanalen `production` om du även har `insiders-fast` databasens kanal konfigurerad på den här enheten.</span><span class="sxs-lookup"><span data-stu-id="b8e60-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b8e60-176">Det här kan inträffa om du använder flera Microsoft-produkter på din enhet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="b8e60-177">Ladda ned onboarding-paketet</span><span class="sxs-lookup"><span data-stu-id="b8e60-177">Download the onboarding package</span></span>

<span data-ttu-id="b8e60-178">Ladda ned introduktionspaketet från Microsoft Defender Säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="b8e60-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="b8e60-179">I Microsoft Defender Säkerhetscenter går du till Inställningar > **på Enhetshantering > Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="b8e60-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="b8e60-180">I den första listrutan väljer du **Linux Server** som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="b8e60-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="b8e60-181">I den andra listrutan väljer du Lokalt skript (för upp till **10 enheter)** som distributionsmetod.</span><span class="sxs-lookup"><span data-stu-id="b8e60-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="b8e60-182">Välj **Hämta introduktionspaket**.</span><span class="sxs-lookup"><span data-stu-id="b8e60-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="b8e60-183">Spara filen som WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="b8e60-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender Säkerhetscenter skärmbild](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="b8e60-185">Kontrollera att filen finns i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="b8e60-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="b8e60-186">Extrahera innehållet i arkivet:</span><span class="sxs-lookup"><span data-stu-id="b8e60-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="b8e60-187">Klientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="b8e60-187">Client configuration</span></span>

1. <span data-ttu-id="b8e60-188">Kopiera MicrosoftDefenderATPOnboardingLinuxServer.py till målenheten.</span><span class="sxs-lookup"><span data-stu-id="b8e60-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="b8e60-189">Till en början är klientenheten inte kopplad till en organisation.</span><span class="sxs-lookup"><span data-stu-id="b8e60-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="b8e60-190">Observera att *orgId-attributet* är tomt:</span><span class="sxs-lookup"><span data-stu-id="b8e60-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="b8e60-191">Kör MicrosoftDefenderATPOnboardingLinuxServer.py och observera att du måste ha installerat på enheten för att kunna `python` köra det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="b8e60-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="b8e60-192">Kontrollera att enheten nu är kopplad till din organisation och rapporterar en giltig organisationsidentifierare:</span><span class="sxs-lookup"><span data-stu-id="b8e60-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="b8e60-193">Några minuter efter att du slutfört installationen kan du se statusen genom att köra följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b8e60-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="b8e60-194">Returvärdet för `1` anger att produkten fungerar som förväntat:</span><span class="sxs-lookup"><span data-stu-id="b8e60-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b8e60-195">När produkten startas för första gången laddas de senaste definitionerna för program mot skadlig programvara ned.</span><span class="sxs-lookup"><span data-stu-id="b8e60-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="b8e60-196">Beroende på din Internetanslutning kan det ta upp till några minuter.</span><span class="sxs-lookup"><span data-stu-id="b8e60-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="b8e60-197">Under den här tiden returnerar kommandot ovan värdet `false` .</span><span class="sxs-lookup"><span data-stu-id="b8e60-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="b8e60-198">Du kan kontrollera statusen för definitionsuppdateringen med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b8e60-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="b8e60-199">Observera att du kan också behöva konfigurera en proxy när du har slutfört den första installationen.</span><span class="sxs-lookup"><span data-stu-id="b8e60-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="b8e60-200">Se [Konfigurera Defender för slutpunkt på Linux för statisk proxyidentifiering: Konfiguration efter installation.](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)</span><span class="sxs-lookup"><span data-stu-id="b8e60-200">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="b8e60-201">Kör ett identifieringstest för att verifiera att enheten är korrekt onboarded och rapporterar till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="b8e60-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="b8e60-202">Utför följande steg på den nyligen inbyggda enheten:</span><span class="sxs-lookup"><span data-stu-id="b8e60-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="b8e60-203">Se till att realtidsskyddet är aktiverat (som visas på grund av att följande kommando `1` körs):</span><span class="sxs-lookup"><span data-stu-id="b8e60-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="b8e60-204">Öppna ett terminalfönster.</span><span class="sxs-lookup"><span data-stu-id="b8e60-204">Open a Terminal window.</span></span> <span data-ttu-id="b8e60-205">Kopiera och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b8e60-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="b8e60-206">Filen skulle ha satts i karantän av Defender för Endpoint på Linux.</span><span class="sxs-lookup"><span data-stu-id="b8e60-206">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="b8e60-207">Använd följande kommando för att lista alla identifierade hot:</span><span class="sxs-lookup"><span data-stu-id="b8e60-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="b8e60-208">Upplev Linux identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt) med simulerade attacker</span><span class="sxs-lookup"><span data-stu-id="b8e60-208">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="b8e60-209">För att testa funktionerna i Identifiering och åtgärd på slutpunkt för Linux följer du stegen nedan för att simulera en identifiering på din Linux-server och undersöka ärendet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-209">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="b8e60-210">Kontrollera att den onboarded Linux-servern visas i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="b8e60-210">Verify that the onboarded Linux server appears in Microsoft Defender Security Center.</span></span> <span data-ttu-id="b8e60-211">Om det här är den första onboarding av datorn kan det ta upp till 20 minuter tills den visas.</span><span class="sxs-lookup"><span data-stu-id="b8e60-211">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="b8e60-212">Ladda ned och extrahera [skriptfilen](https://aka.ms/LinuxDIY) till en onboarded Linux-server och kör följande kommando: `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="b8e60-212">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="b8e60-213">Efter några minuter ska en identifiering av den upphöjas Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="b8e60-213">After a few minutes, a detection should be raised in Microsoft Defender Security Center.</span></span>

4.  <span data-ttu-id="b8e60-214">Titta på varningsinformationen, datortidslinjen och utför dina vanliga undersökningssteg.</span><span class="sxs-lookup"><span data-stu-id="b8e60-214">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="b8e60-215">Installationsskript</span><span class="sxs-lookup"><span data-stu-id="b8e60-215">Installer script</span></span>

<span data-ttu-id="b8e60-216">Alternativt kan du använda ett automatiserat installationsprogram [bash-skript](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) som tillhandahålls i vår [offentliga GitHub databas.](https://github.com/microsoft/mdatp-xplat/)</span><span class="sxs-lookup"><span data-stu-id="b8e60-216">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="b8e60-217">Skriptet identifierar distributionen och versionen och uppsättningar av enheten för att hämta det senaste paketet och installera det.</span><span class="sxs-lookup"><span data-stu-id="b8e60-217">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="b8e60-218">Du kan också registrera dig för ett skript.</span><span class="sxs-lookup"><span data-stu-id="b8e60-218">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="b8e60-219">Läs mer [här.](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)</span><span class="sxs-lookup"><span data-stu-id="b8e60-219">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="b8e60-220">Logga installationsproblem</span><span class="sxs-lookup"><span data-stu-id="b8e60-220">Log installation issues</span></span>

<span data-ttu-id="b8e60-221">Mer [information om hur](linux-resources.md#log-installation-issues) du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Problem med logginstallationen.</span><span class="sxs-lookup"><span data-stu-id="b8e60-221">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="b8e60-222">Uppgraderingar av operativsystem</span><span class="sxs-lookup"><span data-stu-id="b8e60-222">Operating system upgrades</span></span>

<span data-ttu-id="b8e60-223">När du uppgraderar ditt operativsystem till en ny huvudversion måste du först avinstallera Defender för Slutpunkt i Linux, installera uppgraderingen och slutligen konfigurera om Defender för Slutpunkt på Linux på din enhet.</span><span class="sxs-lookup"><span data-stu-id="b8e60-223">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="b8e60-224">Migrera från Insiders-Fast till produktionskanalen</span><span class="sxs-lookup"><span data-stu-id="b8e60-224">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="b8e60-225">Avinstallera "Insiders-Fast-kanalen" versionen av MDE för Linux.</span><span class="sxs-lookup"><span data-stu-id="b8e60-225">Uninstall the “Insiders-Fast channel” version of MDE for Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="b8e60-226">Inaktivera MDE för Linux Insiders-Fast platsen  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="b8e60-226">Disable the MDE for Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8e60-227">Utdata ska visa "packages-microsoft-com-fast-prod".</span><span class="sxs-lookup"><span data-stu-id="b8e60-227">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="b8e60-228">Distribuera om MDE för Linux med "Produktionskanal".</span><span class="sxs-lookup"><span data-stu-id="b8e60-228">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="b8e60-229">Avinstallation</span><span class="sxs-lookup"><span data-stu-id="b8e60-229">Uninstallation</span></span>

<span data-ttu-id="b8e60-230">Se [Avinstallera](linux-resources.md#uninstall) för mer information om hur du tar bort Defender för Slutpunkt på Linux från klientenheter.</span><span class="sxs-lookup"><span data-stu-id="b8e60-230">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8e60-231">Se även</span><span class="sxs-lookup"><span data-stu-id="b8e60-231">See also</span></span>
- [<span data-ttu-id="b8e60-232">Undersöka hälsoproblem i agenten</span><span class="sxs-lookup"><span data-stu-id="b8e60-232">Investigate agent health issues</span></span>](health-status.md)
