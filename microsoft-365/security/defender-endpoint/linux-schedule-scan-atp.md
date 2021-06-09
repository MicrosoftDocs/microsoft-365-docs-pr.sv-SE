---
title: Schemalägga genomsökningar med Microsoft Defender för Endpoint (Linux)
description: Lär dig hur du schemalägger en automatisk genomsökningstid för Microsoft Defender för Endpoint (Linux) för att bättre skydda organisationens tillgångar.
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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845372"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="daac8-104">Schemalägga genomsökningar med Microsoft Defender för Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="daac8-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="daac8-105">Läs kommandon som stöds om du vill köra en [genomsökning för Linux.](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="daac8-105">To run a scan for Linux, see [Supported Commands](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="daac8-106">Linux (och Unix) har verktyget **t.ex.tab** (liknar Schemaläggaren) för att kunna köra schemalagda aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="daac8-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="daac8-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="daac8-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="daac8-108">Om du vill visa en lista över alla tidszoner kör du följande kommando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="daac8-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="daac8-109">Exempel för tidszoner:</span><span class="sxs-lookup"><span data-stu-id="daac8-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="daac8-110">Så här ställer du in Job</span><span class="sxs-lookup"><span data-stu-id="daac8-110">To set the Cron job</span></span>
<span data-ttu-id="daac8-111">Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="daac8-111">Use the following commands:</span></span>

<span data-ttu-id="daac8-112">**Om du vill säkerhetskopiera poster**</span><span class="sxs-lookup"><span data-stu-id="daac8-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="daac8-113">Där 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="daac8-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="daac8-114">Gör detta innan du redigerar eller tar bort.</span><span class="sxs-lookup"><span data-stu-id="daac8-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="daac8-115">Så här redigerar du fliken och lägger till ett nytt jobb som rotanvändare:</span><span class="sxs-lookup"><span data-stu-id="daac8-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="daac8-116">Standardredigeraren är VIM.</span><span class="sxs-lookup"><span data-stu-id="daac8-116">The default editor is VIM.</span></span>

<span data-ttu-id="daac8-117">Du kan se:</span><span class="sxs-lookup"><span data-stu-id="daac8-117">You might see:</span></span>

<span data-ttu-id="daac8-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="daac8-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="daac8-119">Tryck på Infoga</span><span class="sxs-lookup"><span data-stu-id="daac8-119">Press “Insert”</span></span>

<span data-ttu-id="daac8-120">Lägg till följande poster:</span><span class="sxs-lookup"><span data-stu-id="daac8-120">Add the following entries:</span></span>

<span data-ttu-id="daac8-121">CRON_TZ=Amerika/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="daac8-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="daac8-122">0 2 \* lör /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="daac8-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="daac8-123">I det här exemplet har vi ställt in det på 00 minuter, 02:00.</span><span class="sxs-lookup"><span data-stu-id="daac8-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="daac8-124">(timme i 24-timmarsformat), valfri dag i månaden, valfri månad, på lördagar.</span><span class="sxs-lookup"><span data-stu-id="daac8-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="daac8-125">Det innebär att det körs lördagar kl. 02:00.</span><span class="sxs-lookup"><span data-stu-id="daac8-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="daac8-126">Stilla havet (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="daac8-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="daac8-127">Tryck på Esc</span><span class="sxs-lookup"><span data-stu-id="daac8-127">Press “Esc”</span></span>

<span data-ttu-id="daac8-128">Skriv ":wq" utan dubbla citattecken.</span><span class="sxs-lookup"><span data-stu-id="daac8-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="daac8-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="daac8-129">w == write, q == quit</span></span>

<span data-ttu-id="daac8-130">Om du vill visa dina jobb skriver du `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="daac8-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="daac8-132">**Så här inspekterar du jobb jobb**</span><span class="sxs-lookup"><span data-stu-id="daac8-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="daac8-133">**Inspektera mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="daac8-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="daac8-134">För dem som använder Ansible, Chef eller Engrå</span><span class="sxs-lookup"><span data-stu-id="daac8-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="daac8-135">Använd följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="daac8-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="daac8-136">Så här ställer du in jobb på Ansible</span><span class="sxs-lookup"><span data-stu-id="daac8-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="daac8-137">Mer [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) information finns i.</span><span class="sxs-lookup"><span data-stu-id="daac8-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="daac8-138">Så här ställer du in ttabben i Chef</span><span class="sxs-lookup"><span data-stu-id="daac8-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="daac8-139">Mer [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) information finns i.</span><span class="sxs-lookup"><span data-stu-id="daac8-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="daac8-140">Så här ställer du in jobb i Vilja</span><span class="sxs-lookup"><span data-stu-id="daac8-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="daac8-141">Resurstyp: t</span><span class="sxs-lookup"><span data-stu-id="daac8-141">Resource Type: cron</span></span>

<span data-ttu-id="daac8-142">Mer [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) information finns i.</span><span class="sxs-lookup"><span data-stu-id="daac8-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="daac8-143">Automatisera med Kalkylblad: Jobb och schemalagda aktiviteter</span><span class="sxs-lookup"><span data-stu-id="daac8-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="daac8-144">Mer [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) information finns i.</span><span class="sxs-lookup"><span data-stu-id="daac8-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="daac8-145">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="daac8-145">Additional information</span></span>

<span data-ttu-id="daac8-146">**Få hjälp med ttabben**</span><span class="sxs-lookup"><span data-stu-id="daac8-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="daac8-147">**Så här visar du en lista över ttabsfilen för den aktuella användaren**</span><span class="sxs-lookup"><span data-stu-id="daac8-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="daac8-148">**Så här hämtar du en lista över ttabsfilen för en annan användare**</span><span class="sxs-lookup"><span data-stu-id="daac8-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="daac8-149">**Om du vill säkerhetskopiera poster**</span><span class="sxs-lookup"><span data-stu-id="daac8-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="daac8-150">Gör detta innan du redigerar eller tar bort.</span><span class="sxs-lookup"><span data-stu-id="daac8-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="daac8-151">**Återställa ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="daac8-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="daac8-152">**Redigera fliken och lägga till ett nytt jobb som rotanvändare**</span><span class="sxs-lookup"><span data-stu-id="daac8-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="daac8-153">**Redigera fliken och lägga till ett nytt jobb**</span><span class="sxs-lookup"><span data-stu-id="daac8-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="daac8-154">**Redigera andra användares ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="daac8-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="daac8-155">**Ta bort alla ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="daac8-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="daac8-156">**Ta bort andra användares ttabsposter**</span><span class="sxs-lookup"><span data-stu-id="daac8-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="daac8-157">**Förklaring**</span><span class="sxs-lookup"><span data-stu-id="daac8-157">**Explanation**</span></span>

<span data-ttu-id="daac8-158">+—————- minut (värden: 0–59) (specialtecken: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="daac8-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="daac8-159">| +————- timme (värden: 0–23) (specialtecken: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="daac8-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="daac8-160">| | +———- dag i månaden (värden: 1–31) (specialtecken: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="daac8-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="daac8-161">| | | +——- månad (värden: 1–12) (specialtecken: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="daac8-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="daac8-162">| | | | +— veckodag (värden: 0–6) (söndag=0 eller 7) (specialtecken: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="daac8-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="daac8-163">| | | | |\*\*\*\*\*-kommando som ska utföras</span><span class="sxs-lookup"><span data-stu-id="daac8-163">| | | | |\*\*\*\*\*command to be executed</span></span>


