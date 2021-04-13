---
title: Felsöka installationsproblem för Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Felsöka installationsproblem för Microsoft Defender ATP för Linux
keywords: microsoft, defender, atp, linux, installation
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
ms.openlocfilehash: 347528def6929dde200249cd9710f7ce33484c7f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688819"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Felsöka installationsproblem för Microsoft Defender för Slutpunkt i Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Kontrollera att installationen lyckades

Ett fel vid installationen kan eller kanske inte resultera i ett meningsfullt felmeddelande av pakethanteraren. Kontrollera om installationen lyckades genom att hämta och kontrollera installationsloggarna med hjälp av:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Ett utdata från föregående kommando med rätt datum och tid för installationen anger framgång.

Kontrollera även [klientkonfigurationen](linux-install-manually.md#client-configuration) för att verifiera produktens hälsa och identifiera TEXTFILEN EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Kontrollera att du har rätt paket

Tänk på att paketet som du installerar matchar värddistributionen och versionen.

| paket                       | distribution                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL och CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL och CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Ubuntu och Ubuntu 16.04, 18.04 och 20.04 |

Vid [manuell distribution](linux-install-manually.md)kontrollerar du att rätt distro och version har valts.

## <a name="installation-failed"></a>Installationen misslyckades

Kontrollera om mdatp-tjänsten körs:

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

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Steg för felsökning om mdatp-tjänsten inte körs

1. Kontrollera om "mdatp"-användaren finns:

    ```bash
    id "mdatp"
    ```

    Om det inte finns några utdata kör du

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Prova att aktivera och starta om tjänsten med hjälp av:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Om mdatp.service inte hittas när du kör föregående kommando kör du:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    where ```<systemd_path>``` is for Ubuntu and Distributions Distributions and for ```/lib/systemd/system``` ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle and SLES.
   Kör sedan steg 2 igen.

4. Om stegen ovan inte fungerar kontrollerar du om SELinux är installerat och i tvingande läge. I så fall kan du prova att ställa in det till tillåtande (helst) eller inaktiverat läge. Det kan göras genom att ange parametern `SELINUX` till "tillåtande" eller "inaktiverad" i `/etc/selinux/config` filen, följt av omstart. Mer information finns på sidan med selinux.
Prova nu att starta om mdatp-tjänsten med steg 2. Återställ konfigurationsändringen omedelbart, men av säkerhetsskäl när du har försökt och startat om den.

5. Om `/opt` katalog är en symbolisk länk skapar du ett bindfästen för `/opt/microsoft` .

6. Kontrollera att daemon har körbar behörighet.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Om daemon inte har körbara behörigheter gör du det körbart med hjälp av:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    och försöker köra steg 2 igen.

7. Kontrollera att filsystemet som innehåller wdavdaemon inte har "noexec".

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Om mdatp-tjänsten körs, men EICAR-textfilidentifiering inte fungerar

1. Kontrollera filsystemtypen med hjälp av:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    De filsystem som för närvarande stöds för aktivitet vid åtkomst anges [här.](microsoft-defender-endpoint-linux.md#system-requirements) Filer utanför dessa filsystem genomsöks inte.

## <a name="command-line-tool-mdatp-isnt-working"></a>Kommandoradsverktyget "mdatp" fungerar inte

1. Om ett fel uppstår när `mdatp` kommandoradsverktyget körs `command not found` kör du följande kommando:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    och försök igen.

    Om inget av stegen ovan hjälper samlar du in diagnostikloggarna:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Sökväg till en zip-fil som innehåller loggarna visas som en utdatafil. Kontakta vår kundsupport med de här loggarna.
