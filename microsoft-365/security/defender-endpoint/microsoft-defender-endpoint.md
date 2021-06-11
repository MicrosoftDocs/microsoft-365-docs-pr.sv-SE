---
title: Microsoft Defender för Endpoint
description: Microsoft Defender för Endpoint är en plattform för säkerhet för företagsslutpunkter som hjälper dem att försvara sig mot avancerade fortlöpande hot.
keywords: introduktion till Microsoft Defender för Endpoint, introduktion till Microsoft Defender för Endpoint, cybersäkerhet, avancerade fortlöpande hot, företagssäkerhet, sensor för maskinbeteende, molnsäkerhet, analys, hotinformation, minskning av hotytan, nästa generations skydd, automatisk undersökning och åtgärd, microsoft threat-experter, säker poäng, avancerad sökning, Microsoft 365 Defender, cyberhotssäkerhet
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
ms.openlocfilehash: 23a9b99a71d700bdeddb3398c592eeb778ceef23
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879270"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Mer information om Windows 10 Enterprise Edition-funktioner finns i [Windows 10 Enterprise utgåva.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender för Endpoint är en säkerhetsplattform för företag som utformats för att hjälpa företagsnätverk att förhindra, upptäcka, undersöka och hantera avancerade hot.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender för Endpoint använder följande kombination av teknik som är inbyggd i Windows 10 och Microsofts robusta molntjänst:

-   **Slutpunktsbeteendesensorer:** Inbäddade i Windows 10 samlar dessa sensorer in och processbeteendesignaler från operativsystemet och skickar sensordata till din privata, isolerade molninstans av Microsoft Defender för Slutpunkt.


-   Molnsäkerhetsanalyser: Utnyttja stora data, enhetsinlärning och unik Microsoft-optisk användning över Windows-ekosystem, företagmolnprodukter (till exempel Office 365) och onlinetillgångar, funktionssignaler översättas till insikter, identifieringar och rekommenderade svar på avancerade hot.

-   **Hotinformation:** Genereras av Microsoft-säkerhetsteam, säkerhetsteam och utökas av hotinformation som tillhandahålls av partner, och med hjälp av hotinformation kan Defender för Endpoint identifiera attackersverktyg, tekniker och procedurer, och generera aviseringar när de observeras i insamlade sensordata.

<center><h2>Microsoft Defender för Slutpunkt</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Hot & sårbarhetshantering</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Minskning av attackytan</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Nästa generations skydd</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Identifiering och svar av slutpunkter</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Automatiserad undersökning och åtgärder</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft Hotexperter</b></a></center></td>
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

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Nyheter i Microsoft Defender för slutpunkt.](whats-new-in-microsoft-defender-atp.md)
> - Microsoft Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen. Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

<a name="tvm"></a>

**[Hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)**<br>
Den inbyggda funktionen använder en spelförändrande riskbaserad metod för identifiering, prioritering och åtgärd av svagheter och felkonfigurationer i slutpunkten. 

<a name="asr"></a>

**[Minskning av attackytan](overview-attack-surface-reduction.md)**<br>
Minskningsuppsättningen för attackytan ger den första försvarslinjen i högen. Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kan funktionerna motarbeta angrepp och användning. Den här uppsättningen funktioner omfattar även [nätverksskydd och](network-protection.md) [webbskydd, som](web-protection-overview.md)reglerar åtkomsten till skadliga IP-adresser, domäner och URL-adresser. 

<a name="ngp"></a>

**[Nästa generations skydd](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.

<a name="edr"></a>

**[Identifiering och svar för slutpunkt](overview-endpoint-detection-response.md)**<br>
Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och hantera avancerade hot som kan ha gjort det förbi de två första säkerhetspelarna. [Avancerad sökning](advanced-hunting-overview.md) är ett frågebaserat verktyg för hotsökning som gör att du proaktivt kan hitta överträdelser och skapa anpassade identifieringar.

<a name="ai"></a>

**[Automatiserad undersökning och åtgärder](automated-investigations.md)**<br>
I kombination med att snabbt kunna svara på avancerade attacker erbjuder Microsoft Defender för Endpoint funktioner för automatisk undersökning och åtgärder som hjälper till att minska mängden aviseringar i minuter i skala. 

<a name="ss"></a>

**[Microsoft Secure Score för enheter](tvm-microsoft-secure-score-devices.md)**<br>

Defender för Endpoint innehåller Microsoft Secure Score för enheter som hjälper dig att dynamiskt bedöma företagsnätverkets säkerhetstillstånd, identifiera oskyddade system och vidta rekommenderade åtgärder för att förbättra organisationens övergripande säkerhet.

<a name="mte"></a>

**[Microsoft Hotexperter](microsoft-threat-experts.md)**<br>
Med Microsoft Defender för Endpoints nya tjänst för att hantera hot kan du proaktiva produkter, prioritera samt ytterligare kontext och insikter som ytterligare ger säkerhetscenter (SOCs) möjlighet att identifiera och reagera på hot snabbt och korrekt.

>[!IMPORTANT]
>Defender för Endpoint-kunder måste söka efter Microsoft Hotexperter-tjänsten för hanterade hot för att få proaktiva riktade attackmeddelanden och samarbeta med experter på begäran. Experter på begäran är en tilläggstjänst. Riktade attackmeddelanden inkluderas alltid när du har godkänts för Microsoft Hotexperter av hot efter hot.<p>
><p>Om du inte är registrerad ännu och vill uppleva fördelarna går du till fliken <b>Allmänna Inställningar</b> > <b></b> > <b>som du</b> > <b>Microsoft Hotexperter</b> använda. När du accepterat, får du fördelarna med riktade attackmeddelanden och påbörja en 90-dagars utvärderingsversion av experter på begäran. Kontakta din Microsoft-representant för att få en fullständig prenumeration för Experter på begäran.

<a name="apis"></a>

**[Centraliserad konfiguration och administration, API:er](management-apis.md)**<br>
Integrera Microsoft Defender för Slutpunkt i dina befintliga arbetsflöden.

<a name="mtp"></a>

**[Integrering med Microsoft-lösningar](threat-protection-integration.md)** <br>
Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar, bland annat:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender för Office
- Skype för företag

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Med Microsoft 365 Defender skapar Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit efter intrång som inbyggt integreras i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt reagera på avancerade attacker.


## <a name="related-topic"></a>Relaterat ämne
[Microsoft Defender för Slutpunkt hjälper till att identifiera avancerade hot](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
