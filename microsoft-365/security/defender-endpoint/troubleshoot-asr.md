---
title: Felsöka problem med minskningsregler för attackytan
description: Resurser och exempelkod för att felsöka problem med minskningsregler för attackytan i Microsoft Defender för Slutpunkt.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9ff00c706b0fb336c178e227b1cb33eff9e9ebbc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935227"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Felsöka minskningsregler för attackytor

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


När du använder [minskningsregler för attackytan](attack-surface-reduction.md) kan du få problem, till exempel:

- En regel blockerar en fil, en process eller utför någon annan åtgärd som den inte ska utföra (falsk positiv inställning)

- En regel fungerar inte enligt beskrivningen eller blockerar inte en fil eller process som den ska (falskt negativt)

Det finns fyra steg för att felsöka dessa problem:

1. [Bekräfta förutsättningarna](#confirm-prerequisites)

2. [Använda granskningsläge för att testa regeln](#use-audit-mode-to-test-the-rule)

3. [Lägga till undantag för den angivna regeln](#add-exclusions-for-a-false-positive) (för falska positiva resultat)

4. [Skicka supportloggar](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Bekräfta förutsättningarna

Minskning av attackytan fungerar bara på enheter med följande villkor:

- Slutpunkter kör Windows 10 Enterprise, version 1709 (kallas även Fall Creators Update).

- Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen. [Om du använder någon annan antivirusapp inaktiveras microsoft Defender AV.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

- [Realtidsskydd är](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) aktiverat.

- Granskningsläget är inte aktiverat. Använd grupprincip för att ställa in regeln på **Inaktiverad** (värde: **0**) enligt beskrivningen i [Aktivera minskningsregler för attackytor.](enable-attack-surface-reduction.md)

Om samtliga krav har uppfyllts går du vidare till nästa steg och testar regeln i granskningsläge.

## <a name="use-audit-mode-to-test-the-rule"></a>Använda granskningsläge för att testa regeln

Du kan besöka webbplatsen med Windows Defender Test på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att minskningsregler för attackytor vanligtvis fungerar för förkonfigurerade scenarier och processer på en enhet, eller så kan du använda granskningsläge, vilket endast tillåter rapporteringsregler.

Följ de här [anvisningarna i Använd demoverktyget](evaluate-attack-surface-reduction.md) för att se hur minskningsregler för attackytor fungerar för att testa den specifika regel som du stöter på problem med.

1. Aktivera granskningsläge för den regel som du vill testa. Använd grupprincip för att ställa in regeln på **Granskningsläge (värde:** **2**) enligt beskrivningen i [Aktivera minskningsregler för attackytan.](enable-attack-surface-reduction.md) Granskningsläget tillåter att regeln rapporterar filen eller processen, men den kan fortfarande köras.

2. Utföra den aktivitet som orsakar ett problem (öppna eller kör till exempel den fil eller process som ska blockeras men som tillåts).

3. [Granska händelseloggarna för att minska attackytan](attack-surface-reduction.md) för att se om regeln skulle ha blockerat filen eller processen om regeln hade angetts till **Aktiverad.**

Om en regel inte blockerar en fil eller process som du förväntar dig bör den blockeras, kontrollerar du först om granskningsläge är aktiverat.

Granskningsläge kan ha aktiverats för testning av en annan funktion eller av ett automatiserat PowerShell-skript och kan ha inaktiverats när testerna har slutförts.

Om du har testat regeln med demoverktyget och med granskningsläge och minskningsregler för attackytor arbetar på förkonfigurerade scenarier, men regeln inte fungerar som förväntat, går du till något av följande avsnitt beroende på din situation:

1. Om minskningsregeln för attackytan blockerar något som den inte borde blockera (kallas även falsk positiv inställning) kan du först lägga till en exkluderingsregel för [attackytan.](#add-exclusions-for-a-false-positive)

2. Om minskningsregeln för attackytan inte blockerar något som den ska blockera (kallas även falskt negativt) kan du fortsätta direkt till det sista steget, samla in diagnostikdata och skicka problemet [till oss.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>Lägga till undantag för falska positiva resultat

Om minskningsregeln för attackytan blockerar något som den inte borde blockera (kallas även falsk positiv inställning) kan du lägga till undantag för att förhindra minskningsregler för attackytan från att utvärdera de undantagna filerna eller mapparna.

Mer information om hur du lägger till ett undantag finns [i Anpassa minskning av attackytan](customize-attack-surface-reduction.md).

>[!IMPORTANT]
>Du kan ange att enskilda filer och mappar ska undantas, men du kan inte ange enskilda regler.
>Det innebär att filer eller mappar som är undantagna undantas från alla ASR-regler.

## <a name="report-a-false-positive-or-false-negative"></a>Rapportera ett falskt positivt eller falskt negativt värde

Använd det [webbaserade insändningsformuläret](https://www.microsoft.com/wdsi/filesubmission) i Windows Defender Security Intelligence om du vill rapportera ett falskt negativt eller falskt värde för nätverksskydd. Med en Windows E5-prenumeration kan du också [skicka en länk till eventuell associerad avisering](alerts-queue.md).

## <a name="collect-diagnostic-data-for-file-submissions"></a>Samla in diagnostikdata för inskickade filer

När du rapporterar ett problem med minskningsregler för attackytan uppmanas du att samla in och skicka in diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem.

1. Öppna en upphöjd kommandotolk och ändra till Windows Defender-katalogen:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Kör det här kommandot för att generera diagnostikloggarna:

   ```console
   mpcmdrun -getfiles
   ```

3. Som standard sparas de i `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . Bifoga filen i inskickat formulär.

## <a name="related-articles"></a>Relaterade artiklar

- [Regler för minskning av attackytan](attack-surface-reduction.md)

- [Aktivera regler för minskning av attackytan](enable-attack-surface-reduction.md)

- [Utvärdera regler för minskning av attackytan](evaluate-attack-surface-reduction.md)
