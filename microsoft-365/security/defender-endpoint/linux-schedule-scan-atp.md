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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Schemalägga genomsökningar med Microsoft Defender för Endpoint (Linux)

Läs kommandon som stöds om du vill köra en [genomsökning för Linux.](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux (och Unix) har verktyget **t.ex.tab** (liknar Schemaläggaren) för att kunna köra schemalagda aktiviteter.

## <a name="pre-requisite"></a>Förutsättningar

> [!NOTE]
> Om du vill visa en lista över alla tidszoner kör du följande kommando: `timedatectl list-timezones`<br>
> Exempel för tidszoner:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Så här ställer du in Job
Använd följande kommandon:

**Om du vill säkerhetskopiera poster**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Där 200919 == YRMMDD

> [!TIP]
> Gör detta innan du redigerar eller tar bort. <br>

Så här redigerar du fliken och lägger till ett nytt jobb som rotanvändare: <br>
`sudo crontab -e`

> [!NOTE]
> Standardredigeraren är VIM.

Du kan se:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Tryck på Infoga

Lägg till följande poster:

CRON_TZ=Amerika/Los_Angeles

0 2 * lör /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>I det här exemplet har vi ställt in det på 00 minuter, 02:00. (timme i 24-timmarsformat), valfri dag i månaden, valfri månad, på lördagar. Det innebär att det körs lördagar kl. 02:00. Stilla havet (UTC –8).

Tryck på Esc

Skriv ":wq" utan dubbla citattecken.

> [!NOTE]
> w == write, q == quit

Om du vill visa dina jobb skriver du `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**Så här inspekterar du jobb jobb**

`sudo grep mdatp /var/log/cron`

**Inspektera mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

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

+—————- minut (värden: 0–59) (specialtecken: , – * /)  <br>
| +————- timme (värden: 0–23) (specialtecken: , – * /) <br>
| | +———- dag i månaden (värden: 1–31) (specialtecken: , – * / L W C)  <br>
| | | +——- månad (värden: 1–12) (specialtecken: ,- * / )  <br>
| | | | +— veckodag (värden: 0–6) (söndag=0 eller 7) (specialtecken: , – * / L W C) <br>
| | | | |*****-kommando som ska utföras


