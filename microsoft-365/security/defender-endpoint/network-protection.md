---
title: Använda nätverksskydd för att förhindra anslutningar till dåliga webbplatser
description: Skydda nätverket genom att hindra användare från att komma åt kända skadliga och misstänkta nätverksadresser
keywords: Nätverksskydd, sårbarheter, skadlig webbplats, ip, domän, domäner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844268"
---
# <a name="protect-your-network"></a>Skydda ditt nätverk

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Nätverksskydd hjälper till att minska enheternas attackytor från Internetbaserade händelser. Det förhindrar anställda att använda något program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet. Nätverksskydd utökar omfattningen av [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för att blockera all utgående HTTP-trafik som försöker ansluta till berykande källor med låg rykte (baserat på domän eller värdnamn).

Nätverksskydd stöds i alla Windows, med början från Windows 10 version 1709. Nätverksskydd stöds ännu inte på andra operativsystem, men webbskydd stöds med den nya Microsoft Edge baserat på Chromium. Mer information finns i [Webbskydd](web-protection-overview.md).

Nätverksskydd utökar skyddet i [webbskyddet](web-protection-overview.md) till operativsystemets nivå. Det ger webbskyddsfunktioner i Microsoft Edge till andra webbläsare som stöds och program som inte är webbläsarbaserade. Dessutom tillhandahåller nätverksskydd synlighet och blockering av indikatorer på intrång (IOCs) när de används med identifiering och [svar av slutpunkter.](overview-endpoint-detection-response.md) Till exempel fungerar nätverksskydd med dina [anpassade indikatorer](manage-indicators.md).

Mer information om hur du aktiverar nätverksskydd finns [i Aktivera nätverksskydd.](enable-network-protection.md) Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.

> [!TIP]
> Se testfältwebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur nätverksskyddet fungerar.

Nätverksskyddet fungerar bäst med [Microsoft Defender](microsoft-defender-endpoint.md)för Endpoint , som ger dig detaljerad rapportering om sårbarhetsskyddshändelser och -block som en del av scenarier [för aviseringsundersökning.](investigate-alerts.md)

När nätverksskydd blockerar en anslutning visas ett meddelande från Åtgärdscenter. Ditt säkerhetsteam kan [anpassa meddelandet](customize-attack-surface-reduction.md#customize-the-notification) med organisationens information och kontaktinformation. Dessutom kan regler för att minska attackytan aktiveras och anpassas så att de passar vissa tekniker att övervaka.

Du kan också använda [granskningsläge](audit-windows-defender.md) för att utvärdera hur nätverksskydd skulle påverka organisationen om det var aktiverat.

## <a name="requirements"></a>Krav

Nätverksskydd kräver Windows 10 Pro företag och Microsoft Defender Antivirus i realtidsskydd.

| Windows version | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 version 1709 eller senare <p>Windows Server 1803 eller senare | [Microsoft Defender Antivirus realtidsskydd och](configure-real-time-protection-microsoft-defender-antivirus.md) moln [levererat skydd måste](enable-cloud-protection-microsoft-defender-antivirus.md) vara aktiverat |

När du har aktiverat tjänsterna kan du behöva konfigurera nätverket eller brandväggen så att anslutningarna mellan tjänsterna och dina enheter tillåts (kallas även slutpunkter).  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Granska nätverksskyddshändelser i Microsoft Defender för Endpoint Säkerhetscenter

Microsoft Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning.](investigate-alerts.md)

Du kan fråga Microsoft Defender efter slutpunktsdata med hjälp av [avancerad sökning.](advanced-hunting-overview.md) Om du använder granskningsläge [kan du](audit-windows-defender.md)använda avancerad sökning för att se hur inställningarna för nätverksskydd skulle påverka din miljö om de var aktiverade.

Här är en exempelfråga

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Granska nätverksskyddshändelser i Windows Loggboken

Du kan granska Windows om du vill se händelser som skapas när nätverksskydd blockerar (eller granskar) åtkomst till en skadlig IP eller domän:

1. [Kopiera XML-filen direkt.](event-views.md)

2. Välj **OK**.

Den här proceduren skapar en anpassad vy som filtrerar för att bara visa följande händelser relaterade till nätverksskydd:

| Händelse-ID | Beskrivning |
|:---|:---|
| 5007 | Händelse när inställningar ändras |
| 1125 | Händelse när nätverksskydd aktiveras i granskningsläge |
| 1126 | Händelse när nätverksskyddet utbrandar i blockläge |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Att tänka på Windows virtuella skrivbordet som Windows 10 Enterprise flersession

Tänk på Windows 10 Enterprise funktioner för flera användare:

1. Nätverksskydd är en funktion för hela enheten och kan inte riktas till specifika användarsessioner.

2. Principer för filtrering av webbinnehåll är också enhetsomfattande.

3. Om du behöver skilja mellan användargrupper kan du skapa separata Windows för virtuella skrivbord som värd för pooler och tilldelningar.

4. Testa nätverksskydd i granskningsläge för att bedöma dess beteende innan det lanseras. 

5. Överväg att ändra distributionen om du har ett stort antal användare eller ett stort antal sessioner för flera användare.

### <a name="alternative-option-for-network-protection"></a>Alternativt alternativ för nätverksskydd

För Windows 10 Enterprise flersession 1909 och uppåt, och används i Windows Virtual Desktop i Azure, kan nätverksskydd för Microsoft Edge aktiveras med följande metod:

1. Använd [Aktivera nätverksskydd och](enable-network-protection.md) följ instruktionerna för att tillämpa principen.

2. Utför följande PowerShell-kommando: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Felsökning av nätverksskydd

På grund av miljön där Network Protection körs kanske Microsoft inte kan identifiera proxyinställningar för operativsystemet. I vissa fall kan inte nätverksskyddsklienter nå molntjänsten. För att lösa anslutningsproblem bör kunder med E5-licenser konfigurera någon av följande Defender-registernycklar:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Relaterade artiklar

- [Utvärdera |](evaluate-network-protection.md) Utför ett snabbt scenario som visar hur funktionen fungerar och vilka händelser som normalt skulle skapas.

- [Aktivera nätverksskydd](enable-network-protection.md) | Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.
