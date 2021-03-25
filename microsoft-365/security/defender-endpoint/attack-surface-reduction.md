---
title: Använd minskningsregler för attackytan för att förhindra skadlig smitta
description: Minskningsregler för attackytan kan förhindra sårbarheter från att använda appar och skript för att smitta enheter med skadlig programvara.
keywords: Minskningsregler för attackytan, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, prevention av smitta, Microsoft Defender för Endpoint, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 2bd8442dd8e119a57c490773b6e01a7c5f7adcac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075418"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Använd minskningsregler för attackytan för att förhindra skadlig smitta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="why-attack-surface-reduction-rules-are-important"></a>Varför det är viktigt att minska attackytans regler

Din organisations attackyta omfattar alla platser där en attack kan avslöja organisationens enheter eller nätverk. Att minska attackytan innebär att skydda organisationens enheter och nätverk, vilket gör att attacker inte hindras från att utföra attacker. Det kan hjälpa att konfigurera regler för att minska attackytan i Microsoft Defender för Endpoint!

Minskningsregler för attackytan riktar sig mot vissa programvarubeteenden, till exempel:

- Starta körbara filer och skript som försöker ladda ned eller köra filer.
- Köra obfuscated eller på annat sätt misstänkta skript. och 
- Utföra beteenden som appar normalt inte initierar under normalt normalt arbete.

Sådana programvarubeteenden kan ibland ses i legitima program. Men dessa beteenden anses ofta vara riskfyllda eftersom de ofta används av attackerare via skadlig programvara. Regler för att minska attackytan kan begränsa riskfyllda beteenden och skydda organisationen.

Mer information om hur du konfigurerar regler för att minska attackytan finns i [Aktivera minskningsregler för attackytor.](enable-attack-surface-reduction.md)

## <a name="assess-rule-impact-before-deployment"></a>Utvärdera påverkan på regeln före distribution  

Du kan utvärdera hur en minskningsregel för attackytan kan påverka nätverket genom att öppna säkerhetsrekommendationerna för den regeln i [hantering av hot och sårbarhet.](https://docs.microsoft.com/windows/security/threat-protection/#tvm) 

:::image type="content" source="images/asrrecommendation.png" alt-text="Säkerhetsreco för minskningsregel för attackytan":::

Kontrollera användareffekter i informationsfönstret om rekommendationen för att avgöra vilken procentandel av dina enheter som kan acceptera en ny princip som gör att regeln blockerar läge utan att påverka produktiviteten negativt.

## <a name="audit-mode-for-evaluation"></a>Granskningsläge för utvärdering

Använd [granskningsläge för](audit-windows-defender.md) att utvärdera hur minskning av attackytan skulle påverka organisationen om de var aktiverade. Kör först alla regler i granskningsläge så att du förstår hur de påverkar affärsprogrammen. Många affärsprogram är skrivna med begränsade säkerhetsproblem och de kan utföra uppgifter på sätt som verkar likna skadlig programvara. Genom att övervaka granskningsdata [och lägga till undantag för](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) nödvändiga program kan du distribuera minskningsregler för attackytor utan att minska produktiviteten.

## <a name="warn-mode-for-users"></a>Varningsläge för användare

(**NY**!) Innan varningslägesfunktioner aktiverades kunde minskningsregler för attackytor ställas in på antingen granskningsläge eller blockläge. Med det nya varningsläget kan användare se en dialogruta som anger att innehållet blockeras när innehåll blockeras av en minskningsregel för attackytor. I dialogrutan finns också ett alternativ för att ta bort blockeringen av innehållet. Användaren kan sedan försöka utföra åtgärden igen och åtgärden har slutförts. När en användare tar bort blockeringen av innehåll förblir innehållet oblockerade i 24 timmar och blockerar sedan meritförteckningar.

Varningsläge hjälper din organisation att ha regler för att minska attackytan på plats utan att hindra användarna från att komma åt det innehåll de behöver för att utföra sina uppgifter. 

### <a name="requirements-for-warn-mode-to-work"></a>Krav för att varningsläge ska fungera

Varningsläge stöds på enheter som kör följande versioner av Windows:
- [Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) eller senare
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) eller senare
 
Microsoft Defender Antivirus måste köras med realtidsskydd i [aktivt läge.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Kontrollera också att uppdateringar [för Microsoft Defender Antivirus och program mot skadlig programvara](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) är installerade.
- Lägsta krav för plattformsutgågår: `4.18.2008.9`  
- Lägsta krav för släppt motor: `1.1.17400.5`

Mer information och information om hur du får dina uppdateringar finns [i Uppdatering för Microsoft Defender-plattform mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)

### <a name="cases-where-warn-mode-is-not-supported"></a>Fall där varningsläge inte stöds

Varningsläge stöds inte för följande minskningsregler för attackytor:

- [Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d` )
- [Blockera beständighet via WMI-händelseprenumeration](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b` )
- [Använd avancerat skydd mot utpressningstrojaner](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35` )

Dessutom stöds inte varningsläge på enheter med äldre versioner av Windows. I sådana fall kommer minskningsregler för attackytan som är konfigurerade att köras i varningsläge att köras i blockläge.

## <a name="notifications-and-alerts"></a>Meddelanden och aviseringar

När en minskningsregel för attackytan utlöses visas ett meddelande på enheten. Du kan [anpassa meddelandet med](customize-attack-surface-reduction.md#customize-the-notification) företagets information och kontaktinformation.

När vissa minskningsregler för attackytan utlöses genereras dessutom varningar. 

Meddelanden och alla aviseringar som genereras kan visas i Microsoft Defender Säkerhetscenter ( ) och i Säkerhetscenter för [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Avancerad sökning och minskning av attackytor

Du kan använda avancerad sökning för att visa händelser för att minska attackytan. För att effektivisera mängden inkommande data kan endast unika processer för varje timme visas med avancerad sökning. Tiden för en minskning av attackytan är första gången som händelsen ses inom en timme.

Anta till exempel att en minskning av attackytan inträffat på 10 enheter under 14:00.00. Anta att den första händelsen inträffade kl. 02:15 och den sista kl. 02:45. Med avancerad sökning visas en instans av händelsen (även om den faktiskt ägde rum på 10 enheter) och tidsstämpeln är 14:15. 

Mer information om avancerad sökning finns i [Proaktivt sök efter hot med avancerad sökning.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Funktioner för att minska attackytan i alla Windows-versioner

Du kan ange minskningsregler för attackytan för enheter som kör någon av följande versioner av Windows:
- Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Även om minskningsregler för attackytor inte kräver en [Windows E5-licens](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)får du avancerade hanteringsfunktioner om du har Windows E5. Dessa funktioner är endast tillgängliga i Windows E5: övervakning, analys och arbetsflöden som är tillgängliga i Defender för [slutpunkt,](microsoft-defender-advanced-threat-protection.md)samt rapporterings- och konfigurationsfunktioner i [Säkerhetscenter för Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center) Dessa avancerade funktioner är inte tillgängliga med en Windows Professional- eller Windows E3-licens. Men om du har de licenserna kan du använda Loggboken och Microsoft Defender Antivirus-loggarna för att granska dina minskningsregelhändelser för attackytan.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Granska händelser för att minska attackytan i Microsoft Defender Säkerhetscenter

Defender för Endpoint tillhandahåller detaljerad rapportering för händelser och block som en del av scenarier för aviseringsundersökning.

Du kan fråga Defender om slutpunktsdata genom att använda [avancerad sökning](advanced-hunting-query-language.md). Om du kör granskningsläge [kan du](audit-windows-defender.md)använda avancerad sökning för att förstå hur minskningar av attackytor kan påverka din miljö.

Här är en exempelfråga:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Granska händelser för att minska attackytan i Windows Loggboken

Du kan granska Windows-händelseloggen om du vill visa händelser som genererats av minskningsregler för attackytan:

1. Ladda ned [utvärderingspaketet](https://aka.ms/mp7z2w) och extrahera filen *cfa-events.xml* till en lättillgänglig plats på enheten.
2. Ange orden, *Loggboken,* på Start-menyn för att öppna Windows Loggboken.
3. Under **Åtgärder** väljer du **Importera anpassad vy...**.
4. Välj filen *cfa-events.xml* där den extraherades. Du kan också [kopiera XML direkt.](event-views.md)
5. Välj **OK**.

Du kan skapa en anpassad vy som filtrerar händelser för att endast visa följande händelser, som alla är relaterade till kontrollerad mappåtkomst:

|Händelse-ID | Beskrivning |
|:---|:---|
|5007 | Händelse när inställningar ändras |
|1121 | Händelse när en regel ut sätts i blockläge |
|1122 | Händelse när en regel aktiveras i granskningsläge |

"engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system. Defender för slutpunkt är integrerad med Windows 10, så den här funktionen fungerar på alla enheter med Windows 10 installerat.

## <a name="attack-surface-reduction-rules"></a>Minskningsregler för attackytor

I följande tabell och underavsnitt beskrivs var och en av de 15 minskningsregler för attackytor. Minskningsregler för attackytor listas i alfabetisk ordning, efter regelnamn. 

Om du konfigurerar regler för att minska attackytan med grupprinciper eller PowerShell måste du ha GUID:er. Å andra sidan behöver du inte GUID:er om du använder Microsoft Endpoint Manager eller Microsoft Intune.


| Regelnamn | GUID | Undantag & mappar | Lägsta operativsystem som stöds |
|:-----|:-----:|:-----|:-----|
|[Blockera Adobe Reader från att skapa underordnade processer](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera alla Office-program från att skapa underordnade processer](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera att autentiseringsuppgifter stjäls från Windows lokala säkerhetsutfärdares undersystem (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera körbart innehåll från e-postklient och webbaserad e-post](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera körbara filer från att köras såvida de inte uppfyller ett villkor för en vän, ålder eller en betrodd lista](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera körning av potentiellt oönskade skript](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera Office-program från att skapa körbart innehåll](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera Office-program från att mata in kod i andra processer](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera Office-kommunikationsprogram från att skapa underordnade processer](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |Stöds |[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare  |
|[Blockera beständighet via WMI-händelseprenumeration](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | Stöds inte | [Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (version 18362) eller senare |
|[Blockera processskapanden som kommer från PSExec- och WMI-kommandon](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera icke betrodda och osignerade processer som körs från USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Blockera Win32 API-anrop från Office-makron](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |
|[Använd avancerat skydd mot utpressningstrojaner](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | Stöds | [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, version 16299) eller senare |

### <a name="block-adobe-reader-from-creating-child-processes"></a>Blockera Adobe Reader från att skapa underordnade processer

Den här regeln förhindrar attacker genom att blockera Adobe Reader från att skapa processer.

Genom social teknik eller sårbarheter kan skadlig programvara ladda ned och starta nyttolaster och bryta ut från Adobe Reader. Genom att blockera underordnade processer från att genereras av Adobe Reader förhindras skadlig programvara som försöker använda den som en vektor från att spridas.

Den här regeln infördes i: 
- [Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-namn: `Process creation from Adobe Reader (beta)`

Konfigurationshanterarens namn: Ännu inte tillgängligt

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Blockera alla Office-program från att skapa underordnade processer

Den här regeln blockerar Office-appar från att skapa underordnade processer. Office-apparna innehåller Word, Excel, PowerPoint, OneNote och Access.

Att skapa skadliga underordnade processer är en vanlig strategi för skadlig programvara. Skadlig programvara som utnyttjar Office som en vektor ofta kör VBA-makron och utnyttjar kod för att ladda ned och försöka köra fler nyttolaster. Men vissa legitima affärsprogram kan också generera underordnade processer i syfte att använda kommersiellt syfte, till exempel att ta bort en kommandotolk eller använda PowerShell för att konfigurera registerinställningar.

Den här regeln infördes i: 
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Office apps launching child processes`

Konfigurationshanterarens namn: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Blockera autentiseringsuppgifter som stjäls från Windows lokala säkerhetsutfärdares undersystem

Den här regeln förhindrar att autentiseringsuppgifter stjäls genom att låsning av undersystemet i Lokal säkerhetsutfärdare (LSASS).

LSASS autentiserar användare som loggar in på en Windows-dator. Microsoft Defender Credential Guard i Windows 10 förhindrar normalt försök att extrahera autentiseringsuppgifter från LSASS. Men vissa organisationer kan inte aktivera Credential Guard på alla sina datorer på grund av kompatibilitetsproblem med anpassade smartkortsdrivrutiner eller andra program som läses in på den lokala säkerhetsutfärdaren (LSA). I sådana fall kan attackerare använda hacka-verktyg som Mimikatz för att få fram lösenord med klartext och NTLM-hash från LSASS.

> [!NOTE]
> I vissa appar uppräkningar koden alla körprocesser och försöker öppna dem med uttömmande behörighet. Den här regeln nekar programåtgärden öppna och loggar information i säkerhetshändelseloggen. Den här regeln kan generera mycket brus. Om du har en app som bara räknar upp LSASS, men som inte har någon verklig påverkan på funktioner, behöver du INTE lägga till den i undantagslistan. Det är inte säkert att den här händelseloggposten indikerar något skadligt hot.

Den här regeln infördes i:
- [Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Flag credential stealing from the Windows local security authority subsystem`

Konfigurationshanterarens namn: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Blockera körbart innehåll från e-postklient och webbaserad e-post

Den här regeln blockerar följande filtyper från att startas från e-post som öppnas i Microsoft Outlook-programmet eller Outlook.com och andra populära webbaserade e-postleverantörer:

- Körbara filer (till exempel .exe, .dll eller .scr)
- Skriptfiler (till exempel en PowerShell.ps-, Visual Basic .vbs- eller JavaScript .js-fil)

Den här regeln infördes i: 
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [CB 1710 för Microsoft Endpoint Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager-namn: `Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> Regeln Blockera **körbart innehåll från e-postklient och webbaserad** e-post har följande alternativa beskrivningar, beroende på vilket program du använder:
> - Intune (konfigurationsprofiler): Körning av körbart innehåll (exe, dll, ps, js, vbs osv.) har släppts från e-post (webmail/mail client) (inga undantag).
> - Slutpunktshanteraren: Blockera hämtning av körbart innehåll från e-post- och webbaserade e-postklienter.
> - Grupprincip: Blockera körbart innehåll från e-postklient och webbaserad e-post.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Blockera körbara filer från att köras såvida de inte uppfyller ett villkor för en vän, ålder eller en betrodd lista

Den här regeln blockerar följande filtyper från att startas såvida de inte uppfyller särskilda villkor eller ålderskriterier, eller om de finns i en betrodd lista eller en undantagslista:

- Körbara filer (till exempel .exe, .dll eller .scr)

Det kan vara riskabelt att starta opålitliga eller okända körbara filer, eftersom det kanske inte står helt tydligt om filerna är skadliga.

> [!IMPORTANT]
> Du måste [aktivera moln levererat skydd om du](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) vill använda den här regeln. <br/><br/> Regeln Blockera **körbara** filer från att köras såvida de inte uppfyller ett villkor av hög ålder eller betrodd lista med GUID ägs av Microsoft och anges inte `01443614-cd74-433a-b99e-2ecdc07bfc25` av administratörer. Den här regeln använder moln levererat skydd för att regelbundet uppdatera sin betrodda lista.
>
>Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn) men du kan inte ange vilka regler eller undantag som gäller för.

Den här regeln infördes i: 
- [Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Executables that don't meet a prevalence, age, or trusted list criteria`

Konfigurationshanterarens namn: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Blockera körning av potentiellt oönskade skript

Den här regeln identifierar misstänkta egenskaper i ett intjänat skript.

Script obfuscation är en vanlig teknik som både författare av skadlig programvara och legitima program använder för att dölja immateriell egendom eller minska inläsningstider för skript. Författare som använder skadlig programvara använder också information för att göra skadlig kod svårare att läsa, vilket förhindrar en närmare granskning av människor och säkerhetsprogramvara.

Den här regeln infördes i:
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Obfuscated js/vbs/ps/macro code`

Konfigurationshanterarens namn: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll

Den här regeln förhindrar skript från att starta potentiellt skadligt hämtat innehåll. Skadlig programvara som skrivits i JavaScript eller VBScript fungerar ofta som en nedladdare för att hämta och starta annan skadlig programvara från Internet.

Även om det inte är vanligt använder verksamhetsbaserade program ibland skript för att ladda ned och starta installationsprogram.

Den här regeln infördes i:  
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `js/vbs executing payload downloaded from Internet (no exceptions)`

Konfigurationshanterarens namn: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Blockera Office-program från att skapa körbart innehåll

Den här regeln förhindrar att Office-program, till exempel Word, Excel och PowerPoint, skapar potentiellt skadligt körbart innehåll genom att blockera skadlig kod från att skrivas till hårddisken.

Skadlig programvara som missbrukar Office som en vektor kan försöka bryta ut ur Office och spara skadliga komponenter på disken. De här skadliga komponenterna skulle överleva en dator omstart och skulle finnas kvar på systemet. Därför försvaras den här regeln mot en vanlig beständig teknik.

Den här regeln infördes i: 
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [CB](https://docs.microsoft.com/configmgr/core/servers/manage/updates) 1710 (SCCM är nu Microsoft Endpoint Configuration Manager)

Intune-namn: `Office apps/macros creating executable content`

SCCM-namn: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Blockera Office-program från att mata in kod i andra processer

Den här regeln blockerar kodinjiceringsförsök från Office-appar i andra processer.

Attacker kan försöka använda Office-appar för att migrera skadlig kod till andra processer genom kodinjicering, så att koden kan masquerade som en ren process.

Det finns inga kända legitima affärssyften för att använda kodinjicering.

Den här regeln gäller för Word, Excel och PowerPoint.

Den här regeln infördes i: 
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Office apps injecting code into other processes (no exceptions)`

Konfigurationshanterarens namn: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Blockera Office-kommunikationsprogram från att skapa underordnade processer

Den här regeln förhindrar att Outlook skapar underordnade processer, samtidigt som legitima Outlook-funktioner tillåts.

Den här regeln skyddar mot social engineering-angrepp och förhindrar att sårbarheter i kod från säkerhetsproblem i Outlook utnyttjas. Det skyddar även mot [Outlook-regler och formulär sårbarheter](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) som attacker kan använda när en användares autentiseringsuppgifter har komprometterats.

> [!NOTE]
> Den här regeln gäller endast Outlook.com Outlook.

Den här regeln infördes i: 
- [Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-namn: `Process creation from Office communication products (beta)`

Konfigurationshanterarens namn: Inte tillgängligt

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Blockera beständighet via WMI-händelseprenumeration

Den här regeln förhindrar skadlig programvara från att använda WMI så att det inte går att hålla sig beständig på en enhet.

> [!IMPORTANT]
> Undantag för filer och mappar gäller inte för den här minskningsregeln för attackytor.

Fillösa hot använder olika taktiker för att hålla sig dold, för att undvika att synas i filsystemet och för att få periodisk körningskontroll. Vissa hot kan missbruket av WMI-lagringsplatsen och händelsemodellen för att förbli dold.

Den här regeln infördes i: 
- [Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune-namn: Inte tillgängligt

Konfigurationshanterarens namn: Inte tillgängligt

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Blockera processskapanden som kommer från PSExec- och WMI-kommandon

Den här regeln blockerar processer som skapats [via PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) [och WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) från att köras. Både PsExec och WMI kan köra kod via fjärrstyrd körning, så det finns en risk för att skadlig programvara ska kunna använda den här funktionen för kommando- och kontrolländamål eller för att sprida en smitta i organisationens nätverk.

> [!WARNING]
> Använd bara den här regeln om du hanterar dina enheter med [Intune eller en](https://docs.microsoft.com/intune) annan MDM-lösning. Den här regeln är inkompatibel med hantering genom [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) eftersom den här regeln blockerar WMI-kommandon som Configuration Manager-klienten använder för att fungera korrekt.

Den här regeln infördes i: 
- [Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune-namn: `Process creation from PSExec and WMI commands`

Konfigurationshanterarens namn: Ej tillämpligt

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Blockera icke betrodda och osignerade processer som körs från USB

Med den här regeln kan administratörer förhindra att osignerade eller icke betrodda körbara filer körs från flyttbara USB-enheter, inklusive SD-kort. Blockerade filtyper är körbara filer (till exempel .exe, .dll eller .scr)

Den här regeln infördes i: 
- [Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Untrusted and unsigned processes that run from USB`

Konfigurationshanterarens namn: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Blockera Win32 API-anrop från Office-makron

Den här regeln förhindrar VBA-makron från att anropa Win32-API:er.

Office VBA aktiverar Win32 API-anrop. Skadlig programvara kan missbruka den här funktionen, till exempel att [anropa Win32-API:er](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) för att starta skadlig kod utan att skriva något direkt på disken. De flesta organisationer förlitar sig inte på möjligheten att anropa Win32-API:er i sina dagliga funktioner, även om de använder makron på andra sätt.

Den här regeln infördes i:
- [Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Win32 imports from Office macro code`

Konfigurationshanterarens namn: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Använd avancerat skydd mot utpressningstrojaner

Den här regeln ger ett extra skydd mot utpressningstrojaner. Körbara filer som matas in i systemet skannas för att ta reda på om de är betrodda. Om filerna liknar utpressningstrojaner blockerar den här regeln dem från att köras, såvida de inte finns i en betrodd lista eller en undantagslista.

> [!NOTE]
> Du måste [aktivera moln levererat skydd om du](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) vill använda den här regeln.

Den här regeln infördes i: 
- [Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune-namn: `Advanced ransomware protection`

Konfigurationshanterarens namn: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>Se även

- [Vanliga frågor och svar om att minska attackytan](attack-surface-reduction-faq.md)
- [Aktivera minskningsregler för attackytor](enable-attack-surface-reduction.md)
- [Utvärdera minskningsregler för attackytor](evaluate-attack-surface-reduction.md)
- [Kompatibilitet med Microsoft Defender Antivirus med andra antivirus- och antimalwarelösningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
