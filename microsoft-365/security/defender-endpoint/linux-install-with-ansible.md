---
title: Distribuera Microsoft Defender för Slutpunkt på Linux med Ansible
ms.reviewer: ''
description: Här beskrivs hur du distribuerar Microsoft Defender för Slutpunkt på Linux med Ansible.
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
ms.openlocfilehash: 15ee02d90e81c48bf5ec718e669bf8f88f6424ff
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934783"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Distribuera Microsoft Defender för Slutpunkt på Linux med Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

I den här artikeln beskrivs hur du distribuerar Defender för Slutpunkt på Linux med Ansible. För en lyckad distribution måste alla följande uppgifter slutföras:

- [Ladda ned onboarding-paketet](#download-the-onboarding-package)
- [Skapa ansible YAML-filer](#create-ansible-yaml-files)
- [Distribution](#deployment)
- [Referenser](#references)

## <a name="prerequisites-and-system-requirements"></a>Krav och systemkrav

Innan du börjar kan du gå [till huvudsidan för Defender](microsoft-defender-endpoint-linux.md) för Slutpunkt på Linux för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.

För ansible-distribution måste du dessutom känna till Ansible-administrationsuppgifter, ha Ansible konfigurerat och veta hur du distribuerar spelböcker och uppgifter. Det finns många sätt att slutföra samma aktivitet på ansible. De här instruktionerna förutsätter tillgänglighet för ansible-moduler som stöds, till exempel *apt* och *inte arkiverade för* distribution av paketet. Din organisation kan använda ett annat arbetsflöde. Mer information finns [i dokumentationen till Ansible.](https://docs.ansible.com/)

- Ansible måste vara installerat på minst en dator (vi kallar det för primär dator).
- SSH måste konfigureras för ett administratörskonto mellan den primära datorn och alla klienter, och det rekommenderas att konfigureras med offentlig nyckelautentisering.
- Följande programvara måste vara installerad på alla klienter:
  - böjning
  - python-apt

- Alla värdar måste visas i följande format i `/etc/ansible/hosts` den eller relevanta filen:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping-test:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Ladda ned onboarding-paketet

Ladda ned introduktionspaketet från Microsoft Defender Säkerhetscenter:

1. I Microsoft Defender Säkerhetscenter går du till **Inställningar > Enhetshantering > Onboarding**.
2. I den första listrutan väljer du **Linux Server** som operativsystem. I den andra nedrullningsmenyn väljer du **Det konfigurationshanteringsverktyg du** föredrar i Linux som distributionsmetod.
3. Välj **Hämta introduktionspaket**. Spara filen som WindowsDefenderATPOnboardingPackage.zip.

    ![Skärmbild av Microsoft Defender Säkerhetscenter](images/atp-portal-onboarding-linux-2.png)

4. Kontrollera att filen finns i kommandotolken. Extrahera innehållet i arkivet:

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

Skapa en underaktivitet eller rollfiler som bidrar till en spelbok eller uppgift.

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

- Lägg till Defender för slutpunktens lagringsplats och nyckel.

    Defender för Slutpunkt i Linux kan distribueras från någon av följande kanaler (anges nedan som *[kanal]*): *insiders-fast,* *insiders-slow* eller *prod*. Var och en av dessa kanaler motsvarar en linux-programvarudatabas.

    Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet. Enheter inom *insiders – snabbt* är de första som får uppdateringar och nya funktioner, följt senare av *insiders-slow* och slutligen *av prod*.

    Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget så att de använder *insiders snabbt* eller *insiders -långsamt.*

    > [!WARNING]
    > Om du byter kanal efter den första installationen måste produkten installeras om. Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.

    Notera distribution och version och ange den mest närmaste posten för den under `https://packages.microsoft.com/config/` .

    I följande kommandon ersätter *du [distro]* *och [version]* med den information som du har identifierat.

    > [!NOTE]
    > Om du använder Oracle Linux *ersätter du [distro]* med "rhel".

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

- Skapa ansible-installationen och avinstallera YAML-filer.

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

- Installation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> När produkten startas för första gången laddas de senaste definitionerna för program mot skadlig programvara ned. Beroende på din Internetanslutning kan det ta upp till några minuter.

- Verifiering/konfiguration:

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

## <a name="log-installation-issues"></a>Logga installationsproblem

Mer [information om hur](linux-resources.md#log-installation-issues) du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Problem med logginstallationen.

## <a name="operating-system-upgrades"></a>Uppgraderingar av operativsystem

När du uppgraderar ditt operativsystem till en ny huvudversion måste du först avinstallera Defender för Slutpunkt i Linux, installera uppgraderingen och slutligen konfigurera om Defender för Slutpunkt på Linux på din enhet.

## <a name="references"></a>Referenser

- [Lägga till eller ta bort YUM-lagringsplatsen](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Hantera paket med pakethanteraren för dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Lägga till och ta bort APT-lagringsplatsen](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Hantera avd-paket](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
