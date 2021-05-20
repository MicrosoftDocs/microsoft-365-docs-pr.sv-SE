---
title: Microsoft Defender för Endpoint för myndighetskunder i USA
description: Lär dig mer om Microsoft Defender för slutpunkt för amerikanska myndigheters kunders krav och funktioner som är tillgängliga
keywords: myndighet, gcc, hög, krav, funktioner, försvarare, Microsoft Defender för slutpunkt, slutpunkt, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572675"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender för Endpoint för myndighetskunder i USA

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender för punkt för amerikanska myndighets kunder, som är byggda i Azure US Government-miljön, använder samma underliggande teknik som Defender för punkt i Azure Commercial.

Detta erbjudande är tillgängligt för GCC-, GCC High- och DoD-kunder och baseras på samma förebyggande, identifiering, undersökning och reparation som den kommersiella versionen. Det finns dock vissa skillnader i tillgängligheten för funktioner för det här erbjudandet.

> [!NOTE]
> Om du är GCC kund som använder Defender for Endpoint in Commercial, se de offentliga dokumentationssidorna.

## <a name="licensing-requirements"></a>Licensieringskrav
Microsoft Defender för slutpunkt för amerikanska myndighetskunder kräver något av följande Microsoft-volymlicensieringserbjudanden:

### <a name="desktop-licensing"></a>Licensiering av stationära datorer
GCC | GCC hög | Dod
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 för GCC Hög | Windows 10 Enterprise E5 för DOD
| | Microsoft 365 E5 för GCC High | Microsoft 365 G5 för DOD
| | Microsoft 365 G5 Säkerhet för GCC hög | Microsoft 365 G5 Säkerhet för DOD
Microsoft Defender för slutpunkt – GCC | Microsoft Defender för slutpunkt för GCC hög | Microsoft Defender för slutpunkt för DOD

### <a name="server-licensing"></a>Serverlicensiering
GCC | GCC hög | Dod
:---|:---|:---
Microsoft Defender för slutpunktsserver GCC | Microsoft Defender för slutpunktsserver för GCC hög | Microsoft Defender för slutpunktsserver för DOD
Azure Defender för servrar | Azure Defender för servrar - Regeringen | Azure Defender för servrar - Regeringen

<br />

## <a name="portal-urls"></a>Url:er för portaler
Följande är url:erna för Microsoft Defender för Slutpunktsportalen för amerikanska myndighetskunder:

Kundtyp | Portal URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC hög | https://securitycenter.microsoft.us
Dod | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Slutpunktsversioner

### <a name="standalone-os-versions"></a>Fristående OS-versioner
Följande os-versioner stöds:

OS-version | GCC | GCC hög | Dod
:---|:---|:---|:---
Windows 10, version 20H2 (med [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 2004 (med [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 1909 (med [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 1903 (med [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 1809 (med [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 version 1803 (med [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 1709 | ![Nej](images/svg/check-no.svg)<br />Obs: Stöds inte | ![Ja ](images/svg/check-yes.svg) med [KB4499147](https://support.microsoft.com/help/4499147)<br />Obs: [Inaktuell](/lifecycle/announcements/revised-end-of-service-windows-10-1709), vänligen uppgradera | ![Nej](images/svg/check-no.svg)<br />Obs: Stöds inte
Windows 10, version 1703 och tidigare | ![Nej](images/svg/check-no.svg)<br />Obs: Stöds inte | ![Nej](images/svg/check-no.svg)<br />Obs: Stöds inte | ![Nej](images/svg/check-no.svg)<br />Obs: Stöds inte
Windows Server 2019 (med [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Företag | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
macOS (olika) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Android | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning
iOS | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning

> [!NOTE]
> Om en korrigeringsfil anges måste den distribueras före enhets onboarding för att konfigurera Defender för punkt till rätt miljö.

> [!NOTE]
> Försöker du registrera Windows enheter som är äldre än Windows 10 eller Windows Server 2019 med [Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Du måste välja "Azure US Government" under "Azure Cloud" om du använder [installationsguiden](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard), eller om du använder [en kommandorad](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) eller ett [skript](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) - ställ in parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>OS-versioner när du använder Azure Defender för servrar
Följande os-versioner stöds när du använder [Azure Defender för servrar:](/azure/security-center/security-center-wdatp)

OS-version | GCC | GCC hög | Dod
:---|:---|:---|:---
Windows Server 2019 | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Nödvändiga anslutningsinställningar
Om en proxy eller brandvägg blockerar all trafik som standard och endast tillåter vissa domäner, lägger du till domänerna som visas på det nedladdningsbara bladet i listan med tillåtna domäner.

I följande nedladdningsbara kalkylblad visas tjänsterna och tillhörande webbadresser som nätverket måste kunna ansluta till. Kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som skulle neka åtkomst till dessa webbadresser eller skapa en *tillståndsregel* specifikt för dem.

Kalkylblad med domäner lista | Beskrivning
:-----|:-----
![Tumbild för kalkylbladet Microsoft Defender för url:er för slutpunkter](images/mdatp-urls.png)<br/> | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br /><br />[Ladda ner kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Mer information finns i Konfigurera inställningar [för enhetsproxy och Internet-anslutning](configure-proxy-internet.md).

> [!NOTE]
> Kalkylbladet innehåller också kommersiella webbadresser, se till att du kontrollerar flikarna "US Gov".
> 
> När du filtrerar letar du efter posterna märkta som "US Gov" och ditt specifika moln under geografikolumnen.

### <a name="service-backend-ip-ranges"></a>IP-intervall för servicebackend

Om nätverksenheterna inte stöder DNS-baserade regler använder du IP-intervall i stället.

Defender for Endpoint för amerikanska myndighets kunder är byggd i Azure US Government-miljön, distribuerad i följande regioner:

- AzureCloud.usgovtexas (engelska)
- AzureCloud.usgovvirginia (engelska)

Du hittar Azure IP-intervallen i [Azure IP Ranges and Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Som en molnbaserad lösning kan IP-adressintervallen ändras. Vi rekommenderar att du går över till DNS-baserade regler.

<br />

## <a name="api"></a>Application Programming Interface
I stället för de offentliga URI:er som anges i vår [API-dokumentation](apis-intro.md)måste du använda följande URI: er:

Typ av slutpunkt | GCC | GCC Hög & dod
:---|:---|:---
logga in | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender för API:et för slutpunkter | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM (på alla) | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Funktionsparitet med kommersiell
Defender for Endpoint för amerikanska myndigheters kunder har inte fullständig paritet med det kommersiella erbjudandet. Även om vårt mål är att leverera alla kommersiella funktioner och funktionalitet till våra amerikanska regeringskunder, finns det vissa funktioner som ännu inte är tillgängliga som vi vill lyfta fram.

Dessa är de kända luckorna:

Funktionsnamn | GCC | GCC hög | Dod
:---|:---|:---|:---
Hantering och API:er: API för direktuppspelning | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Filtrering av webbinnehåll | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) Varningar <br /> ![Nej](images/svg/check-no.svg) Incidenter & Rådata: Under utveckling | ![Ja](images/svg/check-yes.svg) Varningar <br /> ![Nej](images/svg/check-no.svg) Incidenter & Rådata: Under utveckling
Integrationer: Microsoft Cloud App Security | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Compliance Manager | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Defender för identitet | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Endpoint DLP | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Integrationer: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Microsoft Hotexperter | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning | ![Nej](images/svg/check-no.svg) På teknisk eftersläpning
