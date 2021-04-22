---
title: Felsöka installationsproblem för Microsoft Defender för Slutpunkt i Linux
ms.reviewer: ''
description: Felsöka installationsproblem för Microsoft Defender för Slutpunkt i Linux
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, linux, installation
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
ms.openlocfilehash: 12f648ce476f6e29cbb6b038cc42f2e744d77104
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933307"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="851c6-104">Felsöka installationsproblem för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="851c6-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="851c6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="851c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="851c6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="851c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="851c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="851c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="851c6-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="851c6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="851c6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="851c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="851c6-110">Kontrollera att installationen lyckades</span><span class="sxs-lookup"><span data-stu-id="851c6-110">Verify if installation succeeded</span></span>

<span data-ttu-id="851c6-111">Ett fel vid installationen kan eller kanske inte resultera i ett meningsfullt felmeddelande av pakethanteraren.</span><span class="sxs-lookup"><span data-stu-id="851c6-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="851c6-112">Kontrollera om installationen lyckades genom att hämta och kontrollera installationsloggarna med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="851c6-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="851c6-113">Ett utdata från föregående kommando med rätt datum och tid för installationen anger framgång.</span><span class="sxs-lookup"><span data-stu-id="851c6-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="851c6-114">Kontrollera även [klientkonfigurationen](linux-install-manually.md#client-configuration) för att verifiera produktens hälsa och identifiera TEXTFILEN EICAR.</span><span class="sxs-lookup"><span data-stu-id="851c6-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="851c6-115">Kontrollera att du har rätt paket</span><span class="sxs-lookup"><span data-stu-id="851c6-115">Make sure you have the correct package</span></span>

<span data-ttu-id="851c6-116">Tänk på att paketet som du installerar matchar värddistributionen och versionen.</span><span class="sxs-lookup"><span data-stu-id="851c6-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="851c6-117">paket</span><span class="sxs-lookup"><span data-stu-id="851c6-117">package</span></span>                       | <span data-ttu-id="851c6-118">distribution</span><span class="sxs-lookup"><span data-stu-id="851c6-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="851c6-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="851c6-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="851c6-120">Oracle, RHEL och CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="851c6-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="851c6-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="851c6-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="851c6-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="851c6-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="851c6-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="851c6-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="851c6-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="851c6-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="851c6-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="851c6-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="851c6-126">Oracle, RHEL och CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="851c6-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="851c6-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="851c6-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="851c6-128">Ubuntu och Ubuntu 16.04, 18.04 och 20.04</span><span class="sxs-lookup"><span data-stu-id="851c6-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="851c6-129">Vid [manuell distribution](linux-install-manually.md)kontrollerar du att rätt distro och version har valts.</span><span class="sxs-lookup"><span data-stu-id="851c6-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="851c6-130">Installationen misslyckades</span><span class="sxs-lookup"><span data-stu-id="851c6-130">Installation failed</span></span>

<span data-ttu-id="851c6-131">Kontrollera om mdatp-tjänsten körs:</span><span class="sxs-lookup"><span data-stu-id="851c6-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="851c6-132">Steg för felsökning om mdatp-tjänsten inte körs</span><span class="sxs-lookup"><span data-stu-id="851c6-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="851c6-133">Kontrollera om "mdatp"-användaren finns:</span><span class="sxs-lookup"><span data-stu-id="851c6-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="851c6-134">Om det inte finns några utdata kör du</span><span class="sxs-lookup"><span data-stu-id="851c6-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="851c6-135">Prova att aktivera och starta om tjänsten med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="851c6-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="851c6-136">Om mdatp.service inte hittas när du kör föregående kommando kör du:</span><span class="sxs-lookup"><span data-stu-id="851c6-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="851c6-137">where ```<systemd_path>``` is for Ubuntu and Distributions Distributions and for ```/lib/systemd/system``` ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle and SLES.</span><span class="sxs-lookup"><span data-stu-id="851c6-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="851c6-138">Kör sedan steg 2 igen.</span><span class="sxs-lookup"><span data-stu-id="851c6-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="851c6-139">Om stegen ovan inte fungerar kontrollerar du om SELinux är installerat och i tvingande läge.</span><span class="sxs-lookup"><span data-stu-id="851c6-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="851c6-140">I så fall kan du prova att ställa in det till tillåtande (helst) eller inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="851c6-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="851c6-141">Det kan göras genom att ange parametern `SELINUX` till "tillåtande" eller "inaktiverad" i `/etc/selinux/config` filen, följt av omstart.</span><span class="sxs-lookup"><span data-stu-id="851c6-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="851c6-142">Mer information finns på sidan med selinux.</span><span class="sxs-lookup"><span data-stu-id="851c6-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="851c6-143">Prova nu att starta om mdatp-tjänsten med steg 2.</span><span class="sxs-lookup"><span data-stu-id="851c6-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="851c6-144">Återställ konfigurationsändringen omedelbart, men av säkerhetsskäl när du har försökt och startat om den.</span><span class="sxs-lookup"><span data-stu-id="851c6-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="851c6-145">Om `/opt` katalog är en symbolisk länk skapar du ett bindfästen för `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="851c6-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="851c6-146">Kontrollera att daemon har körbar behörighet.</span><span class="sxs-lookup"><span data-stu-id="851c6-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="851c6-147">Om daemon inte har körbara behörigheter gör du det körbart med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="851c6-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="851c6-148">och försöker köra steg 2 igen.</span><span class="sxs-lookup"><span data-stu-id="851c6-148">and retry running step 2.</span></span>

7. <span data-ttu-id="851c6-149">Kontrollera att filsystemet som innehåller wdavdaemon inte har "noexec".</span><span class="sxs-lookup"><span data-stu-id="851c6-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="851c6-150">Om mdatp-tjänsten körs, men EICAR-textfilidentifiering inte fungerar</span><span class="sxs-lookup"><span data-stu-id="851c6-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="851c6-151">Kontrollera filsystemtypen med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="851c6-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="851c6-152">De filsystem som för närvarande stöds för aktivitet vid åtkomst anges [här.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="851c6-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="851c6-153">Filer utanför dessa filsystem genomsöks inte.</span><span class="sxs-lookup"><span data-stu-id="851c6-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="851c6-154">Kommandoradsverktyget "mdatp" fungerar inte</span><span class="sxs-lookup"><span data-stu-id="851c6-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="851c6-155">Om ett fel uppstår när `mdatp` kommandoradsverktyget körs `command not found` kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="851c6-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="851c6-156">och försök igen.</span><span class="sxs-lookup"><span data-stu-id="851c6-156">and try again.</span></span>

    <span data-ttu-id="851c6-157">Om inget av stegen ovan hjälper samlar du in diagnostikloggarna:</span><span class="sxs-lookup"><span data-stu-id="851c6-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="851c6-158">Sökväg till en zip-fil som innehåller loggarna visas som en utdatafil.</span><span class="sxs-lookup"><span data-stu-id="851c6-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="851c6-159">Kontakta vår kundsupport med de här loggarna.</span><span class="sxs-lookup"><span data-stu-id="851c6-159">Reach out to our customer support with these logs.</span></span>
