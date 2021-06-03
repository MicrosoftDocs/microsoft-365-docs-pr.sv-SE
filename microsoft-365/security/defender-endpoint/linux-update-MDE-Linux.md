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
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730876"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Schemalägga en uppdatering av Microsoft Defender för Endpoint (Linux)

Information om hur du kör en uppdatering på Microsoft Defender för Slutpunkt på Linux finns i [Distribuera uppdateringar för Microsoft Defender för slutpunkt i Linux.](/microsoft-365/security/defender-endpoint/linux-updates)

Linux (och Unix) har verktyget **t.ex.tab** (liknar Schemaläggaren) för att kunna köra schemalagda aktiviteter.

## <a name="pre-requisite"></a>Förutsättningar

> [!NOTE]
> Om du vill visa en lista över alla tidszoner kör du följande kommando: `timedatectl list-timezones`<br>
> Exempel för tidszoner: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Så här ställer du in Job
Använd följande kommandon:

**Om du vill säkerhetskopiera poster**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Där 201118 == YYMMDD

> [!TIP]
> Gör detta innan du redigerar eller tar bort. <br>

Så här redigerar du fliken och lägger till ett nytt jobb som rotanvändare: <br>
`sudo crontab -e`

> [!NOTE]
> Standardredigeraren är VIM.

Du kan se:

0****/etc/opt/microsoft/mdatp/logrorate.sh

Och

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Se [Schemalägga genomsökningar med Microsoft Defender för Endpoint (Linux)](linux-schedule-scan-atp.md)

Tryck på Infoga

Lägg till följande poster:

CRON_TZ=Amerika/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL och varianter (CentOS och Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES och varianter

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu och Ubuntu systems

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> I exemplen ovan anger vi 00 minuter, 6 timmar i 24-timmarsformat), valfri dag i månaden, valfri månad, på söndagar. [$(datum + d) -le 15] == Körs inte om det inte är lika med eller mindre än den \% 15:e dagen (3:e veckan). Det innebär att den körs var tredje söndag(7) i månaden kl. 06:00. Stilla havet (UTC -8).

Tryck på Esc

Skriv ":wq" utan dubbla citattecken.

> [!NOTE]
> w == write, q == quit

Om du vill visa dina jobb skriver du `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="uppdatera MDE linux":::

Så här inspekterar du ett jobb: `sudo grep mdatp /var/log/cron`

Inspektera mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>För dem som använder Ansible, Chef eller Engrå

Använd följande kommandon:
### <a name="to-set-cron-jobs-in-ansible"></a>Så här ställer du in jobb på Ansible

`cron – Manage cron.d and crontab entries`

Mer [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) information finns i.

### <a name="to-set-crontabs-in-chef"></a>Så här ställer du in ttabben i Chef
`cron resource`

Mer [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) information finns i.

### <a name="to-set-cron-jobs-in-puppet"></a>Så här ställer du in jobb i Vilja
Resurstyp: t

Mer [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) information finns i.

Automatisera med Kalkylblad: Jobb och schemalagda aktiviteter

Mer [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) information finns i.

## <a name="additional-information"></a>Ytterligare information

**Få hjälp med ttabben**

`man crontab`

**Så här visar du en lista över ttabsfilen för den aktuella användaren**

`crontab -l`

**Så här hämtar du en lista över ttabsfilen för en annan användare**

`crontab -u username -l`

**Om du vill säkerhetskopiera poster**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Gör detta innan du redigerar eller tar bort. <br>

**Återställa ttabsposter**

`crontab /var/tmp/cron_backup.dat`

**Redigera fliken och lägga till ett nytt jobb som rotanvändare**

`sudo crontab -e`

**Redigera fliken och lägga till ett nytt jobb**

`crontab -e`

**Redigera andra användares ttabsposter**

`crontab -u username -e`

**Ta bort alla ttabsposter**

`crontab -r`

**Ta bort andra användares ttabsposter**

`crontab -u username -r`

**Förklaring**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

