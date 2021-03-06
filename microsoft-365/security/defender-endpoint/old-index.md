---
title: Skydd mot hot (Windows 10)
description: Microsoft Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar.
keywords: Skydd mot hot, Microsoft Defender för Endpoint, minskning av attackytan, nästa generations skydd, identifiering och åtgärd på slutpunkt, automatisk undersökning och svar, Microsoft Threat-experter, Microsoft Secure Score för enheter, avancerad sökning, sökning efter cyberhot, skydd mot webbhot
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841000"
---
# <a name="threat-protection"></a>Skydd mot hot
[Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. Defender för Endpoint skyddar slutpunkter mot cyberhot, identifierar avancerade attacker och databrott, automatiserar säkerhetstillbud och förbättrar säkerhetsriskerna.

> [!TIP]
> Gör det enkelt för användarna att få tillgång till molntjänster och lokala program och möjliggöra moderna hanteringsfunktioner för alla enheter. Mer information finns i Skydda [din fjärranslutna arbetsstyrka.](/enterprise-mobility-security/remote-work/) 

<center><h2>Microsoft Defender för Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Hot & hantering av säkerhetsrisker</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Minskning av attackytan</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Nästa generations skydd</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Identifiering och svar av slutpunkter</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Automatiserad undersökning och åtgärder</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft Hotexperter</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Centraliserad konfiguration och administration, API:er</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Hot och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)**<br>
Den inbyggda funktionen använder en spelförändrande riskbaserad metod för identifiering, prioritering och åtgärd av svagheter och felkonfigurationer i slutpunkten.

- [Översikt över & hantering av säkerhetsrisker hot](next-gen-threat-and-vuln-mgt.md)
- [Komma igång](tvm-prerequisites.md)
- [Komma åt din säkerhet](tvm-dashboard-insights.md)
- [Förbättra säkerheten och minska risken](tvm-security-recommendation.md)
- [Förstå sårbarhet på dina enheter](tvm-software-inventory.md)

<a name="asr"></a>

**[Minskning av attackytan](overview-attack-surface-reduction.md)**<br>
Minskningsuppsättningen för attackytan ger den första försvarslinjen i högen. Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.

- [Maskinvarubaserad avgränsning](overview-hardware-based-isolation.md)
- [Applikationskontroll](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Enhetskontroll](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Exploateringsskydd](exploit-protection.md)
- [Nätverksskydd](network-protection.md), [webbskydd](web-protection-overview.md)
- [Kontrollerad mappåtkomst](controlled-folders.md)
- [Nätverksbrandvägg](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regler för minskning av attackytan](attack-surface-reduction.md)

<a name="ngp"></a>

**[Nästa generations skydd](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.

- [Övervakning av beteende](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Molnbaserat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Maskininlärning](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL-skydd](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Automatiserad begränsat lägestjänst](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Identifiering och svar för slutpunkt](overview-endpoint-detection-response.md)**<br>
Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och svara på intrångsförsök och aktiva intrång. Med Avancerad sökning har du ett frågebaserat verktyg för hotsökning som gör att du proaktivt kan hitta överträdelser och skapa anpassade identifieringar.

- [Varningar](alerts-queue.md)
- [Historiska slutpunktsdata](investigate-machines.md#timeline)
- [Svarsreaktion](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Samlingen Collection Collection](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Hotinformation](threat-indicator-concepts.md)
- [Avancerad detonation- och analystjänst](respond-file-alerts.md#deep-analysis)
- [Avancerad jakt](advanced-hunting-overview.md)
    - [Anpassade identifieringar](overview-custom-detections.md)

<a name="ai"></a>

**[Automatiserad undersökning och åtgärder](automated-investigations.md)**<br>
Förutom att snabbt svara på avancerade attacker erbjuder Microsoft Defender för Endpoint funktioner för automatisk undersökning och åtgärder som hjälper till att minska mängden aviseringar i minuter i skala.

- [Automatiserad undersökning och åtgärder](automated-investigations.md)
- [Visa detaljer och resultat av automatiserade undersökningar](auto-investigation-action-center.md)
- [Visa och godkänna reparationsåtgärder](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft Hotexperter](microsoft-threat-experts.md)**<br>
Med Microsoft Defender för Endpoints nya tjänst för att hantera hot får du proaktiva produkter, prioritering samt ytterligare kontext och insikter. Microsoft Hotexperter ytterligare möjligheter för säkerhetscenter (SOCs) att identifiera och reagera på hot snabbt och korrekt.

- [Riktad attackavisering](microsoft-threat-experts.md)
- [Experter på begäran](microsoft-threat-experts.md)
- [Konfigurera den hanterade Microsoft 365 i Defender](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Centraliserad konfiguration och administration, API:er](management-apis.md)**<br>
Integrera Microsoft Defender för Slutpunkt i dina befintliga arbetsflöden.
- [Introduktioner](onboard-configure.md)
- [API- och SIEM-integrering](configure-siem.md)
- [Exponerade API:er](apis-intro.md)
- [Rollbaserad åtkomstkontroll (RBAC)](rbac.md)
- [Rapportering och trender](threat-protection-reports.md)

<a name="integration"></a>
**[Integrering med Microsoft-lösningar](threat-protection-integration.md)** <br>
 Microsoft Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar, bland annat:
- Intune
- Microsoft Defender för Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype för företag
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Med Microsoft 365 Defender skapar Microsoft Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit efter intrång som integreras inbyggt i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt svara på avancerade attacker.
