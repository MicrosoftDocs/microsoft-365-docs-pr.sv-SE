---
title: Distribuera Microsoft Defender för slutpunkt på Linux med Ansible
ms.reviewer: ''
description: I artikeln beskrivs hur du distribuerar Microsoft Defender för slutpunkt på Linux med Ansible.
keywords: microsoft, defender, Microsoft Defender för Endpoint, linux, installation, distribution, avinstallation, docka, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572735"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Distribuera Microsoft Defender för slutpunkt på Linux med Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Defender for Endpoint? [Registrera dig för en gratis provperiod.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

I den här artikeln beskrivs hur du distribuerar Defender för punkt på Linux med ansible. En lyckad distribution kräver att alla följande uppgifter slutförs:

- [Ladda ner onboarding-paketet](#download-the-onboarding-package)
- [Skapa ansible YAML-filer](#create-ansible-yaml-files)
- [Distribution](#deployment)
- [Referenser](#references)

## <a name="prerequisites-and-system-requirements"></a>Förutsättningar och systemkrav

Innan du börjar, se [huvud defender för endpoint på Linux-sidan](microsoft-defender-endpoint-linux.md) för en beskrivning av förutsättningar och systemkrav för den aktuella programvaruversionen.

För ansibel distribution måste du dessutom vara bekant med Ansible-administrationsuppgifter, ha Ansible konfigurerad och veta hur du distribuerar spelböcker och uppgifter. Ansible har många sätt att slutföra samma uppgift. De här anvisningarna förutsätter tillgänglighet för ansible-moduler som stöds, *till exempel lämpliga och osökbara* *för* att hjälpa till att distribuera paketet. Din organisation kan använda ett annat arbetsflöde. Mer information finns i dokumentationen om [ansible.](https://docs.ansible.com/)

- Ansible måste installeras på minst en dator (Ansible kallar detta kontrollnoden).
- SSH måste konfigureras för ett administratörskonto mellan kontrollnoden och alla hanterade noder (enheter som har Defender för slutpunkt installerad på dem), och vi rekommenderar att du konfigureras med autentisering av offentliga autentiseringar.
- Följande programvara måste installeras på alla hanterade noder:
  - hårlock
  - python-apt

- Alla hanterade noder måste visas i följande format i `/etc/ansible/hosts` den eller relevanta filen:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping-test:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Ladda ner onboarding-paketet

Ladda ner onboarding-paketet från Microsoft Defender Säkerhetscenter:

1. I Microsoft Defender Säkerhetscenter går du **till Inställningar > Device Management > Onboarding**.
2. Välj Linux Server som operativsystem i den **första nedrullningsbara** menyn. I den andra listrutan väljer du Ditt önskade **Linux-konfigurationshanteringsverktyg** som distributionsmetod.
3. Välj **Ladda ner onboarding-paket**. Spara filen som WindowsDefenderATPOnboardingPackage.zip.

    ![Microsoft Defender Säkerhetscenter skärmdump](images/atp-portal-onboarding-linux-2.png)

4. Kontrollera att du har filen i kommandotolken. Extrahera innehållet i arkivet:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Skapa ansible YAML-filer

Skapa en undertask eller rollfiler som bidrar till en spelbok eller uppgift.

- Skapa onboarding-uppgiften: `onboarding_setup.yml`

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Lägg till databasen och nyckeln Defender för `add_apt_repo.yml` slutpunkt:

    Defender for Endpoint på Linux kan distribueras från någon av följande kanaler (betecknas nedan som *[kanal]*): *insiders-fast*, *insiders-slow* eller *prod*. Var och en av dessa kanaler motsvarar en Linux-programvarudatabas.

    Valet av kanal avgör vilken typ och frekvens av uppdateringar som erbjuds din enhet. Enheter i *insiders-fast* är de första som får uppdateringar och nya funktioner, följt senare *av insiders-långsamma* och slutligen *av prod*.

    För att förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag för att använda *antingen insiders-fast* eller *insiders-slow*.

    > [!WARNING]
    > Om du byter kanal efter den första installationen måste produkten installeras om. Så här byter du produktkanal: avinstallerar det befintliga paketet, konfigurerar om enheten så att den använder den nya kanalen och följer anvisningarna i det här dokumentet för att installera paketet från den nya platsen.

    Notera distributionen och versionen och identifiera den närmaste posten för den under `https://packages.microsoft.com/config/` .

    I följande kommandon ersätter du *[distro]* och *[version]* med den information du har identifierat.

    > [!NOTE]
    > När det gäller Oracle Linux, ersätt *[distro]* med "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Skapa Ansible-installera och avinstallera YAML-filer.

    - För apt-baserade distributioner använder du följande YAML-fil:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - För dnf-baserade distributioner använder du följande YAML-fil:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Distribution

Kör nu uppgiftsfilerna under `/etc/ansible/playbooks/` eller relevant katalog.

- installation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> När produkten startar för första gången laddar den ner de senaste antimalware-definitionerna. Beroende på din Internetanslutning kan det ta upp till några minuter.

- Validering/konfiguration:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Avinstallation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Problem med logginstallation

Mer information [om hur](linux-resources.md#log-installation-issues) du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Logga installationsproblem.

## <a name="operating-system-upgrades"></a>Uppgraderingar av operativsystem

När du uppgraderar operativsystemet till en ny huvudversion måste du först avinstallera Defender för Endpoint på Linux, installera uppgraderingen och slutligen konfigurera om Defender för slutpunkt på Linux på din enhet.

## <a name="references"></a>Referenser

- [Lägga till eller ta bort YUM-databaser](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Hantera paket med dnf-pakethanteraren](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Lägga till och ta bort APT-databaser](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Hantera apt-paket](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Se även
- [Undersöka hälsoproblem i agenten](health-status.md)
