---
title: Distribuera Microsoft Defender för slutpunkt på Linux med Defender
ms.reviewer: ''
description: Här beskrivs hur du distribuerar Microsoft Defender för Slutpunkt på Linux med Hjälp av Linux.
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
ms.openlocfilehash: d54732134e91b87b2639634c365556beda5312b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934579"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>Distribuera Microsoft Defender för slutpunkt på Linux med Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

I den här artikeln beskrivs hur du distribuerar Defender för Endpoint på Linux med Hjälp av Linux. För en lyckad distribution måste alla följande uppgifter slutföras:

- [Ladda ned onboarding-paketet](#download-the-onboarding-package)
- [Create Manifest](#create-a-puppet-manifest)
- [Distribution](#deployment)
- [Kontrollera onboarding-status](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Krav och systemkrav

 En beskrivning av krav och systemkrav för den aktuella programvaruversionen finns på [huvudsidan för Defender för slutpunkt på Linux.](microsoft-defender-endpoint-linux.md)

För distributionen av distributionsen så måste du dessutom vara bekant med projektadministrationsuppgifter, har konfigurering av första hand och vet hur du distribuerar paket. Det finns många sätt att slutföra samma uppgift på. I de här instruktionerna förutsätts att det finns stöd för moduler som stöds, till exempel *apt* för att distribuera paketet. Din organisation kan använda ett annat arbetsflöde. Mer information finns [i dokumentation](https://puppet.com/docs) om Dokumentation.

## <a name="download-the-onboarding-package"></a>Ladda ned onboarding-paketet

Ladda ned introduktionspaketet från Microsoft Defender Säkerhetscenter:

1. I Microsoft Defender Säkerhetscenter går du till Inställningar > **på Enhetshantering > Onboarding.**
2. I den första listrutan väljer du **Linux Server** som operativsystem. I den andra nedrullningsmenyn väljer du **Det konfigurationshanteringsverktyg du** föredrar i Linux som distributionsmetod.
3. Välj **Hämta introduktionspaket**. Spara filen som WindowsDefenderATPOnboardingPackage.zip.

    ![Microsoft Defender Säkerhetscenter skärmbild](images/atp-portal-onboarding-linux-2.png)

4. Kontrollera att filen finns i kommandotolken. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Extrahera innehållet i arkivet.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Skapa ett manifest av semanifest

Du måste skapa ett Manifest för att distribuera Defender för Slutpunkt på Linux till enheter som hanteras av en Server för server av en klient. I det här exemplet används de *apt-* och *yumrepo-moduler* som är tillgängliga från celllabs, och förutsätter att modulerna har installerats på din Server för server för server, så att du kan installera dem på den.

Skapa mapparna *install_mdatp/filer* *och install_mdatp/manifest* under modulmappen i din arkivinstallation. Den här mappen finns normalt *i /etc/lablabs/code/environments/production/modules* på din Server för server för server, där du kan installera en server. Kopiera filen mdatp_onboard.jsfilen som skapats ovan till mappen *install_mdatp/filer.* Skapa en *init.pp* som innehåller distributionsanvisningarna:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Innehållet i `install_mdatp/manifests/init.pp`

Defender för Slutpunkt i Linux kan distribueras från någon av följande kanaler (anges nedan som *[kanal]*): *insiders-fast,* *insiders-slow* eller *prod*. Var och en av dessa kanaler motsvarar en linux-programvarudatabas.

Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet. Enheter inom *insiders – snabbt* är de första som får uppdateringar och nya funktioner, följt senare av *insiders-slow* och slutligen *av prod*.

Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget så att de använder *insiders snabbt* eller *insiders -långsamt.*

> [!WARNING]
> Om du byter kanal efter den första installationen måste produkten installeras om. Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.

Notera distribution och version och ange den mest närmaste posten för den under `https://packages.microsoft.com/config/` .

I kommandona nedan *ersätter du [distro]* *och [version]* med den information som du har identifierat:

> [!NOTE]
> När det gäller RedHat, Oracle EL och CentOS 8 ersätter *du [distro]* med 'rhel'.

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Distribution

Ta med manifestet ovan på din webbplats.pp fil:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

Registrerade agentenheter avsöker med jämna mellanrum på Server för server, och installerar nya konfigurationsprofiler och principer så snart de hittas.

## <a name="monitor-puppet-deployment"></a>Övervaka distribution av bildskärmar

På agentenheten kan du även kontrollera status för onboarding genom att köra:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **licensierad:** Detta bekräftar att enheten är knuten till din organisation.

- **orgId:** Det här är din Defender för slutpunktsorganisationsidentifierare.

## <a name="check-onboarding-status"></a>Kontrollera onboarding-status

Du kan kontrollera att enheter har varit korrekt onboarded genom att skapa ett skript. Följande skript kontrollerar till exempel registrerade enheter för registreringsstatus:

```bash
mdatp health --field healthy
```

Kommandot ovan skrivs ut `1` om produkten är onboarded och fungerar som förväntat.

> [!IMPORTANT]
> När produkten startas för första gången laddas de senaste definitionerna för program mot skadlig programvara ned. Beroende på din Internetanslutning kan det ta upp till några minuter. Under den här tiden returnerar kommandot ovan värdet `0` .

Om produkten inte är felfri visar utgångskoden (som kan kontrolleras `echo $?` genom) problemet:

- 1 om enheten inte är ombord ännu.
- 3 om anslutningen till daemon inte kan upprättas.

## <a name="log-installation-issues"></a>Logga installationsproblem

 Mer information om hur du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i [Problem med logginstallation.](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Uppgraderingar av operativsystem

När du uppgraderar ditt operativsystem till en ny huvudversion måste du först avinstallera Defender för Slutpunkt i Linux, installera uppgraderingen och slutligen konfigurera om Defender för Slutpunkt på Linux på din enhet.

## <a name="uninstallation"></a>Avinstallation

Skapa en *remove_mdatp* som *install_mdatp* med följande innehåll i *init.pp* fil:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
