---
title: Symantec för Microsoft Defender för Endpoint – fas 1, förberedelse
description: Det här är fas 1, förbereda för migrering från Symantec till Microsoft Defender för Endpoint.
keywords: migrering, Microsoft Defender för Slutpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 7fe0eb8adc90c259d31f237082effc80c5e8622c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537985"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrera från Symantec – fas 1: Förbereda migreringen

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fas 1: Förbereda](images/phase-diagrams/prepare.png)<br/>Fas 1: Förbereda |[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fas 2: Konfigurera](symantec-to-microsoft-defender-atp-setup.md) |[![Fas 3: Introduktion](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fas 3: Introduktion](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Du är här!*| | |


**Välkommen till förberedelsefasen för [migreringen från Symantec till Defender för Slutpunkt](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. 

Den här migreringsfasen omfattar följande steg:

1. [Uppdatera din organisations enheter.](#update-your-organizations-devices)

2. [Skaffa Microsoft Defender för Slutpunkt](#get-microsoft-defender-for-endpoint).

3. [Bevilja åtkomst till Microsoft Defender Säkerhetscenter](#grant-access-to-the-microsoft-defender-security-center).

4. [Konfigurera proxy- och internetanslutningsinställningar för enheter](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="update-your-organizations-devices"></a>Uppdatera organisationens enheter

Det är alltid bra att hålla organisationens enheter och slutpunkter uppdaterade. Kontrollera att din befintliga slutpunktsskydd och antiviruslösning är uppdaterade och att operativsystemen och apparna som din organisation använder också har de senaste uppdateringarna. Om du gör det här nu kan det förhindra problem senare när du migrerar till Defender för Endpoint.

### <a name="make-sure-symantec-is-up-to-date"></a>Kontrollera att Symantec är uppdaterat

Håll din befintliga lösning för slutpunktsskydd uppdaterad och kontrollera att din organisations enheter har de senaste säkerhetsuppdateringarna.

Behöver du hjälp? Se Broadcoms dokumentation: [Symantec Endpoint Protection installations- och administrationsguide](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)

### <a name="make-sure-your-endpoints-are-up-to-date"></a>Kontrollera att dina slutpunkter är uppdaterade

Behöver du hjälp med att uppdatera organisationens enheter? Se följande resurser:


|OS  |Resurs  |
|---------|---------|
|Windows     | [Microsoft Update](https://www.update.microsoft.com/)        |
|macOS     | [Uppdatera programvaran på din Mac](https://support.apple.com/HT201541)         |
|iOS     | [Uppdatera din iPhone, iPad eller iPod touch](https://support.apple.com/HT204204)         |
|Android     | [Kontrollera & din Android-version](https://support.google.com/android/answer/7680439)        |
|Linux     | [Linux 101: Uppdatera ditt system](https://www.linux.com/training-tutorials/linux-101-updating-your-system)        |


## <a name="get-microsoft-defender-for-endpoint"></a>Skaffa Microsoft Defender för Slutpunkt

Nu när du har uppdaterat organisationens enheter är nästa steg att skaffa Defender för Endpoint, tilldela licenser och kontrollera att tjänsten är etablerad.

1. Köp eller prova Defender för Slutpunkt idag. [Besök Defender för Endpoint om du vill påbörja en kostnadsfri utvärderingsversion eller begära en offert](https://aka.ms/mdatp). 

2. Kontrollera att licenserna har etablerats korrekt. [Kontrollera licenstillståndet](production-deployment.md#check-license-state).

3. Konfigurera den dedikerade molninstansen av Defender för Slutpunkt som global administratör eller säkerhetsadministratör. Se [Konfiguration av Defender för slutpunkt: Klientorganisationskonfiguration](production-deployment.md#tenant-configuration).

4. Om slutpunkter (till exempel enheter) i organisationen använder en proxy för att komma åt Internet, se Defender för [Konfiguration av slutpunkt: Nätverkskonfiguration](production-deployment.md#network-configuration).
 
I det här läget är du redo att ge åtkomst till dina säkerhetsadministratörer och säkerhetsoperatorer som kommer att använda Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> The Microsoft Defender Säkerhetscenter kallas ibland för Defender för Endpoint-portalen. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Bevilja åtkomst till Microsoft Defender Säkerhetscenter

I Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) får du åtkomst till och konfigurerar funktioner i Defender för Endpoint. Mer information finns i [Översikt över Microsoft Defender Säkerhetscenter](use.md).

Behörigheter till Microsoft Defender Säkerhetscenter kan beviljas med hjälp av antingen grundläggande behörigheter eller rollbaserad åtkomstkontroll (RBAC). Vi rekommenderar att du använder RBAC så att du har mer detaljerad kontroll över behörigheter.

1. Planera rollerna och behörigheterna för dina säkerhetsadministratörer och säkerhetsoperatorer. Se [Rollbaserad åtkomstkontroll](prepare-deployment.md#role-based-access-control).

2. Konfigurera och konfigurera RBAC. Vi rekommenderar att du använder [Intune](/mem/intune/fundamentals/what-is-intune) för att konfigurera RBAC, särskilt om organisationen använder en kombination av Windows 10-, macOS-, iOS- och Android-enheter. Se [konfigurera RBAC med Intune](/mem/intune/fundamentals/role-based-access-control).

   Om din organisation kräver en annan metod än Intune väljer du något av följande alternativ:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Avancerad grupprinciphantering](/microsoft-desktop-optimization-pack/agpm)

    - [Windows Administrationscenter](/windows-server/manage/windows-admin-center/overview)

3. Bevilja åtkomst till Microsoft Defender Säkerhetscenter. (Behöver du hjälp? Se [Hantera portalåtkomst med RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurera proxy- och internetanslutningsinställningar för enheter

Konfigurera proxy- och Internetinställningar för att aktivera kommunikation mellan dina enheter och Defender för slutpunkt. Följande tabell innehåller länkar till resurser som du kan använda för att konfigurera proxy- och Internetinställningar för olika operativsystem och funktioner:

|Kapaciteter  | Operativsystem | Resurser |
|:----|:----|:---|
|[Identifiering och svar av slutpunkt](overview-endpoint-detection-response.md) (Identifiering och åtgärd på slutpunkt) | [Windows 10](/windows/release-health/release-information/) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 eller senare](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Konfigurera datorproxy och internetanslutningsinställningar](configure-proxy-internet.md) |
|Identifiering och åtgärd på slutpunkt | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurera proxy- och Internetanslutningsinställningar](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|Identifiering och åtgärd på slutpunkt  |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) |[Defender för Slutpunkt på macOS: Nätverksanslutningar](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) |[Windows 10](/windows/release-health/release-information/)<p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 eller senare](/windows-server/get-started/whats-new-in-windows-server-1803)<p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md) |
|Antivirus |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)  |[Defender för slutpunkt på Mac: Nätverksanslutningar](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS eller senare LTS<p>SLES 12+<p>9+<p>Oracle Linux 7.2 |[Defender för Slutpunkt i Linux: Nätverksanslutningar](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört **förberedelsefasen** för [migreringen från Symantec till Defender för Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!
- [Fortsätt att konfigurera Defender för Slutpunkt](symantec-to-microsoft-defender-atp-setup.md).
