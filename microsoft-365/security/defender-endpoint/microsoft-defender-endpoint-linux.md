---
title: Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, installation, distribuera, avinstallation, enkel, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073001"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Endpoint för Linux.

> [!CAUTION]
> Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Microsoft Defender för Endpoint för Linux kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>Så här installerar du Microsoft Defender för Endpoint för Linux

### <a name="prerequisites"></a>Förutsättningar

- Åtkomst till Microsoft Defender Säkerhetscenter-portalen
- Linux-distribution med [systemd](https://systemd.io/) system manager
- Nybörjarupplevelse i Linux och BASH-skript
- Administratörsbehörigheter på enheten (vid manuell distribution)

### <a name="installation-instructions"></a>Installationsanvisningar

Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Microsoft Defender för Endpoint för Linux.

I allmänhet måste du göra följande:

- Kontrollera att du har en Microsoft Defender för Slutpunkt-prenumeration och att du har åtkomst till [Microsoft Defender för Slutpunktsportalen.](microsoft-defender-security-center.md)
- Distribuera Microsoft Defender för Endpoint för Linux med någon av följande distributionsmetoder:
  - Kommandoradsverktyget:
    - [Manuell distribution](linux-install-manually.md)
  - Hanteringsverktyg från tredje part:
    - [Distribuera med verktyget För konfigurationshantering av såsend](linux-install-with-puppet.md)
    - [Distribuera med ett ansible-konfigurationsverktyg](linux-install-with-ansible.md)

Om du får problem med installationen kan du gå till [Felsöka installationsproblem i Microsoft Defender för Slutpunkt för Linux.](linux-support-install.md)

### <a name="system-requirements"></a>Systemkrav

- Linux-serverdistributioner och -versioner som stöds:

  - Red Hat Enterprise Linux 7.2 eller senare
  - CentOS 7.2 eller senare
  - Ubuntu 16.04 LTS eller senare LTS
  - Hane 9 eller senare
  - SUSE Linux Enterprise Server 12 eller senare
  - Oracle Linux 7.2 eller senare

- Minsta kernel-version 3.10.0-327
- `fanotify`Kernel-alternativet måste vara aktiverat
  > [!CAUTION]
  > Det går inte att köra Defender för Slutpunkt för Linux sida vid sida med `fanotify` andra -baserade säkerhetslösningar. Det kan leda till oväntade resultat, till exempel att operativsystemet hänger sig.

- Diskutrymme: 1 GB
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
  >[!NOTE]
  > Systemhändelser som fångas av regler som lagts till `audit.logs` i läggs till i granskningsloggar och kan påverka värdgranskning och överordnad samling. Händelser som läggs till av Microsoft Defender för Endopoint för Linux kommer att märkas med `mdatp` tangenten.

### <a name="network-connections"></a>Nätverksanslutningar

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er. Om så är möjligt kan du behöva skapa en *tillåta-regel* specifikt för dem.

|**Kalkylblad med domänlista**|**Beskrivning**|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> En mer specifik URL-lista finns i Konfigurera [proxy- och Internetanslutningsinställningar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:
- Transparent proxy
- Manuell statisk proxykonfiguration

Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er. För transparenta proxy proxypar behövs ingen ytterligare konfiguration för Defender för Endpoint. För statisk proxy följer du stegen i Manuell [statisk proxykonfiguration.](linux-static-proxy-configuration.md)

> [!WARNING]
> PAC, WPAD och autentiserad proxy går inte att använda. Se till att bara en statisk proxy eller transparent proxy används.
>
> SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontroll och din proxyserver för att direkt överföra data från Defender för Endpoint för Linux till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.

Mer information om felsökning finns i [Felsöka molnanslutningsproblem för Microsoft Defender för Endpoint för Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>Uppdatera Microsoft Defender för Endpoint för Linux

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner. Om du vill uppdatera Microsoft Defender för Endpoint för Linux går du till [Distribuera uppdateringar för Microsoft Defender för Endpoint för Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>Konfigurera Microsoft Defender för Slutpunkt för Linux

Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för Slutpunkt för Linux.](linux-preferences.md)

## <a name="resources"></a>Resurser

- Mer information om loggning, avinstallation eller andra ämnen finns i [Resurser](linux-resources.md).
