---
title: Rapportera och felsöka Microsoft Defender för SLUTPUNKT ASR-regler
description: I det här avsnittet beskrivs hur du rapporterar och felsöker Microsoft Defender för Slutpunkt ASR-regler
keywords: Minskningsregler för attackytan, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, prevention av smitta, microsoft defender för slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246259"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Rapportera och felsöka Microsoft Defender för ATP ASR-regler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Det Microsoft 365 säkerhetscentret är det nya gränssnittet för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur. Här kan du enkelt se säkerhetshälsa för din organisation, konfigurera enheter, användare och appar och få aviseringar om misstänkt aktivitet. Säkerhetscentret Microsoft 365 avsett för säkerhetsadministratörer och säkerhetsgrupper för att bättre kunna hantera och skydda organisationen. Besök säkerhetscentret Microsoft 365 på https://security.microsoft.com .
I Microsoft 365 säkerhetscenter erbjuder vi dig en fullständig titt på aktuella konfigurationer och händelser för ASR-regler på din resurs. Observera att dina enheter måste vara onboarded in i Microsoft Defender för Endpoint-tjänsten för att dessa rapporter ska fyllas i.
Här är en skärmbild från säkerhetscentret Microsoft 365 (under Rapporter **enheter Minska**  >    >  **attackytan).** På enhetsnivå väljer du **Konfiguration i** fönstret För att **minska attackytan.** Följande skärm visas, där du kan välja en specifik enhet och kontrollera dess enskilda konfiguration av ASR-regler.

:::image type="content" source="images/asrrulesnew.png" alt-text="Skärmen ASR-regler":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender för slutpunkt – avancerad sökning

En av de mest kraftfulla funktionerna i Microsoft Defender för Endpoint är avancerad sökning. Om du inte är bekant med avancerad sökning kan du referera till att [proaktivt leta efter hot med avancerad sökning.](advanced-hunting-overview.md)

Avancerad sökning är ett frågebaserat verktyg (Kusto Query Language) som du kan använda för att utforska upp till 30 dagar efter de registrerade (rådata) som MDE-slutpunktsidentifiering och svar (Identifiering och åtgärd på slutpunkt) samlar in från alla dina datorer. Genom avancerad sökning kan du proaktivt kontrollera händelser för att hitta intressanta indikatorer och enheter. Den flexibla åtkomsten till data hjälper till att undvika en fast uppgift om både kända och potentiella hot.

Genom avancerad sökning kan du extrahera ASR-regelinformation, skapa rapporter och få ingående information om kontexten för en viss ASR-regelgranskning eller blockhändelse.

ASR-regelhändelser är tillgängliga att köra frågor från tabellen DeviceEvents i avsnittet om avancerad sökning i Microsoft Defender Säkerhetscenter. Till exempel kan en enkel fråga som den nedan rapportera alla händelser som har ASR-regler som datakälla, under de senaste 30 dagarna, och summera dem med antalet ActionType, som i det här fallet är den faktiska kodnamnet för ASR-regeln.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Avancerad fråga om sökning":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="avancerad skärm för sökning":::

Med avancerad sökning kan du utforma frågorna efter dina önskemål, så att du kan se vad som händer, oavsett om du vill hitta något på en enskild dator eller om du vill extrahera insikter från hela miljön.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender för slutpunktsdatortidslinje

Ett alternativ till avancerad sökning, men med en smalare omfattning, är tidslinjen för Microsoft Defender för Endpoint-datorn. Du kan visa alla insamlade händelser för en enhet under de senaste sex månaderna i Microsoft Defender Säkerhetscenter genom att gå till listan Datorer, välja en viss dator och sedan klicka på fliken Tidslinje.

På bilden nedan visas en skärmbild av vyn Tidslinje över dessa händelser på en viss slutpunkt.  I den här vyn kan du filtrera händelselistan baserat på valfri händelsegrupp i fönstret till höger. Du kan också aktivera eller inaktivera flaggade och utförliga händelser när du visar aviseringar och bläddrar genom den historiska tidslinjen.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="tidslinje i Microsoft Defender Säkerhetscenter":::

## <a name="how-to-troubleshoot-asr-rules"></a>Felsöka ASR-regler?

Det första och mest direkta sättet är att kontrollera lokalt på en Windows-enhet, som ASR-regler aktiveras (och deras konfiguration) är att använda PowerShell-cmdlets.

Här är några andra informationskällor som kan Windows som hjälper dig felsöka påverkan på och åtgärd för ASR-regler.

### <a name="querying-which-rules-are-active"></a>Fråga vilka regler som är aktiva
Ett av de enklaste sätten att avgöra om ASR-regler redan är aktiverade, och är via en PowerShell-cmdlet, Get-MpPreference.
Här är ett exempel:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="skaffa mppreference-skript":::

Det finns flera ASR-regler aktiva, med olika konfigurerade åtgärder.

Om du vill visa informationen om ASR-regler ovan kan du använda egenskaperna **AttackSurfaceReductionRules_Ids** och/eller **AttackSurfaceReductionRules_Actions**.

Exempel:

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="exempel på hämta slutledning":::

Ovan visas alla ID:er för ASR-regler som har en annan inställning än 0 (Ej konfigurerad).

Nästa steg är att lista de faktiska åtgärderna (block eller granskning) som varje regel är konfigurerad med. 

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a>Frågeblockering och granskningshändelser
ASR-regelhändelser kan visas i Windows Defender loggen.

Du kommer åt det genom Windows Loggboken och bläddra till **Program-** och  >  **tjänstloggar Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="loggboken scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Skyddsloggar för Microsoft Defender Malware
Du kan också visa regelhändelser via det Microsoft Defender Antivirus dedikerade kommandoradsverktyget, som kallas , som kan användas för att hantera och konfigurera, och automatisera `*mpcmdrun.exe*` uppgifter vid behov.

Du hittar det här verktyget i *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Du måste köra den från en upphöjd kommandotolk (det vill säga kör som administratör).

Om du vill generera supportinformation skriver *duMpCmdRun.exe -getfiles*. Efter ett tag paketeras flera loggar till ett arkiv (MpSupportFiles.cab) och görs tillgängliga i *C:\ProgramData\Microsoft\Windows Defender\Support.*

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="skyddsloggar för skadlig programvara":::

Extrahera det arkivet så har du många filer tillgängliga för felsökning.

De mest relevanta filerna är följande:

- **MPOperationalEvents.txt** – Den här filen innehåller samma informationsnivå som finns i Loggboken Windows Defender filens driftlogg.
- **MPRegistry.txt** – I den här filen kan du analysera alla Windows Defender konfigurationer från det att supportloggarna har fångats in.
- **MPLog.txt** – Den här loggen innehåller mer utförlig information om alla åtgärder/åtgärder i Windows Defender.
