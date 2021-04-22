---
title: Schemalägga en uppdatering av Microsoft Defender för slutpunkt (Linux)
description: Lär dig hur du schemalägger en uppdatering av Microsoft Defender för slutpunkt (Linux) för att bättre skydda organisationens tillgångar.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, genomsökningar, antivirus, microsoft defender för slutpunkt (linux)
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 22ff42cb399b3d07c0ebd8ec4f947352eb6f44aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934771"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="6fd51-104">Schemalägga en uppdatering av Microsoft Defender för Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="6fd51-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="6fd51-105">Information om hur du kör en uppdatering på Microsoft Defender för Slutpunkt på Linux finns i [Distribuera uppdateringar för Microsoft Defender för slutpunkt i Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)</span><span class="sxs-lookup"><span data-stu-id="6fd51-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="6fd51-106">Linux (och Unix) har verktyget **t.ex.tab** (liknar Schemaläggaren) för att kunna köra schemalagda aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="6fd51-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="6fd51-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="6fd51-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="6fd51-108">Om du vill visa en lista över alla tidszoner kör du följande kommando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="6fd51-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="6fd51-109">Exempel för tidszoner:</span><span class="sxs-lookup"><span data-stu-id="6fd51-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="6fd51-110">Så här ställer du in Job</span><span class="sxs-lookup"><span data-stu-id="6fd51-110">To set the Cron job</span></span>
<span data-ttu-id="6fd51-111">Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="6fd51-111">Use the following commands:</span></span>

<span data-ttu-id="6fd51-112">**Om du vill säkerhetskopiera poster**</span><span class="sxs-lookup"><span data-stu-id="6fd51-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="6fd51-113">Där 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="6fd51-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="6fd51-114">Gör detta innan du redigerar eller tar bort.</span><span class="sxs-lookup"><span data-stu-id="6fd51-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="6fd51-115">Så här redigerar du fliken och lägger till ett nytt jobb som rotanvändare:</span><span class="sxs-lookup"><span data-stu-id="6fd51-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="6fd51-116">Standardredigeraren är VIM.</span><span class="sxs-lookup"><span data-stu-id="6fd51-116">The default editor is VIM.</span></span>

<span data-ttu-id="6fd51-117">Du kan se:</span><span class="sxs-lookup"><span data-stu-id="6fd51-117">You might see:</span></span>

<span data-ttu-id="6fd51-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="6fd51-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="6fd51-119">Och</span><span class="sxs-lookup"><span data-stu-id="6fd51-119">And</span></span>

<span data-ttu-id="6fd51-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="6fd51-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="6fd51-121">Se [Schemalägga genomsökningar med Microsoft Defender för Endpoint (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="6fd51-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="6fd51-122">Tryck på Infoga</span><span class="sxs-lookup"><span data-stu-id="6fd51-122">Press “Insert”</span></span>

<span data-ttu-id="6fd51-123">Lägg till följande poster:</span><span class="sxs-lookup"><span data-stu-id="6fd51-123">Add the following entries:</span></span>

<span data-ttu-id="6fd51-124">CRON_TZ=Amerika/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="6fd51-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="6fd51-125">! RHEL och varianter (CentOS och Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="6fd51-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="6fd51-126">! SLES och varianter</span><span class="sxs-lookup"><span data-stu-id="6fd51-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="6fd51-127">! Ubuntu och Ubuntu systems</span><span class="sxs-lookup"><span data-stu-id="6fd51-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="6fd51-128">I exemplen ovan anger vi 00 minuter, 6 timmar i 24-timmarsformat), valfri dag i månaden, valfri månad, på söndagar. [$(datum + d) -le 15] == Körs inte om det inte är lika med eller mindre än den \% 15:e dagen (3:e veckan).</span><span class="sxs-lookup"><span data-stu-id="6fd51-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="6fd51-129">Det innebär att den körs var tredje söndag(7) i månaden kl. 06:00.</span><span class="sxs-lookup"><span data-stu-id="6fd51-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="6fd51-130">Stilla havet (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="6fd51-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="6fd51-131">Tryck på Esc</span><span class="sxs-lookup"><span data-stu-id="6fd51-131">Press “Esc”</span></span>

<span data-ttu-id="6fd51-132">Skriv ":wq" utan dubbla citattecken.</span><span class="sxs-lookup"><span data-stu-id="6fd51-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="6fd51-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="6fd51-133">w == write, q == quit</span></span>

<span data-ttu-id="6fd51-134">Om du vill visa dina jobb skriver du `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="6fd51-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="uppdatera MDE linux":::

<span data-ttu-id="6fd51-136">Så här inspekterar du ett jobb: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="6fd51-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="6fd51-137">Inspektera mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="6fd51-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="6fd51-138">För dem som använder Ansible, Chef eller Engrå</span><span class="sxs-lookup"><span data-stu-id="6fd51-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="6fd51-139">Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="6fd51-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="6fd51-140">Så här ställer du in jobb på Ansible</span><span class="sxs-lookup"><span data-stu-id="6fd51-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="6fd51-141">Mer [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) information finns i.</span><span class="sxs-lookup"><span data-stu-id="6fd51-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="6fd51-142">Så här ställer du in ttabben i Chef</span><span class="sxs-lookup"><span data-stu-id="6fd51-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="6fd51-143">Mer [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) information finns i.</span><span class="sxs-lookup"><span data-stu-id="6fd51-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="6fd51-144">Så här ställer du in jobb i Vilja</span><span class="sxs-lookup"><span data-stu-id="6fd51-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="6fd51-145">Resurstyp: t</span><span class="sxs-lookup"><span data-stu-id="6fd51-145">Resource Type: cron</span></span>

<span data-ttu-id="6fd51-146">Mer [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) information finns i.</span><span class="sxs-lookup"><span data-stu-id="6fd51-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="6fd51-147">Automatisera med Kalkylblad: Jobb och schemalagda aktiviteter</span><span class="sxs-lookup"><span data-stu-id="6fd51-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="6fd51-148">Mer [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) information finns i.</span><span class="sxs-lookup"><span data-stu-id="6fd51-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="6fd51-149">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="6fd51-149">Additional information</span></span>

<span data-ttu-id="6fd51-150">**Få hjälp med ttabben**</span><span class="sxs-lookup"><span data-stu-id="6fd51-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="6fd51-151">**Så här visar du en lista över ttabsfilen för den aktuella användaren**</span><span class="sxs-lookup"><span data-stu-id="6fd51-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="6fd51-152">**Så här hämtar du en lista över ttabsfilen för en annan användare**</span><span class="sxs-lookup"><span data-stu-id="6fd51-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="6fd51-153">**Om du vill säkerhetskopiera poster**</span><span class="sxs-lookup"><span data-stu-id="6fd51-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="6fd51-154">Gör detta innan du redigerar eller tar bort.</span><span class="sxs-lookup"><span data-stu-id="6fd51-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="6fd51-155">**Återställa ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="6fd51-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="6fd51-156">**Redigera fliken och lägga till ett nytt jobb som rotanvändare**</span><span class="sxs-lookup"><span data-stu-id="6fd51-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="6fd51-157">**Redigera fliken och lägga till ett nytt jobb**</span><span class="sxs-lookup"><span data-stu-id="6fd51-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="6fd51-158">**Redigera andra användares ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="6fd51-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="6fd51-159">**Ta bort alla ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="6fd51-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="6fd51-160">**Ta bort andra användares ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="6fd51-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="6fd51-161">**Förklaring**</span><span class="sxs-lookup"><span data-stu-id="6fd51-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

