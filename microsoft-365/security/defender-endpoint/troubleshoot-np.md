---
title: Felsöka problem med nätverksskydd
description: Resurser och exempelkod för att felsöka problem med nätverksskydd i Microsoft Defender för slutpunkt.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844064"
---
# <a name="troubleshoot-network-protection"></a>Felsöka nätverksskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


När du använder [nätverksskydd](network-protection.md) kan det uppstå problem, till exempel:

- Nätverksskydd blockerar en webbplats som är säker (falsk positiv åtkomst)
- Nätverksskydd blockerar inte misstänkta eller kända skadliga webbplatser (falskt negativt)

Det finns fyra steg för att felsöka dessa problem:

1. Bekräfta förutsättningarna
2. Använda granskningsläge för att testa regeln
3. Lägga till undantag för den angivna regeln (för falska positiva resultat)
4. Skicka supportloggar

## <a name="confirm-prerequisites"></a>Bekräfta förutsättningarna

Nätverksskydd fungerar bara på enheter med följande villkor:

>[!div class="checklist"]
> - Slutpunkter körs med Windows 10 Pro Enterprise- eller Enterprise-version, version 1709 eller senare.
> - Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen. [Se vad som händer när du använder en antiviruslösning som inte är en Microsoft-lösning.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [Realtidsskydd är](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) aktiverat.
> - [Moln levererat skydd är](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) aktiverat.
> - Granskningsläge är inte aktiverat. Använd [grupprincip för](enable-network-protection.md#group-policy) att ange att regeln ska **inaktiveras** (värde: **0**).

## <a name="use-audit-mode"></a>Använda granskningsläge

Du kan aktivera nätverksskydd i granskningsläge och sedan besöka en webbplats som vi har skapat för att nedgradera funktionen. Alla webbplatsanslutningar tillåts av nätverksskydd, men en händelse loggas för att ange vilken anslutning som skulle ha blockerats om nätverksskyddet var aktiverat.

1. Ange nätverksskydd som **Granskningsläge**.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Utför den anslutningsaktivitet som orsakar ett problem (försök till exempel gå till webbplatsen eller anslut till den IP-adress du vill eller inte vill blockera).

3. [Granska händelseloggarna för nätverksskydd](network-protection.md#review-network-protection-events-in-windows-event-viewer) för att se om funktionen skulle ha blockerat anslutningen om den hade angetts till **Aktiverad.**
   
   Om nätverksskyddet inte blockerar en anslutning som du förväntar dig bör den blockeras, aktivera funktionen.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Rapportera ett falskt positivt eller falskt negativt värde

Om du har testat funktionen med demowebbplatsen och med granskningsläge och nätverksskydd arbetar med förkonfigurerade scenarier, men inte fungerar som förväntat för en viss anslutning, kan du använda det webbaserade insändningsformuläret för [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) om du vill rapportera ett falskt negativt eller falskt positivt resultat för nätverksskydd. Med en E5-prenumeration kan du också [skicka en länk till eventuell associerad avisering](alerts-queue.md).

Se [Adress: falska positiva/negativa i Microsoft Defender för Slutpunkt](defender-endpoint-false-positives-negatives.md).

## <a name="exclude-website-from-network-protection-scope"></a>Undanta webbplatsen från nätverkets skyddsområde

Om du vill tillåta att webbplatsen blockeras (falsk positiv inställning) lägger du till dess URL-adress i [listan med betrodda platser.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/) Webbresurser från den här listan kringgår kontrollen av nätverksskydd.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Samla in diagnostikdata för inskickade filer

När du rapporterar ett problem med nätverksskydd uppmanas du att samla in och skicka diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem.

1. Öppna en upphöjd kommandotolk och ändra i Windows Defender katalog:

   ```console
   cd c:\program files\windows defender
   ```

2. Kör det här kommandot för att generera diagnostikloggarna:

   ```console
   mpcmdrun -getfiles
   ```

3. Bifoga filen i inskickat formulär. Som standard sparas diagnostikloggar på `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Lösa anslutningsproblem med nätverksskydd (för E5-kunder)

På grund av miljön där nätverksskyddet körs kan Microsoft inte se dina proxyinställningar för operativsystemet. I vissa fall kan inte nätverksskyddsklienter nå molntjänsten. Lös anslutningsproblem med nätverksskydd genom att konfigurera en av följande registernycklar så att nätverksskyddet blir medvetna om proxykonfigurationen:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---ELLER---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

Du kan konfigurera registernyckeln med hjälp av PowerShell, Microsoft Endpoint Manager eller grupprincip. Här är några resurser som kan vara till hjälp:
- [Arbeta med registernycklar](/powershell/scripting/samples/working-with-registry-keys)
- [Konfigurera anpassade klientinställningar för Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Använda grupprincipinställningar för att hantera Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Se även

- [Nätverksskydd](network-protection.md)
- [Utvärdera nätverksskydd](evaluate-network-protection.md)
- [Aktivera nätverksskydd](enable-network-protection.md)
- [Adressera falska positiva/negativa tal i Defender för Slutpunkt](defender-endpoint-false-positives-negatives.md)
