---
title: Microsoft Defender för slutpunkt för myndighetskunder i USA
description: Läs mer om kraven och funktionerna för Microsoft Defender för slutpunkt för kunder inom myndigheter i USA tillgängliga
keywords: myndigheter, gcc, hög, krav, funktioner, defender, defender atp, mdatp, slutpunkt, dod
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
ms.openlocfilehash: 1fd128a9b734606039438db1f6d9fbc36e93a3b9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199023"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender för slutpunkt för myndighetskunder i USA

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender för slutpunkt för kunder inom myndigheter i USA, inbyggda i US Azure Government-miljön, använder samma underliggande teknik som Defender för Slutpunkt i kommersiell Azure.

Det här erbjudandet är tillgängligt för kunder med GCC, GCC High och DoD och baseras på samma skydd, identifiering, undersökning och åtgärd som den kommersiella versionen. Det finns emellertid vissa skillnader i tillgängligheten för funktionerna för det här erbjudandet.

> [!NOTE]
> Om du är GCC-kund och använder Defender för Slutpunkt i kommersiellt bruk kan du läsa mer på de offentliga dokumentationssidorna.

## <a name="licensing-requirements"></a>Licenskrav
Microsoft Defender för endpoint för kunder inom myndigheter i USA kräver något av följande volymlicensieringserbjudanden från Microsoft:

### <a name="desktop-licensing"></a>Skrivbordslicensiering
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 för GCC High | Windows 10 Enterprise E5 för DOD
| | Microsoft 365 E5 för GCC High | 
| | Microsoft 365 G5 Säkerhet för GCC High | 
Microsoft Defender för slutpunkt – GCC | Microsoft Defender för Slutpunkt för GCC High | Microsoft Defender för Slutpunkt för DOD

### <a name="server-licensing"></a>Serverlicensiering
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender för Endpoint Server GCC | Microsoft Defender för Endpoint Server för GCC High | Microsoft Defender för Slutpunktsserver för DOD
Azure Defender för servrar | Azure Defender för servrar – myndigheter | Azure Defender för servrar – myndigheter

> [!NOTE]
> DoD licensing will only be available at DoD general availability.

<br>

## <a name="portal-urls"></a>URL-adresser för portal
Följande är URL-adresser för Microsoft Defender för Slutpunktsportalen för kunder inom myndigheter i USA:

Kundtyp | Url till portalen
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (FÖRHANDSVISNING) | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>Slutpunktsversioner

### <a name="standalone-os-versions"></a>Fristående OS-versioner
Följande os-versioner stöds:

OS-version | GCC | GCC High | DoD (FÖRHANDSVISNING)
:---|:---|:---|:---
Windows 10 – version 20H2 – (med [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 – version 2004 – (med [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 – version 1909 – (med [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 – version 1903 – (med [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 – version 1809 – (med [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10 – version 1803 – (med [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, version 1709 | ![Nej](images/svg/check-no.svg)<br>Obs! Stöds inte | ![Ja ](images/svg/check-yes.svg) med [KB4499147](https://support.microsoft.com/help/4499147)<br>Obs! [Inaktuell ,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)vänligen uppgradera | ![Nej](images/svg/check-no.svg)<br>Obs! Stöds inte
Windows 10, version 1703 och tidigare | ![Nej](images/svg/check-no.svg)<br>Obs! Stöds inte | ![Nej](images/svg/check-no.svg)<br>Obs! Stöds inte | ![Nej](images/svg/check-no.svg)<br>Obs! Stöds inte
Windows Server 2019 (med [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
macOS | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Android | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
iOS | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg

> [!NOTE]
> Där en korrigering har angetts måste den distribueras innan enhets onboarding för att kunna konfigurera Defender för Endpoint till rätt miljö.

> [!NOTE]
> Försöker du registrera Windows-enheter som är äldre än Windows 10 eller Windows Server 2019 med [hjälp av Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Du måste välja "Azure US Government" under "Azure [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)Cloud" om du [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) använder installationsguiden , eller om du använder en kommandorad eller ett skript [–](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) ange parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>OS-versioner när du använder Azure Defender för servrar
Följande OS-versioner stöds när du använder [Azure Defender för servrar:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

OS-version | GCC | GCC High | DoD (FÖRHANDSVISNING)
:---|:---|:---|:---
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br>

## <a name="required-connectivity-settings"></a>Nödvändiga anslutningsinställningar
Om en proxy eller brandvägg blockerar all trafik som standard och bara tillåter specifika domäner genom, lägger du till de domäner som visas i det nedladdningsbara bladet i listan med tillåtna domäner.

I följande nedladdningsbara kalkylblad visas tjänsterna och deras tillhörande URL:er som nätverket måste kunna ansluta till. Kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till url:erna, eller skapa *en* tillåta-regel specifikt för dem.

Kalkylblad med domänlista | Beskrivning
:-----|:-----
![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/> | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Mer information finns i Konfigurera [enhetsproxy och Internetanslutningsinställningar.](configure-proxy-internet.md)

> [!NOTE]
> Kalkylbladet innehåller även kommersiella WEBBADRESSer. Kontrollera att du har flikarna "US Gov". <br> När du filtrerar letar du efter poster som heter "US Gov" och ditt specifika moln under geografikolumnen.

<br>

## <a name="api"></a>API
I stället för offentliga URI:er som visas i vår [API-dokumentation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)måste du använda följande URI:er:

Slutpunktstyp | GCC | GCC High & DoD (PREVIEW)
:---|:---|:---
Inloggning | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender för Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>Funktionsparitet med kommersiell
Defender för Endpoint har inte fullständig paritet med det kommersiella erbjudandet. Även om vårt mål är att tillhandahålla alla kommersiella funktioner till våra kunder inom myndigheter i USA finns det en del funktioner som vi inte vill lyfta fram ännu.

Det här är de kända luckorna från februari 2021:

Funktionsnamn | GCC | GCC High | DoD (FÖRHANDSVISNING)
:---|:---|:---|:---
Automatiserad undersökning och åtgärd: Live-svar | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Automatiserad undersökning och åtgärd: Svar på Office 365-aviseringar | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
E-postaviseringar | ![Nej](images/svg/check-no.svg) Lanseras | ![Nej](images/svg/check-no.svg) Lanseras | ![Nej](images/svg/check-no.svg) Lanseras
Utvärderingslabb | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Hanterings- och API:er: Hälso- och efterlevnadsrapport för enheter | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Hantering och API:er: Integrering med produkter från tredje part | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Hantering och API:er: Streaming API | ![Ja](images/svg/check-yes.svg) | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Hanterings- och API:er: Rapport om skydd mot hot | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Hot & sårbarhetshantering | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Analys av hot | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Filtrering av webbinnehåll | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Cloud App Security | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
Integrationer: Microsoft Compliance Manager | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
Integrationer: Microsoft Defender för identitet | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
Integrationer: Microsoft Defender för Office 365 | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
Integrationer: Microsoft Endpoint DLP | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
Integrationer: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Microsoft Power Automate & Azure Logic-appar | ![Ja](images/svg/check-yes.svg) | ![Nej](images/svg/check-no.svg) Under utveckling | ![Nej](images/svg/check-no.svg) Under utveckling
Integrationer: Skype för företag/Teams | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Microsoft Threat Experts | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg | ![Nej](images/svg/check-no.svg) När det gäller teknisk logg
