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
ms.date: 03/08/2021
ms.openlocfilehash: b6069d392da1b8610d018908d172dc27044baffc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069378"
---
# <a name="protect-your-network"></a>Skydda ditt nätverk

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Nätverksskydd hjälper till att minska enheternas attackytor från Internetbaserade händelser. Det förhindrar anställda att använda något program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet. Nätverksskyddet utökar Omfattningen av [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för att blockera all utgående HTTP-trafik som försöker ansluta till ryktes beryka källor (baserat på domän eller värdnamn).

Nätverksskydd stöds i Windows från och med Windows 10, version 1709. 

Mer information om hur du aktiverar nätverksskydd finns [i Aktivera nätverksskydd.](enable-network-protection.md) Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.

> [!TIP]
> Se webbplatsen för Microsoft Defender ATP-testfält [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur nätverksskyddet fungerar.

Nätverksskyddet fungerar bäst med [Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)för Endpoint , som ger dig detaljerad rapportering om sårbarhetsskyddshändelser och -block som en del av scenarier [för aviseringsundersökning.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

När nätverksskydd blockerar en anslutning visas ett meddelande från Åtgärdscenter. Ditt säkerhetsteam kan [anpassa meddelandet](customize-attack-surface-reduction.md#customize-the-notification) med organisationens information och kontaktinformation. Dessutom kan regler för att minska attackytan aktiveras och anpassas så att de passar vissa tekniker att övervaka.

Du kan också använda [granskningsläge](audit-windows-defender.md) för att utvärdera hur nätverksskydd skulle påverka organisationen om det var aktiverat.

## <a name="requirements"></a>Krav

Nätverksskydd kräver Windows 10 Pro eller Enterprise och realtidsskydd i Microsoft Defender Antivirus.

| Windows-version | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 version 1709 eller senare <p>Windows Server 1803 eller senare | [Realtidsskydd och moln levererat skydd](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) [i](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) Microsoft Defender Antivirus måste vara aktiverat |

När du har aktiverat tjänsterna kan du behöva konfigurera nätverket eller brandväggen så att anslutningarna mellan tjänsterna och dina enheter tillåts (kallas även slutpunkter).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Granska nätverksskyddshändelser i Microsoft Defender för Endpoint Säkerhetscenter

Microsoft Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Du kan fråga Microsoft Defender efter Slutpunktsdata med hjälp av [Avancerad sökning](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection). Om du använder granskningsläge [kan du](audit-windows-defender.md)använda avancerad sökning för att se hur inställningarna för nätverksskydd skulle påverka din miljö om de var aktiverade.

Här är en exempelfråga

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Granska nätverksskyddshändelser i Windows Loggboken

Du kan granska Windows händelselogg för att se händelser som skapas när nätverksskydd blockerar (eller granskar) åtkomst till en skadlig IP eller domän:

1. [Kopiera XML-filen direkt.](event-views.md)

2. Välj **OK**.

Den här proceduren skapar en anpassad vy som filtrerar för att bara visa följande händelser relaterade till nätverksskydd:

| Händelse-ID | Beskrivning |
|:---|:---|
| 5007 | Händelse när inställningar ändras |
| 1125 | Händelse när nätverksskydd aktiveras i granskningsläge |
| 1126 | Händelse när nätverksskyddet utbrandar i blockläge |

## <a name="related-articles"></a>Relaterade artiklar

- [Utvärdera |](evaluate-network-protection.md) Utför ett snabbt scenario som visar hur funktionen fungerar och vilka händelser som normalt skulle skapas.

- [Aktivera nätverksskydd](enable-network-protection.md) | Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.
