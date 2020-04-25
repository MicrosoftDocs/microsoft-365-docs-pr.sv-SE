---
title: Enhetsövervakning och rapportering i Microsoft 365-säkerhetscentret
description: Beskriver hur du kan skydda dina enheter, uppdaterade och upptäcka potentiella hot i organisationen
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, övervaka, rapportera, enheter
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f8adb04e968f19c6b0577127e4f9c0ceb7d9e315
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804880"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Enhetsövervakning och rapportering i Microsoft 365-säkerhetscentret

Skydda dina enheter, uppdaterade och upptäck potentiella hot i säkerhetscentret Microsoft 365.

## <a name="view-device-alerts"></a>Visa enhetsaviseringar

Få aktuella aviseringar om intrångsaktivitet och andra hot på dina enheter från Microsoft Defender ATP (tillgängligt med en E5-licens). Microsoft 365-säkerhetscenter övervakar effektivt dessa aviseringar på en hög nivå med hjälp av ditt önskade arbetsflöde.

### <a name="monitor-high-impact-alerts"></a>Övervaka varningar med hög genomslagskraft

Varje Microsoft Defender ATP-avisering har en motsvarande allvarlighetsgrad (hög, medel, låg eller informativ) som anger dess potentiella inverkan på nätverket om den lämnas obevakad.  

Använd **allvarlighetsgradkortet för enhetsavisering** för att specifikt fokusera på aviseringar som är allvarligare och som kan kräva omedelbara svar. På det här kortet kan du visa mer information på Microsoft Defender Security Center-portalen.

![Allvarlighetskort för enhetsaviseringar](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Förstå källor till varningar

Microsoft Defender ATP utnyttjar data från ett brett spektrum av säkerhetssensorer och underrättelsekällor för att generera aviseringar. Den kan till exempel använda identifieringsinformation från Windows Defender Antivirus och antimalware från tredje part, samt din egen anpassade hotinformation som tillhandahålls via webbtjänst-API:et.

Kortet För identifiering av **enhetsaviseringsidentifiering** visar distributionen av aviseringar efter källa. Det här kortet kan hjälpa dig att spåra aktivitet som är relaterad till vissa källor, särskilt dina anpassade källor. Du kan också använda detta för att fokusera på aviseringar som kommer från sensorer som inte är konfigurerade för att automatiskt blockera skadlig aktivitet eller komponenter.

![Informationstecken för enhetsaviseringsidentifiering](../../media/device-alert-detection-sources.png)

På det här kortet kan du visa mer information på Microsoft Defender Security Center-portalen.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Förstå vilka typer av hot som utlöser aviseringar

Microsoft Defender ATP sorterar varje avisering i en kategori som representerar ett visst stadium i attackkedjan eller en typ av hotkomponent. En identifierad hotaktivitet kan till exempel kategoriseras som "lateral rörelse" för att indikera att det gjordes ett försök att nå andra enheter i nätverket. Aktiviteten har också sannolikt inträffat efter att angripare fått ett första fotfäste. När en hotkomponent upptäcks kan den antingen klassificeras som skadlig kod eller mer specifikt som ransomware, stöld av autentiseringsuppgifter eller andra typer av skadlig eller oönskad programvara.

Kortet **Enhetshotkategorier** visar fördelningen av aviseringar i dessa kategorier. Du kan använda den här informationen för att identifiera hotaktivitet, till exempel stöldförsök, som kan ha större inverkan jämfört med sociala ingenjörsförsök. Du kan också använda den här informationen för att övervaka potentiellt destruktiva hot som ransomware.

![Kort för kategorier av enhetshot](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Övervaka aktiva aviseringar

**Statuskortet för enhetsavisering** anger antalet aviseringar som inte har lösts och som kan kräva uppmärksamhet. På det här kortet kan du visa mer information på Microsoft Defender Security Center-portalen.

![Statuskort för enhetsavisering](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Övervaka klassificering av lösta aviseringar

När du löser en Microsoft Defender ATP-avisering kan säkerhetspersonalen ange om en avisering har verifierats som:

* En sann avisering som identifierar faktisk intrångsaktivitet eller hotkomponenter
* En falsk avisering som felaktigt har upptäckt normal aktivitet

**Klassificeringskortet för enhetsvarningar** visar om dina lösta aviseringar har klassificerats som sanna eller falska aviseringar. På det här kortet kan du visa mer information på Microsoft Defender Security Center-portalen.

I vissa fall är klassificeringsinformation inte tillgänglig för vissa aviseringar.

![Klassificeringskort för enhetsvarning](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Övervaka bestämning av lösta aviseringar

Förutom att klassificera om en avisering är sann eller falsk under upplösningen kan säkerhetspersonalen ange vilken typ av normal eller skadlig aktivitet som hittades när aviseringen validerades.

**Bestämningskortet för enhetsvarning** visar den bestämning som anges för varje varning.

* **APT**: avancerat beständigt hot, vilket indikerar att den upptäckta aktiviteten eller hotkomponenten är en del av en sofistikerad överträdelse som är utformad för att få fotfäste i det berörda nätverket  
* **Skadlig kod:** skadlig fil eller kod
* **Säkerhetspersonal**: normal verksamhet utförd av säkerhetspersonal
* **Säkerhetstestning:** aktivitet eller komponenter som utformats för att simulera faktiska hot och förväntas utlösa säkerhetssensorer och generera varningar
* **Oönskad programvara:** appar och annan programvara som inte anses vara skadlig, men som på annat sätt bryter mot policy- eller godtagbara användningsstandarder
* **Övrigt:** varje annan bestämning som inte omfattas av de angivna typerna

På det här kortet kan du visa mer information i Microsoft Defender Security Center.

![Bestämningskort för enhetsvarning](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Förstå vilka enheter som är i riskzonen

**Enhetsskydd** visar risknivån för enheter. Risknivån baseras på faktorer som typ och allvarlighetsgrad för aviseringar på enheten.

![Enhetsskyddskort](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Övervaka och rapportera status för Intune-hanterade enheter

Följande rapporter innehåller data från enheter som registrerats i Intune. Data från ej registrerade enheter ingår inte. Endast globala administratörer kan visa dessa kort.

Intune-registrerade enhetsdata omfattar:

* Enhetsefterlevnad
* Enheter med aktiv skadlig kod
* Typer av skadlig kod på enheter
* Skadlig kod på enheter
* Enheter med identifiering av skadlig programvara
* Användare med upptäckt av skadlig programvara

### <a name="monitor-device-compliance"></a>Övervaka enhetens efterlevnad

**Enhetsefterlevnad** visar hur många enheter som är registrerade i Intune följer konfigurationsprinciper.

![Kortet för enhetsefterlevnad](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Upptäck enheter med identifiering av skadlig programvara

**Identifiering av skadlig programvara** för enhet ger antalet Intune-registrerade enheter med skadlig kod som inte har lösts helt. Detta kan bero på väntande åtgärder, en omstart, en fullständig genomsökning, manuella användaråtgärder eller om reparationsåtgärden inte slutfördes.

![Identifieringskort för enhets skadlig programvara](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Förstå vilka typer av skadlig kod som har upptäckts

**Typer av skadlig kod på enheter** visar olika typer av skadlig kod som har upptäckts på enheter som registrerats i Intune. Du kan undersöka varje typ i Microsoft 365-säkerhetscentret.

![Typer av skadlig kod på enhetskort](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Förstå den specifika skadlig kod som upptäckts på dina enheter

**Skadlig kod på enheter** innehåller en lista över den specifika skadlig kod som har upptäckts på dina enheter.

![Malware på enheter kort](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Förstå vilka enheter som har mest skadlig kod

**Enheter med identifiering av skadlig programvara** visar vilka enheter som har flest identifieringar av skadlig kod. I Säkerhetscentret Microsoft 365 kan du undersöka om skadlig kod är aktiv, vem som använder enheten och dess hanteringsstatus i Intune.

![Enheter med kort för identifiering av skadlig kod](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Förstå vilka användare som har enheter med mest skadlig kod

**Användare med identifiering av skadlig programvara** visar användare med enheter som hade flest identifieringar av skadlig kod. I säkerhetscentret Microsoft 365 kan du se hur många enheter som tilldelas varje användare och mer information om varje enhet och vilken typ av skadlig kod som ska utföras.

![Användare med detektionskort för skadlig programvara](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>Övervaka och hantera ASR-regeldistribution och identifieringar

[Asr-regler (Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) förhindrar åtgärder och appar som vanligtvis används genom att använda skadlig kod för att infektera enheter. Dessa regler styr när och hur körbara filer kan köras. Du kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar, blockerar Win32 API-anrop från Office-makron eller blockerar processer som körs från USB-enheter.

![Attack yta minskningar kort](../../media/attack-surface-reduction-rules.png)

Attack **surface reduction rules-kortet** ger en översikt över distributionen av regler på dina enheter.

Det övre fältet på kortet visar det totala antalet enheter som finns i följande distributionslägen:

* **Blockläge:** enheter med minst en regel konfigurerad för att blockera upptäckt aktivitet
* **Granskningsläge:** enheter utan regler inställda på att blockera upptäckt aktivitet, men har minst en regel inställd på granskning av upptäckt aktivitet  
* **Av**: enheter med alla ASR-regler avstängda

Den nedre delen av det här kortet visar inställningar efter regel på dina enheter. Varje stapel anger antalet enheter som är inställda på att blockera eller granska identifiering eller har regeln helt avstängd.

### <a name="view-asr-detections"></a>Visa ASR-identifieringar

Om du vill visa detaljerad information om ASR-regelidentifieringar i nätverket väljer du **Visa identifieringar** på **attacksäkerhetsdeduktionsregelkortet.** Fliken **Identifieringar** på den detaljerade rapportsidan öppnas.

![Fliken Identifieringar](../../media/detections-tab.png)

Diagrammet högst upp på sidan visar identifieringar över tid som stackningsidentifieringar som antingen blockerades eller granskades. Tabellen längst ned visar de senaste identifieringarna. Använd följande information i tabellen för att förstå vilken typ av identifieringar:

* **Upptäckt fil:** filen, vanligtvis ett skript eller ett dokument, vars innehåll utlöste den misstänkta attackaktiviteten
* **Regel**: namn som beskriver attacken aktiviteter regeln är utformad för att fånga. Läs om befintliga ASR-regler
* **Källapp:** programmet som läste in eller utförde innehåll som utlöser den misstänkta attackaktiviteten. Detta kan vara ett legitimt program, till exempel webbläsare, ett Office-program eller ett systemverktyg som PowerShell
* **Utgivare**: leverantören som släppte källappen

### <a name="review-device-asr-rule-settings"></a>Granska asr-regelinställningar för enheten

På rapportsidan **Attack surface reduction rules** går du till fliken **Konfiguration** för att granska regelinställningar för enskilda enheter. Välj en enhet för att få detaljerad information om huruvida varje regel är i blockläge, granskningsläge eller helt avstängd.

![Fliken Konfiguration](../../media/configuration-tab.png)

Microsoft Intune tillhandahåller hanteringsfunktioner för ASR-reglerna. Om du vill uppdatera inställningarna väljer du **Kom igång** under **Konfigurera enheter** på fliken för att öppna enhetshanteringen på Intune.

### <a name="exclude-files-from-asr-rules"></a>Exkludera filer från ASR-regler

Microsoft 365 security center samlar in namnen på de [filer som du kanske vill utesluta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) från identifieringar genom regler för att minska angreppsytan. Genom att utesluta filer kan du minska falska positiva identifieringar och mer säkert distribuera regler för att minska angreppsytan i blockläge.

Undantagen hanteras på Microsoft Intune, men Microsoft 365 security center tillhandahåller ett analysverktyg som hjälper dig att förstå filerna. Om du vill börja samla in filer för uteslutning går du till fliken **Lägg till undantag** på rapportsidan Attack surface reduction **rules.**

>[!NOTE]  
>Verktyget analyserar identifieringar av alla regler för att minska angreppsytan, men [endast vissa regler stöder undantag](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).

![Fliken Lägg till undantag](../../media/add-exclusions-tab.png)

I tabellen visas alla filnamn som identifieras av reglerna för att minska angreppsytan. Du kan välja filer för att granska effekten av att utesluta dem:

* Hur många färre identifieringar
* Hur många färre enheter rapporterar identifieringarna

Om du vill hämta en lista över de markerade filerna med fullständiga sökvägar för uteslutning väljer du **Hämta uteslutningssökvägar**.

Loggar för ASR-regeln **Blockera autentiseringsuppgifter stjäla från Windows lokala säkerhetsmyndigheten undersystem (lsass.exe)** fånga källappen **lsass.exe**, en normal systemfil, som den identifierade filen. Därför innehåller den genererade listan över uteslutningssökvägar den här filen. Om du vill utesluta filen som utlöste den här regeln i stället för **lsass.exe**använder du sökvägen till källappen i stället för den identifierade filen.

Om du vill hitta källappen kör du följande [avancerade jaktfråga](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) för den här specifika regeln (identifieras med regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Kontrollera om du vill utesluta filer

Innan du utesluter en fil från ASR rekommenderar vi att du inspekterar filen för att avgöra om den verkligen inte är skadlig.

Om du vill granska en fil använder du [filinformationssidan](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) på Microsoft Defender Security Center. Sidan innehåller prevalensinformation samt virustotal antivirus upptäckt förhållandet. Du kan också använda sidan för att skicka filen för djupanalys.

Om du vill hitta en identifierad fil i Microsoft Defender Security Center söker du efter alla ASR-identifieringar med följande avancerade jaktfråga:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Använd **SHA1** eller **InitiatingProcessSHA1** i resultaten för att söka efter filen med hjälp av det universella sökfältet i Microsoft Defender Security Center.
