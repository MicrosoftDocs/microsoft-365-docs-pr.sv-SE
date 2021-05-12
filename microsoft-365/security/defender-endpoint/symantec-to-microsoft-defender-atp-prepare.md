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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: bba48803863cd330b371c24600239462b1ca9250
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327420"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrera från Symantec – fas 1: Förbereda migreringen

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fas 1: Förbereda](images/phase-diagrams/prepare.png)<br/>Fas 1: Förbereda |[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fas 2: Konfigurera](symantec-to-microsoft-defender-atp-setup.md) |[![Fas 3: Introduktion](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fas 3: Introduktion](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Du är här!*| | |


**Välkommen till förberedelsefasen för [migreringen från Symantec till Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. 

Den här migreringsfasen omfattar följande steg:
1. [Skaffa Microsoft Defender för Slutpunkt](#get-microsoft-defender-for-endpoint).
2. [Bevilja åtkomst till Microsoft Defender Säkerhetscenter.](#grant-access-to-the-microsoft-defender-security-center)
3. [Konfigurera enhetsproxy och internetanslutningsinställningar](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-microsoft-defender-for-endpoint"></a>Skaffa Microsoft Defender för Slutpunkt

För att komma igång måste du ha Microsoft Defender för Endpoint, med tilldelade och etablerade licenser.

1. Köp eller prova Microsoft Defender för Slutpunkt idag. [Besök Microsoft Defender för Endpoint om du vill påbörja en kostnadsfri utvärderingsversion eller begära en offert](https://aka.ms/mdatp). 
2. Kontrollera att licenserna har etablerats korrekt. [Kontrollera licenstillståndet](production-deployment.md#check-license-state).
3. Konfigurera den dedikerade molninstansen av Microsoft Defender för Slutpunkt som global administratör eller säkerhetsadministratör. Se [Konfiguration av Microsoft Defender för slutpunkt: Klientorganisationskonfiguration](production-deployment.md#tenant-configuration).
4. Om slutpunkter (till exempel enheter) i organisationen använder en proxy för att komma åt Internet kan du gå till Microsoft Defender för [Konfiguration av slutpunkt: Nätverkskonfiguration](production-deployment.md#network-configuration).
 
I det här läget är du redo att ge åtkomst till dina säkerhetsadministratörer och säkerhetsoperatorer som kommer att använda Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Microsoft Defender Säkerhetscenter kallas ibland för Microsoft Defender för Endpoint-portalen. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Bevilja åtkomst till Microsoft Defender Säkerhetscenter

I Microsoft Defender Säkerhetscenter [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () får du åtkomst till och konfigurerar funktioner i Microsoft Defender för Endpoint. Mer information finns i [Översikt över Microsoft Defender Säkerhetscenter.](use.md)

Behörigheter till Microsoft Defender Säkerhetscenter kan beviljas med hjälp av grundläggande behörigheter eller rollbaserad åtkomstkontroll (RBAC). Vi rekommenderar att du använder RBAC så att du har mer detaljerad kontroll över behörigheter.

1. Planera rollerna och behörigheterna för dina säkerhetsadministratörer och säkerhetsoperatorer. Se [Rollbaserad åtkomstkontroll](prepare-deployment.md#role-based-access-control).
2. Konfigurera och konfigurera RBAC. Vi rekommenderar att du använder [Intune](/mem/intune/fundamentals/what-is-intune) för att konfigurera RBAC, särskilt om organisationen använder en kombination av Windows 10-, macOS-, iOS- och Android-enheter. Se [konfigurera RBAC med Intune](/mem/intune/fundamentals/role-based-access-control).<br/>
   Om din organisation kräver en annan metod än Intune väljer du något av följande alternativ:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Avancerad grupprinciphantering](/microsoft-desktop-optimization-pack/agpm)
    - [Administrationscenter för Windows](/windows-server/manage/windows-admin-center/overview)
3. Bevilja åtkomst till Microsoft Defender Säkerhetscenter. (Behöver du hjälp? Se [Hantera portalåtkomst med RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurera proxy- och internetanslutningsinställningar för enheter

Om du vill aktivera kommunikation mellan dina enheter och Microsoft Defender för Endpoint konfigurerar du proxy- och Internetinställningar. Följande tabell innehåller länkar till resurser som du kan använda för att konfigurera proxy- och Internetinställningar för olika operativsystem och funktioner:

|Kapaciteter  | Operativsystem | Resurser |
|:----|:----|:---|
|[Identifiering och svar av slutpunkt](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 eller senare](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Konfigurera datorproxy och internetanslutningsinställningar](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Konfigurera proxy- och Internetanslutningsinställningar](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender för slutpunkt i macOS: Nätverksanslutningar](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 eller senare](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)  |[Microsoft Defender för slutpunkt på Mac: Nätverksanslutningar](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender för slutpunkt i Linux: Nätverksanslutningar](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört **förberedelsefasen** av [migreringen från Symantec till Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!
- [Fortsätt att konfigurera Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-setup.md).
