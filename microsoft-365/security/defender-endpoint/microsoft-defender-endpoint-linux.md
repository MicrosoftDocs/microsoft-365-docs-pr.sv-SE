---
title: Microsoft Defender för Endpoint för Linux
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender för Endpoint på Linux.
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 008263bfb948d1a2c52031635d074aca323e6764
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256897"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint på Linux.

> [!CAUTION]
> Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint på Linux kan sannolikt leda till prestandaproblem och oförutsägbara sidoeffekter. Om skydd mot slutpunkter som inte är Microsoft är ett absolut krav i din miljö kan du fortfarande tryggt dra nytta av Defender för Endpoint på Linux Identifiering och åtgärd på slutpunkt-funktioner när du har konfigurerat antivirusfunktionerna så att de körs i [passivt läge.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Så här installerar du Microsoft Defender för Slutpunkt i Linux

### <a name="prerequisites"></a>Förutsättningar

- Åtkomst till Microsoft Defender Säkerhetscenter portalen
- Linux-distribution med [systemd](https://systemd.io/) system manager
- Nybörjarupplevelse i Linux och BASH-skript
- Administratörsbehörigheter på enheten (vid manuell distribution)

> [!NOTE]
>  Microsoft Defender för Slutpunkt på Linux-agenten är fristående [från OMS-agenten.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent) Microsoft Defender för Endpoint använder sig av en egen oberoende telemetripipeline.
> 
> Microsoft Defender för Endpoint på Linux är ännu inte integrerat i Azure Säkerhetscenter.



### <a name="installation-instructions"></a>Installationsanvisningar

Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint i Linux.

I allmänhet måste du göra följande:

- Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)
- Distribuera Microsoft Defender för Slutpunkt på Linux med någon av följande distributionsmetoder:
  - Kommandoradsverktyget:
    - [Manuell distribution](linux-install-manually.md)
  - Hanteringsverktyg från tredje part:
    - [Distribuera med verktyget För konfigurationshantering av såsend](linux-install-with-puppet.md)
    - [Distribuera med ett ansible-konfigurationsverktyg](linux-install-with-ansible.md)
    - [Distribuera med konfigurationshanteringsverktyget Chef](linux-deploy-defender-for-endpoint-with-chef.md)
    
Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt i Linux.](linux-support-install.md)



### <a name="system-requirements"></a>Systemkrav

- Linux-serverdistributioner och x64-versioner (AMD64/EM64T) stöds:

  - Red Hat Enterprise Linux 7.2 eller senare
  - CentOS 7.2 eller senare
  - Ubuntu 16.04 LTS eller senare LTS
  - Hane 9 eller senare
  - SUSE Linux Enterprise Server 12 eller senare
  - Oracle Linux 7.2 eller senare

    > [!NOTE]
    > Distributions- och versionsnummer som inte uttryckligen anges stöds inte (även om de härleds från de officiellt angivna fördelningarna).


- Minsta kernel-version 3.10.0-327

- `fanotify`Kernel-alternativet måste vara aktiverat

  > [!CAUTION]
  > Det går inte att köra Defender för slutpunkt på Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar. Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.

- Diskutrymme: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon kräver körbar behörighet. Mer information finns i "Se till att daemon har körbar behörighet" i Felsöka installationsproblem för [Microsoft Defender för slutpunkt i Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)

- Kärnor: minst 2, 4 som prioriteras

- Minne: minst 1 GB, 4 som rekommenderas

    > [!NOTE]
    > Kontrollera att du har ledigt diskutrymme i /varians.

- Lösningen tillhandahåller för närvarande realtidsskydd för följande filsystemtyper:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.

- Granskningsramverket `auditd` () måste vara aktiverat.
  > [!NOTE]
  > Systemhändelser som fångas av regler som lagts till i läggs till `/etc/audit/rules.d/` `audit.log` i (s) och kan påverka värdgranskning och överordnad samling. Händelser som läggs till av Microsoft Defender för Endpoint i Linux kommer att taggas med `mdatp` en nyckel.

### <a name="network-connections"></a>Nätverksanslutningar

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er. Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.

| Kalkylblad med domänlista | Beskrivning |
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:
- Transparent proxy
- Manuell statisk proxykonfiguration

Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er. För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint. För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)

> [!WARNING]
> PAC, WPAD och autentiserad proxy går inte att använda. Se till att bara en statisk proxy eller transparent proxy används.
>
> SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontrollen och proxyservern för att direkt överföra data från Defender för Slutpunkt i Linux till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.

Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Slutpunkt på Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Uppdatera Microsoft Defender för Slutpunkt i Linux

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner. Om du vill uppdatera Microsoft Defender för Slutpunkt på Linux går du till [Distribuera uppdateringar för Microsoft Defender för Slutpunkt i Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Konfigurera Microsoft Defender för Slutpunkt i Linux

Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för slutpunkt i Linux.](linux-preferences.md)

## <a name="resources"></a>Resurser

- Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).
